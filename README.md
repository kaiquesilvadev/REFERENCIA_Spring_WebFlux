# Reactive Backend using Spring Webflux and Mongodb
>  Estudo de caso para implementar um backend reativo usando spring webflux e mongodb no projeto base dsposts

##  Introdução ao Spring Webflux

Spring Webflux é um framework reativo oferecido pela plataforma Spring que permite o desenvolvimento de aplicativos assíncronos e não bloqueantes em Java. Ele é especialmente adequado para construir sistemas de alta concorrência e escalabilidade, utilizando programação reativa para lidar com grandes volumes de requisições de forma eficiente e responsiva.



#### Base repository

material oferecido pelo DevSuperior

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

