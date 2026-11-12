# Open5GS Dockerized Core Network

Container definitions and Compose profiles for running Open5GS network functions in local core-network experiments.

## Included services

The repository builds or configures Open5GS functions such as AMF, AUSF, NRF, SMF, UPF, and WebUI, alongside MongoDB and monitoring services. Compose files cover a default setup and home/visited local-breakout variants.

## Requirements

- Docker Engine and Docker Compose
- A compatible Open5GS release
- Host networking/DNS configuration for the selected deployment
- The environment variables and configuration files referenced by the Compose files

The Compose configurations expect an `.env` file and use `OPEN5GS_VERSION`, but no environment template is included. Prepare those values and review exposed host ports before starting the stack.

## Start

From the repository root, select the deployment profile you intend to use and run its Compose file, for example:

```bash
docker compose -f docker-compose.yaml up --build
```

The repository is a deployment configuration, not a bundled Open5GS source distribution. The public Compose file contains static database credentials; rotate them and replace them with private configuration before exposing the services.
