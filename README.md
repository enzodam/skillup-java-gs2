# SkillUp API

Projeto exemplo para a disciplina de Java Advanced.

Requisitos contemplados:
- Spring Boot Web (API REST) + páginas HTML simples
- Anotações do Spring para beans e DI
- Camada model/DTO com getters/setters
- Spring Data JPA + PostgreSQL
- Bean Validation
- Caching com @EnableCaching e @Cacheable
- Internacionalização (messages.properties e messages_pt_BR.properties)
- Paginação em endpoints com muitos registros (Pageable)
- Spring Security (autenticação por email/senha e roles USER/ADMIN)
- Tratamento global de erros com @RestControllerAdvice
- Mensageria com filas assíncronas (RabbitMQ)
- Spring AI para recomendações de cursos
- Flyway para versionamento do banco
- Pronto para deploy em nuvem (Render, Railway, etc.)

## Usuários

A criação de usuários é feita pela tela /register ou via endpoint POST /api/auth/register.
Na tela de registro é possível escolher se o usuário será USER ou ADMIN.

No primeiro registro como ADMIN, a role ROLE_ADMIN é criada automaticamente.

## Como rodar

1. Ajuste o `application.properties` com a URL do seu PostgreSQL.
2. Execute:
   ```bash
   mvn spring-boot:run
   ```
3. Acesse:
   - http://localhost:8080/register para registrar usuário ou admin
   - http://localhost:8080/login para login
   - Endpoints REST sob `/api/**`.

Para uso real da IA, configure a variável de ambiente `OPENAI_API_KEY`.
