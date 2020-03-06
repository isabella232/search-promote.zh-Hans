---
description: 您可以使用完整索引为分阶段或实时网站的所有页面编制索引。 索引帮助您的客户在执行搜索时更轻松地找到他们正在寻找的内容或他们需要的内容。
seo-description: 您可以使用完整索引为分阶段或实时网站的所有页面编制索引。 索引帮助您的客户在执行搜索时更轻松地找到他们正在寻找的内容或他们需要的内容。
seo-title: 关于完整索引
solution: Target
subtopic: Full Index
title: 关于完整索引
topic: Index,Site search and merchandising
uuid: dce1eafd-5aea-4945-8305-8f9e7dc392df
translation-type: tm+mt
source-git-commit: 7af85dd37f06fe506e5f57e28a25385ca7ab3db5

---


# 关于完整索引{#about-full-index}

您可以使用完整索引为分阶段或实时网站的所有页面编制索引。 索引帮助您的客户在执行搜索时更轻松地找到他们正在寻找的内容或他们需要的内容。

## 使用完整索引 {#concept_C69BD21863FD4856B49326F35DB570D3}

生成完整索引时，将显示状态信息，如开始时间、已用时间和索引过程中的错误。 还会显示有关上一个索引状态的信息。

如果您更改了需要重新生成索引的帐户设置，则状态可能为“重新生成”。 在重新生成过程中，会应用帐户设置来创建更新的站点索引。

您可以随时停止或重新开始索引创建过程。

虽然新索引是为实时网站构建的，但客户可以使用您的最后一个索引继续搜索您的网站。 还会显示有关上一个索引状态的信息。

## 为实时网站设置完整索引计划 {#task_6760F3256D004A228B38968DF15421F0}

您可以指定要搜索网站和更新索引的时间和天数。

您选择的时间是根据帐户设置中配置的时区所在的本地时间。

请参 [阅配置帐户设置](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

Web服务器通常安排在半夜停工进行维护。 如果服务器在计划的索引时间内关闭，则索引构建过程将失败。 请确保选择一天中Web服务器可用的时间。

索引计划仅适用于您的实时索引；无法计划分阶段的索引。

**为实时网站设置完整索引计划的步骤**

1. 在产品菜单中，单击 **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Schedule]**。
1. 在下 **[!UICONTROL Time]** 拉列表中，选择您希望开始构建完整索引的小时数。
1. 选择要运行完整索引的一天或多天。
1. 单击 **[!UICONTROL Save Changes]**.

## 运行实时网站或分阶段网站的完整索引 {#task_F7FE04D8A1654A7787FCCA31B45EB42D}

您可以使用完整索引为分阶段或实时网站的所有页面编制索引。 索引帮助您的客户在执行搜索时更轻松地找到他们正在寻找的内容或他们需要的内容。

**运行实时网站或分阶段网站的完整索引**

1. 在产品菜单中，执行下列操作之一：

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Index]**.

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Staged Index]**.

1. 设置所需的索引设置选项。

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
    <td colname="col2"> <p>从索引缓存中删除所有文档。 </p> <p>选择后，将从服务器下载每个网站页面。 如果选中并禁用了此设置，则帐户将设置为在每次执行完整索引时清除缓存。 或者，某些以前更改的帐户设置现在需要完整索引。 </p> <p>取消选择后，所有已索引的页面都会保留在索引中，直到Web服务器显示该页面不再存在。 即使删除了指向该页面的链接，这种情况也是正确的。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>重新生成待定 </p> </td> 
    <td colname="col2"> <p>选择如果您对帐户设置进行了更改，而这些设置已对索引的内容进行了实质性更改。 重大变动包括对下列任一项目作出变动： 
    <ul id="ul_4EB8FF692FEB47BBB9A64D61299380D1"> 
    <li id="li_7CF8D286512F4210BEA3DB9F0EFA097A">同义词 </li> 
    <li id="li_8178ABC342BB4365B3927E20433756E3">收藏集 </li> 
    <li id="li_57C8BD06BFA64AFAA2C9EF2CC59520EF">元数据 </li> 
    <li id="li_C4B6A7DA023B4A43991D03EC592170C9">排除的单词 </li> 
    <li id="li_9E0AD4B6DDC24A5A8FB5C2C1CCD5348A">帐户语言 </li> 
    <li id="li_338F107547DF48AAA0EF90F4AD8664A5">排名 </li> 
    <li id="li_7F49B86D94974E79AAD381A64A1400F2">切换区分大小写的搜索 </li> 
    <li id="li_E8FE6EE240A840AC826ADF4294AAC6F6">切换变音支持 </li> 
    <li id="li_51763D482DCB4ED0972966F492B8C0F2">切换数索引 </li> 
    </ul> </p> <p>在进行另一个爬行操作之前，会通过所有索引数据进行快速传递，以使其符合新帐户设置。 </p> <p>仅当您对已分阶段的网站执行完整索引时，此选项才可用。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>计算所有页面 </p> </td> 
    <td colname="col2"> <p>允许继续搜索网站页面，即使您已达到帐户页面限制也是如此。 </p> <p>其他页面不会添加到索引中，但您可以确定网站上的文档总数。 </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Full Index Now]**.
1. （可选）如果出现索引错误，请单 **[!UICONTROL View Errors]** 击以查看关联的日志。

## 查看实时网站或分阶段网站的完整索引日志 {#task_02E5E944C56B4EB19CC1FF321F3221B8}

当实时完整索引或分阶段完整索引完成时，您可以查看其关联的日志来排除发生的任何错误。

您无法导出日志，也无法保存它们。 新索引出现之前，日志一直可供查看。

**查看实时网站或分阶段网站的完整索引日志**

1. 在产品菜单中，执行下列操作之一：

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Log]**.

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Staged Log]**.

1. 在日志页面顶部或底部，执行下列任一操作：

   * 使用导航选 **[!UICONTROL First]**&#x200B;项、 **[!UICONTROL Prev]**、 **[!UICONTROL Next]**、 **[!UICONTROL Last]**&#x200B;或 **[!UICONTROL Go to line]** 在日志中移动。

   * 使用显示选 **[!UICONTROL Errors only]**&#x200B;项 **[!UICONTROL Wrap line]**&#x200B;或 **[!UICONTROL Show]** 优化您看到的内容。

