FROM node:14.14.0-alpine
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
COPY . .
# SI USA NODEMON PER FAR RIPARTIRE IL SERVER OGNI VOLTA SI CAMBIA
CMD ["npm","run","start"]