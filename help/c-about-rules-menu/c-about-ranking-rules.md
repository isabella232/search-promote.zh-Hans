---
description: 您可以使用排名规则根据包含的元标记内容和相关的Adobe Analytics指标来控制客户搜索结果的相对位置或排名。
seo-description: 您可以使用排名规则根据包含的元标记内容和相关的Adobe Analytics指标来控制客户搜索结果的相对位置或排名。
seo-title: 关于排名规则
solution: Target
subtopic: Ranking Rules
title: 关于排名规则
topic: Rules,Site search and merchandising
uuid: 21962f9a-1d9c-442f-a6c4-5f452436c640
translation-type: tm+mt
source-git-commit: f4f69e6bdb37fb39045f8f25cffa4bf616834e54

---


# 关于排名规则{#about-ranking-rules}

您可以使用排名规则根据包含的元标记内容和相关的Adobe Analytics指标来控制客户搜索结果的相对位置或排名。

## 使用排名规则 {#concept_F555C076759B4E81B925441CFE707397}

您可以根据每个文档的内容定义排名规则，以影响文档在搜索结果中的相对位置。 您可以根据元标记内容、Adobe Analytics指标（如果您的帐户配置为与Adobe Analytics配合使用）或Adobe Analytics HBX指标（如果帐户配置为与Adobe Analytics HBX配合使用）来制定排名规则。

您可以设置包含具有所需特征（如特定品牌名称或价格）的元标记的网页，或具有所需Adobe Analytics关键绩效指标（如唯一查看器）的网页，以获得比不具有所需特征的网页更高的排名。 通过添加或编辑排名规则，然后重新为网站构建索引，可轻松更新“理想”特征。

如果定义了多个类型为“排名”的元标记，则可以创建单独的规则集合以用于计算各种排名字段。 您可以添加一个排名规则组，然后将该组分配给您定义的一个排名字段。 规则组通常包含一个或多个规则定义，但也可以引用其他规则组，因此您可以创建一个或多个常用规则组，这些规则组在计算多个级别时共享。

请参 [阅添加排名规则组](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)。

正排名值会推动搜索结果向顶部靠拢；负秩值将搜索结果降低到搜索结果的底部。 排名值的正常范围是1.0，这是搜索结果中的最大升级，而-1.0是最高降级。 虽然可以通过编辑元数据定义中的排名字段来自定义此范围，但通常不需要这种自定义。

