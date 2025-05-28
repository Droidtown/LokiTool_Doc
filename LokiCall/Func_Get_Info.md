# 取得專案句子
> 適用於 `意圖/句型分析`, `NeuroKumoko(文本分類)` 和 `GreedySlime(文本分群)` 等模型

針對不同種類的 Loki 專案，取得該專案內的詳細資訊。

## 意圖/句型分析 專案

獲取專案`(Weather)`內所有意圖中的句子。
> docker 版與線上版的參數不一致！請參見下面的說明

```python
from requests import post
from pprint import pprint

#url = "https://api.droidtown.co/Loki/Call/"  #線上版 URL
#url = "https://nlu.droidtown.co/Loki_EN/Call/"  #英文版線上 URL
url = "http://LokiTool_URL/loki/call/" #LokiCall Docker 版請自訂 URL
payload = {
    #"username" : "", # 這裡填入您在 https://api.droidtown.co 使用的帳號 email。     Docker 版不需要此參數！
    #"loki_key": "", # 這裡填入您在 https://api.droidtown.co 登入後取得的 loki_key。     Docker 版不需要此參數！
    "project": "Weather", # 這裡填入您想要查詢的 project name。     線上版不需要此參數！
    "func": "get_info",
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
    "result": {
        "project_name": "AskWeather",
        "intent": {
            "Weather": [
                "下午會不會下雨？",
                "今天天氣如何？"
            ]
        },
        "total_intent_count": 1,
        "total_utterance_count": 2
    }
}
```

## Neuro Kumoko (文本分類) 專案

獲取專案內的所有文件資訊。
> 文件內容 `content` 長度最多回傳 15 個字元，超過的內容會被省略！

```python
from requests import post
from pprint import pprint

url = "https://api.droidtown.co/Loki/Call/"  #線上版 URL
#url = "https://nlu.droidtown.co/Loki/Call/"  #英文版線上 URL
#url = "http://LokiTool_URL/loki/call/" #LokiCall Docker 版請自訂 URL
payload = {
    "username" : "", # 這裡填入您在 https://api.droidtown.co 使用的帳號 email。     Docker 版不需要此參數！
    "loki_key": "", # 這裡填入您在 https://api.droidtown.co 登入後取得的 loki_key。     Docker 版不需要此參數！
    #"project": "Weather", # 這裡填入您想要查詢的 project name。     線上版不需要此參數！
    "func": "get_info",
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
    "result": {
        "project_name": "your_project_name",
        "label": {
            "類別1": [
                {
                    "title": "資料1",
                    "content": "資料內容1"
                },
                {
                    "title": "資料2",
                    "content": "資料內容2"
                },
                {
                    "title": "資料3",
                    "content": "資料內容3"
                }
            ],
            "類別2": [
                {
                    "title": "資料4",
                    "content": "資料內容4"
                },
                {
                    "title": "資料5",
                    "content": "資料內容5"
                }
            ]
        },
        "document_count": 5
    }
}
```

## Greedy Slime (文本分群) 專案
獲取專案內所有文件的 `分群` 結果。

> 文件內容 `content` 長度最多回傳 15 個字元，超過的內容會被省略！

```python
from requests import post
from pprint import pprint

url = "https://api.droidtown.co/Loki/Call/"  #線上版 URL
#url = "https://nlu.droidtown.co/Loki/Call/"  #英文版線上 URL
#url = "http://LokiTool_URL/loki/call/" #LokiCall Docker 版請自訂 URL
payload = {
    "username" : "", # 這裡填入您在 https://api.droidtown.co 使用的帳號 email。     Docker 版不需要此參數！
    "loki_key": "", # 這裡填入您在 https://api.droidtown.co 登入後取得的 loki_key。     Docker 版不需要此參數！
    #"project": "Weather", # 這裡填入您想要查詢的 project name。     線上版不需要此參數！
    "func": "get_info",
    "data": {}
}

response = post(url, json=payload).json()
pprint(response)
```


輸出結果如下

```json
{
    "msg": "Success!",
    "result": {
        "cluster": {
            "cluster_1": {
                "key_info": [
                    "關鍵詞1",
                    "關鍵詞2",
                ],
                "source": [
                    "段落1",
                    "段落2"
                ],
            "document_count": 2,
            "project_name": ""
            }
        }
    },
    "status": true
}
```
