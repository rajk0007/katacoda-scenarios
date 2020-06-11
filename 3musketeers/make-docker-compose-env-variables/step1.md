Often times there are many environment variables that need to be passed into containers and having them in a .env becomes handy. An env.template file will provide some help when managing environment variables that are expected inside a container. This file is meant to be the template for our environment variables, we should not update environment variables in this file, rather if we expect new environment vars we can add them to this list. 

## Task
Let's take a look at the env.template file. Suppose we have a container that accepts 3 environment variables in order to run correctly. We simply add those keys into the env.template file. 
