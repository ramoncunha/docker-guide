## Docker Run

[Menu](../README.md)

Como o próprio nome já diz, o comando `run` é utilizado para colocar um conteinêr em execução já existente ou iniciar um novo.

### Comandos

#### Executar uma imagem

```
docker run {image-name}
```

Exemplo: `docker run hello-world`

#### Executar uma imagem com tag específica

```
docker run {image-name:tag}
```

Exemplo: `docker run postgres:latest`

#### Atribuir um nome ao conteinêr

```
docker run --name {nome-desejado} {image-name}
```

Dessa forma ficará mais fácil executar comando sobre esse conteinêr.

#### Associar um volume do seu computador

```
docker run -v {source-path}:{target-path-conteinêr} {image-name}
```

Exemplo: `docker run -v .:/var/www node`

#### Associar uma porta para comunicação local x conteinêr

```
docker run {image-name} -p {porta-local}:{porta-conteinêr}
```

Exemplo: `docker run node -p 3000:3000`