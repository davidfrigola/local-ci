# Simple jenkins local CI

This is a simple approach for a local jenkins startup

# Requirements

* docker

# Initial setup

Run `make build` to create a local image `local-ci/jenkins:1.0`.

Run `make start` to get jenkins up and running in local `8088` port.
Use your favourite browser to `localhost:8088`.
You'll be asked for a password. Use `docker logs local-ci-jenkins` and search for it in container logs.

Then you should install the plugins by default when asked.

After this step, you have to create an `admin` user. Simplest approach is :
user: admin
pass: admin
email: admin@localhost

# Creating a simple jenkins job

A simple mvn project can be build in the local jenkins
Go to `localhost:8088` and create a new project.
Freestyle project named `simple-mvn-build` with :
* Description : `Simple MVN build`
* Source code management : git : <your git url : I am using a github mvn project>
* Build : Execute shell : `mvn clean package`
