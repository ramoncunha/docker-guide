## Docker Run

[Menu](../README.md)

Como o próprio nome já diz, o comando `run` é utilizado para colocar um container em execução já existente ou iniciar um novo.

### Comandos

#### Executar uma imagem

```
docker run <IMAGE_NAME>
```

Exemplo: `docker run hello-world`

#### Executar uma imagem e após isso, exclui o container

```
docker run --rm <IMAGE_NAME>
```

Exemplo: `docker run --rm hello-world`

#### Executar uma imagem com tag específica

```
docker run <IMAGE_NAME:TAG>
```

Exemplo: `docker run postgres:latest`

#### Passar variáveis na criação

```
docker run -e <ENV> = value <IMAGE_NAME>
```

Exemplo: `docker run -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=secret postgres`

Esse comando é útil quando sua imagem requer a informação de variáveis de ambiente para subir, como é o exemplo do PostgreSQL que necessita que você informe user e password.

#### Iniciar um container no modo detach


```
docker run -d <IMAGE_NAME>
```

Exemplo: `docker run -d -e POSTGRES_USER=admin -e POSTGRES_PASSWORD=secret postgres`

Com o -d seu terminal não irá ficar travado na execução do container.

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

O . (ponto) nesse caso vai servir para mapear a pasta em que você está no momento.

#### Associar uma porta para comunicação local x container

```
docker run <IMAGE_NAME> -p <PORTA_LOCAL>:<PORTA_CONTAINER>
```

Exemplo: `docker run node -p 3000:3000`

Quando você se conetar a porta 3000 do seu computador, estará se conectando a porta 3000 do container.

#### Associar uma network

```
docker run --network <NOME_DA_REDE> <IMAGE_NAME>
```

Exemplo: `docker run --network minha-rede hello-world`

O novo container será criado e associado a rede minha-rede.

#### Você pode utilizar quantos comandos quiser ao mesmo tempo

```
docker run -d --name <CONTAINER_NAME> -p <PORTA_LOCAL>:<PORTA_CONTAINER> -v <SOURCE_PATH>:<TARGET_PATH_CONTAINER> --network <NOME_DA_REDE> <IMAGE_NAME>
```

Exemplo: 
```
docker run -d \
  --name meu-container \
  -p 8080:80 \
  -v $(pwd)/dados:/app/dados \
  --network minha-rede \
  -e VARIAVEL=valor \
  minha-imagem`
```