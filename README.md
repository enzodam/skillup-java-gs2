# SkillUp API

**Aplicação web (Global Solution Java Advanced) desenvolvida com Spring Boot, Spring Security, Spring AI, RabbitMQ e PostgreSQL.**

Objetivo: ajudar pessoas a requalificarem suas carreiras.  
O SkillUp conecta usuários, cursos e objetivos a partir de recomendações inteligentes, usando IA para sugerir trilhas personalizadas de aprendizado alinhadas ao perfil profissional.

---

## O que foi implementado (rubrica completa do desafio)

* Configuração via anotações do Spring (injeção de dependências, controllers, services e beans)
* Model e DTOs com encapsulamento correto
* Spring Data JPA para persistência
* Bean Validation (validações de campos)
* Paginação para rotas com muitos registros
* Caching para melhorar a performance
* Internacionalização (pt e en)
* Spring Security com autenticação via JWT
* Tratamento de erros centralizado (Exception Handler)
* Mensageria assíncrona com RabbitMQ
* Inteligência Artificial Generativa com Spring AI
* Deploy em nuvem (Render)
* API REST seguindo boas práticas de verbos HTTP e códigos de status

---

## Stack

* Java 17 • Spring Boot 3
* Spring Web • Spring Data JPA
* Spring Security (JWT)
* Spring Validation
* Spring Cache
* Spring AMQP para RabbitMQ
* Spring AI
* PostgreSQL
* Docker e Render para deploy

---

## Estrutura do projeto

```text
src/main/java/...
  controller/      # Controllers REST
  model/           # Entidades JPA
  dto/             # Objetos de transferência de dados
  service/         # Regras de negócio
  repository/      # Repositórios JPA
  security/        # Configuração de JWT
  ai/              # Serviço de IA (Spring AI)
  messaging/       # Integração RabbitMQ

src/main/resources/
  messages.properties        # pt
  messages_en.properties     # en
  application.properties
````

---

## Acesso e Segurança
A API utiliza JWT para autenticação.

1. Faça login para receber um token.

2. Envie o token no header Authorization para acessar rotas protegidas.

Rotas públicas e privadas foram configuradas separadamente, garantindo segurança e organização.

---

## Configuração por variáveis de ambiente
```
server.port=${PORT:${SERVER_PORT:8080}}

spring.datasource.url=${SPRING_DATASOURCE_URL}
spring.datasource.username=${SPRING_DATASOURCE_USERNAME}
spring.datasource.password=${SPRING_DATASOURCE_PASSWORD}

spring.rabbitmq.host=${SPRING_RABBITMQ_HOST}
spring.rabbitmq.port=${SPRING_RABBITMQ_PORT}
spring.rabbitmq.username=${SPRING_RABBITMQ_USERNAME}
spring.rabbitmq.password=${SPRING_RABBITMQ_PASSWORD}

spring.ai.openai.api-key=${SPRING_AI_OPENAI_API_KEY:dummy}
````
Variáveis aceitas:

- SPRING_DATASOURCE_URL
- SPRING_DATASOURCE_USERNAME
- SPRING_DATASOURCE_PASSWORD
- SPRING_RABBITMQ_HOST
- SPRING_RABBITMQ_PORT
- SPRING_RABBITMQ_USERNAME
- SPRING_RABBITMQ_PASSWORD
- SPRING_AI_OPENAI_API_KEY

---

## Rotas principais

Autenticação

- POST /auth/login

- POST /auth/register

Usuários

- GET /usuarios (paginado)

- GET /usuarios/{id}

- POST /usuarios

- PUT /usuarios/{id}

- DELETE /usuarios/{id}

Cursos

- GET /cursos (paginado)

- POST /cursos

- PUT /cursos/{id}

- DELETE /cursos/{id}

Recomendações com IA

- POST /ai/recomendar

Mensageria

- POST /fila/enviar

---

## Deploy na nuvem
A API está rodando no Render:

[aplicção](https://skillup-java-gs2.onrender.com/)

---

## Vídeo demonstrativo

[Vídeo]()

---

## 👨‍💻 Desenvolvedores

| Nome                          | RM      | GitHub |
|-------------------------------|---------|--------|
| Enzo Dias Alfaia Mendes       | 558438  | [@enzodam](https://github.com/enzodam) |
| Matheus Henrique Germano Reis | 555861  | [@MatheusReis48](https://github.com/MatheusReis48) |
| Luan Dantas dos Santos        | 559004  | [@lds2125](https://github.com/lds2125) |
