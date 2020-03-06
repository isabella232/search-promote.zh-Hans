---
description: 通过分阶段，您可以测试和预览对设置和配置所做的更改，而不会影响实时索引。
seo-description: 通过分阶段，您可以测试和预览对设置和配置所做的更改，而不会影响实时索引。
seo-title: 关于暂存
solution: Target
title: 关于暂存
topic: Staging,Site search and merchandising
uuid: 2e5889a6-2e9c-4ac7-9d6e-d35e7cafda5b
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# 关于暂存{#about-staging}

通过分阶段，您可以测试和预览对设置和配置所做的更改，而不会影响实时索引。

## 关于暂存 {#concept_08B8F3CA1F4241108F14BA7FC7806CA7}

通过分阶段，您可以测试和预览对设置和配置所做的更改，而不会影响实时索引。

另请参 [阅元素ID:context_A5783D07C72042EC8886F300FFF62C50](c-about-simulator.md#context_A5783D07C72042EC8886F300FFF62C50)。

具有暂存选项的任何页 **[!UICONTROL Push All Live]** 面， **[!UICONTROL View Live Settings]** 或表示可以暂存该页面上的所有设置。 索引中的网页除外。 此区域中的页面显式用于分阶段索引或实时索引，以便您直接独立控制两个索引。

您几乎可以暂存包括索引在内的任何内容。 一些例外包括帐户特定设置，这些设置同时影响分阶段环境和实时环境以及索引操作的计划。 默认情况下，在保存对可暂存的设置所做的任何更改时，该设置将自动暂存。

当或 **[!UICONTROL Push All Live]** 选项未 **[!UICONTROL View Lives Settings]** 启用（灰显）时，这意味着该页面上的暂存设置与实时设置相同。

对于已暂存的项目，请注意设置的实时版本是只读的；只能通过实时推送暂存设置来操纵它。

## 关于已分阶段页面的历史记录 {#section_5BE780AFF26A450A9EFF4000DE53531B}

大多数分阶段设 [!DNL History] 置在页面的右上角区域有一个选项。 单击时， **[!UICONTROL History]**&#x200B;它允许您还原最近对已打开的特定分阶段页面所做的任何更改。

您还可以查看更改日志以查看替代历史记录视图。 每次应用更改时，都会创建基础数据文件的备份版本。 “更改日志”显示每个此类修订，其中显示版本号、执行更改的用户的电子邮件地址以及进行备份的日期。 带有粗体版本值的条目表示当前版本。

See [Viewing the Change Log](c-about-reports-menu/c-about-reports-menu.md#task_166F1156719F4B3D834BEA8E249C8057).

## “管理舞台——实时设置”页 {#section_E72B8CAF516345A5B6B6783CF6E512EE}

除了直接在 **[!UICONTROL Push All Live]** 给定页 **[!UICONTROL View Live Settings]** 面中提供和选项外，您还可以使用该页面 **[!UICONTROL Manage Stage-Live Settings]** 执行相同的操作。 主 **[!UICONTROL Manage Stage-Live Settings]** 产品菜单中提供的页面是一个中心位置，它显示了帐户中当前已暂存的所有设置。 您可以实时推送所有设置，仅可以实时推送选定设置，也可以删除设置。 但是，作为最佳实践，始终将所有分阶段的项目实时推送，以避免任何相互依赖问题。

页面上的设置被分为几个类别。 您可以展开每个类别以显示要暂存的页面设置。 当前，不在舞台管理器中跟踪依赖项。 因此，建议您同时将除索引之外的所有内容推送到活动状态。

您可以实时推送分阶段索引。 请确保首先检查您的分阶段索引是否陈旧或损坏。 如果您犯了错误并将分阶段发布的索引上线，则可以回滚旧的实时索引。 实时推送分阶段索引通常需要不到30秒。

## 测试分阶段设置或索引 {#section_6800E52D20854A779946EAB600801F12}

在支持测试控件的页面上，可以根据分阶段或实时设置进行测试。 查看分阶段设置时，将使用分阶段设置进行测试。 同样，当您查看实时设置时，测试会使用实时设置。 在“模板”部分中，将针对索引的分阶段版本执行所有测试。 要搜索分阶段索引，请将 `sp_staged` CGI参数设置为等于1。 反过来，这表示您希望使用分阶段索引。 如果暂存索引不存在，则会搜索您的实时索引，并根据需要应用任何暂存搜索时间设置。

另请参阅后 [端搜索CGI参数](c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。

## 查看实时设置 {#task_401A0EBDB5DB4D4CA933CBA7BECDC10F}

您可以从任何分阶段页面查看设置的实时版本。

<!-- 

t_viewing_live_settings.xml

 -->

如果选 **[!UICONTROL View Live Settings]** 项未启用（灰显），则表示该页面的舞台设置和实时设置已同步。

**查看实时设置**

1. 在具有暂存设置的任何页面上， **[!UICONTROL View Live Settings]** 单击可查看设置的实时版本。
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL View]** 可查看为分阶段设置选择的当前选项。
   * 单 **[!UICONTROL View Stage Settings]** 击以返回到分阶段设置，在该设置中可以编辑或删除设置。

## 实时推送舞台设置 {#task_44306783B4C0408AAA58B471DAF2D9A4}

您可以从任何分阶段的页面视图或中心页面实时推送 **[!UICONTROL Manage Stage-Live Settings]** 设置。

<!-- 

t_pushing_live_settings_live.xml

 -->

在页 **[!UICONTROL Push Live]** 面上启用（不灰显）此选项时，表示存在已暂存的设置。 或者，这意味着某个设置具有编辑，并且保存后，该设置将变为暂存状态。 单击此选项时，所有未保存的编辑都将保存到暂存区域。 如果没有待定编辑，则页面设置将立即实时推送。

**要实时推送分阶段设置，请执行以下操作：**

1. 执行以下操作之一：

   * 在选择“已暂存”作为“视图”的任何页面上，单击 **[!UICONTROL Push Live]**。
   * 在产品菜单中，单击 **[!UICONTROL Staging]**。 在页 **[!UICONTROL Manage Stage-Live Settings]** 面上，执行下列操作之一：

   * 使用设置树可仅检查要实时推送的设置，然后单击 **[!UICONTROL Push Selected Live]**。
   * 单击 **[!UICONTROL Push All Live]**.

## 从中心位置删除舞台实时设置 {#task_B72BEA9269704B1399600A9CA273369B}

如果您有许多要删除的设置，则可以使用页 **[!UICONTROL Manage Stage-Live Settings]** 面从一个中心位置删除设置。

<!-- 

t_deleting_staged_settings_from_a_central_location.xml

 -->

**警告**:单击时， **[!UICONTROL Delete Selected]**&#x200B;所有选中的设置都会立即删除；没有确认对话框来确认您确实要删除选定的设置。 此外，没有与页面关联的历史记录功能。 因此，您无法撤消删除操作。

**从中心位置删除舞台实时设置**

1. 在产品菜单中，单击 **[!UICONTROL Staging]**。
1. 在页 **[!UICONTROL Manage Stage-Live Settings]** 面上，使用设置树可仅检查要删除的设置。
1. 单击 **[!UICONTROL Delete Selected]**.
