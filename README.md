# Raspberry Pi Swarm based docker-compose files for different services


Create Docker networks for the stacks
```
docker network create --driver overlay traefik-public 
docker network create --driver overlay consul-bridge
```
