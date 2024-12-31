## Primeiros Passos

[Menu](../README.md)

### Primeiros Passos com Docker

Aqui vamos subir uma imagem Docker, ver ela funcionando e depois excluindo tudo. Em apenas 8 passos. :)

#### 1. Verificar se o Docker está instalado
Antes de começar, certifique-se de que o Docker está instalado na sua máquina. Para verificar, execute:

```
docker --version
```

Este comando retornará a versão instalada do Docker.

#### 2. Executar seu primeiro container

Para confirmar que o Docker está funcionando corretamente, execute um container simples:

```
docker run hello-world
```

Este comando baixa a imagem hello-world (se ainda não estiver disponível) e a executa, exibindo uma mensagem de boas-vindas.

#### 3. Listar containers ativos

Para ver os containers que estão sendo executados atualmente, use:

```
docker ps
```

Você também pode adicionar a flag -a para listar os containers que estão parados, se houver.

```
docker ps -a
```

#### 4. Baixar uma imagem

Imagens são o ponto de partida para criar containers. Para baixar uma imagem, utilize:

```
docker pull nginx
```

Nesse caso, vamos baixar a imagem do Nginx. Ele é um servidor web que serve como load balancer, proxy reverso, entre outros.

#### 5. Executar um container

Execute um container baseado na imagem que você baixou:

```
docker run -d -p 8080:80 nginx
```

`-d` executa o container em segundo plano.
`-p` mapeia a porta do host (8080) para a porta do container (80).

#### 6. Abra o navegador e acesse o Nginx

Para garantir que o container está rodando corretamente abra o navegador e acesse `http://localhost:8080`.

Perceba que a porta 8080 é a que mapeamos anteriormente.

#### 7. Parar um container

Para parar um container em execução, utilize:

```
docker stop <CONTAINER_ID>
```

#### 8. Remover containers e imagens

- Para remover um container:

```
docker rm <CONTAINER_ID>
```

- Para remover uma imagem:

```
docker rmi <IMAGE_NAME>
```

ou

```
docker image rm <IMAGE_NAME>
```