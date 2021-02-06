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

And in each file could be looks like this.

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
- oauth: Oauth authentication, **plugin oauth is need to be activated to use this type of authentication**. If you choose this authentication, the client request must include the `Authorization` header in the request with the access token as the value `Bearer access-token-that-you-got-from-altair`.
- oauth_application: Oauth application authentication, **plugin oauth is need to be activated to use this type of authentication**. This feature is currently in a testing phase where you have to submit your request in json format and include `client_id` and `client_secret` in the request body for Altair to validate with your `oauth_application` list.
### prefix

Prefix of the service.

### host

Target host of the service. Example: `yourservice.com` or `localhost:8000`. The specified host must be written without the `http` or `https` protocol.

### path

List of service paths to be forwarded to the backend service. This will combine the service prefix with the path specified here, example:

- host: `www.example.com`
- prefix: `/users`
- path: `/address`
- combined path: `http://www.example.com/users/adress/`

#### scope

This config will only be validated if **oauth** plugin is **activated**, each scope separated by space `public users products`. This will validate a request-provided oauth token with the specified scope in each path. If it is empty then this validation will be skipped.

#### auth

The Oauth option for path scope, if empty will follow the authentication specified in the service.

- none: No authentication
- oauth: Oauth authentication, **plugin oauth is need to be activated to use this type of authentication**. If you choose this authentication, the client request must include the `Authorization` header in the request with the access token as the value `Bearer access-token-that-you-got-from-altair`.
- oauth_application: Oauth application authentication, **plugin oauth is need to be activated to use this type of authentication**. This feature is currently in a testing phase where you have to submit your request in json format and include `client_id` and `client_secret` in the request body for Altair to validate with your `oauth_application` list.

## Template Function

### env

env function will get environment variable based on given parameter. Example `env "DATABASE_NAME"` it will return `DATABASE_NAME` from your environment variables.
