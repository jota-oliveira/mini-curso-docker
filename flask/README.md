# FLASK - Restful

## Requisitos
docker, docker-compose e git.

## Resumo
Esse projeto está determinado para atuar na porta 5000.
O diretório de trabalho principal chama-se "app"

## Passo a passo da utilização
Dentro desse diretório, utilize o seguinte comando:

```
docker-compose up
```

Após a criação das imagens através do comando acima, verifique o image_id com o seguinte comando:

```
docker images
```

Após identificar o image_id, substitua-o no código abaixo:

```
docker run -v $(pwd)/app:/app -p 5000:5000 -it image_id python3 api.py
```
