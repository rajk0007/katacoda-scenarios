### Launching a container

To launch a container in docker we specify the following

`docker run -d nginx`{{execute}}

The `-d` means run in detached mode.

This doesn't allow us to access our nginx instance though as we didn't expose it!

Let's try again:

`docker run -d -p 8081:80 nginx`{{execute}}

Now you should be able to access the basic html website with:

`curl docker:8081`{{execute}}


To see currently running containers run:

`docker ps`{{execute}}

If you want to see the whole output:

`docker ps --no-trunc`{{execute}}