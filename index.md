## Artilities REST API Documentation

### [⚠️] Some of our endpoints are secured with a "devkey" AKA an API key.
> If you are a developer and you want to get a devkey for accessing certain endpoints, you should join our [Discord server](https://discord.com/invite/u7dBmKyMWa) and contact moderators via tickets by clicking on `get api key` button in **#ticket-menu** channel.

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
#### `GET /api/dict` + `?query=&lang=` (optional parameters) (query: String, lang: String)
> Bulk load of the whole dictionary without parameters. For specific query specify parameters `query` (search query) and `lang` (ru/eng). If `lang` parameter is empty, search by `eng` is performed
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

### Users' interactions:
#### `GET /api/user/getinfo` + `?devkey=&userid=&searched_userid=` (devkey: String, userid: String, searched_userid: String)
> Get saved ideas, challenges and palettes of user with **searched_userid**. This endpoint requires authentication by **devkey** (API key) parameter which is related to your Discord account with **userid**.
- Example request:
```py
# Python
import requests
payload = {
  'devkey': '123abc', 
  'userid': '468470176887734288',
  'searched_userid': '468470176887734288'
}
requests.get('https://artilities.herokuapp.com/api/user/getinfo', params=payload).json()
```

- Example response:
```
{
    "status_code": 200,
    "data": {
        "ideas": [
            "Lunar Landscape",
            "Humanization of a musical instrument"
        ],
        "challenges": [
            "draw with two hands at once",
            "draw with your foot"
        ],
        "colors": [
            [
                "#1c4a64",
                "#c899cc",
                "#0ab3ad",
                "#1a52a1"
            ]
        ]
    },
    "execution_time": 51
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
