Make is a build automation tool that automatically builds programs and runs commands via the same interface. Make is installed on all distros of Unix/Linux operating systems. It is also available on Windows operating systems. Make obtains all its knowledge of how to build the program from a file called the ```Makefile```. This file contains ```targets``` that can be executed.

Makefiles can be as simple or complex as you like. The key to a good Makefile is a clean one. Lets open the Makefile `Makefile`{{open}}and walk through whats going on. 

## Task
Our first target in our Makefile is a ```help``` target. This target will scan the Makefile and look for any text that comes after a ```##```. We can create self documenting Makefiles using this convention. Lets run the following command to see what our help looks like.
`make help`{{execute}}

## Task
Let's create our first recipe inside of the `build` Make target. Add the correct docker-compose build command to the `build` target. After the makefile has been updated execute it using the following command:

`make build`{{execute}}

We can now pop ```make build``` into our CI/CD pipeline and run it locally the same exact way. 

## Task
Let's create another recipe inside of the `up` Make target. Add the correct docker-compose up command to the `up` target. After the makefile has been updated execute it using the following command:


`make up`{{execute}}

Make really ties docker and docker-compose up. It gives the developers a single interface to interact with. 
This concludes the Make section of this scenario. Head on over to https://3musketeers.io/docs/make.html to dive into Make.  