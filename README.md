```markdown
# CreateUrlLambda

## Descrição

Este projeto é uma função AWS Lambda para encurtar URLs. Ele recebe uma URL original e um tempo de expiração, e retorna um código curto que pode ser usado para acessar a URL original.

## Requisitos

- Java 17
- Maven

## Dependências

- `com.amazonaws:aws-lambda-java-core:1.2.1`
- `com.amazonaws:aws-lambda-java-log4j2:1.2.0`
- `org.projectlombok:lombok:1.18.34`
- `com.fasterxml.jackson.core:jackson-databind:2.12.3`

## Estrutura do Projeto

- `src/main/java/com/rocketseat/createUrlShortner/Main.java`: Classe principal que implementa a função Lambda.

## Como Construir

Para construir o projeto, execute o seguinte comando Maven:

```sh
mvn clean package
```

## Como Implantar

1. Faça o upload do arquivo JAR gerado (`target/CreateUrlLambda-1.0-SNAPSHOT.jar`) para o AWS Lambda.
2. Configure a função Lambda para usar a classe `com.rocketseat.createUrlShortner.Main` como o handler.

## Exemplo de Uso

A função Lambda espera um JSON com um body de entrada com os seguintes campos:

```json
{
  "originalUrl": "http:example.com",
  "expirationTime": "2023-12-31T23:59:59Z"
}
```

A resposta será um JSON com o código curto:

```json
{
  "code": "abcd1234"
}
```

## Aviso
Esse projeto faz parte da imersão backend da Rocketseat.
```