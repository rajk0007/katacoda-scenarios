Containers offer a logical packaging mechanism in which applications can be abstracted from the environment in which they actually run. This decoupling allows container-based applications to be deployed easily and consistently, regardless of whether the target environment is a private data center, the public cloud, or even a developer’s personal laptop. This gives developers the ability to create predictable environments that are isolated from the rest of the applications and can be run anywhere. For more in depth information on docker,please visit their website at https://www.docker.com/

## Task
Let's open the `Dockerfile`{{open}} and take a look at whats going on. It's a rather simple Dockerfile in that it simply:
1. Pulls down the openjdk base image
2. Copies our current directory into /app on the container
3. Sets a working dir to /app
4. Makes the gradle wrapper executable
5. Runs a few gradle tasks that generate a jar file
6. Moves that jar file
7. Finally, execute the jar file

## Task
Our first task will be to build the docker image based off of our Dockerfile. In order to do this, we call upon the ```docker build``` command. We will also pass in an argument of ```-t``` to tag the image and a ```.``` to use the current directory as the build context. This may take a minute or two to complete. 

`docker build -t javaspring-docker .`{{execute T1}}

## Task
Now that we have the docker container built it's time to try and run the docker image. In order to do this, we will call the ```docker run``` command. We will also pass in an argument of ```-p``` to specify which ports will be exposed, as well as the image we created in the previous task  ```javaspring-docker```. It's done when you see ```welcomePageHandlerMapping``` 

`docker run -p 8080:8080 javaspring-docker`{{execute T1}}

## Task 
Now that we have a running container let's try and hit our endpoint. Clicking the below command will open up a new terminal to perform the curl. 

`curl localhost:8080`{{execute T3}}

We should see the output ```Greetings from Spring Boot!```.
`echo Click Here to send ctrl-alt-del to Terminal 1`{{execute interrupt T1}}

## Task
Let's tidy up after ourselves so that we don't leave any orphaned containers. The following commands will remove the containers and the images. 

`docker rm -f $(docker ps -a -q)`{{execute T1}}
`docker rmi -f javaspring-docker`{{execute T1}}