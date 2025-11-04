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
Клиент (Frontend / Postman / Swagger)
│
├──→ NewsSecurityServer (Auth)
│       └── JWT Token
│
└──→ NewsLogicServer (Business Logic)
└── Все операции с новостями и комментариями

# WorldOfNews
1) Сервер содержит основное задание. Весь код находиться в ветке  develop. 
https://github.com/MrFurion/NewsLogicServer

2) Сервер содержит логику 21 пункта задания(аутентификация и авторизация ).
https://github.com/MrFurion/NewsSecurityServer

