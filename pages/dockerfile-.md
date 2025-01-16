## Dockerfile

[Menu](../README.md)

É utilizado para criar imagens docker personalizadas. Ou seja, você pode criar a iamgem da sua aplicação e distribuir ela pela internet. O processo é simples, primeiro vamos criar um Dockerfile, depois builda a imagem e por fim envia ela para o DockerHub. Ficou curioso? Já entra no DockerHub e cria sua conta.

### Primeiro vamos a um exemplo de Dockerfile bem completinho

```
FROM eclipse-temurin:17-jdk-jammy AS build

WORKDIR /app
COPY . /app
RUN ["chmod", "+x", "mvnw"]
RUN ["./mvnw", "-Dmaven.test.skip", "package"]

FROM eclipse-temurin:17-jdk-jammy AS dev

WORKDIR /app
COPY --from=build /app/target/my-app.jar /app/my-app.jar
EXPOSE 8080

ENTRYPOINT ["java", "-Xms750m", "-Xmx750m", "-jar", "my-app.jar"]
```

Antes de entrar nos detalhes desse Dockerfile o que ele faz? Ele cria uma imagem customizado de uma aplicação Java buildada e pronta para produção.
