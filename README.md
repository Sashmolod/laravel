# Laravel Project with Docker

## Описание

Этот проект представляет собой приложение Laravel, развернутое с использованием Docker. Включает конфигурацию для Nginx, PHP, MySQL и Composer.

## Содержание

- [Установка](#установка)
- [Запуск проекта](#запуск-проекта)
- [Настройка](#настройка)
- [Команды Docker](#команды-docker)
- [Примечания](#примечания)

## Установка

1. **Клонируйте репозиторий:**

   ```bash
   git clone https://github.com/Sashmolod/laravel.git
   cd laravel

Убедитесь, что у вас установлен Docker и Docker Compose.

Инструкции по установке Docker можно найти [здесь](https://docs.docker.com/get-docker/) и [здесь](https://docs.docker.com/compose/install/).

## Запуск проекта

1. **Запустите контейнеры:**

   ```bash
   docker-compose up -d
   
Откройте браузер и перейдите по адресу: [http://localhost:8000](http://localhost:8000)

## Настройка

1. **Настройте файл `.env`:**

   - Перейдите в контейнер PHP:

     ```bash
     docker-compose exec php bash
     ```

   - Скопируйте пример файла `.env`, если он еще не был создан:

     ```bash
     cp .env.example .env
     ```

   - Отредактируйте файл `.env`, чтобы настроить подключение к базе данных:

     ```env
     DB_CONNECTION=mysql
     DB_HOST=mysql
     DB_PORT=3306
     DB_DATABASE=laravel
     DB_USERNAME=root
     DB_PASSWORD=root_password
     ```

   - Затем вернитесь к основному каталогу и выполните миграции:

     ```bash
     docker-compose run --rm artisan migrate
     ```






   
## Примечания

- Если вы сталкиваетесь с проблемами, убедитесь, что все пути в `docker-compose.yml` и Dockerfile настроены правильно.
- Не забудьте добавить чувствительные данные, такие как пароли и ключи, в `.env` и исключить их из репозитория.
- Файлы и директории, такие как `.idea`, должны быть добавлены в `.gitignore`, чтобы не попадать в репозиторий.

