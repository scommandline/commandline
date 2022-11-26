---
date: 2022-11-20T12:30:00+06:00
lastmod: 2022-10-21T02:00:00+06:00
title: "Surrealdb - Inicializando"
authors: ["sidon"]
categories:
  - database
tags:
  - surrealdb
slug: connecting-surreal
---

## Inicializando

SurrealDB foi concebido para ser rápido e fácil, isso também se aplica a sua inicialização. Ainda não temos (no momento da escrita desse texto) um cliente GUI para iniciar e importar/exportar dados, mas isso não significa complexidade, na verdade é muito simples através da linha de comando.

### macOS/Linux

``` Bash
user@localhost % surreal start --log debug --user root --pass root memory
```

### Windows

``` Bash
PS C:\> surreal.exe start --log debug --user root --pass root memory
```

#### Output

Em qualquer um dos ambientes a saída resultante do comando deverá ser algo parecido com o apresentado abaixo:

``` Bash
[2022-07-28 15:50:34] INFO  surrealdb::iam Root authentication is enabled
[2022-07-28 15:50:34] INFO  surrealdb::dbs Database strict mode is disabled
[2022-07-28 15:50:34] INFO  surrealdb::kvs Starting kvs store in memory
[2022-07-28 15:50:34] INFO  surrealdb::kvs Started kvs store in memory
[2022-07-28 15:50:34] INFO  surrealdb::net Starting web server on 0.0.0.0:8000
[2022-07-28 15:50:34] INFO  surrealdb::net Started web server on 0.0.0.0:8000
```
