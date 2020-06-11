Musketeer 1 - Make
Make is a build automation tool that automatically builds programs and runs commands via the same interface. Make is installed on all distros of Unix/Linux operating systems. It is also available on Windows operating systems. Make obtains all its knowledge of how to build the program from a file called the ```Makefile```. This file contains ```targets``` that can be executed. 

## Task
Lets create a Makefile in the editor or by clicking the test below and add a target.
`touch Makefile`{{execute}}

## Task
Lets create our first target inside the Makefile. This will be a simple target that prints ```Hello World``` to the screen. Add the following lines to the Makefile we just created:

```
echo:
    echo "Hello World"
```
* TIP: Make doesn't like spaces. Make sure you tab the ```echo "Hello World"``` line


## Task
Our next step is to call the make target we just just created. Either type ```make echo``` in the terminal or click the following:
`make echo`{{execute}}
