# 取得專案句子
> 適用於 `意圖/句型分析` 模型

獲取專案`(Weather)`內所有意圖中的句子。

```python
from requests import post
from pprint import pprint

#url = "https://api.droidtown.co/Loki/Call/"  #線上版 URL
#url = "https://nlu.droidtown.co/Loki/Call/"  #英文版線上 URL
url = "http://LokiTool_URL/loki/call/" #LokiCall Docker 版請自訂 URL
payload = {
    #"username" : "", # 這裡填入您在 https://api.droidtown.co 使用的帳號 email。     Docker 版不需要此參數！
    #"loki_key": "", # 這裡填入您在 https://api.droidtown.co 登入後取得的 loki_key。     Docker 版不需要此參數！
    "project": "Weather", # 這裡填入您想要查詢的 project name。     線上版不需要此參數！
    "func": "get_info",
    "data": {}
}

response = post(url, json=payload).json()
pprint(response)
```

輸出結果如下

```json
{
    "status": true,
    "msg": "Success!",
    "result": {
        "project_name": "AskWeather",
        "intent": {
            "Weather": [
                "下午會不會下雨？",
                "今天天氣如何？"
            ]
        },
        "total_intent_count": 1,
        "total_utterance_count": 2
    }
}
```