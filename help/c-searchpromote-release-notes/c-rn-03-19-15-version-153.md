---
description: 'null'
seo-description: 'null'
seo-title: Search&amp;Promote 15.3.1发行说明(2015/03/24)
solution: Target
title: Search&amp;Promote 15.3.1发行说明(2015/03/24)
topic: Release Notes,Site search and merchandising
uuid: f02da5a4-2207-4603-aa05-5cff7be16dd5
translation-type: tm+mt
source-git-commit: ffdec2cfcb30e733c664a7d1ca23868b7a9a9aa5

---


# Search&amp;Promote 15.3.1 Release Notes (03/24/2015){#search-promote-release-notes}

## 新增功能和增强功能 {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* 搜索产品模型编号——添加了新的语言学设置，允许您选择在字母数字过渡上拆分令牌。 此功能允许部分或产品样式令牌上更灵活的自由文本匹配。

   请参 **[!UICONTROL Partial Alphanumeric Matching]** 阅 [配置搜索词与Web内容的匹配方式……](../c-about-linguistics-menu/c-about-words-and-language.md#task_351A9144A51F4B41923BDBACDEF3B616).

* 增加了导出数据视图结果的功能。

   请参阅 [关于数据视图](../c-about-reports-menu/c-about-data-views.md#concept_DCA897D074464BC1861AA47B40CC86C3)。

* 动态生成范围属性自动分块值分块功能的范围。

   Adobe Systems当前要求您提供内容标识范围值，以便执行此操作。 例如，如果价格为10，则生成范围字符串“$10到$20”)。 或者，Adobe Systems要求您使用脚本过滤。 为元数据字段定义添加了新属性，仅适用于 `Type=Number` 字段。 新选项将数字字段与字段关联 `Type=Text` 起来，并指定描述如何构建范围描述的配置信息。

   请参 [阅添加新的元标记字段](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。

## 修复 {#section_22D1AFC99F394D569898828A0D3C419D}

* 彩块化边栏编辑对话框应包括分阶段彩块化。
* 对于包含日文字符的搜索，为“嵌入”搜索模式清空核心搜索结果。
* Word .docx文件的Tika转换现在填充该属 `title` 性。
* 更正了管理器中错误的“重复横幅” **[!UICONTROL Banner]** 消息。
* [!DNL Dynamic Media Classic] 横幅现在与协议无关。
* 在元 **[!UICONTROL Table Name]** 数据用户界面中编辑用户定义的字段时，字段属性有时会隐藏，即使为帐户 **[!UICONTROL Dynamic Facets]** 启用了字段属性也是如此。
* **[!UICONTROL Recent Searches]** 不再对非ASCII字符进行多重编码。
* 无需使用脚本过滤即可填充MDI字段。
* 建议中的编码错误。
* “其他已选择的facet”触发器现在可正确处理复杂的业务规则。

