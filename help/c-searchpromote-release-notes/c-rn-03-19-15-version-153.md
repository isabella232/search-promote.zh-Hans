---
description: Search&amp;Promote 15.3.1发行说明。
solution: Target
title: Search&amp;Promote 15.3.1发行说明(03/24/2015)
topic: 发行说明、网站搜索和销售
uuid: f02da5a4-2207-4603-aa05-5cff7be16dd5
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 1%

---


# Search&amp;Promote15.3.1发行说明(03/24/2015){#search-promote-release-notes}

## 新增功能和增强功能 {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* 搜索产品模型编号 — 添加了新的语言学设置，允许您选择在字母数字过渡上拆分令牌。 此功能允许部件或产品样式令牌中更灵活的自由文本匹配。

   请参阅[中的&#x200B;**[!UICONTROL Partial Alphanumeric Matching]**&#x200B;配置搜索词与Web内容的匹配方式……](../c-about-linguistics-menu/c-about-words-and-language.md#task_351A9144A51F4B41923BDBACDEF3B616)。

* 增加了导出数据视图结果的功能。

   请参阅[关于数据视图](../c-about-reports-menu/c-about-data-views.md#concept_DCA897D074464BC1861AA47B40CC86C3)。

* 动态生成范围属性自动分面值分段特征的范围。

   Adobe Systems当前要求您提供内容标识范围值以执行此操作。 例如，如果价格为10，则生成范围字符串&quot;$10到$20&quot;)。 或者，Adobe Systems要求您使用脚本过滤。 为元数据字段定义添加了新属性，仅适用于`Type=Number`字段。 新选项将数字字段与`Type=Text`字段关联，并指定说明如何构建范围描述的配置信息。

   请参阅[添加新的meta标签字段](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。

## 修复 {#section_22D1AFC99F394D569898828A0D3C419D}

* Facet边栏编辑对话框应包括已分阶的Facet。
* 对于包含日文字符的搜索，“嵌入”搜索模式的核心搜索结果为空。
* Word .docx文件的Tika转换现在填充`title`属性。
* 更正了&#x200B;**[!UICONTROL Banner]**&#x200B;管理器中错误的“重复横幅”消息。
* [!DNL Dynamic Media Classic] 横幅现在与协议无关。
* 在元数据用户界面中编辑用户定义的字段时，有时会隐藏&#x200B;**[!UICONTROL Table Name]**&#x200B;字段属性，即使为帐户启用了&#x200B;**[!UICONTROL Dynamic Facets]**。
* **[!UICONTROL Recent Searches]** 不再对非ASCII字符进行多重编码。
* 无需使用脚本过滤即可填充MDI字段。
* 建议中的编码错误。
* “其他已选择的facet”触发器现在可以正确处理复杂的业务规则。

