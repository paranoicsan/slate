# User

## Avatar

Для выполнения запросов в закрытой области необходимо передавать адрес электронной почты пользователя как простой GET параметр и token «обёрнутый» в заголовок запроса.


```shell
curl -H 'Authorization: Token token="foobar"' 'https://smartgeo.kz/api/v1/user/avatar?email=admin@test.com' 
```

> В ответ возвращается потоковое изображение или же 404, если аватар для пользователя отсутствует.

Для получения пользовательского аватара необходимо отправить авторизованный запрос на endpoint:

`GET https://smartgeo.kz/api/v1/user/avatar`

### Параметры

Параметр | Обязательное | Описание
-------- | ------------ | --------
email | да | адрес электронной почты

## Info

```shell
curl -X GET -H 'Authorization: Token token="foobar"' 'https://smartgeo.kz/api/v1/user/avatar?email=admin@test.com' 
```

> Возвращаемые данные:

```json
{
  "birth_date": "1995-02-23T06:00:00+06:00",
  "city": "Boydstad",
  "email": "admin@test.com",
  "id": 1,
  "is_male": false,
  "last_name": "Stracke",
  "name": "Birdie2"
}
```

Для получения информации о пользователе необходимо отправить авторизованный GET запрос на endpoint

`GET https://smartgeo.kz/api/v1/user/`

### Параметры

Параметр | Обязательное | Описание
-------- | ------------ | --------
email | да | адрес электронной почты

## Update user info

```shell
curl -X PUT -H 'Authorization: Token token="foobar"' -d param1=val1 -d param2=val2 'https://smartgeo.kz/api/v1/user/avatar?email=admin@test.com'
```

> Тело ответа пустое, статус 200 - изменение успешно. 


Для изменения пользовательской информации необходимо отправить авторизованный запрос на endpoint

`PUT https://smartgeo.kz/api/v1/user/`

### Параметры

Параметр | Значение | Описание
-------- | -------- | --------
user[birth_date] | 1995-02-23T06:00:00+06:00 | дата рождения
user[city] | Москва | город
user[is_male] | 1 | пол мужской
user[lastname] | Иванов | фамилия
user[name] | Иван | имя
user[avatar][data] | iufysiudfysiduyfiusdf | изображение, кодированное в Base64
user[avatar][content_type] | image/png | тип изображения 
user[avatar][file_name] | avatar.png | оригинальное имя файла

