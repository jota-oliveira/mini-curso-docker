# NODEJS

## Requisitos
docker, docker-compose e git.

## Resumo
Esse projeto está determinado para utilização do nodejs em qualquer arquivo do sistema.
O diretório app foi desenvolvido para que você possa testar o container.

## Passo a passo da utilização
Dentro desse diretório, utilize o seguinte comando:

```
docker-compose up
```

Após a criação das imagens, busque o image_id através do seguinte comando:
```
docker images
```

Com o image_id, substitua-o no comando abaixo:
```
docker run -it -v $(pwd)/app:/app image_id npm install
```
