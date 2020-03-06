---
description: 数据视图显示带有元字段的搜索结果。 每列都是元字段，每行都是搜索查询的结果。 通过选择并重新排列列，自定义数据视图。 数据视图也可以具有自定义标题和说明。
seo-description: 数据视图显示带有元字段的搜索结果。 每列都是元字段，每行都是搜索查询的结果。 通过选择并重新排列列，自定义数据视图。 数据视图也可以具有自定义标题和说明。
seo-title: 关于数据视图
solution: Target
title: 关于数据视图
topic: Reports,Site search and merchandising
uuid: 18930551-960d-40c2-b5b7-0807a2e11134
translation-type: tm+mt
source-git-commit: 7af85dd37f06fe506e5f57e28a25385ca7ab3db5

---


# 关于数据视图{#about-data-views}

数据视图显示带有元字段的搜索结果。 每列都是元字段，每行都是搜索查询的结果。 通过选择并重新排列列，自定义数据视图。 数据视图也可以具有自定义标题和说明。

## 使用数据视图 {#concept_DCA897D074464BC1861AA47B40CC86C3}

每个帐户都可以方便地创建多个数据视图。 使用“数据视图”页可创建和编辑这些数据视图。

添加数据视图后，必须编辑它以配置和自定义视图。

请参 [阅编辑数据视图](../c-about-reports-menu/c-about-data-views.md#task_258A367896C24DD498C755925EA8F516)。

您可以复制现有数据视图以用作创建新数据视图的基础。

请参 [阅复制数据视图](../c-about-reports-menu/c-about-data-views.md#task_78D4C2799BC84677843ED4CA1CD205AF)。

## 添加数据视图 {#task_A20FEB2E1CA1444D816D2F5F4B6E5B2D}

您可以向页面添加数据视 [!DNL Data Views] 图，以通过搜索查询显示每个元字段的值。

添加数据视图后，必须编辑它以配置和自定义视图。

请参 [阅编辑数据视图](../c-about-reports-menu/c-about-data-views.md#task_258A367896C24DD498C755925EA8F516)。

**添加数据视图**

1. 在产品菜单中，单击 **[!UICONTROL Reports]** > **[!UICONTROL Data Views]**。
1. 在页面 [!DNL Data Views] 上，单击 **[!UICONTROL Add New Data View]**。
1. 在对 [!DNL Add New Data View] 话框的字段中， [!DNL Title] 输入要创建的数据视图的名称。
1. 单击 **[!UICONTROL Add]**.

## 编辑数据视图 {#task_258A367896C24DD498C755925EA8F516}

向页面添加数据视图时，可使用“编辑”来更改数据视图的名称和说明，或移动、显示或隐藏每个元字段的显示。 [!DNL Data Views]

您还可以锁定或解锁选定的数据视图。

请参 [阅添加数据视图](../c-about-reports-menu/c-about-data-views.md#task_A20FEB2E1CA1444D816D2F5F4B6E5B2D)。

**编辑数据视图**

1. 在产品菜单中，单击 **[!UICONTROL Reports]** > **[!UICONTROL Data Views]**。
1. 在页 [!DNL Data Views] 面上，在表 [!DNL Actions] 的列中，单击要更改的 **[!UICONTROL Edit]** 数据视图所在的行。
1. 在页 [!DNL Data Views Editor] 面上，设置所需的选项。

   “数据视图编辑器”具有“数据视图”页面上用于隐藏、显示和移动字段列的所有控件。

   当您查看数据视图时，生成的表格还显示了以下不可编辑的附加列字段：排名、相关性和得分（整体）。 这三个特殊字段表示每个结果的相关分数、排名分数和总分。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>标题 </p> </td> 
      <td colname="col2"> <p>数据视图的名称。 当您查看数据视图时，该名称显示在右上方。 </p> <p>请参阅 <a href="../c-about-reports-menu/c-about-data-views.md#task_FD0D2CE53DF84CBD9220AD7CA920011F" type="task" format="dita" scope="local"> 查看数据视图</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>描述 </p> </td> 
      <td colname="col2"> <p>（可选）包含数据视图的说明。 说明显示在数据视图的标题名称和“新建搜索”文 <span class="wintitle"> 本字段之间</span> 。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>搜索参数 </p> </td> 
      <td colname="col2"> <p>允许您指定默认搜索参数。 首次显示数据视图时，会自动附加这些CGI参数。 </p> <p>请勿更改或删 <span class="codeph"> 除sp_cs</span><span class="codeph"> 或sp_f</span>。 这些参数对于“数据视图”是必需的，而不管帐户的首选字符集如何。 </p> <p>请参阅 <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> 后端搜索CGI参数</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>锁定状态 </p> </td> 
      <td colname="col2"> <p>允许您锁定或解锁数据视图。 </p> <p>您只能使用口令和用户名查看锁定的数据视图。 用户必须是帐户的当前成员。 </p> <p>无需口令或用户帐户即可访问已解锁的数据视图。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>订购 </p> </td> 
      <td colname="col2"> <p> 允许您通过编辑“顺序”文本框中的数字来更改 <span class="wintitle"> 列顺序</span> 。 您还可以拖放行以更改列顺序。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>包含 </p> </td> 
      <td colname="col2"> <p> 允许您打开或关闭列的显示。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>将URL显示为图像 </p> </td> 
      <td colname="col2"> <p>如果此列的搜索结果返回URL，则显示此列中的缩略图和图像。 </p> <p>URL在成为图像标记的src属性值之前，会去除其方案名称或协 <span class="codeph"> 议</span> 。 </p> <p>如果返回的搜索结果看起来不像图像的URL，则显示一个。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>字段长度 </p> </td> 
      <td colname="col2"> <p>设置在数据视图中显示为结果的字符数。 </p> <p>默认为100个字符。 </p> <p>某些字段（如排名得分和日期字段）没有可调整的字段长度。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列任一操作：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 复制数据视图 {#task_78D4C2799BC84677843ED4CA1CD205AF}

您可以复制页面上的现有数据 [!DNL Data Views] 视图，以用作创建新数据视图的基础。

复制数据视图后，可以通过编辑视图进一步自定义它。

请参 [阅编辑数据视图](../c-about-reports-menu/c-about-data-views.md#task_258A367896C24DD498C755925EA8F516)。

**复制数据视图**

1. 在产品菜单中，单击 **[!UICONTROL Reports]** > **[!UICONTROL Data Views]**。
1. 在页 [!DNL Data Views] 面上，在表 [!DNL Actions] 的列中，单击要复制的 **[!UICONTROL Copy]** 数据视图所在的行。
1. 在页 [!DNL Copy Data View] 面的文本字 [!DNL New Title] 段中，输入要分配数据视图的新名称。
1. 单击 **[!UICONTROL Copy]**.
1. （可选）执行下列任一操作：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 删除数据视图 {#task_61C32F8F00A549A5A3E7EDDA6F537098}

您可以删除页面上不再需要 [!DNL Data Views] 或使用的数据视图。

**删除数据视图**

1. 在产品菜单中，单击 **[!UICONTROL Reports]** > **[!UICONTROL Data Views]**。
1. 在页 [!DNL Data Views] 面上，在表的 [!DNL Actions] 列中，单击要删除的 **[!UICONTROL Delete]** 数据视图所在的行。
1. 在页面 [!DNL Delete Data View] 上，单击“删 **除”**。
1. （可选）执行下列任一操作：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 查看数据视图 {#task_FD0D2CE53DF84CBD9220AD7CA920011F}

您可以在页 [!DNL View] 面上使 [!DNL Data Views] 用以显示选定的数据视图。

您选择的数据视图将在单独的浏览器窗口中打开。

**查看数据视图**

1. 在产品菜单中，单击 **[!UICONTROL Reports]** > **[!UICONTROL Data Views]**。
1. 执行下列任一操作：

   * 在页 [!DNL Data Views] 面上，在表 [!DNL Title] 的列中，单击要打开的数据视图的名称。

   * 在页 [!DNL Data Views] 面上，在表 [!DNL Actions] 的列中，单击要打开的 **[!UICONTROL View]** 数据视图所在的行。

