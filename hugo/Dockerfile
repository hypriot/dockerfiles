FROM ubuntu:14.04

# Install pygments (for syntax highlighting) and git
RUN apt-get -qq update \
    && DEBIAN_FRONTEND=noninteractive apt-get -qq install -y --no-install-recommends python-pygments git openssh-client ca-certificates\
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Download and install hugo
ENV HUGO_VERSION 0.13
ENV HUGO_BINARY hugo_${HUGO_VERSION}_linux_amd64

ADD https://github.com/spf13/hugo/releases/download/v${HUGO_VERSION}/${HUGO_BINARY}.tar.gz /usr/local/
RUN tar xzf /usr/local/${HUGO_BINARY}.tar.gz -C /usr/local/ \
    && ln -s /usr/local/${HUGO_BINARY}/${HUGO_BINARY} /usr/local/bin/hugo \
    && rm /usr/local/${HUGO_BINARY}.tar.gz
