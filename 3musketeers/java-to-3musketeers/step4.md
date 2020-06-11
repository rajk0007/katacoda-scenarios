Make is a build automation tool that automatically builds programs and runs commands via the same interface. Make is installed on all distros of Unix/Linux operating systems. It is also available on Windows operating systems. Make obtains all its knowledge of how to build the program from a file called the ```Makefile```. This file contains ```targets``` that can be executed. For more in depth information on make go to the website https://www.gnu.org/software/make/manual/make.html

## Task
Let's open the `Makefile`{{open}} and take a look around. First let's go through the some of the basic layout of the Makefile. At the top you will see line 1 ```DOCKER_COMPOSE ?= docker-compose```. This line is simply setting a variable of DOCKER_COMPOSE to the docker-compose binary. 
*Note: if you are interested in why we use ?= visit https://www.gnu.org/software/make/manual/html_node/Flavors.html#Flavors to see the different ways of setting a variable*


Let's move down the file until we get to our help target. We start off our first target with a ```.PHONY```. What does this mean? Pretty much make works on a file based system. PHONY means run this target even if there is a file named ```help``` in the directory. 
*Note: For more information visit https://www.gnu.org/software/make/manual/html_node/Phony-Targets.html. Note: this ```.PHONY``` could also be put at the top of the file, I put it here to make the file look cleaner.*

Next, we we declare our first target. We named this first target ```help```. The syntax is the name followed by a colon : ```help:```This is the name that we will call when we want to run this target. You will also see a line that seems to be commented out with ```##```. This will make more sense in a minute. 

Ok, after we define the name of our target. We want to create our ```recipe```. Recipe is just a fancy name for the commands we would like our target to perform. Note that Make is very strict when it comes to recipes and spacing. Always use a tab in your recipes.  In the case of the ```help``` target, its a grep and sed of our Makefile.```@fgrep -h "##" $(MAKEFILE_LIST) | fgrep -v fgrep | sed -e 's/\\$$//' | sed -e 's/##//'``` This line simply scans our Makefile and parses it for anything that comes after a ```##``` and displays that to the screen. 
*Note: Each recipe in a target is performed in a separate shell*

Ok, now that we have a better understanding of how the Makefile is laid out, let's try and run our ```help target```. In order to run our target we just need to execute the following:

`make help`{{execute T1}}

## Task
Let's jump into our next target ```up```. This target calls our DOCKER_COMPOSE variable which is set to our docker-compose binary and then passes the arguments of ```up```. This will build and run our image based off of our ```docker-compose``` file. We also want to run it in detached mode so we pass in an argument of ```-d```. Either type the command or click the button below to run this make target. 

`make up`{{execute T1}}


## Task
After you see the line ```Creating helloworldspringboot_javaspring_1 ... done``` let us try and test our endpoint. Rather than running a curl command directly from the terminal, We can create a make target that calls curl for us. Take a look at the target ```endpoint``` and run it. This may take a minute or two to complete. 

`make endpoint`{{execute T1}}
We should see our application successfully respond with ```Greetings from Spring Boot!```

## Task
We won't go through all the targets but i just wanted to point out the targets ```build``` and ```run```. Instead of calling docker-compose up we could do those 2 tasks independently if we wanted to.

## Task
Ok, so for our last task in this scenario, I would like the user to create a new make target called ```clean```. We want this target to clean up the container and image that we created with our last task. A nice feature would be to also add a help message to the target. Hint: the recipe could be ```docker-compose down --rmi all```. After this target is created run it. 

`make clean`{{execute T1}}