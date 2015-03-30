default: build

build:
	docker build -t hypriot/slackus:latest - < Dockerfile

rmi:
	docker rmi -f hypriot/slackus

rebuild: rmi build
