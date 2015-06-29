Docker Compose Example
======================

This `docker-compose` sample project is based on `compose-test` example from
Compose documentation.

In addition to the "web" and "redis" containers it also has a reverse proxy
based on [jwilder/nginx-proxy](https://github.com/jwilder/nginx-proxy) image.
The reverse proxy is able to automatically detect new web containers when
those are launched using `docker-compose scale web=N` command.

The changes to the original example include "web" container port mapping
which does not specify the host port so it is possible to launch several
containers of that kind.

The "web" container has also 2 environment variables:
* `VIRTUAL_HOST` - specifies the host name/IP address where the reverse
proxy is available at; this value may have to be changed to reflect your
environment
* `VIRTUAL_PORT` - the port on which the "web" container listens to requests.

