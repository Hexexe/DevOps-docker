FROM node:16-alpine

WORKDIR /usr/src/app

EXPOSE 5000

COPY . . 

RUN npm i && npm i -g serve && npm run build

CMD [ "serve", "-s", "-l", "5000", "build" ]