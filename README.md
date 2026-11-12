# Open5GS Dockerized Core Network

Dockerfiles and Compose profiles for local Open5GS core-network experiments. The profiles combine Open5GS functions with MongoDB, WebUI, Prometheus, and home/visited local-breakout configurations.

## Services and profiles

The Compose files define core functions including AMF, AUSF, NRF, SMF, and UPF, plus database, web, and monitoring components. Separate Compose configurations describe default and local-breakout layouts. Select one deployment profile and review its network, port, and bind-mount assumptions before starting it.

## Requirements and configuration

- Docker Engine and Docker Compose
- A compatible Open5GS release/build configuration
- Host networking, DNS, and service-address settings for the selected topology
- The environment values and configuration files referenced by Compose

Compose expects an .env file containing OPEN5GS_VERSION, but the repository does not include an environment template. Prepare that variable and any required host configuration from the selected Compose file before startup.

## Start a selected profile

For the default profile:

```bash
docker compose -f docker-compose.yaml up --build
```

Use the corresponding Compose file for the home/visited local-breakout variants. Stop the chosen stack with docker compose down using the same file.

This repository provides container definitions, not an Open5GS source distribution. The public Compose configuration contains static MongoDB/Mongo Express credentials. Treat them as exposed, rotate them if reused, and replace them with private local configuration before starting services.