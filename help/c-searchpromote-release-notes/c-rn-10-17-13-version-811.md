---
description: 'null'
seo-description: 'null'
seo-title: Search&amp;Promote 8.11.0发行说明(10/29/2013)
solution: Target
title: Search&amp;Promote 8.11.0发行说明(10/29/2013)
topic: Release Notes,Site search and merchandising
uuid: 973f9608-a5c7-4571-ae2b-6f1fa05bc862
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 58%

---


# Search&amp;Promote8.11.0发行说明(10/29/2013){#search-promote-release-notes}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>新功能 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 丹麦语单词拆分 </p> </td> 
   <td colname="col2"> <p> 现在提供了一种机制，允许<span class="keyword">AdobeSearch&amp;Promote</span>访问由Adobe提供的语言（丹麦语）检测、反编译、词干和分段服务。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**功能增强和问题修复**

* 对现有[!DNL Search&Promote]表匹配功能进行了增强。 此增强功能可以更好地支持客户的相关需求，提供 SKU 和产品数据间更复杂的关系。

   >[!NOTE]
   >
   >默认情况下，此功能未启用。 请联系 Adobe 客户关怀来激活 Search&amp;Promote 中的此功能，方便您的使用。

* 增加了一个选项，允许“引导式搜索”使用帐户的语言设置对页面进行排序。

   >[!NOTE]
   默认情况下，此功能未启用。 请联系 Adobe 客户关怀来激活 Search&amp;Promote 中的此功能，方便您的使用。

* 增加了一个选项，以增加用户可以为多个页面指定的页面值的数量。

   >[!NOTE]
   默认情况下，此功能未启用。 请联系 Adobe 客户关怀来激活 Search&amp;Promote 中的此功能，方便您的使用。

* 将复选框选项&#x200B;**[!UICONTROL Only allow searches that use HTTPS]**&#x200B;添加到&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Restrictions]**。

   请参阅[关于限制](../c-about-settings-menu/c-about-searching-menu.md#concept_B5B527E04EBF4E9AB5956EEF881DDBF1)。

* 在向导的&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]** > **[!UICONTROL Create Feed]** > **[!UICONTROL Generic Feed]**&#x200B;中添加了一个选项，以保留向导的[!DNL File Submission]面板中的制表符字符。

   请参阅[创建源](../c-about-settings-menu/c-about-searching-menu.md#task_63179C1FC359497483CD6CE13FD1C250)。

* 对于新的平面定义表单，将每个顶部和底部字段中可接受的数据大小从 80 个字符提高到 1000 个。

   请参阅[关于Facet](../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5)。

* 向导式搜索调试参数现在可以正确报告业务规则编号。
* 业务规则现在应用于实时环境。
* 对于“语言”配置为“丹麦语（丹麦）”的帐户，当按经度/纬度执行搜索时，“近似”搜索现在可以正常使用。
* 对于基于结果的触发器，现在没有预订也可以触发。
* 现在，使用&#x200B;**[!UICONTROL Linguistics]** > **[!UICONTROL Words & Language]**&#x200B;中的&#x200B;**[!UICONTROL Ignore Apostrophes]**&#x200B;选项时，会报告一致的结果。

   请参阅[关于单词和语言](../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79)。

* 自动完成单词列表用户界面现在可以在大量页面上工作。

