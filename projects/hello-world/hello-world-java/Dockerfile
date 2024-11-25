# Build a JAR File
FROM maven:3.8.2-jdk-8-slim AS stage1
WORKDIR /home/app
COPY . /home/app/
# Since the pom.xml file is inside our WORKDIR but our gradle will run from root, that's why we are providing: `/home/app/pom.xml` as argument
RUN mvn -f /home/app/pom.xml clean package

# Create an Image
FROM openjdk:8-jdk-alpine
EXPOSE 5000
# Taking the last caching layer: stage1
COPY --from=stage1 /home/app/target/hello-world-java.jar hello-world-java.jar
# For Python and Nodejs, we use CMD but for Java, we use ENTRYPOINT
# If we are using ENTRYPOINT, in that case, we have to run the bash command: `sh -c java -jar <JAR_FILE_NAME>`
ENTRYPOINT ["sh", "-c", "java -jar /hello-world-java.jar"]
