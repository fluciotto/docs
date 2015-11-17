---
tags: mongodb, services
---

## MongoDB 
You can run the standard Docker MongoDB image without requiring any
additional setup.

### Setup

To use the basic [docker Image](https://registry.hub.docker.com/_/mongo/) in
your build, you can use the following
[wercker.yml](http://devcenter.wercker.io/learn/wercker-
yml/introduction.html) as a starting point:

```
# wercker.yml
box: google/golang
services:
   - id: mongo
build:
   steps:
(...)
```

### Env vars 
Docker will expose the following env vars, which you can use to
connect to mongo from within your application.

```
MONGO_ENV_MONGO_MAJOR='3.0'
MONGO_PORT='tcp://172.17.184.188:27017'
MONGO_ENV_MONGO_VERSION='3.0.7'
MONGO_PORT_27017_TCP='tcp://172.17.184.188:27017'
MONGO_PORT_27017_TCP_PROTO='tcp'
MONGO_PORT_27017_TCP_ADDR='172.17.184.188'
MONGO_NAME='/wercker-pipeline-xxxxxxxxxxxxxxxxxxxxxxxx/mongo',
MONGO_PORT_27017_TCP_PORT='27017'
```

To learn about how to find out the IP address of a service container you should
use the environment variables exposed by Docker. You can read more about that in
our article [_available env vars_](http://devcenter.wercker.io/docs/services
/available-env-vars.html).
