# Социальная сеть Yatube по API
## Описание
###### Этот проект позволяет использовать функционал приложения не посещая сайт, и на основе api-запросов. В этом проекте можно писать посты, комментировать их и подписываться/отписываться от авторов.

### Используется:

[![Python](https://img.shields.io/badge/-Python_3.7.9-464646??style=flat-square&logo=Python)](https://www.python.org/downloads/)
[![Django](https://img.shields.io/badge/-Django-464646??style=flat-square&logo=Django)](https://www.djangoproject.com/)
[![Django](https://img.shields.io/badge/-Django_rest_framework_3.12.4-464646??style=flat-square&logo=Django)](https://www.django-rest-framework.org)
[![Django](https://img.shields.io/badge/-djoser_2.1.0-464646??style=flat-square&logo=Django)](https://djoser.readthedocs.io/en/latest/getting_started.html#installation)

## Установка
_на Mac или Linux используем Bash_
_Для Windows PowerShell_

##### Клонируем репозиторий на локальную машину:
###### https://github.com/PythonGun/api_final_yatube
###### git clone git@github.com:PythonGun/api_final_yatube.git

#### Создаем и активируем виртуальное окружение:
_на Mac или Linux_
##### python3 -m venv venv
##### source venv/bin/activate 

_для Windows_
##### python -m venv venv
##### source venv/Scripts/activate

#### Устанавливаем зависимости:
###### pip install -r requirements.txt

#### Запускаем миграции:
###### python manage.py migrate

#### Запускаем проект:
###### python manage.py runserver

# Примеры
## Cоздаём пользователя
_post .../api/v1/users/_
```
{
    "username": "newadmin",
    "password": "admin12345
}
```

Пример ответа:
```
{
    "email": "",
    "username": "newadmin",
    "id": 2
}
```

## Получение токена
_post .../api/v1/jwt/create/_
```
{
    "username": "newadmin",
    "password": "admin12345
}
```

Пример ответа:
```
{
    "refresh": "eyJ0eXAiOiJ...",
    "access": "eyJ0eXAiOiJK..."
}
```

#### Проект буден доступен по адресу http://127.0.0.1:8000/
## api/v1/posts/:
_POST .../api/v1/posts/_ - создание публикации

```
{
    "text": "new text"
}

```

Пример ответа:
```
{
    "id": 1,
    "author": "newadmin",
    "text": "new text",
    "pub_date": "2022-04-29T07:09:58.007266Z",
    "image": null,
    "group": null
}
```

_PUT /api/v1/posts/{id}/_ - обновление публикации

```
{
    "text": "new text/ add new text"
}
```

Пример ответа:
```
{
    "id": 1,
    "author": "newadmin",
    "text": "new text/ add new text",
    "pub_date": "2022-04-29T07:09:58.007266Z",
    "image": null,
    "group": null
}
```

###### PATCH /api/v1/posts/{id}/ - частичное обновление публикации
###### DELETE /api/v1/posts/{id}/ - удаление публикации
######

_GET api/v1/posts/_ - получить список всех публикаций.
```python

Пример ответа:
```python
[
    {
        "id": 1,
        "author": "newadmin",
        "text": "new text/ add new text",
        "pub_date": "2022-04-29T07:09:58.007266Z",
        "image": null,
        "group": null
    }
]
```

###### GET api/v1/posts/{id}/ - получение публикации по id

## api/v1/groups/:
###### GET api/v1/groups/ - получение списка доступных сообществ
###### GET api/v1/groups/{id}/ - получение информации о сообществе по id


## api/v1/posts/{post_id}/comments/:
###### GET api/v1/{post_id}/comments/ - получение всех комментариев к публикации
###### GET api/v1/{post_id}/comments/{id}/ - Получение комментария к публикации по id

##  Получение доступа к эндпоинту /api/v1/follow/ (подписки) доступен только для авторизованных пользователей:
###### GET /api/v1/follow/ - подписка пользователя от имени которого сделан запрос на пользователя переданного в теле запроса.

#### Ознакомиться с полным функционалом и примерами можно по адресу http://127.0.0.1:8000/redoc (доступен после запуска проекта)

## Автор
Денис Баринов
