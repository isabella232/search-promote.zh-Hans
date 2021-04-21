---
description: 使用Adobe Analytics菜单设置Adobe Analytics量度身份验证，管理报表包的Adobe Analytics量度，或使用SAINT通过接受来自外部源的表格数据来增强Adobe Analytics报表。
solution: Target
subtopic: Adobe Analytics
title: 关于Adobe Analytics菜单
topic-legacy: Settings,Site search and merchandising
uuid: 5536edf1-d3a4-47af-a307-6e46f385f738
exl-id: e1f7b8f0-45d4-457a-a9d3-a8cb4b785059
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '3407'
ht-degree: 1%

---

# 关于Adobe Analytics菜单{#about-the-adobe-analytics-menu}

使用Adobe Analytics菜单设置Adobe Analytics量度身份验证，管理报表包的Adobe Analytics量度，或使用SAINT通过接受来自外部源的表格数据来增强Adobe Analytics报表。

## 设置Adobe Analytics量度身份验证{#task_8AA93F6273B747F9B4DE9E8DFBCBDC42}

要将Adobe Analytics量度纳入您的网站搜索/促销排名，您必须首先获得Adobe Analytics Web服务登录。 获得登录信息后，您可以使用它在网站搜索/销售中设置Adobe Analytics身份验证。

