---
description: 您可以使用回滚来备份和存档您生成的网站索引。 您还可以随时恢复索引的备份。
seo-description: 您可以使用回滚来备份和存档您生成的网站索引。 您还可以随时恢复索引的备份。
seo-title: 关于索引的回滚
solution: Target
subtopic: Rollback
title: 关于索引的回滚
topic: Index,Site search and merchandising
uuid: abed878a-71b3-4122-9822-7410f4427a9a
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a

---


# 关于索引的回滚{#about-rollback-for-indexes}

您可以使用 [!DNL Rollback] 备份和存档您生成的网站索引。 您还可以随时恢复索引的备份。

## 对索引使用回滚 {#concept_0BC4BC975DB045A986C3607CF32705D8}

存档包含四个索引：搜索机器人根据回滚配置设置自动存档的当前站点索引和三个以前的站点索引。 每次为网站编制索引时，都会更新存档。 较新的索引将替换现有的已存档索引，以便存档始终保持最新。

存档中列出的每个存档索引都包含以下信息：

* 最终确定索引的日期和时间。
* 索引年龄。
* 索引的文档数。
* 索引操作类型（完整、增量等）。
* 索引状态，如索引当前是否处于活动状态，以及在下一个索引之后是否将保留或删除它。

每次为网站编制索引时，新索引都会添加到存档中，并删除现有的存档索引。 但是，请注意，最早的索引不一定是删除的索引。 将新索引添加到存档时，会将每个存档索引与回滚配置设置中指定的年龄进行比较。 删除离所需计划最远的索引。 例如，假定配置设置为24,48,72，且保存的索引的年限为5、23、47和71。 当将新索引添加到存档时，将删除最近的索引（使用时间为5小时），因为其年龄与设置最远。 为了方便起见，再次索引站点时将删除哪个索引的存档备注。

在激活索引时，您可以导航到用户界面中的其他区域。 状态指示器会跟踪激活进度，并在您查看页面时可 [!DNL Rollback] 用。 如果恢复了存档的索引，则会在“完整索引”、“增量索引”、“脚本索引”和“重新生成”页面的顶部通知用户。 在恢复索引时，不能执行索引操作。 如果回滚操作与计划的站点索引发生冲突，则将延迟计划的索引编制，直到回滚完成。 如果索引已在进行中，则取消该索引，前提是用户确认回滚接收优先级。

为了保持存档的完整性，如果在爬行过程中发现错误，则搜索自动机不更新回滚存档。 如果用户取消索引操作，也不会进行更新。 如果索引操作超过了最长时间、字节、页面或文档，Crawler将完成索引并将其添加到存档。 此外，如果在索引操作期间未满足最小页数，Crawler将取消索引，而上一个索引将保持活动状态。

## 配置索引的回滚存档计划 {#task_CD403B9AE2244B13A6B3861B5F9B055C}

您可以使 [!DNL Configure] 用来确定要在回滚归档文件中存储的索引文件。 存档文件可以存储当前索引和三个备份索引。

该字 **[!UICONTROL Schedule]** 段包含三个以逗号分隔的值，这些值表示离现在只有几小时。 例如，计划值24,48,72指定从现在或昨天起24小时，从现在或两天前起48小时，从现在或三天前起72小时。

“搜索”会持续存档最接近一天、两天和三天的站点索引。 存档索引的实际时间和日期可能因网站的索引计划而异。

**配置索引的回滚存档计划**

1. 在产品菜单中，单击 **[!UICONTROL Index]** > **[!UICONTROL Rollback]** > **[!UICONTROL Configure]**。
1. 在页 [!DNL Rollback Configuration] 面的字段中，输 **[!UICONTROL Schedule]** 入一个以小时为单位、由三个索引页面组成的单独的命令列表。 将保存最接近这些年龄的索引。
1. 单击 **[!UICONTROL Save Changes]**.

## 激活存档索引 {#task_5DCE3D660F6F4197993E92AA59227332}

可以使用回滚来激活存档的索引。

单击以 **[!UICONTROL Activate]** 回滚索引时，当前活动的索引将移入存档。

激活存档的索引后，您将返回到页 [!DNL Activate Index] 面。 此时将显示有关索引回滚的信息。 此外，表 [!DNL Activate] 中的列标 [!DNL Available Indexes] 识状态为“活动索引”的回滚索引。

1. 在产品菜单中，单击 **[!UICONTROL Index]** > **[!UICONTROL Rollback]** > **[!UICONTROL Rollback]**。
1. 在页 [!DNL Activate Index] 面的表中，单 [!DNL Available Indexes] 击以获取 **[!UICONTROL Activate]** 要激活的关联存档索引类型。

   使用“日期”、“年龄”、“页面”和“操作”列，帮助您确定要激活的索引。
1. 在页面 [!DNL Verify Rollback] 上，查看索引信息以验证您是否选择了正确的索引，然后单击 **[!UICONTROL Activate Now]**。

## 查看所有索引回滚的日志 {#task_D2D9AA7203F0465FB5AE0D49212AC41C}

查看所有回滚相关操作的日期和时间。

**查看所有索引回滚的日志**

1. 在产品菜单中，执行下列操作之一：

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Re-Rank Index]** > **[!UICONTROL Live Log]**.

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Re-Rank Index]** > **[!UICONTROL Staged Log]**.

1. 在日志页面顶部或底部，执行下列任一操作：

   * 使用导航选 **[!UICONTROL First]**&#x200B;项、 **[!UICONTROL Prev]**、 **[!UICONTROL Next]**、 **[!UICONTROL Last]**&#x200B;或 **[!UICONTROL Go to line]** 在日志中移动。

   * 使用显示选 **[!UICONTROL Errors only]**&#x200B;项 **[!UICONTROL Wrap line]**&#x200B;或 **[!UICONTROL Show]** 优化您看到的内容。

