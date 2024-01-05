# Raspberry Pi Swarm based docker-compose files for different services

I found many BAD examples of running Docker on a Raspberry Pi, especially in a swarm. Therefore, I created my repository, utilizing two Raspberry Pis (one Pi3 and one Pi4 4GB), to establish a small, yet enjoyable home infrastructure running in a Docker swarm.

My objective was to deploy Traefik and Portainer in the swarm, followed by creating monitoring for both my home servers and desktops. I incorporated Consul for service discovery and implemented a monitoring stack featuring Prometheus, Grafana, Mariadb, and Karma for an aesthetically pleasing monitoring and alerting system. For a touch of fun, I redirected my alerts to my Slack channel.

Feel free to use my compose files to build your own home servers with these cost-effective Raspberry Pis in 2023. I'll provide more detailed descriptions of the process later on. Enjoy!

## Create Docker networks for the stacks
```
docker network create --driver overlay traefik-public 
docker network create --driver overlay consul-bridge
docker network create --driver overlay vault-network
```
