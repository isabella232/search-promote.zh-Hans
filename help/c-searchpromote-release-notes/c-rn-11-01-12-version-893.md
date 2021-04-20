---
description: Search&amp;Promote 8.9.3发行说明。
solution: Target
title: Search&amp;Promote 8.9.3发行说明(11/01/2012)
topic: Release Notes,Site search and merchandising
uuid: 7bc7bcb6-f47f-4e05-94e5-a22a13a187b7
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 79%

---


# Search&amp;Promote 8.9.3发行说明(11/01/2012){#search-promote-release-notes}

## Search&amp;Promote 8.9.3发行说明(11/01/2012){#concept_85F5B4B4C40C43FEA3AD63E6EA5593CF}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>新增功能和增强功能 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Facet Rail </p> </td> 
   <td colname="col2"> <p> 
     <!--3309390-->添加了新的 <span class="uicontrol">Facet Rail</span> 选项以帮助您更好地控制 Facet 群组和 Facet 名称的排序（按数量、字母）。 </p> <p>请参阅<a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local">关于 Facet Rail</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 嵌套的 Facet </p> </td> 
   <td colname="col2"> <p> 添加了对嵌套的 Facet 的其他排序方式的支持。 </p> <p>请参阅<a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local">关于 Facet Rail</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>排名规则中的附注字段 </p> </td> 
   <td colname="col2"> <p> 
     <!--3063772-->在进行规则排名和规则群组定义的<span class="wintitle">添加排名量度</span>对话框和<span class="wintitle">编辑排名量度</span>对话框中添加了多行<span class="wintitle">注释</span>字段。 </p> <p>规则排名注释显示在<span class="wintitle">定义排名规则</span>页面上。规则群组注释在您编辑定义时显示。 </p> <p>请参阅<a href="../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397" format="dita" scope="local">有关规则排名</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>业务规则 </p> </td> 
   <td colname="col2"> <p> 
     <!--3331637-->通过在业务规则中使用新的<span class="uicontrol">删除所有结果</span>选项删除免费结果，改进了登陆页面的支持。 </p> <p>将此新选项与其他业务规则操作结合使用可创建“封装的登陆页面”。也就是说，如果您只想要按业务规则操作创建页面的内容，则需要放弃搜索的“免费”结果。 </p> <p>请参阅<a href="../c-about-rules-menu/c-about-business-rules.md#task_BD3B31ED48BB4B1B8F1DCD3BFA2528E7" format="dita" scope="local">添加新业务规则</a>或<a href="../c-about-rules-menu/c-about-business-rules.md#task_375CFA75D1D94D9E92A35DE1228E5087" format="dita" scope="local">编辑业务规则</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>横幅和业务规则 </p> </td> 
   <td colname="col2"> <p> 添加了支持选项，使用该选项，您可以根据条件选择在对引用横幅的业务规则进行实时推送时，不对该横幅进行实时推送。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**修复**

* 当存在[!DNL Stage]索引时，业务规则工作不一致。
* 自动规则排名现在可应用于封装的登陆页面。

   请参阅[添加排名规则](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A)中的选项表。

* [!DNL promosearch.cgi] 未退回促销。

   请参阅[关于搜索](../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8)。

* 推送引用许多横幅的规则时有时会失败。

   请参阅[关于横幅](../c-about-design-menu/c-about-banners.md#concept_5BBE01FEC6134393B43CC917C8CC64DA)。

* **[!UICONTROL Did You Mean]** 搜索查询缓存现已禁用。

   请参阅[关于 Did You Mean](../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E)。

