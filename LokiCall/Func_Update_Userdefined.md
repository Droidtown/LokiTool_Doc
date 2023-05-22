# 更新自定義辭典

更新以下的自定義辭典至專案`(Weather)`內的意圖`(AskWeather)`。

1. 中央氣象局、氣象局。
2. 大雨、豪雨、大豪雨、超大豪雨。

```python
from requests import post
from pprint import pprint

url = "http://LokiTool_URL/loki/call/" #LokiCall URL
payload = {
	"project": "Weather",	#專案名稱
	"intent": "AskWeather",	#意圖名稱
	"func": "update_userdefined",
	"data": {
		"user_defined": {	#自定義辭典
			"中央氣象局": ["氣象局"],
			"大雨": ["豪雨", "大豪雨", "超大豪雨"]
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