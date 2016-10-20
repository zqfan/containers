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
