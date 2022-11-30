---
title: "Teste (introducao.md) Introdução ao Surreal"
description: "Teste"
excerpt: "Introdução ao banco de dados Surrealdb."
date: 2022-11-04T09:19:42+01:00
lastmod: 2022-11-04T09:19:42+01:00
draft: false
toc: true
weight: 50
images: ["introducao.png"]
categories: ["Database"]
tags: ["Surreal"]
contributors: ["Sidon Duarte"]
---

## O que é o SurrealDB

O produto é realmente surreal, embora já esteja funcional, no momento da produção desse texto (11/2022) ainda está na fase inicial de desenvolvimento, interface GUI, clientes para a maioria das linguagens main-strema ainda estão sendo desenvolvidos, por exemplo. A melhor descrição talvez esteja no site do produto, abaixo, em tradução livre, tento fazer um resumo.

> Banco de dados Web flexível, amigável ao desenvolvedor, totalmente ACID transacional, baseado em grafos e documentos em tempo real para aplicativos sem servidor.
>

### Destaques

#### Single Node ou distribuido

Pode ser executado em um único nó (na memória ou usando armazenamento em disco) ou em um cluster distribuído altamente disponível.

#### Modelagem de dados flexivel

Usando uma linguagem de consulta avançada, o SurrealDB permite armazenar e acessar dados usando metodologias relacionais, documentais, gráficas e integradas. 

#### Dados estruturados e não estruturados 

O banco é schemafull e, simultaneamente schemaless, volce escolhe o que cada tabela vai ser.

#### Consultas usando SQL 

SurrealQL é a linguagem de consulta, uma versão modificada do SQL tradicional.

#### GraphQL, REST ou WebSockets

Ao conectar-se diretamente de um dispositivo de usuário final, você pode optar por consultar os dados usando SurrealQL, GraphQL ou usando uma API REST tradicional. Além disso, os WebSockets permitem a sincronização bidirecional em tempo real de alto desempenho de quaisquer dados atualizados.

#### Indexação de várias colunas em tempo real

#### Bancos de dados multi-tenant

Com suporte para namespaces e bancos de dados, o SurrealDB permite que você separe seus dados como desejar, simplificando o desenvolvimento de aplicativos SaaS.

## Instalação

### Docker

Se voce tem o docker e não deseja instalar diretamente na sua máquina de trabalho, instale o servidor através de um container docker, com o comando:

```ssh
docker run --rm -p 8000:8000 surrealdb/surrealdb:latest start
```

### Windows

A forma de instalar no windows é semelhante a forma de instação no linux, o equivalente ao `curl`, no windows é o comando [`Invoke-WebRequest`]([Invoke-WebRequest (Microsoft.PowerShell.Utility) - PowerShell | Microsoft Learn](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-7.3)). O site do surreal indica o seguinte comando para instalação:

```ssh
iwr https://windows.surrealdb.com -useb | iex
```

Obs. Esse é um comando do [Powershell]([O que é o PowerShell? - PowerShell | Microsoft Learn](https://learn.microsoft.com/pt-br/powershell/scripting/overview?view=powershell-7.3)) e dependendo da versão, pode não funcionar da forma como está, se for o caso, tente trocar o `iwr` por  `Invoke-WebRequest`.  

### macOS

A forma mais fácil é atravé do Homebrew, se voce não o tem instalado, siga as mesmas instruções para instalação no linux:

``` ssh
user@localhost % brew install surrealdb/tap/surreal
```

### Linux

A melhor forma de instalar em sistemas linux é através do comando `curl` :

``` ssh
curl -sSf https://install.surrealdb.com | sh
```

## Conectando 

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