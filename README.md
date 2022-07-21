# Проект YaMDb

yamdb_final

Проект YaMDb собирает отзывы пользователей на произведения. Произведения делятся на категории: "Книги", "Фильмы", "Музыка". Список категорий может быть расширен.
Сами произведения в YaMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.
В каждой категории есть произведения. Например, в категории "Книги" могут быть произведения "Маленький принц" и "Иуда Искариот", а в категории "Музыка" — песня "Беспечный ездок" группы "Секрет" и Симфония № 40 В.А.Моцарта. Произведению может быть присвоен жанр из списка предустановленных (например, "Сказка", "Рок" или "Артхаус"). Новые жанры может создавать только администратор.
Пользователи оставляют к произведениям текстовые отзывы и ставят произведению оценку в диапазоне от 1 до 10; из пользовательских оценок формируется усреднённая оценка произведения — рейтинг.

## Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone git@github.com:RusanovaAnna/yamdb_final.git
```

```
cd yamdb_final
```

### Шаблон env-файла
Данные БД Postgres: 

D_SECRET_KEY - секретный ключ django

DB_ENGINE - движок postgres

DB_NAME - имя БД

POSTGRES_USER - пользователь БД

POSTGRES_PASSWORD - пароль БД

DB_HOST - название сервиса (контейнера)

DB_PORT - порт для подключения к БД 


### Запуск контейнеров:

```
cd infra
```

#### 1. Развернуть проект:
```
docker-compose up -d
```

#### 2. Сделать миграции:
```
docker-compose exec web python manage.py migrate
```

#### 3. Создать суперпользователя:
```
docker-compose exec web python manage.py createsuperuser
```

#### 4. Собрать статику:
```
docker-compose exec web python manage.py collectstatic --no-input
```


#### Примеры запросов для получения, создания и изменения отзывов и комментариев, а также для управления пользователями

###### */api/v1/titles/*
###### */api/v1/titles/{id}/*
###### *api/v1/titles/{title_id}/reviews/*
###### *api/v1/titles/{title_id}/reviews/{id}/*
###### *api/v1/genres/*
###### *api/v1/genres/{id}/*
###### *api/v1/users/*

Стек: Python, DRF, REST API, jwt-token

## Данные разработчиков:

- Николаев Максим [GitHub профиль](https://github.com/Maxmile-sprint)
- Русанова Анна [GitHub профиль](https://github.com/RusanovaAnna)

![example workflow](https://github.com/RusanovaAnna/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)
