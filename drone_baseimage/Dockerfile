FROM ubuntu:14.04

# Install git to enable drone to do the rest
RUN apt-get -q update \
    && apt-get install -y \
                            apt-cacher-ng \
                            bc \
                            binfmt-support \
                            build-essential \
                            debhelper \
                            debootstrap \
                            devscripts \
                            dosfstools \
                            fakeroot \
                            git \
                            git-core \
                            kpartx \
                            libncurses5-dev \
                            lvm2 \
                            python-pip \
                            python-pip \
                            qemu \
                            qemu-user-static \
                            quilt \
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

