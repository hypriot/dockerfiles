
default: build

build:
	docker build -t hypriot/$(imagename) - < Dockerfile
        # the following three lines are needed to push to our local registry at the (drone) build server
	docker tag -f hypriot/$(imagename):latest $(REGISTRY_URL)/hypriot/$(imagename):latest
	docker push $(REGISTRY_URL)/hypriot/$(imagename)
	docker rmi $(REGISTRY_URL)/hypriot/$(imagename):latest
                                
rmi:
	docker rmi hypriot/$(imagename)
                   
rebuild: rmi build
                          
backup:
	docker tag -f hypriot/$(imagename):latest hypriot/$(imagename):previous
