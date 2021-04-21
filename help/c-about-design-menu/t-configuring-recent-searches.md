---
description: “最近搜索”是一个基于cookie的系统，允许您使用演示文稿模板显示客户的最近搜索历史记录。
solution: Target
subtopic: Navigation
title: 配置最近搜索
topic-legacy: Design,Site search and merchandising
uuid: 8ab1b35c-f953-4c26-921f-524af1fea4ef
exl-id: bc6285fa-eaaf-4afb-8ef3-6f1e66cd7090
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 2%

---

# 配置最近搜索{#configuring-recent-searches}

“最近搜索”是一个基于cookie的系统，允许您使用演示文稿模板显示客户的最近搜索历史记录。

您可以使用“最近搜索”页配置搜索行为。

请参阅演示文稿模板标记参考主题，进一步了解可用于在演示文稿模板上显示最近搜索的各种标记。

请参阅[演示文稿模板标签](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)。

**配置最近搜索**

1. 在“项目”菜单中，单击&#x200B;**[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Recent Searches]**。
1. 在[!DNL Recent Searches]页面上，设置所需的选项。

   <!-- 
   
   r_recent_searches_options.xml
   
   -->

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>启用最近搜索 </p> </td> 
      <td colname="col2"> <p> 启用“最近搜索”模块后，将使用传出的搜索结果设置Cookie“vsrecentsearches”。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>要保存的搜索数 </p> </td> 
      <td colname="col2"> <p>配置要在Cookie中保存的搜索数。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>过期 </p> </td> 
      <td colname="col2"> <p>指定Cookie的过期时间。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。
