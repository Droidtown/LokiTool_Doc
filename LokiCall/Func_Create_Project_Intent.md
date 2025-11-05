# 建立新的專案
> 適用於 `意圖/句型分析`模型

在 Loki 中建立一個新的專案`(Weather)`。

## 線上 API

```python
from requests import post
from pprint import pprint

url = "https://api.droidtown.co/Loki/Call/"  #線上版 URL
#url = "https://nlu.droidtown.co/Loki_EN/Call/"  #英文版線上 URL
#詳細操作請參考線上版文件：https://api.droidtown.co/document/#Loki_12

payload = {
    "username" : "", # 這裡填入您在 https://api.droidtown.co 使用的帳號 email。
    "func": "create_project",
    "data": {
        "name": "Weather", # 這裡填入您想要在 Loki 上建立的專案名稱(僅接受英文 [a-z, A-Z]、數字 [0-9] 和底線 [_])
        "language": "zh-tw", # 可省略，專案使用語言 { 中文："zh-tw", 台語："taigi" }
        "type": "intent", # 可省略
        #"version": "latest" # 可省略，Articut版本
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
  "loki_key" : ""
}
```
註：線上版每個專案會有一個其專屬的專案金鑰 `loki_key`。

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
    "func": "create_project",
    "project": "Weather", # 這裡填入您想要在 Loki 上建立的專案名稱(僅接受英文 [a-z, A-Z]、數字 [0-9] 和底線 [_])
    "data": {
        "language": "zh-tw", # 可省略，專案使用語言 { 中文："zh-tw", 台語："taigi" }
        "type": "intent", # 可省略
        #"version": "latest" # 可省略，Articut版本
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
