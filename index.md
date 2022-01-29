## Artilities REST API Documentation | Документация к REST API Артилит
## Generator's endpoints | Эндпоинты для генератора
### `GET /api/ideas`
> This API endpoint allows you to get a random idea from the database | Этот эндпоинт позволяет вам получить одну случайно выбранную идею из базы данных
- Example request | Пример запроса:
```py
# Python
import requests
print(requests.get('https://artilities.herokuapp.com/api/ideas').json())
```
- Example response | Пример ответа:
```py
{
  status_code: 200, 
  generated_idea: {
    'ru': 'Большой красивый дракон',
    'eng': 'Big beautiful dragon'
  },
  error_response: None,
  execution_time: 0
}
```

## Other endpoints | Другие эндпоинты
### `GET /api/other/patrons`
> This API endpoint allows you to get a list of patrons and their banners (if they exist) | Этот эндпоинт позволяет вам получить список патронов (если таковые существуют)
- Example request | Пример запроса:
```py
# Python
import requests
print(requests.get('https://artilities.herokuapp.com/api/other/patrons').json())
```
- Example response | Пример ответа:
```py
{
  status_code: 200,
  details: [
    {
      "tier":1,
      "custom_message": {
        "message":"Hello world!",
        "approved":true
      },
      "custom_icon": {
        "url":"www",
        "approved":true
      },
      "banner": {
        "url":"www",
        "approved":true,
        "type": [
          "ru","eng"
        ],
        "expires_at":"12345678"
      },
      "nickname":"John Doe"
    }
  ],
  error_response: None,
  execution_time: 0
}
```
