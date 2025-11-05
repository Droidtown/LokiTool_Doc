# 更新 Prompt 別名設定
> 適用於 `意圖/句型分析` 模型

更新以下的 Prompt 別名設定至專案`(Weather)`內的意圖`(AskWeather)`。

- 將詞彙`中央氣象局、氣象局 `替換為`預言家`。
- 將符合 Regex `09[0-9]{8}|\+886[0-9]{9}`替換為`0912345678`。
- 替換`中華民國身分證號碼`及`姓名 (三字)`。

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
    "func": "update_alias",
    "data": {
        "alias": { #Prompt 別名
            "text": { #詞彙替換
                "預言家": ["中央氣象局", "氣象局"]
            },
            "regex": { #Regex 替換
                "0912345678": ["09[0-9]{8}|\+886[0-9]{9}"]
            },
            "ner": { #NER 替換
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
    "func": "update_alias",
    "data": {
        "alias": { #Prompt 別名
            "text": { #詞彙替換
                "預言家": ["中央氣象局", "氣象局"]
            },
            "regex": { #Regex 替換
                "0912345678": ["09[0-9]{8}|\+886[0-9]{9}"]
            },
            "ner": { #NER 替換
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
