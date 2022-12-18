Trying docker containerizing.

First we need to create a .jar file which is an executable java file. We can create .jar file with command below. 

```
mvn clean package -Pnative
```

With this command we are creating native image but only spring 3.0 supports native image. So any spring version under 3.0 cannot take native image. 

After creating .jar file we are ready to create our Dockerfile.

```
docker build -t spring-boot-docker-test.jar
```

After taking build of our Dockerfile our image will be created as spring-boot-docker-test.jar.


```
docker run -p 9090:8080 --name spring-boot-docker-test spring-boot-docker-test.jar
```
With the code above we can run our docker image on localhost 9090 port.

After all we are ready to run our image and use!