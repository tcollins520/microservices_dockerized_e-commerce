# multi-stage nodejs app
#1 build nodejs artifact
FROM node:14 AS nodeapi-build
# set working directory inside of the container
WORKDIR /usr/src/app
# copy everything from present dir to nodeapi dir
COPY ./ ./nodeapi/
# cd into nodeapi dir and run npm install to build the artifact
RUN cd nodeapi && npm install

#2 host artifact node container
FROM node:14
WORKDIR /usr/src/app/
# copy build image from step 1 that is in /usr/src/app/nodeapi/ to work dir which is /usr/src/app/
COPY --from=nodeapi-build /usr/src/app/nodeapi/ ./
# list the files that are in /usr/src/app/
RUN ls
# expose container to port 5000
EXPOSE 5000
# go in /usr/src/app/ dir and run npm start to start the container
CMD ["/bin/sh", "-c", "cd /usr/src/app/ && npm start"]
# Test3
