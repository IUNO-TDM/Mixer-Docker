FROM gcc:latest


# Install dependencies
RUN apt-get update
RUN apt-get install -y \
libboost-all-dev

# Create app directory

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

COPY PumpControl /usr/src/app

RUN make

CMD cd build && ./pumpcontrol.out --simulation=true

EXPOSE 9002

