default: build

build:
	docker build -t hypriot/hugo:latest - < Dockerfile

rmi:
	docker rmi -f hypriot/hugo

rebuild: rmi build
