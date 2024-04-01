# 新增大量句子

在 `loki_key` 對應的 文本分類專案 內新增大量的分類或分群文件。
**注意！標題與內容相同的文件不會重複新增**

```python
from requests import post
from pprint import pprint

#url = "https://api.droidtown.co/Loki/Call/"  #線上版 URL
#url = "https://nlu.droidtown.co/Loki/Call/"  #英文版線上 URL
url = "http://LokiTool_URL/loki/call/" #LokiCall Docker 版請自訂 URL
payload = {
    "username" : "", # 這裡填入您在 https://api.droidtown.co 使用的帳號 email。     Docker 版不需要此參數！
    "loki_key" : "", # 這裡填入您在 https://api.droidtown.co 登入後取得的 loki_key。 Docker 版不需要此參數！
    "func": "insert_document",
    "data": {
        "document": [
            {
                "label": "標籤1",
                "title": "範例標題1",
                "content": "範例內文1",
                "keyword": ["keyword1"]
            },
            {
                "label": "標籤1",
                "title": "範例標題2",
                "content": "範例內文2",
                "keyword": ["keyword2"]
            },
            {
                "label": "標籤2",
                "title": "範例標題3",
                "content": "範例內文3",
                "keyword": ["keyword3", "keyword4"]
            }
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
    "msg": "Success!",
    "result_list": []
}
```