FROM ubuntu:14.04

# Let's start with some basic stuff.
RUN apt-get update -qq && apt-get install -qqy \
		apt-transport-https \
		ca-certificates \
		curl \
		lxc \
		iptables \
		python \
                git-core \
		python-pip \
                tree \
                xzip \
                zip

RUN locale-gen en_US.UTF-8 \
&& apt-get clean \
&& rm -rf /var/lib/apt/lists/* \
&& pip install awscli

ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV TERM xterm


# Install Docker from Docker Inc. repositories.
RUN curl -sSL https://get.docker.com/ubuntu/ | sh

# Install the magic wrapper.
ADD https://raw.githubusercontent.com/jpetazzo/dind/master/wrapdocker /usr/local/bin/wrapdocker
#ADD ./wrapdocker /usr/local/bin/wrapdocker
RUN chmod +x /usr/local/bin/wrapdocker


# Define additional metadata for our image.
VOLUME /var/lib/docker
CMD ["wrapdocker"]
