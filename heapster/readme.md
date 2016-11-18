# Table of Contents

* [API](#api)
* [Metrics](#metrics)

# API

version v1.2.0

* /api/v1/metric-export : Exports the latest point for all Heapster metrics
* /api/v1/metric-export-schema : Schema for metrics exported by heapster
* /api/v1/model/debug/allkeys : Get keys of all metric sets available
* /api/v1/model/metrics : Get a list of all available metrics for the Cluster entity
* /api/v1/model/metrics/{metric-name:*} : Export an aggregated cluster-level metric
  * start: Start time for requested metric, rfc 3399 format, such as 2016-11-10T06:00:00Z or 2016-11-10T06:00:00-07:00
  * end: End time for requested metric
  * labels: A comma-separated list of key:values pairs to use to search for a labeled metric
* /api/v1/model/nodes : Get a list of all nodes that have some current metrics
* /api/v1/model/nodes/{node-name}/metrics : Get a list of all available metrics for a Node entity
* /api/v1/model/nodes/{node-name}/metrics/{metric-name:*} : Export a node-level metric
  * start
  * end
  * labels
* /api/v1/model/nodes/{node-name}/freecontainers : Get a list of all non-pod containers with some metrics
* /api/v1/model/nodes/{node-name}/freecontainers/{container-name}/metrics : Get a list of all available metrics for a free Container entity
* /api/v1/model/nodes/{node-name}/freecontainers/{container-name}/metrics/{metric-name:*} : Export a container-level metric for a free container
  * start
  * end
  * labels
* /healthz : Return wheather heapster api is running well.
* /metrics : ? something related to prometheus

k8s only:

* /api/v1/model/namespaces : Get a list of all namespaces that have some current metrics
* /api/v1/model/namespaces/{namespace-name}/metrics : Get a list of all available metrics for a Namespace entity
* /api/v1/model/namespaces/{namespace-name}/metrics/{metric-name:*} : Export an aggregated namespace-level metric
  * start
  * end
  * labels
* /api/v1/model/namespaces/{namespace-name}/pods : Get a list of pods from the given namespace that have some metrics
* /api/v1/model/namespaces/{namespace-name}/pods/{pod-name}/metrics : Get a list of all available metrics for a Pod entity
* /api/v1/model/namespaces/{namespace-name}/pods/{pod-name}/metrics/{metric-name:*} : Export an aggregated pod-level metric
  * start
  * end
  * labels
* /api/v1/model/namespaces/{namespace-name}/pods/{pod-name}/containers/{container-name}/metrics : Get a list of all available metrics for a Pod entity
* /api/v1/model/namespaces/{namespace-name}/pods/{pod-name}/containers/{container-name}/metrics/{metric-name:*} : Export an aggregated metric for a Pod Container
  * start
  * end
  * labels
* /api/v1/model/namespaces/{namespace-name}/pod-list/{pod-list}/metrics/{metric-name:*} : Export a metric for all pods from the given list
  * pod-list: Comma separated list of pod names to lookup
  * start
  * end
  * labels

Note: no container list API, this is limited by kubernetes client.

APIs are registered and available but not recommended to use, they are v1alpha1, use v1 instead

* /apis/metrics/v1alpha1/nodes : Get a list of metrics for all available nodes.
  * labelSelector: A selector to restrict the list of returned objects by their labels. Defaults to everything.
* /apis/metrics/v1alpha1/nodes/{node-name}/ : Get a list of all available metrics for the specified node.
* /apis/metrics/v1alpha1/pods : Get metrics for all available pods.
* /apis/metrics/v1alpha1/namespaces/{namespace-name}/pods/ : Get a list of metrics for all available pods in the specified namespace.
  * labelSelector
* /apis/metrics/v1alpha1/namespaces/{namespace-name}/pods/{pod-name} : Get metrics for the specified pod in the specified namespace.


not available by default, you need to specify a historical source to enable them, historical_source should be one of sink uri:

* /api/v1/historical/pod-id/{pod-id}/metrics/{metric-name:*} : Export some pod-level metric aggregations
  * start
  * end
* /api/v1/historical/pod-id/{pod-id}/containers/{container-name}/metrics/{metric-name:*} : Export some aggregations for a Pod Container
  * start
  * end
* /api/v1/historical/pod-id-list/{pod-id-list}/metrics/{metric-name:*} : Export an aggregation for all pods from the given list
  * start
  * end
* /api/v1/historical/metrics-aggregated/{aggregations}/{metric-name:*} : Export some cluster-level metric aggregations
  * aggregations: A comma-separated list of requested aggregations, (average, max, min, median, count, 50-perc, 95-perc, 99-perc)
  * start
  * end
  * labels
* /api/v1/historical/nodes/{node-name}/metrics-aggregated/{aggregations}/{metric-name:*} : Export a node-level metric
  * start
  * end
  * labels
* /api/v1/historical/namespaces/{namespace-name}/metrics-aggregated/{aggregations}/{metric-name:*} : Export some namespace-level metric aggregations
  * start
  * end
  * labels
* /api/v1/historical/namespaces/{namespace-name}/pods/{pod-name}/metrics-aggregated/{aggregations}/{metric-name:*} : Export some pod-level metric aggregations
  * start
  * end
  * labels
* /api/v1/historical/namespaces/{namespace-name}/pods/{pod-name}/containers/{container-name}/metrics-aggregated/{aggregations}/{metric-name:*} : Export some aggregations for a Pod Container
  * start
  * end
  * labels
* /api/v1/historical/pod-id/{pod-id}/metrics-aggregated/{aggregations}/{metric-name:*} : Export some pod-level metric aggregations
  * start
  * end
  * labels
* /api/v1/historical/pod-id/{pod-id}/containers/{container-name}/metrics-aggregated/{aggregations}/{metric-name:*} : Export some aggregations for a Pod Container
  * start
  * end
  * labels
* /api/v1/historical/nodes/{node-name}/freecontainers/{container-name}/metrics-aggregated/{aggregations}/{metric-name:*} : Export a contsome iner-level metric aggregations for a free container
  * start
  * end
  * labels
* /api/v1/historical/namespaces/{namespace-name}/pod-list/{pod-list}/metrics-aggregated/{aggregations}/{metric-name:*} : Export some aggregations for all pods from the given list
  * start
  * end
  * labels
* /api/v1/historical/pod-id-list/{pod-id-list}/metrics-aggregated/{aggregations}/{metric-name:*} : Export an aggregation for all pods from the given list
  * start
  * end
  * labels

# Metrics

## cluster level metrics

curl http://localhost:8080/api/v1/proxy/namespaces/kube-system/services/heapster/api/v1/model/metrics

* cpu/limit 
* cpu/request
* cpu/usage_rate
* memory/limit
* memory/request
* memory/usage

## node level metrics

curl http://localhost:8080/api/v1/proxy/namespaces/kube-system/services/heapster/api/v1/model/nodes/bjws/metrics

* cpu/limit
* cpu/node_allocatable
* cpu/node_capacity
* cpu/node_reservation
* cpu/node_utilization
* cpu/request
* cpu/usage
* cpu/usage_rate
* memory/limit
* memory/major_page_faults
* memory/major_page_faults_rate
* memory/node_allocatable
* memory/node_capacity
* memory/node_reservation
* memory/node_utilization
* memory/page_faults
* memory/page_faults_rate
* memory/request
* memory/usage
* memory/working_set
* network/rx
* network/rx_errors
* network/rx_errors_rate
* network/rx_rate
* network/tx
* network/tx_errors
* network/tx_errors_rate
* network/tx_rate
* uptime

## namespace level metrics

curl http://localhost:8080/api/v1/proxy/namespaces/kube-system/services/heapster/api/v1/model/namespaces/kube-system/metrics

* cpu/limit 
* cpu/request
* cpu/usage_rate
* memory/limit
* memory/request
* memory/usage

## pod level metrics

curl http://localhost:8080/api/v1/proxy/namespaces/kube-system/services/heapster/api/v1/model/namespaces/kube-system/pods/influxdb-grafana-jriug/metrics

* cpu/limit
* cpu/request
* cpu/usage
* cpu/usage_rate
* memory/limit
* memory/major_page_faults
* memory/major_page_faults_rate
* memory/page_faults
* memory/page_faults_rate
* memory/request
* memory/usage
* memory/working_set
* network/rx
* network/rx_errors
* network/rx_errors_rate
* network/rx_rate
* network/tx
* network/tx_errors
* network/tx_errors_rate
* network/tx_rate
* uptime

## container level metrics

curl http://localhost:8080/api/v1/proxy/namespaces/kube-system/services/heapster/api/v1/model/namespaces/kube-system/pods/influxdb-grafana-jriug/containers/grafana/metrics

* cpu/limit
* cpu/request
* cpu/usage
* cpu/usage_rate
* memory/limit
* memory/major_page_faults
* memory/major_page_faults_rate
* memory/page_faults
* memory/page_faults_rate
* memory/request
* memory/usage
* memory/working_set
* uptime
