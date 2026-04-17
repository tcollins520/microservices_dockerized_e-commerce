# multi-stage client app
#stage 1, build the Artifact using Node.js
FROM node:14 AS web-build
# set working directory in the container to /usr/src/app
# we do this so other directories in the container are not overwritten with our source code
WORKDIR /usr/src/app
# copy all the files from present directory to client directory
COPY ./ ./client
# cd in client directory and run npm install and npm build with the container name prod
RUN cd client && npm install && npm run build --prod

#stage 2 host the artifact in nginx container
# use official nginx image as the base image
# our application will be hosted on nginx app
FROM nginx:latest
# copy the html build output from /usr/src/app/client/dist/client/to /usr/share/nginx/html replace the default nginx contents
# copy to the path that the nginx image was created in
COPY --from=web-build /usr/src/app/client/dist/client/ /usr/share/nginx/html
# copy our nginx config file to config file directory
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Expose port 4200
EXPOSE 4200
