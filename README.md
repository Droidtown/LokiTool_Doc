# LokiTool 
> 本說明適用 https://api.droidtown.co/loki/ 和 Articut Docker 所附上的 LokiTool。


Loki Tool 是操作 Loki 的 Web 介面和 API 的工具集。透過 Loki Tool 提供的各式功能，快速加入大量文本與自定義辭典，輕鬆管理 Loki 上的所有專案與意圖。


### Functions
- [Create_Project](https://github.com/Droidtown/LokiTool_Doc/wiki/Func_Create_Project)
- [Create_Intent](https://github.com/Droidtown/LokiTool_Doc/wiki/Func_Create_Intent)
- [Get_Info](https://github.com/Droidtown/LokiTool_Doc/wiki/Func_Get_Info)
- [Get_Utterance](https://github.com/Droidtown/LokiTool_Doc/wiki/Func_Get_Utterance)
- [Insert_Utterance](https://github.com/Droidtown/LokiTool_Doc/wiki/Func_Insert_Utterance)
- [Match_Utterance](https://github.com/Droidtown/LokiTool_Doc/wiki/Func_Match_Utterance)
- [Update_Userdefined](https://github.com/Droidtown/LokiTool_Doc/wiki/Func_Update_Userdefined)


## 除了基本的 Loki Tool 功能以外，Loki 也包含了許多額外功能

### ChatGpt API
LokiTool 能[使用生成模型](https://github.com/Droidtown/LokiTool_Doc/wiki/%E4%BD%BF%E7%94%A8%E7%94%9F%E6%88%90%E6%A8%A1%E5%9E%8B)。Loki 可以串接 ChatGpt API，並帶入自定義額外資訊，提昇模型的準確性。

- [Update_Prompt](https://github.com/Droidtown/LokiTool_Doc/wiki/Func_Update_Prompt)
- [Insert_Assistant](https://github.com/Droidtown/LokiTool_Doc/wiki/Func_Insert_Assistant)

### [Alias](https://github.com/Droidtown/LokiTool_Doc/wiki/%E4%B8%B2%E6%8E%A5-Alias-%E5%8A%9F%E8%83%BD)
使用生成模型時，為了不讓使用者的資料外洩，Alias 以「別名」取代真實資料送至生成模型，保護使用者隱私。

- [Update_Alias](https://github.com/Droidtown/LokiTool_Doc/wiki/Func_Update_Alias)
- [Preview_Alias](https://github.com/Droidtown/LokiTool_Doc/wiki/Func_Preview_Alias)
- [Run_Alias](https://github.com/Droidtown/LokiTool_Doc/wiki/Func_Run_Alias)

### [長名詞自動偵測](https://github.com/Droidtown/LokiTool_Doc/wiki/%E9%95%B7%E5%90%8D%E8%A9%9E%E8%87%AA%E5%8B%95%E5%81%B5%E6%B8%AC)
Loki Web 介面中能自動偵測長名詞並生成自定義辭典。