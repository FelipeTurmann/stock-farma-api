# stock-farma-api

Base do backend Stock Farma: Java 21, Spring Boot 4.0.8, Maven, Spring Security, JPA, PostgreSQL e Flyway.

## Executar

Configure `DB_URL`, `DB_USERNAME` e `DB_PASSWORD` no ambiente. O banco deve existir antes da inicialização.

```powershell
$env:DB_URL = 'jdbc:postgresql://localhost:5432/stockfarma'
$env:DB_USERNAME = 'stockfarma'
$env:DB_PASSWORD = '<sua-senha-local>'
.\mvnw.cmd spring-boot:run
```

Validação: `./mvnw verify` (Windows: `.\mvnw.cmd verify`).

API na porta 8080; saúde em `/actuator/health`. Somente saúde é pública. Os demais caminhos permanecem bloqueados até a implementação da Spec 1 (JWT/RBAC).

Pacotes por domínio em `src/main/java/com/farmaciastock`. Cada domínio receberá controller, service, repository, entity e DTO conforme necessário.

A especificação normativa está em `../Especificacao/Specs 1–5.md` no workspace de planejamento. O DDL de referência está em `../estrutura/data-model.txt`. Ainda não foi promovido a migration executável: há decisões pendentes na documentação. As migrations futuras ficam em `src/main/resources/db/migration`.

Esta entrega prepara a estrutura; autenticação, CRUD e movimentações serão desenvolvidos pelas Specs.
