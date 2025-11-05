# News Platform — Микросервисная архитектура

> **Микросервисная платформа для управления новостями, комментариями и пользователями с ролевой моделью доступа.**

---

## Общее описание

Проект представляет собой **микросервисную архитектуру**, состоящую из двух независимых сервисов:

| Сервис | Назначение | Ссылка |
|-------|-----------|------|
| **NewsLogicServer** | Работа с новостями и комментариями: CRUD, поиск, пагинация, фильтрация | [GitHub](https://github.com/MrFurion/NewsLogicServer) |
| **NewsSecurityServer** | Аутентификация и авторизация пользователей (JWT), управление ролями | [GitHub](https://github.com/MrFurion/NewsSecurityServer) |
---

## Архитектура

```text
Клиент (Frontend / Postman / Swagger)
        │
        ├──→ NewsSecurityServer (Auth)
        │       └── JWT Token
        │
        └──→ NewsLogicServer (Business Logic)
                └── Все операции с новостями и комментариями

- **NewsSecurityServer** — отвечает за:
  - Регистрацию (`POST /auth/signup`)
  - Вход в систему (`POST /auth/login` → JWT)
  - Роли: `ADMIN`, `JOURNALIST`, `SUBSCRIBER`

- **NewsLogicServer** — отвечает за:
  - CRUD новости и комментариев
  - Полнотекстовый поиск
  - Пагинацию
  - Ролевой доступ через JWT
```
---

## Быстрый старт

### Предварительные требования
- Docker & Docker Compose
- Java 17+
- IntelliJ IDEA (рекомендуется)

### Запуск системы

1. **Клонируйте оба репозитория:**
   ```bash
   git clone https://github.com/MrFurion/NewsSecurityServer.git
   git clone https://github.com/MrFurion/NewsLogicServer.git
