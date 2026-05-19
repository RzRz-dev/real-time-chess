#Setting up a Java Runtime as a parent image.
FROM eclipse-temurin:21-jdk-alpine

#Set the working directory
WORKDIR /app

#Copy build system configuration and wrappers (Maven)
COPY .mvn/ .mvn
COPY mvnw pom.xml ./

#Add execution permissions to the Maven Script
RUN chmod +x mvnw

#Download dependencies to cache them in Docker Layers
RUN ./mvnw dependency:go-offline -B

#Copy application source code
COPY src ./src

#inform docker that the container listens on port 8080
EXPOSE 8080

#Run spring boot application in development mode
CMD ["./mvnw", "spring-boot:run"]