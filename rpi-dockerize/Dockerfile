# Pull base image
FROM resin/rpi-raspbian:wheezy
MAINTAINER Stefan Scherer <stefan@hypriot.com>

# Install dockerize
RUN apt-get update && \
    apt-get install -y --no-install-recommends python python-pip git ca-certificates rsync binutils && \
    rm -rf /var/lib/apt/lists/* && \
    git clone https://github.com/larsks/dockerize
    cd dockerize && \
    sed -i '/copying file /i \ \ \ \ \ \ \ \ dst = dst.replace("/usr/local/lib/","/usr/lib/")' dockerize/dockerize.py && \
    python setup.py install

# Define working directory
WORKDIR /data

# Define default command
CMD ["dockerize"]
