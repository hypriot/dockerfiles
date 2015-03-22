default: build

build:
	docker build -t hypriot/dockerindocker - < Dockerfile
#	docker tag hypriot/drone_builder_base:latest registry.hypriot.com/hypriot/drone_builder_base:latest
# the following three lines are needed to push to our local registry at the (drone) build server
	docker tag -f hypriot/dockerindocker:latest localhost:5000/hypriot/dockerindocker:latest 
	docker push localhost:5000/hypriot/dockerindocker
	docker rmi localhost:5000/hypriot/dockerindocker:latest 
					
					
rmi:
	docker rmi hypriot/dockerindocker

rebuild: rmi build
