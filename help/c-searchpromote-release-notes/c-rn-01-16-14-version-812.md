---
description: Search&amp;Promote 8.12.0发行说明。
solution: Target
title: Search&amp;Promote 8.12.0发行说明(01/16/2014)
topic: 发行说明、网站搜索和销售
uuid: 4db10eb4-11bf-4483-a7f2-87981d9c7a50
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 72%

---


# Search&amp;Promote 8.12.0发行说明(01/16/2014){#search-promote-release-notes}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>新增功能和增强功能 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>添加了词根字典 </p> </td> 
   <td colname="col2"> <p> </p> <p> 添加了印度尼西亚语和土耳其语的词根字典。 </p> <p>请参阅<a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" format="dita" scope="local">关于字典</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>导出报表 </p> </td> 
   <td colname="col2"> <p> 
     <!--3683368-->您现在可以从以下报表将数据导出到CSV: 
     <ul id="ul_93B619DBB3444F64BD6D7F9E969AB1E1"> 
      <li id="li_96DDE1A196834845A0FA319903C5934B"> <p>术语报表 </p> </li> 
      <li id="li_4F1A19DE98C84F8CAD963EEA2B38ED7A"> <p>空搜索词报表 </p> </li> 
      <li id="li_A7716C62C4D44CD69D411C3FEE246D96"> <p>搜索请求报表 </p> </li> 
     </ul> </p> <p>请参阅<a href="../c-about-reports-menu/c-about-reports-menu.md#concept_5F901459C7AB461BAB30B305957EB00C" format="dita" scope="local">关于“报告”菜单</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>不要关联 </p> </td> 
   <td colname="col2"> <p>现在，您可以控制不应该在搜索结果中将哪两个词关联在一起，如“运动衫”和“衬衫”。 </p> <p> <p>注意：此功能在默认情况下不启用。请联系 Adobe 客户关怀来激活 Search&amp;Promote 中的此功能，方便您的使用。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**修复**

* 您无法在“推荐”区域中添加当前选定分面标准以外的结果。
* 您无法为具有仅限 HTTPS 搜索的帐户保存基于结果的规则。
* 无法为“不是手机”设置业务规则。

   请参阅[关于Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD)。

* 执行库存过滤搜索不返回结果。
* “大小”分面顺序没有进行更新。
* 向“查询清理”页面添加了用于“自定义”规则定义的选项。

   请参阅[关于查询清理规则](../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C)。

* “术语”报表在数据不足的情况下会重复某些条目。

   请参阅[查看术语报表或空搜索术语报表……](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A)。

* 实时推送单个业务规则在暂存模式下可成功进行，但在实时模式下会失败。
* 针对“包含”或“排除”列表的自动完成编辑内容未保存在“历史记录”中，因此无法还原。

   请参阅[关于自动完成](../c-about-auto-complete.md#concept_093A9CD754864BA79B456FE4BEB64578)。

