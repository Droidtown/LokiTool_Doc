# 套用 Prompt 別名執行 ChatGPT

套用專案`(Weather)`內意圖`(AskWeather)`的 Prompt 別名並執行 ChatGPT API。

```python
from requests import post
from pprint import pprint

url = "http://LokiTool_URL/loki/call/" #LokiCall URL
payload = {
    "project": "Weather",	#專案名稱
    "intent": "AskWeather",	#意圖名稱
    "func": "run_alias",
    "data": {
        "messages": [	#ChatGPT prompt
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
    "result_list": [{
    	"index": 0,
    	"finish_reason": "stop",
    	"messages": {
            "role": "assistant",
            "content": "噢！你在問我這種問題嗎？當然會下雨啊！因為梅雨季鋒面報到了，而且還有大豪雨特報，這不是很明顯的嗎？我可是很會預測未來的呦！"
    	}
    }]
}
```