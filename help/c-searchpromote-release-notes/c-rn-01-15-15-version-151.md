---
description: 'null'
seo-description: 'null'
seo-title: Search&amp;Promote 15.1.1发行说明(2015/01/15)
solution: Target
title: Search&amp;Promote 15.1.1发行说明(2015/01/15)
topic: Release Notes,Site search and merchandising
uuid: 070f9c46-426f-4ca1-80c7-8ca53d40a402
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Search&amp;Promote 15.1.1 Release Notes (01/15/2015){#search-promote-release-notes}

## 新功能 {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* 以前，诸如词干、同义词之类的语言始终会应用到引导式搜索规则中的关键字。现在，您可以停用此项扩展，以便按原样使用关键字。

   如果要将触发条件应用于业务规则，请在第一个下拉列 [!DNL Advanced Rule Builder]表中 **[!UICONTROL If any/all of the following conditions are met]**，选择 **[!UICONTROL keyword]**，然后在第二个下拉列表中选择 **[!UICONTROL equal exact]** 新的运算符。

   See [About Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

## Fixes and enhancements {#section_22D1AFC99F394D569898828A0D3C419D}

* [!DNL Visual Rule Builder] 并且 [!DNL Advanced Rule Builder] 不再截断MDI（销售文档ID）字段值。
* 与 RBTA 有关的索引失败现已修复。
* 编辑状态为“已批准”的现有业务规则现在会撤消“已批准”状态。 You must use [!DNL Advanced Rule Builder] to recheck the option **[!UICONTROL Approved]**, and then save the rule as usual. If you do not reapprove an edited rule, the rule&#39;s status is automatically set to WIP (Work In Progress) on the [!DNL Business Rules] page.
* A new **[!UICONTROL Advanced Search]** option is now available on the [!DNL Business Rules] page for improved filtering of rules.
* 为 **[!UICONTROL contains word]** 、 [!DNL Query Cleaning]和中的规则触发器添加了条件， [!DNL Pre-Search Rules][!DNL Post Search Rules][!DNL Business Rules]以便您轻松指定分词。
* 对业务规则注释所做的改进，例如在查看规则时，您现在可以检索该规则的注释历史记录。 此外，注释现已登录 **[!UICONTROL Reports]** > **[!UICONTROL Change Log]**。
* Queries with nonzero `sp_i` values are no longer run through the [!DNL Adobe Analytics] redirector.

   请参阅后端搜索CGI参数中 [的表中的第15行](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。

