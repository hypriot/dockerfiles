FROM ubuntu:14.04

# Install git to enable drone to do the rest
RUN apt-get -q update \
    && apt-get git git-core -y \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
