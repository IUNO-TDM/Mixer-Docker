# Mixer-Docker
Dockerfiles and Docker-Compose script for the machine setup.

Execute the following steps for an easy simple deployment of mixer machine for the iuno technology marketplace. We've setup a docker-compose script to deploy and configure all components within few steps.

Following software is needed:
- Docker: https://www.docker.com/
- Docker Compose: https://docs.docker.com/compose/ V1.13.0 or later
- Git: https://git-scm.com/

```
git clone https://github.com/IUNO-TDM/Mixer-Docker.git
cd Mixer-Docker
git submodule init
git submodule update
docker network create iuno-network
docker-compose up
```

# Custom Configs

Each module has config files under {module_name}/config (example: auth/config/docker_config.js)
Those files define host settings, oauth-credentials and more.
You can either adjust config parameters directly in those files or you can add your own configuration file in the same directory.
After adding your custom_config.js you'll have to update the ENV-Variable (TDM_{module_name}_CONFIG with in the Dockerfile of the targeted module.

The default configuration works straight with the TDM-Docker (https://github.com/IUNO-TDM/TDM-Docker) environment.
