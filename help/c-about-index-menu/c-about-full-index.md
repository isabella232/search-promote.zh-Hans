---
description: 您可以使用“完整索引”为分阶段或实时网站的所有页面编制索引。 索引帮助您的客户在执行搜索时更轻松地找到其正在寻找的内容或需要的内容。
solution: Target
subtopic: Full Index
title: 关于完整索引
topic-legacy: Index,Site search and merchandising
uuid: dce1eafd-5aea-4945-8305-8f9e7dc392df
exl-id: cb702bd6-8702-469b-8ce9-0368ccdd55d9
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 1%

---

# 关于完整索引{#about-full-index}

您可以使用“完整索引”为分阶段或实时网站的所有页面编制索引。 索引帮助您的客户在执行搜索时更轻松地找到其正在寻找的内容或需要的内容。

## 使用完整索引{#concept_C69BD21863FD4856B49326F35DB570D3}

生成完整索引时，将显示状态信息，如开始时间、已用时间和索引过程中的错误。 还将显示有关上一个索引状态的信息。

如果更改了需要重新生成索引的帐户设置，则状态可能为“重新生成”。 在重新生成过程中，会应用帐户设置来创建更新的站点索引。

您可以随时停止或重新启动索引编制过程。

为实时网站构建新索引时，客户可以继续使用您的最后一个索引搜索您的网站。 还将显示有关上一个索引状态的信息。

## 设置实时网站{#task_6760F3256D004A228B38968DF15421F0}的完整索引计划

您可以指定要爬网和更新索引的时间和天数。

您选择的时间是根据在“帐户设置”中配置的时区本地的。

请参阅[配置帐户设置](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

Web服务器通常安排在半夜停机进行维护。 如果服务器在计划的索引时间内关闭，则索引创建过程将失败。 请确保您选择了Web服务器可用的一天中的某个时间。

索引计划仅适用于实时索引；无法计划分阶段索引。

**为实时网站设置完整索引计划**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Schedule]**。
1. 在&#x200B;**[!UICONTROL Time]**&#x200B;下拉列表中，选择您希望完整索引到开始的小时。
1. 选择要运行完整索引的一个或多个天。
1. 单击 **[!UICONTROL Save Changes]**.

## 运行实时或分阶段网站{#task_F7FE04D8A1654A7787FCCA31B45EB42D}的完整索引

您可以使用“完整索引”为分阶段或实时网站的所有页面编制索引。 索引帮助您的客户在执行搜索时更轻松地找到其正在寻找的内容或需要的内容。

**运行实时网站或分阶段网站的完整索引**

1. 在“产品”菜单中，执行下列操作之一：

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Index]**.

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Staged Index]**.

1. 设置所需的索引选项。

   <table> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> <p>选项 </p> </th> 
    <th colname="col2" class="entry"> <p>描述 </p> </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>清除索引缓存 </p> </td> 
    <td colname="col2"> <p>从索引缓存中删除所有文档。 </p> <p>选择后，将从您的服务器下载每个网站页面。 如果选中并禁用了此设置，则您的帐户将设置为在每次执行完整索引时清除缓存。 或者，某些以前更改的帐户设置现在需要完整索引。 </p> <p>取消选择后，所有索引页面都将保留在索引中，直到Web服务器显示该页面不再存在为止。 即使删除了指向该页面的链接，情况也是如此。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>重新生成待定 </p> </td> 
    <td colname="col2"> <p>选择如果您对帐户设置进行了更改，而这些设置已对索引的内容进行了实质性更改。 重大变动包括对下列任何一项作出变动： 
    <ul id="ul_4EB8FF692FEB47BBB9A64D61299380D1"> 
    <li id="li_7CF8D286512F4210BEA3DB9F0EFA097A">同义词 </li> 
    <li id="li_8178ABC342BB4365B3927E20433756E3">收藏集 </li> 
    <li id="li_57C8BD06BFA64AFAA2C9EF2CC59520EF">元数据 </li> 
    <li id="li_C4B6A7DA023B4A43991D03EC592170C9">排除的单词 </li> 
    <li id="li_9E0AD4B6DDC24A5A8FB5C2C1CCD5348A">帐户语言 </li> 
    <li id="li_338F107547DF48AAA0EF90F4AD8664A5">排名 </li> 
    <li id="li_7F49B86D94974E79AAD381A64A1400F2">切换区分大小写的搜索 </li> 
    <li id="li_E8FE6EE240A840AC826ADF4294AAC6F6">切换音符支持 </li> 
    <li id="li_51763D482DCB4ED0972966F492B8C0F2">切换数索引 </li> 
    </ul> </p> <p>在进行另一个爬网操作之前，将对所有索引数据进行快速传递，以使其符合新帐户设置。 </p> <p>此选项仅在执行分阶段网站的完整索引时可用。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>计算所有页面 </p> </td> 
    <td colname="col2"> <p>允许搜索网站页面以继续，即使已达到帐户页面限制也是如此。 </p> <p>其他页面不会添加到您的索引中，但您可以确定网站上的文档总数。 </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Full Index Now]**.
1. （可选）如果出现索引错误，请单击&#x200B;**[!UICONTROL View Errors]**&#x200B;以视图关联的日志。

## 查看实时或分阶段网站{#task_02E5E944C56B4EB19CC1FF321F3221B8}的完整索引日志

当实时完整索引或分阶段完整索引完成时，您可以视图其关联日志以排除发生的任何错误。

您无法导出日志，也无法保存它们。 在新索引出现之前，日志仍可供查看。

**视图实时网站或分阶段网站的完整索引日志**

1. 在“产品”菜单中，执行下列操作之一：

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Log]**.

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Staged Log]**.

1. 在日志页面顶部或底部，执行下列任一操作：

   * 使用导航选项&#x200B;**[!UICONTROL First]**、**[!UICONTROL Prev]**、**[!UICONTROL Next]**、**[!UICONTROL Last]**&#x200B;或&#x200B;**[!UICONTROL Go to line]**&#x200B;在日志中移动。

   * 使用显示选项&#x200B;**[!UICONTROL Errors only]**、**[!UICONTROL Wrap line]**&#x200B;或&#x200B;**[!UICONTROL Show]**&#x200B;细化您所看到的内容。
