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
> This API endpoint allows you to get a list of patrons | Этот эндпоинт позволяет вам получить список патронов (если таковые существуют)
- Example request | Пример запроса:
```py
# Python
import requests
print(requests.get('https://artilities.herokuapp.com/api/other/patrons').json())
```
- Example response | Пример ответа:
```py
{
    "status_code": 200,
    "details": [
        {
            "tier": 2,
            "custom_message": {
                "message": "Hello world!",
                "approved": true
            },
            "custom_icon": {
                "url": "https://i.ibb.co/8P09wHK/image.png"
            },
            "nickname": "lukeFTW"
        }
    ],
    "execution_time": 27
}
```

### `GET /api/other/banners`
> This API endpoint allows you to get a random banner | Этот эндпоинт позволяет вам получить рандомный баннер 
- Example request | Пример запроса:
```py
# Python
import requests
print(requests.get('https://artilities.herokuapp.com/api/other/banners').json())
```
- Example response | Пример ответа:
```py
{
    "status_code": 200,
    "details": {
        "banner_url": "https://discord.com/invite/u7dBmKyMWa",
        "banner_image": "https://cdn.kapwing.com/final_61f939fdb4e9fb0099ce1da3_270030.gif",
        "language": ""
    },
    "execution_time": 59
}
```
