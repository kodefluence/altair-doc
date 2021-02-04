---
title: "Config"
description: "Introduction to Altair Config."
lead: "Introduction to Altair Config."
date: 2020-10-13T15:21:01+02:00
lastmod: 2020-10-13T15:21:01+02:00
draft: false
images: []
menu:
  docs:
    parent: "prologue"
weight: 130
toc: true
---

# Application Config

## app.yml

This is where you store all application configurations for Altair.

```yaml
port: 1304
proxy_host: {{ env "PROXY_HOST" }}
authorization:
  username: altair
  password: {{ env "BASIC_AUTH_PASSWORD" }}
plugins:
  - oauth
metric:
  interface: prometheus
```

### port

This configuration is used to declare where Altair should bind the port when running the server.

### proxy_host

This is the http header variable of the `Host` when forwarding the request to the respective service.

### authorization

Authorization keep your internal plugin API secure. Internal plugin API in Altair use basic auth as it's authentication system, the config for it's username and password are configurable in here.

### plugins

List of plugins that are active for your applications. Currently available plugin are:

- oauth (authorization and authentication plugin for your reverse proxy request)

### metric

Metric expose behaviour of your application. Currently available interfaces are: `prometheus`

## database.yml

This is where you store config for your database instances.

```yaml
main_database:
  driver: mysql
  database: {{ env "DATABASE_NAME" }}
  username: {{ env "DATABASE_USERNAME" }}
  password: {{ env "DATABASE_PASSWORD" }}
  host:     {{ env "DATABASE_HOST" }}
  port:     {{ env "DATABASE_PORT" }}
  migration_source: "file://migration"
  connection_max_lifetime: 120s
  max_iddle_connection: 100
  max_open_connection: 100

secondary_database:
  driver: mysql
  database: {{ env "SECONDARY_DATABASE_NAME" }}
  username: {{ env "SECONDARY_DATABASE_USERNAME" }}
  password: {{ env "SECONDARY_DATABASE_PASSWORD" }}
  host:     {{ env "SECONDARY_DATABASE_HOST" }}
  port:     {{ env "SECONDARY_DATABASE_PORT" }}
  migration_source: "file://migration"
  connection_max_lifetime: 120s
  max_iddle_connection: 100
  max_open_connection: 100
```

### driver

Type of your database driver, currently supported driver are:

- mysql

## Template Function

### env

env function will get environment variable based on given parameter. Example `env "DATABASE_NAME"` it will return `DATABASE_NAME` from your environment variables.
