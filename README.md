# myapp

Учебный проект ПР №2: базовая структура Go-проекта (cmd / internal / utils).

## Запуск
```
go run ./cmd/myapp
```

## Сборка
```
go build -o bin/myapp ./cmd/myapp
./bin/myapp
```

## Эндпоинты
- `GET /`     — текст
- `GET /ping` — JSON `{"status":"ok","time":"<RFC3339>"}`
- `GET /fail` — пример ошибки, 400 `{"error":"bad_request_example"}`

Каждый ответ содержит заголовок `X-Request-Id`; все запросы логируются в консоль.

## Структура
```
myapp/
├─ cmd/myapp/main.go              — точка входа
├─ internal/app/app.go            — сборка роутера, middleware, запуск
├─ internal/app/handlers/ping.go  — хендлер /ping
├─ utils/logger.go                — логгер, генератор request-id
├─ utils/httpjson.go              — JSON-ответы и ошибки
├─ go.mod
└─ README.md
```