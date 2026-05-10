# Kittygram

![Main Kittygram workflow](https://github.com/MaximKhmelevskoy/kittygram_final/actions/workflows/main.yml/badge.svg)

## Описание проекта

Kittygram — это веб-приложение для публикации фотографий котиков.

Пользователи могут:
- регистрироваться и авторизовываться;
- добавлять котиков;
- загружать изображения;
- просматривать список котиков;
- редактировать и удалять свои публикации.

Проект разворачивается в Docker-контейнерах и автоматически деплоится на сервер через GitHub Actions.

---

## Технологии

### Backend
- Python 3.11
- Django
- Django REST Framework
- Gunicorn
- PostgreSQL

### Frontend
- React
- JavaScript

### DevOps
- Docker
- Docker Compose
- Nginx
- GitHub Actions
- Docker Hub

---

## Ссылки на проект

### Kittygram
https://kittygram-maksi.duckdns.org

### Taski
https://taski-maksi.duckdns.org

---

## Как развернуть проект

### 1. Клонировать репозиторий

```bash
git clone git@github.com:maxpadget/kittygram_final.git
cd kittygram_final
```

### 2. Создать файл .env (пример)

```
POSTGRES_DB=kittygram
POSTGRES_USER=kittygram_user
POSTGRES_PASSWORD=kittygram_password
DB_HOST=db
DB_PORT=5432

SECRET_KEY=django-insecure-very-long-random-string-change-me

DEBUG=False

ALLOWED_HOSTS=127.0.0.1,localhost,kittygram-maksi.duckdns.org
```

### 3. Запустить контейнеры

```bash
docker compose -f docker-compose.production.yml up -d
```

### 4. Выполнить миграции

```bash
docker compose -f docker-compose.production.yml exec backend python manage.py migrate
```

### 5. Собрать статику

```bash
docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic --no-input
```

### 6. Открыть проект

Kittygram: <https://kittygram-maksi.duckdns.org>

---

### Над проектом работал:
[Максим Хмелевской](https://github.com/MaximKhmelevskoy)
