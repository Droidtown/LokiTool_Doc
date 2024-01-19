# 更新自定義辭典

更新以下的自定義辭典至專案`(Weather)`內的意圖`(AskWeather)`。

- 中央氣象局、氣象局。
- 大雨、豪雨、大豪雨、超大豪雨。

## 注意！「更新自定義辭典」只有「新增」，而沒有「刪除」。
## 要刪除辭典內容，請參考 [reset_userdefined](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Reset_Userdefined.md) ！

```python
from requests import post
from pprint import pprint

#url = "https://api.droidtown.co/Loki/Call/"  #線上版 URL
url = "http://LokiTool_URL/loki/call/" #LokiCall Docker 版請自訂 URL
payload = {
    #"username" : "", # 這裡填入您在 https://api.droidtown.co 使用的帳號 email。     Docker 版不需要此參數！
    #"loki_key" : "", # 這裡填入您在 https://api.droidtown.co 登入後取得的 loki_key。 Docker 版不需要此參數！
    "project": "Weather", #專案名稱
    "func": "update_userdefined",
    "data": {
        "user_defined": { #自定義辭典
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
