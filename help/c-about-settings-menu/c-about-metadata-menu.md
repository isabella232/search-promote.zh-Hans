---
description: 使用元数据菜单可自定义搜索定义和索引注入。
solution: Target
subtopic: Metadata
title: 关于元数据菜单
topic-legacy: Settings,Site search and merchandising
uuid: f12fc863-a140-45e8-b219-3dbfdef099cd
exl-id: 53d62da9-c5bd-4c4a-bb89-743704f66f7f
source-git-commit: 95bf92df17d7832df72e8d883a22f9063e53a18d
workflow-type: tm+mt
source-wordcount: '8028'
ht-degree: 1%

---

# 关于元数据菜单{#about-the-metadata-menu}

使用元数据菜单可自定义搜索定义和索引注入。

## 关于定义 {#concept_AE48035C210145169BE067D396975620}

您可以使用[!DNL Definitions]自定义客户提交搜索查询时考虑的HTML和元数据字段的内容和相关性。

您可以编辑已预定义的字段。 或者，您也可以根据元数据标记内容创建新的用户定义的字段。 每个定义都显示在[!DNL Staged Definitions]页面的一行中。

另请参阅[关于数据视图](../c-about-reports-menu/c-about-data-views.md#concept_DCA897D074464BC1861AA47B40CC86C3)。

## 添加新的元标记字段 {#task_6DF188C0FC7F4831A4444CA9AFA615E5}

您可以定义并添加自己的元数据标记字段。

在客户看到新元标记定义的效果之前，您必须重新构建网站索引。

**添加新的元标记字段**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**。
1. 在[!DNL Definitions]页面上，单击&#x200B;**[!UICONTROL Add New Field]**。
1. 在[!DNL Add Field]页面上，设置所需的选项。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>字段名称 </p> </td> 
      <td colname="col2"> <p>指定用于引用字段的名称。 </p> <p>字段名称必须遵循以下规则： </p> <p> 
      <ul id="ul_D39D09CD7E7D41A59ECB6C5A6F4F263D"> 
      <li id="li_11CE852BE3C64CEF90FEC7A6E1079E13"> 名称只能包含字母数字字符。 </li> 
      <li id="li_7FC340E7C58545C88CE9AF4AF09AD7AD"> 名称中允许使用破折号，但不允许使用空格。 </li> 
      <li id="li_996FF38457AB4C6DB22B15850A0830CC"> 您最多可以输入20个字符的名称。 </li> 
      <li id="li_C1019E587995444D9587D5EA495D719E"> 该名称不区分大小写，但会完全按照您键入的名称来显示和存储该名称。 </li> 
      <li id="li_E55404D6CE354EC89CFFEB1048A11F44"> 不能使用预定义字段中存在的名称，如<span class="wintitle">暂存定义</span>页面的表中所示。 </li> 
      <li id="li_7CE328AE3B5F45A8A09E2DA7ECB62551"> 不能将单词“any”用作用户定义的字段名称的值。 </li> 
      <li id="li_9B8287EED1784E79BFCBBBA956705CD2"> 您无法编辑预定义字段的名称。 </li> 
      </ul> </p> <p> 字段名称示例： </p> <p> 
      <ul id="ul_5881669913D04E35A6D4A6D31BEE7DF3"> 
        <li id="li_0AFFB8B516FE40F8A615C2F578F2CEA3"> 作者 </li> 
        <li id="li_7F0ADFBFB21E4B84ACA8A1CEBFE344D1"> PublishDate </li> 
        <li id="li_6D1BEB3D19AC499E9227EC115AEB6296"> 狂野 </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>元标记名称 </p> </td> 
      <td colname="col2"> <p>确定与定义的字段关联的内容。 </p> <p>名称列表最长可包含255个字符。 而且，名称可以包含HTML元标记的名称属性中允许使用的任何字符。 </p> <p>您可以在单个字段定义中指定多个元标记。 </p> <p>多个值必须以逗号分隔，并且在任何给定网页上找到的最左侧的元标记名称优先。 </p> <p>例如，假定您定义了一个名为“auth”的字段。 字段名称具有关联的元标记“author， dc.author”。 在这种情况下，如果网页上同时显示了“author”元标记的内容，则会将“author”元标记中的内容编入索引并搜索“dc.author”元标记中的内容。 </p> <p>用户定义的字段的定义中必须至少有一个元标记名称。 预定义的字段不需要具有关联的元标记。 但是，如果指定了一个或多个元标记，则元标记的内容将覆盖每个标记的当前数据源。 </p> <p>例如，如果元标记“dc.title”与预定义的“title”字段关联，则“dc.title”元标记中的内容将在 
      <code>
        &lt;title&gt; 
      </code>标记。 </p> <p>请参见如下示例： </p> <p> 
      <ul id="ul_0132E15FC19E4C0CA13CD5A12EA3BBEC"> 
      <li id="li_ECD3B194FECB4C2090CAEC8449320D3F"> dc.date </li> 
      <li id="li_09C76BC7AC7348859D01989697212E31"> 描述 </li> 
      <li id="li_9230C0450F9D424087D1F127048DA311"> 独资企业 </li> 
      </ul> </p> </td> 
    </tr> 
      <tr> 
      <td colname="col1"> <p>数据类型 </p> </td> 
      <td colname="col2"> <p>每个字段都有一个关联的数据类型，如文本、数字、日期、版本、排名或位置。 此数据类型确定字段内容的索引、搜索和排序（可选）方式。 </p> <p>创建字段定义后，便无法更改数据类型。 </p> <p>使用以下信息可帮助您选择与字段包含的信息相关的数据类型。 </p> <p> 
      <ul id="ul_A3AD5A0CF354410F836311F39151B8A6"> 
      <li id="li_9F412DA7D9EF497BA6E65F9CE10F3046"> <span class="uicontrol"> 文本 </span> 数据类型字段会被视为字符串。 </li> 
      <li id="li_AD78B75644AE40208F0239311015611F"> <span class="uicontrol"> 数字 </span> 数据类型字段会被视为整数或浮点数值。 </li> 
      <li id="li_0B46975C589148E9A7C32A8D250487B7"> <span class="uicontrol"> 日期 </span> 数据类型字段会被视为日期/时间说明符。在添加或编辑新字段时，您可以自定义允许的日期/时间格式。 </li> 
      <li id="li_BB68CB1DBE0543AC9000B3DEDFB28E7E"> <span class="uicontrol"> 版本 </span> 数据类型字段会被视为自由格式的数字数据。例如，1.2.3在1.2.2之前排序。 </li> 
      <li id="li_0BA895B4DADA46528A7A4161EEB1521E"> <span class="uicontrol"> 排名 </span> 数据类型字段与“数字”类型字段相同，不同之处在于它们还会影响搜索结果中的排名/相关性计算。 <p>请参阅<a href="../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397" type="concept" format="dita" scope="local">有关规则排名</a>。 </p> </li> 
      <li id="li_459405DA437049AD88AA1FAC28F04720"> <span class="uicontrol"> 位置 </span> 数据类型字段被视为世界上任何位置的物理位置。允许的位置格式包括： <p> 
      <ul id="ul_D2CEBFA1A5504AA996BA2F7641AFB7F3"> 
      <li id="li_5283A2F2D5D84840B3D920C08D43654C"> 5位或9位DDDDD或DDDDD-DDD格式的邮政编码，其中每个“D”是0-9位数字。 </li> 
      <li id="li_A5CD4DFC90164BC68183DB7D10603B7C"> 以DDD形式的三位数区域代码。 </li> 
      <li id="li_9DAEAE64BC7F4902B25043D998C8F56D"> 纬度/经度对的形式为±DD.DDD±DDD.DDD，其中第一个数字指定纬度，第二个数字指定经度。 </li> 
      </ul> </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>允许列表 </p> </td> 
      <td colname="col2"> <p>仅当选择了<span class="uicontrol">文本</span>或<span class="uicontrol">数字</span>时才可用。 </p> <p>在此字段的元数据内容中单独索引分隔的值。 </p> <p>例如，在选择“允许列表”时，“红、黄、绿、蓝”内容会被视为四个单独的值，而不是一个值。 此处理对于范围搜索(使用 
      <code>
        sp_q_min 
      </code>, 
      <code>
        sp_q_max 
      </code>或 
      <code>
        sp_q_exact 
      </code>)和 
      <code>
        &lt;search-field-value-list&gt; 
      </code>, 
      <code>
        &lt;search-field-values&gt; 
      </code>和 
      <code>
        &lt;search-display-field-values&gt; 
      </code>。 </p> <p>如果选择“版本”数据类型，则不可用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> 动态Facet </p> </td> 
      <td colname="col2"> <p> 
        <!--NEW 2/2/2014--> <p>注意：此功能在默认情况下不启用。请联系技术支持以将其激活以供您使用。 激活后，它会显示在用户界面中。 </p> </p> <p>将标识的Facet设置为动态。 </p> <p>Facet基于元标记字段构建。 元标记字段是低级的核心搜索层AdobeSearch&amp;Promote。 另一方面，Facet是GS（引导式搜索）的一部分，GS是AdobeSearch&amp;Promote的高级表示层。 Facet自有的元标记字段，但是，元标记字段对Facet一无所知。 </p> <p>请参阅<a href="../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local">关于动态Facet </a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>允许重复数据消除 </p> </td> 
      <td colname="col2"> <p>选中此选项可为此字段启用重复数据删除。 即，允许在搜索时通过 
        <code>
          sp_dedupe_field 
        </code>搜索CGI参数。 </p> <p>请参阅<a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local">搜索CGI参数</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>表名称 </p> </td> 
      <td colname="col2"> <p>将给定字段与给定表名永久关联。 </p> <p>每当在核心搜索CGI参数或模板标记中提及此类字段时，表名称便会自动提供。 此功能允许通过表匹配来选择动态Facet，但您也可以根据需要将其用于非动态Facet字段。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>列表分隔符 </p> </td> 
      <td colname="col2"> <p>仅在选择<span class="uicontrol">允许列表</span>时可用。 </p> <p>指定哪些字符分隔单个列表值。 您可以指定多个字符，每个字符都被视为值分隔符。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>默认搜索 </p> </td> 
      <td colname="col2"> <p>选择后，即使在给定的搜索查询中没有明确指定字段，也会搜索字段内容。 如果取消选择此选项，则仅在请求时搜索字段。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>垂直更新字段 </p> </td> 
      <td colname="col2"> <p> <p>注意：此功能在默认情况下不启用。请联系技术支持以将其激活以供您使用。 激活后，它会显示在用户界面中。 </p> </p> <p>将标识的字段设置为“垂直更新”字段。 </p> <p>“垂直更新”字段是通过“垂直更新”过程（“索引”</span> &gt; “垂直更新”</span>）进行更新的候选字段。 <span class="uicontrol"><span class="uicontrol">由于进行垂直更新的方式，在自由文本搜索中无法搜索来自这些字段的内容。 选中此选项会导致在任何类型的索引操作期间，此字段的内容未添加到“word”索引中。 它还允许在“垂直更新”操作期间更新此字段。 </span></span></p> <p>要了解有关垂直更新的更多信息，请参阅<a href="../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local">关于垂直更新</a> 。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>相关性 </p> </td> 
      <td colname="col2"> <p>您可以编辑预定义字段和用户定义的字段的相关性。 </p> <p>在1-10分级中指定相关性。 设置为1表示它最不相关，设置为10表示它最相关。 当软件考虑每个字段中的查询匹配时，会考虑这些值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>排序 </p> </td> 
      <td colname="col2"> <p>指定何时按命名字段对结果进行排序，具体方式为 
        <code>
          sp_s 
        </code>搜索CGI参数。 </p> <p>请参阅<a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local">搜索CGI参数</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>语言 </p> </td> 
      <td colname="col2"> <p>仅当选择数据类型<span class="uicontrol">排名</span>、<span class="uicontrol">数字</span>或<span class="uicontrol">日期</span>时才可用。 </p> <p>控制在索引此字段的日期、数字和排名值时应用的语言和区域设置约定。 </p> <p>您可以选择应用帐户语言（语言&gt;单词和语言）。 或者，也可以应用与包含每个数字或日期值的文档关联的语言，或者应用特定语言。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>日期格式 </p> </td> 
      <td colname="col2"> <p>仅当选择数据类型<span class="uicontrol">日期</span>时可用。 </p> <p>控制在索引此字段的日期值时识别的日期格式。 </p> <p>为每个日期字段提供了日期格式字符串的默认列表。 您可以添加到列表或编辑列表以满足您自己网站的需求。 </p> <p>请参阅<a href="../c-appendices/r-date-formats.md#reference_4D1FC1F6B9F44857967188496D8D335B" type="reference" format="dita" scope="local">日期格式</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>测试日期格式 </p> </td> 
      <td colname="col2"> <p>仅当选择数据类型<span class="uicontrol">日期</span>时才可用。 </p> <p>用于预览您指定的日期格式，以确保格式正确。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>时区 </p> </td> 
      <td colname="col2"> <p>仅当选择数据类型<span class="uicontrol">日期</span>时才可用。 </p> <p>控制在为未指定时区的此字段的日期值编制索引时应用的假定时区。 </p> <p>例如，如果帐户时区设置为“America/Los Angeles”，并且您选择了<span class="uicontrol">使用帐户时区</span>，则以下元日期值（没有指定时区）会被视为太平洋时间，并考虑夏令时： </p> <p>&lt;meta name="dc.date" content="Mon, 05 Sep 201213:12:00"&gt; </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最不重要的排名值 </p> </td> 
      <td colname="col2"> <p>仅当选择数据类型<span class="uicontrol">排名</span>时才可用。 </p> <p>控制表示任何文档的最低排名的排名值。 </p> <p>如果文档排名从最低排名的0到最高排名的10之间，则将此值设置为0。 </p> <p>如果文档排名从最高排名的1到最低排名的10，则将此值设置为10。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>默认排名值 </p> </td> 
      <td colname="col2"> <p>仅当选择数据类型<span class="uicontrol">排名</span>时才可用。 </p> <p>控制在文档不包含为此排名字段定义的任何元标记时所使用的排名值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最重要的排名值 </p> </td> 
      <td colname="col2"> <p>仅当选择数据类型<span class="uicontrol">排名</span>时才可用。 </p> <p>控制表示任何文档的最大排名的排名值。 </p> <p>如果文档排名从最低排名的0到最高排名的10之间，则将此值设置为10。 </p> <p>如果文档排名从最高排名的1到最低排名的10，则将此值设置为1。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>默认件数 </p> </td> 
      <td colname="col2"> <p>仅当选择<span class="uicontrol">位置</span>作为数据类型时才可用。 </p> <p>控制用于邻近搜索的距离值的处理。 </p> <p>如果将默认单位设置为<span class="uicontrol"> Miles </span>，则应用于此字段的任何接近搜索最小/最大距离标准(通过 
      <code>
        sp_q_min[_#] 
      </code>或 
      <code>
        sp_q_max[_#] 
      </code>搜索CGI参数)被视为英里，否则视为公里。 </p> <p>此选项还控制应用于输出的默认距离单位 
      <code>
        &lt;Search-Display-Field&gt; 
      </code>搜索结果模板标记。 </p> <p>请参阅<a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local">关于近距离搜索</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>创建范围描述？ </p> </td> 
      <td colname="col2"> <p>仅当选择<span class="uicontrol">数字</span>作为数据类型时才可用。 </p> <p>控制自动创建字段范围描述，以与<span class="uicontrol">设计</span> &gt; <span class="uicontrol">导航</span> &gt; <span class="uicontrol"> Facets </span>一起使用。 </p> <p>请参阅<a href="../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5" format="dita" scope="local">关于Facet </a>。 </p> <p> <p>注意： 如果此字段选中了<span class="uicontrol">垂直更新字段</span> ，则在垂直更新期间将更新生成的“字段范围”描述字段。 但是，建议在<span class="uicontrol">范围字段</span>中标识的字段也选中<span class="uicontrol">垂直更新字段</span>。 </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>范围字段 </p> </td> 
      <td colname="col2"> <p>仅当选中<span class="uicontrol">创建范围描述</span>时可用。 </p> <p>要更新的<span class="uicontrol">文本</span>字段，其中包含当前字段的范围描述。 此列表包含所有尚未与字段范围生成的其他字段一起使用的<span class="uicontrol">文本</span>字段。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>范围值 </p> </td> 
      <td colname="col2"> <p>仅当选中<span class="uicontrol">创建范围描述</span>并选择了<span class="uicontrol">范围字段</span>项时才可用。 </p> <p>创建字段范围描述时要使用的数据点列表以空白分隔。 例如： </p> <code> 10&amp;nbsp;20&amp;nbsp;50&amp;nbsp;100&amp;nbsp;1000 </code> <p>您可以按任意顺序输入这些值。 在保存值之前，会先对值进行排序和删除重复项。 您还可以指定负值和非整数值。 </p> <p>对于此字段的每个值： 
      <ul id="ul_C4B41AF5AADF4B84B9C489CE82FF7075"> 
      <li id="li_90736394A5AE4F5CA6B47687BCB627AA">如果值小于(&lt;)<span class="uicontrol">范围值</span>中的最小值，则使用<span class="uicontrol"> "Less Than" Format </span> </li> 
      <li id="li_A5C272B2D26A468CA07EB2046B2EA8A7">如果值大于或等于<span class="uicontrol">范围值</span>中最大值(&gt;=)，则使用<span class="uicontrol"> "Greater Than" Format </span>。 </li> 
      <li id="li_9DDFB70E1E824CF4819C57450C1A6DD2">否则，会找到一个“范围”，其中字段值位于两个连续的<span class="uicontrol">范围值</span>(大于(&gt;)较小值，小于或等于(&lt;=)较大值)之间，并且使用<span class="uicontrol">中间格式</span>。 </li> 
    </ul> </p> <p>例如，上面的值示例集将为值定义一组描述： 
    <ul id="ul_03ED30D5A19346AB8E6809BDD186A9A9"> 
      <li id="li_F97A6B3763954EFE9B6751F472AF7D20">少于10 </li> 
      <li id="li_12B6F636A6444B8292E0BFE4F55032DF">大于或等于10且小于20 </li> 
      <li id="li_545A2EAF5BD046B5AD59B77DB43DCD14">大于或等于20且小于50 </li> 
      <li id="li_26A8CD2422524D2CBD36794C6908572A">大于或等于50且小于100 </li> 
      <li id="li_05EBEEE68DC348E0821F1CC16D04D69C">大于或等于100且小于10000 </li> 
      <li id="li_9513A6B519394780A6A41B80762A0370">大于或等于10000 </li> 
      </ul> </p> <p>请参阅<span class="uicontrol">使用大于进行测试？ </span> 来更改这些测试的执行方式。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>“小于”格式 </p> </td> 
      <td colname="col2"> <p>仅当选中<span class="uicontrol">创建范围描述</span>并选择了<span class="uicontrol">范围字段</span>项时才可用。 </p> <p>此模板用于为小于<span class="uicontrol">范围值</span>中最小值的值指定范围描述。 最小值将使用数字占位符令牌<span class="uicontrol"> ~N~ </span>来表示。 例如： </p> <code> Less&amp;nbsp;than&amp;nbsp;~N~ </code> <p>或: </p> <code> ~N~&amp;nbsp;and&amp;nbsp;below </code> <p>通常，该值将按“原样”格式设置 — 即，对于“5 10 20”的<span class="uicontrol">范围值</span>定义和提供的值1，生成的范围描述将类似于“小于5”。 如果您希望它为“4.99及更低版本”，请将<span class="uicontrol"> Precision </span>设置为<span class="uicontrol"> 2 </span>并使用以下格式： </p> <code> ~n~&amp;nbsp;and&amp;nbsp;below </code> <p>在<span class="uicontrol"> "Less Than" Format </span>中，小写<span class="uicontrol"> ~n~ </span>将根据<span class="uicontrol"> Precision </span>设置将值四舍五入到<i> down</i>中。 </p> <p>注意：要按原样在范围描述中包含任何数字占位符，请使用反斜线(\)前缀指定 — 例如<span class="uicontrol"> \~N~ </span>或<span class="uicontrol"> \~n~ </span>。 要包含反斜线字符，请使用另一个反斜线(例如，<span class="uicontrol"> \\ </span>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>中间格式 </p> </td> 
      <td colname="col2"> <p>仅当选中<span class="uicontrol">创建范围描述</span>并选择了<span class="uicontrol">范围字段</span>项时才可用。 </p> <p>此模板用于为介于<span class="uicontrol">范围值</span>中找到的最小值和最大值之间的值指定范围描述。 对于给定范围，较低范围值将使用数字占位符令牌<span class="uicontrol"> ~L~ </span>表示，较高范围值将使用令牌<span class="uicontrol"> ~H~ </span>表示。 例如： </p> <code> ~L~&amp;nbsp;to&amp;nbsp;~H~ </code> <p>或: </p> <code> Between&amp;nbsp;~L~&amp;nbsp;and&amp;nbsp;~H~ </code> <p>或: </p> <code> Less&amp;nbsp;than&amp;nbsp;~H~&amp;nbsp;and&amp;nbsp;greater&amp;nbsp;than&amp;nbsp;~L~ </code> <p>通常，这些值将按“原样”格式设置 — 即，对于“5 10 20”的<span class="uicontrol">范围值</span>定义和提供的值8，生成的范围描述将类似于“5到10”。 如果希望其值为“5到9.99”，且值较高时向下调整<i></i>，请将<span class="uicontrol">精度</span>设置为<span class="uicontrol"> 2 </span>并使用以下格式： </p> <code> Between&amp;nbsp;~L~&amp;nbsp;and&amp;nbsp;~h~ </code> <p>同样，<span class="uicontrol"> ~L~ </span>可以被<span class="uicontrol"> ~l~ </span>替换，以便根据<span class="uicontrol">精度</span>设置，将较低值调整为<i>上方</i>。 这表示定义如下： </p> <code> Between&amp;nbsp;~l~&amp;nbsp;and&amp;nbsp;~H~ </code> <p>如果<span class="uicontrol">精度</span>值为<span class="uicontrol"> 2 </span>，则会创建“5.01到10之间”。 </p> <p>小写<span class="uicontrol"> ~l~ </span>将根据<span class="uicontrol">精度</span>设置使小写值<i>向上</i>舍入，小写<span class="uicontrol"> ~h~ </span>将使大写值<i>向下</i>舍入。 </p> <p>注意：要按原样在范围描述中包含任何数字占位符，请使用反斜线(\)前缀指定 — 例如<span class="uicontrol"> \~L~ </span>或<span class="uicontrol"> \~h~ </span>。 要包含反斜线字符，请使用另一个反斜线(例如，<span class="uicontrol"> \\ </span>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>“大于”格式 </p> </td> 
      <td colname="col2"> <p>仅当选中<span class="uicontrol">创建范围描述</span>并选择了<span class="uicontrol">范围字段</span>项时才可用。 </p> <p>此模板用于为大于<span class="uicontrol">范围值</span>中最大值的值指定范围描述。 最大值将使用数字占位符令牌<span class="uicontrol"> ~N~ </span>表示。 例如： </p> <code> Greater&amp;nbsp;than&amp;nbsp;~N~ </code> <p>或: </p> <code> ~N~&amp;nbsp;and&amp;nbsp;above </code> <p>通常，该值将按“原样”格式设置 — 即，对于“5 10 20”的<span class="uicontrol">范围值</span>定义和提供的值30，生成的范围描述将类似于“大于20”。 如果您希望它为“20.01及更高版本”，请将<span class="uicontrol"> Precision </span>设置为<span class="uicontrol"> 2 </span>并使用以下格式： </p> <code> ~n~&amp;nbsp;and&amp;nbsp;above </code> <p>在<span class="uicontrol"> "Greater Than" Format </span>中，小写<span class="uicontrol"> ~n~ </span>将根据<span class="uicontrol"> Precision </span>设置将值四舍五入到<i>上</i>。 </p> <p>注意：要按原样在范围描述中包含任何数字占位符，请使用反斜线(\)前缀指定 — 例如<span class="uicontrol"> \~N~ </span>或<span class="uicontrol"> \~n~ </span>。 要包含反斜线字符，请使用另一个反斜线(例如，<span class="uicontrol"> \\ </span>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>查准率 </p> </td> 
      <td colname="col2"> <p>仅当选中<span class="uicontrol">创建范围描述</span>并选择了<span class="uicontrol">范围字段</span>项时才可用。 </p> <p>指定小数点右侧位数的整数值。 这也控制舍入操作。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>脱零？ </p> </td> 
      <td colname="col2"> <p>仅当选中<span class="uicontrol">创建范围描述</span>时，才会选择<span class="uicontrol">范围字段</span>项，并设置了非零<span class="uicontrol">精度</span>值。 </p> <p>我们是否应将“0.50”显示为“。50”？ </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>去尾随零？ </p> </td> 
      <td colname="col2"> <p>仅当选中<span class="uicontrol">创建范围描述</span>时，才会选择<span class="uicontrol">范围字段</span>项，并设置了非零<span class="uicontrol">精度</span>值。 </p> <p>我们是否应将“10.00”显示为“10”？ </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>显示千位分隔符？ </p> </td> 
      <td colname="col2"> <p>仅当选中<span class="uicontrol">创建范围描述</span>并选择了<span class="uicontrol">范围字段</span>项时才可用。 </p> <p>我们是否应将“10000”显示为“10,000”？ 将使用区域设置特定的值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>是否调整零值？ </p> </td> 
      <td colname="col2"> <p>仅当选中<span class="uicontrol">创建范围描述</span>并选择了<span class="uicontrol">范围字段</span>项时才可用。 </p> <p>显示四舍五入零值时，是否应根据<span class="uicontrol">精度</span>设置向上或向下四舍五入？ 即显示“0.01”？ </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>是否使用大于进行测试？ </p> </td> 
      <td colname="col2"> <p>仅当选中<span class="uicontrol">创建范围描述</span>并选择了<span class="uicontrol">范围字段</span>项时才可用。 </p> <p>由于每个值都与<span class="uicontrol">范围值</span>中的值进行比较（按<i><b>降序</b></i>处理），因此，默认情况下，使用“大于”或“等于”(&gt;=)运算符比较该值，在测试成功后停止。 这意味着，如果使用一组<span class="uicontrol">范围值</span>（如“10 20 50 100 1000”），则值100将在100到1000之间，因为100实际上&gt;= 100。 如果希望比较值在50到100之间，请勾选此选项，这将导致比较使用大于(&gt;)运算符。 </p> <p>例如，对于此字段的每个值，如果选中此选项： 
      <ul id="ul_969621B1BD914FA5BD73ED21F8841010"> 
      <li id="li_157BEFDA7D0E44C481F4E4BC9046EF24">如果值小于或等于<span class="uicontrol">范围值</span>中的最小值(&lt;=)，则将使用<span class="uicontrol"> "Less Than" Format </span> </li> 
      <li id="li_737EE666CA6243A8864E17A311CF3ACC">如果值大于(&gt;)<span class="uicontrol">范围值</span>中的最大值，则将使用<span class="uicontrol"> "Greater Than" Format </span> </li> 
      <li id="li_353A9820F7F74CCCBB3281EC4CB48734">否则，将找到字段值介于两个连续<span class="uicontrol">范围值</span>(大于或等于(&gt;=)小于(&lt;)大小值)之间的范围，并且将使用<span class="uicontrol">中间格式</span> </li> 
    </ul> </p> <p>和：如果未选中，则： 
    <ul id="ul_945844C33C2E4D95A598C4876E15F211"> 
      <li id="li_653B6E2934574DA3B4BCEF07D0A84527">如果值小于(&lt;)<span class="uicontrol">范围值</span>中的最小值，则将使用<span class="uicontrol"> "Less Than" Format </span> </li> 
      <li id="li_AECA6880002F40FAB1820B37237550A7">如果值大于或等于<span class="uicontrol">范围值</span>中最大值(&gt;=)，则将使用<span class="uicontrol"> "Greater Than" Format </span> </li> 
      <li id="li_ECB2DF7CA592497298E9ADC708220366">否则，将找到字段值介于两个连续<span class="uicontrol">范围值</span>(大于(&gt;)小值且小于或等于(&lt;=)大值)之间的范围，并且将使用<span class="uicontrol">中间格式</span> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>测试 </p> </td> 
      <td colname="col2"> <p>仅当选中<span class="uicontrol">创建范围描述</span>并选择了<span class="uicontrol">范围字段</span>项时才可用。 </p> <p>提供示例数值，然后按<span class="uicontrol">测试</span>按钮以查看如何创建范围字段。 将在窗口中显示生成的范围描述。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

   另请参阅[添加新的元标记字段](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。
1. 单击 **[!UICONTROL Add]**.
1. （可选）如果要预览结果，请重新构建暂存站点索引。

   请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在[!DNL Definitions]页面上，执行以下任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;还原您所做的任何更改。

      请参阅[使用History选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送阶段设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 编辑预定义或用户定义的元标记字段 {#task_0A7657B63596421BB6DB3ED44F827AB3}

您只能编辑预定义元标记中的某些字段，或编辑用户定义的元标记中的所有字段。

在客户看到元标记更改的效果之前，必须重新构建网站索引。

**要编辑预定义或用户定义的元标记字段，请执行以下操作**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**。
1. 在[!DNL Definitions]页面的表[!DNL Actions]列中，单击要更改的元标记字段名称行中的&#x200B;**[!UICONTROL Edit]**。
1. 在[!DNL Pinned Keyword Results Manager]页面的表格中，单击要更改的关键字行中的&#x200B;**[!UICONTROL Edit]**。
1. 在[!DNL Edit Field]页面上，设置所需的选项。

   如果您选择更改预定义的元标记字段，请注意并非所有字段都可编辑。

   请参阅[Adding a new meta tag field](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)下的选项表。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）如果要预览结果，请重新构建暂存站点索引。

   请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在[!DNL Definitions]页面上，执行以下任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;还原您所做的任何更改。

      请参阅[使用History选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送阶段设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 删除用户定义的元标记字段 {#task_9361EF38B5E743038B6672FA6CF70FD3}

您可以删除不再需要或使用的用户定义的元标记字段。

您无法删除预定义的元标记字段。 但是，您可以编辑某些字段。

请参阅[编辑预定义或用户定义的元标记字段](../c-about-settings-menu/c-about-metadata-menu.md#task_0A7657B63596421BB6DB3ED44F827AB3)。

在客户看到删除元标记的效果之前，必须重新构建网站索引。

**删除用户定义的元标记字段**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**。
1. 在[!DNL Definitions]页面的表[!DNL User-defined fields]部分中，单击要删除的元标记字段名称行中的&#x200B;**[!UICONTROL Delete]**。
1. 在确认对话框中，单击&#x200B;**[!UICONTROL OK]**。
1. （可选）如果要预览结果，请重新构建暂存站点索引。

   请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在[!DNL Definitions]页面上，执行以下任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;还原您所做的任何更改。

      请参阅[使用History选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送阶段设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于注射 {#concept_DA091920671948A0A893A26B3A2FAAE5}

您可以使用[!DNL Injections]将内容插入网页，而无需自行编辑页面。

您可以将内容附加到特定的索引字段（如“target”或“body”），或将索引内容替换为新值。 例如，如果在“目标”元标记字段中插入新内容，则会像对硬编码页面内容一样处理此信息。 无论网站页面是否具有相应的内容，您都可以编辑任何预定义元标记字段的内容。 例如，您可以编辑以下预定义元标记字段名称的内容：

* Alt
* body
* charset
* 日期
* desc
* 键
* language
* Target
* title
* url

## 使用测试现场注入 {#section_74939EA9E6EA4D2A92E8066B3B11CF92}

您可以选择在[!DNL Staged Injections]页面上使用&#x200B;**[!UICONTROL Test]**。 您可以输入测试字段名称（例如，“标题”或“正文”）、原始字段值（例如，“主页”），以及您网站中的测试URL。 结果值将显示为您的引用。 测试期间不会更改当前值。

## 使用字段注入定义 {#section_C1BBF19DE8EF4A6F8CC3ED691F3953A9}

注入定义具有以下形式：

```
append|replace field [regexp] URL value
```

`append|replace`、`field`、`URL`。 和`value`项是必填项。 每行输入一个注入定义。 以下示例包含六种不同的注入定义。

```
replace title  https://www.yoursite.com/company/contactus.html Adobe: Contact Us 
append body https://www.yoursite.com/products/* On Sale Now! 
append target https://www.yoursite.com/news/bob_white/ Regular Weekly Feature 
append target regexp https://www.yoursite.com/travel/mr_travel/.*\column.html$ Regular Weekly Feature 
replace charset https://www.yoursite.com/japanese/intro.txt shift-jis 
replace language https://www.yoursite.com/japanese/intro.txt ja_JP
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>注入定义 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> 附加|替换  </span> </p> </td> 
   <td colname="col2"> <p>选择“append”以添加注入定义的值(“Adobe:联系我们”或“立即售出！” 中)到现有字段内容。 选择“替换”以使用定义的值覆盖现有字段内容。 如果字段当前没有内容，则无论使用哪种选项（追加或替换），都会自动添加定义的值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> 字段  </span> </p> </td> 
   <td colname="col2"> <p>字段名称为必填字段。 以下是十个可使用的预定义字段名称： </p> <p> 
     <ul id="ul_B9336FA53023474EAEE399116E7FC972"> 
      <li id="li_C621203DCD2B4875A54A1DD19F0B5B90"> <span class="codeph"> Alt </span> </li> 
      <li id="li_9217E6A037254BEDBB8D006B70D7670D"> <span class="codeph"> body </span> </li> 
      <li id="li_DCDC50F93F224F02897419B745E09399"> <span class="codeph"> charset </span> </li> 
      <li id="li_D95668236B6547B99966668C82B302AB"> <span class="codeph"> 日期 </span> </li> 
      <li id="li_D2071681274345C3B97E9ADA6D223271"> <span class="codeph"> desc  </span> </li> 
      <li id="li_26683A9209454A438D811187FB929482"> <span class="codeph"> 键  </span> </li> 
      <li id="li_A5E19F81B872402CA62B5AB9497E030D"> <span class="codeph"> language </span> </li> 
      <li id="li_FD0B1CD9E6304B18B9D7F57E61015107"> <span class="codeph"> 目标  </span> </li> 
      <li id="li_400D7E3F3E9B47EFB2FF5C0D278DB573"> <span class="codeph"> title </span> </li> 
      <li id="li_449BCBEE4F64424BB69F780C10F5956C"> <span class="codeph"> url </span> </li> 
     </ul> </p> <p>每个字段名称都对应于您网站页面上的元素。 例如，如果指定字段名称<span class="codeph"> desc </span>，则可以将注入定义值添加到与网站页面上的描述Meta标记对应的字段中。 </p> <p>如果您的页面上不存在描述元标记，则定义的内容会为您创建该标记。 在<span class="codeph"> desc </span>注入中指定的内容会像硬编码的元描述内容一样显示在结果页面上。 </p> <p>您还可以创建具有相同字段名称的多个定义。 例如，假定您注射了以下内容： </p> <p> <code> replace&nbsp; <b>title</b>&nbsp;https://www.mysite.com/&nbsp;Welcome&nbsp;to&nbsp;My&nbsp;Site </code> </p> <p> <code> replace&nbsp; <b>title</b>&nbsp;https://www.mysite.com/company/*.html&nbsp;My&nbsp;Site:&nbsp;Contact </code> </p> <p>上述示例中的所有网站页面都将收到一个插入的标题“欢迎使用我的网站”。 “/company/”文件夹中的页面会插入一个新标题“My Site:联系我们”，以替换前一个页面。 </p> <p>请注意，注入的应用顺序是<span class="wintitle">字段注入定义</span>文本框中注入的顺序。 如果在同一位置的页面多次定义同一字段（本例中为“标题”），则优先使用后面的定义。 </p> <p> <span class="codeph"> [regexp]  </span>  — 可选。如果选择使用<span class="codeph"> regexp </span>选项，则定义的URL将被视为正则表达式。 </p> <p>请参阅<a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local">正则表达式</a>。 </p> <p>在以下定义中： </p> <p> <code> replace&nbsp;target&nbsp; <b>regexp&amp;nbsp;^.*/products/.*\.html$</b>&nbsp;Important&nbsp;information </code> </p> <p> “重要信息”将插入到与正则表达式<span class="codeph"> ^匹配的所有页面的“target”字段中。*/产品/.*\.html$ </span>. </p> <p>因此，您具有以下功能： </p> <p> <code> https://www.mydomain.com/products/page1.html 
      &nbsp;&nbsp;&nbsp;&nbsp;(Will&nbsp;receive&nbsp;"target"&nbsp;content) </code> </p> <p> <code> https://www.mydomain.com/product/oldstuff.html 
      &nbsp;&nbsp;&nbsp;&nbsp;(Will&nbsp;not&nbsp;receive&nbsp;"target"&nbsp;content) </code> </p> <p>在以下示例中： </p> <p> <code> append&amp;nbsp;title&amp;nbsp;regexp&amp;nbsp;^.*\.pdf$&amp;nbsp;Millennium&amp;nbsp;Science </code> </p> <p>此注入会将“Millennium Science”附加到所有以“.pdf”扩展名结尾的页面的“标题”内容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph">URL</span> </p> </td> 
   <td colname="col2"> <p>需要URL并指定插入哪些文档。 </p> <p>该URL是以下任一URL: </p> <p> 
     <ul id="ul_C5C74F6D5EA943B293742989EB822751"> 
      <li id="li_382392DB778D4E14BFFC96D35A861951"> 完整路径，如https://www.mydomain.com/products.html中所示 </li> 
      <li id="li_EA2BD0FB66A44CD0844613316F6174D4"> 部分路径，如https://www.mydomain.com/products中所示 </li> 
      <li id="li_D5E0D6D897C8493ABBFC65517CD4A7DB"> 使用通配符的URL，如https://www.mydomain.com/*.html中所示 </li> 
     </ul> </p> <p>URL值中不得包含任何空格字符。 如果使用<span class="codeph"> regexp </span>选项，则URL会被视为正则表达式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> value </span> </p> </td> 
   <td colname="col2"> <p>值是必需的，用于替换现有字段内容或将其添加到现有字段内容中。 您可以为同一字段名称指定多个值。 例如： </p> <p>附加<b>键</b> https://www.mysite.com/travel/ <b>summer</b>、 <b>beach</b>、 <b>sand</b> </p> <p>附加<b>keys</b> https://www.mysite.com/travel/fare/*.html <b>cheal tickets</b> </p> <p>在上例中，单词“summer， beach， sand”会附加到“/travel/”目录所有页面的“keys”字段中。 “ceap tickets”一词还会附加到“/travel/fare/”目录所有页面的“keys”字段中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

另请参阅[选择要爬网和索引的内容类型](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8)。

## 添加字段注入定义 {#task_E86566FA1FF74CF68115C0ADA05172AE}

您可以使用[!DNL Injections]将内容插入网页，而无需自行编辑页面。

您可以选择在[!DNL Injections]页面上使用&#x200B;**[!UICONTROL Test]**。 您可以输入测试字段名称（例如，“标题”或“正文”）、原始字段值（例如，“主页”），以及您网站中的测试URL。 结果值将显示为您的引用。 测试期间不会更改当前值。

**添加字段注入定义**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]**。
1. （可选）在[!DNL Injections]页面的[!DNL Test Field Injections]区域中，输入测试字段、测试原始值和测试URL，然后单击&#x200B;**[!UICONTROL Test]**。
1. 在[!DNL Field Injection Definitions]字段中，为每行输入一个注入定义。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行以下任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;还原您所做的任何更改。

      请参阅[使用History选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送阶段设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于属性加载器 {#concept_9EF38E98811B42CDA41996432B9AD209}

使用[!DNL Attribute Loader]定义其他输入源以扩充从网站爬网的数据。

>[!NOTE]
>
>要使用属性加载器，您可能需要由Adobe帐户代表或Adobe支持在您的帐户中启用它。

您可以使用数据馈送输入源访问以不同于通常在网站上发现的表单形式存储的内容。 使用可用的爬网方法之一执行此操作。 然后，可以将来自这些源的数据注入来自爬网内容的数据。

在[!DNL Staged Attribute Loader Definitions]页面中添加属性加载器定义后，可以更改除名称值和类型值之外的任何配置设置

[!DNL Attribute Loader]页面显示以下信息：

* 您配置并添加的已定义属性加载器配置的名称。
* 您添加的每个连接器的以下数据源类型之一：

   * **文本**  — 简单的“平面”文件、以逗号分隔、制表符分隔或其他一致分隔的格式。
   * **信息源**  - XML信息源。

* 是否为下一个爬网和索引启用配置。
* 数据源的地址。

另请参阅[属性注入过程如何用于文本和信息源……](../c-about-settings-menu/c-about-metadata-menu.md#section_E059A33D61EE4DB0972A37B8A35E9E16)

另请参阅[关于配置多个属性加载器](../c-about-settings-menu/c-about-metadata-menu.md#section_4CC49C74EF294608A184E233F215ADFF)

另请参阅[关于添加属性时使用预览……](../c-about-settings-menu/c-about-metadata-menu.md#section_E9CAB000A94C4D9189786C1EDB1CDB46)

## 属性注入过程如何用于属性加载器中的文本和信息源配置 {#section_E059A33D61EE4DB0972A37B8A35E9E16}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>步骤 </p> </th> 
   <th colname="col2" class="entry"> <p>过程 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>下载数据源。 </p> </td> 
   <td colname="col3"> <p>对于文本和信息源配置，只需下载一个简单的文件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>将下载的数据源划分为单个伪文档。 </p> </td> 
   <td colname="col3"> <p>对于<span class="uicontrol">文本</span>，每行以换行符分隔的文本都对应于单个文档，并使用指定的分隔符（如逗号或制表符）进行解析。 </p> <p>对于<span class="uicontrol">馈送</span>，使用以下形式的正则表达式模式提取每个文档的数据： </p> <p> <code class="syntax js"> &lt;${Itemtag}&gt;(.*?)&lt;/${Itemtag}&gt; </code> </p> <p>使用<span class="uicontrol">属性加载器添加</span>页面上的</span>映射<span class="wintitle"> ，创建数据的缓存副本，然后为Crawler创建链接列表。 数据存储在本地缓存中，并填充配置的字段。 </span></p> <p>解析后的数据被写入本地缓存。 </p> <p>稍后读取此缓存，以创建爬网程序所需的简单HTML文档。 例如： </p> <p> <code class="syntax html"> &lt;html&gt;&lt;head&gt; 
      &lt;title&gt;{title}&lt;/title&gt; 
      &lt;meta&nbsp;name="{field}"&nbsp;content="{data}"&nbsp;/&gt; 
      ... 
      &lt;/head&gt;&lt;body&gt; 
      {body} 
      &lt;/body&gt;&lt;/html&gt; </code> </p> <p><span class="codeph"> &lt;title&gt; </span>元素仅在映射存在于“标题”元数据字段时生成。 同样，仅当存在到Body元数据字段的映射时，才会生成<span class="codeph"> &lt;body&gt; </span>元素。 </p> <p> <b>重要信息</b>:不支持为预定义URL元标记分配值。 </p> <p>对于所有其他映射，将为每个包含原始文档中找到数据的字段生成<span class="codeph"> &lt;meta&gt; </span>标记。 </p> <p>每个文档的字段都会添加到缓存中。 对于写入到缓存的每个文档，也会生成一个链接，如以下示例中所示： </p> <p> <code class="syntax html"> &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      .... </code> </p> <p>配置的映射必须有一个字段被标识为主键。 此映射构成从缓存获取数据时使用的键。 </p> <p>Crawler可识别URL <span class="codeph">索引：</span>方案前缀，然后可以访问本地缓存的数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>爬取缓存的文档集。 </p> </td> 
   <td colname="col3"> <p><span class="codeph">索引：</span>链接将添加到Crawler的待处理列表，并按正常爬网顺序进行处理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>处理每个文档。 </p> </td> 
   <td colname="col3"> <p>每个链接的键值都与缓存中的一个条目相对应，因此爬取每个链接会导致从缓存中获取该文档的数据。 然后，该图像会“组合”到HTML图像中，并进行处理并添加到索引中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 关于配置多个属性加载器 {#section_4CC49C74EF294608A184E233F215ADFF}

您可以为任何帐户定义多个属性加载器配置。

添加属性加载器时，您可以选择使用功能&#x200B;**[!UICONTROL Setup Maps]**&#x200B;下载数据源的示例。 检查数据是否适合。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p> 属性加载器类型 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>文本 </p> </td> 
   <td colname="col2"> <p>通过先尝试制表符，然后再尝试垂直条(<span class="codeph"> | </span>)，最后用逗号(<span class="codeph"> 、 </span>)。 如果在单击<span class="uicontrol">设置图</span>之前已指定分隔符值，则将改用该值。 </p> <p>最适合方案会在映射字段中填充相应标记和字段值的猜测值。 此外，还显示所解析数据的采样。 如果您知道文件包含标题行，请务必在第一行</span>中选择<span class="uicontrol">标题。 设置函数使用此信息来更好地识别生成的映射条目。 </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>信息源 </p> </td> 
   <td colname="col2"> <p>下载数据源并执行简单的XML解析。 </p> <p>生成的XPath标识符显示在映射表的标记行中，并在字段中显示类似值。 这些行仅标识可用数据，并且不会生成更复杂的XPath定义。 但是，它仍然很有用，因为它描述了XML数据并标识了Itemtag。 </p> <p> <p>注意： “设置映射”功能下载整个XML源以执行其分析。 如果文件较大，此操作可能会超时。 </p> </p> <p>成功后，此函数将标识所有可能的XPath项目，其中许多项目是不想使用的。 请务必检查生成的映射定义，并删除您不需要或不需要的映射定义。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>“设置映射”功能可能不适用于大型XML数据集，因为其文件解析器尝试将整个文件读入内存。 因此，您可能会遇到内存不足的情况。 但是，当在索引时处理同一文档时，它不会读入内存。 相反，大文档会“在移动中”进行处理，而不会首先完全读入内存。

## 关于在添加属性加载器时使用“预览” {#section_E9CAB000A94C4D9189786C1EDB1CDB46}

属性加载器数据在“索引”操作之前加载。

在添加属性加载器时，您可以选择使用功能&#x200B;**[!UICONTROL Preview]**&#x200B;来验证数据，就像在保存它一样。 它会针对配置运行测试，但不会将配置保存到帐户。 测试访问配置的数据源。 但是，它会将下载缓存写入临时位置；它与索引爬网程序使用的主缓存文件夹不冲突。

仅预览按&#x200B;**Acct:IndexConnector-Preview-Max-Documents**&#x200B;控制的方式处理默认的5个文档。 预览的文档以源形式显示，如向索引爬网程序显示。 显示内容类似于Web浏览器中的“查看源”功能。 您可以使用标准导航链接导航预览集中的文档。

预览不支持XML配置，因为此类文档是直接处理的，不会下载到缓存中。

## 添加属性加载器定义 {#task_A735E5EF763343A9B675E1A3B09AFDBC}

每个属性加载器配置定义一个数据源和映射，以将为该源定义的数据项与索引中的元数据字段相关联。

>[!NOTE]
>
>要使用属性加载器，您可能需要由Adobe帐户代表或Adobe支持在您的帐户中启用它。

在客户看到新定义和已启用定义的效果之前，请重新构建网站索引。

**添加属性加载器定义**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**。
1. 在[!DNL Stage Attribute Loader Definitions]页面上，单击&#x200B;**[!UICONTROL Add New Attribute Loader]**。
1. 在[!DNL Attribute Loader Add]页面上，设置所需的配置选项。 可用的选项取决于您选择的&#x200B;**[!UICONTROL Type]**。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>名称 </p> </td> 
      <td colname="col2"> <p>属性加载器配置的唯一名称。 您可以使用字母数字字符。 还允许使用字符“_”和“ — ”。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>类型 </p> </td> 
      <td colname="col2"> <p>数据源。 您选择的数据源类型会影响<span class="wintitle">属性加载器添加</span>页面上可用的生成选项。 您可以从以下选项中进行选择： </p> <p> 
      <ul id="ul_1ADC3DFBC929467385F7465BE8E13635"> 
      <li id="li_64FCD749F55442BAB316BD474128D4F9"> <span class="uicontrol"> 文本 </span> <p>简单的平面文本文件、以逗号分隔、制表符分隔或其他一致分隔的格式。 每个以换行符分隔的文本行对应于单个文档，并使用指定的分隔符进行解析。 </p> <p>您可以从1(1)开始，将每个值或列映射到由列号引用的元数据字段。 </p> </li> 
      <li id="li_2A4F16CE6DCE4114B7F8E4FE156252BB"> <span class="uicontrol"> 信息源 </span> <p>下载包含多个“行”信息的主XML文档。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>数据源类型：文本</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>启用 </p> </td> 
      <td colname="col2"> <p>将配置“打开”以供使用。 或者，您也可以关闭配置以阻止使用。 </p> <p> <b>注意</b>:已禁用的属性加载器配置将被忽略。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>主机地址 </p> </td> 
      <td colname="col2"> <p>指定数据所在的服务器主机的地址。 </p> <p>如果需要，您可以指定数据源文档的完整URI（统一资源标识符）路径，如以下示例中所示： </p> <p> <code otherprops="syntax html"> https://www.somewhere.com/some_path/some_file.tsv </code> </p> <p>或 </p> <p> <code class="syntax html"> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.csv </code> </p> <p>URI将划分为主机地址、文件路径、协议以及用户名和密码（可选）字段的相应条目 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>文件路径 </p> </td> 
      <td colname="col2"> <p>指定简单平面文本文件、以逗号分隔、制表符分隔或其他一致分隔格式文件的路径。 </p> <p>路径相对于主机地址的根。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>协议 </p> </td> 
      <td colname="col2"> <p>指定用于访问文件的协议。 您可以从以下选项中进行选择： </p> <p> 
      <ul id="ul_F6BC10FD51CA4A1D855B2B3212838A9C"> 
      <li id="li_79FB7DC65E774ABBB23E57BF98AD9738"> HTTP <p>如有必要，您可以输入正确的身份验证凭据来访问HTTP服务器。 </p> </li> 
      <li id="li_BAA9AD5E4B014E09B3A66C94022B7225"> HTTPS <p>如有必要，您可以输入正确的身份验证凭据来访问HTTPS服务器。 </p> </li> 
      <li id="li_E716ABB169DD408BA91F1CA27F445A16"> FTP <p>您必须输入正确的身份验证凭据才能访问FTP服务器。 </p> </li> 
      <li id="li_FD7143019C5244C3B8A5B1B5AA84859A"> SFTP <p>您必须输入正确的身份验证凭据才能访问SFTP服务器。 </p> </li> 
      <li id="li_38E0036C1365419F9D00083CACA34AFB"> File（文件） </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>超时 </p> </td> 
      <td colname="col2"> <p>指定FTP、SFTP、HTTP或HTTPS连接的超时时间（以秒为单位）。 此值必须介于30到300之间。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>重试 </p> </td> 
      <td colname="col2"> <p>指定失败的FTP、SFTP、HTTP或HTTPS连接的最大重试次数。 此值必须介于0和10之间。 </p> <p>值为零(0)将阻止重试尝试。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>编码 </p> </td> 
      <td colname="col2"> <p>指定在指定的数据源文件中使用的字符编码系统。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Delimiter（分隔符） </p> </td> 
      <td colname="col2"> <p>指定要在指定的数据源文件中描绘每个字段时使用的字符。 </p> <p>逗号字符(<span class="codeph"> 、 </span>)是分隔符的示例。 逗号用作字段分隔符，有助于分隔指定数据源文件中的数据字段。 </p> <p>选择<span class="uicontrol">选项卡？ </span> 使用“水平制表符”字符作为分隔符。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>第一行中的标题 </p> </td> 
      <td colname="col2"> <p>表示数据源文件中的第一行仅包含标题信息，而不包含数据。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>过时的日子 </p> </td> 
      <td colname="col2"> <p>设置属性加载器数据下载之间的最小间隔。 在下载刷新频率间隔内发生的索引触发的下载将被忽略。 如果将此值设置为默认值1，则属性加载器数据在24小时内不会多次下载。 在下载刷新频率间隔内发生的所有搜索索引都使用上次下载的数据集。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>地图 </p> </td> 
      <td colname="col2"> <p>使用列号指定列到元数据的映射。 </p> <p> 
      <ul id="ul_981AE2C6D30443BDBFC6575D413732A2"> 
      <li id="li_A42CB9DFFF8C45A7BAC2D471FE96CEBE"> <span class="uicontrol"> 列 </span> <p> 指定列号，第一列为1(1)。 要为每列添加新映射行，请在<span class="wintitle">操作</span>下，单击<span class="uicontrol"> + </span>。 </p> <p>您无需引用数据源中的每个列。 相反，您可以选择跳过值。 </p> </li> 
      <li id="li_26E8C9554A5D4BC5A5073D6385E3626F"> <span class="uicontrol"> 字段 </span> <p>定义用于每个生成的&lt;meta&gt;标记的名称属性值。 </p> </li> 
      <li id="li_5DFA514B7F9549B98D6CBC095A66033C"> <span class="uicontrol"> 元数据? </span> <p>使<span class="uicontrol">字段</span>成为下拉列表，您可以从中为当前帐户选择定义的元数据字段。 </p> <p>如果需要，<span class="uicontrol">字段</span>值可以是未定义的元数据字段。 未定义的元数据字段有时对创建<span class="wintitle">筛选脚本</span>所使用的内容非常有用。 </p> <p>请参阅<a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local">关于筛选脚本</a>。 </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892C95"> <span class="uicontrol"> 主键？  </span> <p>只有一个字段被标识为主键。 此字段将用作“外键”，以将属性加载器数据与索引中的相应文档进行匹配。 </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892D96"> <span class="uicontrol"> 删除HTML?  </span> <p>选中此选项后，在此字段数据中找到的任何HTML标记都将被删除。 </p> </li> 
      <li id="li_359D2902859B4C5BADB0BA26F0BA4DC0"> <span class="uicontrol"> 操作 </span> <p>用于向映射中添加行或从映射中删除行。 行的顺序不重要。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>数据源类型：信息源</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>启用 </p> </td> 
      <td colname="col2"> <p>将配置“打开”以供使用。 或者，您也可以关闭配置以阻止使用。 </p> <p> <b>注意</b>:已禁用的属性加载器配置将被忽略。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>主机地址 </p> </td> 
      <td colname="col2"> <p>指定数据所在的服务器主机的地址。 </p> <p>如果需要，您可以指定数据源文档的完整URI（统一资源标识符）路径，如以下示例中所示： </p> <p> <code class="syntax html"> https://www.somewhere.com/some_path/some_file.tsv </code> </p> <p>或 </p> <p> <code class="syntax html"> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.csv </code> </p> <p>URI将划分为主机地址、文件路径、协议以及用户名和密码（可选）字段的相应条目。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>文件路径 </p> </td> 
      <td colname="col2"> <p>指定包含多个“行”信息的主XML文档的路径。 </p> <p>路径相对于主机地址的根。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>协议 </p> </td> 
      <td colname="col2"> <p>指定用于访问文件的协议。 您可以从以下选项中进行选择： </p> <p> 
      <ul id="ul_976A34FD14A841F2B610C1C0CCBB82B9"> 
      <li id="li_05BBA0F670F14431A89AE4178F1A6F94"> HTTP <p>如有必要，您可以输入正确的身份验证凭据来访问HTTP服务器。 </p> </li> 
      <li id="li_100446691F304572B8FC3F083F86A2CB"> HTTPS <p>如有必要，您可以输入正确的身份验证凭据来访问HTTPS服务器。 </p> </li> 
      <li id="li_027088A8E30444DAA8CCCC5B0BAA74C1"> FTP <p>您必须输入正确的身份验证凭据才能访问FTP服务器。 </p> </li> 
      <li id="li_DCEF9D5C99354990B03E29083C2ED8DC"> SFTP <p>您必须输入正确的身份验证凭据才能访问SFTP服务器。 </p> </li> 
      <li id="li_44E34FF2AB0D429EB3408106E6FCF780"> File（文件） </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Itemtag </p> </td> 
      <td colname="col2"> <p>标识可用于标识您指定的数据源文件中各个XML行的XML元素。 </p> <p>例如，在AdobeXML文档的以下馈送片段中，Itemtag值为<span class="codeph">记录</span>: </p> <p> <code class="syntax xml"> &lt;?xml&nbsp;version="1.0"&nbsp;encoding="utf-8"?&gt; 
        &lt;!DOCTYPE&nbsp;gsafeed&nbsp;PUBLIC&nbsp;"-//Google//DTD&nbsp;GSA&nbsp;Feeds//EN"&nbsp;""&gt; 
        &lt;gsafeed&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;datasource&gt;marketplace&lt;/datasource&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;feedtype&gt;incremental&lt;/feedtype&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;group&nbsp;action="add"&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa/ 
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=1&nbsp;action="add"&nbsp;mimetype="text/html"displayurl="https://www.adobe.com/cfusion/marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=1"&gt; 
        &lt;metadata&gt; 
        &lt;meta&nbsp;name="mp_mkt"&nbsp;content="1"/&gt; 
        &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
        dbreferenced/marketplaceicons/icn_air.png"/&gt; 
        &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;AIR&nbsp;Marketplace"/&gt; 
        &lt;meta&nbsp;name="description"&nbsp;content="Discover&nbsp;new&nbsp;applications&nbsp;..."/&gt; 
        &lt;/metadata&gt; 
        &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;AIR&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Discover&nbsp;new&nbsp;applications&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;&lt;/cntent&gt; 
        &lt;/record&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa/ 
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=2&nbsp;action="add"&nbsp;mimetype="text/html"&nbsp;displayurl="https://www.adobe.com/cfusion/ 
        marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=2"&gt; 
        &lt;metadata&gt; 
        &lt;meta&nbsp;name="mp_mkt"&nbsp;content="2"/&gt; 
        &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
        dbreferenced/marketplaceicons/icn_photoshop.png"/&gt; 
        &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;Photoshop&nbsp;Marketplace"/&gt; 
        &lt;meta&nbsp;name="description"&nbsp;content="Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;..."/&gt; 
        &lt;/metadata&gt; 
        &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;Photoshop&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;/content&gt; 
        &lt;/record&gt; 
        ... 
        &lt;record&gt; 
        ... 
        &lt;/record&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/group&gt; 
        &lt;/gsafeed&gt; 
        </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>交叉引用字段名称 </p> </td> 
      <td colname="col2"> <p>指定一个元数据字段，其值将用作属性加载器配置数据中的查找“键”。 如果未选择任何值(<b>—None—</b>)，则此配置的数据不可用于排名计算（<b>规则</b> &gt; <b>排名规则</b> &gt; <b>编辑规则</b>）。 当您选择值时，此字段的值将用于使用此配置数据交叉引用网站搜索/推销文档。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>过时的日子 </p> </td> 
      <td colname="col2"> <p>设置属性加载器数据下载之间的最小间隔。 在下载刷新频率间隔内发生的索引触发的下载将被忽略。 如果将此值设置为默认值1，则属性加载器数据在24小时内不会多次下载。 在下载刷新频率间隔内发生的所有搜索索引都使用上次下载的数据集。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>地图 </p> </td> 
      <td colname="col2"> <p>允许您使用XPath表达式指定XML元素到元数据的映射。 </p> <p> 
      <ul id="ul_604108C0277C4892AE8A40CA39889ABD"> 
      <li id="li_0AF92270AE9F4BA8B2C7EE41FABC0F34"> <span class="uicontrol"> 标记 </span> <p>指定解析的XML数据的XPath表示形式。 使用上面的示例AdobeXML文档，在选项Itemtag下，可以使用以下语法映射该文档： </p> <p> <code class="syntax xml"> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
        /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>上述语法的转换如下： </p> <p> 
        <ul id="ul_6400EBD08D424EADA1612FE4F7EFB640"> 
        <li id="li_9958F9B40D42434195597DBA9F2AF28F"> <code class="syntax xml"> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p><span class="codeph">显示<span class="codeph">记录</span>元素的</span>属性映射到元数据字段<span class="codeph"> page-url </span>。 </p> </li> 
        <li id="li_759013EA02CD48BE971A55B0A6A11424"> <code class="syntax xml"> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>任何<span class="codeph">元</span>元素的<span class="codeph">内容</span>属性（包含在<span class="codeph">元数据</span>元素内），该元素包含在<span class="codeph">记录</span>元素内，其名称属性为<span class="codeph">标题</span>，并映射到元数据字段<span class="codeph">标题</span>。 </p> </li> 
        <li id="li_E741CA59197D462EB2946EDE874AFDC8"> <code class="syntax xml"> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>任何<span class="codeph">元</span>元素的<span class="codeph">内容</span>属性（包含在<span class="codeph">元数据</span>元素内），该元素包含在<span class="codeph">记录</span>元素内，其名称属性为<span class="codeph">描述</span>，并映射到元数据字段<span class="codeph"> desc </span>。 </p> </li> 
        <li id="li_E35EAE3D284D46D485D9064D7BB6AB13"> <code class="syntax xml"> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>包含在<span class="codeph">元数据</span>元素内的任何<span class="codeph">元元素的</span>内容<span class="codeph">属性（该元素包含在<span class="codeph">记录</span>元素内，其名称属性为<span class="codeph">描述</span>）映射到元数据字段<span class="codeph">正文</span>。</span> </p> </li> 
        </ul> </p> <p>XPath是一种相对复杂的表示法。 有关更多信息，请访问以下位置： </p> <p>请参阅<a href="https://www.w3schools.com/xml/xpath_intro.asp" scope="external" format="html"> https://www.w3schools.com/xml/xpath_intro.asp </a> </p> </li> 
      <li id="li_8147075D7ACD4811A7ED335F23FE62A6"> <span class="uicontrol"> 字段 </span> <p>定义用于每个生成的<span class="codeph"> &lt;meta&gt; </span>标记的名称属性值。 </p> </li> 
      <li id="li_2380199D63BF425A919606D8232FA6E2"> <span class="uicontrol"> 元数据? </span> <p>使<span class="uicontrol">字段</span>成为下拉列表，您可以从中为当前帐户选择定义的元数据字段。 </p> <p>如果需要，<span class="uicontrol">字段</span>值可以是未定义的元数据字段。 未定义的元数据字段有时对创建<span class="wintitle">筛选脚本</span>使用的内容非常有用。 </p> <p>请参阅<a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local">关于筛选脚本</a>。 </p> <p>当属性加载器在任意映射字段上处理具有多个点击的XML文档时，这些值将合并到生成的缓存文档中的单个值中。 默认情况下，这些值使用逗号分隔符组合。 但是，假定相应的<span class="wintitle">字段</span>值是定义的元数据字段。 此外，该字段还设置了<span class="wintitle">允许列表</span>属性。 在这种情况下，将在串联中使用字段的列表分隔符值（定义的第一个分隔符）。 </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC70E"> <span class="uicontrol"> 主键？  </span> <p>只有一个字段被标识为主键。 此字段将用作“外键”，以将属性加载器数据与索引中的相应文档进行匹配。 </p> </li> 
      <li id="li_80D6AF130FCE40AC972FE4B605B86BF6"> <span class="uicontrol"> 删除HTML?  </span> <p>选中此选项后，在此字段数据中找到的任何HTML标记都将被删除。 </p> </li> 
      <li id="li_D40E2F9AD8AD49FC9AC4B8C75BA31E28"> <span class="uicontrol"> 操作 </span> <p>用于向映射中添加行或从映射中删除行。 行的顺序不重要。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. （可选）单击&#x200B;**[!UICONTROL Setup Maps]**&#x200B;下载数据源的示例。 检查数据是否适合。
1. 单击&#x200B;**[!UICONTROL Add]**&#x200B;将配置添加到[!DNL Attribute Loader Definitions]页面。
1. 在[!DNL Attribute Loader Definitions]页面上，单击&#x200B;**[!UICONTROL rebuild your staged site index]**。
1. （可选）在[!DNL Attribute Loader Definitions]页面上，执行以下任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;还原您所做的任何更改。

      请参阅[使用History选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送阶段设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 编辑属性加载器定义 {#task_AA2D1B2BCAFA44A6A0C59A0318274E80}

您可以编辑已定义的现有属性加载器。

>[!NOTE]
>
>要使用属性加载器，您可能需要由Adobe帐户代表或Adobe支持在您的帐户中启用它。

并非所有属性加载器选项都可供您更改，例如[!DNL Type]下拉列表中的“属性加载器名称”或“类型”。

**编辑属性加载器定义**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**。
1. 在[!DNL Attribute Loader]页面的[!DNL Actions]列标题下，单击&#x200B;**[!UICONTROL Edit]**&#x200B;以获取要更改其设置的属性加载器定义名称。
1. 在[!DNL Attribute Loader Edit]页面上，设置所需的选项。

   请参阅[添加属性加载器定义](../c-about-settings-menu/c-about-metadata-menu.md#task_A735E5EF763343A9B675E1A3B09AFDBC)下的选项表。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）在[!DNL Attribute Loader Definitions]页面上，单击&#x200B;**[!UICONTROL rebuild your staged site index]**。
1. （可选）在[!DNL Attribute Loader Definitions]页面上，执行以下任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;还原您所做的任何更改。

      请参阅[使用History选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送阶段设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 复制属性加载器定义 {#task_9B40D5ECFC81411E9480F62A0FD5F2E0}

您可以复制现有的属性加载器定义，以用作要创建的新属性加载器的基础。

>[!NOTE]
>
>要使用属性加载器，您可能需要由Adobe帐户代表或Adobe支持在您的帐户中启用它。

复制属性加载器定义时，默认情况下会禁用复制的定义。 要启用或“打开”定义，必须从[!DNL Attribute Loader Edit]页面对其进行编辑，然后选择&#x200B;**[!UICONTROL Enable]**。

请参阅[编辑属性加载器定义](../c-about-settings-menu/c-about-metadata-menu.md#task_AA2D1B2BCAFA44A6A0C59A0318274E80)。

**复制属性加载器定义**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**。
1. 在[!DNL Attribute Loader]页面的[!DNL Actions]列标题下，单击&#x200B;**[!UICONTROL Copy]** ，以获取要复制其设置的属性加载器定义名称。
1. 在[!DNL Attribute Loader Copy]页面上，输入定义的新名称。
1. 单击 **[!UICONTROL Copy]**.
1. （可选）在[!DNL Attribute Loader Definitions]页面上，执行以下任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;还原您所做的任何更改。

      请参阅[使用History选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送阶段设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 重命名属性加载器定义 {#task_58D5DFD7EBC04111BCB91118E4440DB4}

您可以更改现有属性加载器定义的名称。

>[!NOTE]
>
>要使用属性加载器，您可能需要由Adobe帐户代表或Adobe支持在您的帐户中启用它。

**重命名属性加载器定义**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**。
1. 在[!DNL Attribute Loader]页面的[!DNL Actions]列标题下，单击&#x200B;**[!UICONTROL Rename]**&#x200B;以获取要更改的属性加载器定义名称。
1. 在[!DNL Attribute Loader Rename]页面的[!DNL Name]字段中，输入定义的新名称。
1. 单击 **[!UICONTROL Rename]**.
1. （可选）在[!DNL Attribute Loader Definitions]页面上，执行以下任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;还原您所做的任何更改。

      请参阅[使用History选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送阶段设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 加载属性加载器数据 {#task_2F3C55189B0A4049AB2113F2291CC181}

您可以将配置的属性加载器数据下载到站点搜索/促销中。

[!DNL Data Load]页面显示有关上次属性加载器数据加载操作状态的以下信息：

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
   <td colname="col2"> <p>指示上次数据加载尝试的成功或失败。 或者，它会显示正在进行的数据加载操作的状态。 </p> </td> 
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

**加载属性加载器数据**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**。
1. 在[!DNL Attribute Loader Definitions]页面上，单击&#x200B;**[!UICONTROL Load Attribute Loader Data]**。
1. 在&#x200B;**[!UICONTROL Attribute Loader Data Load]**&#x200B;页面上，执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL Start Load]**&#x200B;以开始加载操作。

      在数据加载操作期间，**Progress**&#x200B;行会提供有关其进度的信息。

   * 单击&#x200B;**[!UICONTROL Stop Load]**&#x200B;以停止加载操作。

1. 单击&#x200B;**[!UICONTROL Close]**&#x200B;返回到[!DNL Attribute Loader Definitions]页面。

## 预览属性加载器数据 {#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0}

您可以使用“预览”查看最近加载的属性加载器数据。

表中的Row列显示每行数据的编号，指示属性加载器值加载的原始顺序。

其余列显示与每个条目关联的值。

如果表为空，则表示您尚未加载任何属性加载器数据。 您可以关闭[!DNL Attribute Loader Data Preview]页面，然后加载属性加载器数据。

请参阅[加载属性加载器数据](../c-about-settings-menu/c-about-metadata-menu.md#task_2F3C55189B0A4049AB2113F2291CC181)。

**预览属性加载器数据**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**。
1. 在[!DNL Attribute Loader Definitions]页面的[!DNL Actions]列下，单击&#x200B;**[!UICONTROL Preview]**&#x200B;以查看其下载数据的配置。
1. 在[!DNL Attribute Loader Data Preview]页面上，使用页面顶部和底部的导航和查看选项来查看数据。

   单击表中的任意列标题，以对数据进行升序或降序排序。
1. 执行以下任一操作：

   * 单击&#x200B;**[!UICONTROL Download to Desktop]**&#x200B;下载表并将其另存为.xlt文件。
   * 预览完属性加载器数据并返回到之前查看的页面时，关闭页面。

## 查看属性加载器定义的设置 {#task_EA99A9694FE948ADA82C1DBA0667851B}

您可以查看现有属性加载器定义的配置设置。

将属性加载器定义添加到[!DNL Attribute Loader Definitions]页面后，便无法更改其类型设置。 您而是必须删除定义，然后添加新定义。

>[!NOTE]
>
>要使用属性加载器，您可能需要由Adobe帐户代表或Adobe支持在您的帐户中启用它。

**查看属性加载器定义的设置**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**。
1. 在[!DNL Attribute Loader]页面的[!DNL Actions]列标题下，单击&#x200B;**[!UICONTROL Edit]**&#x200B;以获取要查看或编辑其设置的属性加载器定义名称。

## 从最近的属性加载器数据加载中查看日志 {#task_9C7D6E34BB6C4A40B7CA3EE36ACB0837}

可以使用[!DNL View Log]检查最近下载过程的属性加载器数据日志文件。 您还可以使用日志视图来监视正在运行的下载。

请参阅[加载属性加载器数据](../c-about-settings-menu/c-about-metadata-menu.md#task_2F3C55189B0A4049AB2113F2291CC181)。

**查看最近一次属性加载器数据加载中的日志**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**。
1. 在[!DNL Attribute Loader Definitions]页面上，单击&#x200B;**[!UICONTROL View Log]**。 日志页面、
1. 在[!DNL Attribute Loader Data Log]页面上，使用页面顶部和底部的导航和查看选项来查看日志信息。
1. 完成后，关闭页面以返回到[!DNL Attribute Loader Definitions]页面。

## 删除属性加载器定义 {#task_E8980F66888B476E98C228C1D307EDF8}

您可以删除不再需要或使用的现有属性加载器定义。

>[!NOTE]
>
>要使用属性加载器，您可能需要由Adobe帐户代表或Adobe支持在您的帐户中启用它。

**删除属性加载器定义**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**。
1. 在[!DNL Attribute Loader Definitions]页面的[!DNL Actions]列标题下，单击&#x200B;**[!UICONTROL Delete]**&#x200B;以获取要删除的属性加载器定义名称。
1. 在[!DNL Attribute Loader Delete]页面上，单击&#x200B;**[!UICONTROL Delete]**。
