FROM ubuntu:14.04

# Install git to enable drone to do the rest
RUN apt-get -q update \
    && apt-get git git-core -y \
    && locale-gen en_US.UTF-8 \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV TERM xterm
