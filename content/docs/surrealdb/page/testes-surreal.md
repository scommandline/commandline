---
date: 2022-11-20T12:30:00+06:00
lastmod: 2022-11-07T02:00:00+06:00
title: "Surrealdb Instalação"
categories:
  - database
tags:
  - surrealdb
slug: install-surreal
---

/*
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
*/