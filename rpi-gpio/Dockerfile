# Pull base image
FROM registry.hypriot.com/rpi-dockerize
MAINTAINER Stefan Scherer <stefan@hypriot.com>

# Install wiringPi
RUN apt-get update && apt-get install -y build-essential sudo
RUN git clone git://git.drogon.net/wiringPi
RUN cd wiringPi && ./build

# Define working directory
WORKDIR /data

# Define default command
CMD ["gpio"]
