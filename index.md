## Artilities REST API Documentation | Документация к REST API Артилит
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
