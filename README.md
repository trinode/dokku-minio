# dokku redis (beta)  [![Build Status](https://img.shields.io/travis/dokku/dokku-redis.svg?branch=master "Build Status")](https://travis-ci.org/dokku/dokku-redis) [![IRC Network](https://img.shields.io/badge/irc-freenode-blue.svg "IRC Freenode")](https://webchat.freenode.net/?channels=dokku)

Official redis plugin for dokku. Currently defaults to installing [redis 3.2.8](https://hub.docker.com/_/redis/).

## requirements

- dokku 0.4.x+
- docker 1.8.x

## installation

```shell
# on 0.4.x+
sudo dokku plugin:install https://github.com/dokku/dokku-minio.git minio
```



## Partially Working Commands

```
minio:create <name>            Create a minio service with environment variables
minio:destroy <name>           Delete the service, delete the data and stop its container if there are no links left (requires manual clean up of data)

```


## usage

```shell
# create a minio service named lolipop
dokku minio:create lolipop

# you can also specify the image and image
# version to use for the service
# it *must* be compatible with the
#  minio/minio image
export MINIO_IMAGE="minio/minio"
export MINIO_IMAGE_VERSION="edge"
dokku minio:create lolipop

# you can also specify custom environment
# variables to start the minio service
# in semi-colon separated form
export MINIO_CUSTOM_ENV="USER=alpha;HOST=beta"
dokku minio:create lolipop
```
