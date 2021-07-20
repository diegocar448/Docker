# Docker

## Comandos utilizados no Docker

* https://hub.docker.com/
* https://ubuntu.com/download/server

## Mount

### Bind

* As montagens Bind são basicamento apenas vincular um determinado diretório ou arquivo do host dentro do container:

```
docker run -v /hostdir:/containerdir mysql
```