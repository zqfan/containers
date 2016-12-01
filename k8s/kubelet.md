kubelet api default port 10255

# API

## stats

* /stats/ : Return root container stats
  * for i.e.: curl 'http://localhost:10255/stats/', [response example](examples/kubelet.api/stats.json)
* /stats/summary : Return stats summary
  * for i.e.: curl 'http://localhost:10255/stats/summary', [response example](examples/kubelet.api/stats.summary.json)
* /stats/container : Return non-kubernetes container stats
  * for i.e.: curl 'http://localhost:10255/stats/container', [response example](examples/kubelet.api/stats.container.json)
* /stats/POD_NAME/CONTAINER_NAME : Return kubernetes pod/container stats
  * not available in my env
* /stats/NAMESPACE_NAME/POD_NAME/UUID/CONTAINER_NAME : Return kubernetes pod/container stats
  * UUID can be any value except empty
  * for i.e.: curl 'http://localhost:10255/stats/kube-system/kubernetes-dashboard-v1.4.0-fdsn3/1/kubernetes-dashboard', [response example](examples/kubelet.api/stats.ns.pod.uid.container.json)
