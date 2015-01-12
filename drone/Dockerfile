# Pull from base Ubuntu image
FROM ubuntu

# Do system updates and install dependencies
RUN apt-get update
#RUN apt-get -y upgrade
RUN sudo apt-get -y install git
RUN apt-get clean

# Download Drone.io
ADD http://downloads.drone.io/master/drone.deb drone.deb
RUN dpkg -i drone.deb && rm -f drone.deb

# Expose the Drone.io port
EXPOSE 80

ENV DRONE_SERVER_PORT 0.0.0.0:80
ENV DRONE_DATABASE_DATASOURCE /var/lib/drone/drone.sqlite

# Define our GitHub OAuth keys below
ENV DRONE_GITHUB_CLIENT xxx
ENV DRONE_GITHUB_SECRET xxx

# The command we'll be running when the container starts
CMD /usr/local/bin/droned