---
description: 'null'
seo-description: 'null'
seo-title: 模板
solution: Target
title: 模板
topic: Appendices,Site search and merchandising
uuid: 78299032-dc23-4dfe-b68f-cd57b2b6d7d8
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a

---


# 模板{#templates}

## 模板 {#concept_A5CFB6BD805D49459A96219AF1B17842}

## 演示文稿模板标记 {#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64}

演示文稿模板的站点搜索／销售标记和属性列表。


演示文稿模板是包含站点搜索／销售定义的演示文稿模板标记的HTML文件。 这些标记指示客户看到的搜索结果的格式。

请参阅 [关于模板](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5)。

您可以从以下演示文稿标记组中进行选择：

* [声明](../c-appendices/c-templates.md#section_82C5CA734D2941EB858FEFE3B695D2EC)
* [结果](../c-appendices/c-templates.md#section_06F249C9F6AE4B0F8C32117E19DCC905)
* [彩块化](../c-appendices/c-templates.md#section_EA4C5678D5864B89BAB4D0DFE62A4624)
* [痕迹导航](../c-appendices/c-templates.md#section_9B39B71FA6EC49FA8D88AD8A3BA987F7)
* [菜单](../c-appendices/c-templates.md#section_1D489ADF041F4351A66E5D5742125CA8)
* [Pagenav](../c-appendices/c-templates.md#section_2EE397635C514BBC8D668278EA314F35)
* [最近搜索](../c-appendices/c-templates.md#section_8CD907521F584257B475595B01A5964B)
* [Did You Mean](../c-appendices/c-templates.md#section_C1EB3B9D8E1242798A6E04609D1E3543)
* [自动完成](../c-appendices/c-templates.md#section_897316BEE1454E839A56B565CA4AF018)
* [商店](../c-appendices/c-templates.md#section_A33E25DB5E67404A823BD9618665B773)
* [区域](../c-appendices/c-templates.md#section_B9B3179E000C42D492E1541F2FE44CB5)
* [循环指示器](../c-appendices/c-templates.md#section_387322CA0AA843A2ACF2795C328673E9)
* [其他语言](../c-appendices/c-templates.md#section_BFE8DC98E26F4D7BB60FEC54D9A5DC6C)

## 声明 {#section_82C5CA734D2941EB858FEFE3B695D2EC}

声明是特殊的指引式声明标记，您可以在顶级演示文稿模板的顶部设置这些标记。 将忽略任何后续声明，包括包含的模板中的声明。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-content-type-header content="content-type"&gt; </span> </p> </td> 
   <td colname="col2"> <p>默认情况下，演示文稿模板会以text/html的mime类型发回。 您可以更改此标记使用的内容类型。 </p> <p>在演示文稿模板中尽可能高地声明此标记。 请勿使用此标记在同一行上添加其他文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-xml-declare [charset="charset"]&gt; </span> </p> </td> 
   <td colname="col2"> <p> 如果要返回XML，则可以使用此标签创建XML声明。 使此标记成为演示文稿模板中的第一行。 使用此标记时，除非在第一行中用 <span class="codeph"> &lt;guided-content-type-header&gt;覆盖它，否则content-type将自动设置为text/xml </span> 。 如果不指定字符集，则默认为UTF-8。 此标签在XML文档中生成以下输出： </p> <p> <span class="codeph"> &lt;?xml version="1.0" encoding="charset-name" standalone="yes" ?&gt; </span> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 结果 {#section_06F249C9F6AE4B0F8C32117E19DCC905}

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng 1/31/13--> <span class="codeph"> &lt;guided-results [gsname="searchname"]&gt;&lt;/guided-results&gt; </span> </p> </td> 
   <td colname="col2"> <p>向导式结果标签定义结果循环的边界。 可以通过指定gsname属性访问任何结 <span class="codeph"> 果 </span> 集。 如果未 <span class="codeph"> 提供 </span> gsname，则显示默认搜索结果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng 1/31/13--> <span class="codeph"> &lt;guided-result-link [gsname="fieldname"] [attr="value"]+&gt;&lt;/guided-result-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>要创建指向给定结果的链接，请使 <span class="codeph"> 用向导结果链接标 </span> 签。 通过定义 <span class="codeph"> gsname属 </span> 性，您可以使用索引中的字段，而不是引用“search-url”的标准“loc”标记。 任何其他属性（如类和目标）也可以传递，这些属性将输出到生成的锚点标签中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng 1/31/13--> <span class="codeph"> &lt;guided-result-img gsname="fieldname" [attr="value"+&gt; </span> </p> </td> 
   <td colname="col2"> <p>&lt;guided-result-img&gt;标 <span class="codeph"> 记有助于创建图像标记，而不是将变量嵌入原始 </span> img标 <span class="codeph"></span> 记中。 </p> <p>在gsname属性中指定用于图像路径的 <span class="codeph"> 字 </span> 段。 结果是一个 <span class="codeph"> img标 </span> 签，其中包含您定义并传递的任何标准HTML属性。 因此，以下示例： </p> <p> <code class="syntax html"> &lt;guided-result-img&nbsp;gsname="thumbnail" 
      &nbsp;class="thumb"&nbsp;border="0"/&gt; </code> </p> <p>becomes: </p> <p> <code class="syntax html"> &lt;img&nbsp;src="prod8172.jpg"&nbsp;class="thumb" 
      &nbsp;border="0"/&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 1/31/13; search-eng version does not have [escape...] Added ijson on 8/28/2015--> <span class="codeph"> &lt;guided-result-field gsname="fieldname" [escape="html|url|js|json|ijson|0"/&gt; </span> </p> </td> 
   <td colname="col2"> <p> 结果中显示的任何信息都将显示为 <span class="codeph"> &lt;guided-result-field&gt;标记(使用自动生成标记(如 </span> &lt;guided-result-img&gt;标记)除 <span class="codeph"></span> 外)。 </p> <p>在gsname中指定搜索索引字段的 <span class="codeph"> 名称 </span>。 传递的确切字符串是在模板中输出的。 </p> <p>如果希望此字段以不同于传输模板中指定的方式转义，则可指定转义选项。 </p> <p>此编码应用于传输模板中指定的任何编码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <span class="codeph"> &lt;guided-if[-not-result-field gsname="fieldname&gt;&lt;/guided-if-result-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果特定字段中有要显示的内容，则此条件标记集为true。 如果不存在内容，则条件为false。 您可以使用标记来决定是否在不存在值时显示或不显示周围的HTML，或者是否显示其他图像等。 </p> <p> <code class="syntax html"> &lt;guided-if-result-field&nbsp;gsname="thumbnail"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-result-img&nbsp;gsname="thumbnail"&nbsp;class="thumb"&nbsp;/&gt; 
      &lt;guided-else-result-field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;img&nbsp;src="nothumb.jpg"&nbsp;class="nothumb"&nbsp;/&gt; 
      &lt;/guided-if-result-field&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <code> &lt;guided-if[-not]-result-wrap&gt; 
      &lt;guided-else-result-wrap&gt; 
      &lt;/guided-if[-not]-result-wrap&gt; </code> </p> </td> 
   <td colname="col2"> <p>在列中显示结果时，此标签用于标识当前结果是否标记列的结尾。 </p> <p>当Boolean条件为true时，将HTML添加到结果末尾以结束行并开始一个新行。 当它是最后一行时，不会启动新行。 </p> <p>请参 <span class="codeph"> 阅&lt;guided-if-not-last&gt;以了 </span> 解有关该标记的更多信息。 </p> <p> <code class="syntax html"> &lt;guided-if-result-wrap&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/div&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-not-last&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;div&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-not-last&gt; 
      &nbsp;&lt;/guided-if-result-wrap&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-results-found [gsname="searchname""/&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果后端搜索请求返回结果，则返回1；如果未返回，则返回0。 如果未 <span class="codeph"> 指定 </span> gsname，则标记将采用主搜索。 此标签有助于将逻辑传递给JavaScript例程。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-results-total [gsname="searchname"]/&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回指定结果集中的结果总数。 假定未提供gsname时使用 <span class="codeph"> 默认 </span> 搜索。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-results-lower [gsname="searchname"]/&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回页面上指定结果集的较低结果的结果编号。 假定未提供gsname时使用 <span class="codeph"> 默认 </span> 搜索。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-results-upper [gsname="searchname""/&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回页面上指定结果集的上方结果的结果编号。 假定未提供gsname时使用 <span class="codeph"> 默认 </span> 搜索。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> 

    &amp;lt;/guided-if[-not]-results-found&amp;gt;&lt;/code> &lt;/p> &lt;/td>
<td colname="col2"> <p>在找到结果时显示内容。 或者，在找不到结果时不显示结果HTML。 </p> <p> <code class="syntax html"> &lt;guided-if-results-found&nbsp;gsname="products"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-results&nbsp;gsname="products"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;... 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-results&gt; 
      &lt;guided-else-results-found&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;No&nbsp;results&nbsp;were&nbsp;found. 
      &lt;/guided-if-results-found&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-title/&gt; </span> </p> </td> 
   <td colname="col2"> <p>&lt;guided-result-title&gt;标签提供了 <span class="codeph"> 使用 </span> &lt;title&gt;传输标签指定的标题传输模 <span class="codeph"></span> 板字段值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-description/&gt; </span> </p> </td> 
   <td colname="col2"> <p>&lt;guided-result-description&gt;标 <span class="codeph"> 签提供了使用 </span> &lt;description&gt;传输标签指定的描述传输模板字段 <span class="codeph"></span> 的值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-loc/&gt; </span> </p> </td> 
   <td colname="col2"> <p>&lt; <span class="codeph"> guided-result-loc&gt;标签提供 </span> 了loc传输模板字段的值，该字段使用 <span class="codeph"> &lt;loc&gt;传输标 </span> 签指定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;/guided-if-result-field&amp;gt;&lt;/code> &lt;/p> &lt;/td>
<td colname="col2"> <p>如果特定字段中有要显示的内容，则为true。 如果不存在内容，则条件为false。 使用标记决定是否显示周围的HTML（如果不存在值，或者是否显示其他图像等）。 </p> <p> <code class="syntax html"> &lt;guided-if-result-field&nbsp;gsname="thumbnail"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-result-img&nbsp;gsname="thumbnail"&nbsp;class="thumb"/&gt; 
      &lt;guided-else-result-field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;img&nbsp;src="nothumb.jpg"&nbsp;class="nothumb"/&gt; 
      &lt;/guided-if-result-field&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-attribute-table gsname="tablename"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签提供了在传输模板中定义的具有 <span class="codeph"> &lt;attribute_table&gt;传输标签的 </span> 遍历属性表。 有 <span class="codeph"> &lt;guided-result-attribute-table-field&gt;标签用于显 </span> 示属性表字段值。 此外，还可以使用简单的导 <span class="codeph"> 向结果字段内部 </span> 循环标签来显示其他结果字段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-attribute-table-field gsname="fieldname" [escape="html|url|js|json|0"]/&gt; </span> </p> </td> 
   <td colname="col2"> <p>显示在传输模板中定义的属性表字段。 </p> <p> 

    ...
    
    &amp;gt&amp;lt;guided-result-attribute-table&amp; nbsp;gsname=&quot;downloads&quot;&amp;gt;
    
    &amp;nbsp;&amp;li&amp;gt&amp;nbsp;
    &amp;&amp;nbsp;&amp;nbsp;&amp;am;nbsp;&amp;ap;lt;a&amp; nbsp; lt; guided-result-attribute-table-field&amp; nbsp;gsname=&quot;download-link&quot;&amp; nbsp;/&amp;&quot;&amp;gt;
    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;;nbsp;&amp;;bsp;&amp;&amp;&amp; lt; guided-result-attribute-table-field&amp; nbsp; gsname=&quot;download-title&quot;&amp; nbsp;/&amp;
    &amp;nbsp;&amp;&amp;nbsp;&amp;nbsp;&amp;lt&amp;am;&amp;am;&amp;a;&amp;am;&amp;a;&amp;amnbsp;(&amp;lt;)nbsp;
    &amp;&amp;;/liamp;;lt;/result-attribute-mable&amp;&amp;;gt;gt;gt;gt;amp&amp;
    
    
    
    
    
    &amp;......
    
    &amp;lt;/guided results&amp;gt;&lt;/code> &lt;/p> &lt;/td>
</tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release in October 2014--> <span class="codeph"> &lt;guided-trace [gsname="searchname""/&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出在给定搜索的传输模板输出的JSON数据的常规部分内在跟踪数据中找到的跟踪信息。 </p> <p>如果未提供搜索名称，则假 <span class="codeph"> 定采 </span> 用默认名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release on October 30, 2014)--> <span class="codeph"> &lt;guided-result-trace/&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出在“结果”&gt;“跟踪”中找到的JSON内容，该JSON数据由传输模板输出，其中包含当前搜索结果的跟踪信息。 </p> <p>此标记仅在 <span class="codeph"> &lt;guided-results&gt;&lt;/guided-results&gt;循环中有 </span> 效。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 彩块化 {#section_EA4C5678D5864B89BAB4D0DFE62A4624}

Facet是可导航的组件，可让您深入搜索结果。 您可以使用facet标签在您的演示文稿模板上显示各种facet。 按名称引用彩块化。

请参阅 [关于彩块化](../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5)。

请参阅[关于 Facet Rail](../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB)。

请参阅 [关于动态彩块化](../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899)。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 02/27/2014--> <span class="codeph"> &lt;guided-dynamic-facets&gt;&lt;/guided-dynamic-facets&gt; </span> </p> </td> 
   <td colname="col2"> 
    <!--NEW 2/2/2014--> <p>给定搜索的任何动态彩块化的循环上下文。 </p> <p>编辑 <span class="codeph"> &lt;guided-facet&gt;演示文稿模板标 </span> 签，以便gsname属性由 <span class="codeph"> &lt;guided-dynamic-facets&gt;循环上下文自动 </span> 提供。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-display-name gsname=" <span class="varname"> facetname </span>"/&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回facet的显示标签。 </p> <p>如果facet在传输模 <span class="codeph"> 板上使用&lt;display-name&gt; </span> 标签，则该标签的内容将成为标签。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-rail&gt;&lt;/guided-facet-rail&gt; </span> </p> </td> 
   <td colname="col2"> <p> 在演示文稿模板上定义一个部分，该部分用作facet边栏中每个facet的重复图案。 </p> <p> 属于facet边栏的每个facet都使用此部分来评估其输出。 </p> <p>以下是facet边栏的示例： </p> <p> <code class="syntax html"> &lt;guided-facet-rail&gt; 
      &nbsp;&nbsp;&lt;guided-facet&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-display-name/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;... 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet&gt; 
      &nbsp;&nbsp;&lt;/guided-facet-rail&gt; </code> </p> <p>请注意，当在 <span class="codeph"> &lt;guided-facet-rail&gt;标签内部时，以下标签不需要 </span><span class="codeph"></span> gsname属性，因为值在搜索时动态确定并正确替换： </p> 
    <ul id="ul_5B5ACAFD2B8848DDB27471AB9DA7BE6E"> 
     <li id="li_5A07E78D51FE4708879DD742C877FFFF">向导彩块化 </li> 
     <li id="li_B875DCACD7AB4FC890A456A6939AB657">guided-facet-display-name </li> 
     <li id="li_B70450749E864DE7BA401E3CD6EF5EB3">向导彩块化总数 </li> 
     <li id="li_DECDF5EF6FF7454F86C236D322F2BFEA">向导——彩块化——还原——链接 </li> 
     <li id="li_176949227AC14E8CA643A419E10F7B5A">向导——彩块化——还原路径 </li> 
     <li id="li_B32D981281744462BC680F6EFEAC0069">向导——彩块化行为 </li> 
    </ul> <p>“彩块化边栏”页 <span class="wintitle"> 面上的排 </span> 序条件决定彩块化的位置。 您可以从Sort Facets Method（排序彩块化方法）下拉列表中选择排序顺序。 </p> <p> 
     <!--NEW 02/27/2014-->此标签可以选择接受 <span class="codeph"> _dynamic_facets的gsname属性值 </span>，该值为此搜索的任何动态彩块化提供循环上下文。 此预定义的facet边栏也会在Business Rules用户界面中显示，以便在facet边栏“_dynamic_facets”中将 <span class="codeph"> facet X动作推送到位置Y </span>”。 </p> <p>请参阅<a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local">关于 Facet Rail</a>。 </p> <p>另请参 <a href="../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> 阅关于动态彩块 </a>化。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match current search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet gsname=" <span class="varname"> facetname </span>" height=" 60px <span class="varname"> " width=" </span>120px <span class="varname"></span>"&gt;&lt;/guided-facet&gt; </span> </p> </td> 
   <td colname="col2"> <p>使用向 <span class="codeph"> 导facet标 </span> 签可定义一个区域，其中所有facet标签都与特定facet相关。 此标签也是一个布尔标签，如果facet中不存在任何值，则会隐藏所有内容。 在这种情况下，没有输出小平面值的点)。 </p> <p>高度和宽度属性是可选的，尺寸以像素(px)为单位指定。 可视规则生成器(VRB)使用这两个属性，并在隐藏facet时显示一个虚线框作为交互式占位符。 </p> <p> 当显示名称位于facet中且facet处于隐藏状态时，该名称也会隐藏。 但是，如果名称位于facet之外，则仅当区域标签或guided-if-facet-visible标签被包围时，才可隐藏 <span class="codeph"></span><span class="codeph"></span> 该名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-if[-not]-facet-long [gsname="facetname"]&gt;&lt;/guided-if[-not]-facet-long&gt; </span> </p> </td> 
   <td colname="col2"> <p>当facet值的数量超过配置中定义的长度阈值时，此条件标签为true。 当列表过长时，使用它将facet显示为其他UI元素（如截断列表或滚动框）。 </p> <p> <code class="syntax xml"> &lt;guided-facet&nbsp;name="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-long&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;select&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-option&nbsp;/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/select&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-long&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-value-link&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-long&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>您还可以通过使用gsname属性直接引用特定facet，在命名的 <span class="codeph"> guided-facet块的上下文之外使 </span> 用此 <span class="codeph"></span> 条件。 </p> <p> <code class="syntax html"> &lt;guided-if-facet-long&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;The&nbsp;category&nbsp;facet&nbsp;is&nbsp;very&nbsp;long! 
      &lt;/guided-if-facet-long&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-if[-not]-facet-selected [gsname="facetname"]&gt;&lt;/guided-if[-not]-facet-selected&gt; </span> </p> </td> 
   <td colname="col2"> <p>当点击facet至少一次且当前已选择facet值时，此条件标签为true。 它用于显示或隐藏HTML或gs标记，具体取决于是否单击了facet。 </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;name="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This&nbsp;facet&nbsp;has&nbsp;been&nbsp;selected.&nbsp;&nbsp;You&nbsp;can&nbsp;no&nbsp;longer&nbsp;refine&nbsp;it. 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-value-link&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-selected&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>您还可以通过使用gsname属性直接引用特定facet，在命名的 <span class="codeph"> guided-facet块的上下文之外使 </span> 用此 <span class="codeph"></span> 条件。 </p> <p> <code> &lt;guided-if-facet-selected&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;The&nbsp;category&nbsp;facet&nbsp;is&nbsp;selected! 
      &lt;/guided-if-facet-selected&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-if[-not]-facet-single [gsname="facetname"]&gt;&lt;/guided-if[-not]-facet-single&gt; </span> </p> </td> 
   <td colname="col2"> <p>当只有一个facet值时，此条件标记为true。 当facet无法优化结果时，使用标记更改facet的显示。 </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;name="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-single&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Facet&nbsp;is&nbsp;not&nbsp;refinable. 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-single&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-value-link&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-single&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>您还可以通过使用gsname属性直接引用特定facet，在命名的 <span class="codeph"> guided-facet块的上下文之外使 </span> 用此 <span class="codeph"></span> 条件。 </p> <p> <code class="syntax html"> &lt;guided-if-facet-single&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;There&nbsp;is&nbsp;only&nbsp;one&nbsp;value&nbsp;in&nbsp;the&nbsp;category&nbsp;facet! 
      &lt;/guided-if-facet-single&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--Added 7/15/2014--> <span class="codeph"> &lt;guided-if[-not]-facet-multiselect [gsname="facetname"]&gt;&lt;/guided-if[-not]-facet-multiselect&gt; </span> </p> </td> 
   <td colname="col2"> <p>当facet为多选时，此条件标签为true。 使用标记可更改&lt;guided-facet-rail&gt;或 <span class="codeph"> &lt;guided-dynamic-facets&gt;标 </span> 记 <span class="codeph"> 内facet的显示 </span> 。 </p> <p> 

    &amp; nbsp;&amp; nbsp;&amp; nbsp;&amp; lt; guided-if-facet-multiselect&amp;gt;
    &amp; nbsp;...
    &amp; nbsp;&amp; lt; guided-else-facet-multiselect&amp;gt;
    &amp; nbsp;...
    &amp;&amp; lt;/guided-if-facet-multiselect&amp; gt;
    &amp; nbsp;&amp; nbsp;&amp; nbsp;&amp;&amp; nbsp;&amp;nbsp;...
    &amp;&amp; nbsp;&amp;&amp; nbsp;&amp; lt;/向导-facet&amp; gt;
    &amp;&amp; nbsp;&amp;&amp; lt;/向导-facet-rail&amp;gt;&lt;/code> &lt;/p> &lt;/td>
</tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-values [gsname=" <span class="varname"> facetname </span>"]&gt;&lt;/guided-facet-values&gt; </span> </p> </td> 
   <td colname="col2"> <p>这是facet value循环迭代器标签。 您可以在命名的向导facet块的上下文中定 <span class="codeph"> 义它 </span> ，在这种情况下可以忽略 <span class="codeph"> gsname <span class="varname"></span></span>。 或者，您可以在任何向导facet块 <span class="codeph"> 之外定义它， </span> 但它需要gsname属性来标识显示的facet <span class="codeph"><span class="varname"></span></span> 值集合。 </p> <p>您还可以使用此标记在指定的向导facet块的上下文外显示facet <span class="codeph"> 值 </span> 。 您可以使用gsname属性直接引用特定 <span class="codeph"> facet <span class="varname"></span></span> 。 </p> <p> <code class="syntax html"> &lt;script&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;registerFacetValues('category',&nbsp;'&lt;guided-facet-values&nbsp;gsname="category"&gt;&lt;guided-facet-value/&gt;,&lt;/guided-facet-values&gt;'); 
      &lt;/script&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-value [escape="html|url|js|json|0"/&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出当前facet值的字符串。 </p> <p>默认情况下，该值为HTML转义。 您可以使用转义选项更改转义值的方式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-count/&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出与当前facet值匹配的结果数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-facet-value-link [attr="value"]+&gt;&lt;/guided-facet-value-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>在facet值字符串周围创建一个链接，以便站点访客单击。 将自动生成路径，以按当前facet值缩小结果范围。 它支持将任何属性直接传递到锚点标签。 </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-value-link&nbsp;class="facetlink"&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-value-link&gt; 
      &lt;/guided-facet-values&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> <code> &lt;guided-if-facet-value-selected&gt; 
      &lt;guided-else-facet- 
      value-selected&gt; 
      &lt;/guided-if-facet-value-selected&gt; </code> </p> </td> 
   <td colname="col2"> <p>更改当前选定facet值的显示。 如果它已经被选中，在大多数情况下，它不再可链接。 </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-value-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;b&gt;&lt;guided-facet-value/&gt;&lt;/b&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-value-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt;&nbsp;&nbsp;&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-value-selected&gt; 
      &lt;/guided-facet-values&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> 

    &amp;lt;/guided-if[-not]-facet-value-ghost&amp;gt;&lt;/code> &lt;/p> &lt;/td>
<td colname="col2"> <p>当facet值为重影值时，更改facet值的显示。 当facet值是重影值时，它通常以斜体文本显示，以指示该值缺失或“重影”。 </p> <p>以下代码摘录是facet块的一个示例： </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-value-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;b&gt;&lt;guided-facet-value&nbsp;/&gt;&nbsp;(&lt;guided-facet-count&nbsp;/&gt;)&lt;/b&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-value-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-value-ghost&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;i&gt;&lt;guided-facet-value&nbsp;/&gt;&nbsp;(0)&lt;/i&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-value-ghost&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&nbsp;class="link"&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-link&gt;&nbsp;(&lt;guided-facet-count&nbsp;/&gt;) 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-value-ghost&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-value-selected&gt; 
      &lt;/guided-facet-values&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-undo-link gsname=" <span class="varname"> facetname </span>"&gt;&lt;/guided-facet-undo-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>显示给定Facet的撤消链接。 如果存在多选facet，则此链接将取消选择给定facet的所有值。 为facet命名。 如果当前未选择facet，则链接是当前路径。 </p> <p>以下是此标记用法的示例： </p> <p> <code class="syntax html"> &lt;guided-if-facet-selected&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-undo-link&nbsp;gsname="category"&gt;Undo&nbsp;Category&lt;/guided-facet-undo-link&gt; 
      &lt;/guided-if-facet-selected&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <varname></varname> </p> </td> 
   <td colname="col2"> <p>当facet值的数量超过配置中定义的长度阈值时，此条件标签为true。 当列表过长时，使用它将facet显示为其他用户界面元素（如截断列表或滚动框）。 </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-long&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;div&nbsp;class="long_facet"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/div&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-long&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;div&nbsp;class="facet"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/div&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-long&gt; 
      &nbsp;&lt;/guided-facet&gt; </code> </p> <p>您还可以通过使用gsname属性直接引用特定facet，在命名的 <span class="codeph"> guided-facet块的上下文之外使用 </span> 此条 <span class="codeph"><span class="varname"></span></span> 件。 </p> <p> <code class="syntax html"> &lt;guided-if-facet-long&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The&nbsp;category&nbsp;facet&nbsp;is&nbsp;very&nbsp;long! 
      &lt;/guided-if-facet-long&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-facet-selected [gsname="facetname"]&gt; 
      &lt;guided-else-facet-selected&gt;&lt;/guided-if-facet-selected&gt; </code> </p> </td> 
   <td colname="col2"> <p>当点击facet至少一次且当前已选择facet值时，此条件标签为true。 它可用于显示或隐藏HTML或gs标记，具体取决于是否单击了facet。 </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This&nbsp;facet&nbsp;has&nbsp;been&nbsp;selected.&nbsp;&nbsp;You&nbsp;can&nbsp;no&nbsp;longer&nbsp;refine&nbsp;it. 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-selected&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>您还可以通过使用gsname属性直接引用特定facet，在命名的 <span class="codeph"> guided-facet块的上下文之外使 </span> 用此 <span class="codeph"></span> 条件。 </p> <p> <code class="syntax html"> &lt;guided-if-facet-selected&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The&nbsp;category&nbsp;facet&nbsp;is&nbsp;selected! 
      &lt;/guided-if-facet-selected&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> <varname></varname> </p> </td> 
   <td colname="col2"> <p>当只有一个facet值时，此条件标记为true。 当它无法优化结果时，它可用于更改facet的显示。 </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-single&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Facet&nbsp;is&nbsp;not&nbsp;refinable. 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-single&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-single&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>您还可以通过使用gsname属性直接引用特定facet，在命名的 <span class="codeph"> guided-facet块的上下文之外使用 </span> 此条 <span class="codeph"><span class="varname"></span></span> 件。 </p> <p> <code class="syntax html"> &lt;guided-if-facet-single&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;There&nbsp;is&nbsp;only&nbsp;one&nbsp;value&nbsp;in&nbsp;the&nbsp;category&nbsp;facet! 
      &lt;/guided-if-facet-single&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> <varname></varname> </p> </td> 
   <td colname="col2"> <p>此条件允许您检查指定的facet是否具有任何值。 您可以使用它显示另一个facet而不是空的facet。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>20 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-total-count gsname=" <span class="varname"> facetname </span>"/&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出给定facet内的结果总数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>21 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value gsname=" <span class="varname"> associated custom facet value </span>" [escape="html|url|js|json|0"]/&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出与facet关联的值的字符串。 您可以有0个或多个与facet关联的字段。 具有关联字段很少见，因此您可以配置传输模板。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>22 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-facet-value gsname=" <span class="varname"> associated custom facet value </span>"/&gt;&lt;guided-else-facet-value&gt;&lt;/guided-if-facet-value&gt; </span> </p> </td> 
   <td colname="col2"> <p>测试facet值是否具有关联的字段值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>23 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-link [attr=" <span class="varname"> value </span>"]+&gt;&lt;/guided-facet-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>在facet值字符串周围创建一个链接，供客户单击。 将自动生成路径，以按当前facet值缩小结果范围。 它支持将任何属性直接传递到锚点标签。 </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&nbsp;class="facetlink"&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &lt;/guided-facet-values&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>24 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-path [escape="html|url|js|json|0"]/&gt; </span> </p> </td> 
   <td colname="col2"> <p>创建指向facet值的您自己的链接。 </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-lt/&gt;a&nbsp;href="&lt;guided-facet-value-path/&gt;"&lt;guided-gt/&gt;&lt;guided-facet-value/&gt;&lt;/a&gt; 
      &lt;/guided-facet-values&gt; </code> </p> <p>默认情况下，该值为URL转义。 但是，您可以通过指定要通过转义参数使用的转义模式，来添加另一层编码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>25 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-children&gt;&lt;/guided-facet-value-children&gt; </span> </p> </td> 
   <td colname="col2"> <p>当 <span class="codeph"> &lt;guided-facet-values&gt;遍历每 </span> 个facet值时，此标签会迭代嵌套facet的所有子值。 在此标记中，使用典型的facet标记创建链接、创建撤消链接和显示facet值。 此标签必须位于 <span class="codeph"> &lt;guided-facet-values&gt;中，因 </span> 为它确实嵌套循环。 </p> <p>使用此标记的示例如下： </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&lt;guided-facet-link&nbsp;title='&lt;guided-facet-value&nbsp;/&gt;'&gt;&lt;guided-facet-value&nbsp;/&gt;&nbsp;(&lt;guided-facet-count&nbsp;/&gt;)&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&lt;guided-if-facet-value-has-children&gt; 
      &nbsp;&nbsp;&nbsp;&lt;guided-facet-value-children&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&nbsp;title='&lt;guided-facet-value&nbsp;/&gt;'&gt;&lt;guided-facet-value&nbsp;/&gt;&nbsp;(&lt;guided-facet-count&nbsp;/&gt;)&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&lt;/guided-facet-value-children&gt; 
      &nbsp;&nbsp;&lt;/guided-if-facet-value-has-children&gt; 
      &lt;/guided-facet-values&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>26 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-facet-value-has-children&gt; 
      &lt;guided-else-facet- 
      value-has-children&gt; 
      &lt;/guided-if-facet-value-has-children&gt; </code> </p> </td> 
   <td colname="col2"> <p>测试当前facet值是否具有子值。 建议在使用 <span class="codeph"> &lt;guided-facet-value-children&gt;标签之前使 </span> 用。 “else”子句是可选的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>27 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;guided-else[-not]-facet-value-above-length-threshold&amp;gt;
    
    &amp;lt;/guided-if[-not]-facet-value-above-threshold&amp;gt;&lt;/code> &lt;/p> &lt;/td>
<td colname="col2"> <p>确定facet-values循环中的当前facet值是否高于长度阈值。 它通常仅用于在长facet上显示低于阈值的值（除非用户之前选择了facet下方显示的“查看更多”链接）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>28 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;guided-else[-not]-facet-value-equals-length-threshold&amp;gt;
    
    &amp;lt;/guided-if[-not]-facet-value-equals-threshold&amp;gt;&lt;/code> &lt;/p> &lt;/td>
<td colname="col2"> <p>确定facet-values循环中的当前facet值是否等于长度阈值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>29 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-undo-link&gt;&lt;/guided-facet-value-undo-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>显示给定选定facet值的撤消链接。 使用它可在选定facet值旁边显示撤消链接。 由于此撤消链接仅取消选择该特定的选定值，因此它与 <span class="codeph"> &lt;guided-facet-undo-link&gt;不同，后者取消选择 </span> 所有选定的值。 </p> <p> <p>注意： 如果facet没有多选行为，则两个撤消链接具有相同的行为。 即，facet只能有一个选定值。 </p> </p> <p>如果当前未选择facet，则链接是当前路径。 仅在向导facet-values循 <span class="codeph"> 环中使用此标 </span> 签。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>30 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-undo-path/&gt; </span> </p> </td> 
   <td colname="col2"> <p>创建您自己的facet值撤消链接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>31 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-undo-path gsname=" <span class="varname"> facetname </span>"/&gt; </span> </p> </td> 
   <td colname="col2"> <p>创建您自己的facet撤消链接。 </p> <p> 与 <span class="codeph"></span> &lt;guided-facet-undo-link&gt;标签类似，只是它为您提供了构建您自己的撤消链接的原始路径。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>32 </p> </td> 
   <td colname="col1"> <p> <varname></varname> </p> </td> 
   <td colname="col2"> <p>当给定facet具有选定值或单个值“value”时，有条件地显示HTML。 这组标签通常用于根据在另一个facet中选择的值显示facet。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>33 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-behavior gsname=" <span class="varname"> facetname </span>"/&gt; </span> </p> </td> 
   <td colname="col2"> <p>确定Facet的行为，如正常、粘滞或多选。 对于收到XML结果并希望根据facet的行为动态更改facet显示方式的客户来说，此功能非常有用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>34 </p> </td> 
   <td colname="col1"> <p> <varname></varname>

    &amp;lt;/guided-if-facet[-not]-visible&amp;gt;&lt;/code> &lt;/p> &lt;/td>
<td colname="col2"> <p>此标签所包裹的内容会根据facet的可见性状态进行隐藏或显示。 如果业务规则直接隐藏或显示facet，则facet内的任何内容将被隐藏或显示。 这些标记不必在facet周围绕排。 </p> <p> 此标记的一个常见用途是当名称位于facet之外时隐藏显示名称。 在显示名称周围包含此标记会在facet隐藏时使名称消失。 </p> <p>此标签替换了区域，并具有与使用区域相同的许多性能优势。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 痕迹导航 {#section_9B39B71FA6EC49FA8D88AD8A3BA987F7}

请参阅 [关于痕迹导航](../c-about-design-menu/c-about-breadcrumbs.md#concept_FB8A943C594A4A1593B118141DA61F03)。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-breadcrumb [gsname=" <span class="varname"> breadcrumbname </span>"]&gt;&lt;/guided-breadcrumb&gt; </span> </p> </td> 
   <td colname="col2"> <p>痕迹导航的循环标签。 在开始和结束标签之间的任何内容对于当前状态的每个查询编号被重复。 </p> <p>如果 <span class="codeph"> 忽略 <span class="varname"> gsname，则 </span></span> 使用名为“default”的痕迹导航。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-breadcrumb-link [gsname="goto|remove|drop"] [attr="value"]+&gt;&lt;/guided-breadcrumb-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>在痕迹导航中创建链接。 默认行为是“goto”行为。 如果链接的行为方式不同，请使 <span class="codeph"> 用gsname <span class="varname"> 可 </span></span> 选属性指定“remove”或“drop”。 标记中包含的任何属性都会传递到生成的锚点标记。 </p> <p> <code class="syntax html"> &lt;guided-breadcrumb&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-link&nbsp;gsname="remove"&nbsp;class="bc_link"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-value/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-breadcrumb-value /&gt; </span> </p> </td> 
   <td colname="col2"> <p>value标签将打印出当前痕迹导航小版本的转换值。 它仅在向导痕迹导航块的上 <span class="codeph"> 下文中使 </span> 用。 </p> <p> <code class="syntax html"> &lt;guided-breadcrumb&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-value/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-breadcrumb-label /&gt; </span> </p> </td> 
   <td colname="col2"> <p>标签标签输出痕迹导航值的标签，详细描述选择哪个facet以生成该痕迹导航项。 它仅用于向导痕迹导航块 <span class="codeph"> 的上下文 </span> 中。 </p> <p> <code class="syntax html"> &lt;guided-breadcrumb&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-label/&gt;:&nbsp;&lt;guided-breadcrumb-value/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to search-eng version, 2/1/2013--> <code> &lt;guided-if-breadcrumb-label&gt; 
      &lt;guided-else- 
      breadcrumb-label&gt; 
      &lt;guided-if-breadcrumb-label /&gt; </code> </p> </td> 
   <td colname="col2"> <p>如果当前痕迹导航值具有标签，则此条件标签用于有条件地显示内容。 它仅用于在标签实际存在时显示标签和相关内容。 它仅用于向导痕迹导航块 <span class="codeph"> 的上下文 </span> 中。 </p> <p> <code class="syntax html"> &lt;guided-breadcrumb&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-breadcrumb-label&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-label/&gt;: 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-breadcrumb-label&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-value/&gt;&lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-breadcrumb-path [gsname="goto|remove|drop"]/&gt; </span> </p> </td> 
   <td colname="col2"> <p>用于构建您自己的痕迹导航链接。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 菜单 {#section_1D489ADF041F4351A66E5D5742125CA8}

请参阅 [关于菜单](../c-about-design-menu/c-about-menus.md#concept_68123CE5CF4447B59217B5D721424E32)。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu gsname="menuname"&gt;&lt;/guided-menu&gt; </span> </p> </td> 
   <td colname="col2"> <p>这是菜单值循环迭代器标签。 使用 <span class="codeph"> gsname </span> 属性可标识显示的菜单项集。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-link [attr="value"]+&gt;&lt;/guided-menu-item-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>为您提供URL以优化当前对菜单项的搜索。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-option [attr="value"]+ /&gt; </span> </p> </td> 
   <td colname="col2"> <p>通常，菜单显示在模板上的选择控件中。 此标签使构建选择控件变得更简单，因为它生成用于为选择控件生成选项的HTML。 </p> <p>例如，以下代码块： </p> <p> <code class="syntax html"> &lt;select&nbsp;name="sort"&nbsp;onchange="gcGo(this);"&gt; 
      &lt;guided-menu&nbsp;gsname="sort"&gt; 
      &lt;guided-menu-item-option/&gt; 
      &lt;/guided-menu&gt; 
      &lt;/select&gt; </code> </p> <p>可以生成如下HTML: </p> <p> <code class="syntax html"> &lt;select&nbsp;name="sort"&nbsp;onchange="gcGo(this);"&gt; 
      &nbsp;&nbsp;&lt;option&nbsp;value="?sort=relevance;sp_sfvl_field=product-type|category|size;"&nbsp;selected="selected"&gt;Sort&nbsp;by&nbsp;Relevance&lt;/option&gt; 
      &nbsp;&nbsp;&lt;option&nbsp;value="?sort=avail-code;sp_sfvl_field=product-type|category|size;"&gt;Sort&nbsp;by&nbsp;Availability&lt;/option&gt; 
      &nbsp;&nbsp;&lt;option&nbsp;value="?sort=price;sp_sfvl_field=product-type|category|size;"&gt;Sort&nbsp;by&nbsp;Price&lt;/option&gt; 
      &lt;/select&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-value /&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回与菜单关联的值的字符串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-label /&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回与菜单关联的标签的字符串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-path /&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回路径字符串。 如果要向路径中添加参数并创建自定义链接，请使用标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if-menu-item-selected&gt; 
      &lt;guided-else-menu- 
      item-selected&gt; 
      &lt;/guided-if-menu-item-selected&gt; </code> </p> </td> 
   <td colname="col2"> <p>返回1或0，指示当前菜单项是否被选中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Pagenav {#section_2EE397635C514BBC8D668278EA314F35}

页面导航标记可用于构建一组链接，允许用户通过搜索结果进行页面浏览。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-pages&gt;&lt;/guided-pages&gt; </span> </p> </td> 
   <td colname="col2"> <p>页面导航的循环标签。 每个页面都会重复出现开始标记和结束标记之间的任何内容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-link [attr="value"]+&gt;&lt;/guided-page-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>在页面导航中创建链接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-link gsname="first|prev|next|last|viewall|viewpages" [attr="value"]+&gt;&lt;/guided-page-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>创建指向第一页、上一页、下一页或最后一页的链接。 它还可以创建一个链接，用于查看一个页面上的所有页面。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-number /&gt; </span> </p> </td> 
   <td colname="col2"> <p> 返回具有当前页码的字符串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if-page-selected&gt; 
      &lt;guided-else-page- 
      selected&gt; 
      &lt;/guided-if-page-selected&gt; </code> </p> </td> 
   <td colname="col2"> <p>如果选择了当前重复的页面，则这组条件标记为true。 它通常用于在页面导航控件中以不同的方式显示页码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-page-prev&gt; 
      &lt;guided-else-page- 
      prev&gt; 
      &lt;/guided-if[-not]-page-prev&gt; </code> </p> </td> 
   <td colname="col2"> <p> 如果当前页面有上一页，则此条件标记集为true。 它通常用于显示页面导航中的上一个链接（如果有意义）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-page-next&gt; 
      &lt;guided-else-page- 
      next&gt; 
      &lt;/guided-if[-not]-page-next&gt; </code> </p> </td> 
   <td colname="col2"> <p> 如果当前页面有下一页，则此条件标记集为true。 它通常用于显示页面导航中的上一个链接（如果有意义）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-page-viewall&gt; 
      &lt;guided-else-page- 
      viewall&gt; 
      &lt;/guided-if[-not]-page-viewall&gt; </code> </p> </td> 
   <td colname="col2"> <p> 当搜索返回大的结果集时，您可能不想提供查看所有结果的功能。 因此，您可以使用这组条件标签确定何时显示“查看全部”链接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-page-viewpages&gt; 
      &lt;guided-else-page- 
      viewpages&gt; 
      &lt;/guided-if[-not]-page-viewpages&gt; </code> </p> </td> 
   <td colname="col2"> <p>您可以使用这组条件标记确定何时显示“查看页面”链接。 它通常用于允许客户查看特定页面。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 

    &amp;lt;guided-else-page-link&amp;gt;
    &amp;lt;/guided-if[-not-page-link&amp;gt;&lt;/code> &lt;/p> &lt;/td>
<td colname="col2"> <p>测试页面导航是否包含第一页、上一页、下一页等。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-total /&gt; </span> </p> </td> 
   <td colname="col2"> <p> 返回一个包含搜索结果总页数的字符串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-pagination gsname= 
      "pagination_name"&gt;&lt;/guided-pagination&gt; </code> </p> </td> 
   <td colname="col2"> <p>使用引 <span class="codeph"> 导式分页标 </span> 签可定义一个区域，在该区域中，如果定义的页面导航设置很少，则所有分页标签都与特定分页设置相关。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> 

    next|last|viewwall|viewpages]/&amp;gt;&lt;/code> &lt;/p> &lt;/td>
<td colname="col2"> <p>在页面导航中创建您自己的链接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-page-high-eq-last&gt; 
      &lt;guided-else-page- 
      high-eq-last&gt; 
      &lt;/guided-if-page-high-eq-last&gt; </code> </p> </td> 
   <td colname="col2"> <p>测试页面导航中的最高页面是否等于页面总数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-page-low-eq-first&gt; 
      &lt;guided-else-page-low-eq-first&gt; &lt;/guided-if-page-low-eq-first&gt; </code> </p> </td> 
   <td colname="col2"> <p>测试页面导航中的最低页面是否等于该页面。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-page-is-multipage&gt; &lt;guided-else-page-is-multipage&gt; &lt;/guided-if-page-is-multipage&gt; </span> </p> </td> 
   <td colname="col2"> <p>测试是单页结果还是多页结果。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最近搜索 {#section_8CD907521F584257B475595B01A5964B}

您可以使用最近搜索标记构建一组链接，让用户快速运行以前的搜索，如下例所示：

```
<guided-if-recent-searches> 
    <span>Recent Searches</span><br/> 
    <guided-recent-searches> 
        <guided-recent-searches-link><guided-recent-searches-value></guided-recent-searches-link><br/> 
    </guided-recent-searches> 
    <guided-recent-searches-clear-link>Clear Recent Searches</guided-recent-searches-clear-link> 
</guided-if-recent-searches>
```

请参阅 [配置最近搜索](../c-about-design-menu/t-configuring-recent-searches.md#task_E9E8ACA04C90484F8AFD5262167B2562)。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches&gt;&lt;/guided-recent-searches&gt; </span> </p> </td> 
   <td colname="col2"> <p>最近搜索的循环标签。 每个页面都会重复出现开始标记和结束标记之间的任何内容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-recent-searches-link [attr="value"]+&gt; 
      &lt;/guided-recent-searches-link&gt; </code> </p> </td> 
   <td colname="col2"> <p>允许您构建指向最近搜索的链接。 它支持将任何HTML属性直接传递到锚点标签。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-path/&gt; </span> </p> </td> 
   <td colname="col2"> <p>允许您在引导式最近搜索循环中获取最近搜索的 <span class="codeph"> 相对URL路 </span> 径。 通常，您会 <span class="codeph"> 使用向导式最近搜索链接 </span>。 但是，如果您要构建自己的链接，可以使用此标签。 以下是一个示例： </p> <p> <code class="syntax html"> &lt;guided-lt/&gt;a&amp;nbsp;href="&lt;guided_recent_searches_path&gt;"&gt;&lt;guided-recent-searches-value&gt;&lt;/a&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-value&gt; </span> </p> </td> 
   <td colname="col2"> <p>允许您获取与最近搜索关联的查询词。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-clear-link [attr="value"]+&gt;&lt;/guided-recent-searches-clear-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>允许您为客户提供清除最近保存的搜索的功能。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-clear-path/&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回 <span class="codeph"> &lt;guided-recent-searches-clear-link&gt;所使用的路 </span> 径，以便您构建自己的链接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;/guided-if-recent-searches&amp;gt;&lt;/code> &lt;/p> &lt;/td>
<td colname="col2"> <p>允许您在客户执行最近搜索时显示最近搜索。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Did You Mean {#section_C1EB3B9D8E1242798A6E04609D1E3543}

当搜索未返回结果且搜索词不在帐户的词典中时，您可以使用“您是否是指”标记来构建指向建议的一组链接。 以下是使用Did You Mean标签的示例：

```
<guided-if-suggestions> 
    <span>Did You Mean?</span><br/> 
    <guided-suggestions> 
        <guided-suggestion-link><guided-suggestion/></guided-suggestion-link><br/> 
    </guided-suggestions> 
</guided-if-suggestions>
```

请参阅[关于 Did You Mean](../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E)。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matches search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-sembineds&gt;&lt;/guided-sembines&gt; </span> </p> </td> 
   <td colname="col2"> <p>这是用于循环查看建议的循环标签。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matches search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-seckuing-link [attr="value"]+&gt;&lt;/guided-seckuing-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>创建指向给定建议的链接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Newly added from search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-subcement-value /&gt; </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-suggestions&gt;&lt;guided-else[-not]- 
      suggestions&gt;&lt;/guided-if[-not]-suggestions&gt; </code> </p> </td> 
   <td colname="col2"> <p>允许您测试是否有任何建议。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-subcement-path/&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回建议的路径字符串。 您可以使用它构建自己的锚点标签。 通常， <span class="codeph"> 会改用向导建议 </span> 链接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-sucception/&gt; </span> </p> </td> 
   <td colname="col2"> <p>建议。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-subcement-result-count/&gt; </span> </p> </td> 
   <td colname="col2"> <p>建议的结果计数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-suggestion-autosearch&gt; 
      &lt;guided-else[-not]-suggestion-autosearch&gt; 
      &lt;/guided-if[-not]-suggestion-autosearch&gt; </code> </p> </td> 
   <td colname="col2"> <p>允许您测试是否执行了零结果的建议自动搜索，以防此功能开启。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-sequection-original-query/&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果执行了自动搜索，则返回原始查询。 </p> <p>使用示例： </p> <p> <code class="syntax html"> &lt;guided-if-suggestion-autosearch&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;Search&nbsp;for&nbsp;&lt;guided-query-param&nbsp;gsname="q"&nbsp;/&gt;&nbsp;instead&nbsp;of&nbsp;&lt;guided-suggestion-original-query&nbsp;/&gt; 
      &lt;/guided-if-suggestion-autosearch&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-suggestion-low-results&gt; 
      &lt;guided-else[-not]-suggestion-low-results&gt; 
      &lt;/guided-if[-not]-suggestion-low-results&gt; </code> </p> </td> 
   <td colname="col2"> <p>如果由于结果计数低而有建议，则此条件为true，以防此功能打开。 </p> <p>以下是使用此标记的示例： </p> <p> <code class="syntax html"> &lt;guided-if-suggestion-low-results&gt; 
      &nbsp;&nbsp;&nbsp;You&nbsp;have&nbsp;a&nbsp;low&nbsp;result&nbsp;count&nbsp;for&nbsp;&lt;guided-query-param&nbsp;gsname="q"&nbsp;/&gt;. 
      &nbsp;&nbsp;&nbsp;Did&nbsp;you&nbsp;mean:&nbsp;&lt;guided-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestion-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestion&nbsp;/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-suggestion-link&gt;&lt;guided-if-not-last&gt;,&nbsp;&lt;/guided-if-not-last&gt; 
      &nbsp;&nbsp;&nbsp;&lt;/guided-suggestions&gt; 
      &lt;/guided-if-suggestion-low-results&gt; </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 自动完成 {#section_897316BEE1454E839A56B565CA4AF018}

以下标记可用于向搜索表单添加自动完成功能。 头内容和表单内容标签是确保自动完成正常工作所必需的。 建议您使用标记，而不是将自动完成的Javascript和CSS硬编码到演示文稿模板中。 原因是，每当您更改自动完成设置时，标记都使您的模板能够拾取任何新的失败缓存ID，而无需手动更新模板。

请参 [阅关于自动完成](../c-about-auto-complete.md#concept_093A9CD754864BA79B456FE4BEB64578)。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-autocomplete&gt; &lt;guided-else-autocomplete&gt; &lt;/guided-if-autocomplete&gt; </span> </p> </td> 
   <td colname="col2"> <p>检测是否启用了自动完成功能。 您可以使用标记来选择自动完成所需的头部和表单内容。 这反过来又允许您打开和关闭功能，而不必更改演示文稿模板。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-ac-css/&gt; </span> </p> </td> 
   <td colname="col2"> <p>在演示文稿模板的头部中使用，并由相应的CSS脚本（包括）替换以实现自动完成。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-ac-form-content/&gt; </span> </p> </td> 
   <td colname="col2"> <p>在演示文稿模板的搜索表单(在 <span class="codeph"></span><span class="codeph"></span> &lt;form&gt;和&lt;/form&gt;标记之间)中使用，而不是硬编码表单中的自动完成标记。 标记将替换为完成自动完成工作所需的相应HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-ac-javascript/&gt; </span> </p> </td> 
   <td colname="col2"> <p>生成指向自动完成JavaScript的链接。 为获得最佳性能，建议将此标签放在页面底部附近的结束“body”标签之前。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Store {#section_A33E25DB5E67404A823BD9618665B773}

使用以下标记测试和显示用户当前所在的商店。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-store/&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出当前存储。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-store-defined&gt; &lt;guided-else-store-defined&gt; &lt;/guided-if-store-defined&gt; </span> </p> </td> 
   <td colname="col2"> <p>检测用户是否在商店中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-store gsname="store"&gt; &lt;guided-else-store&gt; &lt;/guided-if-store&gt; </span> </p> </td> 
   <td colname="col2"> <p>检测用户是否在商店中gsname参数指 <span class="codeph"> 定 </span> 的位置。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 区域 {#section_B9B3179E000C42D492E1541F2FE44CB5}

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-zone gsname="zone area" [search="associated search"] [facet="associated facet"] [width="xx" height="yy"]&gt; </span> </p> </td> 
   <td colname="col2"> <p>您可以将任何内容包含在区域标记中，以创建出该区域之外的区域。 这允许您使用业务规则根据需要显示区域。 默认情况下，始终显示区域。 您可以使用可选的搜索和facet参数来指示与区域关联的搜索或facet。 此类功能使软件在隐藏区域时可跳过搜索或彩块化，从而提高搜索时间性能。 高度和宽度属性是可选的，用于配置在删除区域时占位符在可视规则生成器中的显示方式。 </p> <p> 请尽 <span class="codeph"> 可能使用guided-if-facet[-not]-visible标 </span> 记，而不是区域。 它简化了演示文稿模板。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-zone gsname="zone area"&gt; &lt;guided-else-zone&gt; &lt;/guided-if-zone&gt; </span> </p> </td> 
   <td colname="col2"> <p>这组标记允许测试当前是否显示区域。 当您在页面上的其他位置有内容并且仅希望在显示区域时显示时，此功能很有用。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 循环指示器 {#section_387322CA0AA843A2ACF2795C328673E9}

您可以在以下任何循环块中使用以下每个循环指示符：

* 向导结果
* 向导化彩块化值
* 向导痕迹导航
* 向导菜单项
* 向导页面

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-first&gt;&lt;guided-else[-not]-first&gt; 
      &lt;/guided-if[-not]-first&gt; </code> </p> </td> 
   <td colname="col2"> <p>当当前迭代是循环的第一次迭代时，此条件为true。 这不一定表示第一个结果或第一个页面，但表示显示的第一个结果。 如果站点访问者位于每页10的结果集的第2页，则第一个小版本为结果11。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-last&gt;&lt;guided-else[-not]-last&gt; 
      &lt;/guided-if[-not]-last&gt; </code> </p> </td> 
   <td colname="col2"> <p>当当前迭代是循环的上次迭代时，此条件为true。 这并不一定意味着最后一个结果或最后一页，而是当前上下文（页面）中显示的最后一个结果。 如果站点访问者位于包含200个结果但每页仅有10个结果的结果集的第1页上，则最后一次迭代的结果是结果10而不是结果200。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-odd&gt;&lt;guided-else[-not]-odd&gt; 
      &lt;/guided-if[-not]-odd&gt; </code> </p> </td> 
   <td colname="col2"> <p>当当前迭代是循环的奇数迭代（与偶数迭代相比）时，此条件为true。 这对于显示不同的行颜色很有帮助。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-even&gt;&lt;guided-else[-not]-even&gt; 
      &lt;/guided-if[-not]-even&gt; </code> </p> </td> 
   <td colname="col2"> <p>当当前迭代是循环的偶数迭代（与奇数迭代相比）时，此条件为true。 这对于显示不同的行颜色很有帮助。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-alt&gt;&lt;guided-else[-not]-alt&gt; 
      &lt;/guided-if[-not]-alt&gt; </code> </p> </td> 
   <td colname="col2"> <p>当当前迭代是循环的偶数迭代时，此条件为true。 这对于显示不同的行颜色很有帮助。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-inner&gt;&lt;guided-else[-not]-inner&gt; 
      &lt;/guided-if[-not]-inner&gt; </code> </p> </td> 
   <td colname="col2"> <p>如果当前小版本既不是第一个小版本，也不是最后一个小版本，则包括它们之间的文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-outer&gt;&lt;guided-else[-not]-outer&gt; 
      &lt;/guided-if[-not]-outer&gt; </code> </p> </td> 
   <td colname="col2"> <p>如果当前小版本是第一个或最后一个小版本，则包括它们之间的文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-loop-index&gt; </span> </p> </td> 
   <td colname="col2"> <p>一个整数（从0开始），其值为循环的每次迭代递增。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-loop-counter&gt; </span> </p> </td> 
   <td colname="col2"> <p>一个整数（从1开始），其值为循环的每次迭代递增。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 其他语言 {#section_BFE8DC98E26F4D7BB60FEC54D9A5DC6C}

以下标记可用于使用模板执行更高级的操作，如构建您自己的微型彩块化。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng, 2/1/2013--> <span class="codeph"> &lt;guided-current-path [escape="html|url|js|json|0"] /&gt; </span> </p> </td> 
   <td colname="col2"> <p>为您提供使用的当前路径。 通常，它用于创建一个链接，该链接将新参数添加到现有搜索中。 默认情况下，路径为URL转义。 您可以通过转义参数指定要使用的转义模式。 </p> <p>示例： </p> <p> <code class="syntax html"> &lt;a&nbsp;href="&lt;guided-current-path&nbsp;/&gt;&amp;lang=fr"&gt; 
      French&nbsp;Version </code> </p> <p>在此示例中，搜索处理规则使用lang来选择法语版本。 </p> <p>当前路径始终至少具有一个查询参数。 如果不存在其他查询参数，则将其设置为 <span class="codeph"> q=* </span> ，以便更轻松地添加更多参数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> 基本路径 </span> </p> </td> 
   <td colname="col2"> <p> 如果要使用basepath创建链接，请在href的开头 <span class="codeph"> 使 </span> 用／并添加 <span class="codeph"> 参 </span> 数。 </p> <p> <code class="syntax html"> &lt;a&nbsp;href="/"&gt;All&nbsp;Products&lt;/a&gt; 
      Would&nbsp;create&nbsp;a&nbsp;link&nbsp;"All&nbsp;Products"&nbsp;to&nbsp;your 
      basepath,&nbsp;for&nbsp;example&nbsp;https://search.mycompany.com/ 
       </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng, 2/1/2013--> <span class="codeph"> &lt;guided-query-param gsname="query-parameter" [escape="html|url"] /&gt; </span> </p> </td> 
   <td colname="col2"> <p>允许您获取URL上查询参数的现有值。 如果参数不存在，则此标记返回空字符串。 如果不指定转义选项，则返回的字符串将自动转义为HTML转义，则可以指定HTML转义或URL转义。 </p> <p>示例： </p> <p> 

    &amp;lt; guided-query-param&amp;nbsp; gsname=&quot;q&quot;&amp; nbsp;
    gs&amp; nbsp; you&amp; nbsp; nbsp;value&amp;nbsp;lt;guided-query-param&amp;nbsp;gsname=&quot;lang&quot;&amp;nbsp;/nbsp;nbsp;nbsp;value&amp;nbsp;en
    
    &amp;lt;guided-query-param&amp;nbsp;gsname=&quot;test&quot;&amp;nbsp;/&amp;gt;
    gt&amp;nbsp;nap&amp;nbsp;an&amp;nbsp;nbsp；字符串
    
    &amp; nbsp;
    
    
    &amp; nbsp;&amp; nbsp;&amp; nbsp;&amp; nbsp;&amp;&amp; nbsp;&amp;&lt;/code> &lt;/p> &lt;/td>
</tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-query-param-name gsname="param#" offset="offset-number"/&gt; </span> </p> </td> 
   <td colname="col2"> <p>“向导式搜索”具有查询编号的概念，该编号用于痕迹导航控件中。 <span class="codeph"> “向导式搜索” </span> 允许您将参数定义为演示文稿模板中某个链接的一部分，在该链接中，“向导式搜索”会为您找出正确的查询编号。 gsname <span class="codeph"> 中 </span> 有一个“x”,“向导式搜索”将替换为正确的编号。 偏移值可以是0 - 15，其中0表示使用了下一个可用的查询编号。 1表示您要向其中添加1，依此类推。 </p> <p>与向 <span class="codeph"> 导式当前路径相结 </span>合，您可以构建自己的微型facet链接或允许额外的向下钻取级别。 </p> <p>示例： </p> <p> <code class="syntax html"> &lt;a&nbsp;href="&lt;guided-current-path 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;&amp;&lt;guided-query-param-name&nbsp;gsname="q#"&nbsp;offset="0" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=mens&amp;&lt;guided-query-param-name&nbsp;gsname="x#"&nbsp;offset="0" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=category"&nbsp;&gt;Category:Men&lt;/a&gt;&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </code> </p> <p> <code class="syntax html"> &lt;a&nbsp;href="&lt;guided-current-path 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;&amp;&lt;guided-query-param-name&nbsp;gsname="sp_q_exact_#"&nbsp;offset="0" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=mens&amp;&lt;guided-query-param-name&nbsp;gsname="sp_x_#"&nbsp;offset="0" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=category&amp;&lt;guided-query-param-name&nbsp;gsname="sp_q_exact_#"&nbsp;offset="1" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=Jeans&amp;&lt;guided-query-param-name&nbsp;gsname="sp_x_#"&nbsp;offset="1" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=product-type"&nbsp;&gt;Cat:Men&nbsp;-&nbsp;Product:Jeans&lt;/a&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-include gsfile="filename" /&gt; </span> </p> </td> 
   <td colname="col2"> <p> 允许您包括其他模板文件。 此功能意味着您可以使用子模板作为模块创建多个模板。 </p> <p>在以下示例中，包含痕迹 <span class="filepath"> 导航 </span> 和 <span class="filepath"> facet </span> 文件： </p> <p> <code class="syntax html"> &lt;guided-include&nbsp;gsfile='breadcrumbs.tmpl'&nbsp;/&gt; 
      &lt;guided-include&nbsp;gsfile='facets.tmpl'&nbsp;/&gt; </code> </p> <p>不支持动态包含。 换句话说， <span class="codeph"> gsfile不 </span> 能是变量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 1/17/2013--> <span class="codeph"> &lt;guided-search-time&gt; </span> </p> </td> 
   <td colname="col2"> <p> 标识搜索所花费的时间。 返回的搜索时间值以毫秒为单位指定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 1/17/2013--> <span class="codeph"> &lt;guided-fall-through-searches&gt; </span> </p> </td> 
   <td colname="col2"> <p> 返回用于构建搜索结果页面的核心搜索计数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 1/17/2013--> <span class="codeph"> &lt;guided-if-fall-through-search&gt;&lt;/guided-if-fall-through-search&gt; </span> </p> </td> 
   <td colname="col2"> <p>测试核心搜索的计数是否大于1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-even&gt;&lt;guided-else[-not]-even&gt; 
      &lt;/guided-if[-not]-even&gt; </code> </p> </td> 
   <td colname="col2"> <p>当当前迭代是循环的偶数迭代（与奇数迭代相比）时，此条件为true。 这对于显示不同的行颜色很有帮助。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-alt&gt;&lt;guided-else[-not]-alt&gt; 
      &lt;/guided-if[-not]-alt&gt; </code> </p> </td> 
   <td colname="col2"> <p>当当前迭代是循环的偶数迭代时，此条件为true。 这对于显示不同的行颜色很有帮助。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-inner&gt;&lt;guided-else[-not]-inner&gt; 
      &lt;/guided-if[-not]-inner&gt; </code> </p> </td> 
   <td colname="col2"> <p>如果当前小版本既不是第一个小版本，也不是最后一个小版本，则包括它们之间的文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-outer&gt;&lt;guided-else[-not]-outer&gt; 
      &lt;/guided-if[-not]-outer&gt; </code> </p> </td> 
   <td colname="col2"> <p>如果当前小版本是第一个或最后一个小版本，则包括它们之间的文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-first-search&gt;&lt;guided-else-first-search&gt; 
      &lt;/guided-if-first-search&gt; </code> </p> </td> 
   <td colname="col2"> <p>允许您检查是否在初始搜索中（查询是搜索框中的搜索结果）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-search-url/&gt; </span> </p> </td> 
   <td colname="col2"> <p>您可以在模板中使用此标记，以免硬编码搜索表单的操作。 它会检测您何时处于“暂存”或“实时”环境，并相应地进行更改。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-query-param-defined gsname="query_parameter"&gt; &lt;guided-else-query-param-defined&gt; &lt;/guided-if-query-param-defined&gt; </span> </p> </td> 
   <td colname="col2"> <p>这组标签允许您测试在搜索路径中定义的CGI参数。 只有在定义了参数的值时，才能测试这些参数的值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-next-query-number [gsname="offset"] /&gt; </span> </p> </td> 
   <td colname="col2"> <p>驱动模板的向导式搜索引擎的概念是浮动查询编号，该引擎生成的每个新链接都使用下一个可用的查询编号。 通过此标签，您可以获取下一个查询编号或偏移量，以便构建可深入到结果集中的自定义链接。 偏移允许您偏移到下一个查询编号。 例如，如果您选择了一个facet，则下一个查询编号为2，偏移量为1，则返回的查询编号为3。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-custom-var gsname="custom_variable" [escape="html|url|js|json|0"]/&gt; </span> </p> </td> 
   <td colname="col2"> <p>允许您获取处理规则定义的自定义变量的现有值。 如果不指定转义选项，则返回的字符串将自动转义为HTML转义，则可以指定 <span class="codeph"> html、 </span>url <span class="codeph"> 、js或 </span>0 <span class="codeph"></span><span class="codeph"></span>个转义。 如果您使用处理规则将传入的CGI参数复制到自定义变量，然后在模板中显示或使用该变量并将转义设置为none或js，那么您可以在搜索中创建XSS漏洞。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-custom-var-defined gsname="custom_variable"&gt; &lt;guided-else-custom-var-defined&gt; &lt;/guided-if-custom-var-defined&gt; </span> </p> </td> 
   <td colname="col2"> <p>在处理规则（查询清理、搜索前处理和搜索后处理）中定义自定义变量时启用测试。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-general-field gsname="searchname" field="fieldname" [escape="html|url|js|json|0"]/&gt; </span> </p> </td> 
   <td colname="col2"> <p>允许您显示传输模板中定义的常规字段的内容。 如果不指定转义选项，则返回的字符串将以您在该字段的传输模板中指定的格式进行编码。 指定转义选项适用于编码字段的任何格式（如传输模板中）。 您可以指定html、 <span class="codeph"> js、 </span>js、url <span class="codeph"> 、url </span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span>0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>20 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-general-field gsname="searchname" field="fieldname"&gt; &lt;guided-else-general-field&gt; &lt;/guided-if-general-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>启用测试（如传输模板中定义）是否存在常规字段的内容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>21 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-cookie-value gsname="cookie-name" [escape="html|url|js|json|0"]/&gt; </span> </p> </td> 
   <td colname="col2"> <p>允许您获取Cookie的值（假定Cookie可用）。 如果不指定转义选项，则返回的字符串将自动转义为HTML转义，您可以指定 <span class="codeph"> url、js </span>html、js <span class="codeph"> html或json </span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span>0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>22 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-cookie gsname="cookie_name"&gt; &lt;guided-else-cookie&gt; &lt;/guided-if-cookie&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果Cookie存在，则启用测试。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>23 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-banner gsname="banner area" [escape="html|url|js|json|0""] [width="xx" height="yy"]/&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出给定区域的横幅。 可视规则生成器中使用可选的宽度和高度属性，以显示有意义的占位符，以便用户选择横幅。 默认情况下，横幅不转义。 而是要将HTML插入演示文稿模板。 但是，如果要构建JSON模板，请考虑使用js转义选项。 </p> <p>示例： </p> <p> <code class="syntax html"> &lt;guided-banner&nbsp;gsname="top"&nbsp;width="400px" 
      &nbsp;height="50px"/&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>24 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-banner-set gsname="banner area"&gt; &lt;guided-else-banner-set&gt; &lt;/guided-if-banner-set&gt; </span> </p> </td> 
   <td colname="col2"> <p>在设置横幅区域时启用测试。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>25 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-simulator-mode&gt; &lt;guided-else-simulator-mode&gt; &lt;/guided-if-simulator-mode&gt; </span> </p> </td> 
   <td colname="col2"> <p>允许您检测在模拟器或可视规则生成器中查看搜索的时间。 它通常用于显示额外的调试信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>26 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-tnt-business-rules&gt; &lt;guided-else-tnt-business-rules&gt; &lt;/guided-if-tnt-business-rules&gt; </span> </p> </td> 
   <td colname="col2"> <p>允许您检测是否有任何引用 <span class="keyword"> Adobe Target营销活动的业务 </span> 规则。 它通常用作与 <span class="keyword"> Adobe Target集成的一部分， </span> 以防止在不需要时 <span class="keyword"> 触 </span> 及Target服务器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>27 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-redirect/&gt; </span> </p> </td> 
   <td colname="col2"> <p>默认情况下，会自动执行重定向。 但是，如果您已配置站点搜索／销售以将XML或JSON响应返回给Web应用程序，则可以选择在Web应用程序中解析302/301响应，或将重定向作为结果集的一部分传递给您。 如果您作为结果集的一部分传递重定向，则此标记可在模板中用于输出重定向位置。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>28 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-redirect&gt; &lt;guided-else-redirect&gt; &lt;/guided-if-redirect&gt; </span> </p> </td> 
   <td colname="col2"> <p>当您在结果集中配置了站点搜索／销售以返回重定向时，这组标记可用于确定是否存在指向输出的重定向。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>29 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-lt/&gt;&lt;guided-gt/&gt; </span> </p> </td> 
   <td colname="col2"> <p>这组标记允许您在HTML属性中嵌入引导式模板标记。 </p> <p>示例： </p> <p> <code class="syntax html"> &lt;guided-lt/&gt;div&nbsp;&lt;guided-if-facet-long&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;style="height:&nbsp;125px;&nbsp;overflow: 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;auto;"&lt;/guided-if-facet-long&gt;&lt;guided-gt/&gt; </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 传输模板标签 {#reference_227D199F5A7248049BE1D405C0584751}

传输模板是XML模板，可将数据从后端搜索传递到“向导式搜索”表示层。

<!-- 

r_transport_template_tags.xml

 -->

在表示层中，您可以有一个表示多个搜索结果的表示模板。 每个搜索都可以使用相同的传输模板或自定义传输模板将数据传递到表示层。

由于传输模板仅用于向表示层传递数据，因此它没有任何与显示搜索结果相关的HTML。 传输模板使用传输模板XML标记传递搜索结果以填充“向导式搜索”组件，如彩块化、痕迹导航和菜单。 在这些标记中，标准搜索模板标记用于显示实际值。

请参 [阅编辑演示文稿或传输模板](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3)。

请参阅 [搜索模板标记](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>传输模板标签 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-xml&gt;&lt;/guided-xml&gt; </span> </p> </td> 
   <td colname="col2"> <p>表示层用来检测从传输模板中解析的内容的根XML标签。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;general&gt;&lt;&lt;general&gt; </span> </p> </td> 
   <td colname="col2"> <p>搜索模板标记周围有标记，这些标记根据结果集提供摘要数据。 通常，这些标记包含搜索标记，用于搜索结果总数、较低结果和最高结果。 您可以使用常规字段标签定义任意数量的其 <span class="codeph"> 他全局字 </span> 段，如下例所示： </p> <p> <code class="syntax html"> &lt;general&gt; 
      &nbsp;&nbsp;&lt;total&gt;&lt;search-total&nbsp;/&gt;&lt;/total&gt; 
      &nbsp;&nbsp;&lt;lower&gt;&lt;search-lower&nbsp;/&gt;&lt;/lower&gt; 
      &nbsp;&nbsp;&lt;upper&gt;&lt;search-upper&nbsp;/&gt;&lt;/upper&gt; 
      &nbsp;&nbsp;&lt;general-field&nbsp;name="my_custom_field"&gt;Some&nbsp;global&nbsp;content&lt;/general-field&gt; 
      &lt;/general&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;results&gt;&lt;/results&gt; </span> </p> </td> 
   <td colname="col2"> <p>标记会围绕搜索结果进行包装，以便“向导式搜索”知道在哪里查找它们。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result&gt;&lt;/result&gt; </span> </p> </td> 
   <td colname="col2"> <p>标记会围绕每个搜索结果进行包装，这样“向导式搜索”就可以识别单个搜索结果的内容开始和结束的位置，如下例所示： </p> <code class="syntax html"> &lt;results&gt; 
     &nbsp;&nbsp;&lt;search-results&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;result&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;index&gt;&lt;search-index&nbsp;/&gt;&lt;/index&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;loc&gt;&lt;search-cdata&gt;&lt;search-url&nbsp;length="500"&nbsp;/&gt;&lt;/search-cdata&gt;&lt;/loc&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;/result&gt; 
     &nbsp;&nbsp;&lt;/search-results&gt; 
     &lt;/results&gt; </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;attribute-table name="tablename"&gt; </span> </p> </td> 
   <td colname="col2"> <p>允许您循环查看多值列表中的每个项目以获得单个结果。 仅在结果中使用此标记。 其目的是让您迭代属于结果字段的属性，如下例所示： </p> <code class="syntax html"> &lt;results&gt; 
     &nbsp;&nbsp;&lt;search-results&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;result&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;index&gt;&lt;search-index&nbsp;/&gt;&lt;/index&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;loc&gt;&lt;search-url&nbsp;/&gt;&lt;/loc&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;title&gt;&lt;search-title&nbsp;/&gt;&lt;/title&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;attribute-table&nbsp;name="downloads"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;field&nbsp;name="download_title"&gt;&lt;search-display-field&nbsp;name="download_title"&nbsp;/&gt;&lt;/field&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;field&nbsp;name="download_link"&nbsp;delimiter="|"&gt;&lt;search-display-field&nbsp;name="download_link"&nbsp;/&gt;&lt;/field&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/attribute-table&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;/result&gt; 
     &nbsp;&nbsp;&lt;/search-results&gt; 
     &lt;/results&gt; </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facets&gt;&lt;/facets&gt; </span> </p> </td> 
   <td colname="col2"> <p>传递填充彩块化的结果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <!--NEW 2/27/2014--> <span class="codeph"> &lt;dynamic-facet&gt;&lt;/dynamic-facet&gt; </span> </p> </td> 
   <td colname="col2"> <p> 可以将facet指定为动态facet和facet边栏的成员。 但是，他们的处理方式与相关的演示模板标签是独立的。 </p> <p>换句话说，不允许在动态facet循环上下文中嵌套facet边栏循环上下文，反之亦然。 </p> <p>对于动态和有栏的彩块化，只有为给定搜索返回的彩块化动态彩块化才会显示在彩块化循环上下文中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet name="name"&gt;&lt;/facet&gt; </span> </p> </td> 
   <td colname="col2"> <p> 每个facet都有其自己的facet标签，其中name参数与facet名称匹配。 搜索标记在facet值的facet标记中使用，如下例所示： </p> <code class="syntax html"> &lt;facets&gt; 
     &nbsp;&nbsp;&lt;facet&nbsp;name="brand"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
     &nbsp;&nbsp;&lt;/facet&gt; 
     &nbsp;&nbsp;&lt;facet&nbsp;name="category"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
     &nbsp;&nbsp;&lt;/facet&gt; 
     &lt;/facets&gt; </code> <p> 使用时隙facet的帐户可以使用动态标记和显示名称标记。 这两个标签有助于在创建业务规则时在时隙彩块化和实际彩块化之间进行映射。 </p> <code class="syntax html"> &lt;facets&gt; 
     &nbsp;&nbsp;&lt;facet&nbsp;name="facet_values01"&gt; 
     &nbsp;&lt;dynamic&gt;1&lt;/dynamic&gt; 
     &nbsp;&lt;display-names&gt;&lt;search-field-value-list&nbsp;name="facet_names01"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/display-names&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="facet_values01"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="facet_values01"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
     &nbsp;&nbsp;&lt;/facet&gt; </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field separator=","&gt; </span> </p> </td> 
   <td colname="col2"> <p>分隔符 <span class="codeph"> 属 </span> 性允许您更改在输出列表的搜索显示字段数据时使用的分隔符。 默认值是逗号。 </p> <p>通常，您使用的分隔符应该是字段内容中不易出现的分隔符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;建议&gt;&lt;建议&gt; </span> </p> </td> 
   <td colname="col2"> <p> 将您的“您的意思”建议用标记包装，以便“向导式搜索”可识别哪些XML节点包含建议。 </p> <p>请参阅<a href="../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E" type="concept" format="dita" scope="local">关于 Did You Mean</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;建议&gt;&lt;/建议&gt; </span> </p> </td> 
   <td colname="col2"> <p>将每个“您的意思”建议用标记括起来，如下例所示： </p> <code class="syntax html"> &lt;search-if-suggestions&gt; 
     &nbsp;&nbsp;&lt;suggestions&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;search-suggestions&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;suggestion&gt;&lt;search-suggestion-text&nbsp;/&gt;&lt;/suggestion&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-suggestions&gt; 
     &nbsp;&nbsp;&lt;/suggestions&gt; 
     &lt;/search-if-suggestions&gt; </code> <p>请参阅<a href="../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E" type="concept" format="dita" scope="local">关于 Did You Mean</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 搜索模板标记 {#reference_F7AA3FF602314E42842BBC740D2CA1A4}

搜索模板是包含站点搜索／销售定义的模板标记的HTML文件。 这些标记指示搜索结果的格式。 以下参考内容包含每个搜索模板标记及其属性的简短说明。

<!-- 

r_search_template_tags.xml

 -->

>[!NOTE]
>
>仅在传输模板文件(.tpl)中使用搜索模板标记。

您可以从以下搜索模板标签组和参考材料中进行选择。

仅在结果循环中有效的标记包括：

* [关于结果循环标签](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629)
* [结果循环字符串标签](../c-appendices/c-templates.md#section_80D68334E8D04A33937A6E58ABAAA320)
* [结果循环条件标签](../c-appendices/c-templates.md#section_35C367969E384A06A9865E388F1F9360)
* [结果循环锚点链接标签](../c-appendices/c-templates.md#section_C5FAEF520E9E42ADAD1F90651922AA02)
* [循环位置条件标签](../c-appendices/c-templates.md#section_E0C29DDA09E043C9A396F36334F05EBB)

在整个模板中有效的标记包括：

* [字段值列表标记](../c-appendices/c-templates.md#section_D3298B5F976447DBA0032B883DCC91B1)
* [字段值列表循环标记](../c-appendices/c-templates.md#section_0717FA09F0FC449CB916883B0500A60E)
* [建议标记](../c-appendices/c-templates.md#section_C28EB8B4F7DC4E278A0F143BCFEEB1AC)
* [模板字符串标签](../c-appendices/c-templates.md#section_67E3D529661F4F03A1FF469D9D658CAF)
* [模板锚点链接标记](../c-appendices/c-templates.md#section_3A51D27616C541E2B818CC52B2B856BA)
* [模板条件标记](../c-appendices/c-templates.md#section_18D9BC66DE484881932FD2F7EA9D170D)
* [模板表单控件标记](../c-appendices/c-templates.md#section_45AFC414ACA74825B72FEAA8456F8DD2)

搜索模板参考主题

* [日期格式字符串](../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4)
* [语言标识符](../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911)
* [指定内容类型HTTP头](../c-appendices/c-templates.md#section_AEED823E9938448A9EDB2F286D9CFD90)
* [在HTML模板中指定字符集](../c-appendices/c-templates.md#section_E0D1816ABB5846BEBE9C26D5980CCBE6)
* [在XML模板中指定字符集](../c-appendices/c-templates.md#section_17DC31CDCC104F5F8081466B41A96E9D)
* [在其他模板中包括搜索模板](../c-appendices/c-templates.md#section_7D1FCD3D9E2340C291E354C9720E8BC0)

## 关于结果循环标签 {#section_D4DC7B4560144663972E8DBC3369C629}

结果循环标签是模板系统的主要功能。 在搜索过程中遇到标记时，HTML会重复出现，而开始和结束结果循环标记之间会有其他标记，用搜索结果替换任何其他标记。

`<search-results> ... </search-results>`

显示搜索结果的HTML周围有结果循环标签。 标记之间的HTML会针对每个结果重复，并显示在页面上。

以下标记仅在结果循环中有效：

* [结果循环字符串标签](../c-appendices/c-templates.md#section_80D68334E8D04A33937A6E58ABAAA320)
* [结果循环条件标签](../c-appendices/c-templates.md#section_35C367969E384A06A9865E388F1F9360)
* [结果循环锚点链接标签](../c-appendices/c-templates.md#section_C5FAEF520E9E42ADAD1F90651922AA02)
* [循环位置条件标签](../c-appendices/c-templates.md#section_E0C29DDA09E043C9A396F36334F05EBB)

## 结果循环字符串标签 {#section_80D68334E8D04A33937A6E58ABAAA320}

以下标签返回一个字符串。

请参阅 [关于结果循环标签](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629)。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-index&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回当前结果的数值索引。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-title length="XX"&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回当前结果的页面标题。 可选的length属性用于限制显示的字符串长度，默认值为80个字符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-bodytext length="XX" encoding="html/javascript/json/perl/url/none" &gt; </span> </p> </td> 
   <td colname="col2"> <p>返回从页面顶部开始的正文文本。 相关术语以粗体显示。 可选的length属性用于限制显示的字符串长度，默认值为80个字符。 编码属性是可选的，它可以使用HTML编码（默认）、Javascript编码、Perl编码或无编码对输出字符进行编码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-description length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p> 返回当前结果的说明。 如果元描述标签存在且内容属性不为空，则显示该文本。 否则，将显示页面正文文本的开头。 可选的length属性用于限制显示的字符串长度，默认值为80个字符。 </p> <p>可选的 <span class="codeph"> 编码属 </span> 性控制输出是否为HTML编码、JavaScript编码、Perl编码、URL编码或未编码，以在结果页上输出。 编码的默认 <span class="codeph"> 值为 </span><span class="codeph"> html </span>。 通常，您无需指定编码属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-score rank="dynamic/static/dynamic-raw/static-raw/final-raw" precision="XX"&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回当前结果的得分，该得分是数字0 - 100。 如果已在“选项” <span class="uicontrol"> &gt; </span> “元数据” <span class="uicontrol"> &gt; </span> “定义”下定义了排名字段，则可以通过将排名属性设置为动态( <span class="uicontrol"></span><span class="codeph"></span>&lt;search-score rank="dynamic"&gt;)来显示动态页面排名。 通过将rank属性设置为static( <span class="codeph"> &lt;search-score rank="static"&gt; </span>)，可显示静态页面排名。 您可以使用可选的precision属性指定要显示的小数位数。 默认值为0，显示整数得分)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-date length="XX" none="text" date-format="date-format-string" gmt="yes/no" language="0/2/language-id"&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回当前结果的日期。 如果没有与当前结果关联的日期，则显示可选的“无”文本值。 如果未提供可选的“无”值，则如果没有与当前结果关联的日期，则显示文本“无日期”。 </p> <p>“date-format”属性采用UNIX样式的日期格式字符串，如“%A, %B %d, %Y”（对于“2016年7月25日，星期一”）。 “gmt”默认为“yes”，并控制日期字符串的时间部分应以GMT(“yes”)输出还是以帐户的时区(“no”)输出。 </p> <p>“语言”属性控制输出日期字符串的语言和区域设置约定。 “0”（默认）表示“使用帐户语言”。 “2”指“使用文档语言”。 “语言”值“1”保留供将来使用。 任何其他“语言”值被解释为特定语言标识符，例如，“en_US”表示“英语（美国）”。 </p> <p>可选的length属性用于限制显示的字符串长度，默认值为80个字符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-size&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回当前结果的大小（以字节为单位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-url length="XX" encoding="html/javascript/json/perl/url/none" &gt; </span> </p> </td> 
   <td colname="col2"> <p>返回当前结果的URL。 </p> <p>使用可选 <span class="codeph"> 的长度 </span> 属性限制显示的字符串长度，默认字符数不限。 </p> <p>编码 <span class="codeph"> 属 </span> 性是可选的，它可以使用HTML编码、Javascript编码、Perl编码或无编码对输出字符进行编码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-url-path-query length="XX"&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回路径和查询部分，包括当前结果URL的问号。 </p> <p>使用可选 <span class="codeph"> 的长度 </span> 属性限制显示的字符串长度，默认字符数不限。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-context length="XX" encoding="html/javascript/json/perl/url/none" &gt; </span> </p> </td> 
   <td colname="col2"> <p>返回搜索词的下一行上下文。 相关术语以粗体显示。 重复调用此标记可显示当前结果的多个上下文行。 </p> <p>使用可选 <span class="codeph"> 的length </span> 属性限制显示的字符串长度，默认值为80个字符。 如果 <span class="codeph"> 此标签由包含长度属性的 </span> &lt;search-if-context&gt;或 <span class="codeph"></span><span class="codeph"></span> &lt;search-if-any-context&gt;标签集包围，则忽略长度属性。 </p> <p>编码 <span class="codeph"> 属 </span> 性是可选的，它可以使用HTML编码（默认）、Javascript编码、Perl编码或无编码对输出字符进行编码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field name="field-name" length="XX" none="text" date-format="date-format-string" gmt="yes/no" language="0/2/language-id" encoding="html/json/perl/none" quotes="yes/no" units=" miles/kres/kris=" </span> </p> </td> 
   <td colname="col2"> <p>此高级标签显示在名称属性中为当前结果指定的元数据字段(url、标题、desc、键、目标、正文、alt、日期、字符集和在“选项” <span class="uicontrol"> &gt; </span> Metadata <span class="uicontrol"> &gt; “定义”下定义的语言或字段)的内 </span><span class="codeph"></span> 容。 例如： </p> <p> <span class="codeph"> &lt;search-display-field name="title" length="70" none="no title"&gt; </span> </p> <p>输出页面标题以获得搜索结果。 如果指定了 <span class="codeph"> 可选 </span> 的none属性，则只有在没有与字段关联的内容时，其值才会显示在结果页面上。 </p> <p>仅当 <span class="codeph"> 指定字段的内容类型为date-format时， </span>日期、gmt和语言 <span class="codeph"> 属性才 </span><span class="codeph"></span><span class="codeph"></span>相关。 </p> <p>date- <span class="codeph"> format属性采用UNIX样式的日期格式字符串，如 </span> %A、%B %d、%Y <span class="codeph"></span> （对于2016年7月25日星期一）。 <span class="codeph"> gmt默 </span> 认为 <span class="codeph"> yes, </span> 并控制日期字符串的时间部分是以GMT（是）输出还是以帐户的时区( <span class="codeph"> 否 </span><span class="codeph"></span>)输出。 </p> <p>请参阅 <a href="../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4" type="section" format="dita" scope="local"> 日期格式字符串</a>。 </p> <p>语言 <span class="codeph"> 属 </span> 性控制输出日期字符串的语言和区域设置约定。 <span class="codeph"> 0 </span> （默认）表示“使用帐户语言”。 <span class="codeph"> 2表 </span> 示“使用文档语言”。 语 <span class="codeph"> 言值1 </span> 保留 <span class="codeph"> 以供将 </span> 来使用)。 任何其 <span class="codeph"> 他语 </span> 言值被解释为特定语言标识符，例如， <span class="codeph"> en_US </span> 表示“英语（美国）”。 </p> <p>请参阅 <a href="../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911" type="section" format="dita" scope="local"> 语言标识符</a>。 </p> <p>可选的 <span class="codeph"> length属 </span> 性用于限制显示的字符串长度，默认值为80个字符。 </p> <p>可选的 <span class="codeph"> 编码属 </span> 性控制输出是否为HTML编码、JavaScript编码、Perl编码、URL编码或未编码，以在结果页上输出。 编码的默认 <span class="codeph"> 值为 </span><span class="codeph"> html </span>。 通常，您无需指定编码属性。 </p> <p>可选的 <span class="codeph"> 引号 </span> 属性控制各个项目输出是否被双引号(或者，如果 <span class="codeph"> encoding=perl，则单引号 </span>)包围。 引号的默 <span class="codeph"> 认值 </span> 是 <span class="codeph"> 否 </span>。 </p> <p>可选的逗 <span class="codeph"> 号属 </span> 性控制各个项目的输出是否以逗号分隔。 逗号的默 <span class="codeph"> 认 </span> 值 <span class="codeph"> 是 </span>。 非列 <span class="codeph"> 表类 </span> 型字段的逗号属性会被忽略。 </p> <p>可选单 <span class="codeph"> 位属 </span> 性控制应用于邻近搜索输出字段的距离单位。 单位的默认值 <span class="codeph"> 由与给 </span> 定邻近搜索输出字段关联的位置类型字段的“默认单位”设置确定。 </p> <p>请参 <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> 阅关于邻近搜索</a>。 </p> <p>可选的 <span class="codeph"> 分隔符 </span> 属性定义在列表类型字段的输出值之间插入的单个字符或分隔符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-values name="field-name"&gt;...&lt;search-display-field-values&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签创建一个循环，用于为当前结果枚举元数据字段值(url、标题、desc、键、目标、正文、alt、日期、字符集和在“选项” <span class="uicontrol"> &gt; “元数据” </span> &gt; <span class="uicontrol"> Definitions”（定义）下定义的语言或字段 </span><span class="uicontrol"></span>)。 请勿将此标记嵌套在另一 <span class="codeph"> 个&lt;search-display-field-values&gt;标记 </span> 中。 name属 <span class="codeph"> 性 </span> 指定包含要枚举的值的字段的名称。 对于选中了“允许列表”属性的字段，此标记最 <span class="uicontrol"> 有用(在“选项” </span> &gt; <span class="uicontrol"> &gt; </span><span class="uicontrol"></span><span class="uicontrol"></span>“元数据定义”下)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-value date-format="date-format-string" gmt="yes/no" language="0/language-id" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签输出当前 <span class="uicontrol"> &lt;search-display-field-values&gt;循环迭代的元数据字段值(url、title、desc、keys、target、body、alt、date、charset和在“选项” </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"></span><span class="codeph"></span> Definitions”下定义的语言或字段)。 此标记仅在 <span class="codeph"> &lt;search-display-field-values&gt;循环中有 </span> 效。 仅当 <span class="codeph"> 在封闭的&lt;search-display-values </span>&lt;search-field-values&gt;字段中指定的名称的内容类型是日期、格林尼治格式和语言属性 <span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span>时，date-format和语言属性才相关。 日 <span class="codeph"> 期属性采 </span> 用UNIX样式日期格式字符串，如 <span class="codeph"> "%A, </span>%B <span class="codeph"> %Unix格式，%B </span><span class="codeph"></span><span class="codeph"></span>%Unix格式"（2016年7月25日星期一）。 默认 <span class="codeph"> 为 </span> yes属性，并 <span class="codeph"> 控制日期字符串的时间部分是以GMT( </span> yes <span class="codeph"> )输出还是以帐户的时区( </span><span class="codeph"></span>no)输出。 </p> <p>语言 <span class="codeph"> 属 </span> 性控制输出日期字符串的语言和区域设置约定。 <span class="codeph"> 0 </span> （默认）表示“使用帐户语言”。 任何其 <span class="codeph"> 他语 </span> 言值被解释为特定语言标识符，例如， <span class="codeph"> en_US </span> 表示“英语（美国）”。 </p> <p>可选的 <span class="codeph"> 编码属 </span> 性控制输出是否为HTML编码、JavaScript编码、Perl编码、URL编码或未编码，以在结果页上输出。 编码的默认 <span class="codeph"> 值为 </span><span class="codeph"> html </span>。 通常，您无需指定编码属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-value-count name="field-name"&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出在使用name属性指定的元数据字段(url、标题、desc、键、目标、正文、alt、日期、字符集和语言或字段，这些字段在“选项” <span class="uicontrol"> &gt; </span> Metadata <span class="uicontrol"> &gt; </span> Definitions <span class="uicontrol"></span>)下定义的当前结果中的总值。 此标签可显示在结果循环中的任意位置。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-value-counter&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出当前&lt;search-display-field-values&gt;循环迭代的序数计数器（1、2、3等） <span class="codeph"></span> 。 此标记仅在 <span class="codeph"> &lt;search-display-field-values&gt;循环中有 </span> 效。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-dynamic-facet-fields&gt; </span> </p> </td> 
   <td colname="col2"> <p>开始为此搜索返回的任何动态彩块化字段循环上下文。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-dynamic-facet-field-name&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出此循环迭代的当前dynamic-facet-field的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release on October 30 2014--> <span class="codeph"> &lt;search-result-trace encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出与当前结果的放置相关的信息，例如影响结果位置的任何基于结果的操作。 </p> <p>此标记的输出格式为JSON，如以下示例所示： </p> <p> <code> { 
      &nbsp;&nbsp;"sliceID":&nbsp;5, 
      &nbsp;&nbsp;"indexID":&nbsp;5894, 
      &nbsp;&nbsp;"finalScore":&nbsp;98.5, 
      &nbsp;&nbsp;"dynamicScore":&nbsp;15.3, 
      &nbsp;&nbsp;"staticScore":&nbsp;55.456, 
      &nbsp;&nbsp;"position":&nbsp;1, 
      &nbsp;&nbsp;"rbtaActionListID":&nbsp;117, 
      &nbsp;&nbsp;"rbtaActionID":&nbsp;57 
      } </code> </p> 
    <!--<p> Results added to the results set by way of <codeph>rbta</codeph> have a "naturalPosition" value of -1. </p>--> <p>编码 <span class="codeph"> 属性 </span> 是可选的；默认值是 <span class="codeph"> html </span>。 </p> <p> <p>注意： 仅当使用核心搜索查询参 <span class="codeph"> 数指定了sp_trace=1 </span> 时，此标记才具有输出。 </p> </p> <p>请参阅后端搜索CGI参数中 <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" format="dita" scope="local"> 的表中的第48行</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 结果循环条件标签 {#section_35C367969E384A06A9865E388F1F9360}

以下标记有条件地包括它们之间的HTML。

请参阅 [关于结果循环标签](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629)。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-title&gt; ...&lt;/search-if-title&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-title&gt; ...&lt;/search-if-not-title&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果下次调用 <span class="codeph"></span> &lt;search-title&gt;时从文档标题返回（或不返回）文本，则这些标签将包括它们之间的HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-description length="XX"&gt; .../search-if-description&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-description&gt; ...&lt;/search-if-not-description&gt; </span> </p> </td> 
   <td colname="col2"> <p> 如果对 <span class="codeph"></span> &lt;search-description&gt;的下一次调用从文档描述返回（或不返回）文本，则这些标记包括它们之间的HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-bodytext&gt; ...&lt;/search-if-bodytext&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-bodytext&gt; ...&lt;/search-if-not-bodytext&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果对 <span class="codeph"></span> &lt;search-bodytext&gt;的下一次调用从文档正文返回（或不返回）文本，则这些标签包括它们之间的HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-context length="XX"&gt; ...&lt;/search-if-context&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-context&gt; ...&lt;/search-if-not-context&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果下次调用 <span class="codeph"> &lt;search-context&gt;返回（或不返回）非空上下文字符串，则这些标 </span> 记包括它们之间的HTML。 length属性将覆盖任何封闭的 <span class="codeph"> &lt;search-context&gt;标签上的length属 </span> 性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-any-context length="XX"&gt; .../search-if-any-context&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-any-context&gt; ...&lt;/search-if-not-any-context&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果存在（或不存在）与结果关联的上下文字符串，则这些标记包括它们之间的HTML。 length属性将覆盖任何封闭的 <span class="codeph"> &lt;search-context&gt;标签上的length属 </span> 性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-score lower="XX" upper="yy" rank="dynamic/static/dynamic-raw/static-raw/final-raw"&gt; ...&lt;/search-if-score&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-score lower=XX upper=yy rank="dynamic/static"&gt; ...&lt;/search-if-not-score&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果当前结果的得分在XX和YY之间（或不在），则这些标记包括它们之间的HTML。 对于添加项目符号或图形来显示结果的相关性很有用。 如果您在“选项” <span class="uicontrol"> &gt; </span> “元数据” <span class="uicontrol"> &gt; </span> Y下定义了排名类型字段，则可以通过将排名属性设置为“动态”( <span class="uicontrol"></span><span class="codeph"></span>&lt;search-if-score rank="dynamic" lower=XX upper=YY&gt;定义)来检查动态页面的排名。 您可以通过将rank属性设置为static( <span class="codeph"> &lt;search-if-score rank="static" lower=XX upper=YY&gt; </span>)来检查静态页面排名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-field name="field-name" value="value"&gt;...&lt;/search-if-field&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-field name="field-name" value="value"&gt;...&lt;/search-if-not-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>这些高级标记包括它们之间的HTML，具体取决于在“name”属性中指定的字段是否包含内容。 如果指定了可选的“value”属性，则根据给定值是否与当前结果中字段的值匹配（或不匹配），这些标记将包括它们之间的HTML。 这些标记仅在结果循环中(在 <span class="codeph"> &lt;search-results&gt;和 </span><span class="codeph"> &lt;/search-results&gt;标记之间) </span> 起作用。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 结果循环锚点链接标签 {#section_C5FAEF520E9E42ADAD1F90651922AA02}

请参阅 [关于结果循环标签](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629)。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-link target="frame-name" hbx-enable="yes/no" hbx-linkid-name="field-name" hbx-linkid-none="text" hbx-linkid-length="XX" &gt; ...&lt;/search-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>这对标签在它们之间围绕HTML创建锚点链接。 单击链接后，将显示结果页面。 可选的target属性指定了指定窗口，在该窗口中，支持帧的浏览器应显示结果页。 </p> <p>将hbx-enable属性设置为“是”，以利用通过HBX提供的分析。 将hbx-linkid-name设置为要跟踪的元数据字段的名称。 例如，要按SKU编号跟踪搜索结果，请将hbx-linkid-name设置为包含SKU信息的元数据字段的名称。 </p> <p>当前不支持日期类型字段。 hbx-linkid-name的值将附加到生成的锚点中的链接ID。 只要指定的元数据字段为空，hbx-linkid-none属性的值就会附加到链接ID。 hbx-linkid-length的值限制从Meta标签获取和显示的字符数。 默认字符数为12。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-smart-link target="frame-name" hbx-enable="yes/no" hbx-linkid-name="field-name" hbx-linkid-none="text" hbx-linkid-length="XX"&gt; ...&lt;/search-smart-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>这对标记与 <span class="codeph"> &lt;search-link&gt;类似……&lt;/search-link&gt;标 </span> 记。 单击生成的锚点链接时，将显示结果页，但该页滚动到结果之前最近的锚点标签。 对于PDF链接，Acrobat查看器显示包含结果的页面。 可选的target属性指定了指定窗口，在该窗口中，支持帧的浏览器应显示结果页。 </p> <p>将hbx-enable属性设置为“是”，以利用通过HBX提供的分析。 将hbx-linkid-name设置为要跟踪的元数据字段的名称。 例如，要按SKU编号跟踪搜索结果，请将hbx-linkid-name设置为包含SKU信息的元数据字段的名称。 </p> <p>当前不支持日期类型字段。 hbx-linkid-name的值将附加到生成的锚点中的链接ID。 只要指定的元数据字段为空，hbx-linkid-none属性的值就会附加到链接ID。 hbx-linkid-length的值限制从Meta标签获取和显示的字符数。 默认字符数为12。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-link-extension&gt;...&lt;/search-if-link-extension&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-link-extension&gt; ...&lt;/search-if-not-link-extension&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果value属性指定的扩展与结果的URL结尾相匹配，则这些标签包括它们之间的HTML。 此标签对于在基于链接扩展的搜索结果中包含图形很有用。 value属性是一个或多个扩展（空格分隔）的列表，如下所示：VALUE="。pdf"或VALUE="。html .htm"。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 循环位置条件标签 {#section_E0C29DDA09E043C9A396F36334F05EBB}

以下标记有条件地包括它们之间的文本。 它们只能显示在“循环”标记中：&lt; `search-results>` and `<search-field-values>`. 它们用于测试当前结果在结果集中的位置。

请参阅 [关于结果循环标签](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629)。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-first&gt;...&lt;/search-if-first&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-first&gt;...&lt;/search-if-not-first&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果当前结果是（或不是）页面上的第一个结果(在 <span class="codeph"> &lt;search-results&gt;中使用)或第一个字段值(在 </span>&lt;search-field-values&gt;中使用)，则这些标记包括它们之间的文本 <span class="codeph"></span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-last&gt;...&lt;/search-if-last&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-last&gt;...&lt;/search-if-not-last&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果当前结果是（或不是）页面上的最后一个结果(在 <span class="codeph"> &lt;search-results&gt;中使用)或最后一个字段值(在 </span>&lt;search-field-values&gt;中使用)，则这些标记包括它们之间的文本 <span class="codeph"></span>。 此标签可用于在结果之间插入分隔符。 例如，这会在结果之 <span class="codeph"> 间插入 </span> &lt;hr&gt;标签： </p> <p> <code class="syntax html"> &lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&lt;search-lt&gt;tr&lt;search-if-alt&gt;&nbsp;class="alt"&lt;/search-if-alt&gt;&lt;search-gt&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td&gt;&lt;search-url&gt;&lt;/td&gt; 
      &nbsp;&nbsp;&nbsp;&lt;/tr&gt; 
      &lt;/search-results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-inner&gt; ...&lt;/search-if-inner&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-inner&gt; ...&lt;/search-if-not-inner&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果当前结果不是页面上的第一个或最后一个结果(在 <span class="codeph"> &lt;search-results&gt;中使用)，或者不是第一个或最后一个字段值(在 </span>&lt;search-field-values&gt;中使用)，则这些标记包括它们之间的文本 <span class="codeph"></span>。 标签的not版本测试结果是第一个还是最后一个。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-alt&gt;...&lt;/search-if-alt&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-alt&gt; ...&lt;/search-if-not-alt&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果当前结果是（或不是）页面上的替代结果(在 <span class="codeph"> &lt;search-results&gt;中使用)或替代字段值(在 </span>&lt;search-field-values&gt;中使用)，则这些标记包括它们之间的文本 <span class="codeph"></span>。 “备用”结果为页面上的第二个、第四个、第六个，依此类推。 此示例将不同的类应用于替代表行。 请注意，使用 <span class="codeph"> &lt;search-lt&gt;和 </span><span class="codeph"> &lt;search-gt&gt; </span> 可允许将 <span class="codeph"> &lt;search-if-alt&gt;标记“放入” </span><span class="codeph"></span> &lt;tr&gt;标记内。 </p> <p> <code class="syntax html"> &nbsp;&nbsp;&nbsp;&nbsp;&lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-lt&gt;tr&lt;search-if-alt&gt;&nbsp;class="alt"&lt;/search-if-alt&gt;&lt;search-gt&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td&gt;&lt;search-url&gt;&lt;/td&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/tr&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-even&gt; ...&lt;/search-if-even&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-even&gt; ...&lt;/search-if-not-even&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果当前结果是（或不是）偶数编号的结果(在 <span class="codeph"> &lt;search-results&gt;中使用)或偶数字段值(在 </span>&lt;search-field-values&gt;中使用)，则这些标记包括它们之间的文本 <span class="codeph"></span>。 如果搜索结果的&lt;search-index&gt;值为偶数，则 <span class="codeph"> 搜索结果 </span> 的编号为偶数。 换句话说，如果它在整个结果集中的位置是均匀的。 这可能与 <span class="codeph"> &lt;search-if-alt&gt;不同，后者测试 </span> 页面上结果的位置，而不是整个结果集中的位置。 以下两个表说明了差异： </p> </td> 
  </tr> 
 </tbody> 
</table>

### 第一页， sp_n=1

<table>  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>索引 </p> </th> 
   <th colname="col2" class="entry"> <p>结果 </p> </th> 
   <th colname="col3" class="entry"> <p>扯平？ </p> </th> 
   <th colname="col4" class="entry"> <p>Alt? </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>第一个结果 </p> </td> 
   <td colname="col3"> <p>否 </p> </td> 
   <td colname="col4"> <p>否 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>第二个结果 </p> </td> 
   <td colname="col3"> <p>是 </p> </td> 
   <td colname="col4"> <p>是 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>第三个结果 </p> </td> 
   <td colname="col3"> <p>否 </p> </td> 
   <td colname="col4"> <p>否 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>第四个结果 </p> </td> 
   <td colname="col3"> <p>是 </p> </td> 
   <td colname="col4"> <p>是 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>第五个结果 </p> </td> 
   <td colname="col3"> <p>否 </p> </td> 
   <td colname="col4"> <p>否 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 稍后页， sp_n=10

<table>  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>索引 </p> </th> 
   <th colname="col2" class="entry"> <p>结果 </p> </th> 
   <th colname="col3" class="entry"> <p>扯平？ </p> </th> 
   <th colname="col4" class="entry"> <p>Alt? </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>10 </p> </td> 
   <td colname="col2"> <p>第十个结果 </p> </td> 
   <td colname="col3"> <p>是 </p> </td> 
   <td colname="col4"> <p>否 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>11 </p> </td> 
   <td colname="col2"> <p>第11个结果 </p> </td> 
   <td colname="col3"> <p>否 </p> </td> 
   <td colname="col4"> <p>是 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>12 </p> </td> 
   <td colname="col2"> <p>第十二个结果 </p> </td> 
   <td colname="col3"> <p>是 </p> </td> 
   <td colname="col4"> <p>否 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>13 </p> </td> 
   <td colname="col2"> <p>第十三个结果 </p> </td> 
   <td colname="col3"> <p>否 </p> </td> 
   <td colname="col4"> <p>是 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>14 </p> </td> 
   <td colname="col2"> <p>第十四个结果 </p> </td> 
   <td colname="col3"> <p>是 </p> </td> 
   <td colname="col4"> <p>否 </p> </td> 
  </tr> 
 </tbody> 
</table>

最后，请注意， `<search-if-even>` 由于字段值不分页， `<search-if-alt>` 因此始终与搜索字段值相同。

## 字段值列表标记 {#section_D3298B5F976447DBA0032B883DCC91B1}

以下高级标记输出字段值以及整个搜索结果集中的相关数据。 这些标签只针对搜索查询中的 `sp-sfvl-field` CGI参数指定的字段生成输出。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-list name="field-name" quotes="yes/no"逗号="yes/no" data="values/counts/results" separator="X" sortby="none/values/counts/results" max-items="XX" date-format="date-string" gmt="yes/no" langume=""" 0/nage-id"语言="""0/javascript"json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签显示整个结果集中唯一字段值、值计数或结果计数的列表。 </p> <p>此标签仅为搜索查询中的 <span class="codeph"> sp_sfvl_field </span> CGI参数指定的字段生成输出。 可选的“quotes”属性控制各个项目输出是否被双引号（或单引号，如果encoding=perl）所包围。 “quotes”的默认值是“yes”。 可选的“逗号”属性控制各个项目的输出是否以逗号分隔。 “逗号”的默认值为“是”。 可选的“data”属性控制是否输出每个唯一字段值(data="values")，输出每个唯一字段值的总计数(data="counts")，或输出包含每个唯一值的结果数(data="results")。 “data”的默认值是“values”。 对于非列表类型字段，data="counts"和data="results"是等同的。 separator属性定义要插入输出值之间的单个字符或分隔符。 可选的“sortby”属性控制输出的顺序；sortby="none"表示没有特定顺序，sortby="values"表示按字段值排序（根据字段的“排序”属性以升序或降序排序）,sortby="counts"表示按字段值计数的降序排序，sortby="results"表示按包含每个值的结果数的降序排序。 </p> <p>请注意，sortby="counts"和sortby="results"对于非列表类型字段是等效的。 可选的“max-items”属性限制了要输出的项目数。 “max-items”的默认值为-1，表示“输出所有项目”。 </p> <p>最大项目的绝对限制为100。 “date-format”、“gmt”和“language”属性仅在指定字段的内容类型为“date”时相关。 “date-format”属性采用UNIX样式的日期格式字符串，如“%A, %B %d, %Y”（对于“2016年7月25日，星期一”）。 “gmt”默认为“yes”，并控制日期字符串的时间部分应以GMT(“yes”)输出还是以帐户的时区(“no”)输出。 </p> <p>请参阅 <a href="../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4" type="section" format="dita" scope="local"> 日期格式字符串</a>。 </p> <p>“语言”属性控制输出日期字符串的语言和区域设置约定。 “0”（默认）表示“使用帐户语言”。 任何其他“语言”值被解释为特定语言标识符，例如，“en_US”表示“英语（美国）”。 可选的“encoding”属性控制输出字符串字符是否为HTML编码、JavaScript编码、Perl编码、URL编码或未编码，以在结果页上输出。 “encoding”的默认值是“html”。 </p> <p>请参阅 <a href="../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911" type="section" format="dita" scope="local"> 语言标识符</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-list-count name="field-name" value="field-value" results="yes/no"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标记显示给定搜索字段值列表的计数信息。 此标签有三种不同的用途。 如果仅提供“name”属性，则此标签将输出整个结果集中指定字段的唯一值数。 如果同时提供“name”和“value”属性，则此标记将输出整个结果集中给定值的总计数（对于results="no"），或输出包含整个结果集中给定值的结果的总计数（对于results="yes"）。 “results”的默认值为“no”。 注意：对于非列表类型字段，results="yes"和results="no"是等效的。 如果未提供“value”属性，则忽略“results”的值。 此标签仅为搜索查询中的sp-sfvl-field <span class="codeph"> CGI参数指定的字 </span> 段生成输出。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-field-value-list-count name="field-name" value="field-value"&gt;...&lt;/search-if-field-value-list-count&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-field-value-list-count name="field-name" value="field-value"&gt;...&lt;/search-if-not-field-value-list-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果具有给定属性的 <span class="codeph"></span> &lt;search-field-value-list-count name="field-name" value="field-value"&gt;的等效调用将（或不会）返回大于零的值，则这些标记将显示它们之间的HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-single-field-value-list-count name="field-name"&gt; ...&lt;/search-if-single-field-value-list-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果具有给定属性的 <span class="codeph"></span> &lt;search-field-value-list-count name="field-name" value="field-value"&gt;等效调用将（或不会）返回单个值，则这些标记会显示它们之间的内容。 这通常在帐户使用facet插槽时使用。 对于facet槽，您通常只希望在关联的名称槽具有单个项目时显示值槽。 在传输模板中执行此检查比在表示层中执行检查更有效。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 字段值列表循环标记 {#section_0717FA09F0FC449CB916883B0500A60E}

以下高级标签使用循环构造从整个搜索结果集中枚举和输出字段值以及相关数据。 这些标签只针对搜索查询中的 `sp-sfvl-field` CGI参数指定的字段生成输出。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-values name="field-name" sortby="none/values/counts/results" max-items="XX"&gt; ...&lt;/search-field-values&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签创建一个循环，用于枚举整个结果集中特定字段的字段值和相关数据。 请勿将此标记嵌套在另一个 <span class="codeph"> &lt;search-field-values&gt;标记 </span> 中。 “name”属性指定包含要枚举的值的字段的名称。 可选的“sortby”属性控制枚举顺序：“none”表示没有特定顺序，“values”表示按字段值排序（根据字段的“排序”属性以升序或降序排序）,sortby=“counts”表示按字段值计数的降序排序，sortby=“results”表示按包含每个值的结果数的降序排序。 </p> <p>请注意，sortby="counts"和sortby="results"对于非列表类型字段是等效的。. 可选的“max-items”属性将迭代次数限制为给定值。 “max-items”的默认值为-1，表示“枚举所有值”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value date-format="date-format-string" encoding="html/javascript/json/perl/url/none" gmt="yes/no" language="0/language-id"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签输出当前&lt;search-field-values&gt;循环迭代的字段值。 此标记仅在 <span class="codeph"> &lt;search-field-values&gt;循环中有 </span> 效。 仅当封闭&lt;search-field-values&gt;标签中指定的字段名称的内容类型为“date”时，“date-format”、“gmt”和“language”属性才相关。 “date-format”属性采用UNIX样式的日期格式字符串，如“%A, %B %d, %Y”（对于“2020年7月25日，星期一”）。 </p> <p>请参阅 <a href="../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4" type="section" format="dita" scope="local"> 日期格式字符串</a>。 </p> <p>可选的“encoding”属性控制输出字符串字符是否为HTML编码、JavaScript编码、Perl编码、URL编码或未编码，以在结果页上输出。 “encoding”的默认值为“none”。 通常，您无需指定编码属性。 “gmt”默认为“yes”，并控制日期字符串的时间部分应以GMT(“yes”)输出还是以帐户的时区(“no”)输出。 “语言”属性控制输出日期字符串的语言和区域设置约定。 “0”（默认）表示“使用帐户语言”。 任何其他“语言”值被解释为特定语言标识符，例如，“en_US”表示“英语（美国）”。 </p> <p>请参阅 <a href="../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911" type="section" format="dita" scope="local"> 语言标识符</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-count results="yes/no"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签输出与当前 <span class="codeph"> &lt;search-field-values&gt;循环迭代相关 </span> 的计数。 输出计数是包含字段值的整个结果集中的结果数(results="yes")，或整个结果集中字段值的总计数。 “results”的默认值为“no”。 </p> <p>对于非列表类型字段，results="yes"和results="no"是等效的。 此标记仅在 <span class="codeph"> &lt;search-field-values&gt;循环中有 </span> 效。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-counter&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签输出当前&lt;search-field-values&gt;循 <span class="codeph"> 环迭代的序数计 </span> 数器。 此标记仅在 <span class="codeph"> &lt;search-field-values&gt;循环中有 </span> 效。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 建议标记 {#section_C28EB8B4F7DC4E278A0F143BCFEEB1AC}

建议提供用户友好的“您是说？” 用于建议替代搜索词的服务。 例如，如果用户拼写错误了搜索词，“建议”可以通过建议正确的拼写帮助用户查找结果。 系统还可以建议相关关键字，帮助用户发现结果。 在生成建议时，建议服务使用两个词典：一个基于帐户语言(在 **[!UICONTROL Indexing]** > **[!UICONTROL Words and Languages]** > **[!UICONTROL Language]**)，另一个基于帐户索引中的关键字唯一构建。

>[!NOTE]
>
>建议服务不适用于中文、日文或韩文。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-sembineds&gt;...&lt;/search-if-sembineds&gt; </span> </p> </td> 
   <td colname="col2"> <p>在这些标记周围添加任何“建议”模板标记， <span class="codeph"> 如 </span>&lt;search-seckupting&gt; <span class="codeph"> 、&lt;search-seckupting-link&gt; </span>等。 如果搜索生成建议，则搜索引擎输出并处理打开标记和关闭标记之间的所有内容。 如果搜索不生成建议，则不会输出任何嵌套内容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-sembineds&gt; ...&lt;/search-sexcipseds&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签生成“建议”循环，该循环包含建议搜索词的列表（例如，“打算”、“预期”和“打算”，用于最初作为“意向”输入的查询）。 在生成术语列表时，搜索引擎最多重复5次任何嵌套的HTML和／或模板标记，这是建议的最大数目。 使用count属性指定生成的建议数(0-5)。 </p> <p>&lt;search- <span class="codeph"> seckfies&gt;标记可 </span> 以在页面上多次显示以重复建议列表。 根据每个结果的数量对多个建议进行排序。 </p> <p>在打开 <span class="codeph"> 和关闭&lt;search-if-seffices&gt;标记之 </span> 间嵌套&lt;search-secmendations&gt;标 <span class="codeph"></span> 记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-seckument-link&gt;...&lt;/search-seckument-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签使用选定的建议搜索词而不是原始词生成指向原始搜索查询的链接。 标签接受并只打印出任何HTML属性，如类、目标和样式。 标记还可以接受URL属性，其值用作生成链接的基本URL。 这些标记只能显示在 <span class="codeph"> &lt;search-sexpendications&gt;循环 </span> 中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-seckument-text/&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标记将打印出当前建议的查询术语（例如，“打算”是最初作为“意向”输入的查询）。 标记没有属性，只能显示在 <span class="codeph"> &lt;search-seckmendations&gt;循环中 </span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-not-sembines&gt; ...&lt;/search-if-not-sembilies&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果搜索不生成任何建议，则搜索引擎输出并处理打开标记和关闭标记之间的所有内容。 如果搜索生成建议，则不会输出任何嵌套内容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if[-not]-first-segmence&gt;...&lt;/search-if[-not-first-seccument]&gt; </span> </p> </td> 
   <td colname="col2"> <p>这些条件标记包括它们之间的HTML，具体取决于建议的术语是否是建议循环中的第一个术语。 标记必须显示在开始标记和结束标 <span class="codeph"> 记之间&lt;search-seccuption&gt; </span> 标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if[-not]-last-segmenced&gt;...&lt;/search-if[-not-last-accembing&gt; </span> </p> </td> 
   <td colname="col2"> <p>这些条件标记包括它们之间的HTML，具体取决于建议的术语是否是建议循环中的最后一个术语。 标记必须显示在开始标记和结束标 <span class="codeph"> 记之间&lt;search-seccuption&gt; </span> 标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-seccument-index&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签返回当前建议搜索词的数字索引。 标记必须显示在开始标记和结束标 <span class="codeph"> 记之间&lt;search-seccuption&gt; </span> 标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-seckument-total&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标记返回生成的建议搜索词的总数。 标记必须显示在开始标记和结束标 <span class="codeph"> 记之间&lt;search-seccuption&gt; </span> 标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-seckument-result-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标记返回建议搜索词的结果总数。 标记必须显示在开始标记和结束标 <span class="codeph"> 记之间&lt;search-seccuption&gt; </span> 标记。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 模板字符串标签 {#section_67E3D529661F4F03A1FF469D9D658CAF}

以下标签在模板中的该点将字符串输出到HTML中。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-body&gt; </span> </p> </td> 
   <td colname="col2"> <p>带有“基本外观”部分在“模板”链接下设置的任何“搜索链接颜色”设置的HTML正文标记。 向此标签添加背景属性，以在结果页上显示背景图像。 添加到此标签的任何颜色属性都会覆盖“基本外观”部分设置的“搜索链接颜色”设置。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-header&gt; </span> </p> </td> 
   <td colname="col2"> <p>在“模板”链接下的“基本外观”部分中设置的搜索结果标题的HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-cdata&gt;...&lt;/search-cdata&gt; </span> </p> </td> 
   <td colname="col2"> <p>search-cdata标记将替换为其XML等效标记： <span class="codeph"> &lt;search-cdata&gt; </span> 替换为 <span class="codeph"> &lt;![CDATA["和&lt;/search-cdata&gt;标 </span> 记替换为" <span class="codeph"> ]]&gt; </span>"。 XML分析器不解析开放标签和关闭标签之间的任何信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-query query-number="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>访客输入的查询。 高级的可选“query-number”属性控制由此标签输出的编号查询字符串。 例如， <span class="codeph"> &lt;search-query query-number=1&gt; </span> 输出 <span class="codeph"> sp_q_1 cgi参数的内 </span> 容。 如果未指定“query-number”，或如果query-number为“0”，则输出主查询( <span class="codeph"> sp_q </span>)。 可选的“encoding”属性控制输出是否为HTML编码、JavaScript编码、Perl编码、URL编码或未编码，以在结果页上输出。 “encoding”的默认值是“html”。 通常，您无需指定编码属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-total&gt; </span> </p> </td> 
   <td colname="col2"> <p>此搜索的结果总数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>此页面报告的结果计数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-lower&gt; </span> </p> </td> 
   <td colname="col2"> <p>为此页面报告的第一个结果的编号。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-upper&gt; </span> </p> </td> 
   <td colname="col2"> <p>为此页面报告的最后一个结果的编号。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-prev-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>上一页报告的结果数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-next-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>为下一页报告的结果数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-time&gt; </span> </p> </td> 
   <td colname="col2"> <p>此搜索的时间（以秒为单位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-logo&gt; </span> </p> </td> 
   <td colname="col2"> <p>为您的帐户配置的“搜索”徽标的HTML（如果有）。 此徽标是授予网站搜索／销售信誉的图像 </p> <p>目前，大多数帐户没有关联的搜索标志。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-collection all="name"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此搜索的结果集合。 可选的“all”属性用于指定表示整个网站的集合的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-form&gt; ...&lt;/search-form&gt; </span> </p> </td> 
   <td colname="col2"> <p>插入开始和结束表单标记。 将方法和操作属性插入开始表单标签中。 接受其他属性，包括语言的dir="RTL"属性以及与JavaScript相关的“name”和“onSubmit”属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-account&gt; </span> </p> </td> 
   <td colname="col2"> <p>插入指定帐户号的表单输入标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-gallery&gt; </span> </p> </td> 
   <td colname="col2"> <p>插入指定画廊编号的表单输入标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-query query-number="XX"&gt; </span> </p> </td> 
   <td colname="col2"> <p>插入指定查询字符串的表单输入标记。 高级、可选的“query-number”属性控件用于表单输入标记的编号查询。 例如， <span class="codeph"> &lt;search-input-query query-number=1&gt; </span> 为sp_q_1查询输出一个表单 <span class="codeph"> 输入标 </span> 记。 如果未指定“query-number”，或“query-number”为“0”，则插入主 <span class="codeph"> sp_q查询的输入标 </span> 记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-collections all="name"&gt; </span> </p> </td> 
   <td colname="col2"> <p>插入一个表单选择标记和关联的HTML，它们显示集合选择菜单。 可选的“all”属性用于指定表示整个网站的集合的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-lt&gt; </span> </p> </td> 
   <td colname="col2"> <p>在结果页上的其他HTML或模板标记中插入一个“搜索”模板标记的输出。 <span class="codeph"> &lt;search-lt&gt;插 </span> 入小于字符。 使用 <span class="codeph"> &lt;search-lt&gt;和 </span><span class="codeph"></span> &lt;search-gt&gt;提供了一种转义标记定义的方法，以便您可以使用“搜索模板”标记作为属性值。 当响应搜索呈现模板时，小于号(&lt;)将替换 <span class="codeph"> &lt;search-lt&gt;标 </span> 记。 例如， <span class="codeph"> &lt;search-link&gt; </span> 等效于 <span class="codeph"> &lt;search-lt&gt;a href="&lt;search-url&gt;"&lt;search-gt&gt; </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>20 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-gt&gt; </span> </p> </td> 
   <td colname="col2"> <p>在结果页上的其他HTML或模板标记中插入一个“搜索”模板标记的输出。 <span class="codeph"> &lt;search-gt&gt;插入 </span> 的字符大于字符。 使用 <span class="codeph"> &lt;search-lt&gt;和 </span><span class="codeph"></span> &lt;search-gt&gt;提供了一种转义标记定义的方法，以便您可以使用其他模板标记作为属性值。 当响应搜索呈现模板时，大于号(&gt;)将替换 <span class="codeph"> &lt;search-gt&gt;标 </span> 记。 例如， <span class="codeph"> &lt;search-link&gt; </span> 等效于 <span class="codeph"> &lt;search-lt&gt;a href="&lt;search-url&gt;"&lt;search-gt&gt; </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>21 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-param name="param-name" length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回当前搜索请求中名为“param-name”的cgi参数的值。 可选的“encoding”属性控制输出是否为HTML编码、JavaScript编码、Perl编码、URL编码或未编码，以在结果页上输出。 “encoding”的默认值是“html”。 通常，您无需指定编码属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>22 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release on October 30 2014--> <span class="codeph"> &lt;search-trace encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> 
    <!--<p>This global core search template tag outputs a representation of the submitted core search query, including any "fuzzy-search" query term expansions that happen by way of synonyms, sound-alikes, and so forth. </p>--> <p>编码 <span class="codeph"> 属性 </span> 是可选的；默认值是 <span class="codeph"> json </span>。 </p> <p> <p>注意： 仅当使用核心搜索查询参 <span class="codeph"> 数指定了sp_trace=1 </span> 时，此标记才具有输出。 </p> </p> <p>请参阅后端搜索CGI参数中 <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" format="dita" scope="local"> 的表中的第48行</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 模板锚点链接标记 {#section_3A51D27616C541E2B818CC52B2B856BA}

以下是导致锚点链接在它们之间的HTML周围的标记。 单击锚点链接后，将请求显示另一页结果。 可选属性“count”要求页面上显示许多结果。 如果未指定，则使用当前页面上请求的计数。 高级的可选“URL”属性控制关联链接指向的域。 默认情况下，域为， `https://search.atomz.com/search/`但您可以使用URL属性更改此域。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-next URL="https://search.yourdomain.com/search/"&gt; ...&lt;/search-next&gt; </span> </p> <p> <span class="codeph"> &lt;search-prev URL="https://search.yourdomain.com/search/"&gt; ...&lt;/search-prev&gt; </span> </p> </td> 
   <td colname="col2"> <p>显示结果的下一页或上一页。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-sort-by-date URL="https://search.yourdomain.com/search/"&gt; ...&lt;/search-sort-by-date&gt; </span> </p> <p> <span class="codeph"> &lt;search-sort-by-score URL="https://search.yourdomain.com/search/"&gt; ...&lt;/search-sort-by-score&gt; </span> </p> </td> 
   <td colname="col2"> <p>按日期或相关度对结果排序。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-show-summaries URL="https://search.yourdomain.com/search/"&gt; ...&lt;/search-show-summaries&gt; </span> </p> <p> <span class="codeph"> &lt;search-hide-summaries URL="https://search.yourdomain.com/search/"&gt; ...&lt;/search-hide-summaries&gt; </span> </p> </td> 
   <td colname="col2"> <p>显示或隐藏摘要。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 模板条件标记 {#section_18D9BC66DE484881932FD2F7EA9D170D}

允许您有条件地在它们之间包含HTML的标记。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-results&gt; ...&lt;/search-if-results&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-results&gt; ...&lt;/search-if-not-results&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果当前页面包含任何（或不包含）搜索结果，则这些标记包括HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-prev-count&gt;...&lt;/search-if-prev-count&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-prev-count&gt; ...&lt;/search-if-not-prev-count&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-next-count&gt;...&lt;/search-if-next-count&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-next-count&gt; ...&lt;/search-if-not-next-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果上一页或下一页具有与之关联的任何（或无）结果，则这些标记包括HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-sort-by-score&gt; ...&lt;/search-if-sort-by-score&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-sort-by-score&gt; ...&lt;/search-if-not-sort-by-score&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-sort-by-date&gt; ...&lt;/search-if-sort-by-date&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-sort-by-date&gt; ...&lt;/search-if-not-sort-by-date&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果当前页面是否按相关性或日期排序，则这些标记包括HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-show-summaries&gt; ...&lt;/search-if-show-summaries&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-hide-summaries&gt;...&lt;/search-if-hide-summaries&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果当前页面显示或隐藏摘要，则这些标记包括HTML。 您可以使用这些标记来包括或排除搜索结果的任何部分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-input-collections&gt; ...&lt;/search-if-input-collections&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-input-collections&gt; ...&lt;/search-if-not-input-collections&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果在生成当前页面的搜索结果时指定了集合，则这些标记包括HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-advanced&gt;...&lt;/search-if-advanced&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-advanced&gt; ...&lt;/search-if-not-advanced&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果为搜索查询指定 <span class="codeph"> 了sp_advanced=1 </span> CGI参数，则这些标签包括HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-bad-param name="parameter-name"&gt;...&lt;/search-if-bad-param&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-bad-param name="parameter-name"&gt;...&lt;/search-if-not-bad-param&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果给定参数无效或无效，则这些标记包括或排除它们之间的HTML。 </p> <p>当前仅 <span class="codeph"> 支持sp_q_location[_#] </span> 参数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-param name="param-name" value="param-value"&gt;...&lt;/search-if-param&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-param name="param-name" value="param-value"&gt;...&lt;/search-if-not-param&gt; </span> </p> </td> 
   <td colname="col2"> <p>这些高级标签包括它们之间的HTML，具体取决于在“name”属性中指定的CGI参数是否具有在“value”属性中指定的值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-sort-by-field name="field-name"&gt; ...&lt;/search-if-sort-by-field&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-sort-by-field name="field-name"&gt; ...&lt;/search-if-not-sort-by-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果当前页面是按给定字段名称排序的，或者不是按给定字段名称排序的，则这些高级标记包括它们之间的HTML。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 模板表单控件标记 {#section_45AFC414ACA74825B72FEAA8456F8DD2}

用于控制搜索模板中复选框、单选按钮和列表框的默认选择状态 `<form>` 的标记。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input&gt; </span> </p> </td> 
   <td colname="col2"> <p>在模板中用于代替 <span class="codeph"> &lt;input&gt;标 </span> 记。 将标记写入浏览器时，单词输入将 <span class="codeph"> 替换 </span> 搜索 <span class="codeph"> 输入，并且标记中的所 </span> 有其他信息将按原样输出。 此外，如果标 <span class="codeph"> 签中指 </span> 定的名称作为CGI参数列出，并且标签中指定的值是该CGI参数的值，则在标签的末尾添加 <span class="codeph"></span><span class="codeph"></span> 选中的字。 这样，您就可以自动使搜索结果中的默认单选按钮或复选框状态与当前查询相同。 </p> <p>例如，复选框的HTML代码可能如下所示： </p> <p> <span class="codeph"> &lt;input type=checkbox name="sp_w" value="exact"&gt;没有类似声音匹配 </span> </p> <p>该复选框的相应模板代码如下所示： </p> <p> <span class="codeph"> &lt;search-input type=checkbox name="sp_w" value="exact"&gt;没有类似声音匹配 </span> </p> <p>如果查询的CGI参数字符串包含 <span class="codeph"> sp_w=exact </span>，则写入浏览器并且搜索结果的标记如下所示(在标记的末尾插入 <span class="codeph"></span> 了选中的字词): </p> <p> <span class="codeph"> &lt;input type=checkbox name="sp_w" value="exact" checked&gt;没有类似声音匹配 </span> </p> <p>如果查询的CGI参数字符串不包含 <span class="codeph"> sp_w=exact </span>，则写入浏览器并且搜索结果的标记如下所示(标记中未列出选中 <span class="codeph"></span> 的单词): </p> <p> <span class="codeph"> &lt;input type=checkbox name="sp_w" value="exact"&gt;没有类似声音匹配 </span> </p> <p>&lt;search-input&gt; <span class="codeph"> 标签可用于将 </span> 复选框和单选按钮放入搜索模板中。 如果您有要添加到搜索模板中的 <span class="codeph"> &lt;form&gt;的复选框或单选按钮，请使用 </span> &lt;search-input...&gt; <span class="codeph"> 代替 </span> &lt;input...&gt; <span class="codeph"></span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-select&gt; ...&lt;/search-select&gt; </span> </p> <p> <span class="codeph"> &lt;search-option&gt; ...&lt;/search-option&gt; </span> </p> </td> 
   <td colname="col2"> <p>&lt;form&gt;标记中的下拉列 <span class="codeph"> 表框以 </span> &lt;select&gt;标记开头， <span class="codeph"> 以&lt;/select&gt;标记结 </span> 束 <span class="codeph"></span> 。 关 <span class="codeph"> 联 </span> 的CGI参数的名称列在 <span class="codeph"> &lt;select&gt;标签 </span> 中。 在&lt; <span class="codeph"> select&gt;标记后面 </span> 是一个 <span class="codeph"></span> &lt;option&gt;标记列表，这些标记指定要在列表框内显示的值。 </p> <p>&lt; <span class="codeph"> -select&gt;、 </span>&lt;/search-select&gt; <span class="codeph"> 、 </span>&lt;search-option&gt;和 <span class="codeph"></span><span class="codeph"></span><span class="codeph"></span> &lt;/search-option&gt;标签提供与&lt;search-input&gt;搜索标签类似的功能。 即，如果在 <span class="codeph"> &lt; </span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span> option&gt;标签中的词被自动作为CGI，并且如果搜索&lt;option&gt;列出的搜索选项&gt;标签中CGI中列出的CGI参数的值被作为搜索&lt;搜索选项&gt;标签中的值的值被列出的CGI参数的值，则选择的词被添加到发送到浏览器的标签的结尾处。 这样，您就可以自动在搜索结果中选择默认列表框，使其与当前查询相同。 </p> <p>例如，典型列表框如下所示： </p> <p> <code class="syntax html"> &lt;select&nbsp;name="sp_x"&nbsp;size=1&gt; 
      &lt;option&nbsp;value="any"&nbsp;selected&gt;Anywhere&lt;/option&gt; 
      &lt;option&nbsp;value="title"&gt;Title&lt;/option&gt; 
      &lt;option&nbsp;value="desc"&gt;Description&lt;/option&gt; 
      &lt;option&nbsp;value="keys"&gt;Keywords&lt;/option&gt; 
      &lt;option&nbsp;value="body"&gt;Body&lt;/option&gt; 
      &lt;option&nbsp;value="alt"&gt;Alternate&nbsp;text&lt;/option&gt; 
      &lt;option&nbsp;value="url"&gt;URL&lt;/option&gt; 
      &lt;option&nbsp;value="target"&gt;Target&lt;/option&gt; 
      &lt;/select&gt; </code> </p> <p>该列表框的相应模板代码如下所示： </p> <p> <code class="syntax html"> &lt;search-select&nbsp;name="sp_x"&nbsp;size=1&gt; 
      &lt;search-option&nbsp;value="any"&gt;Anywhere&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="title"&gt;Title&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="desc"&gt;Description&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="keys"&gt;Keywords&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="body"&gt;Body&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="alt"&gt;Alternate&nbsp;text&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="url"&gt;URL&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="target"&gt;Target&lt;/search-option&gt; 
      &lt;/search-select&gt; </code> </p> <p>如果要在搜索模板中向 <span class="codeph"> &lt;form&gt; </span> ..... <span class="codeph"> &lt;Search-select&gt;添加的词条，请使用搜索——选择来代替。 </span> &lt;Search/Select&gt;。 <span class="codeph"> &lt;Search-Select&gt;&lt;Place of Place of &lt;Search/Select&gt;,&lt;Search-Option...................................................... </span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span>&lt;?。/option&gt;重要。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-sort-by-field name="field-name" count="XX"&gt; ...&lt;/search-sort-by-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>这些高级标签在它们之间围绕HTML创建锚点链接。 单击此锚点时，将显示在给定字段上排序的结果页。 可选的 <span class="codeph"> count属 </span> 性指定要在结果页上显示的结果数。 如果 <span class="codeph"> 忽略 </span> 计数，则使用当前页面上使用的计数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 日期格式字符串 {#section_4BBDBBEF2B96414497617CD4B52D96E4}

您可以在日期格式字符串中使用以下转换规范：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>日期格式字符串 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%同类群组 </p> </td> 
   <td colname="col2"> <p> 匹配完整工作日名称的国家代表，例如“星期一”。 “语言”&gt;“词 <span class="uicontrol"> 语和语言 </span> ” <span class="uicontrol"> &gt;“语言”中的设 </span> 置将决 <span class="uicontrol"> 定 </span> 国家代表性。 </p> <p>请参阅 <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> 关于单词和语言</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a </p> </td> 
   <td colname="col2"> <p> 匹配缩写工作日名称的国家代表，其中缩写是前三个字符，例如“Mon”。 “语言”&gt;“词 <span class="uicontrol"> 语和语言 </span> ” <span class="uicontrol"> &gt;“语言”中的设 </span> 置将决 <span class="uicontrol"> 定 </span> 国家代表性。 </p> <p>请参阅 <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> 关于单词和语言</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%B </p> </td> 
   <td colname="col2"> <p> 匹配完整月份名称的国家代表，例如“June”。 “语言”&gt;“词 <span class="uicontrol"> 语和语言 </span> ” <span class="uicontrol"> &gt;“语言”中的设 </span> 置将决 <span class="uicontrol"> 定 </span> 国家代表性。 </p> <p>请参阅 <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> 关于单词和语言</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%b </p> </td> 
   <td colname="col2"> <p> 匹配缩写月份名称的国家代表，其中缩写是前三个字符，例如“Jun”。 “语言”&gt;“词 <span class="uicontrol"> 语和语言 </span> ” <span class="uicontrol"> &gt;“语言”中的设 </span> 置将决 <span class="uicontrol"> 定 </span> 国家代表性。 </p> <p>请参阅 <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> 关于单词和语言</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%D </p> </td> 
   <td colname="col2"> <p>等效于"%m/%d/%y"，例如"07/25/13"。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%d </p> </td> 
   <td colname="col2"> <p> 将月份的某天与小数(01-31)匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%e </p> </td> 
   <td colname="col2"> <p> 将月份的某天与小数(1-31)匹配。 空白在单位数之前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%H </p> </td> 
   <td colname="col2"> <p> 将24小时时钟与小数(00-23)相匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%h </p> </td> 
   <td colname="col2"> <p> 匹配缩写月份名称的国家代表，其中缩写是前三个字符，例如“Jun”（与%b相同）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%I </p> </td> 
   <td colname="col2"> <p> 将12小时时钟与小数(01-12)匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%j </p> </td> 
   <td colname="col2"> <p> 以小数(001-366)的形式匹配年份中的某天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%k </p> </td> 
   <td colname="col2"> <p> 将（24小时时钟）与小数(0-23)匹配。 空白在单位数之前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%l </p> </td> 
   <td colname="col2"> <p> 将12小时时钟作为小数(1-12)匹配。 空白在单位数之前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%M </p> </td> 
   <td colname="col2"> <p> 将分钟数与小数(00-59)匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%m </p> </td> 
   <td colname="col2"> <p> 将月份与小数(01-12)匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%p </p> </td> 
   <td colname="col2"> <p> 根据需要匹配“ante meridiem”或“post meridiem”的国家代表，例如“PM”。 “语言”&gt;“词 <span class="uicontrol"> 语和语言 </span> ” <span class="uicontrol"> &gt;“语言”中的设 </span> 置将决 <span class="uicontrol"> 定 </span> 国家代表性。 </p> <p>请参阅 <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> 关于单词和语言</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%R </p> </td> 
   <td colname="col2"> <p>等效于"%H:%M"，例如，"13:23"。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%r </p> </td> 
   <td colname="col2"> <p>相当于"%I:%M:%S %p"，例如，"01:23:45 PM"。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%S </p> </td> 
   <td colname="col2"> <p> 将第二个数字与小数(00-60)匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%T </p> </td> 
   <td colname="col2"> <p>等效于"%H:%M:%S"，例如，"13:26:47"。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%U </p> </td> 
   <td colname="col2"> <p> 将年份的周数（星期日作为周的第一天）与小数(00-53)匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%v </p> </td> 
   <td colname="col2"> <p>等效于“%e-%b-%Y”，例如“2013年7月25日”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Y </p> </td> 
   <td colname="col2"> <p> 将年份与以十进制数字表示的世纪匹配，例如“2013”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%y </p> </td> 
   <td colname="col2"> <p> 以小数(00-99)形式匹配没有世纪的年份。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Z </p> </td> 
   <td colname="col2"> <p> 匹配时区名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%% </p> </td> 
   <td colname="col2"> <p> 匹配 "%". </p> </td> 
  </tr> 
 </tbody> 
</table>

## 语言标识符 {#section_0490DECC00E34691ADE5A9ED90A6D911}

下表包含每种支持语言的语言标识符。 您可以在以下模板标记中将这些标识符用作可选“语言”属性的值：

* `search-date` 和 `search-display-field`.

   请参阅 [结果循环字符串标签](../c-appendices/c-templates.md#section_80D68334E8D04A33937A6E58ABAAA320)。

* `search-field-value-list` 请参 [阅字段值列表标记](../c-appendices/c-templates.md#section_D3298B5F976447DBA0032B883DCC91B1)。

* `search-field-value` 请参 [阅字段值列表循环标记](../c-appendices/c-templates.md#section_0717FA09F0FC449CB916883B0500A60E)。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>语言 </p> </th> 
   <th colname="col2" class="entry"> <p>语言 identifier </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>保加利亚语（保加利亚） </p> </td> 
   <td colname="col2"> <p> bg_BG </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中文（中国） </p> </td> 
   <td colname="col2"> <p> zh_CN </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中文（香港） </p> </td> 
   <td colname="col2"> <p> zh_HK </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中文（新加坡） </p> </td> 
   <td colname="col2"> <p>zh_SG </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中文（台湾） </p> </td> 
   <td colname="col2"> <p> zh_TW </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>捷克语（捷克共和国） </p> </td> 
   <td colname="col2"> <p> cs_CZ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>丹麦语（丹麦） </p> </td> 
   <td colname="col2"> <p> da_DK </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>荷兰语（比利时） </p> </td> 
   <td colname="col2"> <p> nl_BE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>荷兰语（荷兰） </p> </td> 
   <td colname="col2"> <p> nl_NL </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>英语（澳大利亚） </p> </td> 
   <td colname="col2"> <p> en_AU </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>英语（加拿大） </p> </td> 
   <td colname="col2"> <p> en_CA </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>英语（大不列颠） </p> </td> 
   <td colname="col2"> <p> en_GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>英语（美国） </p> </td> 
   <td colname="col2"> <p> en_US </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>法语（比利时） </p> </td> 
   <td colname="col2"> <p> fr_BE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>法语（加拿大） </p> </td> 
   <td colname="col2"> <p>fr_CA </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 芬兰语（芬兰） </p> </td> 
   <td colname="col2"> <p> fi_FI </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>法语（法国） </p> </td> 
   <td colname="col2"> <p> fr_FR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>法语（瑞士） </p> </td> 
   <td colname="col2"> <p> fr_CH </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>德语（奥地利） </p> </td> 
   <td colname="col2"> <p> de_AT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>德语（德国） </p> </td> 
   <td colname="col2"> <p> de_DE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>德语（瑞士） </p> </td> 
   <td colname="col2"> <p> de_CH </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>希腊语（希腊） </p> </td> 
   <td colname="col2"> <p> el_GR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>爱尔兰盖尔语（爱尔兰） </p> </td> 
   <td colname="col2"> <p> ga_IE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>意大利语（意大利） </p> </td> 
   <td colname="col2"> <p> it_IT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日语（日本） </p> </td> 
   <td colname="col2"> <p> ja_JP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>朝鲜语（韩国） </p> </td> 
   <td colname="col2"> <p> ko_KR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>挪威语（挪威） </p> </td> 
   <td colname="col2"> <p> no_NO </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>波兰语（波兰） </p> </td> 
   <td colname="col2"> <p> pl_PL </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>葡萄牙语（巴西） </p> </td> 
   <td colname="col2"> <p> pt_BR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>葡萄牙语（葡萄牙） </p> </td> 
   <td colname="col2"> <p> pt_PT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>俄语（前苏联） </p> </td> 
   <td colname="col2"> <p> ru_SU </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>斯洛伐克语（斯洛伐克语） </p> </td> 
   <td colname="col2"> <p> sk_SK </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>斯洛伐克语（斯洛文尼亚） </p> </td> 
   <td colname="col2"> <p>sl_SI </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>西班牙语（墨西哥） </p> </td> 
   <td colname="col2"> <p> es_MX </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>西班牙语（西班牙） </p> </td> 
   <td colname="col2"> <p> es_ES </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>瑞典语（瑞典） </p> </td> 
   <td colname="col2"> <p> sv_SE </p> </td> 
  </tr> 
 </tbody> 
</table>

## 指定内容类型HTTP头 {#section_AEED823E9938448A9EDB2F286D9CFD90}

可以使用以下标记指定Content-Type HTTP响应头：

`<search-content-type-header [content="MIME-type"] [charset="charset-name"]>`

和 `content` 属 `charset` 性是可选的。 此标记应尽早显示在模板中。 还建议在或之前显示它， `<search-html-meta-charset>` 因 `<search-xml-decl>`为它会影响这些标记的行为。

如果不指定属 `content` 性，则默认值为在 `MIME-type` > **[!UICONTROL Settings]** >中设置的值 **[!UICONTROL Crawling]****[!UICONTROL Content Types]**。 如果指定属 `content` 性，则该属性将用作标 `content` 签的默认属 `<search-html-meta-charset>` 性。

如果不指定属 `charset` 性，则不会将 `charset` 任何值写入标 `content-type` 题。

如果您指 `charset="1"` 定，则CGI参 `charset-name` 数的实际值是 `sp_f` CGI参数的值。 如果搜 `sp_f` 索中未提交CGI参数，则会从帐户设置中 `charset-name` 读取实际值。 您可以在> **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** >下查看或更改与帐户关联的字 **[!UICONTROL Personal Information]** 符集 **[!UICONTROL Character Encoding]**。

请参 [阅配置您的个人用户信息](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6)。

您可以通过列出特定字符集名称作为值(如 `charset` 或)来选 `charset="iso-8859-1"` 择它 `charset="Shift-JIS"`。

如果指定 `charset` 了属性，则它将用作和标 `charset` 签的默认属 `<search-html-meta-charset>` 性， `<search-xml-decl>` 并输出到标 `content-type` 题。

## 在HTML模板中指定字符集 {#section_E0D1816ABB5846BEBE9C26D5980CCBE6}

默认的HTML搜索结果模板通过以下标记指定与当前帐户关联的字符集：

`<search-html-meta-charset [content="MIME-type"] [charset="charset-name"]>`

内容和字符集属性是可选的。 此标记必须显示在模板 `<head>` 的HTML部分中。 此标记在从模板生成的HTML页面上生成以下标记：

`<meta http-equiv="content-type" content="MIME-type; charset=charset-name">`

如果不指定内容属性，则实际值将默认 `MIME-type` 为两个值之一。 如果标 `<search-content-type-header>` 签指定了属 `content` 性，则使用该值。 否则，使用的值是> **[!UICONTROL Templates]****[!UICONTROL Settings]** >选项卡中 **[!UICONTROL Content Type]** 的值。

如果不指定属性， `charset` 则实际值将默认为两 `charset-name` 个值之一。 如果标 `<search-content-type-header>` 签指定了属 `charset` 性，则使用该值。 否则，将从帐户设 `charset-name` 置中读取实际值。 您可以在> **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** >下查看或更改与帐户关联的字 **[!UICONTROL Personal Information]** 符集 **[!UICONTROL Character Encoding]**。

请参 [阅配置您的个人用户信息](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6)。

如果您指 `charset="1"` 定，则CGI参 `charset-name` 数的实际值是 `sp_f` CGI参数的值。 如果搜索 `sp_f` 中未提交任何CGI参数，则实际的值是标记中设置的值（如果指定），或 `charset-name``<search-content-type-header>` 是帐户设置中设置的值。

您可以指定特定字符集名称，如中所示 `charset="charset-name"`。 For example, `charset="iso-8859-1"` or `charset="Shift-JIS"`.

标记 `<search-html-meta-charset>` 是可选的。 如果删除它，浏览器将采用以下 `content-type`默认值： `content="text/html; charset=ISO-8859-1"`. 您还可以选择将标记替 `<search-html-meta-charset>` 换为您自己的标 `http-equiv` 记。

## 在XML模板中指定字符集 {#section_17DC31CDCC104F5F8081466B41A96E9D}

默认的XML搜索结果模板通过以下标记指定与当前帐户关联的字符集：

`<search-xml-decl [charset="charset-name"]>`

该属 `charset` 性是可选的。 此标记必须显示在模板顶部，但位于任何标记之 `<search-content-type-header>` 后。 此标签在从模板生成的XML文档上生成以下标签：

`<?xml version="1.0" encoding="charset-name" standalone="yes" ?>`

如果不指定值， `charset`则实际值将默 `charset-name` 认为两个值之一。 如果 `<search-content-type-header>` 指定了 `charset` 属性，则使用该值。 否则，将从帐户设 `charset-name` 置中读取实际值。 您可以在> **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** >下查看或更改与帐户关联的字 **[!UICONTROL Personal Information]** 符集 **[!UICONTROL Character Encoding]**。

请参 [阅配置您的个人用户信息](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6)。

如果您指 `charset="1"` 定，则CGI参 `charset-name` 数的实际值是 `sp_f` CGI参数的值。 如果搜索 `sp_f``charset-name``<search-content-type-header>` 中未提交CGI参数，则实际值为标记中设置的值（如果已指定）或在帐户设置中设置的值。

如果需要，可以指定特定的字符集名 `charset="charset-name"`称（如中所示）。 例如，`charset="iso-8859-1" or charset="Shift-JIS"`。

您可以选择将标记替 `<search-xml-decl>` 换为您自己的标 `?xml` 记。

## 在其他模板中包括搜索模板 {#section_7D1FCD3D9E2340C291E354C9720E8BC0}

要将一个搜索模板包含在另一个模板中，请使用标记，将file属性设置为要包含的模板文件的名称，如下例所示： `<search-include>`

`<search-include file="seo/seo_search_title.tpl" />`

SEO搜索模板区段位于子文件夹 `seo/` 中，而普通搜索模板位于子文 `templates/` 件夹中。 只有。tpl文件才有意在此上下文中包含。

## 管理网站的多个传输模板 {#reference_12AAB3B9F4C74C11956F1DBA95714C2F}

您可以通过为每个区域使用不同的搜索传输模板来控制网站中搜索结果的外观。

<!-- 

r_managing_multiple_templates.xml

 -->

要实现此类搜索功能，您可以在站点搜索／销售中管理传输模板。 或者，您也可以在发布中管理传输模板。 与网站搜索／销售一样，“发布”允许您编辑、预览和发布多个搜索传输模板。

要设置搜索表单以使用特定传输模板（默认模板除外），请使用查询 `sp_t` 参数。 例如，假定您有一个名为“clearance”的搜索模板，用于您网站的已标记销售区域。 您可以将标准HTML搜索表单与以下其他表单代码一起使用：

`<input type=hidden name="sp_t" value="clearance">`

当客户单击包含此行代码的标准表单时，将显示“清除”搜索传输模板及其搜索结果。

请参阅 [在搜索表单中使用集合](../c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3)。

请参 [阅将框架与表单一起使用](../c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5)。

请参 [阅示例高级搜索表单](../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A)。
