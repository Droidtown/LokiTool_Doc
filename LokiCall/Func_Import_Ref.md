# 匯入 Loki ref 檔


## 線上 API

.ref 檔是線上版 Loki 用以交換不同 intent 時的格式。

```python
from reuqests import post
import json

refDICT = json.load(open("REF_PATH", encoding="utf-8"))

url = "https://api.droidtown.co/Loki/Call/"
payload = {
  "username": "YOUR_USERNAME",
  "loki_key": "YOUR_PROJECT_KEY",
  "intent": "NEW_INTENT_NAME",
  "func": "import_ref",
  "data": {"ref": refDICT}
}

post(url, json=payload).json()
```