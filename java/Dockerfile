# latest oracle openjdk is the basis
FROM openjdk:oracle

# copy jar file into container image under app directory
COPY demo-0.0.1-SNAPSHOT.jar app/demo.jar

# expose server port accept connections
EXPOSE 8080

# start application
CMD ["java", "-jar", "app/demo.jar"]

# Build the Docker image
# docker image build -t demo-app:latest .

# Create and run the container.
# docker container run -p 8080:8080 -d --name app-container demo-app

# http://localhost:8080/hello
