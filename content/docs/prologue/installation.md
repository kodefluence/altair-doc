---
title: "Installation"
description: "This guide will guide you to a minimal installation that’ll work while you walk through the introduction."
lead: "This guide will guide you to a minimal installation that’ll work while you walk through the introduction."
date: 2020-11-16T13:59:39+01:00
lastmod: 2020-11-16T13:59:39+01:00
draft: false
images: []
menu:
  docs:
    parent: "prologue"
weight: 110
toc: true
---

## Getting Started with Docker

If you already know what docker is and want to take a quick jump into altair configuration and implementation, you can use this section as your guide.

### Run Altair with Docker-Compose

We are at the [dockerhub](https://hub.docker.com/r/codefluence/altair)! A common implementation of the docker Altair is to have a directory where you store the config and routes folders in it.

```
config/
routes/
.env
docker-compose.yml
```

The docker-compose content could look like this:

```yaml
version: "3.8"
services:
  altair:
    image: codefluence/altair:latest
    volumes:
      - ./routes/:/opt/altair/routes/
      - ./config/:/opt/altair/config/
      - ./.env:/opt/altair/.env
    ports:
      - "1304:1304"
    network_mode: host
    env_file: ./.env
```

After that, you can start Altair with the command `docker-compose up`. It will serve Altair in http://localhost:1304.

## Getting Started with Window, Linux and Mac

If you don't have a docker on your computer, don't worry we also support manual downloading.

### Download Altair

You can download the latest Altair release here based on your operating system.

| OS      | Download Link                                                                                     |
|---------|---------------------------------------------------------------------------------------------------|
| Linux   |  [Download](https://github.com/codefluence-x/altair/releases/download/0.1.0/altair-linux.zip)        |
| Windows |  [Download](https://github.com/codefluence-x/altair/releases/download/0.1.0/altair-windows.zip)      |
| Mac     |  [Download](https://github.com/codefluence-x/altair/releases/download/0.1.0/altair-darwin.zip)       |

### Unpack and Running

After you unzip your zip file, it should look like this.

```
config/
routes/
.env
docker-compose.yml
```

Copy your `env.sample` file into `.env`, then run the command below to see Altair's configuration.

```
./altair config all
```

Run your Altair api gateway with

```
./altair run
```
