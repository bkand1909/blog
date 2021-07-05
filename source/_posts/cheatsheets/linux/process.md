---
title: Linux process management
date: 2021-07-05 18:08:35
categories:
- Cheatsheet
- Linux
tags:
- linux
---

## Defunct process

List defunct processes
```sh
ps -ef | grep defunct | grep chrome | awk '{print "kill -9 " $2 " " $3 " " $8}'
ps -ef | grep defunct | awk '{print "kill -9 " $2 " " $3 " " $8}'
```

Kill defunct processes
```sh
ps -ef | grep defunct | grep chrome | awk '{print "kill -9 " $2 " " $3}' | sh -x
ps -ef | grep defunct | awk '{print "kill -9 " $2 " " $3}' | sh -x
```
