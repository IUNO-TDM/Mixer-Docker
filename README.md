# Mixer-Docker
Dockerfiles and Docker-Compose script for the machine setup.

Execute the following steps for an easy simple deployment of mixer machine for the iuno technology marketplace. We've setup a docker-compose script to deploy and configure all components within few steps.

Following software is needed:
- Docker: https://www.docker.com/
- Docker Compose: https://docs.docker.com/compose/ V1.13.0 or later
- Git: https://git-scm.com/

```
git clone https://github.com/IUNO-TDM/Mixer-Docker.git
cd TDM-Docker
git submodule init
git submodule update --remote --merge
docker network create iuno-network
docker-compose up
```
