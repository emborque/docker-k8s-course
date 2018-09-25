FROM node:6-alpine

EXPOSE 3000
ENV http_proxy 10.113.55.120:8080
ENV https_proxy 10.114.55.120:8080

RUN apk add --update tini
RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app
COPY package.json package.json

RUN npm install && npm cache clean
COPY . .

CMD ["tini", "--", "node", "./bin/www"]
