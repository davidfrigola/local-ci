
default:
	echo "Use make build|start|stop|delete|rmi"
	echo "build : builds the docker image"
	echo "start: starts a container with jenkins"
	echo "stop: stops the jenkins container"
	echo "delete: stops and deletes jenkins container"
	echo "rmi: stops,deletes container and docker image"
build:
	docker build -t local-ci/jenkins:1.0 .
start:
	echo "Starting jenkins container local-ci-jenkins on 8088"
	docker run -d -p 8088:8080 --name local-ci-jenkins local-ci/jenkins:1.0

stop:
	docker stop local-ci-jenkins

delete: stop
	docker rm local-ci-jenkins

rmi: delete
	docker rmi local-ci/jenkins:1.0
