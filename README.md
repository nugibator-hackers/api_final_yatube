## About 
Учебный проект ЯП по использованию django rest framework 
 
## Install 
<details> 
<summary> 
Scripts 
</summary> 
 
1. Clone the repository: 
```shell 
git clone https://github.com/nugibator-hackers/api_final_yatube.git 
cd api_final_yatube 
``` 
 
2. Устанавливаем виртуальное окружение 
```shell  
python3 -m venv venv 
source venv/Scripts/activate 
``` 
 
3. Установка зависимостей 
```shell 
pip install -r requirements.txt 
``` 
 
4. Подготовка базы данных 
```shell 
python3 yatube_api/manage.py migrate 
``` 
 
5. Запуск сервера 
```shell 
python3 api_yatube/manage.py runserver 
``` 
 
</details> 
 
## Routes 
 
### Create token 
`POST /api/v1/jwt/create/` 
``` 
{ 
  "username": "string", 
  "password": "string" 
} 
``` 
 
### Получение публикаций 
`GET /api/v1/posts/`  
`Authorization: Bearer your_token` 
 
### Получение публикации 
`GET /api/v1/posts/{id}/`  
 
### Создание, обновление(так же частичное) публикации 
`POST(PUT, PUTCH) /api/v1/posts/{id}/` 
`Authorization: Bearer your_token` 
 
``` 
{ 
"text": "string", 
"image": "string", 
"group": 0 
} 
``` 
 
### Удаление публикации  
`DELETE /api/v1/posts/{id}` 
`Authorization: Bearer your_token` 
 
 
### Получение комментариев 
`GET /api/v1/posts/{post_id}/comments/` 
 
### Добавление комментария 
`POST /api/v1/posts/{post_id}/comments/` 
`Authorization: Bearer your_token` 
 
``` 
{ 
"text": "string" 
} 
``` 
 
### Получение комментариея 
`GET /api/v1/posts/{post_id}/comments/{id}/` 
 
### Обновление(так же частичное) комментария 
`PUT, PUTCH /api/v1/posts/{post_id}/comments/{id}/` 
`Authorization: Bearer your_token` 
 
``` 
{ 
"text": "string" 
} 
``` 
 
### Удаление комментария 
`DELETE /api/v1/posts/{post_id}/comments/` 
`Authorization: Bearer your_token` 
 
### Список сообществ 
`GET /api/v1/groups/` 
 
### Информация о сообществе 
`GET /api/v1/groups/{id}/` 
 
### Подписки 
`GET /api/v1/follow/` 
`Authorization: Bearer your_token` 
 
### Подписка 
`POST /api/v1/follow/` 
`Authorization: Bearer your_token` 
 
``` 
{ 
"following": "string" 
} 

