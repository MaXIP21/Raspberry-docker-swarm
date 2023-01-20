# Raspberry Pi Swarm based docker-compose files for different services

I found a lot of bad examples how you can't run your stack in raspberry pi for that reason 
I created my own repository running on two Raspberry PI (1pc PI3 and 1pc PI4 4GB) docker swarm. 

My goal was to set up a swarm Deploy Traefik and Portainer then the create monitoring for my home servers as well as my desktops.
I added Consul as service discovery and a monitoring stack which consists of Prometheus, Grafana, Mariadb, Karma as a fancy monitoring and alerting system. 
I redirected my alerts to my slack channel just for fun. 

You can use my compose files to build your own home servers using these expensive (it's 2023) Raspberry Pis.

I try to create more description here from the process later on. 

Enjoy !!

## Create Docker networks for the stacks
```
docker network create --driver overlay traefik-public 
docker network create --driver overlay consul-bridge
```
