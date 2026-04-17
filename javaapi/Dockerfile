# multi-stage java app
#stage 1 build artifact using Maven
FROM openjdk:8 AS BUILD_IMAGE
# set work dir inside of container
WORKDIR /usr/src/app/
# run apt update and install maven
RUN apt update && apt install maven -y
# copy project files to work dir
COPY ./ /usr/src/app/
# run mvn install to build the artifact
RUN mvn install -DskipTests

#stage 2 host Artifact
FROM openjdk:8
WORKDIR /usr/src/app/

# copy build jar file from stage 1 from /usr/src/app/target/book-work-0.0.1-SNAPSHOT.jar to working directory with the name book-work-0.0.1.jar, so our artifact will be located in /usr/src/app/
COPY --from=BUILD_IMAGE /usr/src/app/target/book-work-0.0.1-SNAPSHOT.jar ./book-work-0.0.1.jar
# expose container to port 9000
EXPOSE 9000
# run java jar in our container, jar file location
ENTRYPOINT ["java","-jar","book-work-0.0.1.jar"]
# Test
