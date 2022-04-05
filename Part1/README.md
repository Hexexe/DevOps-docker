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

Output

```console
[dot@arch DevOpsDocker]$ docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS                     PORTS     NAMES
a341601b46f6   nginx     "/docker-entrypoint.…"   53 seconds ago   Up 51 seconds              80/tcp    condescending_lehmann
1d5bc08d9236   nginx     "/docker-entrypoint.…"   54 seconds ago   Exited (0) 3 seconds ago             laughing_mahavira
c0a25c9b152e   nginx     "/docker-entrypoint.…"   55 seconds ago   Exited (0) 8 seconds ago             jovial_babbage
```

<br>

## Exercise 1.2: Cleanup

---

Cleanup containers & images

```console
[dot@arch DevOpsDocker]$ docker rm -f $(docker ps -aq)
[dot@arch DevOpsDocker]$ docker rmi c9
```

Output

```console
[dot@arch DevOpsDocker]$ docker ps -a
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
[dot@arch DevOpsDocker]$ docker images
REPOSITORY   TAG       IMAGE ID   CREATED   SIZE
```

<br>

## Exercise 1.3: Secret message

---

Commands

```console
[dot@arch DevOpsDocker]$ docker run -dit --rm --name web devopsdockeruh/simple-web-service:ubuntu
[dot@arch DevOpsDocker]$ docker exec -it web bash -c "tail -f ./text.log"
```

Secret Message

```console
Secret message is: 'You can find the source code here: https://github.com/
```

<br>

## Exercise 1.4: Missing dependencies

---

Commands

```console
[dot@arch DevOpsDocker]$ docker run -dit --name web ubuntu sh -c 'apt update; apt install -y curl; echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;'
[dot@arch DevOpsDocker]$ docker attach web
```

Input/Output

```console
Input website:
helsinki.fi
Searching..
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="https://www.helsinki.fi/">here</a>.</p>
</body></html>
```

<br>

## Exercise 1.5: Sizes of images

---

Size

```console
[dot@arch DevOps-docker]$ docker images
REPOSITORY                          TAG       IMAGE ID       CREATED         SIZE
devopsdockeruh/simple-web-service   ubuntu    4e3362e907d5   12 months ago   83MB
devopsdockeruh/simple-web-service   alpine    fd312adc88e0   12 months ago   15.7MB
```

Secret

```console
[dot@arch DevOps-docker]$ docker run -dit --rm --name alpine devopsdockeruh/simple-web-service:alpine
[dot@arch DevOps-docker]$ docker exec alpine sh -c "tail -f ./text.log"
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
```

<br>

## Exercise 1.6: Hello Docker Hub

---

Command

```console
[dot@arch DevOps-docker]$ docker run -it devopsdockeruh/pull_exercise
```

Secret

```console
Give me the password: basics
You found the correct password. Secret message is:
"This is the secret message"
```

https://github.com/docker-hy/docs-exercise/blob/master/index.js
