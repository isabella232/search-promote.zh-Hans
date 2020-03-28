---
description: 'null'
seo-description: 'null'
seo-title: Search&amp;Promote 8.16.0发行说明(2014/9/18)
solution: Target
title: Search&amp;Promote 8.16.0发行说明(2014/9/18)
topic: Release Notes,Site search and merchandising
uuid: 0a59858b-213b-40d6-aea1-d085c4d6d2fa
translation-type: tm+mt
source-git-commit: ffdec2cfcb30e733c664a7d1ca23868b7a9a9aa5

---


# Search&amp;Promote 8.16.0 Release Notes (9/18/2014){#search-promote-release-notes}

## Search&amp;Promote 8.16.0 Release Notes (9/18/2014) {#topic_5BECD3F66C684987828F6AE65E62DA29}

## New features {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* 在向导式搜索3(GS3)中缓存搜索结果——要为您设置此自定义功能，以便在您的帐户中使用它，请与Adobe技术客户经理联系。
* 频繁更改的字段的垂直更新——您现在可以快速更新一组元数据字段的所有值，而无需完全重新索引您的内容。

   请参阅添加新的meta标签字段和关于垂直更 [新中的表中的垂直更新字段](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)[选项](../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899)。

   This feature can only be used on [!DNL Adobe Search&Promote] accounts that use Index Connector. 为您设置此自定义功能，以便您可以在帐户中使用它，请联系 Adobe 客户技术支持经理。

## Fixes and enhancements {#section_22D1AFC99F394D569898828A0D3C419D}

* Corrected the Index Connector parsing of XML feeds that contained `?>` string.
* 修复了强制采用最小文档计数时的索引连接器 SFTP 订阅源。
* 现在 Microsoft Excel 的报表导入支持 UTF8。
* 引导式搜索：Facet 编译速度慢。
* 属性加载程序：总计数据有复制键。
* 修复了激活单个规则时业务规则运行顺序错误的问题。
* 引导式搜索生成错误的 Facet 还原链接。
* 增加了新的远程控制操作 `sp_lines=N`，使您可以检查当前运行的索引爬网的进度和状态。

   请参 [阅关于用于索引的远程控制](../c-about-index-menu/c-about-remote-control-for-indexing.md#concept_C79B322190E84106A434E5C6D4A4118F)。

* 在索引连接器增量过程中提取删除信息时需要发送身份验证信息。
* The [!DNL Change Log] report now identifies the user who initiates a manual index operation.

   See [Viewing the Change Log](../c-about-reports-menu/c-about-reports-menu.md#task_166F1156719F4B3D834BEA8E249C8057).

* When you export a [!DNL Terms Report], you are no longer limited to 500 or less items in the report.

   请参 [阅查看术语报表或空搜索术语报表……](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A).

* 索引连接器 **[!UICONTROL Strip HTML]** 设置始终显示为选中。
* Inconsistent search results were experienced with the **[!UICONTROL Common Phrases]** feature.
* “规则”列表摘要中显示的属性名称被截短。
* 推动单个业务规则的实时推出是推动所有业务规则的实时发布。

