FROM node:lts-alpine

RUN apk add git python g++ make curl cmake

ARG branch=master

RUN mkdir /app \
    && cd /app \
    && git clone https://github.com/project-persona/infra.git . --branch $branch --depth 1 \
    && npm install

WORKDIR /app

ENTRYPOINT ["npm", "run"]