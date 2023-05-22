# 更新 ChatGPT Prompt 設定

更新以下的 ChatGPT Prompt 設定至專案`(Weather)`內的意圖`(AskWeather)`。

- Assistast 設定為 `請閱讀「{{CONTENT}}」`。
- User 設定為`請依上文擬定5句回覆「{{UTTERANCE}}」的句子`。

```python
from requests import post
from pprint import pprint

url = "http://LokiTool_URL/loki/call/" #LokiCall URL
payload = {
    "project": "Weather", #專案名稱
    "intent": "AskWeather", #意圖名稱
    "func": "update_prompt",
    "data": {
        "prompt": { #ChatGPT Prompt
            "assistant": "{{NAME}}的定義為{{DATA}}",
            "user": "請依上文擬定5句回覆「{{UTTERANCE}}」的句子。"}
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