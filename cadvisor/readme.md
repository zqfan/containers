cadvisor is installed by default, node port is 4194 by default.

# API

read [official api doc](https://github.com/google/cadvisor/blob/master/docs/api.md) first.

* /api/v1.3/machine
  * for i.e.: curl 'http://localhost:4194/api/v1.3/machine', [response example](api.response.examples/api.v1.3.machine.json)
* /api/v1.3/containers
  * for i.e.: curl 'http://localhost:4194/api/v1.3/containers', [response example](api.response.examples/api.v1.3.containers.json)
* /api/v1.3/containers/CONTAINER_FULL_NAME
  * for i.e.: curl 'http://localhost:4194/api/v1.3/containers/system.slice/var-lib-docker-containers-dea517ff22c3df176eecc733a4d78359d0c48b61420cb466976deeeee7ab6231-shm.mount', [response example](api.response.examples/api.v1.3.containers.CONTAINER_NAME.json)
  * I don't know where to get this full container name yet, maybe composite by myself? this one is take from /docker response
* /api/v1.3/docker
  * for i.e.: curl 'http://localhost:4194/api/v1.3/docker', [response example](api.response.examples/api.v1.3.docker.json)
