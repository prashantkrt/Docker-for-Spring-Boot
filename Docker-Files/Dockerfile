FROM openjdk:latest
ADD target/my-app.jar my-app.jar
EXPOSE 8085
ENTRYPOINT ["java", "-jar", "my-app.jar"]
CMD ["--server.port=8085"]

# EXPOSE 8085 just tells Docker that the container listens on port 8085 at runtime.
# The EXPOSE instruction does not actually publish the port. To do that, you need to use the -p flag when running the container.
# For example, to publish port 8085 on the host and map it to port 8085 in the container, you would run:
# docker run -p 8085:8085 my-image:demo-3

# ENTRYPOINT and CMD are both instructions in a Dockerfile that define what command should be run when a container is started from the image.
# ENTRYPOINT is used to set the main command to be run when the container starts. It is not overridden by any command line arguments passed to docker run.
# CMD is used to provide default arguments to the ENTRYPOINT command. If CMD is specified, it will be passed as arguments to the ENTRYPOINT command.
# If CMD is not specified, the container will run the ENTRYPOINT command with no arguments.
# In the example above, the ENTRYPOINT command is set to run the Java application with the JAR file my-app.jar.
# The CMD command is used to provide default arguments to the ENTRYPOINT command, which in this case is --server.port=8085.
# This means that when the container is started, it will run the command:
# java -jar my-app.jar --server.port=8085
# If you want to override the default arguments provided by CMD, you can do so by passing new arguments when running the container.
# For example, if you want to run the application on port 9090 instead of 8085, you can run:
# docker run my-image:demo-3 --server.port=9090
# This will run the command:
# java -jar my-app.jar --server.port=9090
# In summary:
# ENTRYPOINT sets the main command to be run when the container starts.
# CMD provides default arguments to the ENTRYPOINT command. 


# CMD adds default arguments
# java -jar my-app.jar --server.port=8085
# ENTRYPOINT sets the command to be executed when the container starts
# java -jar my-app.jar
# CMD is used to provide default arguments to the ENTRYPOINT command
# ENTRYPOINT ["java", "-jar", "my-app.jar"]
# CMD ["--server.port=8085"]
# ENTRYPOINT ["java", "-jar", "my-app.jar", "--server.port=8085"]
# CMD ["--server.port=8085"]
#ENTRYPOINT ["java", "-jar", "my-app.jar", "--server.port=8085"]
#CMD ["--server.port=9090"]
# => java -jar my-app.jar --server.port=8085 entry point always run and cmd will be ignored here in this case

#Even if you try:
#docker run my-container --server.port=9090 still it will run with 8085 since entrypoint is already set to port 8085

# You can override CMD at runtime:
# docker run my-container --server.port=9090
# which runs =>  java -jar my-app.jar --server.port=9090


# To build the image: 
# Spring-Boot-DockerApp % docker build -t my-image:demo-3 .
    