---
description: Search&amp;Promote 15.1.1发行说明。
solution: Target
title: Search&amp;Promote 15.1.1发行说明(01/15/2015)
topic-legacy: Release Notes,Site search and merchandising
uuid: 070f9c46-426f-4ca1-80c7-8ca53d40a402
exl-id: 6176ce1e-aafe-4a46-a564-57c3ac4632ef
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 17%

---

# Search&amp;Promote15.1.1发行说明(01/15/2015){#search-promote-release-notes}

## 新功能 {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* 以前，诸如词干、同义词之类的语言始终会应用到引导式搜索规则中的关键字。现在，您可以停用此项扩展，以便按原样使用关键字。

   如果要将触发条件应用于业务规则，请在[!DNL Advanced Rule Builder]中，在&#x200B;**[!UICONTROL If any/all of the following conditions are met]**&#x200B;之后的第一个下拉列表中，选择&#x200B;**[!UICONTROL keyword]**，然后在第二个下拉列表中选择新运算符&#x200B;**[!UICONTROL equal exact]**。

   请参阅[关于Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD)。

## 修复和增强{#section_22D1AFC99F394D569898828A0D3C419D}

* [!DNL Visual Rule Builder] 并且 [!DNL Advanced Rule Builder] 不再截断MDI(销售文档ID)字段值。
* 与 RBTA 有关的索引失败现已修复。
* 编辑状态为“已批准”的现有业务规则现在会撤销“已批准”状态。 必须使用[!DNL Advanced Rule Builder]重新选中选项&#x200B;**[!UICONTROL Approved]**，然后按常规方式保存规则。 如果您不重新批准已编辑的规则，则在[!DNL Business Rules]页面上，规则的状态将自动设置为“WIP(Work In Progress)”。
* 现在，[!DNL Business Rules]页面上提供了新的&#x200B;**[!UICONTROL Advanced Search]**&#x200B;选项，以改进规则筛选。
* 在[!DNL Query Cleaning]、[!DNL Pre-Search Rules]、[!DNL Post Search Rules]和[!DNL Business Rules]中为规则触发器添加了&#x200B;**[!UICONTROL contains word]**&#x200B;条件，以便您轻松指定换行符。
* 对业务规则注释所做的改进，例如视图规则时，您现在可以检索该规则的注释历史记录。 此外，现在注释记录在&#x200B;**[!UICONTROL Reports]** > **[!UICONTROL Change Log]**&#x200B;中。
* 值为非零`sp_i`的查询不再通过[!DNL Adobe Analytics]重定向器运行。

   请参见[后端搜索CGI参数](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)中表中的第15行。
