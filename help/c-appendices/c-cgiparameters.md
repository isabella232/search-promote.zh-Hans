---
description: 'null'
seo-description: 'null'
seo-title: CGI参数
solution: Target
title: CGI参数
topic: Appendices,Site search and merchandising
uuid: a5f43547-bc15-44aa-ba23-6b8b573e09d2
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a

---


# CGI参数{#cgi-parameters}

## CGI参数 {#concept_F395999090FE4926B38BC73D5E612800}

## 搜索CGI参数 {#reference_DA27A8B0728246DA94994885E1353890}

提供了搜索表单代码，您可以将其复制并粘贴到站点的HTML中( **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**)。

请参 [阅将搜索表单的HTML代码复制到……](../c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

您还可以设置在搜索表单中或从脚本中列出的参数。 除了下面列出的参数之外，您还可以使用后端搜索参数来控制搜索。

请参阅 [后端搜索CGI参数](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。

搜索请求由基本URL组成。 基本URL指示客户正在搜索的帐户，以及一组CGI参数（键值对），这些参数指示如何为关联帐户返回所需的搜索结果。

基本URL与特定帐户以及分阶段或实时环境相关联。 您可以从客户经理处请求基本URL的多个别名。 例如，名为Megacorp的公司可能有两个基本URL与其帐户相关联： `https://search.megacorp.com` 和 `https://stage.megacorp.com`。 前者URL将搜索其实时索引，后者URL将搜索其分阶段索引。

支持三种格式的CGI参数。 默认情况下，您的帐户配置为使用分号分隔CGI参数，如下例所示：

`https://search.megacorp.com?q=shoes;page=2`

如果您愿意，您可以让客户经理将您的帐户配置为使用&amp;符来分隔CGI参数，如下例所示：

`https://search.megacorp.com?q=shoes&page=2`

还支持第三种格式（称为SEO格式），其中正斜杠代替分隔符， `/` 等号如以下示例所示：

`https://search.megacorp.com/q/shoes/page/2`

每当使用SEO格式发送请求时，所有输出链接都将以相同的格式返回。

| “向导式搜索”参数 | 示例 | 描述 |
|--- |--- |--- |
| q | `q=string` | 指定搜索的查询字符串。 此参数映射到后端 `sp_q` 搜索参数。  请参阅 [后端搜索CGI参数](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| q# | `q#=string` | 分面（在给定字段内搜索）是通过编号q和x参数完成的。  q参数定义您在facet中搜索的术语，由相应的编号x参数表示。<br>例如，如果您有两个彩块化，分别命名为大小和颜色，则可以有类似q1=small;x1=size;q2=red;x2=color的功能。  此参数映射到后端 `sp_q_exact_#` 搜索参数。  <br>请参阅 [后端搜索CGI参数](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| x 不支持跨域跟踪# | `q#=string` | 分面（在给定字段内搜索）是通过编号q和x参数完成的。  q参数定义您在facet中搜索的术语，由相应的编号x参数表示。 <br>例如，如果您有两个彩块化，分别命名为大小和颜色，则可以有类似q1=small;x1=size;q2=red;x2=color的功能。  此参数映射到后端 `sp_x_#` 搜索参数。  <br>请参阅 [后端搜索CGI参数](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| collection（集合） | `collection=string` | 指定用于搜索的集合。  此参数映射到后端 `sp_k` 搜索参数。  请参阅 [后端搜索CGI参数](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| count（计数） | `count=number` | 指定显示的结果总数。  默认值在 [!UICONTROL Settings ] > [!UICONTROL Searching ] >中定 [!UICONTROL Searches ]义。.  此参数映射到后端 `sp_c` 搜索参数。  请参阅 [后端搜索CGI参数](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| page | `page=number` | 指定返回的结果页。 |
| 秩 | `rank=field` | 指定用于静态排名的排名字段。  该字段必须是关联度大于0的“排名”类型字段。  此参数映射到后端 `sp_sr` 参数。  请参阅 [后端搜索CGI参数](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| 排序 | `sort=number` | 指定排序顺序。<br>“0”是默认值，并按相关性得分排序；“1”按日期排序；“-1”不排序。  用户可以指定参数值的字段名 `sp_s` 称。  例如， `sp_s=title` 根据标题字段中包含的值对结果进行排序。 当字段名称用于参数的值时，结果将按该字 ` sp_s ` 段排序，然后按相关性进行子排序。  To enable this feature, click [!UICONTROL Settings ] > [!UICONTROL Metadata ] > [!UICONTROL Definitions ]. 在“定义”页面上，单 [!UICONTROL Add New Field ] 击或单 [!UICONTROL Edit ] 击特定字段名称。 在下 [!UICONTROL Sorting ] 拉列表中，选择或 [!UICONTROL Ascending ] 选 [!UICONTROL Descending ]项。 此参数映射到后端 `sp_s` 搜索参数。 <br>请参阅 [后端搜索CGI参数]。(../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |

## 后端搜索CGI参数 {#reference_582E85C3886740C98FE88CA9DF7918E8}

通常，客户会与称为“向导式搜索”的表示层交互。 但是，理论上可以跳过“向导式搜索”层，并直接使用本页所述的CGI参数与后端核心搜索交互。

您可以从下表中选择后端搜索CGI参数：
<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>单查询支持 </p> </th> 
   <th colname="col03" class="entry"> <p>多查询支持 </p> </th> 
   <th colname="col3" class="entry"> <p>示例 </p> </th> 
   <th colname="col4" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>sp_a </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_a=字符串 </span> </p> </td> 
   <td colname="col4"> <p>指定帐号字符串。 此参数为必需参数，且必须是有效的帐号字符串。 您可以在“设置”&gt;“帐户选项” <span class="uicontrol"> &gt;“帐户设 </span> 置”下查 <span class="uicontrol"> 找您的帐 </span> 户号 <span class="uicontrol"> 码字符串 </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>sp_advanced </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_advanced= 0或1 </span> </p> </td> 
   <td colname="col4"> <p>如果 <span class="codeph"> sp_advanced=1随查询一起提交，则搜索模板中 </span> &lt;search-if-advanced&gt;标签和 <span class="codeph"></span><span class="codeph"></span> &lt;/search-if-advanced&gt;标签之间的所有代码都将用于搜索表单。 将忽略 <span class="codeph"> &lt;search-if-not-advanced&gt;标记和 </span> &lt;/search-if-not-advanced&gt;标 <span class="codeph"> 记之间的所有代码 </span> 。 如果 <span class="codeph"> sp_advanced=0 </span> （或任何其他值）已提交，则忽略&lt;search-if-advanced&gt;模板块，并使用&lt;search-if-not-advanced&gt;模板块。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>sp_c </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_c=数字 </span> </p> </td> 
   <td colname="col4"> <p>指定要显示的结果总数。 默认值为 10。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>sp_context_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_context_field= <i>field</i> </code> </p> </td> 
   <td colname="col4"> <p>收集给定字段的上下文信息。 通过&lt;search-context&gt;模板标记将收集的信息输出 <span class="codeph"> 到搜索结果 </span> 中。 The default value is <span class="codeph"> body </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>sp_d </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_d=类型 </span> </p> </td> 
   <td colname="col4"> <p>指定要执行的日期范围搜索的类型。 可能类型为任何，即不执行日期范围搜索，自定义，指示 <span class="codeph"> sp_date_的值确定搜索日期，具体指 </span> sp <span class="codeph"> _start_day、 </span>sp_start_month、 <span class="codeph"> sp_start_month、 </span>sp_start_sert_yer、 <span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span> sp_end.sp_end用于确定要搜索的日期范围。 <span class="codeph"> 只有在 </span> 您的搜索表单包含按自定义范围(通过 <span class="codeph"> sp_date_range)或特定开始和结束日期范围进行搜索的选项时，才需要sp_d </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_d_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_d_#=类型 </span> </p> </td> 
   <td colname="col4"> <p>指定要对相应的sp_q_#查询执行的日 <span class="codeph"> 期范围搜索的类 </span> 型。 将“#”替换为介于1到16之间的数字(例如， <span class="codeph"> sp_d_8 </span>，应用于编号的 <span class="codeph"> 查询sp_q_8 </span>)。 </p> <p>可以设 <span class="codeph"> 置类型，即不执行日期范围搜索，自定义，指示 </span> sp_date_ <span class="codeph"> #的值确定要搜索的日期，具体指示sp_q_date_ </span> #的值表示sp_q_date_day_ <span class="codeph"> day_min_min,sp_ </span>q_min_min_sp_q,sp_ <span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span> q_#应当使用max_month_q#和max_year_q#确定日期范围。 仅当您的搜索表单包含按自定义范围(通过 <span class="codeph"> sp_date_range_#)或特定开始日期和结束日期范围进行搜索的选项时，才需要使用 </span><span class="codeph"></span>sp_d_#。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>sp_date_range </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_date_range= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>指定要应用于搜索的预定义日期范围。 大于或等于零的值指定今天之前要搜索的天数— 例如，值“0”指定“今天”，值“1”指定“今天和昨天”，值“30”指定“过去30天内”，依此类推。 </p> <p>低于零的值指定自定义范围，如下所示： </p> <p>-1 = "None"，与指定无日期范围相同。 </p> <p>-2 = “本周”，从周日到周六搜索。 </p> <p>-3 = "Last week"，搜索时间从当周前一周的星期日到星期六。 </p> <p>-4 = "本月"，搜索日期为当月。 </p> <p>-5 = "上个月"，搜索日期在当前月份前一个月内。 </p> <p>-6 =“今年”，其搜索日期为当年。 </p> <p>-7 = “去年”，其搜索日期在当前年度之前的一年。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_date_range_# </p> </td> 
   <td colname="col3"> <p> <code> sp_date_range_#= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>指定要应用于相应sp_q_#查询的预 <span class="codeph"> 定义日期范 </span> 围。 将“#”替换为介于1到16之间的数字(例如， <span class="codeph"> sp_date_range_8 </span>，应用于编号的 <span class="codeph"> 查询sp_q_8 </span>)。 </p> <p>大于或等于零的值指定今天之前要搜索的天数。 例如，值0指定今天；值为1表示今天和昨天；值30指定在最近30天内，依此类推。 </p> <p>低于零的值指定自定义范围，如下所示： </p> <p>-1 = "None"，与指定无日期范围相同。 </p> <p>-2 = “本周”，从周日到周六搜索。 </p> <p>-3 = "Last week"，搜索时间从当周前一周的星期日到星期六。 </p> <p>-4 = "本月"，搜索日期为当月。 </p> <p>-5 = "上个月"，搜索日期在当前月份前一个月内。 </p> <p>-6 =“今年”，其搜索日期为当年。 </p> <p>-7 = “去年”，其搜索日期在当前年度之前的一年。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>9 </p> </td> 
   <td colname="col2"> <p>sp_dedupe_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_dedupe_field= <i>fieldname</i> </code> </p> </td> 
   <td colname="col4"> <p>指定单个字段以在上消除重复项搜索结果。 该字段上的所有重复结果都将从搜索结果中删除。 例如，如果 <span class="codeph"></span>sp_dedupe_field=title，则搜索结果中只显示给定标题的顶部结果（没有两个结果将具有相同的标题字段内容）。 对于多值（允许列表）类型字段，整个字段内容用于比较。 只能指定一个字段。 字段名称中不允许使用“表限定符”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>10 </p> </td> 
   <td colname="col2"> <p>sp_e </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_e=数字 </span> </p> </td> 
   <td colname="col4"> <p>指定对于查询字符串中具有多于数字字符的任何单词，应进行自动通配符扩展。 换句话说， <span class="codeph"></span> sp_e=5指定具有5个或更多字符的单词（如“query”或“number”）应使用通配符“*”展开，使搜索与搜索“query*”或“number*”等效。 字符数较少的单词不会展开，因此搜索“单词”不会自动进行通配符扩展。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>11 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_e_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_e_#=数字 </span> </p> </td> 
   <td colname="col4"> <p>指定对于来自具有多个数字字符的相应 <span class="codeph"> sp_q_#查询字符串的任何单词 </span> ，将自动进行通配符扩展。 换句话说， <span class="codeph"> sp_e_2=5指定 </span> sp_q_2查询字符串中包含五个或多个字符的单词（如“query”或“number”）应使用通配符“ <span class="codeph"> * </span><span class="codeph"></span>”展开，使搜索等同于搜索“query*”或“number*”。 字符数较少的单词不会展开，因此在 <span class="codeph"> sp_q_2中搜索“word”时 </span> 不会自动扩展通配符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>12 </p> </td> 
   <td colname="col2"> <p>sp_end_day、sp_end_month、sp_end_year </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_end_day= <i>number</i>,sp_end_month= <i>number</i>, sp_end_year= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>这三个值指定了搜索的结束日期范围，并且必须作为一组提供。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>13 </p> </td> 
   <td colname="col2"> <p>sp_f </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_f=字符串 </span> </p> </td> 
   <td colname="col4"> <p>指定查询参数字符串的字符集(如 <span class="codeph"> sp_q </span>)。 此字符串必须始终与包含搜索表单的页面的字符集匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>14 </p> </td> 
   <td colname="col2"> <p>sp_field_table </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_field_ table=table: field,field... </code> </p> </td> 
   <td colname="col4"> <p>定义由给定字段组成的逻辑数据表。 例如，由“color”、“size”和“price”字段组成的名为“items”的表定义如下： </p> <p> <span class="codeph"> sp_field_table=items:color,size,price </span> </p> <p>逻辑表与选中“允许列表”的字段(在“设置”&gt;“元数据” <span class="uicontrol"> &gt;“定义”下 </span> )一起 <span class="uicontrol"> 最 </span> 有用 <span class="uicontrol"> 的方式是 </span>“允许列表”。 所有以字段名称为值的CGI参数和模板标记都可以选择指定表名，后跟“.” 在字段名称之前(例如， <span class="codeph"> sp_x_1=tablename.fieldname </span>)。 </p> <p>例如，要搜索包含大小为“large”（其中项目表示为并行元数据行）的一个或多个“红色”项目的文档，可以使用以下内容： </p> <p> <code> sp_q_exact_1=red&amp;sp_x_1=items.color&amp; sp_q_exact_2=large&amp;sp_x_2=items.size&amp;sp_field_table=items:color,size,price </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>15 </p> </td> 
   <td colname="col2"> sp_i </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_i= <span class="varname"> value </span></span> </p> </td> 
   <td colname="col4"> <p>在生成报告时忽略搜索。 </p> <p>使用此查询可以遮住某些后端搜索，如“您的意思”生成的搜索，或管理员在成员中心生成的搜索。 由于最终用户不生成这些类型的搜索，因此它们不会显示在各种Adobe Search&amp;Promote报告中。 </p> <p>有效值 <span class="codeph"> 为sp_i=1 </span> 和 <span class="codeph"> sp_i=2 </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>16 </p> </td> 
   <td colname="col2"> <p>sp_k </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_k=字符串 </span> </p> </td> 
   <td colname="col4"> <p> 指定用于搜索的集合。 默认值为no collection，这意味着搜索应包括整个站点。 </p> <p>请参 <a href="../c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3" type="reference" format="dita" scope="local"> 阅在搜索表单中使用集合 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>17 </p> </td> 
   <td colname="col2"> <p>sp_l </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_l=字符串 </span> </p> </td> 
   <td colname="col4"> <p>指定查询参数字符串的语言(如 <span class="codeph"> sp_q </span>)。 字 <i> 符串 <span class="codeph"></span></i> 应该是标准区域设置ID，其中包含ISO-639语言代码（可选），后跟ISO-3166国家／地区代码。 例如，英语为“en”或“en_US”，日语为“ja”或“ja_JP”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>18 </p> </td> 
   <td colname="col2"> <p>sp_literal </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_literal= 0或1 </span> </p> </td> 
   <td colname="col4"> <p> 设置 <span class="codeph"> sp_literal=1可临 </span> 时禁用可能解释查询中单词的所有功能。 使用此参数时，只有查询的字面单词匹配文档，而不考虑同义词、替代单词表单和类似声音匹配。 </p> <p>请注意， <span class="codeph"> sp_literal=0没 </span> 有含义，如果使用，则忽略它。 </p> <p>请参 <a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" type="concept" format="dita" scope="local"> 阅关于字典 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>19 </p> </td> 
   <td colname="col2"> <p>sp_m </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_m=数字 </span> </p> </td> 
   <td colname="col4"> <p> 指定是否显示摘要。 1表示是，0表示否。 默认值为 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>20 </p> </td> 
   <td colname="col2"> <p>sp_n </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_n=数字 </span> </p> </td> 
   <td colname="col4"> <p> 指定开始搜索结果的结果数。 默认值为 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>21 </p> </td> 
   <td colname="col2"> <p>sp_not_found_page </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_not_found_page= url </span> </p> </td> 
   <td colname="col4"> <p> 指定如果没有搜索结果，是否重定向到指定的URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>22 </p> </td> 
   <td colname="col2"> <p>sp_p </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_p= any/all/phrase </span> </p> </td> 
   <td colname="col4"> <p> 指定要执行的默认搜索类型。 使用任何 <span class="codeph"> 指 </span> 从查询字符串中搜索包含任何单词的文档。 使用全 <span class="codeph"> 部表 </span> 示搜索包含查询字符串中所有单词的文档。 短语的使 <span class="codeph"> 用意 </span> 味着查询字符串被视为引用的短语，并且忽略所有用户类型的引号。 </p> <p>对于 <span class="codeph"> 短 </span> 语和 <span class="codeph"></span>所有词，搜索词前的“+”和“-”规范被禁用，这些字符会被忽略。 如 <span class="codeph"> 果sp_p不存在，或 </span> 者设置为空字符串或任何字符串，则允许使用标准“+”和“-”字前缀。 </p> <p>有关在搜索中使用加号(“+”)和减号(“-”)的更多信息，请参阅搜索提示说明。 </p> <p>请参阅<a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local">关于搜索</a>。 </p> <p>有关使用sp_p参数的示例，请参阅示例高级 <span class="codeph"> 搜索表 </span> 单。 </p> <p>请参 <a href="../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A" type="reference" format="dita" scope="local"> 阅示例高级搜索表 </a>单。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>23 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_p_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_p_#= any/all/phrase </span> </p> </td> 
   <td colname="col4"> <p>指定要使用相应的sp_q_#查询执行的 <span class="codeph"> 默认搜索类型 </span> 。 将“#”替换为介于1到16之间的数字(例如， <span class="codeph"> sp_p_8应 </span> 用于编号的查询 <span class="codeph"> sp_q_8 </span>)。 使用任何 <span class="codeph"> 表示 </span> 返回包含查询字符串中任意单词的文档。 使用全 <span class="codeph"> 部表 </span> 示返回包含查询字符串中所有单词的文档。 短语的使 <span class="codeph"> 用意 </span> 味着将查询字符串视为完整短语（并忽略所有用户类型的引号）。 </p> <p>如果指定全部或 <span class="codeph"> 短语， </span> 则 <span class="codeph"> 将忽略搜索词 </span>前的任何加号和减号。 如 <span class="codeph"> 果忽略sp_p_# </span> ，或将其设置为空字符串或任何 <span class="codeph"> , </span>则允许使用标准“+”和“-”前缀。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>24 </p> </td> 
   <td colname="col2"> <p>sp_pt </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_pt= <i>exact/equivalent/compatible</i> </code> </p> </td> 
   <td colname="col4"> <p> 指定要应用的目标匹配类型。 使用精确 <span class="codeph"> 表示仅 </span> 在与目标内容中的查询字符串完全匹配的文档中生成目标匹配项。 使用等 <span class="codeph"> 效项 </span> 与精确相同，只是词的顺序不重要。 使用兼容 <span class="codeph"> 性会 </span> 根据sp_p参数的值自动设置目标匹配 <span class="codeph"> 类 </span> 型。 如果所有短语(sp_p)或其他的短语(sp_ <span class="codeph"> p)都使用，则使用， </span> 或者使用其他的同 <span class="codeph"> 等的短 </span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span> 语(sp_p)。 sp_pt的默 <span class="codeph"> 认值是兼 </span> 容 <span class="codeph"> 的 </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>25 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_pt_# </p> </td> 
   <td colname="col3"> <p> <code> sp_pt_#= <i>exact/equivalent/compatible</i> </code> </p> </td> 
   <td colname="col4"> <p>指定要与相应的sp_q_#查询一起应用的目标 <span class="codeph"> 匹配类型 </span> 。 将“#”替换为介于1到16之间的数字(例如， <span class="codeph"> sp_p_8应 </span> 用于编号的查询 <span class="codeph"> sp_q_8 </span>)。 使用精确 <span class="codeph"> 表示仅 </span> 在与目标内容中的查询字符串完全匹配的文档中生成目标匹配项。 使用等 <span class="codeph"> 效项 </span> 与使 <span class="codeph"> 用精确 </span>一样，只是单词的顺序并不重要。 使用兼容 <span class="codeph"> 性时， </span> 会根据相应sp_p_#参数的值自动设置目标 <span class="codeph"> 匹配类型 </span> :如 <span class="codeph"> 果sp_p_# </span> 是全部或短语，则使用精确值 <span class="codeph"> ，否则 </span> 使用等 <span class="codeph"></span> 效值。 sp_pt_#的 <span class="codeph"> 默认值是兼容 </span> 的 <span class="codeph"></span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>26 </p> </td> 
   <td colname="col2"> <p>sp_q </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q=字符串 </span> </p> </td> 
   <td colname="col4"> <p> 指定搜索的查询字符串。 空字符串导致不显示任何结果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>27 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_q_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_#=文本 </span> </p> </td> 
   <td colname="col4"> <p>此参数允许在搜索表单上创建多个查询。 sp_ <span class="codeph"> q_#参数包含 </span> 要在给定编号查询中使用的查询字符串。 搜索请求最多可引用16个不同的编号查询( <span class="codeph"> sp_q_1 </span> 到 <span class="codeph"> sp_q_16 </span>)。 </p> <p>例如，提交以下表单将返回包含“great”和“books”字样的所有文档。 </p> <p> <code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="books"&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>28 </p> </td> 
   <td colname="col2"> <p>sp_q_day、sp_q_month、sp_q_year </p> </td> 
   <td colname="col03"> <p> sp_q _day_#, sp_q _month_#, sp_q _year_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_day=整数值 </span> </p> <p> <span class="codeph"> sp_q_month=整数值 </span> </p> <p> <span class="codeph"> sp_q_year=整数值 </span> </p> <p> <span class="codeph"> sp_q_day_#=整数值 </span> </p> <p> <span class="codeph"> sp_q_month_#=整数值 </span> </p> <p> <span class="codeph"> sp_q_year_#=整数值 </span> </p> </td> 
   <td colname="col4"> <p>这些参数用于指定特定查询的确切日期。 sp_q_day <span class="codeph"> 、 </span>sp_q_month <span class="codeph"> 和 </span>sp_q_year参数应用于主查询( <span class="codeph"></span><span class="codeph"></span>sp_q)。 </p> <p>#参 <span class="codeph"> 数 </span>被替换为介于1到16之间的数字(例如， <span class="codeph"> sp_q_day_6 </span>，它适用于编号的查询sp_q_6 <span class="codeph"></span>)。 默认情况下，所有日期都会相对于格林威治标准时间进行搜索。 </p> <p>下面的代码部分允许用户在标有“Jan”的文档中搜索“orange”一词。 2000年10月1日”，位于用户定义的名为 <span class="codeph"> PublishDate的字段中 </span>: </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt; Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;On&nbsp;:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Month &lt;input&nbsp;type="text"&nbsp;name="sp_q_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Year&nbsp; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>29 </p> </td> 
   <td colname="col2"> <p>sp_q_location </p> </td> 
   <td colname="col03"> <p>sp_q_location_# </p> </td> 
   <td colname="col3"> <p> <code> sp_q_location=<i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code> </p> <p> <code> sp_q_location_#= <i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code> </p> </td> 
   <td colname="col4"> <p>这些参数将位置与主查询或编号查询相关联。 使用 <span class="codeph"> sp_q_location会影响主查询 </span> sp_q_location_# <span class="codeph"> (其中 </span><span class="codeph"></span> #将替换为1到16之间的数字)，从而影响给定的编号查询。 这些参数用于针对为每个站点页面索引的位置数据执行最小和／或最大距离接近度搜索。 值的格式决定其解释。 </p> <p>DDD（三位数字）形式的值被解释为美国电话区号；DDDDDD或DDDDD-DDDD形式的值解释为美国的zipcode;DDDDD表示为经纬度对。 每个值都需要符号。 例如，+38.6317+120.5509指定纬度38.6317，经度120.5509。 </p> <p>请参 <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> 阅关于邻近搜索 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>30 </p> </td> 
   <td colname="col2"> <p>sp_q_max_relevent_distance </p> </td> 
   <td colname="col03"> <p>sp_q_max_relevant _distance _# </p> </td> 
   <td colname="col3"> <p> <code> sp_q_max_relevant_distance= <i>value</i> </code> </p> <p> <code> sp_q_max_relevant_distance_#= <i>value</i> </code> </p> </td> 
   <td colname="col4"> <p>这些参数控制应用于邻近搜索的相关计算。 使用 <span class="codeph"> sp_q_max_relevant_distance </span> 会影响主查询 <span class="codeph"> sp_q_max_relevant_distance_# </span> (其中 <span class="codeph"></span> #由1到16的数字替换)，这会影响给定的编号查询。 </p> <p>sp_q_max_ <span class="codeph"> relevant_distance的默认值 </span> 为100。 </p> <p>邻近组件的完美相关得分表示距离为0。 邻近组件的最低相关得分表示刚好超过指定 <span class="codeph"> sp_q_max_relevant_distance_#值的距离 </span> 。 </p> <p>请参 <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> 阅关于邻近搜索 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>31 </p> </td> 
   <td colname="col2"> <p>sp_q_min_day, sp_q_min_month, sp_q_min_year </p> <p>sp_q_max_day, sp_q_max_month, sp_q_max_year </p> </td> 
   <td colname="col03"> <p>sp_q_min_day_#、sp_q_min_month_#、sp_q_min_year_# </p> <p> sp_q_max_day_#、sp_q_max_month_#、sp_q_max_year_# </p> </td> 
   <td colname="col3"> <p> <code> sp_q_min_day=<i>integer value</i> </code> </p> <p> <code> sp_q_min_month=<i>integer value</i> </code> </p> <p> <code> sp_q_min_year=<i>integer value</i> </code> </p> <p> <code> sp_q_max_day=<i>integer value</i> </code> </p> <p> <code> sp_q_max_month=<i>integer value</i> </code> </p> <p> <code> sp_q_max_year=<i>integer value</i> </code> </p> <p> <code> sp_q_min_day_#=<i>integer value</i> </code> </p> <p> <code> sp_q_min_month_#=<i>integer value</i> </code> </p> <p> <code> sp_q_min_year_#=<i>integer value</i> </code> </p> <p> <code> sp_q_max_day_#=<i>integer value</i> </code> </p> <p> <code> sp_q_max_month_#=<i>integer value</i> </code> </p> <p> <code> sp_q_max_year_#=<i>integer value</i> </code> </p> </td> 
   <td colname="col4"> <p>这些参数用于为特定查询设置最小和最大日期范围。 sp_ <span class="codeph"> min_day </span>、 <span class="codeph"> sp_q_min_month、sp_q_min_year、 </span>sp_q_min_year、 <span class="codeph"> sp_day、sp_min_sp_year、 </span><span class="codeph"></span><span class="codeph"></span><i></i><span class="codeph"></span>sp_max_year和sp_max_q将参数应用于主查询(sp_q)max_q(max_max)。 </p> <p>参数 <span class="codeph"> 名 </span>称中的#将替换为介于1到16之间的数字(例如， <span class="codeph"> sp_q_min_day_6应 </span> 用于编号的查询 <span class="codeph"> sp_q_6 </span>)。 </p> <p>只指定最小日期、最大日期或同时指定最小和最大日期是合法的。 但是，对于给定的最小值或最大值设置，必须指定所有三个日期参数（日、月和年）。 默认情况下，所有日期都会相对于格林威治标准时间进行搜索。 </p> <p>下面的代码部分允许用户在名为 <span class="codeph"> PublishDate的用户定义字段中搜索日期介于2000年1月1日至2000年12月31日之间的文档中的“橙色”一词 </span>: </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;Between:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_min_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Start&nbsp;Year 
      And:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_max_day_1"&nbsp;size="2"&nbsp;value="31"&gt;&nbsp;End&nbsp;Day 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_month_1"&nbsp;size="2"&nbsp;value="12"&gt;&nbsp;End&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;End&nbsp;Year </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>32 </p> </td> 
   <td colname="col2"> <p>sp_q_min, sp_q_max </p> </td> 
   <td colname="col03"> <p>sp_q _min_#, sp_q _max_#, sp_q _exact_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_min=值 </span> </p> <p> <span class="codeph"> sp_q_max=值 </span> </p> <p> <span class="codeph"> sp_q_min_#=值 </span> </p> <p> <span class="codeph"> sp_q_max_#=值 </span> </p> <p> <span class="codeph"> sp_q_exact_#=value </span> </p> </td> 
   <td colname="col4"> <p>这些参数指定要应用于主查询或编号查询的最小值（和／或最大值）。 使用 <span class="codeph"> sp_q_min、sp </span><span class="codeph"> _q_max和 </span>sp_q_exact <span class="codeph"> 会影响主查询( </span><span class="codeph"></span>sp_q)。 </p> <p>将参 <span class="codeph"> 数名 </span>中的#替换为介于1到16之间的数字(例如， <span class="codeph"> sp_q_min_8应 </span> 用于编号的查询 <span class="codeph"> sp_q_8 </span>)。 </p> <p>使用 <span class="codeph"> sp_q_exact_#是指定 </span> sp_q_min_#和 <span class="codeph"> sp_q_max_#的速记，其值相同 </span><span class="codeph"></span> 。 如 <span class="codeph"> 果指定了sp_q_exact_# </span> ，则忽略任何相应的 <span class="codeph"> sp_q_min_# </span> 或 <span class="codeph"> sp_q_max_#参 </span> 数。 </p> <p>sp_q_ <span class="codeph"> min_#、sp_q_max_# </span>和 <span class="codeph"></span><span class="codeph"></span> sp_q_exact_#参数可以选择指定多个“|”分隔的值。 例如，要搜索在“颜色”字段中包含绿色或红色值的文档，请执行以下操作： <span class="codeph"> ...&amp;sp_q_exact_1=green|red&amp;sp_x_1=color </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>33 </p> </td> 
   <td colname="col2"> <p>sp_q_nocp </p> </td> 
   <td colname="col03"> <p>sp_q _nocp _# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_nocp= 1或0 </span> </p> <p> <span class="codeph"> sp_q_nocp_#= 1或0 </span> </p> </td> 
   <td colname="col4"> <p>默认参数值为 <span class="codeph"> 0，表 </span> 示执行“公用短语”展开。 </p> <p>对于相应的搜 <span class="codeph"> 索查 </span> 询，当设置为1时，不执行“常用短语”展开。 </p> <p>使 <span class="codeph"> 用sp_q_nocp会 </span> 影响主搜索查询 <span class="codeph"> 参数sp_q </span>。 要将此参数应用于编号搜索查询，请将参 <span class="codeph"> 数名 </span> 中的#替换为相应的编号。 例如， <span class="codeph"> sp_q_nocp_8应 </span> 用于编号的搜索查 <span class="codeph"> 询sp_q_8 </span>。 </p> <p> 
     <!--See also <xref href="c_about_common_phrases.xml#concept_4946E53586DF492EAEB1B7F757FD440F" format="dita" scope="local">About Common Phrases</xref>--> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>34 </p> </td> 
   <td colname="col2"> <p>sp_q_required </p> </td> 
   <td colname="col03"> <p>sp_q_required_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_required= 1或0或-1 </span> </p> <p> <span class="codeph"> sp_q_required_#= 1或0或-1 </span> </p> </td> 
   <td colname="col4"> <p>此参数确定匹配是否必须(1)、(0)或不得(-1)出现在相应的查询中，以便在结果页上返回文档。 </p> <p>使用 <span class="codeph"> sp_q_required会 </span> 影响主查询( <span class="codeph"> sp_q </span>)。 </p> <p>要应用于已编号的查询，请将参数名称中的 <span class="codeph"> #替换为相应的编号(例如， </span> sp_q_required_8 <span class="codeph"> 应用于已编号的查询 </span> sp_q_8 <span class="codeph"></span>)。 参数的默认值是1（必须匹配）。 </p> <p>要在用户定义的“平台”字段中搜索包含单词“calc”但不包含“mac”、“win”或“all”的文档，您的HTML搜索表单可能包含以下行： </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="platform"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="calc"&gt; 
      Exclude:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="mac&nbsp;win&nbsp;all"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_q_required_1"&nbsp;value="-1"&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>35 </p> </td> 
   <td colname="col2"> <p>sp_redirect_if_one_result </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_redirect_ 
      if_one_result= <i>0 or 1</i> </code> </p> </td> 
   <td colname="col4"> <p>指定在仅有一个搜索结果时是否重定向到搜索结果URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>36 </p> </td> 
   <td colname="col2"> <p>sp_referrer </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_referrer= url </span> </p> </td> 
   <td colname="col4"> <p>指定搜索的引用URL。 对于搜索重写规则很有用，因为搜索结果链接回与搜索表单相同的站点。 </p> <p>默认值是浏览器提供的标准CGI HTTP_REFERRER值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>37 </p> </td> 
   <td colname="col2"> <p>sp_ro </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_ro=字 <span class="varname"> 段 </span>: <span class="varname"> 相关性 </span></span> </p> </td> 
   <td colname="col4"> <p>允许可选的搜索时间、每个字段名称、相关性控制。 参 <span class="codeph"> 数名 </span> 称中的ro表示“相关覆盖”。 该参数接受一个或多个字段名称，后跟冒号字符，后跟从0-10的相关值。 </p> <p>例如，要将字段名称“body”的相关值设置为10，当客户执行搜索时，该参数将显示如下： </p> <p> <span class="codeph"> sp_ro=body:10 </span> </p> <p>或者，要在参数字符串中指定多个字段相关性覆盖，您可以使用管道分隔符。 例如，要将字段名称“body”和“title”的相关值设置为9，客户执行搜索时，该参数将显示如下： </p> <p> <span class="codeph"> sp_ro=body:9|title:9 </span> </p> <p> <p>注意： 指定关联搜索中未涉及的字段不起作用。 例如，如果设置 <span class="codeph"> sp_ro=title:10 </span>，但未搜索标题字段名称，则 <span class="codeph"> sp_ro参数 </span><span class="codeph"></span> 将不起作用。 换句话说，使用sp_ro参数指定字段名 <span class="codeph"> 称不会自 </span> 动搜索该字段；相反，它只会覆盖该字段的相关设置。 </p> </p> <p>请参 <a href="../c-about-settings-menu/c-about-metadata-menu.md#task_0A7657B63596421BB6DB3ED44F827AB3" type="task" format="dita" scope="local"> 阅编辑预定义或用户定义的元标记字段 </a>。 </p> <p>请参 <a href="../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C" type="concept" format="dita" scope="local"> 阅关于查询清除规 </a>则。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>38 </p> </td> 
   <td colname="col2"> <p>sp_s </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_s=数字 </span> </p> </td> 
   <td colname="col4"> <p>指定排序顺序。 Zero(0)是默认值，它是按相关分数排序的方法。 一(1)表示按日期排序，-1表示不排序。 </p> <p>可以为sp_s参数的值指定 <span class="codeph"> 字段名 </span> 称。 例如， <span class="codeph"> sp_s=title </span> 会根据标题字段中包含的值对结果进行排序。 当字段名称用于 <span class="codeph"> sp_s参数的值时， </span> 结果将按该字段排序，然后按相关性子排序。 </p> <p>将引用字段的排序设置为启用此功 <span class="uicontrol"> 能的元数据的 </span><span class="uicontrol"></span><span class="uicontrol"></span><span class="uicontrol"></span><span class="uicontrol"></span> 升序&gt;元数据定义的“设置”&gt;“设置”中的“排序”或“降序”。 </p> <p>您还可以通过在搜索表单中多次设置 <span class="codeph"> sp_s参数，将多个排序字 </span> 段分配给单个查询。 以下模板行设置要先按艺术家姓名、专辑名称和音轨名称排序的搜索结果。 </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="artist"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="album"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="track"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Music&nbsp;Search"&gt; </code> </p> <p>还可以通过在字段名称之前指定表名限定符（例如items.price），对表匹配的字段数据进行排序。 有关表匹 <span class="codeph"> 配的详细信息，请参 </span> 阅sp_field_table参数。 </p> <p>如果按邻近度搜索，则可以通过指定“邻近输出字段”，根据邻近度对结果排序。 </p> <p>请参 <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> 阅关于邻近搜索 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>39 </p> </td> 
   <td colname="col2"> <p>sp_sr </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_sr=字段 </span> </p> </td> 
   <td colname="col4"> <p>指定用于静态排名的排名字段。 该字段必须是关联度大于0的“排名”类型字段。 如果没 <span class="codeph"> 有为查 </span> 询提供sp_sr参数，则会自动选择“排名”类型字段。 </p> <p>要禁用特定查询的静态排名，请为 <span class="codeph"> sp_sr包含一个NULL值 </span> (例如， <span class="codeph"> &lt;input type="hidden" name="sp_sr" value=""&gt; </span>)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>40 </p> </td> 
   <td colname="col2"> <p>sp_sfvl_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_sfvl_field=字符串 </span> </p> </td> 
   <td colname="col4"> <p>指定要与搜索模板中的 <span class="codeph"> &lt;search-field-value-list&gt;标签一起使用的字 </span> 段的名称。 </p> <p>可指定多个 <span class="codeph"> sp_sfvl_field参 </span> 数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>41 </p> </td> 
   <td colname="col2"> <p> sp_sfvl_df_count </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_sfvl_df_count= <span class="varname"> &lt;integer_value&gt; </span></span> </p> </td> 
   <td colname="col4"> <p> 
     <!--NEW 2/2/2014-->请求此搜 <span class="codeph"> 索最多 <span class="varname"> 为&lt;integer_value&gt; </span> search-field-value-list动 </span><span class="codeph"></span> 态彩块化字段。 </p> <p>默认值为 0。允许的最大值是为给定索引定义的动态彩块化字段的当前数量，即动态彩块化字段计数。 小于0的整数值被视为0。 在dynamic-facet-field- <span class="codeph"> count之上指定的整 </span> 数值被 <span class="codeph"> dynamic-facet-field-count所限制 </span>。 忽略非整数值；它们被视为默认值。 </p> <p>给定片段的搜索会以该片段的动态彩块化字段计数值的最大允许 <span class="codeph"> sp_sfvl_df_count </span> 值 <span class="codeph"> 作为上限 </span> 值。 在合并切片结果时， <span class="codeph"> sp_sfvl_df_count的有效最大值 </span> ，是所有切片上的 <span class="codeph"> 最大实际sp_sfvl_df_ </span> count。 </p> <p>请参阅 <a href="../c-about-design-menu/c-about-dynamic-facets.md#task_D17F484130E448258100BAC1EEC53F39" format="dita" scope="local"> 配置动态彩块化 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>42 </p> </td> 
   <td colname="col2"> <p> sp_sfvl_df_exclude </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> <span class="codeph"> sp_sfvl_df_exclude= &lt; <span class="varname"> field_name </span>&gt;[|&lt; <span class="varname"> field_name </span></span>&gt;|... </p> </td> 
   <td colname="col4"> <p> 指定要从此搜索考虑中排除的特定动态彩块字段列表。 </p> <p>默认情况下，会考虑所有动态Facet字段。 </p> <p>请参阅 <a href="../c-about-design-menu/c-about-dynamic-facets.md#task_D17F484130E448258100BAC1EEC53F39" format="dita" scope="local"> 配置动态彩块化 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>43 </p> </td> 
   <td colname="col2"> <p> sp_sfvl_df_include </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> <span class="codeph"> sp_sfvl_df_include= &lt; <span class="varname"> field_name </span>&gt;[|&lt; <span class="varname"> field_name </span></span>&gt;|... </p> </td> 
   <td colname="col4"> <p> 指定要包含在搜索结果中的特定动态彩块化字段列表。 </p> <p> <p>注意： sp_ <span class="codeph"> sfvl_df_count参数确定要返回的动态彩块字段的总数，包括通过 </span> sp_sfvl_df_include指定的任何字段 <span class="codeph"></span>。 即，使用 <span class="codeph"> sp_sfvl_df_include不允许返回的动态彩块化字段的总数超过 </span> sp_sfvl_df_count <span class="codeph"></span>。 </p> </p> <p>请参阅 <a href="../c-about-design-menu/c-about-dynamic-facets.md#task_D17F484130E448258100BAC1EEC53F39" format="dita" scope="local"> 配置动态彩块化 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>44 </p> </td> 
   <td colname="col2"> <p>sp_staged </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_staged= 0或1 </span> </p> </td> 
   <td colname="col4"> <p>如果 <span class="codeph"> sp_staged=1随查 </span> 询一起提交，则运行的查询是分阶段搜索。 </p> <p>分阶段搜索使用当前分阶段的所有组件，包括索引和模板。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>45 </p> </td> 
   <td colname="col2"> <p>sp_start_day、sp_start_month、sp_start_year </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_start_day=数字 </span> </p> <p> <span class="codeph"> sp_start_month=数字 </span> </p> <p> <span class="codeph"> sp_start_year=数字 </span> </p> </td> 
   <td colname="col4"> <p>这三个值指定搜索的开始日期范围，您将其作为一组提供。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>46 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp__soutch_q </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_soutch_q=数字 </span> </p> </td> 
   <td colname="col4"> <p>sp_suckest_q参 <span class="codeph"> 数确定要与建议服务一 </span> 起使用的sp_q[_#] <span class="codeph"></span> 参数。 </p> <p>sp_suckest_q的默认值为0，这表示搜索引擎使用 <span class="codeph"> sp_q的值 </span><span class="codeph"></span> 来确定建议。 </p> <p>设 <span class="codeph"> 置sp_suckest_q=1以 </span> 使用sp_q_1的值 <span class="codeph"></span> 确定建议，依此类推。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>47 </p> </td> 
   <td colname="col2"> <p>sp_t </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_t=字符串 </span> </p> </td> 
   <td colname="col4"> <p>指定要使用的传输模板。 </p> <p>如果要通过对搜索帐户中的每个区域使用不同的搜索传输模板来控制网站中核心搜索结果的外观，此参数很有用。 </p> <p>默认传输模板为“search”。 </p> <p>请参 <a href="../c-appendices/c-templates.md#reference_12AAB3B9F4C74C11956F1DBA95714C2F" type="reference" format="dita" scope="local"> 阅管理网站的多个传输模 </a>板。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>48 </p> </td> 
   <td colname="col2"> <p>sp_trace </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_trace= 0或1 </span> </p> </td> 
   <td colname="col4"> <p>当设置为 <span class="codeph"> sp_stage=1时， </span>在模拟器中启用核心搜索跟踪功能。 </p> <p>请参阅 <a href="../c-about-simulator.md#concept_020AA6751E32421A96A3455508364C7E" format="dita" scope="local"> 关于模拟器 </a>。 </p> <p> <p>注意： 如果未指定此参数，则核心搜索不会收集跟踪信息，并且相关的核心搜索模板标签没有输出。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>49 </p> </td> 
   <td colname="col2"> <p>sp_w, sp_w_control </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_w= <i>sound-alike-enable</i> </code> </p> <p> <code> sp_w_control=<i>sound-alike-control</i> </code> </p> </td> 
   <td colname="col4"> <p>指定应为此特定查询启用或禁用类似声音匹配。 </p> <p>忽略“Exact”的sp_w_control。 类似声匹配已禁用。 </p><p>忽略“Alike”的sp_w_control。 类声匹配已启用</p><p>任何其他项的sp_w_control为1。 类似声匹配已禁用。 </p><p>“其他任何内容”的sp_w_control是任何其他内容。 类声匹配已启用。 </p>使 <span class="codeph"> 用sp_w_control参数可 </span> 以为最终用户控制类似声音匹配创建一个措辞负面或正面的复选框。 </p> <p>如 <span class="codeph"> 果使用sp_w_control=0 </span> ，则使用一个措辞负面的复选框来设置 <span class="codeph"> sp_w参 </span> 数，如下例所示： </p> <p> <code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="0"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="exact"&gt;No&nbsp;Sound-Alike&nbsp;matching </code> </p> <p>如果 <span class="codeph"> 使用sp_w_control=1 </span> ，则使用措辞积极的复选框来设置 <span class="codeph"> sp_w参数，如 </span> 下所示： </p> <p> <code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="1"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="alike"&gt;Sound-Alike&nbsp;matching </code> </p> <p>有关使用sp_w_control和sp_w参数的更多示例，请参阅示例高级搜索表 <span class="codeph"> 单 </span> 以获取更多 <span class="codeph"></span> 示例。 </p> <p>请参 <a href="../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A" type="reference" format="dita" scope="local"> 阅示例高级搜索表 </a>单。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>50 </p> </td> 
   <td colname="col2"> <p>sp_x </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_x=字段 </span> </p> </td> 
   <td colname="col4"> <p>指定要搜索查询字符串的字段。 any表示搜索所有字段。 标题是指仅搜索标题字段。 desc表示仅搜索文档描述字段。 键表示仅搜索文档关键字。 body表示仅搜索正文文本。 alt表示仅搜索替代文本。 url表示仅搜索URL值。 目标表示仅搜索目标关键字。 在任何情况下，忽略相应 <span class="codeph"></span> sp_q参数中“text:”、“desc:”、“keys:”、“body:”、“alt:”、“url:”和“target:”字段前缀的用户规范。 如 <span class="codeph"> 果sp_x不存 </span> 在，或者设置为空字符串或任何字符串，则允许使用标准用户字段前缀。 有关字段前缀的详细信息，请参阅搜索提示说明。 </p> <p>请参阅<a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local">关于搜索</a>。 </p> <p>有关使用sp_x参数的示例，请参阅高级搜索 <span class="codeph"> 表单示例说 </span> 明。 </p> <p>请参 <a href="../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A" type="reference" format="dita" scope="local"> 阅示例高级搜索表 </a>单。 </p> <p>您可以创建以sp_x= <span class="uicontrol"> any Readitions </span> &gt; <span class="uicontrol"> Metadata </span><span class="uicontrol"></span><span class="uicontrol"></span><span class="codeph"></span>Definitions设置为Search By Default的所有字段搜索。 预定义的字段和用户定义的字段都可以用作sp_x参 <span class="codeph"> 数的 </span> 值。 </p> <p>还可以通过多次设置sp_x参数为单个查询分配 <span class="codeph"> 多个字 </span> 段。 以下模板行允许用户查询“Great Books”的“title”和“author”字段。 </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="title"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="author"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Great&nbsp;Books"&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>51 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_x_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_x_#=字段名 </span> </p> </td> 
   <td colname="col4"> <p>此参数指定要在相应的sp_q_#查 <span class="codeph"> 询中搜索的字段 </span> 。 # <span class="codeph"> 被替 <span class="codeph"> 换为介于1到16之间的数字(例如， </span> sp_x_8 </span><span class="codeph"></span>)。 字段名称是任何预定义或用户定义的字段。 </p> <p>如果没有为特定编 <span class="codeph"> 号的查询提供 </span> sp_x#参数，则在“搜索”设置 <span class="uicontrol"> &gt; </span> Metadata <span class="uicontrol"></span><span class="uicontrol"></span><span class="uicontrol"></span> Definitions（搜索的元数据定义）下定义为“By Default”（按默认搜索）的所有字段。 </p> <p>例如，提交以下表单将返回所有包含单词“great”的文档，该单词在“author”字段中也包含单词“Fitzgerald”: </p> <p> <code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="author"&gt;Search&nbsp;only&nbsp;documents&nbsp;written&nbsp;by:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="Fitzgerald"&gt; </code> </p> <p>通过在单个搜索请求中提供同一 <span class="codeph"> sp_x或sp_x_#参数的多个实例，可以将多个字段名与特定查询或编号查询相关联 </span><span class="codeph"></span> 。 </p> <p>例如，要在“body”和“keys”字段中搜索“flower”一词，可创建包含以下信息的搜索表单： </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="body"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="keys"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="flower"&gt; </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 使用后端搜索CGI参数的典型示例 {#section_260012BBC2514CC9A8E02E53DE8B41EE}

以下链接查询使用“音乐”作为搜索查询开始搜索，并使用所有默认参数。 请注意，URL将分为两行，以便可读。 在HTML中，此链接应全部在一行上。

```
<a href="https://search.atomz.com/search/?sp_q=Music&sp_a=sp99999999"> 
Testing...</a>
```

同一功能通常使用表单进行定义：

```
<form action="https://search.atomz.com/search/"> 
<input size=12 name="sp_q" value="Music"><br> 
<input type=hidden name="sp_a" value="sp99999999"> 
<input type=submit value="Search"><br> 
</form>
```

通常在启动搜索时应使用默认参数。 这样，第一页就会显示，并按相关性排序，客户可以选择其他页面和其他选项。 如果站点上的搜索表单包含集合选项，请将集合名称作为参数传递。

## 使用后端搜索CGI参数的详细示例 {#section_5FA3C620D5124FB2AB28857F8D8473F6}

以下表单查询显示 `25` 从结果开始的结果 `10`。 不显示摘要，排序顺序按日期排列，并使用名为的 `support` 集合。 仅返回日期在最近30天内的文档。

```
<form action="https://search.atomz.com/search/"> 
<input size=12 name="sp_q"><br> 
<input type=hidden name="sp_a" value="sp99999999"> 
<input type=submit value="Search"><br> 
<input type=hidden name=sp_n value=10> 
<input type=hidden name=sp_c value=25> 
<input type=hidden name=sp_m value=0> 
<input type=hidden name=sp_s value=1> 
<input type=hidden name=sp_k value="support"> 
<input type=hidden name=sp_date_range value=30> 
</form>
```

