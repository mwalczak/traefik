### Example how to expose docker services with traefik for local development.

1. Create docker network for traefik use:
```shell
docker network create traefik
```

2. Run traefik:
```shell
docker-compose -f docker-compose.traefik.yml up -d
```

3. Run any other services, for example:
```shell
docker-compose -f docker-compose.service.yml up -d
```

4. Access traefik dashboard: http://localhost:8080/dashboard/

5. Check service is working by:
```shell
curl -H Host:exposed.docker.localhost http://127.0.0.1
```
or open browser: http://exposed.docker.localhost/

### Summary:
1. Service containers to expose must be connected to traefik network
2. Internal services should be connected only to default network
3. Check mailcatcher service example to see how to connect custom port