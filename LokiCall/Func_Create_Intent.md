# 建立新的意圖

在專案`(Weather)`中建立一個`基本`意圖`(AskWeather)`。

```python
from requests import post
from pprint import pprint

url = "http://LokiTool_URL/loki/call/" #LokiCall URL
payload = {
    "project": "Weather", #專案名稱
    "intent": "AskWeather", #意圖名稱
    "func": "create_intent",
    "data": {
        "type": "basic" #意圖類別
    }
}

response = post(url, json=payload).json()
pprint(response)
```

輸出結果如下

```json
{
    "status": true,
    "msg": "Success!"
}
```