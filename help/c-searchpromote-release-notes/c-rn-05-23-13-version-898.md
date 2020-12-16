---
description: 'null'
seo-description: 'null'
seo-title: Search&amp;Promote 8.9.8发行说明(05/23/2013)
solution: Target
title: Search&amp;Promote 8.9.8发行说明(05/23/2013)
topic: Release Notes,Site search and merchandising
uuid: ff4bfc53-1d0e-4b7d-83ad-54c81d3f9769
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 57%

---


# Search&amp;Promote8.9.8发行说明(05/23/2013){#search-promote-release-notes}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>新功能 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 常用短语 - 支持精确匹配 </p> </td> 
   <td colname="col2"> <p> 常见短语包含两个或多个词组，它们作为整体进行搜索，如“boot cut”或“tank top”，而不是作为单独的部分。 常用短语代表唯一、不同于它的任何单个字词的含义。 </p> <p> 您可以维护一个与自己业务有关的常用短语词典。当客户执行一个含有多个字词的搜索查询时，就可以在该词典上进行查询以获得精确匹配。 </p> <p>您可以添加、编辑或删除常用短语。还可以像各种领域词典一样，将常用短语进行分组。例如，可以将常用短语按照服装、织物、珠宝、尺寸、购物和常规进行分组。 </p> <p>请参阅<a href="../c-about-linguistics-menu/c-about-common-phrases.md#concept_4946E53586DF492EAEB1B7F757FD440F" format="dita" scope="local">关于常用短语</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**修复和增强功能**

* 后端搜索CGI参数`sp_date_range_#`对用户定义的字段无效。

   请参阅[后端搜索CGI参数](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。

* 还原&#x200B;**[!UICONTROL History]**&#x200B;版本未更新URL入口点字段内容。

   请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   另请参阅[关于URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

* JSON 编码不管理编码错误的字符。
* 目前增加的支持允许您远程实现阶段性指标。

   请参阅[关于索引的远程控制](../c-about-index-menu/c-about-remote-control-for-indexing.md#concept_C79B322190E84106A434E5C6D4A4118F)。

