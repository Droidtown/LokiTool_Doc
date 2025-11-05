# 新增大量的 Assitant 內容
> 適用於 `意圖/句型分析` 模型

在專案`(Weather)`內意圖`(AskWeather)`新增大量的 Assistant 內容。

## 線上 API

```python
from requests import post
from pprint import pprint

url = "https://api.droidtown.co/Loki/Call/"  #線上版 URL
#url = "https://nlu.droidtown.co/Loki_EN/Call/"  #英文版線上 URL
#詳細操作請參考線上版文件：https://api.droidtown.co/document/#Loki_12

payload = {
    "username" : "", # 這裡填入您在 https://api.droidtown.co 使用的帳號 email。     Docker 版不需要此參數！
    "loki_key" : "", # 這裡填入您在 https://api.droidtown.co 登入後取得的 loki_key。 Docker 版不需要此參數！
    "project": "Weather", #專案名稱
    "intent": "AskWeather", #意圖名稱
    "func": "insert_assistant",
    "data": {
        "assistant": [ #Assistant 內容
            {"title": "大雨",
             "content": {
                "NAME": "大雨",
                "DESC": "24 小時累積雨量達 80 毫米以上，或時雨量達 40 毫米以上之降雨現象。"}},
            {"title": "豪雨", 
             "content": {
                "NAME": "豪雨",
                "DESC": "24 小時累積雨量達 200 毫米以上，或 3 小時累積雨量達 100 毫米以上之降雨現象。"}},
            {"title": "大豪雨", 
             "content": {
                "NAME": "大豪雨",
                "DESC": "24 小時累積雨量達 350 毫米以上，或 3 小時累積雨量達 200 毫米以上之降雨現象。"}},
            {"title": "超大豪雨", 
             "content": {
                "NAME": "超大豪雨",
                "DESC": "24 小時累積雨量達 500 毫米以上之降雨現象。"}}
        ]
    }
}

response = post(url, json=payload).json()
pprint(response)
```

## Docker

```python
from requests import post
from pprint import pprint

url = "http://LokiTool_URL/loki/call/" #LokiCall Docker 版請自訂 URL
                                       #步驟 01: 確認 lokitool 啟動
                                       #步驟 02: 取得 lokitool 的 URL
                                       #步驟 03: 將 lokitool 的 URL 取代這一行裡的 LokiTool_URL
                                       #詳細操作請參考 Docker 版文件： https://api.droidtown.co/ArticutDocker/document/#LokiTool 
payload = {
    "project": "Weather", #專案名稱
    "intent": "AskWeather", #意圖名稱
    "func": "insert_assistant",
    "data": {
        "assistant": [ #Assistant 內容
            {"title": "大雨",
             "content": {
                "NAME": "大雨",
                "DESC": "24 小時累積雨量達 80 毫米以上，或時雨量達 40 毫米以上之降雨現象。"}},
            {"title": "豪雨", 
             "content": {
                "NAME": "豪雨",
                "DESC": "24 小時累積雨量達 200 毫米以上，或 3 小時累積雨量達 100 毫米以上之降雨現象。"}},
            {"title": "大豪雨", 
             "content": {
                "NAME": "大豪雨",
                "DESC": "24 小時累積雨量達 350 毫米以上，或 3 小時累積雨量達 200 毫米以上之降雨現象。"}},
            {"title": "超大豪雨", 
             "content": {
                "NAME": "超大豪雨",
                "DESC": "24 小時累積雨量達 500 毫米以上之降雨現象。"}}
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
    "msg": "Success!"
}
```
