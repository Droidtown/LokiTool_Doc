# 調用卓騰語言科技架設的 LLM

```python
from requests import post

url = "https://api.droidtown.co/Loki/Call/" # 中文版
#url = "https://nlu.droidtown.co/Loki_EN/Call/" # 英文版

payload = {
  "username": "YOUR_USERNAME",
  "func": "call_llm",
  "data": {
    "model": "Gemma2-9B", # [Gemma2-9B, Gemma3-12B, Gemma3-27B, Llama3-8B, Llama3-70B, Llama3-Taiwan-8B, Llama3.3-70B, Phi3-3B, Phi4-14B, Nemotron-4B]
    "system": "你是一個天氣助理", # optional
    "assistant": "中央氣象局丁小雨：「今天下午梅雨季鋒面報到，氣象局發出超大豪雨特報。」", # optional
    "user": "依上文設定，請問氣象局助理今天下午會不會下雨？", # required
  }
}

result = post(url, json=payload).json()
```

輸出結果如下：

```python
{
    'status': True,
    'result': [
        {'model': 'Gemma-2-9B-Chinese-Chat.Q4_0',
         'created_at': '2024-09-26T02:22:03.839412Z',
         'message': {'role': 'assistant',
         'content': '根據中央氣象局的最新報告，今天下午確實會有較大的降雨。氣象局已經發出了超大豪雨特報，請您注意防範措施，比如攜帶雨傘、穿著適合的衣物以應對濕冷的天氣，並且留意周遭環境可能出現的水坑或積水，避免不必要的安全風險。'},
         'done_reason': 'stop',
         'done': True,
         'total_duration': 2351226875,
         'load_duration': 47480833,
         'prompt_eval_count': 103,
         'prompt_eval_duration': 331505000,
         'eval_count': 83,
         'eval_duration': 1969274000}
     ]
}
```