**设置Adobe Analytics量度身份验证**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Authentication]**。
1. 在[!DNL Setup Adobe Analytics Metrics Authentication]页面上，指定在每个字段中请求的信息。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>文本字段 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Adobe Analytics 公司名称 </p> </td> 
      <td colname="col2"> <p>用于登录Adobe Analytics帐户的公司名称设置相同。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Web 服务用户名 </p> </td> 
      <td colname="col2"> <p>与您的Adobe Analytics帐户关联的Web服务用户名。 </p> <p>您可以在Adobe Analytics中获取此信息。 在Adobe Analytics菜单栏上，单击<span class="uicontrol"> <b>Admin</b> </span> &gt; <span class="uicontrol"> <b></b> </span> <span class="uicontrol"> <b>公司</span> &gt; <span class="uicontrol"> <b>web服务</b> </span>。 </b>该信息位于“API访问信息”表中。 </span></p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Web服务共享机密 </p> </td> 
      <td colname="col2"> <p>与您的Adobe Analytics帐户关联的Web服务共享机密。 </p> <p>您可以在Adobe Analytics中获取此信息。 在Adobe Analytics菜单栏上，单击<span class="uicontrol"> <b>Admin</b> </span> &gt; <span class="uicontrol"> <b></b> </span> <span class="uicontrol"> <b>公司</span> &gt; <span class="uicontrol"> <b>web服务</b> </span>。 </b>该信息位于“API访问信息”表中。 </span></p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于Adobe Analytics报表包{#concept_1A51AEC5D40E459B813E7891D64B1BAE}

要在网站搜索/促销中使用Adobe Analytics报表包数据，您必须首先在网站搜索/促销帐户中创建Adobe Analytics数据的副本。

您可以创建新的Adobe Analytics报表包定义，也可以视图或修改现有的Adobe Analytics报表包和关联量度。

您首次从网站搜索/促销中访问Adobe Analytics时，将下载并缓存公司可用报表包的列表。 如果最近添加了新报表包，或删除了现有报表包，您可以刷新报表包列表以重新下载报表包的列表。

## 添加Adobe Analytics报表包{#task_6DE17305EA7146DA8C30FF8FDF68A3C0}

您可以选择一个Adobe Analytics报表包，作为网站搜索/促销排名规则的基础。

您可以从中选择的列表应与Adobe Analytics帐户中提供的报表包相对应。 您选择的报表包确定可在网站搜索/促销排名规则中使用的量度。

请参阅[有关规则排名](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397)。

添加Adobe Analytics报表包后，可以编辑其量度。

请参阅[编辑报表包的Adobe Analytics量度](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664)。

**添加Adobe Analytics报表包**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**。
1. 在“Adobe Analytics报表包”页面上，单击&#x200B;**[!UICONTROL Add Report Suite]**。
1. 在新添加的表行的下拉列表中，选择所需的报表包。
1. 编辑报表包的Adobe Analytics量度。

## 编辑报表包{#task_360904CCBBB140238ADA036C3CC07664}的Adobe Analytics量度

要在网站搜索/促销中将Adobe Analytics量度并入您的排名规则，请选择一个或多个与所选报表包关联的量度。 然后，您可配置通过Adobe Analytics Web服务用于获取量度数据的选项。

请参阅[添加Adobe Analytics报表包](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0)。

请参阅[配置高级Adobe Analytics选项](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_C0FF2D69F59D44D8943A7831ED7FEC19)。

**编辑报表包的Adobe Analytics量度**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**。
1. 在[!DNL Adobe Analytics Report Suites]页面的&#x200B;**[!UICONTROL Actions]**&#x200B;列下，单击要配置量度的报表包的&#x200B;**[!UICONTROL Edit]**。
1. 在[!DNL Edit Adobe Analytics Metrics]页面上，设置所需的量度。 量度名称旁边没有星号(*)的量度是可选的。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>报表包 </p> </td> 
      <td colname="col2"> <p>显示您添加的当前报表包的名称。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>报表包视图名 </p> </td> 
      <td colname="col2"> <p>提供Adobe Analytics报表包名称的“别名”名称。 如果在多个定义中使用相同的报表包，则此替代名称很有用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>选择报表类型 </p> </td> 
      <td colname="col2"> <p>指定要与所选报表包一起使用的报表类型值。 该值标识每个返回结果行的键。 </p> <p>报表类型也称为Adobe Analytics元素。 </p> <p>此量度为必需。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>交叉引用字段名称 </p> </td> 
      <td colname="col2"> <p>指定一个元数据字段，其值用作报表包数据中的查找“键”。 </p> <p>如果未选择任何值("— None —")，则此报表包的数据不可用于排名计算(<span class="uicontrol"> <b> Rules</b> </span> &gt; <span class="uicontrol"> <b> Rawing Rules</b> </span> &gt; <span class="uicontrol"> <b>Edit Rules</b> </span>)。 </p> <p>当您选择一个值时，此字段的值将用于使用您之前设置的选定“报表类型”值，将此报表包的Adobe Analytics数据交叉引用网站搜索/促销文档。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>搜索词报表 </p> </td> 
      <td colname="col2"> <p>允许您访问<b>暂存Adobe Analytics数据预览</b>页面，以创建业务规则并模拟搜索词。 </p> <p>请参阅<a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0" type="task" format="dita" scope="local">预览Adobe Analytics数据</a>。 </p> <p>每个包含两个选项的行上都会显示一个下拉菜单：<b>模拟搜索词</b>和<b>创建新业务规则</b>。 </p> <p>这两个选项都使用报表类型中的数据作为搜索词。 因此，仅当“报表类型”表示搜索词时，此功能才有意义。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>量度 </p> </td> 
      <td colname="col2"> <p>标识您要下载的量度值，并在网站搜索/促销排名规则中使用。 </p> <p>当规则A时，您在此处配置的量度在<span class="uicontrol"> <b>规则</b> </span> &gt; <span class="uicontrol"> <b>排名规则</b> </span> &gt; <span class="uicontrol"> <b>编辑规则</b> </span>成员中心页面上显示为选项数据类型设置为<span class="uicontrol"> Adobe Analytics量度(Number)</span>。 这些选项显示报表包名称或报表包视图名称（如果指定）以及单个量度名称的组合。 </p> <p>此量度为必需。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最小量度值 </p> </td> 
      <td colname="col2"> <p>允许您输入非零值以指定量度的最小值。 </p> <p>如果为空或零，则下载该量度的所有值；否则，传递最小量度值时，此量度的下载将停止。 </p> <p>Adobe Analytics量度按降序检索。 </p> <p>单击<span class="uicontrol"> <b>+</b> </span>添加其他量度定义；单击<span class="uicontrol"> <b>-</b> </span>可删除不再需要或不需要的量度定义。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Adobe Analytics量度汇总期间（天） </p> </td> 
      <td colname="col2"> <p> 控制要提取的Adobe Analytics量度的天数，从昨天的日期算起。 未尝试从当天提取数据。 </p> <p>默认值为 7。 </p> <p>此量度为必需。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Adobe Analytics下载刷新频率（天） </p> </td> 
      <td colname="col2"> <p> 设置用于排名计算的Adobe Analytics数据下载之间的最小时间间隔。 </p> <p>忽略在下载刷新频率间隔内发生的索引触发的下载。 但是，手动下载会忽略此值。 </p> <p>如果将此值设置为默认值1，则Adobe Analytics数据在24小时内不会多次下载。 在下载刷新频率间隔内发生的所有搜索索引都使用上次下载的数据集。 </p> <p>此量度为必需。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

   另请参阅[关于排名规则](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397)。
1. 单击 **[!UICONTROL Save Changes]**.

   您将返回到“已暂存[!DNL Adobe Analytics Report Suites]”页面。
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 删除Adobe Analytics报表包{#task_0ACA172214D14654ABDB139F417B9F7D}

您可以使用删除从[!DNL Adobe Analytics Report Suites]页面中删除报表包。 删除报表包仅会从网站搜索/促销服务器中删除数据的副本；它不会影响Adobe Analytics系统上的数据。

**删除Adobe Analytics报表包**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**。
1. 在[!DNL Adobe Analytics Report Suites]页面的&#x200B;**[!UICONTROL Actions]**&#x200B;列下，单击&#x200B;**[!UICONTROL Delete]**&#x200B;以查看要删除的报表包。
1. 在[!DNL Adobe Analytics Delete Report Suite]页面上，单击&#x200B;**[!UICONTROL Delete]**。

## 预览Adobe Analytics数据{#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0}

您可以使用预览来视图最近加载的Adobe Analytics量度。

表中的行列显示每行量度数据的编号，指示Adobe Analytics量度的加载原始顺序。

“产品”列显示与每行量度数据关联的Adobe Analytics元素。 此列中的值用于将您的网站搜索/促销页面与其对应的量度值关联，如排名定义中所配置。

请参阅[有关规则排名](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397)。

请参阅[配置排名](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5)。

其余列显示与每个条目关联的量度值。

如果表为空，则表示尚未加载任何Adobe Analytics数据。 您可以关闭[!DNL Adobe Analytics Data Preview]页面，然后加载Adobe Analytics数据。

请参阅[加载Adobe Analytics数据](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181)。
如果将表指定为搜索词报表，则每行中都会出现一个小三角形。 您可以单击下拉列表并选择**模拟搜索词**&#x200B;或&#x200B;**创建新业务规则**。 您选择的操作将应用于该行的搜索词，即驻留在第二列中的数据

**预览Adobe Analytics数据**

1. 在“产品”菜单中，执行下列操作之一：

   * 单击 **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**. 在[!DNL Adobe Analytics Report Suites]页面的[!DNL Actions]列下，单击&#x200B;**[!UICONTROL Preview]**&#x200B;以查看要视图其下载数据的报表包。

   * 单击 **[!UICONTROL Reports]** > **[!UICONTROL Adobe Analytics Terms Reports]**. 在[!DNL Adobe Analytics Terms Report]页面的[!DNL Actions]列下，单击&#x200B;**[!UICONTROL Preview]**&#x200B;以查看要视图其下载数据的报表包。

1. 在[!DNL Adobe Analytics Data Preview]页面上，使用页面顶部和底部的导航和查看选项来视图数据。

   单击表中的任何列标题，按升序或降序对数据排序。
1. 执行下列任一操作：

   * 单击&#x200B;**[!UICONTROL Download to Desktop]**&#x200B;下载表并将其保存为`.xlt`文件。

   * 在您预览完Adobe Analytics数据后关闭该页面，并返回到之前查看的页面。

## 查看最近Adobe Analytics数据加载{#task_9C7D6E34BB6C4A40B7CA3EE36ACB0837}中的日志

您可以使用视图日志检查最新下载过程的Adobe Analytics数据日志文件。 您还可以使用日志视图监视正在运行的下载。

请参阅[加载Adobe Analytics数据](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181)。

**从最近的Adobe Analytics数据加载视图日志**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**。
1. 在[!DNL Adobe Analytics Report Suites]页面上，单击&#x200B;**[!UICONTROL View Log]**。 日志页，
1. 在[!DNL Adobe Analytics Data Log]页面上，使用页面顶部和底部的导航和查看选项来视图日志信息。
1. 完成后，关闭该页面以返回到[!DNL Adobe Analytics Report Suites]页面。

## 加载Adobe Analytics数据{#task_2F3C55189B0A4049AB2113F2291CC181}

您可以将已配置的Adobe Analytics Report Suite数据下载到网站搜索/促销中。

“数据加载”页显示您上次Adobe Analytics数据加载操作的状态，其中包含以下信息：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>状态字段 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>状态 </p> </td> 
   <td colname="col2"> <p>指示上次数据加载尝试的成功或失败。 或者，它显示已在进行的数据加载操作的状态。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>结果 </p> </td> 
   <td colname="col2"> <p>显示上次数据加载尝试期间下载的量度数据的行数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>开始时间 </p> </td> 
   <td colname="col2"> <p>显示上次数据加载操作开始的日期和时间。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>停止时间 </p> </td> 
   <td colname="col2"> <p>显示上次数据加载操作的完成日期和时间。 或者，它表示当前数据加载操作仍在进行中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**加载Adobe Analytics数据**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**。
1. 在[!DNL Stage Adobe Analytics Report Suites]页面上，单击&#x200B;**[!UICONTROL Load Adobe Analytics Data]**。
1. 在&#x200B;**[!UICONTROL Adobe Analytics Data Load]**&#x200B;页面上，执行以下操作之一：

   * 单击&#x200B;**[!UICONTROL Start Load]**&#x200B;以开始加载操作。

      在数据加载操作期间，**Progress**&#x200B;行提供有关其进度的信息。

   * 单击&#x200B;**[!UICONTROL Stop Load]**&#x200B;以停止加载操作。

1. 单击&#x200B;**[!UICONTROL Close]**&#x200B;返回至[!DNL Stage Adobe Analytics Reports Suite]页面。

## 刷新报表包列表{#task_EA6215D438CA4185B106657D9712ED34}

首次从网站搜索/促销用户界面访问Adobe Analytics时，将下载并缓存公司可用Adobe Analytics报表包的列表。 如果最近添加了新报表包或删除了现有报表包，则可以使用“刷新报表包”列表来更新网站搜索/促销中当前显示的列表。

请参阅[添加Adobe Analytics报表包](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0)。

请参阅[删除Adobe Analytics报表包](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_0ACA172214D14654ABDB139F417B9F7D)。

**刷新报表包列表**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**。
1. 在[!DNL Adobe Analytics Report Suites]页面上，单击&#x200B;**[!UICONTROL Refresh Report Suite List]**。

## 配置高级Adobe Analytics选项{#task_C0FF2D69F59D44D8943A7831ED7FEC19}

您可以使用[!DNL Advanced Adobe Analytics Options]来控制旨在帮助您优化Adobe Analytics报表包下载过程行为的设置。

请参阅[编辑报表包的Adobe Analytics量度](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664)。

**配置高级Adobe Analytics选项**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Advanced Options]**。
1. 在[!DNL Advanced Adobe Analytics Options]页面上，设置以下选项：

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>最大行数、任意量度 </p> </td> 
      <td colname="col2"> <p>可防止下载过多Adobe Analytics数据的优化设置。 </p> <p>如果将此选项设置为非零值，则当每个量度获取的总行数超过指定值时，将停止Adobe Analytics数据提取。 </p> <p>默认值为0;未应用最大值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>量度重复提取大小（行） </p> </td> 
      <td colname="col2"> <p> 控制每次要提取的Adobe Analytics量度值数。 在检索所有数据或达到最大行限制之前，会重复读取度量数据行。 </p> <p>通常，您无需更改此设置。 但是，您可能会发现优化网站完整重新索引的量度下载阶段很有帮助。 </p> <p>默认值为 5000。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于SAINT分类源{#concept_C55609DA24914BBC92CD90ED0259199D}

您可以使用Adobe Analytics SAINT通过接受来自外部源的表格数据来增强您的分析报告。 例如，您可以使用网站搜索/促销从其自己的索引中检索数据并将该数据导出到Adobe Analytics。

要在网站搜索/销售中成功使用Adobe AnalyticsSAINT功能，请注意以下要求：

* 您必须拥有Adobe Analytics公司和报表包。

   请参阅[关于Adobe Analytics菜单](../c-about-settings-menu/c-about-adobe-analytics-menu.md#concept_5FD2D13C9D0D40988E6E51480D690411)。
* Adobe Analytics用户帐户必须具有修改报表包的权限。

   请参阅[设置Adobe Analytics量度身份验证](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_8AA93F6273B747F9B4DE9E8DFBCBDC42)。
* Adobe Analytics用户必须属于Web API组，以便他们能够使用Adobe Analytics Web API。
* 搜索索引必须包含Adobe Analytics可以使用的数据，如数据格式正确。

在创建源之前，请查看以下问题和信息，以便您能够成功完成SAINT源向导：

* 您要使用哪个报表包？
* 您要为哪些分类集（如产品、e-var等）提供数据？
* 报表中存在哪些分类？ 此问题的答案取决于可从网站搜索/销售中随时获得的数据类型以及Adobe Analytics报告所需的报表类型。
* SAINT将网站搜索/促销中的数据接受为文本类型。 这些数据的格式影响Adobe Analytics报告的列报。

## 创建Adobe AnalyticsSAINT源{#task_914B5AB821E84627953D8EF9339A7DD0}

您可以使用Adobe Analytics SAINT通过接受来自外部源的表格数据来增强Adobe Analytics报告。

例如，您可以使用网站搜索/促销从其自己的索引检索数据并将该数据导出到Adobe Analytics。

**创建Adobe AnalyticsSAINT源**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**。
1. 在[!DNL SAINT Classification Feeds]页面上，单击&#x200B;**[!UICONTROL Create SAINT Feed]**。
1. 在[!DNL Create Feed]对话框的&#x200B;**源名称**&#x200B;文本字段中，输入新源名称，然后单击&#x200B;**[!UICONTROL Next]**。

   此时，将保存信息源并将其添加到[!DNL SAINT Classification Feed]页面。 如果您选择，您可以退出，稍后编辑源以完成向导。
1. 在[!DNL Authentication]页面上，在相应的文本字段中指定Adobe Analytics公司名称、用户名和Web机密，然后单击&#x200B;**[!UICONTROL Next]**。

   确保已获得授权将Web API与Adobe Analytics一起使用。
1. 在&#x200B;**[!UICONTROL Report Suite]**&#x200B;页面上，选择报表包及其分类数据集，然后单击&#x200B;**[!UICONTROL Next]**。
1. 在[!DNL Field Maps]页面上，将Adobe Analytics分类与网站搜索/促销元数据字段进行映射，然后单击&#x200B;**[!UICONTROL Next]**。

   要调整Adobe Analytics分类，请单击&#x200B;**[!UICONTROL Edit]** Adobe Analytics分类以登录Adobe Analytics。 完成更改后，单击&#x200B;**[!UICONTROL Refresh Classifications]**&#x200B;刷新分类选项。
1. 在[!DNL Search Criteria]页面上，可在将站点搜索/促销数据提交到Adobe AnalyticsSAINT之前过滤该数据。 使用规则生成器接口在此处构建过滤器规则，然后单击&#x200B;**[!UICONTROL Next]**。
1. 在[!DNL Configure FTP]页面上，选择FTP服务器。 指定上载数据的频率，然后单击&#x200B;**[!UICONTROL Next]**。

   作为最佳实践，每个源都有自己的FTP帐户，以避免意外丢失数据。 您可以在此处创建新的Adobe Analytics FTP帐户。
1. 在[!DNL Verification]页面上，单击&#x200B;**[!UICONTROL Show Data View]**&#x200B;查看输出的数据视图表示。 如果存在任何实际的源文件，它们将列在此处，可供您下载。
1. 单击 **[!UICONTROL Close]**.

## 编辑Adobe AnalyticsSAINT源{#task_5BF34D02D0D14359B1CF4B3C1B0ACC84}

您可以编辑已创建的现有SAINT源的所有方面。

**编辑Adobe AnalyticsSAINT源**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**。
1. 在[!DNL Saint Classification Feeds]页面的&#x200B;**[!UICONTROL Name]**&#x200B;列下，在源旁边的下拉列表中，单击&#x200B;**[!UICONTROL Edit feed]**。
1. 在SAINT源对话框的&#x200B;**源名称**&#x200B;文本字段中，输入新源名称，然后单击&#x200B;**[!UICONTROL Next]**。

   此时，将保存信息源并将其添加到[!DNL SAINT Classification Feed]页面。 如果您选择，您可以退出，稍后编辑源以完成向导。
1. 在[!DNL Authentication]页面上，在相应的文本字段中指定Adobe Analytics公司名称、用户名和Web机密，然后单击&#x200B;**[!UICONTROL Next]**。

   确保已获得授权将Web API与Adobe Analytics一起使用。
1. 在&#x200B;**[!UICONTROL Report Suite]**&#x200B;页面上，选择报表包及其分类数据集，然后单击&#x200B;**[!UICONTROL Next]**。
1. 在[!DNL Field Maps]页面上，将Adobe Analytics分类与网站搜索/促销元数据字段进行映射，然后单击&#x200B;**[!UICONTROL Next]**。

   要调整Adobe Analytics分类，请单击&#x200B;**[!UICONTROL Edit]** Adobe Analytics分类以登录Adobe Analytics。 完成更改后，单击&#x200B;**[!UICONTROL Refresh Classifications]**&#x200B;刷新分类选项。
1. 在[!DNL Search Criteria]页面上，可在将站点搜索/促销数据提交到Adobe AnalyticsSAINT之前过滤该数据。 使用规则生成器接口在此处构建过滤器规则，然后单击&#x200B;**[!UICONTROL Next]**。
1. 在[!DNL Configure FTP]页面上，选择FTP服务器。 指定上载数据的频率，然后单击&#x200B;**[!UICONTROL Next]**。

   作为最佳实践，每个源都有自己的FTP帐户，以避免意外丢失数据。 您可以在此处创建新的Adobe Analytics FTP帐户。
1. 在[!DNL Verification]页面上，单击&#x200B;**[!UICONTROL Show Data View]**&#x200B;查看输出的数据视图表示。 如果存在任何实际的源文件，它们将列在此处，可供您下载。
1. 单击 **[!UICONTROL Close]**.

## 删除Adobe AnalyticsSAINT源{#task_5319B1F4CA1A406393CFD7AE97258CEB}

您可以删除不再需要或使用的现有Adobe AnalyticsSAINT源。

**删除Adobe AnalyticsSAINT源**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**。
1. 在[!DNL Saint Classification Feeds]页面的&#x200B;**[!UICONTROL Name]**&#x200B;列下，在要删除的源旁边的下拉列表中，单击&#x200B;**[!UICONTROL Delete feed]**。
1. 在“删除”对话框中，单击&#x200B;**是**&#x200B;以验证源删除。

## 查看Adobe AnalyticsSAINT源文件{#task_F0C8BADD25E14E5DB30BF31D1F879FDB}

您可以打开现有SAINT源的[!DNL Verification]页，以查看输出的视图表示。

如果存在任何实际的源文件，它们将列在此处，可供您以文本文件形式下载。

**视图Adobe AnalyticsSAINT源文件**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**。
1. 在[!DNL Saint Classification Feeds]页面的&#x200B;**[!UICONTROL Name]**&#x200B;列下，在源旁边的下拉列表中，单击&#x200B;**[!UICONTROL View Feed Files]**。
1. （可选）单击&#x200B;**[!UICONTROL Download File]**&#x200B;将源文件保存为文本文件。
1. 单击&#x200B;**[!UICONTROL Close]**&#x200B;返回至[!DNL SAINT Classification Feeds]页面。

## 测试Adobe AnalyticsSAINT源{#task_9864D69BE3824FC29C10B36EE4855D25}

您无需上传文件即可测试现有Adobe AnalyticsSAINT源。

请参阅[生成和上传Adobe AnalyticsSAINT源](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_47AED946AA964334A877FDC8D4F6F00A)。

请参阅[查看Adobe AnalyticsSAINT源文件](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_F0C8BADD25E14E5DB30BF31D1F879FDB)。

**测试Adobe AnalyticsSAINT源文件**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**。
1. 在[!DNL Saint Classification Feeds]页面的&#x200B;**[!UICONTROL Name]**&#x200B;列下，在源旁边的下拉列表中，单击&#x200B;**[!UICONTROL Test Feed (No file upload)]**。
1. 当源完成处理时，从源名称的下拉列表中，单击&#x200B;**[!UICONTROL View Feed Files]**。
1. 在[!DNL Verification]页面上，单击&#x200B;**[!UICONTROL Download File]**&#x200B;下载源文件。
1. 单击&#x200B;**[!UICONTROL Close]**&#x200B;返回至[!DNL SAINT Classification Feeds]页面。

## 生成和上传Adobe AnalyticsSAINT源{#task_47AED946AA964334A877FDC8D4F6F00A}

您可以为已创建的现有Adobe Analytics源生成并上传源文件。

请参阅[测试Adobe AnalyticsSAINT源](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_9864D69BE3824FC29C10B36EE4855D25)。

请参阅[查看Adobe AnalyticsSAINT源文件](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_F0C8BADD25E14E5DB30BF31D1F879FDB)。

**生成并上传Adobe AnalyticsSAINT源文件**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**。
1. 在[!DNL Saint Classification Feeds]页面的&#x200B;**[!UICONTROL Name]**&#x200B;列下，在源旁边的下拉列表中，单击&#x200B;**[!UICONTROL Generate and Upload Feed]**。
1. 当源完成处理时，从源名称的下拉列表中，单击&#x200B;**[!UICONTROL View Feed Files]**。
1. 在[!DNL Verification]页面上，单击&#x200B;**[!UICONTROL Download File]**&#x200B;下载源文件。
1. 单击&#x200B;**[!UICONTROL Close]**&#x200B;返回至[!DNL SAINT Classification Feeds]页面。
