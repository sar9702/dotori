# RestAPI - Item

## Get
| URI | Description | Attributes | Curl Example |
| --- | --- | --- | --- |
| /api/item | 아이템 가지고 오기 | id | `$ curl "http://192.168.219.104/api/item?id=5e24742f901da0498519f7a7"` |


## Post
| URI | Description | Attributes | Curl Example |
| --- | --- | --- | --- |
| /api/search | 검색하기 | searchword | `$ curl -X POST -d "searchword=나무" http://192.168.219.104/api/search` |
| /api/usingrate | Using Rate 올리기 | id | `$ curl -X POST -d "id=5eaa5758eafdfd2dae3bb050" http://192.168.219.104/api/usingrate`

## Delete
| URI | Description | Attributes | Curl Example |
| --- | --- | --- | --- |
| /api/item | 삭제하기 | id | `curl -H "Authorization: Basic <Token>" -X DELETE "http://192.168.219.104/api/item?id=5ec37a67e048d951ee46a45a"`

## Python example
### asset 가지고 오기 

```python
#!/usr/bin/python
#coding:utf-8
import urllib2
import json

request = urllib2.Request("http://192.168.219.104/api/item?id=5e24742f901da0498519f7a7")
result = urllib2.urlopen(request)
data = json.load(result)
print(data)
```

### 검색하기
```python
#!/usr/bin/python
#coding:utf-8
import urllib2
import urllib
import json

data = urllib.urlencode({"searchword":"나무"}) # 쿼리스트링 파라미터를 Encoding
request = urllib2.Request("http://192.168.0.9/api/search",data) 
result = urllib2.urlopen(request)
data = json.load(result)
print(data)
```