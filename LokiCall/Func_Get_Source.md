# 取得 GreedySlime 模型內各文本的來源出處

> 適用於 `GreedySlime(文本分群)` 模型。

取得 GreedySlime 模型內經過 Loki 分類後，各類別內文本的來源出處。

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
    "project": "", #專案名稱 (請先在 Loki 的設定網頁裡建立一個 Project 以便取得它的專案金鑰 (loki_key)
    "func": "get_source",
    "data": {
        "source": "" # 這裡填入您想要得到來源出處的對應文本
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
    "project": "", #專案名稱
    "func": "get_source",
    "data": {
        "source": "" # 這裡填入您想要得到來源出處的對應文本
    }
}

response = post(url, json=payload).json()
pprint(response)
```

輸出結果如下

```json
{
    "status": true,
    "result": {
        "content": "這裡會回覆來源出處整段文本",
        "end": 5290,
        "start": 5280,
        "title": "這裡會回覆該文章標題"
    },
}

```
