FROM node:lts-alpine

RUN apk add git python g++ make curl cmake

ARG branch=master

RUN mkdir /app \
    && cd /app \
    && git clone https://github.com/project-persona/smtp-server.git . --branch $branch --depth 1 \
    && npm install \
    && apk del git

WORKDIR /app

USER 0

EXPOSE 25

ENTRYPOINT ["npm", "start"]