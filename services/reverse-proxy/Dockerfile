FROM node:lts-alpine as builder

RUN apk add git

ARG branch=master

RUN mkdir -p /src  \
    && cd /src \
    && git clone https://github.com/project-persona/web-client.git . --branch $branch --depth 1 \
    && npm install \
    && npm run generate

FROM nginx

COPY default.conf /etc/nginx/conf.d/

COPY --from=builder /src/dist/. /usr/share/nginx/html/


