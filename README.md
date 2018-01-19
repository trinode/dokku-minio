# dokku minio (beta) 

Minio plugin for dokku. Currently defaults to installing [minio edge](https://hub.docker.com/minio/minio/).

## requirements

- dokku 0.4.x+
- docker 1.8.x

## installation

```shell
# on 0.4.x+
sudo dokku plugin:install https://github.com/trinode/dokku-minio.git minio
```



## Partially Working Commands

```
minio:create <name>            Create a minio service with environment variables
minio:destroy <name>           Delete the service, delete the data and stop its container if there are no links left (requires manual clean up of data)
minio:link <name> <app>        Links the service to an app and sets environment variables
minio:unlink <name> <app>      Unlinks the service from an app and unsets environment variables

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
export MINIO_IMAGE_VERSION="latest"
dokku minio:create lolipop

# you can also specify custom environment
# variables to start the minio service
# in semi-colon separated form
export MINIO_CUSTOM_ENV="USER=alpha;HOST=beta"
dokku minio:create lolipop
```
