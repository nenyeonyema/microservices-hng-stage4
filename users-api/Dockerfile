# Use OpenJDK 8 base image  
FROM openjdk:8-jdk-alpine  

# Set the working directory inside the container  
WORKDIR /app  

# Copy the Maven build artifact (JAR file) from the target directory into the container  
COPY target/users-api-0.0.1-SNAPSHOT.jar /app/users-api.jar  

EXPOSE 8080

# Command to run the application  
CMD ["java", "-jar", "users-api.jar"]
