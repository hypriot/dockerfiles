this image can be used to run docker in docker e.g for building docker images

http://paislee.io/how-to-build-and-deploy-docker-images-with-drone/

you need to run the container with ```docker run --privileged -v /var/run/docker.sock:/var/run/docker.sock hypriot/dockerindocker /bin/bash```

the drone.yml.sample is a example drone.yml file to use with this base image to build other images (the first build needs to be done manually)

