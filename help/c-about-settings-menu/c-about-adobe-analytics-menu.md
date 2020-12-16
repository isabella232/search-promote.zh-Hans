---
description: 使用Adobe Analytics菜单设置Adobe Analytics度量验证、管理报告套件的Adobe Analytics度量，或通过接受来自外部来源的表格数据来使用SAINT来增强Adobe Analytics报告。
seo-description: 使用Adobe Analytics菜单设置Adobe Analytics度量验证、管理报告套件的Adobe Analytics度量，或通过接受来自外部来源的表格数据来使用SAINT来增强Adobe Analytics报告。
seo-title: 关于Adobe Analytics菜单
solution: Target
subtopic: Adobe Analytics
title: 关于Adobe Analytics菜单
topic: Settings,Site search and merchandising
uuid: 5536edf1-d3a4-47af-a307-6e46f385f738
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a
workflow-type: tm+mt
source-wordcount: '3448'
ht-degree: 1%

---


# 关于Adobe Analytics菜单{#about-the-adobe-analytics-menu}

使用Adobe Analytics菜单设置Adobe Analytics度量验证、管理报告套件的Adobe Analytics度量，或通过接受来自外部来源的表格数据来使用SAINT来增强Adobe Analytics报告。

## 设置Adobe Analytics度量身份验证{#task_8AA93F6273B747F9B4DE9E8DFBCBDC42}

要将Adobe Analytics指标纳入您的网站搜索／销售排名，您必须首先获得Adobe AnalyticsWeb服务登录名。 获取登录信息后，可以使用它在网站搜索／销售中设置Adobe Analytics身份验证。

