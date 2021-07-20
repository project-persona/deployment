FROM node:lts-alpine

RUN apk add git python g++ make curl cmake openssh

ARG repo
ARG branch=master

RUN test -z "$repo" && echo "ARG repo is not set!" && exit 1 || :

RUN mkdir /app \
    && cd /app \
    && git clone https://github.com/project-persona/${repo}.git . --branch $branch --depth 1 \
    && npm install

WORKDIR /app

ENTRYPOINT ["npm", "start"]