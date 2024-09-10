# LokiTool 
> 本說明適用 [線上版 Loki](https://api.droidtown.co/loki/) , [英文版線上 Loki](https://api.droidtown.co/loki/) 和 Articut Docker 所附上的 LokiTool。


Loki Tool 是操作 [Loki](https://api.droidtown.co/loki/) 的 Web 介面和 API 的工具集。透過 Loki Tool 提供的各式功能，快速加入大量文本與自定義辭典，輕鬆管理 Loki 上的所有專案與意圖。

## Loki Tool 使用說明

[點擊此處](https://github.com/Droidtown/LokiTool_Doc/wiki/Home)或上方的`Wiki`標籤查看更詳細的 Loki Tool 應用教學

### 一、意圖/句型分析模型
#### 基本功能
- [Create_Project_intent](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Create_Project_intent.md)
- [Create_Intent](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Create_Intent.md)
- [Insert_Utterance](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Insert_Utterance.md)
- [Update_Userdefined](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Update_Userdefined.md)
- [Get_Info](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Get_Info.md)
- [Get_Utterance](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Get_Utterance.md)
- [Match_Utterance](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Match_Utterance.md)
- [Reset_Userdefined](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Reset_Userdefined.md)

### 額外功能
1. 加入生成模型 - 加入LLM
Loki Tool 能使用生成模型。Loki 可以串接 ChatGpt API，並帶入自定義額外資訊，提昇模型的準確性。
- [Set_LLM](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Set_LLM.md)
- [Insert_Assistant](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Insert_Assistant.md)
- [Update_Prompt](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Update_Prompt.md)

使用生成模型時，為了不讓使用者的資料外洩，Alias 以「別名」取代真實資料送至生成模型，保護使用者隱私。
- [Update_Alias](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Update_Alias.md)
- [Preview_Alias](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Preview_Alias.md)
- [Run_Alias](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Run_Alias.md)
- [Reset_Alias](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Reset_Alias.md)

2. 長名詞自動偵測
Loki Web 介面中能自動偵測長名詞並生成自定義辭典。

### 二、文本分類-分群模型
Loki Tool 提供了 `NeuroKumoko` 與 `GreedySlime`，協助您建立 文本分類/分群 模型，處理大批資料集，並判斷新資料所屬的分類。

#### NeuroKumoko
- [Create_Project_NeuroKumoko](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Create_Project_NeuroKumoko)
- [Insert_Document](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Insert_Document)
- [Deploy_Model](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Deploy_Model))
- [Check_Model](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Check_Model)

如果您想讓 LLM 祝您一臂之力，產生文章摘要，您可以額外設定加入生成模型：
- [Set_LLM](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Set_LLM)

#### GreedySlime
- [Create_Project_GreedySlime](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Create_Project_GreedySlime)
- [Insert_Document](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Insert_Document)
- [Deploy_Model](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Deploy_Model)
- [Check_Model](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Check_Model)
- [Get_Source](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Get_Source)

如果您想讓 LLM 祝您一臂之力，產生文章摘要，您可以額外設定加入生成模型：
- [Set_LLM](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Set_LLM)