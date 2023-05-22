# 更新 Prompt 別名設定

更新以下的 Prompt 別名設定至專案`(Weather)`內的意圖`(AskWeather)`。

- 將詞彙`中央氣象局、氣象局 `替換為`預言家`。
- 將符合 Regex `09[0-9]{8}|\+886[0-9]{9}`替換為`電話號碼`。
- 替換`中華民國身分證號碼`及`姓名 (三字)`。

```python
from requests import post
from pprint import pprint

url = "http://LokiTool_URL/loki/call/" #LokiCall URL
payload = {
	"project": "Weather",	#專案名稱
	"intent": "AskWeather",	#意圖名稱
	"func": "update_alias",
	"data": {
		"alias": {	#Prompt 別名
			"text": {
				"預言家": ["中央氣象局", "氣象局"]
			},
			"regex": {
				"0912345678": ["09[0-9]{8}|\+886[0-9]{9}"]
			},
			"ner": {
				"id": True,
				"person": True,
				"address": False,
				"route": False,
				"url": False
			}
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