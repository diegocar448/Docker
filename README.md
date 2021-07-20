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

### Named

* Volumes nomeados são volumes que você cria manualmente com o comando: 

```
docker volume create nome-do-volume
```

* Eles são criados em /var/lib/docker/ volumes e podem ser referenciados apenas por seu nome.
* Digamos que você crie um volume chamado "mysql_data", você pode apenas referenciá-lo como o comando:

```
docker run -v mysql_data:/containerdir mysql
```

### dockerfile volume

* Tipo de volume que são criados pela instrução VOLUME. Esses volumes também são criados em /var/lib/docker/ volumes, mas não têm um determinado nome. O volume é criado ao executar o contêiner e são úteis para salvar dados persistentes. O desenvolvedor pode dizer onde estão os dados importantes e o que deve ser persistente.

### Qual devo utilizar?

* Depende de você. Se você quiser manter tudo na "área do docker" (/var/lib/docker), você pode usar volumes. Se você deseja manter sua propria estrutura de diretorio, você poder usar binds.
* O Docker recomenda o uso de volumes em vez do uso de binds, pois os volumes são criados e gerenciados pelo docker.