# dynamic makefile to build docker images

default: build

build:
	docker build -t hypriot/$(imagename) - < Dockerfile
        #       docker tag hypriot/drone_builder_base:latest registry.hypriot.com/hypriot/drone_builder_base:latest
        # the following three lines are needed to push to our local registry at the (drone) build server
	docker tag -f hypriot/$(imagename):latest localhost:5000/hypriot/$(imagename):latest
	docker push localhost:5000/hypriot/$(imagename)
	docker rmi localhost:5000/hypriot/$(imagename):latest
                                
rmi:
	docker rmi hypriot/$(imagename)
                   
rebuild: rmi build
                          
backup:
	docker tag -f hypriot/$(imagename):latest hypriot/$(imagename):bak
              
build2: build4registry
                                 
build2export:
	docker build -t hypriot/$(imagename) - < Dockerfile
#       docker tag hypriot/drone_builder_base:latest registry.hypriot.com/hypriot/drone_builder_base:latest
# the following three lines are needed to push to our local registry at the (drone) build server
	docker images
	docker save hypriot/$(imagename) > /result/$(imagename).tar
#       docker tag -f hypriot/dockerindocker:latest 172.17.42.1:5000/hypriot/dockerindocker:latest 
#       docker push 172.17.42.1:5000/hypriot/dockerindocker
#       docker rmi 172.17.42.1:5000/hypriot/dockerindocker:latest 

build4registry:
	docker build -t hypriot/$(imagename) - < Dockerfile
        #       docker tag hypriot/drone_builder_base:latest registry.hypriot.com/hypriot/drone_builder_base:latest
        # the following three lines are needed to push to our local registry at the (drone) build server
	docker tag -f hypriot/$(imagename):latest $(REGISTRY_URL)/hypriot/$(imagename):latest
	docker push $(REGISTRY_URL)/hypriot/$(imagename)
	docker rmi $(REGISTRY_URL)/hypriot/$(imagename):latest
