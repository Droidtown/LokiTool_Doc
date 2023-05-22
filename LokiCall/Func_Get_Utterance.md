# 取得意圖句子

獲取專案`(Weather)`內意圖`(AskWeather)`的所有句子。

```python
from requests import post
from pprint import pprint

url = "http://LokiTool_URL/loki/call/" #LokiCall URL
payload = {
	"project": "Weather", #專案名稱
	"intent": "AskWeather", #意圖名稱
	"func": "get_utterance",
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
    "result_list": [
    	"下午會不會下雨？",
    	"今天天氣如何？"
    ]
}
```