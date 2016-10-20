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
