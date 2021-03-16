---
description: 使用“我的用户档案”菜单设置个人信息、首选项、登录口令和视图访问权限。
solution: Target
subtopic: My Profile
title: 关于“我的用户档案”菜单
topic: 设置、网站搜索和销售
uuid: 6a0a4e57-59fa-48fb-b712-eb16a9f47c3a
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1055'
ht-degree: 0%

---


# 关于“我的用户档案”菜单{#about-the-my-profile-menu}

使用“我的用户档案”菜单设置个人信息、首选项、登录口令和视图访问权限。

## 配置您的个人用户信息{#task_A11A3BE2527B4204B896E04303B04AA6}

您可以视图和管理与您的帐户关联的个人用户信息，包括设置所需的电子邮件地址以及大多数网站页面所使用的字符编码。

您选择的字符编码将应用于帐户中的网页，只要它们不指定meta标签中的覆盖字符集编码。 字符编码也应用于帐户配置页。 默认值为“西欧(ISO-8859-1)”。

在指定电子邮件地址时，它只能包含ASCII字符。 使用标准字母(a..z)字符或数字`(0..9)`字符，只有一个`@`字符，用于将用户名与域分开。 字符`_`、`+`、`-`、`.`、`!`、`#`、`$`、`'`、`%`、`&`、`*`、`=`、`?`、`^`、还允许a14/>和`}`。 `{`您的电子邮件地址不能开始为句点(`.`)字符。

