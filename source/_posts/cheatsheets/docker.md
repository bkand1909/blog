---
title: Docker useful commands
date: 2021-07-05 05:47:52
categories:
  - Cheatsheet
tags:
  - docker
  - cheatsheet
---

## Containers

```sh
# List all exited containers
docker ps -aq -f status=exited

# Remove stopped containers
docker ps -aq --no-trunc -f status=exited | xargs docker rm
```

## Volumes

```sh
# Remove dangling volumes
docker volume rm $(docker volume ls -qf dangling=true)
docker volume ls -qf dangling=true | xargs -r docker volume rm
```

## Images

```sh
# Remove dangling/untagged images
docker images -q --filter dangling=true | xargs docker rmi
# Remove containers created after a specific container
docker ps --since a1bz3768ez7g -q | xargs docker rm
# Remove containers created before a specific container
docker ps --before a1bz3768ez7g -q | xargs docker rm
# Use --rm for docker build
# Use --rm together with docker build to remove intermediary images during the build process.
```