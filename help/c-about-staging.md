---
description: 通过暂存，您可以测试和预览对设置和配置的更改，而不会影响实时索引。
solution: Target
title: 关于暂存
topic-legacy: Staging,Site search and merchandising
uuid: 2e5889a6-2e9c-4ac7-9d6e-d35e7cafda5b
exl-id: 61f254b7-4dc1-4a5e-a22e-94763f140c50
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '959'
ht-degree: 0%

---

# 关于暂存{#about-staging}

通过暂存，您可以测试和预览对设置和配置的更改，而不会影响实时索引。

## 关于暂存{#concept_08B8F3CA1F4241108F14BA7FC7806CA7}

通过暂存，您可以测试和预览对设置和配置的更改，而不会影响实时索引。

另请参阅[元素ID:context_A5783D07C72042EC8886F300FFF62C50](c-about-simulator.md#context_A5783D07C72042EC8886F300FFF62C50)。

具有暂存选项&#x200B;**[!UICONTROL Push All Live]**&#x200B;或&#x200B;**[!UICONTROL View Live Settings]**&#x200B;的任何页面都表示可以暂存该页面上的所有设置。 索引中的网页除外。 此区域中的页面显式用于分阶索引或实时索引，以便您直接独立控制两个索引。

您几乎可以存放任何内容，包括索引。 某些例外包括帐户特定设置，这些设置会同时影响暂存和实时环境以及索引操作的计划。 默认情况下，当您保存对可暂存的设置所做的任何更改时，系统会自动暂存该设置。

当&#x200B;**[!UICONTROL Push All Live]**&#x200B;或&#x200B;**[!UICONTROL View Lives Settings]**&#x200B;选项未启用（灰显）时，表示该页面上的暂存设置与实时设置相同。

对于已暂存的项目，请注意，设置的实时版本为只读；只能通过实时推送暂存设置来操纵它。

## 关于已分阶段页面的历史记录{#section_5BE780AFF26A450A9EFF4000DE53531B}

大多数分阶段设置在页面的右上角区域具有[!DNL History]选项。 单击&#x200B;**[!UICONTROL History]**&#x200B;后，您可以还原最近对已打开的特定分阶段页面所做的任何更改。

您还可以视图更改日志，以查找历史记录的替代视图。 每次应用更改时，都会创建基础数据文件的备份版本。 “更改日志”显示每个此类修订，显示版本号、执行更改的用户的电子邮件地址以及备份的日期。 具有粗体版本值的条目表示当前版本。

请参阅[查看更改日志](c-about-reports-menu/c-about-reports-menu.md#task_166F1156719F4B3D834BEA8E249C8057)。

## “管理舞台 — 实时设置”页{#section_E72B8CAF516345A5B6B6783CF6E512EE}

除了直接在给定页面中提供&#x200B;**[!UICONTROL Push All Live]**&#x200B;和&#x200B;**[!UICONTROL View Live Settings]**&#x200B;选项外，您还可以使用&#x200B;**[!UICONTROL Manage Stage-Live Settings]**&#x200B;页面执行相同的操作。 **[!UICONTROL Manage Stage-Live Settings]**&#x200B;页面（可从主产品菜单中访问）是一个中心位置，它显示了帐户中当前已暂存的所有设置。 您可以实时推送所有设置，仅实时推送选定设置，也可以删除设置。 但是，作为最佳实践，始终将所有暂存项目实时推送以避免任何相互依赖问题。

页面上的设置将分组为类别。 您可以展开每个类别以显示要暂存的页面设置。 当前，在舞台管理器中不跟踪依赖项。 因此，建议您将除索引外的所有内容同时上线。

您可以实时推送分阶段索引。 请确保首先检查您的分阶段索引是否过时或已损坏。 如果您犯了错误并将分阶段发布的索引实时推送，则可以回退旧的实时索引。 实时推送分阶段索引通常需要不到30秒。

## 测试分阶段设置或索引{#section_6800E52D20854A779946EAB600801F12}

在支持测试控件的页面上，可以根据分阶段设置或实时设置进行测试。 视图分阶设置时，分阶设置将用于测试。 同样，在查看实时设置时，测试会使用实时设置。 在“模板”部分中，将针对索引的分阶段版本执行所有测试。 要搜索分阶段索引，请将`sp_staged` CGI参数设置为等于1。 反过来，这表示您希望使用分阶段索引。 如果分阶段的索引不存在，则会搜索您的实时索引，并根据需要应用任何分阶段的搜索时间设置。

另请参阅[后端搜索CGI参数](c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。

## 查看实时设置{#task_401A0EBDB5DB4D4CA933CBA7BECDC10F}

您可以从任何分阶段页面查看设置的实时版本。

<!-- 

t_viewing_live_settings.xml

 -->

如果&#x200B;**[!UICONTROL View Live Settings]**&#x200B;选项未启用（灰显），则表示该页面的舞台设置和实时设置已同步。

**视图实时设置**

1. 在具有暂存设置的任何页面上，单击&#x200B;**[!UICONTROL View Live Settings]**&#x200B;查看设置的实时版本。
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL View]**&#x200B;可查看为分阶段设置选择的当前选项。
   * 单击&#x200B;**[!UICONTROL View Stage Settings]**&#x200B;可返回到可在其中编辑或删除设置的分阶段设置。

## 实时推送舞台设置{#task_44306783B4C0408AAA58B471DAF2D9A4}

您可以从任何分阶段页面视图或从中心&#x200B;**[!UICONTROL Manage Stage-Live Settings]**&#x200B;页面实时推送设置。

<!-- 

t_pushing_live_settings_live.xml

 -->

在页面上启用&#x200B;**[!UICONTROL Push Live]**&#x200B;选项（不灰显）时，表示存在已暂存的设置。 或者，这意味着设置具有编辑，并且保存后，设置将变为暂存状态。 单击此选项时，所有未保存的编辑都将保存到暂存区域。 如果没有待定的编辑，则页面的设置将立即实时推送。

**要实时推送分阶段设置**

1. 执行以下操作之一：

   * 在选择“已暂存”作为视图的任何页面上，单击&#x200B;**[!UICONTROL Push Live]**。
   * 在产品菜单上，单击&#x200B;**[!UICONTROL Staging]**。 在&#x200B;**[!UICONTROL Manage Stage-Live Settings]**&#x200B;页面上，执行以下操作之一：

   * 使用设置树可以仅检查要实时推送的设置，然后单击&#x200B;**[!UICONTROL Push Selected Live]**。
   * 单击 **[!UICONTROL Push All Live]**.

## 从中心位置{#task_B72BEA9269704B1399600A9CA273369B}删除舞台实时设置

如果您有许多要删除的设置，则可以使用&#x200B;**[!UICONTROL Manage Stage-Live Settings]**&#x200B;页面从一个中心位置删除设置。

<!-- 

t_deleting_staged_settings_from_a_central_location.xml

 -->

**警告**:单击时， **[!UICONTROL Delete Selected]**&#x200B;所有选中的设置将立即删除；没有确认对话框来验证您是否确实要删除选定的设置。此外，没有与页面关联的历史记录功能。 因此，您无法撤消删除操作。

**从中心位置删除舞台实时设置**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Staging]**。
1. 在&#x200B;**[!UICONTROL Manage Stage-Live Settings]**&#x200B;页面上，使用设置树可以仅检查要删除的设置。
1. 单击 **[!UICONTROL Delete Selected]**.