**设置Adobe Analytics度量身份验证**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Authentication]**。
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
      <td colname="col1"> <p>Adobe Analytics公司 </p> </td> 
      <td colname="col2"> <p>用于登录您的Adobe Analytics帐户的公司名设置相同。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Web 服务用户名 </p> </td> 
      <td colname="col2"> <p>与您的Adobe Analytics帐户关联的Web服务用户名。 </p> <p>你可以在Adobe Analytics获得这些信息。 在Adobe Analytics菜单栏上，单击<span class="uicontrol"><b>Admin</b> </span> &gt; <span class="uicontrol"> <b>Admin Console</b> </span> &gt; <span class="uicontrol"> <b>公司</span> &gt; <span class="uicontrol"> <b>web服务</b> </span>。 </b>该信息位于“API访问信息”(API Access Information)表格中。 </span></p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Web服务共享机密 </p> </td> 
      <td colname="col2"> <p>与您的Adobe Analytics帐户关联的Web服务共享机密。 </p> <p>你可以在Adobe Analytics获得这些信息。 在Adobe Analytics菜单栏上，单击<span class="uicontrol"><b>Admin</b> </span> &gt; <span class="uicontrol"> <b>Admin Console</b> </span> &gt; <span class="uicontrol"> <b>公司</span> &gt; <span class="uicontrol"> <b>web服务</b> </span>。 </b>该信息位于“API访问信息”(API Access Information)表格中。 </span></p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;以还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于Adobe Analytics报告套件{#concept_1A51AEC5D40E459B813E7891D64B1BAE}

要在网站搜索／销售中使用Adobe Analytics报告套件数据，您必须首先在网站搜索／销售帐户中创建Adobe Analytics数据的副本。

您可以创建新的Adobe Analytics报告包定义，也可以视图或修改现有的Adobe Analytics报告包和关联指标。

首次从网站搜索／销售中访问Adobe Analytics时，将下载和缓存公司可用报告包的列表。 如果最近添加了新的报表包或删除了现有的报表包，您可以刷新报表包列表以重新下载报表包的列表。

## 添加Adobe Analytics报告套件{#task_6DE17305EA7146DA8C30FF8FDF68A3C0}

您可以选择一个Adobe Analytics报表包，在其上设置网站搜索／销售排名规则。

您可以选择的列表应与Adobe Analytics帐户中提供的报表包相对应。 您选择的报表包确定可在网站搜索／销售排名规则中使用的指标。

请参阅[有关规则排名](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397)。

添加Adobe Analytics报表包后，可编辑其量度。

请参阅[编辑报表包的Adobe Analytics度量](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664)。

**添加Adobe Analytics报表包**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**。
1. 在“Adobe Analytics报表包”页面上，单击&#x200B;**[!UICONTROL Add Report Suite]**。
1. 在新添加的表行的下拉列表中，选择所需的报表包。
1. 编辑报表包的Adobe Analytics指标。

## 编辑报表包{#task_360904CCBBB140238ADA036C3CC07664}的Adobe Analytics指标

要在网站搜索／销售中将Adobe Analytics指标纳入您的排名规则，您可以选择一个或多个与所选报表包关联的指标。 然后，您配置通过Adobe AnalyticsWeb服务获取度量数据的选项。

请参阅[添加Adobe Analytics报告套件](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0)。

请参阅[配置高级Adobe Analytics选项](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_C0FF2D69F59D44D8943A7831ED7FEC19)。

**编辑报表包的Adobe Analytics指标**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**。
1. 在[!DNL Adobe Analytics Report Suites]页面的&#x200B;**[!UICONTROL Actions]**&#x200B;列下，单击要配置其度量的报表包的&#x200B;**[!UICONTROL Edit]**。
1. 在[!DNL Edit Adobe Analytics Metrics]页面上，设置所需的度量。 度量名称旁没有星号(*)的度量是可选的。

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
      <td colname="col2"> <p>为Adobe Analytics报告套件名称提供“别名”名称。 如果在多个定义中使用相同的报表包，则此替代名称很有用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>选择报告类型 </p> </td> 
      <td colname="col2"> <p>指定要与所选报表包一起使用的报表类型值。 该值标识返回的每行结果的键。 </p> <p>报告类型也称为Adobe Analytics元素。 </p> <p>此度量是必需的。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>交叉引用字段名称 </p> </td> 
      <td colname="col2"> <p>指定一个元数据字段，其值将用作报表包数据中的查找“键”。 </p> <p>如果未选择任何值("— None —")，则此报告包的数据不能用于排名计算(<span class="uicontrol"> <b> Rules</b> </span> &gt; <span class="uicontrol"> <b> Rawing Rules</b> </span> &gt; <span class="uicontrol"> <b>Edit Rules&lt;a110/&gt; </span>)。</b> </p> <p>当您选择一个值时，此字段的值将用于使用您之前设置的选定报表类型值，将此报表包的Adobe Analytics数据交叉引用网站搜索／销售文档。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>搜索词报表 </p> </td> 
      <td colname="col2"> <p>允许您访问<b>阶段Adobe Analytics数据预览</b>页面，创建业务规则并模拟搜索词。 </p> <p>请参阅<a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0" type="task" format="dita" scope="local">预览Adobe Analytics数据</a>。 </p> <p>包含两个选项的每行都显示一个下拉菜单：<b>模拟搜索词</b>和<b>创建新业务规则</b>。 </p> <p>这两个选项都使用报表类型中的数据作为搜索词。 因此，仅当“报表类型”表示搜索词时，此功能才有意义。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>量度 </p> </td> 
      <td colname="col2"> <p>标识要下载的指标值，并在网站搜索／销售排名规则中使用。 </p> <p>当规则为“规则”时，您在此处配置的度量在<span class="uicontrol"> <b>规则</b> </span> &gt; <span class="uicontrol"> <b>排名规则</b> </span> &gt; <span class="uicontrol"> <b>编辑规则</b> </span>成员中心页上显示为选项数据类型设置为<span class="uicontrol">Adobe Analytics度量（数字）</span>。 这些选项显示报表包名称或报表包视图名称（如果指定）以及各个度量名称的组合。 </p> <p>此度量是必需的。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最小度量值 </p> </td> 
      <td colname="col2"> <p>允许您输入非零值以指定度量的最小值。 </p> <p>如果为空或零，则下载该度量的所有值；否则，当传递最小度量值时，此度量的下载将停止。 </p> <p>Adobe Analytics度量以降序检索。 </p> <p>单击<span class="uicontrol"> <b>+</b> </span>以添加其他度量定义；单击<span class="uicontrol"> <b>-</b> </span>以删除您不再需要或不需要的度量定义。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Adobe Analytics度量汇总期间（天） </p> </td> 
      <td colname="col2"> <p> 控制Adobe Analytics指标的日数，从昨天开始算起。 未尝试从当天获取数据。 </p> <p>默认值为 7。 </p> <p>此度量是必需的。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Adobe Analytics下载刷新频率（天） </p> </td> 
      <td colname="col2"> <p> 设置用于排名计算的Adobe Analytics数据下载之间的最小时间间隔。 </p> <p>忽略在下载刷新频率间隔内发生的索引触发的下载。 但是，手动下载会忽略此值。 </p> <p>如果将此值设置为默认值1，则Adobe Analytics数据在24小时内不会多次下载。 在下载刷新频率间隔内发生的所有搜索索引都使用上次下载的数据集。 </p> <p>此度量是必需的。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

   另请参阅[关于排名规则](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397)。
1. 单击 **[!UICONTROL Save Changes]**.

   您将返回到“已暂存[!DNL Adobe Analytics Report Suites]”页。
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;以还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 删除Adobe Analytics报告包{#task_0ACA172214D14654ABDB139F417B9F7D}

您可以使用删除从[!DNL Adobe Analytics Report Suites]页面中删除报表包。 删除报表包只会从网站搜索／销售服务器中删除数据的副本；它不会影响Adobe Analytics系统的数据。

**删除Adobe Analytics报表包**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**。
1. 在[!DNL Adobe Analytics Report Suites]页面的&#x200B;**[!UICONTROL Actions]**&#x200B;列下，单击&#x200B;**[!UICONTROL Delete]**&#x200B;以获取要删除的报表包。
1. 在[!DNL Adobe Analytics Delete Report Suite]页面上，单击&#x200B;**[!UICONTROL Delete]**。

## 预览Adobe Analytics数据{#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0}

您可以使用预览视图最近加载的Adobe Analytics指标。

表中的“行”列显示每行度量数据的编号，指示加载Adobe Analytics度量的原始顺序。

“产品”列显示与每行度量数据关联的Adobe Analytics元素。 此列中的值用于将您的网站搜索／销售页面与其相应的度量值关联，这在您的排名定义中进行了配置。

请参阅[有关规则排名](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397)。

请参阅[配置排名](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5)。

其余列显示与每个条目关联的度量值。

如果表为空，则表示尚未加载任何Adobe Analytics数据。 您可以关闭[!DNL Adobe Analytics Data Preview]页面，然后加载Adobe Analytics数据。

请参阅[加载Adobe Analytics数据](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181)。
如果表被指定为搜索词报告，则每行中都会出现一个小三角形。 单击下拉列表卡，然后选择**模拟搜索词**&#x200B;或&#x200B;**创建新业务规则**。 您选择的操作将应用于该行的搜索词，即驻留在第二列中的数据

**预览Adobe Analytics数据**

1. 在产品菜单中，执行下列操作之一：

   * 单击 **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**. 在[!DNL Adobe Analytics Report Suites]页面的[!DNL Actions]列下，单击&#x200B;**[!UICONTROL Preview]**，查看要视图其下载数据的报表包。

   * 单击 **[!UICONTROL Reports]** > **[!UICONTROL Adobe Analytics Terms Reports]**. 在[!DNL Adobe Analytics Terms Report]页面的[!DNL Actions]列下，单击&#x200B;**[!UICONTROL Preview]**，查看要视图其下载数据的报表包。

1. 在[!DNL Adobe Analytics Data Preview]页面上，使用页面顶部和底部的导航和查看选项来视图数据。

   单击表中的任意列标题，按升序或降序对数据进行排序。
1. 执行下列任一操作：

   * 单击&#x200B;**[!UICONTROL Download to Desktop]**&#x200B;下载表并将其保存为`.xlt`文件。

   * 在您完成预览Adobe Analytics数据后关闭该页面，并返回到之前查看的页面。

## 查看最近Adobe Analytics数据加载{#task_9C7D6E34BB6C4A40B7CA3EE36ACB0837}中的日志

您可以使用视图日志检查最新下载过程的Adobe Analytics数据日志文件。 您还可以使用日志视图来监视正在运行的下载。

请参阅[加载Adobe Analytics数据](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181)。

**从最近的Adobe Analytics视图加载中日志**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**。
1. 在[!DNL Adobe Analytics Report Suites]页面上，单击&#x200B;**[!UICONTROL View Log]**。 日志页，
1. 在[!DNL Adobe Analytics Data Log]页面上，使用页面顶部和底部的导航和查看选项视图日志信息。
1. 完成后，关闭该页面以返回[!DNL Adobe Analytics Report Suites]页面。

## 加载Adobe Analytics数据{#task_2F3C55189B0A4049AB2113F2291CC181}

您可以将配置的Adobe Analytics报告套件数据下载到网站搜索／销售中。

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
   <td colname="col2"> <p>显示上次数据加载尝试期间下载的度量数据行数。 </p> </td> 
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

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**。
1. 在[!DNL Stage Adobe Analytics Report Suites]页面上，单击&#x200B;**[!UICONTROL Load Adobe Analytics Data]**。
1. 在&#x200B;**[!UICONTROL Adobe Analytics Data Load]**&#x200B;页面上，执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL Start Load]**&#x200B;以开始加载操作。

      在数据加载操作期间，**Progress**&#x200B;行提供有关其进度的信息。

   * 单击&#x200B;**[!UICONTROL Stop Load]**&#x200B;以停止加载操作。

1. 单击&#x200B;**[!UICONTROL Close]**&#x200B;返回至[!DNL Stage Adobe Analytics Reports Suite]页面。

## 刷新报表包列表{#task_EA6215D438CA4185B106657D9712ED34}

首次从网站搜索／销售用户界面访问Adobe Analytics时，将下载和缓存公司可用的Adobe Analytics报告套件的列表。 如果最近添加了新的报表包或删除了现有报表包，则可以使用“刷新报表包”列表更新站点搜索／销售中当前显示的列表。

请参阅[添加Adobe Analytics报告套件](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0)。

请参阅[删除Adobe Analytics报告包](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_0ACA172214D14654ABDB139F417B9F7D)。

**刷新报表包列表**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**。
1. 在[!DNL Adobe Analytics Report Suites]页面上，单击&#x200B;**[!UICONTROL Refresh Report Suite List]**。

## 配置高级Adobe Analytics选项{#task_C0FF2D69F59D44D8943A7831ED7FEC19}

您可以使用[!DNL Advanced Adobe Analytics Options]来控制旨在帮助您优化Adobe Analytics报告包下载过程行为的设置。

请参阅[编辑报表包的Adobe Analytics度量](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664)。

**配置高级Adobe Analytics选项**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Advanced Options]**。
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
      <td colname="col1"> <p>最大行数，任意度量 </p> </td> 
      <td colname="col2"> <p>一个优化设置，可防止下载太多Adobe Analytics数据。 </p> <p>如果将此选项设置为非零值，则当每个度量所获取的总行数超过指定值时，将停止Adobe Analytics数据提取。 </p> <p>默认值为0;未应用最大值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>度量重复提取大小（行） </p> </td> 
      <td colname="col2"> <p> 控制每次要获取的Adobe Analytics度量值数。 度量数据行被重复读取，直到检索到所有数据或达到最大行限制为止。 </p> <p>通常，您无需更改此设置。 但是，您会发现优化网站完整重新索引的度量下载阶段很有帮助。 </p> <p>默认值为 5000。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;以还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于SAINT分类源{#concept_C55609DA24914BBC92CD90ED0259199D}

您可以使用Adobe AnalyticsSAINT通过接受来自外部来源的表格数据来增强您的分析报告。 例如，您可以使用网站搜索／销售从其自己的索引中检索数据并将该数据导出到Adobe Analytics。

要在网站搜索／销售中成功使用Adobe AnalyticsSAINT功能，请注意以下要求：

* 您必须拥有Adobe Analytics公司和报告套件。

   请参阅[关于Adobe Analytics菜单](../c-about-settings-menu/c-about-adobe-analytics-menu.md#concept_5FD2D13C9D0D40988E6E51480D690411)。
* Adobe Analytics用户帐户必须具有修改报告包的权限。

   请参阅[设置Adobe Analytics度量身份验证](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_8AA93F6273B747F9B4DE9E8DFBCBDC42)。
* Adobe Analytics用户必须属于Web API组，以便使用Adobe AnalyticsWeb API。
* 搜索索引必须包含Adobe Analytics可以使用的数据，如数据格式正确。

在创建源之前，请查看以下问题和信息，以便您能够成功完成SAINT源向导：

* 您要使用哪个报表包？
* 您要为哪些分类集（如产品、e-var等）提供数据？
* 报表中存在哪些分类？ 该问题的答案取决于网站搜索／销售中随时可获得的数据类型以及Adobe Analytics报告所需的报告类型。
* SAINT将站点搜索／销售中的数据接受为文本类型。 这些数据的格式影响Adobe Analytics报告的列报。

## 创建Adobe AnalyticsSAINT源{#task_914B5AB821E84627953D8EF9339A7DD0}

您可以使用Adobe AnalyticsSAINT通过接受来自外部来源的表格数据来增强Adobe Analytics报告。

例如，您可以使用网站搜索／销售从其自己的索引中检索数据并将该数据导出到Adobe Analytics。

**创建Adobe AnalyticsSAINT源**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**。
1. 在[!DNL SAINT Classification Feeds]页面上，单击&#x200B;**[!UICONTROL Create SAINT Feed]**。
1. 在[!DNL Create Feed]对话框的&#x200B;**源名称**&#x200B;文本字段中，输入新源名称，然后单击&#x200B;**[!UICONTROL Next]**。

   此时，将保存源并将其添加到[!DNL SAINT Classification Feed]页面。 如果您选择，您可以退出，稍后编辑源以完成向导。
1. 在[!DNL Authentication]页面上，在相应的文本字段中指定Adobe Analytics公司名、用户名和Web机密，然后单击&#x200B;**[!UICONTROL Next]**。

   确保已获得授权将Web API与Adobe Analytics一起使用。
1. 在&#x200B;**[!UICONTROL Report Suite]**&#x200B;页面上，选择报表包及其分类数据集，然后单击&#x200B;**[!UICONTROL Next]**。
1. 在[!DNL Field Maps]页面上，将Adobe Analytics分类与网站搜索／销售元数据字段进行映射，然后单击&#x200B;**[!UICONTROL Next]**。

   要调整Adobe Analytics分类，请单击&#x200B;**[!UICONTROL Edit]** Adobe Analytics分类以登录Adobe Analytics。 完成更改后，单击&#x200B;**[!UICONTROL Refresh Classifications]**&#x200B;以刷新分类选项。
1. 在[!DNL Search Criteria]页面上，可以过滤网站搜索／销售中的数据，然后再将其提交给Adobe AnalyticsSAINT。 使用规则构建器接口在此处构建过滤器规则，然后单击&#x200B;**[!UICONTROL Next]**。
1. 在[!DNL Configure FTP]页面上，选择FTP服务器。 指定上传数据的频率，然后单击&#x200B;**[!UICONTROL Next]**。

   作为最佳实践，每个源都有自己的FTP帐户，以避免意外丢失数据。 您可以在此处新建一个Adobe AnalyticsFTP帐户。
1. 在[!DNL Verification]页面上，单击&#x200B;**[!UICONTROL Show Data View]**&#x200B;查看输出的视图表示。 如果存在任何实际的源文件，它们将列在此处，可供您下载。
1. 单击 **[!UICONTROL Close]**.

## 编辑Adobe AnalyticsSAINT源{#task_5BF34D02D0D14359B1CF4B3C1B0ACC84}

您可以编辑已创建的现有SAINT源的所有方面。

**编辑Adobe AnalyticsSAINT源**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**。
1. 在[!DNL Saint Classification Feeds]页面的&#x200B;**[!UICONTROL Name]**&#x200B;列下，在源旁的下拉列表下，单击&#x200B;**[!UICONTROL Edit feed]**。
1. 在SAINT源对话框的&#x200B;**源名称**&#x200B;文本字段中，输入新源名称，然后单击&#x200B;**[!UICONTROL Next]**。

   此时，将保存源并将其添加到[!DNL SAINT Classification Feed]页面。 如果您选择，您可以退出，稍后编辑源以完成向导。
1. 在[!DNL Authentication]页面上，在相应的文本字段中指定Adobe Analytics公司名、用户名和Web机密，然后单击&#x200B;**[!UICONTROL Next]**。

   确保已获得授权将Web API与Adobe Analytics一起使用。
1. 在&#x200B;**[!UICONTROL Report Suite]**&#x200B;页面上，选择报表包及其分类数据集，然后单击&#x200B;**[!UICONTROL Next]**。
1. 在[!DNL Field Maps]页面上，将Adobe Analytics分类与网站搜索／销售元数据字段进行映射，然后单击&#x200B;**[!UICONTROL Next]**。

   要调整Adobe Analytics分类，请单击&#x200B;**[!UICONTROL Edit]** Adobe Analytics分类以登录Adobe Analytics。 完成更改后，单击&#x200B;**[!UICONTROL Refresh Classifications]**&#x200B;以刷新分类选项。
1. 在[!DNL Search Criteria]页面上，可以过滤网站搜索／销售中的数据，然后再将其提交给Adobe AnalyticsSAINT。 使用规则构建器接口在此处构建过滤器规则，然后单击&#x200B;**[!UICONTROL Next]**。
1. 在[!DNL Configure FTP]页面上，选择FTP服务器。 指定上传数据的频率，然后单击&#x200B;**[!UICONTROL Next]**。

   作为最佳实践，每个源都有自己的FTP帐户，以避免意外丢失数据。 您可以在此处新建一个Adobe AnalyticsFTP帐户。
1. 在[!DNL Verification]页面上，单击&#x200B;**[!UICONTROL Show Data View]**&#x200B;查看输出的视图表示。 如果存在任何实际的源文件，它们将列在此处，可供您下载。
1. 单击 **[!UICONTROL Close]**.

## 删除Adobe AnalyticsSAINT源{#task_5319B1F4CA1A406393CFD7AE97258CEB}

您可以删除您不再需要或使用的现有Adobe AnalyticsSAINT源。

**删除Adobe AnalyticsSAINT源**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**。
1. 在[!DNL Saint Classification Feeds]页面的&#x200B;**[!UICONTROL Name]**&#x200B;列下，在要删除的源旁的下拉列表中，单击&#x200B;**[!UICONTROL Delete feed]**。
1. 在删除对话框中，单击&#x200B;**是**&#x200B;以验证源删除。

## 查看Adobe AnalyticsSAINT源文件{#task_F0C8BADD25E14E5DB30BF31D1F879FDB}

您可以打开现有SAINT源的[!DNL Verification]页面，查看输出的视图表示。

如果存在任何实际的源文件，它们将列在此处，可供您以文本文件形式下载。

**视图Adobe AnalyticsSAINT源文件**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**。
1. 在[!DNL Saint Classification Feeds]页面的&#x200B;**[!UICONTROL Name]**&#x200B;列下，在源旁的下拉列表下，单击&#x200B;**[!UICONTROL View Feed Files]**。
1. （可选）单击&#x200B;**[!UICONTROL Download File]**&#x200B;将源文件另存为文本文件。
1. 单击&#x200B;**[!UICONTROL Close]**&#x200B;返回至[!DNL SAINT Classification Feeds]页面。

## 测试Adobe AnalyticsSAINT源{#task_9864D69BE3824FC29C10B36EE4855D25}

您可以测试现有的Adobe AnalyticsSAINT源，而无需上传文件。

请参阅[生成和上传Adobe AnalyticsSAINT源](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_47AED946AA964334A877FDC8D4F6F00A)。

请参阅[查看Adobe AnalyticsSAINT源文件](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_F0C8BADD25E14E5DB30BF31D1F879FDB)。

**测试Adobe AnalyticsSAINT源文件**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**。
1. 在[!DNL Saint Classification Feeds]页面的&#x200B;**[!UICONTROL Name]**&#x200B;列下，在源旁的下拉列表下，单击&#x200B;**[!UICONTROL Test Feed (No file upload)]**。
1. 当源完成处理后，从源名称的下拉列表中单击&#x200B;**[!UICONTROL View Feed Files]**。
1. 在[!DNL Verification]页面上，单击&#x200B;**[!UICONTROL Download File]**&#x200B;下载源文件。
1. 单击&#x200B;**[!UICONTROL Close]**&#x200B;返回至[!DNL SAINT Classification Feeds]页面。

## 生成和上传Adobe AnalyticsSAINT源{#task_47AED946AA964334A877FDC8D4F6F00A}

您可以为已创建的现有Adobe Analytics源生成并上传源文件。

请参阅[测试Adobe AnalyticsSAINT源](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_9864D69BE3824FC29C10B36EE4855D25)。

请参阅[查看Adobe AnalyticsSAINT源文件](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_F0C8BADD25E14E5DB30BF31D1F879FDB)。

**生成并上传Adobe AnalyticsSAINT源文件**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**。
1. 在[!DNL Saint Classification Feeds]页面的&#x200B;**[!UICONTROL Name]**&#x200B;列下，在源旁的下拉列表下，单击&#x200B;**[!UICONTROL Generate and Upload Feed]**。
1. 当源完成处理后，从源名称的下拉列表中单击&#x200B;**[!UICONTROL View Feed Files]**。
1. 在[!DNL Verification]页面上，单击&#x200B;**[!UICONTROL Download File]**&#x200B;下载源文件。
1. 单击&#x200B;**[!UICONTROL Close]**&#x200B;返回至[!DNL SAINT Classification Feeds]页面。
