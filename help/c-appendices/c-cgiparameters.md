---
description: 了解如何使用各种CGI参数。
solution: Target
title: CGI参数
topic: Appendices,Site search and merchandising
uuid: a5f43547-bc15-44aa-ba23-6b8b573e09d2
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1943'
ht-degree: 1%

---


# CGI参数{#cgi-parameters}

## CGI参数{#concept_F395999090FE4926B38BC73D5E612800}

## 搜索CGI参数{#reference_DA27A8B0728246DA94994885E1353890}

提供的搜索表单代码可复制并粘贴到站点的HTML中(**[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**)。

请参阅[将搜索表单的HTML代码复制到……](../c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7)。

您还可以设置在搜索表单中或从脚本中列出的参数。 除了下面列出的参数之外，您还可以使用后端搜索参数来控制搜索。

请参阅[后端搜索CGI参数](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。

搜索请求由基本URL组成。 基本URL指示客户正在搜索的帐户，以及一组CGI参数（键值对），这些参数指示如何为关联帐户返回所需的搜索结果。

基本URL与特定帐户和分阶段或实时环境关联。 您可以从帐户管理器请求基本URL的多个别名。 例如，名为Megacorp的公司可能有两个与其帐户关联的基本URL:`https://search.megacorp.com`和`https://stage.megacorp.com`。 前者URL搜索其活动索引，后者URL搜索其分阶段索引。

支持三种格式的CGI参数。 默认情况下，您的帐户配置为使用分号分隔CGI参数，如下例所示：

`https://search.megacorp.com?q=shoes;page=2`

如果您愿意，您可以让您的客户经理将您的帐户配置为使用&amp;符号来分隔CGI参数，如下例所示：

`https://search.megacorp.com?q=shoes&page=2`

还支持第三种格式（称为SEO格式），其中使用正斜杠`/`代替分隔符，并与以下示例中的等号相同：

`https://search.megacorp.com/q/shoes/page/2`

每当使用SEO格式发送请求时，所有输出链接都以相同的格式返回。

| 导向搜索参数 | 示例 | 描述 |
|--- |--- |--- |
| q | `q=string` | 指定搜索的查询字符串。 此参数映射到`sp_q`后端搜索参数。  请参阅[后端搜索CGI参数](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| q# | `q#=string` | 分面（在给定字段内搜索）是通过编号q和x参数完成的。  q参数定义要在facet中搜索的术语，由相应的编号x参数表示。<br>例如，如果您有两个彩块化，它们被命名为大小和颜色，则可以有类似q1=small;x1=size;q2=red;x2=color的内容。此参数映射到`sp_q_exact_#`后端搜索参数。  <br>请参 [阅后端搜索CGI参数](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| x 不支持跨域跟踪# | `q#=string` | 分面（在给定字段内搜索）是通过编号q和x参数完成的。  q参数定义要在facet中搜索的术语，由相应的编号x参数表示。 <br>例如，如果您有两个彩块化，它们被命名为大小和颜色，则可以有类似q1=small;x1=size;q2=red;x2=color的内容。此参数映射到`sp_x_#`后端搜索参数。  <br>请参 [阅后端搜索CGI参数](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| collection（集合） | `collection=string` | 指定要用于搜索的集合。  此参数映射到`sp_k`后端搜索参数。  请参阅[后端搜索CGI参数](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| count（计数） | `count=number` | 指定所显示结果的总计数。  默认值在[!UICONTROL Settings ] > [!UICONTROL Searching ] > [!UICONTROL Searches ]中定义。.  此参数映射到`sp_c`后端搜索参数。  请参阅[后端搜索CGI参数](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| page | `page=number` | 指定返回的结果页。 |
| 排名 | `rank=field` | 指定用于静态排名的排名字段。  该字段必须是关联度大于0的“排名”类型字段。  此参数映射到`sp_sr`后端参数。  请参阅[后端搜索CGI参数](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| 排序 | `sort=number` | 指定排序顺序。<br>“0”是默认值，按相关性得分排序；“1”按日排序；“–1”不排序。用户可以为`sp_s`参数的值指定字段名。  例如，`sp_s=title`会根据标题字段中包含的值对结果进行排序。 当使用字段名称作为` sp_s `参数的值时，结果将按该字段排序，然后按相关性子排序。  要启用此功能，请单击[!UICONTROL Settings ] > [!UICONTROL Metadata ] > [!UICONTROL Definitions ]。 在“定义”页上，单击[!UICONTROL Add New Field ]或单击[!UICONTROL Edit ]获取特定字段名称。 在[!UICONTROL Sorting ]下拉列表中，选择[!UICONTROL Ascending ]或[!UICONTROL Descending ]。 此参数映射到`sp_s`后端搜索参数。 <br>请参 [阅后端搜索CGI参数]。(../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |

## 后端搜索CGI参数{#reference_582E85C3886740C98FE88CA9DF7918E8}

客户通常与称为“向导式搜索”的表示层进行交互。 但是，理论上可以跳过引导式搜索层，并直接使用本页中描述的CGI参数与后端核心搜索交互。

您可以从下表中选择后端搜索CGI参数：
<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>单一查询支持 </p> </th> 
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
   <td colname="col3"> <p> <code>sp_a= string </code> </p> </td> 
   <td colname="col4"> <p>指定帐号字符串。 此参数是必需的，且必须是有效的帐号字符串。 您可以在“设置</span> &gt; <span class="uicontrol">帐户选项</span> &gt; <span class="uicontrol">帐户设置</span>”下找到您的帐户号字符串。<span class="uicontrol"> </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>sp_advanced </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_advanced= 0 or 1 </code> </p> </td> 
   <td colname="col4"> <p>如果<code>sp_advanced=1 </code>是随查询一起提交的，则搜索模板中<code>&lt;search-if-advanced&gt; </code>标记和<code>&lt;/search-if-advanced&gt; </code>标记之间的所有代码都将用于搜索表单。 将忽略<code>&lt;search-if-not-advanced&gt; </code>标记和<code>&lt;/search-if-not-advanced&gt; </code>标记之间的所有代码。 如果提交了<code>sp_advanced=0 </code>（或任何其他值），则忽略&lt;search-if-advanced&gt;模板块，并使用&lt;search-if-not-advanced&gt;模板块。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>sp_c </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_c= number </code> </p> </td> 
   <td colname="col4"> <p>指定要显示的结果总数。 默认值为 10。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>sp_context_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_context_field= <i>field</i> </code> </p> </td> 
   <td colname="col4"> <p>收集给定字段的上下文信息。 通过<code>&lt;search-context&gt; </code>模板标记在搜索结果中输出所收集的信息。 默认值为 <code>body </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>sp_d </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_d= type </code> </p> </td> 
   <td colname="col4"> <p>指定要执行的日期范围搜索的类型。 可能的类型值是任意值，即不执行日期范围搜索，自定义值指示应使用<code>sp_date_range </code>的值确定要搜索的日期，而具体值指示使用<code>sp_start_day </code>、<code>sp_start_month </code>、<code>sp_start_year </code>、<code>sp_end_day </code>、<code>sp_end_month </code>和<code>sp_end_year </code>中的值确定要搜索的日期范围。 <code>sp_d </code> 仅当您的搜索表单包含按自定义范围（通过方式）或按特定开始和结束日期范 <code>sp_date_range </code>围进行搜索的选项时才需要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_d_# </p> </td> 
   <td colname="col3"> <p> <code>sp_d_#= type </code> </p> </td> 
   <td colname="col4"> <p>指定要对相应的<code>sp_q_# </code>查询执行的日期范围搜索的类型。 “#”替换为介于1和16之间的数字(例如，<code>sp_d_8 </code>，适用于编号查询<code>sp_q_8 </code>)。 </p> <p>可以将<code>type </code>设置为任意，即不执行日期范围搜索，自定义，指示<code>sp_date_range_# </code>的值用于确定要搜索的日期，并指定<code>sp_q_min_day_# </code>、<code>sp_q_min_month_# </code>、<code>sp_q_min_year_# </code>、<code>sp_q_max_day_# </code>、<code>sp_q_max_month_# </code>和<code>sp_q_max_year_# </code>中的值应用于确定日期范围。 仅当您的搜索表单包含按自定义范围（通过<code>sp_date_range_# </code>）或按特定开始和结束日期范围进行搜索的选项时，才需要使用<code>sp_d_# </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>sp_date_range </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_date_range= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>指定要应用于搜索的预定义日期范围。 大于或等于零的值指定今天之前要搜索的天数 — 例如，值“0”指定“今天”，值“1”指定“今天和昨天”，值“30”指定“最近30天内”，依此类推。 </p> <p>低于零的值指定自定义范围，如下所示： </p> <p>-1 = "无"，与指定无日期范围相同。 </p> <p>-2 = "This week"，从当周的星期日到星期六进行搜索。 </p> <p>-3 = "Last week"，从当前周之前的星期日到星期六进行搜索。 </p> <p>-4 =“本月”，搜索日期在当月内。 </p> <p>-5 = "上个月"，搜索当月前一个月内的日期。 </p> <p>-6 =“今年”，搜索日期在当年。 </p> <p>-7 =“去年”，其搜索日期在当前年度之前的年份。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_date_range_# </p> </td> 
   <td colname="col3"> <p> <code> sp_date_range_#= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>指定要应用于相应<code>sp_q_# </code>查询的预定义日期范围。 “#”替换为介于1和16之间的数字(例如，<code>sp_date_range_8 </code>，适用于编号查询<code>sp_q_8 </code>)。 </p> <p>大于或等于零的值指定今天之前要搜索的天数。 例如，值0指定今天；值为1表示今天和昨天；值30指定在过去30天内，依此类推。 </p> <p>低于零的值指定自定义范围，如下所示： </p> <p>-1 = "无"，与指定无日期范围相同。 </p> <p>-2 = "This week"，从当周的星期日到星期六进行搜索。 </p> <p>-3 = "Last week"，从当前周之前的星期日到星期六进行搜索。 </p> <p>-4 =“本月”，搜索日期在当月内。 </p> <p>-5 = "上个月"，搜索当月前一个月内的日期。 </p> <p>-6 =“今年”，搜索日期在当年。 </p> <p>-7 =“去年”，其搜索日期在当前年度之前的年份。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>9 </p> </td> 
   <td colname="col2"> <p>sp_dedupe_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_dedupe_field= <i>fieldname</i> </code> </p> </td> 
   <td colname="col4"> <p>指定要对搜索结果进行重复数据消除的单个字段。 该字段上的所有重复结果都将从搜索结果中删除。 例如，对于<code>sp_dedupe_field=title </code>，搜索结果中只显示给定标题的顶部结果（没有两个结果将具有相同的标题字段内容）。 对于多值(允许列表)类型字段，整个字段内容用于比较。 只能指定一个字段。 字段名称中不允许使用“table-qualifier”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>10 </p> </td> 
   <td colname="col2"> <p>sp_e </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_e= number </code> </p> </td> 
   <td colname="col4"> <p>指定对查询字符串中的任意字进行自动通配符扩展，该字符数大于数字。 换句话说，<code>sp_e=5 </code>指定应使用通配符“*”展开包含5个或更多字符的单词(如“查询”或“number”)，使搜索等同于搜索“查询*”或“number*”。 字符数较少的单词不会展开，因此搜索“word”时不会自动扩展通配符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>11 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_e_# </p> </td> 
   <td colname="col3"> <p> <code>sp_e_#= number </code> </p> </td> 
   <td colname="col4"> <p>指定对来自相应<code>sp_q_# </code>查询字符串的任意字进行自动通配符扩展，该字符串的字符数多于数字。 换句话说，<code>sp_e_2=5 </code>指定在<code>sp_q_2 </code>查询字符串中包含5个或5个以上字符的单词(如"查询"或"number")应使用通配符"<code>* </code>"展开，使搜索等同于搜索"查询*"或"number*"。 字符数较少的单词不会展开，因此在<code>sp_q_2 </code>中搜索“word”时不会自动扩展通配符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>12 </p> </td> 
   <td colname="col2"> <p>sp_end_day、sp_end_month、sp_end_year </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_end_day= <i>number</i>,sp_end_month= <i>number</i>, sp_end_year= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>值的这三个部分指定搜索的结束日期范围，并且必须作为集提供。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>13 </p> </td> 
   <td colname="col2"> <p>sp_f </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_f= string </code> </p> </td> 
   <td colname="col4"> <p>指定查询参数字符串的字符集（如<code>sp_q </code>）。 此字符串必须始终与包含搜索表单的页面的字符集匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>14 </p> </td> 
   <td colname="col2"> <p>sp_field_table </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_field_ table=table: field,field... </code> </p> </td> 
   <td colname="col4"> <p>定义包含给定字段的逻辑数据表。 例如，由“color”、“size”和“price”字段组成的名为“items”的表将定义为： </p> <p> <code>sp_field_table=items:color,size,price </code> </p> <p>逻辑表与选中了“允许列表”的字段（在<span class="uicontrol">设置</span> &gt; <span class="uicontrol">元数据</span> &gt; <span class="uicontrol">定义</span>下）一起使用时最为有用。 所有以字段名称为值的CGI参数和模板标记都可以选择指定表名，后跟“”。 在字段名之前（例如<code>sp_x_1=tablename.fieldname </code>）。 </p> <p>例如，要搜索包含大小为“large”（其中项目表示为并行的元数据行）的一个或多个“red”项目的文档，可以使用以下代码： </p> <p> <code> sp_q_exact_1=red&amp;sp_x_1=items.color&amp; sp_q_exact_2=large&amp;sp_x_2=items.size&amp;sp_field_table=items:color,size,price </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>15 </p> </td> 
   <td colname="col2"> sp_i </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> </p></td><td colname="col4"><p></p><p></p><p><code>sp_i=1 </code><code>sp_i=2 </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_k= string </code></p></td><td colname="col4"><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_l= string </code></p></td><td colname="col4"><p><code>sp_q </code><code>string </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_literal= 0 or 1 </code></p></td><td colname="col4"><p><code>sp_literal=1 </code></p><p><code>sp_literal=0 </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_m= number </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_n= number </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_not_found_page= url </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_p= any/all/phrase </code></p></td><td colname="col4"><p><code>any </code><code>all </code><code>phrase </code></p><p><code>phrase </code><code>all </code><code>sp_p </code></p><p></p><p></p><p><code>sp_p </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_p_#= any/all/phrase </code></p></td><td colname="col4"><p><code>sp_q_# </code><code>sp_p_8 </code><code>sp_q_8 </code><code>any </code><code>all </code><code>phrase </code></p><p><code>all </code><code>phrase </code><code>sp_p_# </code><code>any </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_pt= <i>exact/equivalent/compatible</i> </code></p></td><td colname="col4"><p><code>exact </code><code>equivalent </code><code>compatible </code><code>sp_p </code><code>exact </code><code>sp_p </code><code>all </code><code>phrase </code><code>equivalent </code><code>sp_pt </code><code>compatible </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_pt_#= <i>exact/equivalent/compatible</i> </code></p></td><td colname="col4"><p><code>sp_q_# </code><code>sp_p_8 </code><code>sp_q_8 </code><code>exact </code><code>equivalent </code><code>exact </code><code>compatible </code><code>sp_p_# </code><code>exact </code><code>sp_p_# </code><code>equivalent </code><code>sp_pt_# </code><code>compatible </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q= string </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_#= text </code></p></td><td colname="col4"><p><code>sp_q_# </code><code>sp_q_1 </code><code>sp_q_16 </code></p><p></p><p><code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="books"&gt; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_day= integer value </code></p><p><code>sp_q_month= integer value </code></p><p><code>sp_q_year= integer value </code></p><p><code>sp_q_day_#= integer value </code></p><p><code>sp_q_month_#= integer value </code></p><p><code>sp_q_year_#= integer value </code></p></td><td colname="col4"><p><code>sp_q_day </code><code>sp_q_month </code><code>sp_q_year </code><code>sp_q </code></p><p><code># </code><code>sp_q_day_6 </code><code>sp_q_6 </code></p><p><code>PublishDate </code></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt; Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;On&nbsp;:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Month &lt;input&nbsp;type="text"&nbsp;name="sp_q_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Year&nbsp; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_q_location=<i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code></p><p><code> sp_q_location_#= <i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code></p></td><td colname="col4"><p><code>sp_q_location </code><code>sp_q_location_# </code><code># </code></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_q_max_relevant_distance= <i>value</i> </code></p><p><code> sp_q_max_relevant_distance_#= <i>value</i> </code></p></td><td colname="col4"><p><code>sp_q_max_relevant_distance </code><code>sp_q_max_relevant_distance_# </code><code># </code></p><p><code>sp_q_max_relevant_distance </code></p><p><code>sp_q_max_relevant_distance_# </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p><p></p></td><td colname="col03"><p></p><p></p></td><td colname="col3"><p><code> sp_q_min_day=<i>integer value</i> </code></p><p><code> sp_q_min_month=<i>integer value</i> </code></p><p><code> sp_q_min_year=<i>integer value</i> </code></p><p><code> sp_q_max_day=<i>integer value</i> </code></p><p><code> sp_q_max_month=<i>integer value</i> </code></p><p><code> sp_q_max_year=<i>integer value</i> </code></p><p><code> sp_q_min_day_#=<i>integer value</i> </code></p><p><code> sp_q_min_month_#=<i>integer value</i> </code></p><p><code> sp_q_min_year_#=<i>integer value</i> </code></p><p><code> sp_q_max_day_#=<i>integer value</i> </code></p><p><code> sp_q_max_month_#=<i>integer value</i> </code></p><p><code> sp_q_max_year_#=<i>integer value</i> </code></p></td><td colname="col4"><p><code>sp_q_min_day </code><code>sp_q_min_month </code><code>sp_q_min_year </code><code>sp_q_max_day </code><code>sp_q_max_month </code><code>sp_q </code></p><p><code># </code><code>sp_q_min_day_6 </code><code>sp_q_6 </code></p><p></p><p><code>PublishDate </code></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;Between:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_min_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Start&nbsp;Year 
      And:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_max_day_1"&nbsp;size="2"&nbsp;value="31"&gt;&nbsp;End&nbsp;Day 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_month_1"&nbsp;size="2"&nbsp;value="12"&gt;&nbsp;End&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;End&nbsp;Year </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_min= value </code></p><p><code>sp_q_max= value </code></p><p><code>sp_q_min_#= value </code></p><p><code>sp_q_max_#= value </code></p><p><code>sp_q_exact_#=value </code></p></td><td colname="col4"><p><code>sp_q_min </code><code>sp_q_max </code><code>sp_q_exact </code><code>sp_q </code></p><p><code># </code><code>sp_q_min_8 </code><code>sp_q_8 </code></p><p><code>sp_q_exact_# </code><code>sp_q_min_# </code><code>sp_q_max_# </code><code>sp_q_exact_# </code><code>sp_q_min_# </code><code>sp_q_max_# </code></p><p><code>sp_q_min_# </code><code>sp_q_max_# </code><code>sp_q_exact_# </code><code>...&amp;sp_q_exact_1=green|red&amp;sp_x_1=color </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_nocp= 1 or 0 </code></p><p><code>sp_q_nocp_#= 1 or 0 </code></p></td><td colname="col4"><p><code>0 </code></p><p><code>1 </code></p><p><code>sp_q_nocp </code><code>sp_q </code><code># </code><code>sp_q_nocp_8 </code><code>sp_q_8 </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_required= 1 or 0 or -1 </code></p><p><code>sp_q_required_#= 1 or 0 or -1 </code></p></td><td colname="col4"><p></p><p><code>sp_q_required </code><code>sp_q </code></p><p><code># </code><code>sp_q_required_8 </code><code>sp_q_8 </code></p><p></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="platform"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="calc"&gt; 
      Exclude:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="mac&nbsp;win&nbsp;all"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_q_required_1"&nbsp;value="-1"&gt; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_redirect_ 
      if_one_result= <i>0 or 1</i> </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_referrer= url </code></p></td><td colname="col4"><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p></p></td><td colname="col4"><p><code>ro </code></p><p></p><p><code>sp_ro=body:10 </code></p><p></p><p><code>sp_ro=body:9|title:9 </code></p><p><p><code>sp_ro=title:10 </code><code>title </code><code>sp_ro </code><code>sp_ro </code></p></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_s= number </code></p></td><td colname="col4"><p></p><p><code>sp_s </code><code>sp_s=title </code><code>sp_s </code></p><p></p><p><code>sp_s </code></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="artist"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="album"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="track"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Music&nbsp;Search"&gt; </code></p><p><code>sp_field_table </code></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_sr= field </code></p></td><td colname="col4"><p><code>sp_sr </code></p><p><code>sp_sr </code><code>&lt;input type="hidden" name="sp_sr" value=""&gt; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_sfvl_field= string </code></p></td><td colname="col4"><p><code>search-field-value-list</code></p><p><code>sp_sfvl_field </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p></p></td><td colname="col4"><p><code>search-field-value-list </code></p><p><code>dynamic-facet-field-count </code><code>dynamic-facet-field-count </code></p><p><code>sp_sfvl_df_count </code><code>dynamic-facet-field-count </code><code>sp_sfvl_df_count </code><code>sp_sfvl_df_count </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p></p><p></p></td><td colname="col4"><p></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p></p><p></p></td><td colname="col4"><p></p><p><p><code>sp_sfvl_df_count </code><code>sp_sfvl_df_include </code><code>sp_sfvl_df_include </code><code>sp_sfvl_df_count </code></p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_staged= 0 or 1 </code></p></td><td colname="col4"><p><code>sp_staged=1 </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_start_day= number </code></p><p><code>sp_start_month= number </code></p><p><code>sp_start_year= number </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_suggest_q= number </code></p></td><td colname="col4"><p><code>sp_suggest_q </code><code>sp_q[_#] </code></p><p><code>sp_suggest_q </code><code>sp_q </code></p><p><code>sp_suggest_q=1 </code><code>sp_q_1 </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_t= string </code></p></td><td colname="col4"><p></p><p></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_trace= 0 or 1 </code></p></td><td colname="col4"><p><code>sp_stage=1 </code></p><p></p><p><p></p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_w= <i>sound-alike-enable</i> </code></p><p><code> sp_w_control=<i>sound-alike-control</i> </code></p></td><td colname="col4"><p></p><p></p><p></p><p></p><p></p><code>sp_w_control </code></p><p><code>sp_w_control=0 </code><code>sp_w </code></p><p><code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="0"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="exact"&gt;No&nbsp;Sound-Alike&nbsp;matching </code></p><p><code>sp_w_control=1 </code><code>sp_w </code></p><p><code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="1"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="alike"&gt;Sound-Alike&nbsp;matching </code></p><p><code>sp_w_control </code><code>sp_w </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_x= field </code></p></td><td colname="col4"><p><code>sp_q </code><code>sp_x </code></p><p></p><p><code>sp_x </code></p><p></p><p><code>sp_x=any </code><code>sp_x </code></p><p><code>sp_x </code></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="title"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="author"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Great&nbsp;Books"&gt; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_x_#= field-name </code></p></td><td colname="col4"><p><code>sp_q_# </code><code> # </code><code>sp_x_8 </code></p><p><code>sp_x_# </code></p><p></p><p><code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="author"&gt;Search&nbsp;only&nbsp;documents&nbsp;written&nbsp;by:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="Fitzgerald"&gt; </code></p><p><code>sp_x </code><code>sp_x_# </code></p><p></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="body"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="keys"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="flower"&gt; </code></p></td></tr></tbody></table>

## 使用后端搜索CGI参数{#section_260012BBC2514CC9A8E02E53DE8B41EE}的典型示例

以下链接查询开始使用“音乐”作为搜索查询的搜索，并使用所有默认参数。 请注意，URL被拆分为两行，以便于读取。 在您的HTML中，此链接应全部在一行上。

```
<a href="https://search.atomz.com/search/?sp_q=Music&sp_a=sp99999999"> 
Testing...</a>
```

同样的功能通常通过表单定义：

```
<form action="https://search.atomz.com/search/"> 
<input size=12 name="sp_q" value="Music"><br> 
<input type=hidden name="sp_a" value="sp99999999"> 
<input type=submit value="Search"><br> 
</form>
```

在启动搜索时，通常应使用默认参数。 这样，第一个页面就会显示，并按相关性排序，并允许客户选择其他页面和其他选项。 如果您网站上的搜索表单包含集合选项，请将集合名称作为参数传递。

## 使用后端搜索CGI参数{#section_5FA3C620D5124FB2AB28857F8D8473F6}的详细示例

以下表单查询显示`25`结果，从结果`10`开始。 不显示摘要，排序顺序按日期排列，并使用名为`support`的集合。 仅返回日期在最近30天内的文档。

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

