After we have a base env.template file the next step is to generate a .env file based of the template. In order to do that we need to create a make target. If you open up the makefile we are setting a few variables, one of which is to the location of the env.template file. We created an envfile target that simply copies our env.template over to a .env file. At this point we can update the .env file to the correct values.

## Task 
Run the following command to generate a .env file.

`make envfile`{{execute}}

## Task
Add some values to the .env file