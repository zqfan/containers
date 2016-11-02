kubectl get event --all-namespaces -o json

# after scale up

~~~json
{
    "kind": "List",
    "apiVersion": "v1",
    "metadata": {},
    "items": [
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310b798ae7e3",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310b798ae7e3",
                "uid": "fdae5f6d-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "302",
                "creationTimestamp": "2016-11-02T09:30:28Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10336"
            },
            "reason": "Scheduled",
            "message": "Successfully assigned heapster-v1.2.0-2582472167-5q0s1 to kubernetes-node-1",
            "source": {
                "component": "default-scheduler"
            },
            "firstTimestamp": "2016-11-02T09:30:28Z",
            "lastTimestamp": "2016-11-02T09:30:28Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310bc1c36646",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310bc1c36646",
                "uid": "fe1aa034-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "306",
                "creationTimestamp": "2016-11-02T09:30:28Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{heapster}"
            },
            "reason": "Pulled",
            "message": "Container image \"gcr.io/google_containers/heapster:v1.2.0\" already present on machine",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:30:29Z",
            "lastTimestamp": "2016-11-02T09:30:29Z",
            "count": 2,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310bc5979461",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310bc5979461",
                "uid": "fe2452f1-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "304",
                "creationTimestamp": "2016-11-02T09:30:28Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{heapster}"
            },
            "reason": "Created",
            "message": "Created container with docker id 8af7ed924f48; Security:[seccomp=unconfined]",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:30:29Z",
            "lastTimestamp": "2016-11-02T09:30:29Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310bca029b54",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310bca029b54",
                "uid": "fe2f9438-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "305",
                "creationTimestamp": "2016-11-02T09:30:28Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{heapster}"
            },
            "reason": "Started",
            "message": "Started container with docker id 8af7ed924f48",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:30:29Z",
            "lastTimestamp": "2016-11-02T09:30:29Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310bce7f994d",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310bce7f994d",
                "uid": "fe3b0c4f-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "307",
                "creationTimestamp": "2016-11-02T09:30:28Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{eventer}"
            },
            "reason": "Created",
            "message": "Created container with docker id 0360bd24cc5b; Security:[seccomp=unconfined]",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:30:29Z",
            "lastTimestamp": "2016-11-02T09:30:29Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310bf849df2e",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310bf849df2e",
                "uid": "fea62bae-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "308",
                "creationTimestamp": "2016-11-02T09:30:29Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{eventer}"
            },
            "reason": "Started",
            "message": "Started container with docker id 0360bd24cc5b",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:30:30Z",
            "lastTimestamp": "2016-11-02T09:30:30Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310bf8afcad0",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310bf8afcad0",
                "uid": "fea7413b-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "312",
                "creationTimestamp": "2016-11-02T09:30:29Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{heapster-nanny}"
            },
            "reason": "Pulled",
            "message": "Container image \"gcr.io/google_containers/addon-resizer:1.6\" already present on machine",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:30:30Z",
            "lastTimestamp": "2016-11-02T09:30:32Z",
            "count": 2,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310bfcada89b",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310bfcada89b",
                "uid": "feb1eef5-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "310",
                "creationTimestamp": "2016-11-02T09:30:29Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{heapster-nanny}"
            },
            "reason": "Created",
            "message": "Created container with docker id 444a70823483; Security:[seccomp=unconfined]",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:30:30Z",
            "lastTimestamp": "2016-11-02T09:30:30Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310c6f523e87",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310c6f523e87",
                "uid": "ffd6fa4b-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "311",
                "creationTimestamp": "2016-11-02T09:30:31Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{heapster-nanny}"
            },
            "reason": "Started",
            "message": "Started container with docker id 444a70823483",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:30:32Z",
            "lastTimestamp": "2016-11-02T09:30:32Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310c7649d6c3",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310c7649d6c3",
                "uid": "ffe8ab3b-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "313",
                "creationTimestamp": "2016-11-02T09:30:31Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{eventer-nanny}"
            },
            "reason": "Created",
            "message": "Created container with docker id 0d6b8bb7ab64; Security:[seccomp=unconfined]",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:30:32Z",
            "lastTimestamp": "2016-11-02T09:30:32Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310cf81f732a",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310cf81f732a",
                "uid": "01351d88-a0df-11e6-b955-5254004d18f3",
                "resourceVersion": "314",
                "creationTimestamp": "2016-11-02T09:30:33Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{eventer-nanny}"
            },
            "reason": "Started",
            "message": "Started container with docker id 0d6b8bb7ab64",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:30:34Z",
            "lastTimestamp": "2016-11-02T09:30:34Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167.1483310b78649320",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167.1483310b78649320",
                "uid": "fdab65ad-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "301",
                "creationTimestamp": "2016-11-02T09:30:28Z"
            },
            "involvedObject": {
                "kind": "ReplicaSet",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167",
                "uid": "2ed509e7-a0ca-11e6-b955-5254004d18f3",
                "apiVersion": "extensions",
                "resourceVersion": "10334"
            },
            "reason": "SuccessfulCreate",
            "message": "Created pod: heapster-v1.2.0-2582472167-5q0s1",
            "source": {
                "component": "replicaset-controller"
            },
            "firstTimestamp": "2016-11-02T09:30:28Z",
            "lastTimestamp": "2016-11-02T09:30:28Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0.1483310b7777c305",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0.1483310b7777c305",
                "uid": "fda94fe0-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "300",
                "creationTimestamp": "2016-11-02T09:30:28Z"
            },
            "involvedObject": {
                "kind": "Deployment",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0",
                "uid": "89b36559-a0c8-11e6-b955-5254004d18f3",
                "apiVersion": "extensions",
                "resourceVersion": "10333"
            },
            "reason": "ScalingReplicaSet",
            "message": "Scaled up replica set heapster-v1.2.0-2582472167 to 2",
            "source": {
                "component": "deployment-controller"
            },
            "firstTimestamp": "2016-11-02T09:30:28Z",
            "lastTimestamp": "2016-11-02T09:30:28Z",
            "count": 1,
            "type": "Normal"
        }
    ]
}
~~~

