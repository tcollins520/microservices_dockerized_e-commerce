# multi-stage java web app
#stage 1 build java web app artifact using Maven
FROM maven:3.9-eclipse-temurin-8 AS build_image
# set work dir inside of container
WORKDIR /usr/src/app/
# run apt update and install maven
RUN apt update && apt install maven -y
# copy project files to work dir
COPY ./ /usr/src/app/
# run mvn install to build the artifact
RUN mvn install -DskipTests

#stage 2 host Artifact in java container
FROM eclipse-temurin:8-jre
WORKDIR /usr/src/app/

# copy build jar file from stage 1 
COPY --from=build_image /usr/src/app/target/book-work-0.0.1-SNAPSHOT.jar app.jar
# expose container to port 9000
EXPOSE 9000
# run java jar in our container, jar file location
ENTRYPOINT ["java","-jar","app.jar"]
# Test
