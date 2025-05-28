# 比對句型是否存在
> 適用於 `意圖/句型分析` 模型

在專案`(Weather)`內意圖`(AskWeather)`比對是否已存在相同的句型。

```python
from requests import post
from pprint import pprint

#url = "https://api.droidtown.co/Loki/Call/"  #線上版 URL
#url = "https://nlu.droidtown.co/Loki_EN/Call/"  #英文版線上 URL
url = "http://LokiTool_URL/loki/call/" #LokiCall Docker 版請自訂 URL
payload = {
    #"username" : "", # 這裡填入您在 https://api.droidtown.co 使用的帳號 email。     Docker 版不需要此參數！
    #"loki_key" : "", # 這裡填入您在 https://api.droidtown.co 登入後取得的 loki_key。 Docker 版不需要此參數！
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
