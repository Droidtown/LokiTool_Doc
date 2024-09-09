# LokiTool 
> 本說明適用 [線上版 Loki](https://api.droidtown.co/loki/) , [英文版線上 Loki](https://api.droidtown.co/loki/) 和 Articut Docker 所附上的 LokiTool。


Loki Tool 是操作 [Loki](https://api.droidtown.co/loki/) 的 Web 介面和 API 的工具集。透過 Loki Tool 提供的各式功能，快速加入大量文本與自定義辭典，輕鬆管理 Loki 上的所有專案與意圖。

## Loki Tool 使用說明

[點擊此處](https://github.com/Droidtown/LokiTool_Doc/wiki/Home)或上方的`Wiki`標籤查看更詳細的 Loki Tool 應用教學


### Functions
- [Create_Project_intent](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Create_Project_intent.md)
- [Create_Intent](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Create_Intent.md)
- [Insert_Utterance](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Insert_Utterance.md)
- [Update_Userdefined](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Update_Userdefined.md)
- [Get_Info](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Get_Info.md)
- [Get_Utterance](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Get_Utterance.md)
- [Match_Utterance](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Match_Utterance.md)
- [Reset_Userdefined](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Reset_Userdefined.md)

## 除了基本的 Loki Tool 功能以外，Loki 也包含了許多額外功能

### ChatGPT API
Loki Tool 能使用生成模型。Loki 可以串接 ChatGpt API，並帶入自定義額外資訊，提昇模型的準確性。

- [Update_Prompt](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Update_Prompt.md)
- [Insert_Assistant](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Insert_Assistant.md)

### Alias
使用生成模型時，為了不讓使用者的資料外洩，Alias 以「別名」取代真實資料送至生成模型，保護使用者隱私。

- [Update_Alias](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Update_Alias.md)
- [Preview_Alias](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Preview_Alias.md)
- [Run_Alias](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Run_Alias.md)
- [Reset_Alias](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Reset_Alias.md)

### 長名詞自動偵測
Loki Web 介面中能自動偵測長名詞並生成自定義辭典。

### 建立文本分類-分群模型
Loki Tool 提供了 `NeuroKumoko` 與 `GreedySlime`，協助您建立 文本分類/分群 模型，處理大批資料集，並判斷新資料所屬的分類。
