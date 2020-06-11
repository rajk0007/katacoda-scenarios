Musketeer 2 - Docker
Docker is a tool designed to make it easier to create, deploy, and run applications by using containers. We can stack up different docker commands into make targets and orchestrate those different steps to help us achieve our desired outcome. In this section we will cover running a docker container from a make target with a simple Hello World example.

## Task 
Lets update our Makefile recipe to call docker run. We will pull and run a simple alpine image and pass it the command echo 'Hello World'
Our echo target should now look like the following snippet:
```
echo:
	docker run --rm alpine echo 'Hello, World!'
```
In this command, we're telling `docker` to start a container based on the `alpine` image. The docker run command is simultaneously pulling the official `alpine` image from Docker Hub and running the `echo 'Hello, World!'` command inside that container. The remove (`--rm`) flag removes the container when it is finished.  Alpine is a very slim Linux distribution.

## Task
Finally, lets run make echo again and see our results. Either type ```make echo``` in the terminal or click the following:
`make echo`{{execute}}
