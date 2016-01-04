## Installing Prerequisites

## Inspection
### Consul Registered Services

```shell
curl http://`docker-machine ip default 2>/dev/null`:8500/v1/catalog/services
```

### Visit LB In Default Browser

```shell
open "http://`docker-machine ip default 2>/dev/null`/"
```

## Gotchas
* The auto-detected advertise IP for Consul-in-Docker on Boot2docker does not appear to be routable from the Nginx container. Use the following to look up the IP to set for `-advertise`:

```shell
docker-machine ssh default ifconfig eth0 | grep 'inet addr'
```
