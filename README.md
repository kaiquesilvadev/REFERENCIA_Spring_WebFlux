![Java](https://img.shields.io/badge/Java-11-orange.svg)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-2.5.4-brightgreen.svg)

# Reactive Backend using Spring Webflux and Mongodb
>  Estudo de caso para implementar um backend reativo usando spring webflux e mongodb no projeto base dsposts

##  Introdução ao Spring Webflux

Spring Webflux é um framework reativo oferecido pela plataforma Spring que permite o desenvolvimento de aplicativos assíncronos e não bloqueantes em Java. Ele é especialmente adequado para construir sistemas de alta concorrência e escalabilidade, utilizando programação reativa para lidar com grandes volumes de requisições de forma eficiente e responsiva.

## Diagrama de Classes

> O diagrama de classes apresenta a estrutura do projeto e as relações entre as diferentes classes e entidades. Ele fornece uma visão visual do design da aplicação e ajuda a entender como as partes do sistema interagem entre si

![UML](https://github.com/kaiquesilvadev/REFERENCIA_Spring_WebFlux/blob/main/assets/model-spring-mongodb.png)

# Endpoints Disponíveis do projeto

## Controlador de Postagens

> Este controlador gerencia as requisições relacionadas às postagens de usuários.

### Endpoints Disponíveis

- `GET /posts/{id}`: Retorna uma postagem específica com base no ID fornecido.
- `GET /posts/titlesearch?text={text}`: Retorna todas as postagens que contenham o texto fornecido no título.
- `GET /posts/fullsearch?text={text}&minDate={minDate}&maxDate={maxDate}`: Retorna todas as postagens que correspondam aos critérios de pesquisa fornecidos.

#### Observações

- O endpoint `GET /posts/{id}` verifica se a postagem com o ID fornecido existe antes de retornar os dados. Caso contrário, retorna um erro 404.
- O endpoint `GET /posts/fullsearch` permite pesquisar postagens com base em um texto, data mínima e data máxima. Os resultados são filtrados de acordo com esses critérios.

---

## Controlador de Usuários

> Este controlador gerencia as requisições relacionadas aos usuários do sistema.

### Endpoints Disponíveis

- `GET /users`: Retorna todos os usuários cadastrados.
- `GET /users/{id}`: Retorna um usuário específico com base no ID fornecido.
- `POST /users`: Cria um novo usuário com base nos dados fornecidos.
- `PUT /users/{id}`: Atualiza as informações de um usuário existente com base no ID fornecido.
- `DELETE /users/{id}`: Exclui um usuário existente com base no ID fornecido.

#### Observações

- Os endpoints `GET /users/{id}`, `PUT /users/{id}`, e `DELETE /users/{id}` verificam se o usuário com o ID fornecido existe antes de realizar a operação. Caso contrário, retorna um erro 404 no caso dos métodos GET e PUT, e um 204 no caso do DELETE.
- O endpoint `POST /users` retorna um código de status 201 (Created) juntamente com os dados do novo usuário criado.

#### Base repository

> material oferecido pelo DevSuperior

[Spring MongoDB Reference Project](https://github.com/devsuperior/spring-mongodb-ref)

## passo a passo para implementar Spring Webflux

- Passo 1
Incluir ao final a dependência do  mongtodB -reactive 

```java
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-data-mongodb</artifactId>
</dependency>
```

dessa maneira 

```java
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-data-mongodb-reactive</artifactId>
</dependency>
```

- Passo 2

trocar a dependência do starter-web

```java
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-web</artifactId>
</dependency>
```

dessa maneira

```java
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-webflux</artifactId>
</dependency>
```
### Pré-requisitos para testar o projeto

- Java Development Kit (JDK)
- MongoDB em execução
- IDE de sua escolha (recomendado: IntelliJ IDEA ou Spring Tool Suite)

### Container Docker do MongoDB para desenvolvimento

```
docker run -d -p 27017:27017 -v /data/db --name mongo1 mongo:4.4.3-bionic
```

```
docker exec -it mongo1 bash
```
## Recursos adicionais

### Documentação MongoDB: query operators

https://docs.mongodb.com/manual/reference/operator/query

### Documentação Spring Data MongoDB

https://docs.spring.io/spring-data/mongodb/docs/current/reference/html

### Localização dos volumes Docker no Windows

https://stackoverflow.com/questions/43181654/locating-data-volumes-in-docker-desktop-windows
