## Docker Run

[Menu](../README.md)

Como o próprio nome já diz, o comando `run` é utilizado para colocar um container em execução já existente ou iniciar um novo.

### Comandos

#### Executar uma imagem

```
docker run <IMAGE_NAME>
```

Exemplo: `docker run hello-world`

#### Executar uma imagem com tag específica

```
docker run <IMAGE_NAME>
```

Exemplo: `docker run postgres:latest`

#### Atribuir um nome ao container

```
docker run --name <NOME_DESEJADO> <IMAGE_NAME>
```

Dessa forma ficará mais fácil executar comando sobre esse container.

#### Associar um volume do seu computador

```
docker run -v <SOURCE_PATH>:<TARGET_PATH_CONTAINER> <IMAGE_NAME>
```

Exemplo: `docker run -v .:/var/www node`

#### Associar uma porta para comunicação local x container

```
docker run <IMAGE_NAME> -p <PORTA_LOCAL>:<PORTA_CONTAINER>
```

Exemplo: `docker run node -p 3000:3000`