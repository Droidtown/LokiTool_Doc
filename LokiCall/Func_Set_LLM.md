# 設定 LLM
> 適用於 `意圖/句型分析`, `NeuroKumoko(文本分類)` 和 `GreedySlime(文本分群)` 等模型。

設定 Loki 專案內要使用的生成模型相關內容。

> [!IMPORTANT]
> 
> 使用此功能即代表您已詳閱並同意我們的**免責聲明**：
> 1. 啟用生成式 AI 模型設定 (下稱「生成模型」)，即表示使用者已同意本免責聲明。
> 2. 設定生成模型串接功能後，卓騰語言科技非串接後所生成之內容服務提供者，卓騰語言科技不對所串接之ChatGPT或其他生成模型之內容及使用者使用本產品串接其他軟體後因所串接軟體內容修改所生之結果負責。

## 線上 API

> docker 版與線上版的參數不一致！請參見下面的說明

```python
from requests import post
from pprint import pprint

url = "https://api.droidtown.co/Loki/Call/"  #線上版 URL
#url = "https://nlu.droidtown.co/Loki/Call/"  #英文版線上 URL

payload = {
    "username": "", # 這裡填入您在 https://api.droidtown.co 使用的帳號 email。
    "loki_key": "", # 這裡填入您在 https://api.droidtown.co 登入後取得的 loki_key。
    "func": "set_llm",
    "data": {
        "llm": "OpenAI ChatGPT", # OpenAI ChatGPT / Azure ChatGPT
        "model": "gpt-3.5-turbo-16k", # ChatGPT Model
        "api_key": "", # ChatGPT Key
        "endpoint": "", # Only for Azure ChatGPT
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

---

## Docker

> 對於 `NeuroKumoko(文本分類)` 和 `GreedySlime(文本分群)` 等模型，Docker 版提供自定義 prompt 功能。

```python
from requests import post
from pprint import pprint

url = "http://LokiTool_URL/loki/call/" #LokiCall Docker 版請自訂 URL

payload = {
    "project": "",
    "func": "set_llm",
    "data": {
        "llm": "OpenAI ChatGPT", # For llm.json
        "prompt": "" # customize prompt only for NeuroKumoko and GreedySlime
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