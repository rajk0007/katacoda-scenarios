Compose is a tool for defining and running multi-container Docker applications. With Compose, you use a YAML file to configure your application’s services. Then, with a single command, you create and start all the services (and their dependencies) from your configuration.  In 3 Musketeers, it also simplifies our Makefiles.

Our next task will be to add docker-compose. In order to do this we need a docker-compose.yml file. We will keep this file rather simple. If you open the docker-compose.yml file `docker-compose.yml`{{open}}, you will see we have a service named ```printvars```. Under printvars we have a build section (which builds our dockerfile) and an image section (which tags our image).

## Task
If you remember from the previous steps this script needs an environment variable to run correctly. We can pass environment variables to a container via a docker-compose environment block. Let's add a block to our docker-compose.yml file. 

*TIP-If you are stuck with what to add to the Dockerfile there is a "Show Solution" button at the bottom the scenario.*

***PRO-TIP The environment section is really useful when your container excepts multiple variables. The next iteration of the environment block is the use of an env file. Check out the course https://www.katacoda.com/james5101/scenarios/make-docker-compose-env-variables for more info on using an envfile with 3musketers.***

## Task
After our editing of the docker-compose file, let's try and build the container.

`docker-compose build`{{execute}}

The command above will produce a newly built printvars-compose image. Let's run the following command to confirm our image built. 

`docker images`{{execute}}

## Task
Let's try and run our image now via docker-compose up. Docker-compose up builds, (re)creates, starts and attaches containers for a service. You could also run ```docker-compose run servicename``` for one-off/adhoc tasks.  
`docker-compose up`{{execute}}

## Task
After creating our images and running our container we should be good samaritans and clean up after ourselves. We can do so by running docker-compose down 
`docker-compose down`{{execute}}



This wraps up the section on docker-compose. Docker-compose is very powerful for running containers, for more info visit https://docs.docker.com/compose/. 

Now, onto the last Musketeer, Make!