# PRODUCTION DOCKERFILE (MULTI STEP BUILD) FOR FRONTEND
# TEMPORARY CONTAINER (all that will save is the build content for NGINX)
FROM node:16-alpine as builder
WORKDIR '/app'
COPY package.json .
RUN npm install 
COPY . .
# COMMAND FOR PROD, JUST ONLY A  SINGLE COMMAND (CMD NOT REQUIRED)
RUN npm run build

FROM nginx
# COPY FROM THE PREVIOUS STEP (--from=builder) THE BUILD FOLDER (/app/build) AND THEN PUT INTO NGINX (/usr/share/nginx/html)
# to dialog with the nginx http server broker
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
# copy the result of builder
COPY --from=builder /app/build /usr/share/nginx/html 

# COME OGNI DOCKERFILE RICORDARSI IL DOCKER BUILD .
