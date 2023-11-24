# 清空專案內所有自定義辭典

清除專案`(Weather)`內的所有自定義辭典內容。

```python
from requests import post
from pprint import pprint

#url = "https://api.droidtown.co/Loki/Call/"  #線上版 URL
url = "http://LokiTool_URL/loki/call/" #LokiCall Docker 版請自訂 URL
payload = {
    #"username" : "", # 這裡填入您在 https://api.droidtown.co 使用的帳號 email。     Docker 版不需要此參數！
    #"loki_key" : "", # 這裡填入您在 https://api.droidtown.co 登入後取得的 loki_key。 Docker 版不需要此參數！
    "project": "Weather", #專案名稱
    "intent": "AskWeather", #意圖名稱，該專案內任意意圖皆可
    "func": "reset_userdefined",
    "data": {}
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
