FROM node:boron
RUN npm install pm2 -g

# Create app directory

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

# Bundle app source

COPY MixerControl/MixerControl-app /usr/src/app

# Copy custom configs

COPY config/ /usr/src/app/config/

# Install app dependencies
RUN npm install
RUN npm install -g @angular/cli

RUN ng build

# Set ENV Variables
ENV TDM_MIXER_CONFIG config_docker
ENV NODE_ENV docker

EXPOSE 3000

CMD [ "pm2-docker", "npm", "--", "start" ]