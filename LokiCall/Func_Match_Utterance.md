# 比對句型是否存在

在專案`(Weather)`內意圖`(AskWeather)`比對是否已存在相同的句型。

```python
from requests import post
from pprint import pprint

url = "http://LokiTool_URL/loki/call/" #LokiCall URL
payload = {
    "project": "Weather", #專案名稱
    "intent": "AskWeather", #意圖名稱
    "func": "match_utterance",
    "data": {
        "utterance": [ #比對的句子
            "今天天氣如何？",
            "下午會不會下雨？"
        ]
    }
}

response = post(url, json=payload).json()
pprint(response)
```

輸出結果如下

```json
{
    "status": true,
    "msg": "Success!",
    "result_list": [
    	{"status": true, "msg": "Pattern same as [今天][天氣]如何？."},
    	{"status": true, "msg": "Pattern same as [下午]會不[會]下雨？."}
    ]
}
```