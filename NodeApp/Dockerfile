FROM node:alpine

RUN apk add --update tini \
    && apk add --update bash

RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app

COPY package.json .

RUN npm install \
    && npm cache clean --force

COPY . .

EXPOSE 3000

CMD [ "tini", "--", "node",  "./bin/www" ]
