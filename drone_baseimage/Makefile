default: build

build:
	docker build -t hypriot/drone_builder_base - < Dockerfile
#	docker tag hypriot/drone_builder_base:latest registry.hypriot.com/hypriot/drone_builder_base:latest
# the following three lines are needed to push to our local registry at the (drone) build server
	docker tag -f hypriot/drone_builder_base:latest localhost:5000/hypriot/drone_builder_base:latest 
	docker push localhost:5000/hypriot/drone_builder_base
	docker rmi localhost:5000/hypriot/drone_builder_base:latest 
					
					
rmi:
	docker rmi hypriot/drone_builder_base

rebuild: rmi build
