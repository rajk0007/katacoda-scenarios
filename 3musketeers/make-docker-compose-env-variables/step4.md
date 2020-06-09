After we review the docker-compose, its time to pull down and run our image as a container. Open up the makefile and review the `shell` target. This target calls docker-compose run with the service we want to run and shells into the container. 

## Task
Run the make target from below or from the terminal. 

`make shell`{{execute}}