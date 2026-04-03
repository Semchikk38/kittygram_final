# Kittygram

[![Main workflow](https://github.com/Semchikk38/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/Semchikk38/kittygram_final/actions/workflows/main.yml)

## Описание проекта

Kittygram — это веб-приложение для публикации фотографий котов. Пользователи могут загружать изображения, указывать год рождения и цвет кота, а также добавлять достижения. Проект состоит из бэкенда на Django Rest Framework, фронтенда на React и шлюза на Nginx.

## Стек технологий

- **Backend:** Django, Django REST Framework, djoser, Gunicorn, PostgreSQL
- **Frontend:** React, Node.js
- **Infrastructure:** Docker, Docker Compose, Nginx, GitHub Actions
- **Deployment:** Yandex Cloud (Ubuntu), Docker Hub

## Как развернуть проект

### Требования

- Сервер с Ubuntu 22.04
- Установленный Docker и Docker Compose
- Доменное имя (или поддомен)

### Шаги для развертывания

1. **Клонируйте репозиторий:**
   ```bash
   git clone https://github.com/Semchikk38/kittygram_final.git
   cd kittygram_final

2. **Создайте файл .env в корне проекта:**

    POSTGRES_DB=kittygram
    POSTGRES_USER=kittygram_user
    POSTGRES_PASSWORD=your_password
    DB_HOST=db
    DB_PORT=5432

    SECRET_KEY=your_secret_key
    DEBUG=False
    ALLOWED_HOSTS=your_domain.com

3. **Запустите проект локально:**

    ```bash
    docker compose up -d
4. **Для продакшена используйте:**

    ```bash
    docker compose -f docker-compose.production.yml up -d

#### Настройка CI/CD

Проект настроен на автоматический деплой через GitHub Actions при пуше в ветку main. Для работы необходимо добавить в GitHub Secrets:

- DOCKER_USERNAME, DOCKER_PASSWORD
- HOST, USER, SSH_KEY, SSH_PASSPHRASE
- TELEGRAM_TO, TELEGRAM_TOKEN

##### Как заполнить .env
**Переменная**	        **Описание**
POSTGRES_DB	            Имя базы данных
POSTGRES_USER	        Пользователь PostgreSQL
POSTGRES_PASSWORD   	Пароль PostgreSQL
DB_HOST	                Хост БД (обычно db)
DB_PORT	                Порт БД (обычно 5432)
SECRET_KEY	            Секретный ключ Django
DEBUG	                Режим отладки (False для продакшена)
ALLOWED_HOSTS	        Домены через запятую

**Автор**
Semchikk38

**Коллабораторы**
EugeneSal — ревьюер