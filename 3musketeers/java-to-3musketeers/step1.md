Let's review the java project. It is a simple java springboot application that displays ```Greetings from Spring Boot!``` when ran. At the top level we have all our supporting files from our gradle configuration down to the source code which is housed inside the ```src``` folder. Let's try and run this the old fashioned way with gradle directly from the terminal. 

## Task
We will be building the jars today with gradle. The first step we need to perform is to build the jar. We will run the following command to generate a jar. This may take a minute or two to complete. 

`chmod u+x ./gradlew`{{execute T1}}

`./gradlew bootJar`{{execute T1}}


After this gradle task completes we should have a jar file located under build/libs.

`ls build/libs/`{{execute T1}}

After it's built and you see the jar, lets try and run it. It's done when you see ```welcomePageHandlerMapping``` 

`java -jar build/libs/demo-0.0.1-SNAPSHOT.jar`{{execute T1}}

After we run this let's open another terminal inside Katacoda and try and hit the endpoint:

`curl localhost:8080`{{execute T3}}

We should see the output ```Greetings from Spring Boot!```.

`echo Click Here to send ctrl-alt-del to Terminal 1`{{execute interrupt T1}}

And just like that we have a running springboot application! The next logical step here would be to try and run this in a docker container so that it is more portable and not relying on dependencies. 