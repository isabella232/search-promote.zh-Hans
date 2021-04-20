---
description: 您可以使用回滚来备份和存档您生成的网站索引。 您还可以随时恢复索引的备份。
solution: Target
subtopic: Rollback
title: 关于索引的回滚
topic: Index,Site search and merchandising
uuid: abed878a-71b3-4122-9822-7410f4427a9a
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '840'
ht-degree: 0%

---


# 关于索引的回滚{#about-rollback-for-indexes}

可以使用[!DNL Rollback]备份和存档您生成的网站索引。 您还可以随时恢复索引的备份。

## 对索引{#concept_0BC4BC975DB045A986C3607CF32705D8}使用回滚

存档包含四个索引：搜索机器人根据回滚配置设置自动存档的当前站点索引和前三个站点索引。 每次为网站编制索引时，都会更新存档。 较新的索引将替换现有的已存档索引，以便存档始终保持最新。

每个归档索引都列在归档中，并包含以下信息：

* 索引最终确定的日期和时间。
* 索引页面。
* 索引的文档数。
* 索引操作类型（完整、增量等）。
* 索引状态，如索引当前是否处于活动状态，以及在下一个索引之后是否保留或删除它。

每次为您的网站编制索引时，新索引都会添加到存档中，而现有的存档索引也会被删除。 但是，请注意，最早的索引不一定是删除的索引。 在将新索引添加到存档时，会将每个存档索引与在回滚配置设置中指定的页面进行比较。 删除离所需计划最远的索引。 例如，假设配置设置为24、48、72，且保存的索引的年龄为5、23、47和71。 将新索引添加到存档时，将删除最近的索引（使用时间为5小时），因为其使用时间与设置最远。 为方便起见，再次对站点编制索引时将删除索引的存档备注。

在激活索引时，您可以导航到用户界面中的其他区域。 状态指示器会跟踪激活进度，当您视图[!DNL Rollback]页面时，状态指示器可用。 如果恢复了存档的索引，则会在“完整索引”、“增量索引”、“脚本索引”和“重新生成”页面顶部通知用户。 恢复索引时，不能执行索引操作。 如果回滚操作与计划的站点索引冲突，则计划的索引将延迟到回滚完成。 如果索引已经在进行中，则取消该索引，前提是用户确认回滚接收优先级。

如果在爬网过程中发现错误，则搜索机器人不会更新回滚归档文件，以保持归档文件的完整性。 如果用户取消索引操作，也不会进行更新。 如果索引操作超过最长时间、字节、页面或文档,Crawler将完成索引并将其添加到存档。 此外，如果在索引操作期间未满足最小页数，爬网程序将取消该索引，而上一个索引保持活动状态。

## 配置索引{#task_CD403B9AE2244B13A6B3861B5F9B055C}的回滚存档计划

可以使用[!DNL Configure]确定要在回滚归档文件中存储的索引文件。 归档文件可以存储当前索引和三个备份索引。

**[!UICONTROL Schedule]**&#x200B;字段包含三个以逗号分隔的值，它们表示距现在的小时数。 例如，计划值24,48,72指定从现在或昨天开始24小时，从现在或两天前开始48小时，从现在或三天前开始72小时。

搜索会持续存档最接近一天、两天和三天的站点索引。 归档索引的实际时间和日期可能因网站的索引计划而异。

**配置索引的回滚存档计划**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Rollback]** > **[!UICONTROL Configure]**。
1. 在[!DNL Rollback Configuration]页面的&#x200B;**[!UICONTROL Schedule]**&#x200B;字段中，输入一个以小时为单位的三个索引页列表的命令。 将保存最接近这些年龄的索引。
1. 单击 **[!UICONTROL Save Changes]**.

## 激活存档索引{#task_5DCE3D660F6F4197993E92AA59227332}

您可以使用回滚来激活存档的索引。

单击&#x200B;**[!UICONTROL Activate]**&#x200B;回退索引时，当前活动的索引将移入存档。

在激活存档的索引后，您将返回到[!DNL Activate Index]页。 将显示有关索引回滚的信息。 此外，[!DNL Available Indexes]表中的[!DNL Activate]列标识状态为“活动索引”的回滚索引。

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Rollback]** > **[!UICONTROL Rollback]**。
1. 在[!DNL Activate Index]页面的[!DNL Available Indexes]表中，单击&#x200B;**[!UICONTROL Activate]**&#x200B;以获取要激活的关联归档索引类型。

   使用“日期”、“年龄”、“页面”和“操作”列，帮助您确定要激活的索引。
1. 在[!DNL Verify Rollback]页面上，查看索引信息以验证是否选择了正确的索引，然后单击&#x200B;**[!UICONTROL Activate Now]**。

## 查看所有索引回滚的日志{#task_D2D9AA7203F0465FB5AE0D49212AC41C}

视图所有与回滚相关的操作的日期和时间。

**视图所有索引回滚的日志**

1. 在“产品”菜单中，执行下列操作之一：

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Re-Rank Index]** > **[!UICONTROL Live Log]**.

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Re-Rank Index]** > **[!UICONTROL Staged Log]**.

1. 在日志页面顶部或底部，执行下列任一操作：

   * 使用导航选项&#x200B;**[!UICONTROL First]**、**[!UICONTROL Prev]**、**[!UICONTROL Next]**、**[!UICONTROL Last]**&#x200B;或&#x200B;**[!UICONTROL Go to line]**&#x200B;在日志中移动。

   * 使用显示选项&#x200B;**[!UICONTROL Errors only]**、**[!UICONTROL Wrap line]**&#x200B;或&#x200B;**[!UICONTROL Show]**&#x200B;细化您所看到的内容。

