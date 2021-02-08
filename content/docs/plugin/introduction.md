---
title: "Introduction"
description: "Introduction to Altair's Plugin"
lead: "Introduction to Altair's Plugin"
date: 2021-02-08T21:39:44+07:00
lastmod: 2021-02-08T21:39:44+07:00
draft: false
images: []
menu:
  docs:
    parent: "plugin"
weight: 200
toc: true
---

## Definition

Plugin definitions in the Altair ecosystem are optional features that you can enable to support your system and architecture. All plugins have endpoints which are accessible via HTTP and configurable via the yaml file, there are also plugins that let you have additional features on your route yaml such as the oauth plugin which can be activated to authenticate your request to include a bearer token.

## Pattern

All plugin features can be accessed via HTTP with the prefix `_plugins`, for example the plugin URL of oauth `http://localhost:1304/_plugins/oauth/applications` which allows you to view all oauth applications. `_plugins` feature is protected with basic authentication, which you can set up in your [application configuration](/docs/prologue/config/#authorization).

To activate plugins you could add [available plugin](#list) in your [application configuration](/docs/prologue/config/#plugins).

## Documentation

All plugin features are documented in this [Postman API Documentation](https://documenter.getpostman.com/view/3666028/SzmcZJ79?version=latest#b870ae5a-b305-4016-8155-4899af1f26b1).

## List

### Oauth

The [Oauth plugin](/docs/plugin/oauth/) allows you to authenticate all your requests with bearer tokens and application authentication. Altair speeds up your development experience with this plugin so you can speed up your development without the hassle of developing an oauth flow first.
