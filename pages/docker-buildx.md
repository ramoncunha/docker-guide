## Docker Buildx

[Menu](../README.md)


### Comandos

#### Listar buildx disponíveis

Exemplo: `docker buildx ls`

#### Criar buildx e torna-lo padrão

Exemplo: `docker buildx create --name mybuilder --driver docker-container --use`

#### Remover buildx

Exemplo: `docker buildx rm mybuilder`

#### Buildar Dockerfile para diferentes plataformas e enviar para DockerHub

Exemplo: `docker buildx build --platform linux/amd64,linux/arm64 -t seu_user/sua_imagem:latest . --push`