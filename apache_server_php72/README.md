# Apache Server PHP 7.2

## Requisitos
docker, docker-compose e git.

## Resumo
Esse projeto está determinado para o banco de dados atuar na porta 3307, e o servidor web na porta 5000.
O diretório de trabalho principal chama-se "projeto"

## Passo a passo da utilização
Dentro desse diretório, acesse o arquivo Dockerfile no diretório composer, e em seguida, altere a seguinte linha com seu usuário:

```
de
ARG user="seu_usuario"
para
ARG user="joao"
```

Retorne a raíz (apache_server_php72), via terminal, e utilize o seguinte comando:

```
docker-compose up
```

Para utilizar o composer, busque o image_id do mesmo com o seguinte comando:

```
docker images
```

Copie o image_id, e substitua-o no seguinte comando:

```
docker run -v $(pwd)/projeto:/app -it image_id entrypoint install
# O install após o entrypoint, pode ser qualquer comando do composer
```

Para utilizar o nodejs, de forma semelhante utilize:

```
docker run -it -v $(pwd)/projeto:/app image_id npm install
```
