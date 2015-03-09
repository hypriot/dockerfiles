# Dockerize in Docker on your Raspberry Pi

This is a small test if it is possible to install and run `dockerize` in a Docker container
and use it in there to dockerize other binaries within that Docker container.
The final Docker image is created in your host's Docker.

## Clone the repo on your HypriotOS RPi

```bash
git clone git@github.com:hypriot/dockerfiles
cd dockerfiles/rpi-dockerize
```

## Create the dockerize container

```bash
docker build -t dockerize .
```

## Create a first sample: sed

Now we create a very tiny Docker image with only the `sed` binary in it.
To be able to create the new Docker image on your host we have to map the docker cli and 
the docker socket to the docker container. Therefore the commandline is a little bit longer
as usual, but works fine on HypriotOS with docker 1.5.0.

```bash
docker run -v /var/run/docker.sock:/var/run/docker.sock -v /usr/bin/docker:/usr/bin/docker -v /lib/arm-linux-gnueabihf/libdevmapper.so.1.02.1:/lib/arm-linux-gnueabihf/libdevmapper.so.1.02.1 -ti dockerize dockerize -t sed /bin/sed
```

List the output

```bash
$ docker images
REPOSITORY            TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
sed                   latest              d7c7d1c7be75        5 minutes ago       1.588 MB
```

Now test the newly created Docker image

```bash
docker run -ti sed --help
```