# after scale down

~~~json
{
    "kind": "List",
    "apiVersion": "v1",
    "metadata": {},
    "items": [
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310b798ae7e3",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310b798ae7e3",
                "uid": "fdae5f6d-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "302",
                "creationTimestamp": "2016-11-02T09:30:28Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10336"
            },
            "reason": "Scheduled",
            "message": "Successfully assigned heapster-v1.2.0-2582472167-5q0s1 to kubernetes-node-1",
            "source": {
                "component": "default-scheduler"
            },
            "firstTimestamp": "2016-11-02T09:30:28Z",
            "lastTimestamp": "2016-11-02T09:30:28Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310bc1c36646",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310bc1c36646",
                "uid": "fe1aa034-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "306",
                "creationTimestamp": "2016-11-02T09:30:28Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{heapster}"
            },
            "reason": "Pulled",
            "message": "Container image \"gcr.io/google_containers/heapster:v1.2.0\" already present on machine",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:30:29Z",
            "lastTimestamp": "2016-11-02T09:30:29Z",
            "count": 2,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310bc5979461",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310bc5979461",
                "uid": "fe2452f1-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "304",
                "creationTimestamp": "2016-11-02T09:30:28Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{heapster}"
            },
            "reason": "Created",
            "message": "Created container with docker id 8af7ed924f48; Security:[seccomp=unconfined]",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:30:29Z",
            "lastTimestamp": "2016-11-02T09:30:29Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310bca029b54",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310bca029b54",
                "uid": "fe2f9438-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "305",
                "creationTimestamp": "2016-11-02T09:30:28Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{heapster}"
            },
            "reason": "Started",
            "message": "Started container with docker id 8af7ed924f48",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:30:29Z",
            "lastTimestamp": "2016-11-02T09:30:29Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310bce7f994d",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310bce7f994d",
                "uid": "fe3b0c4f-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "307",
                "creationTimestamp": "2016-11-02T09:30:28Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{eventer}"
            },
            "reason": "Created",
            "message": "Created container with docker id 0360bd24cc5b; Security:[seccomp=unconfined]",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:30:29Z",
            "lastTimestamp": "2016-11-02T09:30:29Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310bf849df2e",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310bf849df2e",
                "uid": "fea62bae-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "308",
                "creationTimestamp": "2016-11-02T09:30:29Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{eventer}"
            },
            "reason": "Started",
            "message": "Started container with docker id 0360bd24cc5b",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:30:30Z",
            "lastTimestamp": "2016-11-02T09:30:30Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310bf8afcad0",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310bf8afcad0",
                "uid": "fea7413b-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "312",
                "creationTimestamp": "2016-11-02T09:30:29Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{heapster-nanny}"
            },
            "reason": "Pulled",
            "message": "Container image \"gcr.io/google_containers/addon-resizer:1.6\" already present on machine",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:30:30Z",
            "lastTimestamp": "2016-11-02T09:30:32Z",
            "count": 2,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310bfcada89b",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310bfcada89b",
                "uid": "feb1eef5-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "310",
                "creationTimestamp": "2016-11-02T09:30:29Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{heapster-nanny}"
            },
            "reason": "Created",
            "message": "Created container with docker id 444a70823483; Security:[seccomp=unconfined]",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:30:30Z",
            "lastTimestamp": "2016-11-02T09:30:30Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310c6f523e87",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310c6f523e87",
                "uid": "ffd6fa4b-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "311",
                "creationTimestamp": "2016-11-02T09:30:31Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{heapster-nanny}"
            },
            "reason": "Started",
            "message": "Started container with docker id 444a70823483",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:30:32Z",
            "lastTimestamp": "2016-11-02T09:30:32Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310c7649d6c3",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310c7649d6c3",
                "uid": "ffe8ab3b-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "313",
                "creationTimestamp": "2016-11-02T09:30:31Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{eventer-nanny}"
            },
            "reason": "Created",
            "message": "Created container with docker id 0d6b8bb7ab64; Security:[seccomp=unconfined]",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:30:32Z",
            "lastTimestamp": "2016-11-02T09:30:32Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483310cf81f732a",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483310cf81f732a",
                "uid": "01351d88-a0df-11e6-b955-5254004d18f3",
                "resourceVersion": "314",
                "creationTimestamp": "2016-11-02T09:30:33Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{eventer-nanny}"
            },
            "reason": "Started",
            "message": "Started container with docker id 0d6b8bb7ab64",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:30:34Z",
            "lastTimestamp": "2016-11-02T09:30:34Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483316a5a2dc4fc",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483316a5a2dc4fc",
                "uid": "f044859a-a0df-11e6-b955-5254004d18f3",
                "resourceVersion": "317",
                "creationTimestamp": "2016-11-02T09:37:15Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{heapster}"
            },
            "reason": "Killing",
            "message": "Killing container with docker id 8af7ed924f48: Need to kill pod.",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:37:15Z",
            "lastTimestamp": "2016-11-02T09:37:15Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483316a5adadb42",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483316a5adadb42",
                "uid": "f0462d35-a0df-11e6-b955-5254004d18f3",
                "resourceVersion": "318",
                "creationTimestamp": "2016-11-02T09:37:15Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{eventer-nanny}"
            },
            "reason": "Killing",
            "message": "Killing container with docker id 0d6b8bb7ab64: Need to kill pod.",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:37:15Z",
            "lastTimestamp": "2016-11-02T09:37:15Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483316a5d615d4e",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483316a5d615d4e",
                "uid": "f04ca92b-a0df-11e6-b955-5254004d18f3",
                "resourceVersion": "319",
                "creationTimestamp": "2016-11-02T09:37:15Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{heapster-nanny}"
            },
            "reason": "Killing",
            "message": "Killing container with docker id 444a70823483: Need to kill pod.",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:37:15Z",
            "lastTimestamp": "2016-11-02T09:37:15Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167-5q0s1.1483316a5dda17f3",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167-5q0s1.1483316a5dda17f3",
                "uid": "f04ddb26-a0df-11e6-b955-5254004d18f3",
                "resourceVersion": "320",
                "creationTimestamp": "2016-11-02T09:37:15Z"
            },
            "involvedObject": {
                "kind": "Pod",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167-5q0s1",
                "uid": "fdaa4328-a0de-11e6-b955-5254004d18f3",
                "apiVersion": "v1",
                "resourceVersion": "10338",
                "fieldPath": "spec.containers{eventer}"
            },
            "reason": "Killing",
            "message": "Killing container with docker id 0360bd24cc5b: Need to kill pod.",
            "source": {
                "component": "kubelet",
                "host": "kubernetes-node-1"
            },
            "firstTimestamp": "2016-11-02T09:37:15Z",
            "lastTimestamp": "2016-11-02T09:37:15Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167.1483310b78649320",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167.1483310b78649320",
                "uid": "fdab65ad-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "301",
                "creationTimestamp": "2016-11-02T09:30:28Z"
            },
            "involvedObject": {
                "kind": "ReplicaSet",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167",
                "uid": "2ed509e7-a0ca-11e6-b955-5254004d18f3",
                "apiVersion": "extensions",
                "resourceVersion": "10334"
            },
            "reason": "SuccessfulCreate",
            "message": "Created pod: heapster-v1.2.0-2582472167-5q0s1",
            "source": {
                "component": "replicaset-controller"
            },
            "firstTimestamp": "2016-11-02T09:30:28Z",
            "lastTimestamp": "2016-11-02T09:30:28Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0-2582472167.1483316a384a2c90",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0-2582472167.1483316a384a2c90",
                "uid": "f03b4188-a0df-11e6-b955-5254004d18f3",
                "resourceVersion": "316",
                "creationTimestamp": "2016-11-02T09:37:14Z"
            },
            "involvedObject": {
                "kind": "ReplicaSet",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0-2582472167",
                "uid": "2ed509e7-a0ca-11e6-b955-5254004d18f3",
                "apiVersion": "extensions",
                "resourceVersion": "10791"
            },
            "reason": "SuccessfulDelete",
            "message": "Deleted pod: heapster-v1.2.0-2582472167-5q0s1",
            "source": {
                "component": "replicaset-controller"
            },
            "firstTimestamp": "2016-11-02T09:37:14Z",
            "lastTimestamp": "2016-11-02T09:37:14Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0.1483310b7777c305",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0.1483310b7777c305",
                "uid": "fda94fe0-a0de-11e6-b955-5254004d18f3",
                "resourceVersion": "300",
                "creationTimestamp": "2016-11-02T09:30:28Z"
            },
            "involvedObject": {
                "kind": "Deployment",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0",
                "uid": "89b36559-a0c8-11e6-b955-5254004d18f3",
                "apiVersion": "extensions",
                "resourceVersion": "10333"
            },
            "reason": "ScalingReplicaSet",
            "message": "Scaled up replica set heapster-v1.2.0-2582472167 to 2",
            "source": {
                "component": "deployment-controller"
            },
            "firstTimestamp": "2016-11-02T09:30:28Z",
            "lastTimestamp": "2016-11-02T09:30:28Z",
            "count": 1,
            "type": "Normal"
        },
        {
            "kind": "Event",
            "apiVersion": "v1",
            "metadata": {
                "name": "heapster-v1.2.0.1483316a376a3cf6",
                "namespace": "kube-system",
                "selfLink": "/api/v1/namespaces/kube-system/events/heapster-v1.2.0.1483316a376a3cf6",
                "uid": "f03840c3-a0df-11e6-b955-5254004d18f3",
                "resourceVersion": "315",
                "creationTimestamp": "2016-11-02T09:37:14Z"
            },
            "involvedObject": {
                "kind": "Deployment",
                "namespace": "kube-system",
                "name": "heapster-v1.2.0",
                "uid": "89b36559-a0c8-11e6-b955-5254004d18f3",
                "apiVersion": "extensions",
                "resourceVersion": "10790"
            },
            "reason": "ScalingReplicaSet",
            "message": "Scaled down replica set heapster-v1.2.0-2582472167 to 1",
            "source": {
                "component": "deployment-controller"
            },
            "firstTimestamp": "2016-11-02T09:37:14Z",
            "lastTimestamp": "2016-11-02T09:37:14Z",
            "count": 1,
            "type": "Normal"
        }
    ]
}
~~~
