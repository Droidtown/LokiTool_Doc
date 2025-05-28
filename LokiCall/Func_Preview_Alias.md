# 預覽套用 Prompt 別名效果
> 適用於 `意圖/句型分析` 模型

預覽套用專案`(Weather)`內意圖`(AskWeather)`的 Prompt 別名結果。

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
    "func": "preview_alias",
    "data": {
        "messages": [ #ChatGPT prompt
            {"role": "assistant", "content": "中央氣象局丁小雨：「今天下午梅雨季鋒面報到，氣象局發出超大豪雨特報。」"},
            {"role": "user", "content": "你是一個傲嬌的天氣助理，依上文，請問氣象局助理今天下午會不會下雨？"}
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
    	{"role": "assistant", "content": "預言家梅友仁：「今天下午梅雨季鋒面報到，預言家發出超大豪雨特報。」"},
    	{"role": "user", "content": "你是一個傲嬌的天氣助理，依上文，請問預言家助理今天下午會不會下雨？"}
    ]
}
```