请参阅[配置首选项](../c-about-settings-menu/c-about-my-profile-menu.md#task_5E06BF565C284C2EBBE18E10A1C4BFBB)。

请参阅[更改登录密码](../c-about-settings-menu/c-about-my-profile-menu.md#task_F5FF13AAD1514FE997C8882D4537C0C9)

请参阅[取消登录](../c-about-settings-menu/c-about-my-profile-menu.md#task_D57701BB726243B08CEA14EEC86C3087)。

请参阅[查看您的访问权限](../c-about-settings-menu/c-about-my-profile-menu.md#task_6107C5BA333B4053A56325AE5E3A1848)。

**配置您的个人用户信息**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]**。
1. 在[!DNL Personal Information]页面上，指定所需的字段。

   只有[!DNL Email Address]字段是必填字段。
1. 单击 **[!UICONTROL Save Changes]**.

## 配置您的首选项{#task_5E06BF565C284C2EBBE18E10A1C4BFBB}

您可以配置特定于用户界面的首选项。

例如，您可以设置您希望用作默认规则生成器用户界面的首选项。 或者，您可以选择在保存时验证模板标签属性，或在保存时验证对导向搜索对象的模板引用。

请参阅[配置您的个人用户信息](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6)。

请参阅[更改登录密码](../c-about-settings-menu/c-about-my-profile-menu.md#task_F5FF13AAD1514FE997C8882D4537C0C9)

请参阅[取消登录](../c-about-settings-menu/c-about-my-profile-menu.md#task_D57701BB726243B08CEA14EEC86C3087)。

请参阅[查看您的访问权限](../c-about-settings-menu/c-about-my-profile-menu.md#task_6107C5BA333B4053A56325AE5E3A1848)。

请参阅[关于Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD)。

请参阅[关于模板](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5)。

**配置首选项**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL My Preferences]**。
1. 在[!DNL My Preferences]页面上，设置所需的字段。

   | 选项 | 描述 |
   |--- |--- |
   | 规则生成器首选项 | 允许您选择在构建新业务规则时要使用的默认用户界面。 您可以选择简化的可视界面来快速创建规则，也可以选择高级选项界面来为您提供更大的控制和灵活性。  默认首选项为Visual。 在构建业务规则时，您仍然可以在使用可视界面或高级界面之间切换，而不管您设置了规则生成器首选项。 |
   | 在保存时验证模板标签属性 | 在模板编辑器中保存模板时，验证&lt;guided-*和&lt;search-*>中的所有属性。  请参阅[编辑演示文稿或传输模板](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3)。 |
   | 在保存时验证对GS对象的模板引用 | 检查“向导搜索”对象（如&lt;向导 — *>标签中引用的菜单、彩块化、痕迹导航、自定义变量和模板）是否存在。 |

1. 单击&#x200B;**保存更改**。

## 更改登录密码{#task_F5FF13AAD1514FE997C8882D4537C0C9}

您可以更改用于登录的口令。 首次使用的用户会自动分配密码。

如果您丢失或忘记了密码，请单击登录页面上的&#x200B;**[!UICONTROL Forgot your password?]**，然后按照说明生成新密码。

以下规则和限制适用于帐户密码：

* 密码区分大小写。
* 最小8个字符，最大20个字符。
* 必须至少包含一个字母和一个数字。
* 允许所有ASCII文本字符，但`"@"`符号除外。
* 允许使用空格（删除前导空格）。
* 不允许使用词典词。

请参阅[配置您的个人用户信息](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6)。

请参阅[配置首选项](../c-about-settings-menu/c-about-my-profile-menu.md#task_5E06BF565C284C2EBBE18E10A1C4BFBB)。

请参阅[取消登录](../c-about-settings-menu/c-about-my-profile-menu.md#task_D57701BB726243B08CEA14EEC86C3087)。

请参阅[查看您的访问权限](../c-about-settings-menu/c-about-my-profile-menu.md#task_6107C5BA333B4053A56325AE5E3A1848)。

**更改登录密码**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Password]**。
1. 在[!DNL Change Password]页面的[!DNL Current Password]字段中，键入您使用的当前登录密码。
1. 在[!DNL New Password]字段和[!DNL New Password (again)]字段中，键入要使用的新登录密码。
1. 单击&#x200B;**保存更改**。

## 取消登录{#task_D57701BB726243B08CEA14EEC86C3087}

您可以选择取消Adobe登录。 如果取消登录，则您无法通过显示的登录电子邮件访问此帐户或任何其他Adobe帐户。

作为帐户所有者，在取消登录之前，请将帐户所有权转移给其他有效帐户用户。 完成此操作后，您可以像任何其他帐户用户一样取消登录。

请参阅[将帐户所有权转移给其他帐户用户](../c-about-settings-menu/c-about-account-options-menu.md#task_47E3C66CC6374274830DA10171E0CF17)。

请参阅[从帐户](../c-about-settings-menu/c-about-account-options-menu.md#task_C56F5AB87B664BAAAC2FD2F15003E73F)中删除您自己。

请参阅[删除帐户](../c-about-settings-menu/c-about-account-options-menu.md#task_975178D5B9444BF8B52D72B897A49C32)。

**取消登录**

1. 将帐户所有权转移给其他帐户用户。

   请参阅[将帐户所有权转移给其他帐户用户](../c-about-settings-menu/c-about-account-options-menu.md#task_47E3C66CC6374274830DA10171E0CF17)。
1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Cancel]**。
1. 在[!DNL Cancel Login]页面上，单击&#x200B;**[!UICONTROL Cancel Login]**。
1. 单击&#x200B;**[!UICONTROL Yes]**&#x200B;确认取消。

## 查看您的访问权限{#task_6107C5BA333B4053A56325AE5E3A1848}

使用“我的访问权限”，您可以使用角色限制对页面的访问或删除很少使用的页面。 访问权限显示您属于哪些角色（如果有）。 如果您当前未分配给一个或多个角色，则您具有完全无限制的访问权限。

树视图显示成员中心中可以限制的页面，以及您当前是否有权访问由复选标记表示的该页面。

请参阅[向帐户添加新角色](../c-about-settings-menu/c-about-users-menu.md#task_E148D02275DE4F899BA79736A29895AB)。

请参阅[查看帐户](../c-about-settings-menu/c-about-users-menu.md#task_4EAE1D018F384691A083AD51E5CE58DC)中存在的角色。

树视图中的权限&#x200B;**[!UICONTROL Can push live]**&#x200B;是一个特殊控件，它授予该角色中的任何用户实时推送任何暂存项目的能力。 通过创建不具有此功能的角色，您可以确保该角色中的用户在能够实时推送设置的用户审阅其工作并这样做之前，无法影响实时搜索。

权限&#x200B;**[!UICONTROL Run live indexes]**&#x200B;和&#x200B;**[!UICONTROL Run stage indexes]**&#x200B;是用于向角色中的用户授予或拒绝其运行索引的能力的特殊控件。

例如，某些用户的角色可能具有运行分阶段索引但不运行实时索引或实时推送分阶段设置的能力。 担任此角色的用户可以在一个分阶段环境中测试其所有工作，而不会影响实时索引。 某些设置要求您在预览所做更改之前重新构建索引。

要更改访问权限，您必须在管理员区域中更改相应角色的权限。

请参阅[配置您的个人用户信息](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6)。

请参阅[配置首选项](../c-about-settings-menu/c-about-my-profile-menu.md#task_5E06BF565C284C2EBBE18E10A1C4BFBB)。

请参阅[更改登录密码](../c-about-settings-menu/c-about-my-profile-menu.md#task_F5FF13AAD1514FE997C8882D4537C0C9)

请参阅[取消登录](../c-about-settings-menu/c-about-my-profile-menu.md#task_D57701BB726243B08CEA14EEC86C3087)。

**视图访问权限**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL My Access Privileges]**。
1. 在[!DNL My Access Privileges]页面上，展开树视图以查看权限或受限访问。
