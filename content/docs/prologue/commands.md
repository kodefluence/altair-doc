---
title: "Commands"
description: "Altair comes with CLI."
lead: "Altair comes with CLI."
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

## run

Start Altair's server.

{{< btn-copy text="./altair run" >}}

```bash
./altair run
```

## config

Show and validate all config in Altair's application.

{{< btn-copy text="./altair config all" >}}

```bash
./altair config all
```

To see application config.

{{< btn-copy text="./altair config app" >}}

```bash
./altair config app
```

To see database instances config.

{{< btn-copy text="./altair config db" >}}

```bash
./altair config db
```

## migrate

To migrate the databases

{{< btn-copy text="./altair migrate" >}}

```bash
./altair migrate [database instance name]
```

## migrate:down

To reset all of the migration

{{< btn-copy text="./altair migrate:down" >}}

```bash
./altair migrate:down [database instance name]
```

## migrate:rollback

To rollback previous migrations

{{< btn-copy text="./altair migrate:rollback" >}}

```bash
./altair migrate:rollback [database instance name]
```
