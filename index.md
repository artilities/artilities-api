## Artilities REST API Documentation
## Interactions:
### Generator:
#### `GET /api/ideas`
> Get random idea from the database
- Example request:
```py
# Python
import requests
requests.get('https://artilities.herokuapp.com/api/ideas').json()
```
- Example response:
```
{
  "status_code":200,
  "generated_idea": {
    "ru":"7 гномов и один кот",
    "eng":"7 gnomes and one cat"
  },
  "execution_time":142
}
```

#### `GET /api/challenges`
> Get random challenge from the database
- Example request:
```py
# Python
import requests
requests.get('https://artilities.herokuapp.com/api/challenges').json()
```
- Example response:
```
{
  "status_code":200,
  "generated_challenge": {
    "eng":"draw using anything but your hands",
    "ru":"Рисуй чем угодно, только не руками"
  },
  "execution_time":26
}
```

### Dictionary
#### `GET /api/dict?query=&lang=`
> Bulk load of the whole dictionary. For specific query specify parameters `query` (search query) and `lang` (`ru`/`eng`). If `lang` parameter is empty, search by `eng` is performed
- Example request:
```py
# Python
import requests
requests.get('https://artilities.herokuapp.com/api/dict?query=oc').json()
```
- Example response:
```
{
    "status_code": 200,
    "query_results": [
        [
            "OC",
            "original character; most often invented by you personally."
        ],
        [
            "Monochrome",
            "(Greek \"mono\" - one and \"chroma\" - color) monochromatic (but not necessarily black and white) work"
        ],
        [
            "Boaf OC",
            "original character based on a friend"
        ]
    ],
    "execution_time": 47
}
```

### Other:
#### `GET /api/other/banners`
> Get a random banner
- Example request:
```py
# Python
import requests
requests.get('https://artilities.herokuapp.com/api/other/banners').json()
```
- Example response:
```
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

#### `GET /api/other/patrons`
> Get list of Patreon supporters
- Example request:
```py
# Python
import requests
requests.get('https://artilities.herokuapp.com/api/other/patrons').json()
```
- Example response:
```
{
  "status_code":200,
  "details": [
    {
      "tier":2,
      "custom_message":{"message":"Hello world!","approved":true},
      "custom_icon: {"url":"https://i.ibb.co/8P09wHK/image.png"},
      "nickname":"lukeFTW"
    }
  ],
  "execution_time":26
}
```