请参阅 [关于定义](../c-about-settings-menu/c-about-metadata-menu.md#concept_AE48035C210145169BE067D396975620)。

如果您在“设置”>“元数据”>“定义”下定义了多个排名字段，则可以选择创建其他一组排名规则，每个排名字段各一个。 您可以定义其他排名规则集，而无需直接与排名字段关联。 这种灵活性允许您创建在计算一个或多个排名值时可以共享的通用规则集。

**重要说明**:在使用排名规则之前，必须先完成几个帐户配置步骤。

请参阅 [配置排名](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5)

## 配置排名 {#task_4CEBC13925B047FC95BDC217B48089C5}

在使用排名规则之前，必须先完成几个帐户配置步骤。

**配置排名**

1. 从以下选项中进行选择：

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>任务 </p> </th> 
      <th colname="col2" class="entry"> <p>配置 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>创建基于元标记的排名规则 </p> </td> 
      <td colname="col2"> <p> 
      <ol id="ol_28ABB980143948DFA79AC4360AAB7556"> 
      <li id="li_544075CFA0964C6F8FAF7941AAA9ECCC"> 在产品菜单中，单击 <span class="uicontrol"> 设置 </span> &gt;元数 <span class="uicontrol"> 据 </span> &gt;定 <span class="uicontrol"> 义 </span>。 </li> 
      <li id="li_F237F13B89E8425080C15D3BD697652C"> 在“定义”页面上，单击“ <span class="uicontrol"> 添加新字段” </span>。 </li> 
      <li id="li_2A839874D71D45FEA661B3D3B8BE2A86"> 在“添加字段”页面的“字段名 <span class="uicontrol"> 称”文本 </span> 字段中，键入 
      <userinput>
        秩 
      </userinput>;在“元标 <span class="uicontrol"> 记名称”文本 </span> 字段中，键入 
      <userinput>
        秩 
      </userinput>;在“数 <span class="uicontrol"> 据类型” </span> 下拉列表中，选择 <span class="uicontrol"> 排名 </span>。 保留所有其他字段选项。 <p>请参阅后端搜 <span class="codeph"> 索CGI参数 </span> 中的 <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> 查询参数sp_sr </a>。 </p> </li> 
      <li id="li_8E91AF4BE51A4A41ABBF9680DDE0B7CE">单击<span class="uicontrol">添加</span>。 </li> 
      </ol> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>创建基于Adobe Analytics指标的排名规则 </p> </td> 
      <td colname="col2"> <p> 
      <ol id="ol_BE57CBC303D941778B10D855ADC93C68"> 
      <li id="li_8DF5D8F924B24ECBBD2D93C76C69D00C"> 确保您已从网站搜索／销售中设置Adobe Analytics身份验证。 <p>请参 <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_8AA93F6273B747F9B4DE9E8DFBCBDC42" type="task" format="dita" scope="local"> 阅设置Adobe Analytics指标身份验证 </a>。 </p> </li> 
      <li id="li_CF7DD073FC5A432DADBD282AA8BB9920"> 选择并添加可用的报告套件。 <p>请参 <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0" type="task" format="dita" scope="local"> 阅添加Adobe Analytics报告套件 </a>。 </p> </li> 
      <li id="li_9A63448577D04E028DF211D8715F943A"> 配置要用于创建新排名规则的Adobe Analytics指标列表。 <p>请参 <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664" type="task" format="dita" scope="local"> 阅编辑报告包的Adobe Analytics指标 </a>。 </p> </li> 
      <li id="li_1ACA3611D9B44AC394604CD89209C966"> 为您的网站页面加载初始Adobe Analytics指标。 <p>请参 <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181" type="task" format="dita" scope="local"> 阅加载Adobe Analytics数据 </a>。 </p> </li> 
      </ol> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 添加一个或多个排名规则。

   请参 [阅添加排名规则](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A)。

1. 单 **[!UICONTROL regenerate your staged site index]** 击以对网站执行完整索引(从 **[!UICONTROL Index]** > **[!UICONTROL Full Index]**)。

   请参 [阅运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   请参 [阅配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. 检查> **[!UICONTROL Settings]** >中Rank（排名）列中的值， **[!UICONTROL Metadata]****[!UICONTROL Definitions]** 以确认您的排名规则是否正确应用。

## 关于按年龄对文档进行排序 {#topic_770815CF1B2A491F83FF765871B6F1B8}

可以按HTML文档的年龄使用指数衰减函数对其进行排名。 衰减速率使用选定的半衰期常数指定，该值降低到其初始值的一半之前必须经过的时间。

年龄等级基于以下两个等式：

`K = -ln(2) / H`

`RANK = e^(K * T)`

变量 `H` 和 `T` 是此函数的输入：是期 `H` 望的半衰期，是文 `T` 档的年龄，以秒为单位表示。 `K` 是计算的半衰期， `RANK` 是指定年龄值的指数衰减。 结果值为0到1。 与较旧的文档相比，较新文档的排名值更接近1。 理论上，文档永远不应达到0的值，但舍入错误可能导致结果变为0。

## 使用年龄排名的要求 {#section_D716507D589442C6B7848892BD28F966}

* 您的帐户应已正确配置以进行排名。 如果未配置，请参阅配 [置排名](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5)。
* HTML文档必须有一个HTML meta标记字段，该字段表示其出生日期、开始日期作为时间戳或某些其他有意义的日期值。
* 在“添加或编辑排 `search_get_age_rank()`名规则”页面中指定的特殊内置函数用于计算文档的年龄等级。 下几节详细描述了年龄排序函数的一般用途。 最后，给出了一个实例，说明了年龄排序的特点。

## 在“添加排名规则”页或“编辑排名规则”页使用search_get_age_rank() {#section_34BC5276F2AB4419AD92872A397CA0AF}

指定 `search_get_age_rank()` 如下：

`search_get_age_rank(Birthdate#Half_Life#Default_Rank)`

* 出生日期——文件的出生日期或开始日期必须是根据字段的日期格式设置的日期字符串。 此日期格式化字符串必须是字段引用，如中所示 `{field_name}`。
* Half_Life —— 半衰期是该值降至其初始值的一半之前必须经过的时间。 此值以天数表示，它是整数或浮点数。
* Default_Rank —— 如果出生日期无效或日期在将来，则使用默认排名作为安全网。 如果其关联的元数据字段也具有有效的默认值，则不能使用此默认值。 此处的值是浮点数或整数。 如果您遇到使用默认值的问题，请参阅下面的建议。

请参 [阅添加排名规则](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A)。

See [Editing a ranking rule](../c-about-rules-menu/c-about-ranking-rules.md#task_5EBF55A43D6545FEA46BAE5E586FA275).

**示例**

在以下示例中，

`search_get_age_rank({birthdate}#28#0.20)`

文档字段中包含的日 `birthdate` 期将作为时间戳传入。 半衰期为28天。 如果日期无效，则默认的排名值为0.20。

请参阅添加排名 [规则中的选项表](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A)。

在“添加排名规则”页面或“编辑排名规则”页面的“值／排名”部分，您只能与自定义 `search_get_age_rank` 的规则一起使用。 因此，请务必从“值 **** /排名”下拉列表中选择“自定义”。 当规则使用年龄排名函数时，规则的值部分不允许有空格。 请确保函数参数中或它们之间没有空格。 而且，任何数学或条件运算符之间没有空格。

以下是值／排名规则的示例——与文本字段关联的规则：

`regexp .* search_get_age_rank({other_field}#365#0.20)`

此示例假定 `other_field` 包含日期值。 如果此字段本身不是日期类型字段，则此值将使用与预定义的“日期”字段关联的日期格式进行解释。 否则，将使用此字段的日期格式。 每当文档的字段（规则的数据源标识的字段）为非空并且函数的返回值（从0到1）是指定的秩时，都会使用此值／秩条目。

对于与数字字段关联的规则，特别是日期字段：

`9999999999 search_get_age_rank({other_field}#365#0.20)`

在处理每个文档时，中的值 `other_field` 将使用字段的日期格式定义转换为Unix的“纪元”表单。 此值用于调 `search_get_age_rank()` 用。 由于每个&quot;纪元&quot;值小于999999999（至少目前），规则只提供函数的返回值（从0到1）作为等级。

在前面两个示例中，规则的数据源与函数中使用的字段是典型的——在 `search_get_age_rank()` 此 `other_field` 例中。

## 将年龄排名纳入排名规则的一个实例 {#section_A86D909687CC45E19D4EA7A4A9283F28}

以下是如何将年龄排名集成到排名规则中的示例。 该示例还显示年龄排序函数的原始结果和排名规则的结果。 该示例假定：

* 已搜索的网页具有名为“出生日期”的HTML meta标签。 此标记的内容是与文档相关的时间戳。
* 元数据定义有一个为出生日期标记定义的元标记字段。 此字段设置为“日期”类型。

**排名规则**

请参 [阅添加新的元标记字段](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。

现在，您添加了新的排名规则。 该规则定义为在文档中使用“出生日期”字段。 新的排名规则添加了以下属性集：

* 数据源类型：Meta标签
* 数据源名称：出生日期
* 权重／条件：10 —— 最大重要性
* 值／排名：9999999999search_get_age_rank({burdate}#14#0.10)
* 默认排名：-1

这条规则做了几件事。 规则的权重设置为10。 秩值只是年龄秩函数的结果，即0到1的值。 不能将空格用于 `search_get_age_rank()`。 另外，请注意，字段“出生日期”用大括号括起来。 最后，保存此规则时，值／排名定义中的逗号将替换为字 `#` 符；这种行为是正常的。

**查看结果**

使用“数据视图”功能可快速查看年龄等级函数的结果。 添加相应的元数据字段。 在示例中， `age_val` 和 `myrank` 是应添加到数据视图的两个元数据字段。 该字 `myrank` 段显示年龄排名如何影响排名值。 该 `age_val` 字段显示该文档的指数衰减函数的原始输出。

## 默认值 {#section_CB109EF78F914E92955D512ACFC3310E}

以下是与函数相关的三个默认值 `search_get_age_rank()`:

* 可以输入到函数本身中的默 `search_get_age_rank()` 认值。
* “排名”规则的默认排名值。
* 元数据定义中的默认值。

根据故障发生的位置，您可能会得到不同的默认值。

例如，如果正确实施了排名和筛选，则元数据定义中的默认值永远不会发生。 当该元数据字段不存在有效或已知的内容时，此默认值是最后的值。 当引用其自己的关联标记并且该标记在文档中 `search_get_age_rank()` 缺失时，可能会显示排名规则的默认值。 在这种情况下，此规则将直接转到规则的默认值。 如果年龄排序函数引用另一个排名规则的标记，则如果引用的标记缺失或无效，则可能使用传递到该年龄排序函数的默认值。

## 添加排名规则 {#task_A132789FD4E5423DAD090DCDA7311E8A}

您可以添 [!DNL Ranking Rules] 加内容，以根据每个网页的内容影响网页在搜索结果中的相对位置。

请参阅 [配置排名](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5)。

**添加排名规则**

1. 在产品菜单中，单击 **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**。
1. （可选）如果您已创建规则组并将规则添加到该组，请在页面的下拉列表中 [!DNL Define Ranking Rules]**[!UICONTROL Select Rule Group]** ，选择包含要编辑的规则的规则组。

   请参 [阅添加排名规则组](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)。
1. 在页 [!DNL Define Ranking Rules] 面上，单 **[!UICONTROL Add Rule]** 击以添加新的排名规则，或添加对规则集的引用。
1. 在页 [!DNL Add Ranking Rule] 面上，设置所需的选项。 标有星号(*)的字段为必填字段。

   您选择的数据源类型会影响下拉列表中 [!DNL Data Source Name] 的可用选项。 例如，如果您选择 **[!UICONTROL Meta Tag]** 作为数据源类型，则数据源名称将引用网站页面上元标记的名称。 如果您选 **[!UICONTROL Adobe Analytics Metric (Number)]**&#x200B;择，数据源名称将引用您在报表包中选择的其中一个Adobe Analytics度量名称，该名称位于站点搜索／销售的页面 **[!UICONTROL Edit Adobe Analytics Metrics]** 上。

   请参 [阅编辑报告包的Adobe Analytics指标](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664)。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>数据源类型 </p> </td> 
      <td colname="col2"> <p>确定用作此排名规则输入的数据源的特性。 </p> <p>您可以从中选择的数据源类型包括： 
      <ul id="ul_B0A97BF0E314495985F44A642C86918D"> 
      <li id="li_4D8BDE32853540809AE78FF5FF5677A1"> <span class="uicontrol"> Meta标签 </span> <p> 此规则基于数字数据或存储在网站页面上的命名meta标签中的文本数据。 </p> </li> 
      <li id="li_4976C31D67254C7F81D554EC49DDBB40"> <span class="uicontrol"> Adobe Analytics指标（数字） </span> <p>此规则基于与您的网站页面关联的数字Adobe Analytics量度。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Data Source Name（数据源名称） </p> </td> 
      <td colname="col2"> <p>如果选择 <span class="uicontrol"> 元标签 </span> 作为数据源类型，则这是在网站的页面中找到的元标签的名称。 下拉菜单中的名称来自在“设置”&gt;“元数据”&gt;“定义”中配置的已定义元数据值列表。 </p> <p>请参 <a scope="local" href="../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5" type="task" format="dita"> 阅添加新的元标记字段 </a>。 </p> <p>如果选择Adobe Analytics量度（数字）作为数据源类型，则此为Adobe Analytics量度的名称。 下拉菜单中的名称来自在“设置”&gt;“Adobe Analytics”&gt;“指标”&gt;“编辑”中配置的已定义可用Adobe Analytics指标的列表。 </p> <p>请参 <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664" type="task" format="dita" scope="local"> 阅编辑报告包的Adobe Analytics指标 </a>。 </p> <p>如果您选择的Adobe Analytics度量名称尚未在“设置” <span class="uicontrol"></span> &gt; <span class="uicontrol"> “元数据” </span> &gt; <span class="uicontrol"></span>“定义”中定义，则会显示一个文本字段和“添加”按钮。 输入元数据字段名称（元数据字段名称不能超过20个字符），然后单击“添 <span class="uicontrol"> 加” </span>。 </p> <p>当多个Adobe Analytics键碰到页面时，就像一个显示多个产品的产品页面一样，组合方案指定如何处理与该页面关联的多个Adobe Analytics度量值。 选择下列选项之一： </p> <p> 
      <ul id="ul_D6E51748BB3949048A37C1895F2C0A58"> 
      <li id="li_04F00F382A264C96A519B0D975E25E94"> <span class="uicontrol">“总计”</span> <p>返回度量值的和。 </p> </li> 
      <li id="li_FA44219B663F4CC197BD3A094EB84396"> <span class="uicontrol"> 平均 </span> <p>返回值的平均值（总和除以值数）。 </p> </li> 
      <li id="li_F0EAAE1EA1754FFEB30F611E5550097B"> <span class="uicontrol"> 最大值 </span> <p>返回值中的最大值。 </p> </li> 
      <li id="li_38E3E3F3D9AF4C57803B84B60223FB9D"> <span class="uicontrol"> 首次 </span> <p>返回与第一个键对应的值。 </p> </li> 
      <li id="li_4AEE470CE6BB4D899E975915EC226624"> <span class="uicontrol"> 上次 </span> <p>返回与最后一个键对应的值。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>权重／条件 </p> </td> 
      <td colname="col2"> <p>包含简单、单个规则权重编号或规则权重编号和测试条件的成对列表。 </p> <p>规则权重数是从1到10的值，它指示该排序规则相对于其它排序规则在确定文档的整体排序中的重要性。 规则权重越高表示重要性越高。 零(0)的权重将忽略该规则。 </p> <p>从下 <span class="uicontrol"> 拉列 </span> 表中选择“自定义”，通过定义规则权重／测试条件对列表，为不同页面自定义规则权重。 测试条件是用于测试数据源值的Perl的片段，或在自定义筛选器脚本中定义的全局变量（例如，价格、品牌、季节或页面视图，如下例所示）。 如果测试条件的计算结果为“true”，则应用关联的规则权重值。 如果测试条件的计算结果为“false”，则计算列表中的下一个条件。 <code> 0&nbsp;({price}&nbsp;&gt;&nbsp;50.00)&nbsp;&amp;&amp;&nbsp;({brand}=~/Kuhl/)5&nbsp;{season}&nbsp;=~&nbsp;/Fall/10&nbsp;{pageviews}&nbsp;&gt;&nbsp;1000005 </code>在上述自定义创建的权重／条件示例中，如果第一个测试条件的计算结果为“true”，则应用规则权重0。 即，价格包含大于50的值，且品牌包含“Kuhl”)。 如果第一个测试条件的计算结果为“false”，则计算下一个条件。 如果未满足以前的条件，则分配规则权重5。 </p> <p>您应始终在列表末尾提供规则权重，且没有条件。 如果不这样做，则规则的权重为0，如果条件测试的结果都不为“true”。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>值／排名 </p> </td> 
      <td colname="col2"> <p>由内置的排名功能之一或可能的数据源内容以及所需的排名组成。 </p> <p>如果选择 <span class="uicontrol"> Adobe Analytics Metric(Number) </span> 作为数据源类型，将显示一个包含以下选项的下拉列表： 
      <ul id="ul_104906B6AA8547BAB6979AA37C4FAB90"> 
      <li id="li_7656A2855A054DB8B64E90FE501517AA"> <span class="uicontrol"> 按顺序自动排名（默认） </span> <p>根据文档的Adobe Analytics Metric计算基于文档的相对位置的排名。 例如，文档与排名最前的文档的位置越近，其排名就越高。 </p> </li> 
      <li id="li_1A7D60EA6965434AA6D39B215C158306"> <span class="uicontrol"> 按值自动排名 </span> <p>根据文档的Adobe Analytics Metric，根据文档的相对值计算排名。 例如，文档值与排名最前的文档值越近，其排名就越高。 </p> </li> 
      <li id="li_457DE44D6ADA40619DC77220BF12318E"> <span class="uicontrol"> 自定义 </span> <p>指定自定义设置。 例如，名为“brand”的数据源可能包含特定产品的品牌名称。 您可以通过列出每个品牌及其排名来指定其相对重要性。 </p> </li> 
      </ul> </p> <p>自动排名计算返回的排名值在0.0（最低）到1.0（最高）范围内。 它们不会根据在“设置”&gt;“元数据”&gt;“定义”下为“排名”字段定义的范围进行调整。 </p> <p>在以下示例中，如果特定搜索结果的品牌数据源与“DKNY”完全匹配，则该结果的应用排名为0.5。否则，如果品牌为“级别”，则应用的排名为0.1。数据源内容必须与设置的值匹配。 换句话说，如果数据源内容是“Levis Corp.”，则它将不匹配值“Levis”。 忽略大小写，因此“DKNY”与“dkny”和“Dkny”匹配。 <code> DKNY&nbsp;0.5 Levis&nbsp;0.1 Lee&nbsp;0.2 </code> </p> <p>作为更高级的选项，您可以将值指定为正则表达式。 例如，假设您的某些网站页面包含品牌值“Levis”，而其他网站页面包含品牌值“Levis jeans”。 您可以使用用关键字指定的正则表达式 
      <userinput>
        regexp 
      </userinput>. </p> <p>请参阅 <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> 正则表达式 </a>。 </p> <p>在以下示例中，将为包含品牌内容“Levis jeans”的搜索结果文档分配0.1的等级。与标准比较一样，正则表达式将忽略大小写。 <code> DKNY&nbsp;0.5 regexp&nbsp;Levis.*&nbsp;0.1 Lee&nbsp;0.2 </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>默认排名 </p> </td> 
      <td colname="col2"> <p> 指定对与任何指定值不匹配的搜索结果文档应用的排名。 在上例中，将为包含“品牌”数据源且包含“gap”的搜索结果文档分配默认的排名值，因为“gap”与任何定义的值都不匹配。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>注释 </p> </td> 
      <td colname="col2"> <p>添加与您创建的排名规则定义或规则组定义相关的信息。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

   有效排名值的范围通常为-1.0到1.0，如下所示：

   * `-1.0` 是“最低等级（在搜索结果中显示较低）”。
   * `0.0` 为“中性排名（不更改搜索结果顺序）”。
   * `1.0` 是“最高排名（在搜索结果中显示得更高）”。
   定义的级别应在每个规则的相同范围内。 排名范围还必须与为> **[!UICONTROL Settings]** >下的“排名”字段定义的范围 **[!UICONTROL Metadata]** 匹配 **[!UICONTROL Definitions]**。

   请参 [阅添加新的元标记字段](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。

   另请参阅 [编辑排名规则](../c-about-rules-menu/c-about-ranking-rules.md#task_5EBF55A43D6545FEA46BAE5E586FA275)。
1. 单击 **[!UICONTROL Add]**.
1. 要预览添加规则的结果，请单击以重 **[!UICONTROL regenerate your staged site index]** 新构建分阶段的网站索引。

   请参 [阅运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   请参 [阅运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 编辑排名规则 {#task_5EBF55A43D6545FEA46BAE5E586FA275}

您可以编辑已添加的现有排名规则。

请参阅 [配置排名](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5)。

**编辑排名规则**

1. 在产品菜单中，单击 **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**。
1. （可选）如果您已创建规则组并将任何规则添加到该组，请在页面的下拉列表中 **[!UICONTROL Define Ranking Rules]****[!UICONTROL Select Rule Group]** ，选择包含要编辑的规则的规则组。

   请参 [阅添加排名规则组](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)。
1. 在表的列标题下， **[!UICONTROL Actions]** 单击要更 **[!UICONTROL Edit]** 改的数据源名称。
1. 在页 [!DNL Edit Ranking Rule] 面上，设置所需的选项。 标有星号(*)的字段为必填字段。

   请参阅添加排名规则 [下的选项表](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A)。
1. 单击 **[!UICONTROL Save Changes]**.
1. 重建分阶段网站索引以预览规则编辑的结果。

   请参 [阅运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   请参 [阅运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 删除排名规则 {#task_742A3BCC2A6E4164BE84CC7408807EBB}

您可以删除不再需要使用的排名规则。

请参阅 [配置排名](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5)。

请参 [阅添加排名规则组](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)。

**删除排名规则**

1. 在产品菜单中，单击 **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**。
1. （可选）如果您已创建规则组并将任何规则添加到该组，请在页面的下拉列表中 [!DNL Define Ranking Rules]**[!UICONTROL Select Rule Group]** ，选择包含要删除的规则的规则组。
1. 在表的列标题下， **[!UICONTROL Actions]** 单击要更 **[!UICONTROL Delete]** 改的数据源名称。
1. 在页面 [!DNL Delete Ranking Rule] 上，单击 **[!UICONTROL Delete]**。

   您将返回到页 [!DNL Define Ranking Rules] 面。
1. 重建分阶段网站索引以预览删除规则的结果。

   请参 [阅运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   请参 [阅运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 添加排名规则组 {#task_B65081B3CC9E4330A7FEE77B7BCD36C8}

如果定义了多个类型为“rank”的元标记，则可以创建单独的规则集合以用于计算各种排名字段。 您可以添加一个排名规则组，然后将该组分配给您定义的一个排名字段。

规则组通常包含您添加的一个或多个规则。 但是，规则组也可以引用其他规则组。 例如，您可以创建一个或多个规则组，然后向每个规则组添加常用规则。 然后，在计算多个级别时共享这些规则。

请参 [阅编辑排名规则组](../c-about-rules-menu/c-about-ranking-rules.md#task_D3EC0437E47144BC9E754FEF99C725E5)。

请参 [阅删除排名规则组](../c-about-rules-menu/c-about-ranking-rules.md#task_BE5BE01F377843BEA9846E094A07F2EA)。

请参 [阅查看排名规则组](../c-about-rules-menu/c-about-ranking-rules.md#task_5694459D050C4254A25186038CD66B6E)。

**添加排名规则组**

1. 在产品菜单中，单击 **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**。
1. 在页 [!DNL Define Ranking Rules] 面上，单击下拉列 **[!UICONTROL Select Rule Group]** 表右侧的 **[!UICONTROL Add]**。
1. 在页 [!DNL Add Ranking Rule Group] 面的字段中， **[!UICONTROL Rule Group Name]** 键入新规则组的唯一名称。
1. 在下拉 **[!UICONTROL Rank Field Name]** 列表中，选择要与新规则组关联的排名元数据字段名称。 如 **[!UICONTROL None]** 果不想分配排名，请选择。

   排名字段名称列表来自在 **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** >中添加的元数据定义 **[!UICONTROL Definitions]**。

   请参阅添加新元标 [记字段中的选项表](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。
1. 单击 **[!UICONTROL Add]**.
1. 重建分阶段网站索引以预览添加规则的结果。

   请参 [阅运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   请参 [阅运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 编辑排名规则组 {#task_D3EC0437E47144BC9E754FEF99C725E5}

您可以编辑现有排名规则组的设置。

请参 [阅添加排名规则组](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)。

**编辑排名规则组**

1. 在产品菜单中，单击 **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**。
1. 在页 [!DNL Define Ranking Rules] 面上，单击下拉列 **[!UICONTROL Select Rule Group]** 表右侧的 **[!UICONTROL Edit]**。
1. 在页 [!DNL Edit Ranking Rule Group] 面的字段中， **[!UICONTROL Rule Group Name]** 键入规则组的唯一名称。
1. 在下拉 **[!UICONTROL Rank Field Name]** 列表中，选择要与规则组关联的排名元数据字段名称。 如 **[!UICONTROL None]** 果不想分配排名，请选择。

   排名字段名称列表来自在 **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** >中添加的元数据定义 **[!UICONTROL Definitions]**。

   请参阅添加新元标 [记字段中的选项表](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。
1. 单击 **[!UICONTROL Save Changes]**.
1. 重建分阶段网站索引以预览添加规则的结果。

   请参 [阅运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   请参 [阅运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 删除排名规则组 {#task_BE5BE01F377843BEA9846E094A07F2EA}

您可以删除不再需要或使用的排名规则组。 删除用户组时，添加到该用户组的所有规则也会被删除。 无法删除默认的“排名规则”组。

删除组中包含的任何规则组的内容不会被删除；仅删除对这些组的引用。

请务必重新为网站编制索引，以便在搜索结果中正确反映所做的更改。

请参 [阅添加排名规则组](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)。

**删除排名规则组**

1. 在产品菜单中，单击 **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**。
1. 在页 [!DNL Define Ranking Rules] 面的下拉列 **[!UICONTROL Select Rule Group]** 表中，选择要删除的组。
1. 在下拉列表 **[!UICONTROL Select Rule Group]** 的右侧，单击 **[!UICONTROL Delete]**。
1. 在页面 [!DNL Delete Ranking Rule Group] 上，单击 **[!UICONTROL Delete]**。
1. 重建分阶段网站索引以预览添加规则的结果。

   请参 [阅运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   请参 [阅运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 查看排名规则组 {#task_5694459D050C4254A25186038CD66B6E}

您可以使用排名规则组概览来查看每个组的排名字段名称以及关联的数据源和权重。

请参 [阅添加排名规则组](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)。

**要查看排名规则组，请执行以下操作：**

1. 在产品菜单中，单击 **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**。
1. 在页 [!DNL Define Ranking Rules] 面上，单击下拉列 **[!UICONTROL Select Rule Group]** 表右侧的 **[!UICONTROL Overview]**。
1. 在页 [!DNL Ranking Rule Groups Overview] 面上，单 **[!UICONTROL Close]** 击以返回页 [!DNL Define Ranking Rules] 面。
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 测试排名规则 {#task_56F64EE7ED5B42E481F0990A9DD98ADB}

您可以为您设置的排名规则定义提供合适的URL测试。 将显示计算中使用的度量以及计算的排名值。

请参阅[有关规则排名](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397)。

**测试排名规则**

1. 在产品菜单中，单击 **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**。
1. 在页 [!DNL Define Ranking Rules] 面上的区 **[!UICONTROL Test URL]** 域中，键入网站上网页的URL。
1. 单击 **[!UICONTROL Test]**.
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 调整与排名规则关联的权重 {#task_3CB6FC92A66F4D99874A42D55825DB64}

您可以更改各个排名规则的相对贡献以及排名对最终搜索结果的贡献。

如果未定义排名，则搜索结果将全部位于页面的“规 **[!UICONTROL Natural Relevance]** 则和相关性”滑块栏的一 **[!UICONTROL Adjust Ranking Weights]** 侧。 这种平衡只意味着搜索结果仅基于搜索词进行排序。

定义“排名”后，关联的“排名”元数据字段将分配一个介于1-10之间的“相关性”值。 值1表示计算的排名占搜索结果排序的10%，而自然相关性占其余90%。

如果您在规则组中定义了多个规则，则每个规则的权重值将决定该规则的结果对总计算排名的贡献。 例如，假设您的“自然相关性”为80%，这意味着关联的“排名”字段的相关性为2。 您还定义了两个规则：一个重量为3，另一个重量为7。 在这种情况下，第一条规则对最终结果的贡献为6%((3 /(3+7))* 20%)。 第二条规则对最终结果的贡献为14%((7 /(3+7))* 20%)。

**调整与排名规则关联的权重**

1. 在产品菜单中，单击 **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Adjust Weights]**。
1. 在页 [!DNL Adjust Ranking Weights] 面的下拉列 **[!UICONTROL Select Rule Group]** 表中，选择要调整其排名权重的组。
1. 拖动滑块可更改相应的贡献值。

   饼图以图形方式反映您所做的更改。
1. 单击 **[!UICONTROL Save Changes]**.
1. 重建分阶段网站索引以预览添加规则的结果。

   请参 [阅运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   请参 [阅运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。
