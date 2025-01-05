## Primeiros Passos

[Menu](../README.md)

### Primeiros Passos com Docker 👣

Aqui vamos subir uma imagem Docker, ver ela funcionando e depois excluindo tudo. Em apenas 9 passos. :)

#### 1. Verifique se o Docker está instalado
Antes de começar, certifique-se de que o Docker está instalado na sua máquina. Para verificar, execute:

```
docker --version
```

Este comando retornará a versão instalada do Docker.

#### 2. Execute seu primeiro container 

Para confirmar que o Docker está funcionando corretamente, execute um container simples:

```
docker run hello-world
```

Este comando baixa a imagem hello-world e a executa, exibindo uma mensagem de boas-vindas. A mensagem abaixo deve aparecer:

> Unable to find image 'hello-world:latest' locally
> latest: Pulling from library/hello-world
> . . .
> Hello from Docker!
> This message shows that your installation appears to be working correctly.

A primeira linha mostra que não foi possível encontrar a imagem na sua máquina, por isso, o Docker baixou automaticamente.
A segunda linha mostra o repositório de onde a imagem está sendo baixada, nesse caso, library/hello-world.
Após baixar aparecerá essa mensagem de Hello, isso mostra que o comandou foi executado com sucesso.

#### 3. Liste os containers ativos

Para ver os containers que estão sendo executados atualmente, use:

```
docker ps
```

Nesse caso não veremos nada, pois o hello-world apenas imprime uma mensagem na tela e o container é derrubado.
Para verificar que o container foi realmente criado adicione flag -a para incluir na listagem os containers que estão parados.

```
docker ps -a
```

#### 4. Exclua o container

Agora que vimos que o container foi criado e ele já funcionou, vamos excluir e criar outro. Utilize o comando abaixo para excluir:

```
docker rm <CONTAINER_ID>
```

```
docker rm <CONTAINER_NAME>
```

#### 5. Baixe uma imagem

Imagens são o nosso ponto de partida. Como você já percebeu, é com elas que criamos nossos containers. Para baixar uma imagem, utilize:

```
docker pull <IMAGE_NAME>
```

Nesse caso, vamos baixar a imagem do Nginx. Ele é um servidor web que serve como load balancer, proxy reverso, entre outros.

```
docker pull nginx
```

#### 6. Execute um container

Crie um container baseado na imagem que você baixou:

```
docker run -d -p 8080:80 nginx
```

`-d` executa o container em segundo plano, dessa forma não ficamos com o terminal travado.
`-p` mapeia a porta do host (8080) para a porta do container (80). Isso significa que ao acessar a porta 8080 da sua máquina, você estará acessando a porta 80 do container.

🤓 _Desafio:_
_Experimente rodar o docker run sem os parâmetros e veja o que acontece!_

#### 7. Abra o navegador e acesse o Nginx

Para garantir que o container está rodando corretamente abra o navegador e acesse `http://localhost:8080`.

Perceba que a porta 8080 é a que mapeamos anteriormente. Você deve ver a seguinte mensagem:

> Welcome to nginx!
> If you see this page, the nginx web server is successfully installed and working. Further configuration is required.
> For online documentation and support please refer to nginx.org.
> Commercial support is available at nginx.com.
> Thank you for using nginx.

Parabéns, isso significa que você tem uma aplicação rodando na sua máquina via Docker.

#### 8. Pare o container

Para parar um container em execução, utilize:

```
docker stop <CONTAINER_ID>
```

#### 9. Remova containers e imagens

Remover um container você ja sabe, então remova o container do nginx. Após isso, remova a imagem que você baixou.

- Para remover uma imagem:

```
docker rmi <IMAGE_NAME>
```

ou

```
docker image rm <IMAGE_NAME>
```

Caso tenha dúvida sobre o nome, execute o comando:

```
docker image ls
```