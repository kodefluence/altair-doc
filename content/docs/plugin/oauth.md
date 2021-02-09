---
title: "Oauth"
description: "Oauth2 plugin embed in your API Gateway."
lead: "Oauth2 plugin embed in your API Gateway."
date: 2021-02-07T00:42:35+07:00
lastmod: 2021-02-07T00:42:35+07:00
draft: false
images: []
menu:
  docs:
    parent: "plugin"
weight: 201
toc: true
---

## Introduction

OAuth2 is an authorization framework that allows applications to gain limited access to user accounts on HTTP services, such as Facebook, GitHub, and DigitalOcean. It works by delegating user authentication to the service that hosts user accounts, and authorizing third-party applications to access user accounts. OAuth2 provides authorization streams for web and desktop applications, as well as mobile devices.

## OAuth2 in Altair

Common implementation in Altair authorization flow in Altair should be looks like this.

<br><img src="/oauth-grant-flow-01.png" width="575"/><br><br><br>

Explanation:

**Client** process request to server, then **Altair** with forward those request to the **Backend Service**. Then **Backend Service** would request granting access token for **resource_owner_id**, if the request is valid **Altair** will give access token object to **Backend Service** which will be returned to the **Client**. The end point shown in the figure above is [Access Token Grant](https://documenter.getpostman.com/view/3666028/SzmcZJ79?version=latest#3f47c350-6b28-4cba-950e-ae77a8e67d8d) endpoint.

## Prerequisites

To use this plugin, make sure you have MySQL installed on your machine.

## Installation

To use this plugin, make sure you have migrated the database required by this plugin by running `altair migrate [database_instance_name]`.

## Config

Oauth plugin config located in `config/plugin/oauth.yml`.

```yaml
plugin: oauth
config:
  database: main_database
  access_token_timeout: 24h
  authorization_code_timeout: 24h
```

### plugin

Plugin name, in this case `oauth`.

### config.database

The [database instance](/docs/prologue/config/#databaseyml) used in the OAuth plugin. If the instance doesn't exist it will return an error when running Altair.

### config.access_token_timeout

The duration of the access token expiration.

### authorization_code_timeout

The duration of the authorization code expiration.

## Routes

The role of oauth in Altair routes is for authentication purposes on every request. See [here](/docs/prologue/routes/#auth-1).
