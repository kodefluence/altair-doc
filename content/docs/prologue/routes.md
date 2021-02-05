---
title: "Routes"
description: "Introduction to Altair Routes."
lead: "Introduction to Altair Routes."
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

## Routing

All `yaml` files inside of `routes/` folder will be compiled and generated into reverse proxy path. File inside routes folder could be looks like this

```
routes/
  users.yaml
  products.yaml
  stores.yaml
```

And in each file should be looks like this.

```yaml
name: users
auth: oauth
prefix: /users
host: {{ env "EXAMPLE_USERS_SERVICE_HOST" }}
path:
  /me:
    scope: "users"
  /profiles/:id:
    scope: "users"
    auth: "none"
```

### name

The name of the service
### auth

Oauth option for services scope.

- none: No authentication
- oauth: Oauth authentication, plugin oauth is need to be activated to use this type of authentication
### prefix

Prefix of the service.

### host

Target host of the service. Example: `https://yourservice.com` or `http://localhost:8000`.

### path

#### scope

#### auth
