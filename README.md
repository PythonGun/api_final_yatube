# Социальная сеть Yatube по API

### Используется:
[![Python](https://img.shields.io/badge/-Python_3.7.9-464646??style=flat-square&logo=Python)](https://www.python.org/downloads/)
[![Django](https://img.shields.io/badge/-Django-464646??style=flat-square&logo=Django)](https://www.djangoproject.com/)
[![Django](https://img.shields.io/badge/-Django_rest_framework_3.12.4-464646??style=flat-square&logo=Django)](https://www.django-rest-framework.org)
[![Django](https://img.shields.io/badge/-djoser_2.1.0-464646??style=flat-square&logo=Django)](https://djoser.readthedocs.io/en/latest/getting_started.html#installation)

## Описание
###### Этот проект позволяет использовать функционал приложения не посещая сайт, и на основе api-запросов. В этом проекте можно писать посты, комментировать их и подписываться/отписываться от авторов.


# Установка
<details><summary>Установка</summary>

_на Mac или Linux используем Bash_
_Для Windows PowerShell_

# Установка
<details><summary>Установка</summary>
 
_На Mac или Linux используем Bash_
_Для Windows PowerShell_

#### Клонируем репозиторий на локальную машину:
```
https://github.com/PythonGun/api_yamdb
git clone git@github.com:PythonGun/api_yamdb.git
```

#### Создаем и активируем виртуальное окружение:
Для Mac или Linux
```
python3 -m venv venv
source venv/bin/activate
```

Для Windows
```
python -m venv venv
source venv/Scripts/activate
```

#### Устанавливаем зависимости:
```
pip install -r requirements.txt
```

#### Запускаем миграции:
```
python manage.py migrate
```

#### Запускаем проект:
```
python manage.py runserver

#### Проект буден доступен по адресу http://127.0.0.1:8000/
</details>

# Примеры запросов
<details><summary>Примеры запросов</summary>

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

__PATCH /api/v1/posts/{id}/__ - частичное обновление публикации

__DELETE /api/v1/posts/{id}/__ - удаление публикации

__GET api/v1/posts/__ - получить список всех публикаций.

Пример ответа:
```
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

__GET api/v1/posts/{id}/__ - получение публикации по id

## api/v1/groups/:
__GET api/v1/groups/__ - получение списка доступных сообществ
__GET api/v1/groups/{id}/__ - получение информации о сообществе по id


## api/v1/posts/{post_id}/comments/:
__GET api/v1/{post_id}/comments/__ - получение всех комментариев к публикации
__GET api/v1/{post_id}/comments/{id}/__ - Получение комментария к публикации по id

##  Получение доступа к эндпоинту /api/v1/follow/ (подписки) доступен только для авторизованных пользователей:
__GET /api/v1/follow/__ - подписка пользователя от имени которого сделан запрос на пользователя переданного в теле запроса.

</details>

## Авторы
- :white_check_mark: [Баринов Денис](https://github.com/PythonGun)
