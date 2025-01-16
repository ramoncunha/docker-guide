## Docker Exec

[Menu](../README.md)

O comando `docker exec` permite executar comandos em um container que já está em execução. Ele é útil para realizar tarefas de manutenção, depuração ou para interagir diretamente com o ambiente do container.

Para interagir com esse comando você pode usar <CONTAINER_NAME> ou <CONTAINER_ID>, sendo assim vou usar apenas a tag <CONTAINER> para indicar o que pode ser usado.

### Comandos

#### Conectar o seu terminal ao terminal do container

```
docker exec -it <CONTAINER> <COMANDO>
```

Exemplo: `docker exec -it meu-container bash`

-i (--interactive) deixa o STDIN do container aberto para que possamos enviar comandos a ele. Isso é útil quando queremos concatenar comandos com o pipe como em `echo hello | docker run --rm -i busybox cat`.

-t (--tty) para que você possa usar o terminal é necessário indicar o -t. bash é o programa que permite que tenha um terminal dentro do linux

#### Executar qualquer comando

```
docker exec <CONTAINER> <COMANDO>
```

Exemplo: `docker exec meu-container ls`

O retorno será a lista de arquivos do seu container no diretório padrão.