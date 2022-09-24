# Signal TLS Proxy for Docker Swarm and Traefik

To run this Signal TLS proxy, you will need the following setup:
- a host that has ports 80 and 443 available
- a domain name that points to that host
- a [Docker Swarm Node](https://docs.docker.com/engine/swarm/) running on that host
- a [Traefik reverse proxy](https://traefik.io/) running on that node
- valid TLS certificates for that domain name

## Setup
1. Clone this repository
2. Modify the `docker-stack.yml` file to use your domain name and traefik labels
3. Run `docker stack deploy -c docker-stack.yml signal-tls-proxy`
4. Run `docker service logs -f signal-tls-proxy` to see the logs
5. Wait for the service to start

Your proxy is now running! You can share this with the URL `https://signal.tube/#<your_host_name>`

## Setup without Docker Swarm
If you don't want to use Docker Swarm, you can run the proxy with Docker Compose:
1. Clone this repository
2. Modify the `docker-compose.yml` file to use your domain name and traefik labels
3. Run `docker-compose up -d`
4. Run `docker-compose logs -f` to see the logs