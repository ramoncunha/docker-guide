## Docker Images

[Menu](../README.md)

As imagens são as aplicações em si. Por exemplo, quando você deseja rodar um banco de dados, você vai baixar a imagem de um PostgreSQL, MongoDB ou qualquer outro que esteja disponível. Essas imagens são disponibilizadas oficialmente no hub.docker.com e você pode até mesmo criar uma conta e fazer o upload de imagens customizadas.

### Comandos

#### Listar todas as imagens disponíveis na sua máquina

```
docker images
```

#### Baixar uma imagem 

```
docker pull <IMAGE_NAME>
```

Caso queira baixar a última versão disponível basta não colocar a tag

Exemplo: `docker pull postgres:10`

#### Verificar detalhes da imagens e ver informações como data de criação, variáveis de ambiente utilizadas, etc

```
docker image inspect <IMAGE_NAME>
```

Exemplo: `docker image inspect postgres`

#### Enviar imagem para Docker Hub

```
docker push <IMAGE_NAME>
```

Exemplo: `docker push ramoncunha/nodejs`

#### Remover uma imagem

```
docker image rm <IMAGE_ID>
```
ou 

```
docker image rm <IMAGE_NAME>
```

Exemplo: `docker image rm 7164c9b9f1f7`

#### Remover todas as imagens de uma só vez

```
docker rmi $(docker images -q)
```