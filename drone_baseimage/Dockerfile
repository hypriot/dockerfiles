FROM ubuntu:14.04

# Install git to enable drone to do the rest
RUN apt-get -q update \
    && apt-get install -y git \
                          git-core \
                          python-pip \
                          build-essential \
                          libncurses5-dev \
                          tree \
                          binfmt-support \
                          qemu \
                          qemu-user-static \
                          debootstrap \
                          kpartx \
                          lvm2 \
                          dosfstools \
                          apt-cacher-ng \
    && locale-gen en_US.UTF-8 \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV TERM xterm
