
# Deployment Scripts

## Currently Containerized Services

- [x] `mongodb`: main database
- [x] `reverse-proxy`: nginx reverse-proxy serving static resources and forward `POST /api` to upstream `api-gateway`
- [x] `api-gateway`: exposing microservices as JSON RPC over HTTP
- [x] `service-broker`: service oriented message queue
- [x] `microservice-personas`: personas microservice
- [ ] `microservice-passwords`: emails microservice
- [x] `microservice-notes`: notes microservice
- [x] `microservice-emails`: emails microservice
- [ ] `smtp`: SMTP receive-only email server

## Development Environment

```  
$ docker-compose -f docker-compose-development.yaml up  
```  

A HTTP server is exposed to host and listening on [http://localhost:8080/](http://localhost:8080/) or  
[http://mypersona.tk:8080/](http://mypersona.tk:8080/). You can add an entry to your hosts file to point `mypersona.tk`  
to `127.0.0.1` for development.

Development environment uses a self-hosted MongoDB instance.

## Production Environment

*// TODO*

## Update Services to New Versions

Remember to rebuild image when a repository is updated and push to origin:

```  
$ docker-compose -f docker-compose-development.yaml build --no-cache [service...]  
```  

Don't forget `--no-cache`!

Also watch for new versions of deployment scripts.