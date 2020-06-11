Compose is a tool for defining and running multi-container Docker applications. With Compose, you use a YAML file to configure your application’s services. Then, with a single command, you create and start all the services (and their dependencies) from your configuration. In 3 Musketeers, it also simplifies our Makefiles. For more in depth information on docker-compose, visit the website https://docs.docker.com/compose/

Our next task will be to add docker-compose. In order to do this we need a docker-compose.yml file. We will keep this file rather simple. If you open the `docker-compose.yml`{{open}}, you will see we have a service named ```javaspring```. Under ```javaspring``` we have a build section (which builds our dockerfile,an image section (which tags our image) and a ports section (which tells us what port to open on the host and container respectively)

## Task
We can use compose to orchestrate the build and run of our container with the 1 command

`docker-compose up -d`{{execute T1}}

This command is a lot cleaner than using the regular docker build and docker run commands. If you remember from the previous step, we had to run a ```docker build``` and ```docker run``` in order to build and run our image. With docker-compose we can make this 1 command with ```docker-compose up -d```. You may also notice we didn't have to pass any arguments to the command itself, all that configuration is housed inside of the docker-compose.yml file. This may take a minute or two to complete. 

## Task 
Let's try and hit our endpoint. 

`curl localhost:8080`{{execute T1}}

We should see the output ```Greetings from Spring Boot!```.

## Task
Docker-Compose will also do a bit of clean up for us with the ```down``` flag. It will stop and remove any items created by the ```up``` flag. 

`docker-compose down --rmi all`{{execute T1}}
