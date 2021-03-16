---
description: 使用“用户”菜单可视图和添加用户、视图和添加角色或更改角色成员关系。 您必须是具有管理员权限的网站搜索/促销用户，才能执行“用户”(Users)菜单上的任何任务。
solution: Target
subtopic: Users
title: 关于“用户”菜单
topic: 设置、网站搜索和销售
uuid: 6242b73c-5e8a-44b7-9942-0684530940bc
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1450'
ht-degree: 0%

---


# 关于“用户”菜单{#about-the-users-menu}

使用“用户”菜单可视图和添加用户、视图和添加角色或更改角色成员关系。 您必须是具有管理员权限的网站搜索/促销用户，才能执行“用户”(Users)菜单上的任何任务。

## 查看帐户用户{#task_FDDF30EE23C548DF8CFBB2FB2605303C}

您可以使用[!DNL View Users]页面视图所有现有帐户用户。 您还可以删除帐户用户（帐户所有者除外）。

只有已选中&#x200B;**[!UICONTROL User Admin]**&#x200B;的帐户用户才能删除用户或修改用户角色。

在删除帐户所有者之前，请将帐户所有权转移给其他用户。

在转移所有权后，您可以像任何其他用户一样删除帐户。 已删除的用户会收到一封电子邮件，通知他们状态的更改。

