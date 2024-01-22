# 更新 ChatGPT Prompt 設定

更新以下的 ChatGPT Prompt 設定至專案`(Weather)`內的意圖`(AskWeather)`。

- 若有設定 Assistast ，則依照內容自行設定 Assistant 欄位。
- User 設定為`請依上文擬定5句回覆「{{UTTERANCE}}」的句子`。

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
    "func": "update_prompt",
    "data": {
        "prompt": { #ChatGPT Prompt
            "assistant": "{{NAME}}的定義為{{DATA}}",
            "user": "請依上文擬定5句回覆「{{UTTERANCE}}」的句子。"
        }
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
