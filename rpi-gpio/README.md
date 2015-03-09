# Build `gpio` binary from wiringPi and dockerize it

This Dockerfile installs []() and compiles the `gpio` binary.

## Create Docker image

First we create the Docker image with all the build tools needed.

```bash
$ docker build -t rpi-gpio-builder .
```

The final binary is at `/usr/local/bin/gpio` in the docker image.

## Dockerize it

Now create a minimal Docker image with only the `gpio` binary with

```bash
$ docker run -v /var/run/docker.sock:/var/run/docker.sock -v /usr/bin/docker:/usr/bin/docker -v /lib/arm-linux-gnueabihf/libdevmapper.so.1.02.1:/lib/arm-linux-gnueabihf/libdevmapper.so.1.02.1 -ti rpi-gpio-builder dockerize -t hypriot/rpi-gpio /usr/local/bin/gpio
```

## Check output

```bash
$ docker images
REPOSITORY                           TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
hypriot/rpi-gpio                     latest              522011be58d3        2 minutes ago       2.069 MB
```

## Test it

To access the GPIO ports from within the Docker container must be called in privileged mode.

```bash
$ docker run --privileged -ti hypriot/rpi-gpio readall
```
