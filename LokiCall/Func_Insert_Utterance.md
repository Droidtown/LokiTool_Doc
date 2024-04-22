# 新增大量句子
> 適用於 `意圖/句型分析` 模型

在專案`(Weather)`內意圖`(AskWeather)`新增大量的句子，並自動勾選詞性為`ENTITY_noun`的參數。

```python
from requests import post
from pprint import pprint

#url = "https://api.droidtown.co/Loki/Call/"  #線上版 URL
#url = "https://nlu.droidtown.co/Loki/Call/"  #英文版線上 URL
url = "http://LokiTool_URL/loki/call/" #LokiCall Docker 版請自訂 URL
payload = {
    #"username" : "", # 這裡填入您在 https://api.droidtown.co 使用的帳號 email。     Docker 版不需要此參數！
    #"loki_key" : "", # 這裡填入您在 https://api.droidtown.co 登入後取得的 loki_key。 Docker 版不需要此參數！
    "project": "Weather", #專案名稱
    "intent": "AskWeather", #意圖名稱
    "func": "insert_utterance",
    "data": {
        "utterance": [ #新增的句子
            "今天天氣如何？",
            "下午會不會下雨？"
        ],
        "checked_list": [ #所有詞性全勾選。你可以把不要勾的項目註解掉。
            "ENTITY_noun", #包含所有名詞
            "UserDefined", 
            "ENTITY_num",
            "DegreeP",
            "MODIFIER_color",
            "LOCATION",
            "KNOWLEDGE_addTW",
            "KNOWLEDGE_routeTW",
            "KNOWLEDGE_lawTW",
            "KNOWLEDGE_url",
            "KNOWLEDGE_place",
            "KNOWLEDGE_wikiData",
            "KNOWLEDGE_currency"
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
