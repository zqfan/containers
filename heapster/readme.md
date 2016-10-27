# API

version v1.2.0

* /api/v1/metric-export : Exports the latest point for all Heapster metrics
* /api/v1/metric-export-schema : Schema for metrics exported by heapster
* /api/v1/model/debug/allkeys : Get keys of all metric sets available
* /api/v1/model/metrics : Get a list of all available metrics for the Cluster entity
* /api/v1/model/metrics/{metric-name:*} : Export an aggregated cluster-level metric
  * start: Start time for requested metric
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
* /metrics : ?

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

Note: no container list api

not available:

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

