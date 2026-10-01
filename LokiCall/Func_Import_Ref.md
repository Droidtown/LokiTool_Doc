# 匯入 Loki ref 檔


## 線上 API

.ref 檔是線上版 Loki 用以交換不同 intent 時的格式。

```python
import json
from requests import post
from pprint import pprint

refDICT = json.load(open("REF_PATH", encoding="utf-8"))

url = "https://api.droidtown.co/Loki/Call/"

payload = {
  "username": "", # 這裡填入您在 https://api.droidtown.co 使用的帳號 email。     Docker 版不需要此參數！
  "loki_key": "", # 這裡填入您在 https://api.droidtown.co 登入後取得的 loki_key。 Docker 版不需要此參數！
  "intent": "NEW_INTENT_NAME",  #意圖名稱
  "func": "import_ref",
  "data": {
    "ref": refDICT
   }
 }

response = post(url, json=payload).json()
pprint(response)
```

## Docker
```python
import json
from requests import post
from pprint import pprint

refDICT = json.load(open("REF_PATH", encoding="utf-8"))

url = "http://LokiTool_URL/loki/call/" #LokiCall Docker 版請自訂 URL
                                       #步驟 01: 確認 lokitool 啟動
                                       #步驟 02: 取得 lokitool 的 URL
                                       #步驟 03: 將 lokitool 的 URL 取代這一行裡的 LokiTool_URL
                                       #詳細操作請參考 Docker 版文件： https://api.droidtown.co/ArticutDocker/document/#LokiTool
                                       
payload = {
  "project": "YOUR_PROJECT_NAME",  #專案名稱
  "intent": "NEW_INTENT_NAME",  #意圖名稱
  "func": "import_ref",
  "data": {
    "ref": refDICT
  }
}

response = post(url, json=payload).json()
pprint(response)
```

輸出結果如下：

```python
{
    "status": true,
    "msg": "Success!"
}
```
