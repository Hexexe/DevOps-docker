# Part 1

## Exercise 1.1: Getting started

---

Start 3 containers from image that does not automatically exit, such as nginx, detached.

```console
[dot@arch DevOpsDocker]$ docker container run -d nginx
[dot@arch DevOpsDocker]$ docker container run -d nginx
[dot@arch DevOpsDocker]$ docker container run -d nginx
```

Stop 2 of the containers leaving 1 up.

```console
[dot@arch DevOpsDocker]$ docker stop c0
[dot@arch DevOpsDocker]$ docker stop 1d
```

Submit the output for docker ps -a which shows 2 stopped containers and one running.

```console
[dot@arch DevOpsDocker]$ docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS                     PORTS     NAMES
a341601b46f6   nginx     "/docker-entrypoint.…"   53 seconds ago   Up 51 seconds              80/tcp    condescending_lehmann
1d5bc08d9236   nginx     "/docker-entrypoint.…"   54 seconds ago   Exited (0) 3 seconds ago             laughing_mahavira
c0a25c9b152e   nginx     "/docker-entrypoint.…"   55 seconds ago   Exited (0) 8 seconds ago             jovial_babbage
```
