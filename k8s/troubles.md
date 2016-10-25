### kubeadm init hangs on ubuntu 16.04

~~~
# kubeadm init
<master/tokens> generated token: "c0c47b.c7ce7a73cc02bcfc"
<master/pki> created keys and certificates in "/etc/kubernetes/pki"
<util/kubeconfig> created "/etc/kubernetes/admin.conf"
<util/kubeconfig> created "/etc/kubernetes/kubelet.conf"
<master/apiclient> created API client configuration
<master/apiclient> created API client, waiting for the control plane to become ready
~~~

if you're behind a proxy, you will need to set proxy to docker before running `kubeadm init`, [https://docs.docker.com/engine/admin/systemd/#http-proxy](https://docs.docker.com/engine/admin/systemd/#http-proxy):

~~~
sudo mkdir /etc/systemd/system/docker.service.d
sudo cat << EOF > /etc/systemd/system/docker.service.d/http-proxy.conf
[Service]
Environment="HTTP_PROXY=http://proxy.example.com:80/"
Environment="HTTPS_PROXY=https://proxy.example.com:80/"
EOF
sudo systemctl daemon-reload
sudo systemctl restart docker
~~~

the install steps:

~~~
apt-get install -y docker.io kubelet kubeadm kubectl kubernetes-cni containerd ubuntu-fan runc
kubeadm init --api-advertise-addresses=16.187.242.140
kubectl taint nodes --all dedicated-
kubectl apply -f https://git.io/weave-kube
~~~

### unable to create pod network

~~~
# kubectl apply -f https://git.io/weave-kube
Unable to connect to the server: net/http: TLS handshake timeout
~~~

you need to check the http proxy in root user environment.

### unable to open kubernetes-dashboard

after install kubernetes-dashboard by `kubectl create -f https://rawgit.com/kubernetes/dashboard/master/src/deploy/kubernetes-dashboard.yaml`, and open http://master-ip/ui in browser, it always return 401 Unauthorized.

you can use `kubectl describe services kubernetes-dashboard --namespace=kube-system` to check the NodePort to access it as a workaround

~~~
$ kubectl describe services kubernetes-dashboard --namespace=kube-system
Name:                   kubernetes-dashboard
Namespace:              kube-system
Labels:                 app=kubernetes-dashboard
Selector:               app=kubernetes-dashboard
Type:                   NodePort
IP:                     100.73.120.141
Port:                   <unset> 80/TCP
NodePort:               <unset> 32098/TCP
Endpoints:              10.32.0.16:9090
Session Affinity:       None
~~~

for this case, you can use http://master-ip:32098 to access kubernetes-dashboard
ref: [https://github.com/kubernetes/dashboard/issues/692](https://github.com/kubernetes/dashboard/issues/692)

### unable to open heapster grafana ui

after

~~~
# use canal network
kubectl apply -f https://raw.githubusercontent.com/tigera/canal/master/k8s-install/kubeadm/canal.yaml
git clone https://github.com/kubernetes/heapster
cd heapster
kubectl create -f deploy/kube-config/influxdb/
~~~

grafana is not available, even with NodePort

* remove GF_SERVER_ROOT_URL doesn't work [https://github.com/kubernetes/heapster/issues/1316](https://github.com/kubernetes/heapster/issues/1316)
* use canal network doesn't work [http://stackoverflow.com/questions/37993263/grafana-not-showing-in-kubernetes-heapster](http://stackoverflow.com/questions/37993263/grafana-not-showing-in-kubernetes-heapster)
* make addons false doesn't work [http://stackoverflow.com/questions/38354962/kubernetes-keeps-removing-heapster-grafana-services-due-to-already-used-nodepo](http://stackoverflow.com/questions/38354962/kubernetes-keeps-removing-heapster-grafana-services-due-to-already-used-nodepo)
* specify protocol doesn't work [http://stackoverflow.com/questions/33767736/kubernetes-endpoints-throw-serviceunavailable](http://stackoverflow.com/questions/33767736/kubernetes-endpoints-throw-serviceunavailable)
