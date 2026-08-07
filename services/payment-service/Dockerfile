# Use an official, lightweight Java runtime as the base image
FROM eclipse-temurin:17-jre-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy your built JAR file from the target/build folder into the container
COPY target/my-app.jar app.jar

# Run the Java application
ENTRYPOINT ["java", "-jar", "app.jar"]
