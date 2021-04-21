---
description: 您可以使用排名规则来根据包含的元标记内容和相关的Adobe Analytics量度控制客户搜索结果的相对位置或排名。
solution: Target
subtopic: Ranking Rules
title: 关于排名规则
topic-legacy: Rules,Site search and merchandising
uuid: 21962f9a-1d9c-442f-a6c4-5f452436c640
exl-id: 7f66c4f6-7659-4faf-9f05-b650cf8c7d47
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '4616'
ht-degree: 1%

---

# 关于排名规则{#about-ranking-rules}

您可以使用排名规则来根据包含的元标记内容和相关的Adobe Analytics量度控制客户搜索结果的相对位置或排名。

## 使用排名规则{#concept_F555C076759B4E81B925441CFE707397}

您可以根据每个文档的内容定义排名规则，以影响搜索结果中文档的相对位置。 您可以基于元标记内容、Adobe Analytics量度(如果您的帐户配置为与Adobe Analytics一起使用)或Adobe Analytics HBX量度(如果您的帐户配置为与Adobe Analytics HBX一起使用)来设置排名规则。

您可以设置包含具有所需特征（如某个品牌名称或价格）的meta标签的网页，或具有所需Adobe Analytics关键绩效指标（如独特查看器）的网页，以获得比不具备所需功能的网页更高的排名。 通过添加或编辑排名规则，然后重新为网站编制索引，可轻松更新“理想”特征。

如果定义了多个类型为“rank”的元标记，则可以创建用于计算各种排名字段的规则的单独集合。 您可以添加排名规则组，然后将其分配给您定义的排名字段之一。 规则组通常包含一个或多个规则定义，但也可以引用其他规则组，因此您可以创建一个或多个常用规则组，这些规则组在计算多个排名时共享。

请参阅[添加排名规则组](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)。

正排名值会促使搜索结果向顶端靠拢；负排名值将搜索结果降低到搜索结果的底部。 排名值的正常范围是1.0，这是搜索结果中的最大升级，而–1.0是最高降级。 虽然您可以通过在元数据定义中编辑“排名”字段来自定义此范围，但通常不必进行此类自定义。