请参阅[将帐户所有权转移给其他帐户用户](../c-about-settings-menu/c-about-account-options-menu.md#task_47E3C66CC6374274830DA10171E0CF17)。

>[!NOTE]
>
>您必须是具有管理员权限的网站搜索/促销用户才能执行此任务。

**视图帐户用户**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Users]** > **[!UICONTROL View Users]**。
1. （可选）在[!DNL User Admin]列标题下，选择要允许其删除帐户用户或编辑帐户用户角色的帐户用户。
1. （可选）在[!DNL Remove?]列标题下，选择要删除的帐户用户。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）单击[!DNL View Users]页面上的超链接角色名称。 此时会打开[!DNL Role Membership]页面，您可以在其中将用户分配到角色，也可以将用户从角色中取消分配。

   请参阅[配置角色成员关系](../c-about-settings-menu/c-about-users-menu.md#task_DAC596AAFFCE4EF0BE68CEEF7E365414)。

## 添加帐户用户{#task_176C463A0C0849B29245C28EC9876326}

您可以使用[!DNL Add Users]页面向网站搜索/促销添加新帐户用户。

只需要新用户的电子邮件地址。 将新用户添加到帐户后，会向新用户发送帐户信息。

默认情况下，新用户不会分配为用户管理员。 用户管理员可以定义和编辑角色，并删除其他用户。 您可以从[!DNL Add Users]页面中选择将新用户设为用户管理员。 或者，也可以使用“视图用户”页将新用户设为“用户管理员”。

请参阅[查看帐户用户](../c-about-settings-menu/c-about-users-menu.md#task_FDDF30EE23C548DF8CFBB2FB2605303C)。

您指定的电子邮件地址只能包含ASCII字符。 使用标准字母(a..z)字符或数字(0.9)字符，只有一个`@`字符用于将用户名与域分开。 字符`_`、`+`、`-`、`.`、`!`、`#`、`$`、`'`、`%`、`&`、`*`、`=`、`?`、`^`、还允许a14/>和`}`。 `{`不要将电子邮件地址开始为`.`

如果新用户不是Adobe客户，系统会提示您为该用户创建客户登录。 将向新用户发送登录密码和确认。 新用户首次登录时，会填写客户用户档案。

您可以选择单击[!DNL Add Users]页面上的超链接角色名称。 此时会打开[!DNL Role Membership]页面，您可以在其中将用户分配到角色，也可以将用户从角色中取消分配。

请参阅[配置角色成员关系](../c-about-settings-menu/c-about-users-menu.md#task_DAC596AAFFCE4EF0BE68CEEF7E365414)。

>[!NOTE]
>
>您必须是具有管理员权限的网站搜索/促销用户才能执行此任务。

**添加帐户用户**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Users]** > **[!UICONTROL Add Users]**。
1. 在[!DNL Add Users]页面的[!DNL User's Email]字段和[!DNL User's Email (again)]字段中，输入新用户的电子邮件地址。
1. （可选）选中&#x200B;**[!UICONTROL User Administrator]**&#x200B;可让新帐户用户能够删除帐户用户或编辑帐户用户角色。
1. 在[!DNL Roles for this User]表中，检查要分配给新帐户用户的角色。
1. 单击 **[!UICONTROL Add User]**.

## 查看帐户{#task_4EAE1D018F384691A083AD51E5CE58DC}中存在的角色

您可以使用[!DNL View Roles]页显示当前登录帐户当前存在的所有角色。

如果帐户不存在角色，用户界面会通知您此问题。 您可以使用添加角色来创建和添加角色。

请参阅[向帐户添加新角色](../c-about-settings-menu/c-about-users-menu.md#task_E148D02275DE4F899BA79736A29895AB)。

删除角色不会删除分配给该角色的帐户用户。

>[!NOTE]
>
>您必须是具有管理员权限的网站搜索/促销用户才能执行此任务。

**要视图帐户中存在的角色**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Users]** > **[!UICONTROL View Roles]**。
1. （可选）在表中的[!DNL Remove?]列标题下，选择要删除的角色。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列任一操作：

   * 在表的[!DNL Role Name]列标题下，单击超链接角色名称。 此时会打开[!DNL Role Membership]页面，您可以在其中将用户分配到角色，也可以将用户从角色中取消分配。

      请参阅[配置角色成员关系](../c-about-settings-menu/c-about-users-menu.md#task_DAC596AAFFCE4EF0BE68CEEF7E365414)。

   * 在表中的[!DNL Edit]列标题下，单击铅笔图标。 此时将打开[!DNL Edit Role]页面，您可以在其中重命名角色、更改说明等。

      请参阅[编辑角色](../c-about-settings-menu/c-about-users-menu.md#task_13875C2464034CE387285640412E1B59)。

## 编辑角色{#task_13875C2464034CE387285640412E1B59}

您可以重命名现有角色，更改其描述，并仅选择要授予角色访问权限的用户界面区域。

请参阅[向帐户添加新角色](../c-about-settings-menu/c-about-users-menu.md#task_E148D02275DE4F899BA79736A29895AB)。

>[!NOTE]
>
>您必须是具有管理员权限的网站搜索/促销用户才能执行此任务。

**编辑角色**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Users]** > **[!UICONTROL View Roles]**。
1. 在表中的[!DNL Edit]列标题下，单击要更改的角色旁边的铅笔图标。
1. （可选）执行下列任一操作：

   * 在[!DNL Role Name]文本字段中，根据需要键入新名称。 *表示此字段是角色必需的。
   * 在[!DNL Description]文本字段中，根据需要键入角色的新描述。
   * 在组框中，选中或取消选中您希望角色分别访问或阻止的功能。

1. 单击 **[!UICONTROL Save Changes]**.

## 向帐户{#task_E148D02275DE4F899BA79736A29895AB}添加新角色

您可以使用[!DNL Add Roles]页面来更轻松、快速地分配帐户用户的权限。

例如，您可以单独授予您的公共关系部门的每个成员访问网站搜索/销售任务。 但是，将这些用户添加到“PR”角色，然后将任务分配到整个角色会效率更高。

每个角色名称必须唯一。 可以使用字母数字字符和常用符号，包括短划线`"-"`、下划线`"_"`和句点`"."`。 名称不能以下划线或句点开头。

在表的[!DNL Users in This Role]列标题下，您可以选择单击某个用户的超链接电子邮件地址。 将为特定用户打开[!DNL Role Membership]页面，您可以在该页面中将用户分配到角色，也可以从角色中取消分配用户。

请参阅[配置角色成员关系](../c-about-settings-menu/c-about-users-menu.md#task_DAC596AAFFCE4EF0BE68CEEF7E365414)。

在表中的[!DNL Roles]列标题下，您可以选择单击超链接角色名称。 此时会打开[!DNL Role Membership]页面，您可以在其中将用户分配到所选角色，也可以从所选角色中取消分配用户。

>[!NOTE]
>
>您必须是具有管理员权限的网站搜索/促销用户才能执行此任务。

**向帐户添加新角色**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Users]** > **[!UICONTROL Add Roles]**。
1. 在[!DNL Add Roles]页面的[!DNL Role Name]字段中，输入角色的名称。
1. （可选）在[!DNL Description]字段中，输入一句能够充分描述角色的句子。
1. 选中每个电子邮件地址左侧的复选框，选择属于该角色的用户。
1. 单击 **[!UICONTROL Add Role]**.

## 配置角色成员关系{#task_DAC596AAFFCE4EF0BE68CEEF7E365414}

您可以使用[!DNL Role Membership]页面将用户添加到角色或从角色中删除用户。

您还可以在按用户视图角色时管理单个用户组成员关系。

请参阅[向帐户添加新角色](../c-about-settings-menu/c-about-users-menu.md#task_E148D02275DE4F899BA79736A29895AB)。

请参阅[查看帐户](../c-about-settings-menu/c-about-users-menu.md#task_4EAE1D018F384691A083AD51E5CE58DC)中存在的角色。

>[!NOTE]
>
>您必须是具有管理员权限的网站搜索/促销用户才能执行此任务。

**将帐户用户分配到角色**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Users]** > **[!UICONTROL Role Membership]**。
1. 在[!DNL Role Membership]页面上，执行以下操作之一：

   <table> 
      <thead class="chhead sthead"> 
      <th class="choptionhd"> <p>选项 </p> </th> 
      <th class="chdeschd"> <p>步骤 </p> </th> 
      </thead> 
      <tr class="chrow strow"> 
      <td class="choption"><strong>将一个或多个用户添加到单个角色</strong></td> 
      <td class="chdesc stentry"> <p>
      <ul id="ul_59E7C36210804EF9B6A2706A5357A892"> 
      <li id="li_2A8D31C968B543EBA7948DD4EFA350AA"> 在<span class="uicontrol">更改角色</span>下拉列表中，选择要将用户添加到的角色。 <p>如果未显示<span class="uicontrol">更改角色</span>下拉列表，请单击<span class="uicontrol">视图用户BY GROUP</span>。 </p> </li> 
      <li id="li_3A67F0DDBDBE4883A17300A3F088D71A"> （可选）在表中，选中<span class="uicontrol">仅显示角色成员</span>以使表仅显示当前已分配给选定角色的帐户用户。 </li> 
      <li id="li_4926A22D1ED94AC9972C2619A398A8C7"> 在表的复选框列中，选择要分配给选定角色的一个或多个帐户用户。 <p>取消选择要从所选角色中删除的一个或多个帐户用户。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr class="chrow strow"> 
      <td class="choption"><strong>向单个用户添加一个或多个角色</strong></td> 
      <td class="chdesc stentry"> <p> 
         <ul id="ul_B3F8E84B0ED94B2D83F0DB0C91F07DC7"> 
         <li id="li_67EE15F527384CCDB8171DB3D89F6819"> 在<span class="uicontrol">更改用户</span>下拉列表中，选择要向其分配一个或多个角色的用户。 <p>如果未显示<span class="uicontrol">更改用户</span>下拉列表，请单击<span class="uicontrol">视图角色BY USER</span>。 </p> </li> 
         <li id="li_7830E87D6924433DBBA03C953B9452A2"> （可选）在表中，选中<span class="uicontrol">仅显示此用户的角色</span>以使表仅显示当前分配给选定帐户用户的那些角色。 </li> 
         <li id="li_DE742B95BFC34BF4AE338B165B533FDF"> 在表的复选框列中，选择要分配给选定用户的一个或多个角色。 <p>取消选择要从选定用户中删除的一个或多个角色。 </p> </li> 
         </ul> </p> </td> 
      </tr> 
   </table>

1. 单击&#x200B;**保存更改**。
