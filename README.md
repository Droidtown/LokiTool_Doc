# LokiTool 
> 本說明適用 [線上版 Loki](https://api.droidtown.co/loki/) , [英文版線上 Loki](https://api.droidtown.co/loki/) 和 Articut Docker 所附上的 LokiTool。


Loki Tool 是操作 [Loki](https://api.droidtown.co/loki/) 的 Web 介面和 API 的工具集。透過 Loki Tool 提供的各式功能，快速加入大量文本與自定義辭典，輕鬆管理 Loki 上的所有專案與意圖。

## Loki Tool 使用說明

[點擊此處](https://github.com/Droidtown/LokiTool_Doc/wiki/Home)或上方的`Wiki`標籤查看更詳細的 Loki Tool 應用教學


### Functions
- [Create_Project](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Create_Project.md)
- [Create_Intent](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Create_Intent.md)
- [Get_Info](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Get_Info.md)
- [Get_Utterance](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Get_Utterance.md)
- [Insert_Utterance](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Insert_Utterance.md)
- [Match_Utterance](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Match_Utterance.md)
- [Update_Userdefined](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Update_Userdefined.md)
- [Set_LLM](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Set_LLM.md)


## 除了基本的 Loki Tool 功能以外，Loki 也包含了許多額外功能

### ChatGPT API
Loki Tool 能[使用生成模型](https://github.com/Droidtown/LokiTool_Doc/wiki/%E4%BD%BF%E7%94%A8%E7%94%9F%E6%88%90%E6%A8%A1%E5%9E%8B)。Loki 可以串接 ChatGpt API，並帶入自定義額外資訊，提昇模型的準確性。

- [Update_Prompt](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Update_Prompt.md)
- [Insert_Assistant](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Insert_Assistant.md)

### [Alias](https://github.com/Droidtown/LokiTool_Doc/wiki/%E4%B8%B2%E6%8E%A5-Alias-%E5%8A%9F%E8%83%BD)
使用生成模型時，為了不讓使用者的資料外洩，Alias 以「別名」取代真實資料送至生成模型，保護使用者隱私。

- [Update_Alias](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Update_Alias.md)
- [Preview_Alias](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Preview_Alias.md)
- [Run_Alias](https://github.com/Droidtown/LokiTool_Doc/blob/main/LokiCall/Func_Run_Alias.md)

### [長名詞自動偵測](https://github.com/Droidtown/LokiTool_Doc/wiki/%E9%95%B7%E5%90%8D%E8%A9%9E%E8%87%AA%E5%8B%95%E5%81%B5%E6%B8%AC)
Loki Web 介面中能[自動偵測長名詞](https://github.com/Droidtown/LokiTool_Doc/wiki/%E9%95%B7%E5%90%8D%E8%A9%9E%E8%87%AA%E5%8B%95%E5%81%B5%E6%B8%AC)並生成自定義辭典。

### [建立文本分類-分群模型](https://github.com/Droidtown/LokiTool_Doc/wiki/%E5%BB%BA%E7%AB%8B%E6%96%87%E6%9C%AC%E5%88%86%E9%A1%9E-%E5%88%86%E7%BE%A4%E6%A8%A1%E5%9E%8B)
Loki Tool 提供了 `NeuroKumoko` 與 `GreedySlime`，協助您建立 文本分類/分群 模型，處理大批資料集，並判斷新資料所屬的分類。
