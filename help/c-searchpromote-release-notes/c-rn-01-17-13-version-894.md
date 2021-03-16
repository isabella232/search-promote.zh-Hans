---
description: Search&amp;Promote 8.9.4发行说明。
solution: Target
title: Search&amp;Promote 8.9.4发行说明(01/17/2013)
topic: 发行说明、网站搜索和销售
uuid: a9d550f6-0a23-4c71-b123-c31b997e7384
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 33%

---


# Search&amp;Promote 8.9.4发行说明(01/17/2013){#search-promote-release-notes}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>新增功能和增强功能 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>规则 </p> </td> 
   <td colname="col2"> <p> 已添加在您创建查询清理规则、搜索前规则和搜索后规则时创建内嵌注释的功能。注释字段可让您记录和说明这些规则。 </p> <p>请参阅<a href="../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C" format="dita" scope="local">关于查询清理规则</a>。 </p> <p>请参阅<a href="../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F" format="dita" scope="local">关于预搜索规则</a>。 </p> <p>请参阅<a href="../c-about-rules-menu/c-about-post-search-rules.md#concept_AF6ADFCC0ADF4A788003964939917FDE" format="dita" scope="local">关于搜索后规则</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>引导式搜索 </p> </td> 
   <td colname="col2"> <p> 添加了“向导式搜索”标记以指示搜索所用的总时间。 </p> <p> <span class="codeph"> &lt;guided-search-time&gt;</span>  — 确定搜索所花的时间。返回的搜索时间值以毫秒为单位指定。 </p> <p> <span class="codeph"> &lt;guided-fall-through-searches&gt;</span>  — 返回用于生成搜索结果页面的核心搜索数。 </p> <p> <span class="codeph"> &lt;guided-if-fall-through-search&gt;</span>  — 测试核心搜索的计数是否大于1。 </p> <p>另请参阅<a href="../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64" format="dita" scope="local">演示文稿模板标签</a>中的其他语言。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**修复**

* 术语报表现在忽略星号字符。

   请参阅[查看术语报表或空搜索术语报表……](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A)。

* 打开&#x200B;**[!UICONTROL Reports > Null Search Terms Report]**，选择一个时段，然后视图报表。 点击此报表中的一个词以打开搜索，然后再次点击查看报表。您所点击的关键词的搜索次数增加了两次。这个问题现在已修复。

   请参阅[查看术语报表或空搜索术语报表……](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A)。

* 实时推送业务规则时，已对性能进行优化。

   请参阅[关于Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD)。

* [!DNL Breadcrumbs] 中的删除功能不是一直有效。

   请参阅[关于痕迹导航](../c-about-design-menu/c-about-breadcrumbs.md#concept_FB8A943C594A4A1593B118141DA61F03)。

* 除非使用重新生成，否则重新排名特征不允许任何更改的排名规则在搜索结果中生效。

   请参阅[有关规则排名](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397)。

   请参阅[关于重新排名索引](../c-about-index-menu/c-about-re-rank-index.md#concept_147B0A9FCD51451787DA898E06F7C692)。

