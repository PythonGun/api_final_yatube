# Социальная сеть Yatube по API
## Описание
###### Этот проект позволяет использовать функционал приложения не посещая сайт, и на основе api-запросов можно создавать смарт-приложения для всех мобильных платформ. В этом проекте можно писать посты, объединять их в группы, комментировать их и подписываться на авторов.
## Установка
##### Клонируем репозиторий на локальную машину:
###### https://github.com/PythonGun/api_final_yatube
###### git clone git@github.com:PythonGun/api_final_yatube.git
##### Создаем и активируем виртуальное окружение:
###### python -m venv venv
###### source venv/Scripts/activate
##### Устанавливаем зависимости:
###### pip install -r requirements.txt
###### Запускаем миграции:
###### python manage.py migrate
##### Запускаем проект:
###### python manage.py runserver
## Примеры
#### Проект буден доступен по адресу http://127.0.0.1:8000/

##### api/v1/posts/:
###### POST /api/v1/posts/ - создание публикации
###### PUT /api/v1/posts/{id}/ - обновление публикации
###### PATCH /api/v1/posts/{id}/ - частичное обновление публикации
###### DEL /api/v1/posts/{id}/ - удаление публикации
######
###### GET api/v1/posts/ - получить список всех публикаций.
###### GET api/v1/posts/{id}/ - получение публикации по id

##### api/v1/groups/:
###### GET api/v1/groups/ - получение списка доступных сообществ
###### GET api/v1/groups/{id}/ - получение информации о сообществе по id


##### api/v1/posts/{post_id}/comments/:
###### GET api/v1/{post_id}/comments/ - получение всех комментариев к публикации
###### GET api/v1/{post_id}/comments/{id}/ - Получение комментария к публикации по id

#####  Получение доступа к эндпоинту /api/v1/follow/ (подписки) доступен только для авторизованных пользователей:
###### GET /api/v1/follow/ - подписка пользователя от имени которого сделан запрос на пользователя переданного в теле запроса.

#### Ознакомиться с полным функционалом и примерами можно по адресу http://127.0.0.1:8000/redoc (доступен после запуска проекта)

