FROM gcc:latest


# Install dependencies
RUN apt-get update
RUN apt-get install -y \
libboost-all-dev

# Create app directory

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

COPY PumpControl /usr/src/app
COPY config/ /root/

RUN make ENCRYPTION=off REALDRIVERS=off

CMD cd build && ./pumpcontrol.out --driver=simulation

EXPOSE 9002

