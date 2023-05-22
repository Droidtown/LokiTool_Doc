# 新增大量句子

在專案`(Weather)`內意圖`(AskWeather)`新增大量的句子，並自動勾選詞性為`ENTITY_noun`的參數。

```python
from requests import post
from pprint import pprint

url = "http://LokiTool_URL/loki/call/" #LokiCall URL
payload = {
    "project": "Weather", #專案名稱
    "intent": "AskWeather", #意圖名稱
    "func": "insert_utterance",
    "data": {
        "utterance": [ #新增的句子
            "今天天氣如何？",
            "下午會不會下雨？"
        ],
        "checked_list": [ #勾選的詞性
            "ENTITY_noun"
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
    	{"status": true, "msg": "Success!"},
    	{"status": true, "msg": "Success!"}
    ]
}
```