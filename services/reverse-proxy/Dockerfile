FROM node:lts-alpine as builder

RUN apk add git

ARG branch=master

RUN mkdir -p /src  \
    && cd /src \
    && git clone https://github.com/project-persona/web-client.git . --branch $branch --depth 1 \
    && npm install \
    && npm run generate

FROM nginx

# TODO: copy in certificates for production

COPY default.conf /etc/nginx/conf.d/
COPY ssl.conf /etc/nginx/snippets/

COPY --from=builder /src/dist/. /usr/share/nginx/html/