请参阅[关于定义](../c-about-settings-menu/c-about-metadata-menu.md#concept_AE48035C210145169BE067D396975620)。

如果您在“设置”>“元数据”>“定义”下定义了多个排名字段，则可以选择创建其他一组排名规则，每个排名字段对应一组。 您可以定义其他排名规则集，而无需直接与排名字段关联。 此灵活性允许您创建可在计算一个或多个排名值时共享的通用规则集。

**重要说明**:在使用排名规则之前，您必须完成几个帐户配置步骤。

请参阅[配置排名](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5)

## 配置排名{#task_4CEBC13925B047FC95BDC217B48089C5}

在使用排名规则之前，必须完成几个帐户配置步骤。

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
      <li id="li_544075CFA0964C6F8FAF7941AAA9ECCC"> 在产品菜单上，单击<span class="uicontrol">设置</span> &gt; <span class="uicontrol">元数据</span> &gt; <span class="uicontrol">定义</span>。 </li> 
      <li id="li_F237F13B89E8425080C15D3BD697652C"> 在“定义”页上，单击<span class="uicontrol">添加新字段</span>。 </li> 
      <li id="li_2A839874D71D45FEA661B3D3B8BE2A86"> 在“添加字段”页面的<span class="uicontrol">字段名称</span>文本字段中，键入 
      <code>
        rank 
      </code>;在<span class="uicontrol">元标记名称</span>文本字段中，键入 
      <code>
        rank 
      </code>;在<span class="uicontrol">数据类型</span>下拉列表中，选择<span class="uicontrol">排名</span>。 保留所有其他字段选项。 <p>请参见<a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local">后端搜索CGI参数</a>中的查询参数<span class="codeph"> sp_sr </span>。 </p> </li> 
      <li id="li_8E91AF4BE51A4A41ABBF9680DDE0B7CE">单击<span class="uicontrol">添加</span>。 </li> 
      </ol> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>创建基于Adobe Analytics量度的排名规则 </p> </td> 
      <td colname="col2"> <p> 
      <ol id="ol_BE57CBC303D941778B10D855ADC93C68"> 
      <li id="li_8DF5D8F924B24ECBBD2D93C76C69D00C"> 确保您已从网站搜索/促销中设置Adobe Analytics身份验证。 <p>请参阅<a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_8AA93F6273B747F9B4DE9E8DFBCBDC42" type="task" format="dita" scope="local">设置Adobe Analytics量度身份验证</a>。 </p> </li> 
      <li id="li_CF7DD073FC5A432DADBD282AA8BB9920"> 选择并添加可用的报表包。 <p>请参阅<a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0" type="task" format="dita" scope="local">添加Adobe Analytics报表包</a>。 </p> </li> 
      <li id="li_9A63448577D04E028DF211D8715F943A"> 配置要用于创建新排名规则的Adobe Analytics量度的列表。 <p>请参阅<a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664" type="task" format="dita" scope="local">编辑报表包</a>的Adobe Analytics量度。 </p> </li> 
      <li id="li_1ACA3611D9B44AC394604CD89209C966"> 加载网站页面的初始Adobe Analytics量度。 <p>请参阅<a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181" type="task" format="dita" scope="local">加载Adobe Analytics数据</a>。 </p> </li> 
      </ol> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 添加一个或多个排名规则。

   请参阅[添加排名规则](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A)。

1. 单击&#x200B;**[!UICONTROL regenerate your staged site index]**&#x200B;以对您的网站（从&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Full Index]**）执行完整的重新索引。

   请参阅[运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

   请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. 检查&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**&#x200B;中“排名”列中的值，以验证是否正确应用了排名规则。

## 关于按年龄{#topic_770815CF1B2A491F83FF765871B6F1B8}对文档进行排名

可以按HTML文档的年龄使用指数衰减函数对其进行排名。 衰减率使用选定的半衰期常数来指定，该常数是值降到初始值的一半之前必须经过的时间。

年龄排名基于以下两个公式：

`K = -ln(2) / H`

`RANK = e^(K * T)`

变量`H`和`T`是此函数的输入：`H`是所需的半衰期，`T`是文档的年龄，以秒表示。 `K` 是计算的半衰期， `RANK` 是指定年龄值的指数衰减。结果值为0到1。 与较旧的文档相比，较新文档的排名值更接近1。 理论上，文档永远不应达到0的值，但舍入错误可能导致结果变为0。

## 使用年龄排名{#section_D716507D589442C6B7848892BD28F966}的要求

* 您的帐户应已正确配置以进行排名。 如果未配置，请参阅[配置排名](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5)。
* HTML文档必须有一个HTML meta标记字段，该字段表示其出生日期、开始日期作为时间戳或某些其他有意义的日期值。
* 特殊的内置函数`search_get_age_rank()`（如“添加”或“编辑排名规则”页中所指定）用于计算文档的年龄等级。 下几节详细描述了年龄排名函数的一般用途。 最后，给出了一个实例，说明了年龄排名的特点。

## 在“添加排名规则”页或“编辑排名规则”页{#section_34BC5276F2AB4419AD92872A397CA0AF}中使用search_get_age_rank()

按如下方式指定`search_get_age_rank()`:

`search_get_age_rank(Birthdate#Half_Life#Default_Rank)`

* 出生日期 — 文件的出生日期或开始日期必须是根据字段的日期格式设置日期字符串。 此日期格式化字符串必须是字段引用，如`{field_name}`中所示。
* Half_Life — 半衰期是该值降到初始值的一半之前必须经过的时间。 此值以天数表示，它是整数或浮点数。
* Default_Rank — 在出生日期无效或日期在将来时，默认排名将用作安全网。 如果其关联的元数据字段也具有有效的默认值，则不能使用此默认值。 此处的值是浮点数或整数。 如果您遇到使用默认值的问题，请参阅下面的建议。

请参阅[添加排名规则](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A)。

请参阅[编辑排名规则](../c-about-rules-menu/c-about-ranking-rules.md#task_5EBF55A43D6545FEA46BAE5E586FA275)。

**示例**

在以下示例中，

`search_get_age_rank({birthdate}#28#0.20)`

包含在文档`birthdate`字段中的日期将作为时间戳传入。 半衰期是28天。 如果日期无效，则默认排名值为0.20。

请参阅[添加排名规则](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A)中的选项表。

在“添加排名规则”页或“编辑排名规则”页的“值/排名”部分，您只能将`search_get_age_rank`与自定义规则一起使用。 因此，请务必从“值/排名”下拉列表中选择&#x200B;**自定义**。 当规则使用年龄排名函数时，规则的值部分中不允许有空格。 请确保函数参数中或它们之间没有空格。 而且，任何数学运算符或条件运算符之间没有空格。

以下是值/排名规则的示例 — 与文本字段关联的规则：

`regexp .* search_get_age_rank({other_field}#365#0.20)`

此示例假定`other_field`包含日期值。 如果此字段本身不是日期类型字段，则使用与预定义的“日期”字段关联的日期格式解释此值。 否则，将使用此字段的日期格式。 只要文档的字段（规则的数据源所标识的字段）不为空，且函数的返回值（从0到1）是指定的排名，就会使用此值/排名条目。

对于与数字字段关联的规则，尤其是日期字段：

`9999999999 search_get_age_rank({other_field}#365#0.20)`

在处理每个文档时，`other_field`中的值将使用字段的日期格式定义转换为Unix &quot;epoch&quot;表单。 该值用于`search_get_age_rank()`调用。 由于每个“纪元”值都小于9999999999（至少目前），规则只提供函数的返回值（从0到1）作为排名。

在上述两个示例中，规则的数据源与`search_get_age_rank()`函数 — `other_field`中使用的字段相同是典型情况。

## 将年龄排名集成到排名规则{#section_A86D909687CC45E19D4EA7A4A9283F28}的示例

以下是如何将年龄排名集成到排名规则中的示例。 该示例还显示年龄排名函数的原始结果和排名规则的结果。 该示例假定：

* 已爬网的网页具有名为“bortidate”的HTML meta标签。 此标记的内容是与文档相关的时间戳。
* 元数据定义具有为生日标记定义的元标记字段。 此字段设置为“日期”。

**排名规则**

请参阅[添加新的meta标签字段](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。

现在，您添加了新的排名规则。 规则定义为使用文档上的“出生日期”字段。 新的排名规则将添加以下属性集：

* 数据源类型：Meta标签
* 数据源名称：出生日期
* 权重/条件：10 — 最大重要性
* 值/排名：9999999999 search_get_age_rank({bordate}#14#0.10)
* 默认排名：-1

这条规则做了几件事。 规则的权重设置为10。 排名值只是年龄排名函数的结果，一个0到1之间的值。 不能将空格与`search_get_age_rank()`一起使用。 另外，请注意，字段“出生日期”用大括号括起。 最后，保存此规则时，值/排名定义中的逗号将替换为`#`个字符；这种行为是正常的。

**查看结果**

使用“数据视图”功能可快速查看年龄排名函数的结果。 添加相应的元数据字段。 在示例中，`age_val`和`myrank`是应添加到“数据”视图的两个“元数据”字段。 `myrank`字段显示年龄排名如何影响排名值。 `age_val`字段显示该文档的指数衰减函数的原始输出。

## 默认值{#section_CB109EF78F914E92955D512ACFC3310E}

以下是与函数`search_get_age_rank()`相关的三个默认值：

* 可输入`search_get_age_rank()`函数本身的默认值。
* 排名规则的默认排名值。
* 元数据定义的默认值。

根据故障发生的位置，您可能会获得不同的默认值。

例如，如果正确实施了排名和筛选，则元数据定义中的默认值永远不会发生。 当该元数据字段不存在有效或已知内容时，此默认值是最后的值。 当`search_get_age_rank()`引用其自己的关联标记并且该标记在文档中缺失时，可能会显示排名规则的默认值。 在这种情况下，此规则将直接转到规则的默认值。 如果年龄排名函数引用另一个排名规则的标记，则如果引用的标记缺失或无效，则可能会使用传递到该年龄排名函数的默认值。

## 添加排名规则{#task_A132789FD4E5423DAD090DCDA7311E8A}

您可以添加[!DNL Ranking Rules]，以根据每个网页的内容影响网页在搜索结果中的相对位置。

请参阅[配置排名](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5)。

**添加排名规则**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**。
1. （可选）如果您已创建规则组，并在[!DNL Define Ranking Rules]页面的&#x200B;**[!UICONTROL Select Rule Group]**&#x200B;下拉列表中，选择包含要编辑的规则的规则组。

   请参阅[添加排名规则组](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)。
1. 在[!DNL Define Ranking Rules]页面上，单击&#x200B;**[!UICONTROL Add Rule]**&#x200B;以添加新的排名规则，或添加对规则集的引用。
1. 在[!DNL Add Ranking Rule]页面上，设置所需的选项。 标有星号(*)的字段为必填字段。

   您选择的数据源类型会影响[!DNL Data Source Name]下拉列表中可用的选项。 例如，如果您选择&#x200B;**[!UICONTROL Meta Tag]**&#x200B;作为数据源类型，则数据源名称是指网站页面上元标记的名称。 如果您选择了&#x200B;**[!UICONTROL Adobe Analytics Metric (Number)]**，则数据源名称引用您在报表包中选择的一个Adobe Analytics量度名称，该名称位于网站搜索/促销中的&#x200B;**[!UICONTROL Edit Adobe Analytics Metrics]**&#x200B;页面。

   请参阅[编辑报表包的Adobe Analytics量度](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664)。

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
      <li id="li_4D8BDE32853540809AE78FF5FF5677A1"> <span class="uicontrol"> Meta标签  </span> <p> 此规则基于数字数据或存储在网站页面的已命名meta标记中的文本数据。 </p> </li> 
      <li id="li_4976C31D67254C7F81D554EC49DDBB40"> <span class="uicontrol"> Adobe Analytics量度（数字）  </span> <p>此规则基于与您的网站页面关联的数字Adobe Analytics量度。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Data Source Name（数据源名称） </p> </td> 
      <td colname="col2"> <p>如果选择<span class="uicontrol">元标记</span>作为数据源类型，则这是在网站页面中找到的元标记的名称。 下拉菜单中的名称来自定义的元数据值的列表，这些元数据值是在“设置”&gt;“元数据”&gt;“定义”中配置的。 </p> <p>请参阅<a scope="local" href="../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5" type="task" format="dita">添加新的meta标记字段</a>。 </p> <p>如果选择“Adobe Analytics量度（数字）”作为数据源类型，则此为Adobe Analytics量度的名称。 下拉菜单中的名称来自在“设置”&gt;“Adobe Analytics”&gt;“量度”&gt;“编辑”中配置的列表定义的可用Adobe Analytics量度。 </p> <p>请参阅<a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664" type="task" format="dita" scope="local">编辑报表包</a>的Adobe Analytics量度。 </p> <p>如果在<span class="uicontrol">设置</span> &gt; <span class="uicontrol">元数据</span> &gt; <span class="uicontrol">定义</span>中尚未定义您选择的Adobe Analytics量度名称，将显示一个文本字段和一个“添加”按钮。 输入元数据字段名称（元数据字段名称不能超过20个字符），然后单击<span class="uicontrol">添加</span>。 </p> <p>当页面遇到多个Adobe Analytics键时，如产品页面显示多个产品时，复合方案会指定如何处理与该页面关联的多个Adobe Analytics量度值。 选择下列选项之一： </p> <p> 
      <ul id="ul_D6E51748BB3949048A37C1895F2C0A58"> 
      <li id="li_04F00F382A264C96A519B0D975E25E94"> <span class="uicontrol">“总计”</span> <p>返回量度值的和。 </p> </li> 
      <li id="li_FA44219B663F4CC197BD3A094EB84396"> <span class="uicontrol"> 平均 </span> <p>返回值的平均值（总和除以值数）。 </p> </li> 
      <li id="li_F0EAAE1EA1754FFEB30F611E5550097B"> <span class="uicontrol"> 最大值 </span> <p>返回值中的最大值。 </p> </li> 
      <li id="li_38E3E3F3D9AF4C57803B84B60223FB9D"> <span class="uicontrol"> 首次 </span> <p>返回与第一个键对应的值。 </p> </li> 
      <li id="li_4AEE470CE6BB4D899E975915EC226624"> <span class="uicontrol"> 上次 </span> <p>返回与最后一个键对应的值。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>权重/条件 </p> </td> 
      <td colname="col2"> <p>包含简单、单个规则权重号或规则权重号和测试条件的成对列表。 </p> <p>规则权重编号是1-10之间的值，用于指示此排名规则相对于其他排名规则在确定文档的整体排名时的重要性。 规则权重越高，表示重要性越高。 零(0)权重将忽略该规则。 </p> <p>从下拉列表中选择<span class="uicontrol">自定义</span>，通过定义规则权重/测试条件对的列表来自定义不同页面的规则权重。 测试条件是用于测试数据源值的Perl的片段，或在自定义筛选器脚本中定义的全局变量(例如，价格、品牌、季节或页面视图，如下例所示)。 如果测试条件的计算结果为“true”，则应用关联的规则权重值。 如果测试条件的计算结果为“false”，则计算列表中的下一个条件。 <code> 0&nbsp;({price}&nbsp;&gt;&nbsp;50.00)&nbsp;&amp;&amp;&nbsp;({brand}=~/Kuhl/)5&nbsp;{season}&nbsp;=~&nbsp;/Fall/10&nbsp;{pageviews}&nbsp;&gt;&nbsp;1000005 </code>在上面的自定义创建的权重/条件示例中，如果第一个测试条件的计算结果为“true”，则应用规则权重0。即，价格包含的价值大于50，而品牌包含“Kuhl”)。 如果第一个测试条件的计算结果为“false”，则计算下一个条件。 如果未满足以前的条件，则分配规则权重5。 </p> <p>您应始终在权重末尾提供没有条件的规则列表。 如果不这样做，则规则将获得0的权重，如果所有条件测试的结果都不为“true”。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>值/排名 </p> </td> 
      <td colname="col2"> <p>由一个内置的排名函数或可能的数据源内容以及所需的排名组成。 </p> <p>如果选择<span class="uicontrol"> Adobe Analytics Metric(Number)</span>作为数据源类型，将显示包含以下选项的下拉列表: 
      <ul id="ul_104906B6AA8547BAB6979AA37C4FAB90"> 
      <li id="li_7656A2855A054DB8B64E90FE501517AA"> <span class="uicontrol"> 按顺序自动排名（默认）  </span> <p>根据文档的“Adobe Analytics量度”，计算基于其相对位置的排名。 例如，文档的位置越接近排名第一的文档，其排名就越高。 </p> </li> 
      <li id="li_1A7D60EA6965434AA6D39B215C158306"> <span class="uicontrol"> 按值自动排名  </span> <p>根据文档的Adobe Analytics量度，根据其相对值计算排名。 例如，文档值与排名最靠前的文档值越接近，其排名越高。 </p> </li> 
      <li id="li_457DE44D6ADA40619DC77220BF12318E"> <span class="uicontrol"> 自定义 </span> <p>指定自定义设置。 例如，名为“brand”的数据源可能包含特定产品的品牌名称。 您可以通过列出每个品牌及其排名来指定其相对重要性。 </p> </li> 
      </ul> </p> <p>自动排名计算返回的排名值在0.0（最低）到1.0（最高）范围内。 它们不会根据为“设置”&gt;“元数据”&gt;“定义”下的“排名”字段定义的范围进行调整。 </p> <p>在以下示例中，如果特定搜索结果的品牌数据源与“DKNY”完全匹配，则该结果的应用排名为0.5。否则，如果品牌为“级别”，则应用的排名为0.1。数据源内容必须与设置的值匹配。 换句话说，如果数据源内容为“Levis Corp.”，则它将与值“Levis”不匹配。 忽略大小写，因此"DKNY"与"dkny"和"Dkny"匹配。<code> DKNY&nbsp;0.5 Levis&nbsp;0.1 Lee&nbsp;0.2 </code> </p> <p>作为更高级的选项，您可以将值指定为常规表达式。 例如，假定您的某些网站页面包含品牌值“Levis”，而其他网站页面包含品牌值“Levis jeans”。 可以使用用关键字指定的常规表达式 
      <code>
        regexp 
      </code>。 </p> <p>请参阅<a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local">常规表达式</a>。 </p> <p>在以下示例中，将为包含品牌内容“Levis jeans”的搜索结果文档分配0.1的等级。与标准比较一样，常规表达式将忽略大小写。<code> DKNY&nbsp;0.5 regexp&nbsp;Levis.*&nbsp;0.1 Lee&nbsp;0.2 </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>默认排名 </p> </td> 
      <td colname="col2"> <p> 指定要应用于与任何指定值不匹配的搜索结果文档的排名。 在上例中，将为包含“gap”的“brand”数据源的搜索结果文档分配默认排名值，因为“gap”与任何定义的值都不匹配。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>注释 </p> </td> 
      <td colname="col2"> <p>添加与您创建的排名规则定义或规则组定义相关的信息。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

   有效排名值的范围通常为–1.0到1.0，如下所示：

   * `-1.0` 为“最低排名（在搜索结果中显示较低）”。
   * `0.0` 为“中性排名（不更改搜索结果顺序）”。
   * `1.0` 为“最高排名（在搜索结果中显示得更高）”。

   对于每个规则，定义的排名应在相同范围内。 排名范围还必须与为&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**&#x200B;下的“排名”字段定义的范围相匹配。

   请参阅[添加新的meta标签字段](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。

   另请参阅[编辑排名规则](../c-about-rules-menu/c-about-ranking-rules.md#task_5EBF55A43D6545FEA46BAE5E586FA275)。
1. 单击 **[!UICONTROL Add]**.
1. 要预览添加规则的结果，请单击&#x200B;**[!UICONTROL regenerate your staged site index]**&#x200B;以重新构建分阶段网站索引。

   请参阅[运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

   请参阅[运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 编辑排名规则{#task_5EBF55A43D6545FEA46BAE5E586FA275}

您可以编辑已添加的现有排名规则。

请参阅[配置排名](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5)。

**编辑排名规则**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**。
1. （可选）如果您已创建规则组，并在&#x200B;**[!UICONTROL Define Ranking Rules]**&#x200B;页的&#x200B;**[!UICONTROL Select Rule Group]**&#x200B;下拉列表中，选择包含要编辑的规则的规则组。

   请参阅[添加排名规则组](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)。
1. 在表的&#x200B;**[!UICONTROL Actions]**&#x200B;列标题下，单击&#x200B;**[!UICONTROL Edit]**&#x200B;以获取要更改的数据源名称。
1. 在[!DNL Edit Ranking Rule]页面上，设置所需的选项。 标有星号(*)的字段为必填字段。

   请参阅[添加排名规则](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A)下的选项表。
1. 单击 **[!UICONTROL Save Changes]**.
1. 重新构建分阶段网站索引以预览规则编辑的结果。

   请参阅[运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

   请参阅[运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 删除排名规则{#task_742A3BCC2A6E4164BE84CC7408807EBB}

您可以删除不再需要使用的排名规则。

请参阅[配置排名](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5)。

请参阅[添加排名规则组](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)。

**删除排名规则**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**。
1. （可选）如果您已创建规则组，并在[!DNL Define Ranking Rules]页的&#x200B;**[!UICONTROL Select Rule Group]**&#x200B;下拉列表中，选择包含要删除的规则的规则组。
1. 在表的&#x200B;**[!UICONTROL Actions]**&#x200B;列标题下，单击&#x200B;**[!UICONTROL Delete]**&#x200B;以获取要更改的数据源名称。
1. 在[!DNL Delete Ranking Rule]页面上，单击&#x200B;**[!UICONTROL Delete]**。

   您将返回到[!DNL Define Ranking Rules]页面。
1. 重新构建分阶段网站索引以预览删除规则的结果。

   请参阅[运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

   请参阅[运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 添加排名规则组{#task_B65081B3CC9E4330A7FEE77B7BCD36C8}

如果定义了多个类型为“rank”的元标记，则可以创建用于计算各种排名字段的规则的单独集合。 您可以添加排名规则组，然后将其分配给您定义的排名字段之一。

规则组通常包含您添加的一个或多个规则。 但是，规则组也可以引用其他规则组。 例如，您可以创建一个或多个规则组，然后将常用规则添加到每个规则组。 然后，在计算多个排名时共享这些规则。

请参阅[编辑排名规则组](../c-about-rules-menu/c-about-ranking-rules.md#task_D3EC0437E47144BC9E754FEF99C725E5)。

请参阅[删除排名规则组](../c-about-rules-menu/c-about-ranking-rules.md#task_BE5BE01F377843BEA9846E094A07F2EA)。

请参阅[查看排名规则组](../c-about-rules-menu/c-about-ranking-rules.md#task_5694459D050C4254A25186038CD66B6E)。

**添加排名规则组**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**。
1. 在[!DNL Define Ranking Rules]页面的&#x200B;**[!UICONTROL Select Rule Group]**&#x200B;下拉列表右侧，单击&#x200B;**[!UICONTROL Add]**。
1. 在[!DNL Add Ranking Rule Group]页面的&#x200B;**[!UICONTROL Rule Group Name]**&#x200B;字段中，键入新规则组的唯一名称。
1. 在&#x200B;**[!UICONTROL Rank Field Name]**&#x200B;下拉列表中，选择要与新规则组关联的排名元数据字段名称。 如果您不想分配排名，请选择&#x200B;**[!UICONTROL None]**。

   排名字段名称的列表来自在&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**&#x200B;中添加的元数据定义。

   请参阅[添加新meta标记字段](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)中的选项表。
1. 单击 **[!UICONTROL Add]**.
1. 重新构建分阶段网站索引以预览添加规则的结果。

   请参阅[运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

   请参阅[运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 编辑排名规则组{#task_D3EC0437E47144BC9E754FEF99C725E5}

您可以编辑现有排名规则组的设置。

请参阅[添加排名规则组](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)。

**编辑排名规则组**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**。
1. 在[!DNL Define Ranking Rules]页面的&#x200B;**[!UICONTROL Select Rule Group]**&#x200B;下拉列表右侧，单击&#x200B;**[!UICONTROL Edit]**。
1. 在[!DNL Edit Ranking Rule Group]页面的&#x200B;**[!UICONTROL Rule Group Name]**&#x200B;字段中，键入规则组的唯一名称。
1. 在&#x200B;**[!UICONTROL Rank Field Name]**&#x200B;下拉列表中，选择要与规则组关联的排名元数据字段名称。 如果您不想分配排名，请选择&#x200B;**[!UICONTROL None]**。

   排名字段名称的列表来自在&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**&#x200B;中添加的元数据定义。

   请参阅[添加新meta标记字段](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)中的选项表。
1. 单击 **[!UICONTROL Save Changes]**.
1. 重新构建分阶段网站索引以预览添加规则的结果。

   请参阅[运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

   请参阅[运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 删除排名规则组{#task_BE5BE01F377843BEA9846E094A07F2EA}

您可以删除不再需要或使用的排名规则组。 删除组时，已添加到该组的所有规则也会被删除。 无法删除默认的“排名规则”组。

删除组中包含的任何规则组的内容不会被删除；仅删除对这些组的引用。

请确保重新为网站编制索引，以便在搜索结果中正确反映所做的更改。

请参阅[添加排名规则组](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)。

**删除排名规则组**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**。
1. 在[!DNL Define Ranking Rules]页面的&#x200B;**[!UICONTROL Select Rule Group]**&#x200B;下拉列表中，选择要删除的组。
1. 在&#x200B;**[!UICONTROL Select Rule Group]**&#x200B;下拉列表的右侧，单击&#x200B;**[!UICONTROL Delete]**。
1. 在[!DNL Delete Ranking Rule Group]页面上，单击&#x200B;**[!UICONTROL Delete]**。
1. 重新构建分阶段网站索引以预览添加规则的结果。

   请参阅[运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

   请参阅[运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 查看排名规则组{#task_5694459D050C4254A25186038CD66B6E}

您可以使用排名规则组概览来查看每个组的排名字段名称以及关联的数据源和权重。

请参阅[添加排名规则组](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)。

**查看排名规则组**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**。
1. 在[!DNL Define Ranking Rules]页面的&#x200B;**[!UICONTROL Select Rule Group]**&#x200B;下拉列表右侧，单击&#x200B;**[!UICONTROL Overview]**。
1. 在[!DNL Ranking Rule Groups Overview]页面上，单击&#x200B;**[!UICONTROL Close]**&#x200B;返回至[!DNL Define Ranking Rules]页面。
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 测试排名规则{#task_56F64EE7ED5B42E481F0990A9DD98ADB}

您可以为已设置的排名规则定义提供合适的URL测试。 将显示计算中使用的量度以及计算的排名值。

请参阅[有关规则排名](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397)。

**测试排名规则**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**。
1. 在[!DNL Define Ranking Rules]页面的&#x200B;**[!UICONTROL Test URL]**&#x200B;区域中，键入指向您网站上的网页的URL。
1. 单击 **[!UICONTROL Test]**.
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 调整与排名规则{#task_3CB6FC92A66F4D99874A42D55825DB64}关联的权重

您可以更改单个排名规则的相对贡献以及排名对最终搜索结果的贡献。

如果未定义“排名”，则搜索结果将在&#x200B;**[!UICONTROL Adjust Ranking Weights]**&#x200B;页面的“规则和相关性”滑块栏的&#x200B;**[!UICONTROL Natural Relevance]**&#x200B;一侧为100%。 这种平衡只意味着搜索结果仅基于搜索词进行排序。

定义“排名”后，将为关联的“排名”元数据字段分配一个范围为1-10的“相关性”值。 值1表示计算的排名占搜索结果排序的10%，而自然相关性占其余90%。

如果您在规则组中定义了多个规则，则每个规则的权重值将确定该规则的结果对总计算排名的贡献。 例如，假设您的“自然相关性”为80%，这意味着关联的“排名”字段的相关性为2。 您还定义了两个规则：一个权重为3，另一个权重为7。 在这种情况下，第一条规则对最终结果的贡献为6%((3 /(3+7))* 20%)。 第二条规则对最终结果的贡献为14%((7 /(3+7))* 20%)。

**调整与排名规则关联的权重**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Adjust Weights]**。
1. 在[!DNL Adjust Ranking Weights]页面的&#x200B;**[!UICONTROL Select Rule Group]**&#x200B;下拉列表中，选择要调整其排名权重的组。
1. 拖动滑块可更改相应的贡献值。

   饼图以图形方式反映了您所做的更改。
1. 单击 **[!UICONTROL Save Changes]**.
1. 重新构建分阶段网站索引以预览添加规则的结果。

   请参阅[运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

   请参阅[运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。
