# 取得分類或分群模型的部屬狀態

檢查 Loki 中的 文本分類模型 部屬狀態。

## 線上 API

```python
from requests import post
from pprint import pprint

#url = "https://api.droidtown.co/Loki/Call/"  #線上版 URL
#url = "https://nlu.droidtown.co/Loki/Call/"  #英文版線上 URL
url = "http://LokiTool_URL/loki/call/" #LokiCall Docker 版請自訂 URL
payload = {
    "username" : "", # 這裡填入您在 https://api.droidtown.co 使用的帳號 email。     Docker 版不需要此參數！
    "loki_key" : "", # 這裡填入您在 https://api.droidtown.co 登入後取得的 loki_key。 Docker 版不需要此參數！
    "func": "check_model",
    "data": {}
}

response = post(url, json=payload).json()
pprint(response)
```

輸出結果如下：

#### 模型分析中
```json
{
    "msg": "Model is deploying...",
    "progress_status": "processing",
    "status": true
}
```
#### 分析完成
```json
{
    "msg": "Success!",
    "progress_status": "completed",
    "status": true
}
```