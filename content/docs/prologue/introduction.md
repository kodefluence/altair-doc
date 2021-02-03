---
title: "Introduction"
description: "Altair is an open source API gateway written in Go. Designed to be distributed, lightweight, simple, fast, reliable, cross platform, programming language agnostic and robust - by default"
lead: "Altair is an open source API gateway written in Go. Designed to be distributed, lightweight, simple, fast, reliable, cross platform, programming language agnostic and robust - by default"
date: 2021-02-03T21:25:12+07:00
lastmod: 2021-02-03T21:25:12+07:00
draft: false
images: []
menu:
  docs:
    parent: "prologue"
weight: 100
toc: true
---

## Why Altair

There are various API Gateways available to you when you want to distribute your service or split it into microservices. However we believe Altair is the best choice for building your API Gateway because of its simplicity.

### Distributed

Altair is designed to be distributed, but it can also be a monolithic reverse proxy. What we mean by distributed is that all plugins can be modified according to your choice, you can choose the OAuth plugin and the interface will be mysql, postgre, redis, or an external service in the future. Or have a cache mechanism with memcache or redis. All of them are free and can be configured easily.

### Simple and Fast

Altair is designed to have as many plugins as possible, we aim to support all the tools available for API Gateway for free and can be used interchangeably and sequentially. Even when you want to build an application you don't have to think about or create a flow of authentication and auhorization. Since altair already supports it, simply migrate with the command line and it's ready to go.

Altair is the right choice when you need to build an API service with oauth flow, because we already have it and it will speed up your development.

### Programming Language Agnostic

You don't really have to master any new programming language to understand altair, except yaml. We designed the Altair to be as simple as possible so that anyone can jump right into the configuration and make changes easily without even understanding Go. It can be paired from any service with any programming language.

### Cross Platform

Altair can run on popular platforms such as **Linux**, **Windows**, and **Mac**. Thanks to Go for being cross-platform.
