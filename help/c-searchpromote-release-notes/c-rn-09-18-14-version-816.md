---
description: Search&amp;Promote 8.16.0发行说明。
solution: Target
title: Search&amp;Promote 8.16.0发行说明(9/18/2014)
topic: Release Notes,Site search and merchandising
uuid: 0a59858b-213b-40d6-aea1-d085c4d6d2fa
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 39%

---


# Search&amp;Promote 8.16.0发行说明(9/18/2014){#search-promote-release-notes}

## Search&amp;Promote 8.16.0发行说明(9/18/2014){#topic_5BECD3F66C684987828F6AE65E62DA29}

## 新增功能{#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* 在“向导式搜索3(GS3)”中缓存搜索结果 — 要设置此自定义功能以便您可以在帐户中使用它，请与Adobe技术客户经理联系。
* 频繁更改字段的垂直更新 — 您现在可以快速更新一组元数据字段的所有值，而无需完全重新索引您的内容。

   请参见[添加新元标记字段](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)和[关于垂直更新](../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899)中的表中的“垂直更新字段”选项。

   此功能只能用于使用索引连接器的[!DNL Adobe Search&Promote]帐户。 为您设置此自定义功能，以便您可以在帐户中使用它，请联系 Adobe 客户技术支持经理。

## 修复和增强{#section_22D1AFC99F394D569898828A0D3C419D}

* 更正了包含`?>`字符串的XML源的索引连接器分析。
* 修复了强制采用最小文档计数时的索引连接器 SFTP 订阅源。
* 现在 Microsoft Excel 的报表导入支持 UTF8。
* 引导式搜索：Facet 编译速度慢。
* 属性加载程序：总计数据有复制键。
* 修复了激活单个规则时业务规则运行顺序错误的问题。
* 引导式搜索生成错误的 Facet 还原链接。
* 增加了新的远程控制操作 `sp_lines=N`，使您可以检查当前运行的索引爬网的进度和状态。

   请参阅[关于用于索引的远程控制](../c-about-index-menu/c-about-remote-control-for-indexing.md#concept_C79B322190E84106A434E5C6D4A4118F)。

* 在索引连接器增量过程中提取删除信息时需要发送身份验证信息。
* [!DNL Change Log]报告现在标识启动手动索引操作的用户。

   请参阅[查看更改日志](../c-about-reports-menu/c-about-reports-menu.md#task_166F1156719F4B3D834BEA8E249C8057)。

* 导出[!DNL Terms Report]时，报告中的项目数不再限制为500个或更少。

   请参阅[查看术语报表或空搜索术语报表……](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A)。

* 索引连接器 **[!UICONTROL Strip HTML]** 设置始终显示为选中。
* 使用&#x200B;**[!UICONTROL Common Phrases]**&#x200B;功能时，搜索结果不一致。
* “规则”列表摘要中显示的属性名称被截短。
* 将单个业务规则实时推送就是将所有业务规则实时推送。

