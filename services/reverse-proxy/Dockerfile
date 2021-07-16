FROM node:lts-alpine as builder

ARG branch=master

# TODO: update frontend build script once repository if up
RUN mkdir -p /src/dist  \
    && echo "placeholder front end resource" > /src/dist/index.html

FROM nginx

# TODO: copy in certificates for production

COPY default.conf /etc/nginx/conf.d/

COPY --from=builder /src/dist/* /usr/share/nginx/html/


