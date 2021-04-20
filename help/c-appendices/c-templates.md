---
description: 了解如何在Search&amp;Promote中使用演示和模板标记。
solution: Target
title: 模板
topic: Appendices,Site search and merchandising
uuid: 78299032-dc23-4dfe-b68f-cd57b2b6d7d8
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '15153'
ht-degree: 2%

---


# 模板{#templates}

## 模板 {#concept_A5CFB6BD805D49459A96219AF1B17842}

## 演示文稿模板标签{#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64}

网站搜索/促销标签和演示文稿模板属性的列表。


演示文稿模板是包含站点搜索/促销所定义的演示文稿模板标记的HTML文件。 这些标记指示客户查看的搜索结果的格式。

请参阅[关于模板](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5)。

您可以从以下演示文稿标记组中进行选择：

* [声明](../c-appendices/c-templates.md#section_82C5CA734D2941EB858FEFE3B695D2EC)
* [结果](../c-appendices/c-templates.md#section_06F249C9F6AE4B0F8C32117E19DCC905)
* [彩块化](../c-appendices/c-templates.md#section_EA4C5678D5864B89BAB4D0DFE62A4624)
* [痕迹导航](../c-appendices/c-templates.md#section_9B39B71FA6EC49FA8D88AD8A3BA987F7)
* [菜单](../c-appendices/c-templates.md#section_1D489ADF041F4351A66E5D5742125CA8)
* [帕格纳夫](../c-appendices/c-templates.md#section_2EE397635C514BBC8D668278EA314F35)
* [最近搜索](../c-appendices/c-templates.md#section_8CD907521F584257B475595B01A5964B)
* [Did You Mean](../c-appendices/c-templates.md#section_C1EB3B9D8E1242798A6E04609D1E3543)
* [自动完成](../c-appendices/c-templates.md#section_897316BEE1454E839A56B565CA4AF018)
* [商店](../c-appendices/c-templates.md#section_A33E25DB5E67404A823BD9618665B773)
* [Zones](../c-appendices/c-templates.md#section_B9B3179E000C42D492E1541F2FE44CB5)
* [循环指示器](../c-appendices/c-templates.md#section_387322CA0AA843A2ACF2795C328673E9)
* [其他语言](../c-appendices/c-templates.md#section_BFE8DC98E26F4D7BB60FEC54D9A5DC6C)

## 声明{#section_82C5CA734D2941EB858FEFE3B695D2EC}

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
   <td colname="col2"> <p>默认情况下，演示文稿模板会以MIME类型的text/html发回。 您可以更改此标记使用的内容类型。 </p> <p>在演示文稿模板中尽可能高地声明此标记。 请勿在此标签的同一行上添加其他文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-xml-declare&gt; </span> </p> </td> 
   <td colname="col2"> <p> 如果要返回XML，则可以使用此标签创建XML声明。 使此标记成为演示文稿模板中的第一行。 使用此标记时，content-type将自动设置为text/xml，除非在第一行中用<span class="codeph"> &lt;guided-content-type-header&gt; </span>覆盖它。 如果未指定字符集，则默认为UTF-8。 此标签在您的XML文档中生成以下输出： </p> <p> <span class="codeph"> &lt;?xml version="1.0" encoding="charset-name" standalone="yes" ?&gt; </span> </p> </td> 
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
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng 1/31/13--> <span class="codeph"> &lt;guided-results&gt;&lt;/guided-results&gt; </span> </p> </td> 
   <td colname="col2"> <p>向导结果标签定义结果循环的边界。 通过指定<span class="codeph"> gsname </span>属性，可以访问任何结果集。 如果未提供<span class="codeph"> gsname </span> ，则显示默认的搜索结果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng 1/31/13--> <span class="codeph"> &lt;guided-result-link&gt;&lt;/guided-result-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>要创建指向给定结果的链接，请使用<span class="codeph"> guided-result-link </span>标签。 通过定义<span class="codeph"> gsname </span>属性，您可以使用索引中的字段，而不是引用“search-url”的标准“loc”标记。 任何其他属性(如类和目标)也可以传递，这些属性在生成的锚点标签中输出。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng 1/31/13--> <span class="codeph"> &lt;guided-result-img gsname="fieldname"&gt; </span> </p> </td> 
   <td colname="col2"> <p><span class="codeph"> &lt;guided-result-img&gt; </span>标记有助于创建图像标记，而不是将变量嵌入原始<span class="codeph"> img </span>标记中。 </p> <p>在<span class="codeph"> gsname </span>属性中指定用于图像路径的字段。 结果是一个<span class="codeph"> img </span>标记，其中包含您定义并传递的任何标准HTML属性。 因此，以下示例： </p> <p> <code class="syntax html"> &lt;guided-result-img&nbsp;gsname="thumbnail" 
      &nbsp;class="thumb"&nbsp;border="0"/&gt; </code> </p> <p>becomes: </p> <p> <code class="syntax html"> &lt;img&nbsp;src="prod8172.jpg"&nbsp;class="thumb" 
      &nbsp;border="0"/&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 1/31/13; search-eng version does not have [escape...] Added ijson on 8/28/2015--> <span class="codeph"> &lt;guided-result-field gsname="fieldname"&gt; </span> </p> </td> 
   <td colname="col2"> <p> 结果中显示的任何信息都将显示为<span class="codeph"> &lt;guided-result-field&gt; </span>标记(使用自动生成标记（如<span class="codeph"> &lt;guided-result-img&gt; </span>标记）除外)。 </p> <p>在<span class="codeph"> gsname </span>中指定“搜索索引”字段的名称。 传递的确切字符串是在模板中输出的。 </p> <p>如果希望此字段以不同方式转义，则可以指定转义选项。 </p> <p>在传输模板中指定的编码之上应用此编码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <span class="codeph"> &lt;guided-if&gt;&lt;/guided-if-result-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果特定字段中存在要显示的内容，则此条件标签集为true。 如果不存在内容，则条件为false。 如果某个值不存在，或者显示了其他图像，依此类推，则可以使用这些标签决定是否显示周围的HTML。 </p> <p> <code class="syntax html"> &lt;guided-if-result-field&nbsp;gsname="thumbnail"&gt; 
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
   <td colname="col2"> <p>在列中显示结果时，此标签用于标识当前结果是否标记列的结尾。 </p> <p>当布尔条件为true时，将HTML添加到结果的末尾，以结束行并开始新行。 如果是最后一行，则不启动新行。 </p> <p>请参阅<span class="codeph"> &lt;guided-if-not-last&gt; </span>以了解有关该标签的更多信息。 </p> <p> <code class="syntax html"> &lt;guided-if-result-wrap&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/div&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-not-last&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;div&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-not-last&gt; 
      &nbsp;&lt;/guided-if-result-wrap&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-results-found&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果后端搜索请求返回结果，则返回1；如果未返回，则返回0。 如果未指定<span class="codeph"> gsname </span>，则标记将采用主搜索。 此标签有助于将逻辑传递给JavaScript例程。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-results-total&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回指定结果集中的结果总数。 未给出<span class="codeph"> gsname </span>时，假定默认搜索。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-results-lower&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回指定结果集页上较低结果的结果编号。 未给出<span class="codeph"> gsname </span>时，假定默认搜索。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-results-upper&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回指定结果集页上上结果的结果编号。 未给出<span class="codeph"> gsname </span>时，假定默认搜索。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> 

    &amp;lt;/guided-if[-not]-results-found&amp;gt;   &lt;/p>  &lt;/td>
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
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-title /&gt; </span> </p> </td> 
   <td colname="col2"> <p><span class="codeph"> &lt;guided-result-title&gt; </span>标签提供了使用<span class="codeph"> &lt;title&gt; </span>传输标签指定的标题传输模板字段的值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-description /&gt; </span> </p> </td> 
   <td colname="col2"> <p><span class="codeph"> &lt;guided-result-description&gt; </span>标签提供了使用<span class="codeph"> &lt;description&gt; </span>传输标签指定的描述传输模板字段的值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-loc /&gt; </span> </p> </td> 
   <td colname="col2"> <p><span class="codeph"> guided-result-loc&gt; </span>标签提供了使用<span class="codeph"> &lt;loc&gt; </span>传输标签指定的loc传输模板字段的值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;/guided-if-result-field&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>如果特定字段中有要显示的内容，则为true。 如果不存在内容，则条件为false。 使用标签来决定是否显示周围的HTML（如果不存在值，或是否显示其他图像等）。 </p> <p> <code class="syntax html"> &lt;guided-if-result-field&nbsp;gsname="thumbnail"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-result-img&nbsp;gsname="thumbnail"&nbsp;class="thumb"/&gt; 
      &lt;guided-else-result-field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;img&nbsp;src="nothumb.jpg"&nbsp;class="nothumb"/&gt; 
      &lt;/guided-if-result-field&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-attribute-table gsname="tablename"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签提供在传输模板中定义的具有<span class="codeph"> &lt;attribute_table&gt; </span>传输标签的遍历属性表。 有<span class="codeph"> &lt;guided-result-attribute-table-field&gt; </span>标签用于显示属性表字段值。 也可以在循环内使用plain <span class="codeph"> guided-result-field </span>标签来显示其他结果字段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-attribute-table-field gsname="fieldname"&gt; </span> </p> </td> 
   <td colname="col2"> <p>显示在传输模板中定义的属性表字段。 </p> <p> 

    ...
    
    &amp;lt;ul&amp;gt;
    
    &amp;lt;guided-result-attribute-table&amp;nbsp;gsname=&quot;downloads&quot;&amp;gt;
    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nhref;a&amp;nbsp;&amp;lt;guided-rest-table-field-nsp;gsp;gs=&amp;nsp;gs&quot;download-link&quot;&amp;nbsp;/&amp;gt;&quot;&amp;gt;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;lt;guid-result-attribute-table-field&amp;nbsp;gsname=&quot;download-title&quot;&amp;nbsp;/&amp;gt;
    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;n;&amp;nbsp;&amp;n;&amp;n;&amp;nbsp;&amp;nbsp;/a&amp;gt;&amp;nbsp;(&amp;lt;gsname=&quot;title&quot;/&amp;gt;)
    &amp;nbsp;&amp;lt;/li&amp;gt;
    
    
    
    
    
    
    &amp;lt;/guided-result-attribute-gt&amp;gt;
    
    &amp;lt;/guided results&amp;gt;   &lt;/p>  &lt;/td>
</tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release in October 2014--> <span class="codeph"> &lt;guided-trace&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出在给定搜索的传输模板输出的JSON数据的常规部分内跟踪数据中找到的跟踪信息。 </p> <p>如果未提供搜索名称，则假定<span class="codeph">为默认</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release on October 30, 2014)--> <span class="codeph"> &lt;guided-result-trace /&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出当前搜索结果的传输模板在JSON数据输出的结果&gt;跟踪信息中找到的JSON内容。 </p> <p>此标记仅在<span class="codeph"> &lt;guided-results&gt;&lt;/guided-results&gt; </span>循环中有效。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 彩块化{#section_EA4C5678D5864B89BAB4D0DFE62A4624}

Facet是可导航的组件，可让您深入搜索结果。 您可以使用facet标签在您的演示文稿模板上显示各种facet。 您可以按名称引用彩块化。

请参阅[关于Facets](../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5)。

请参阅[关于 Facet Rail](../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB)。

请参阅[关于动态彩块化](../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899)。

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
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 02/27/2014--> <span class="codeph"> &lt;guided-dynamic-facets&gt;&lt;/guided-dynamic-facets&gt; </span> </p> </td> 
   <td colname="col2"> 
    <!--NEW 2/2/2014--> <p>给定搜索的任何动态彩块化的循环上下文。 </p> <p>编辑<span class="codeph"> &lt;guided-facet&gt; </span>演示文稿模板标签，以便<span class="codeph"> &lt;guided-dynamic-facets&gt; </span>循环上下文自动提供gsname属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-display-name gsname=" <span class="varname"> facetname </span>" /&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回facet的显示标签。 </p> <p>如果facet在传输模板上使用<span class="codeph"> &lt;display-name&gt; </span>标记，则该标记的内容将成为标签。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-rail&gt;&lt;/guided-facet-rail&gt; </span> </p> </td> 
   <td colname="col2"> <p> 在表示模板上定义一个部分，该部分用作facet边栏中每个facet的重复图案。 </p> <p> 属于facet边栏的每个facet都使用此部分来评估其输出。 </p> <p>以下是彩块化边栏的示例： </p> <p> <code class="syntax html"> &lt;guided-facet-rail&gt; 
      &nbsp;&nbsp;&lt;guided-facet&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-display-name/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;... 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet&gt; 
      &nbsp;&nbsp;&lt;/guided-facet-rail&gt; </code> </p> <p>请注意，当<span class="codeph"> &lt;guided-facet-rail&gt; </span>标签内的值在搜索时动态确定并正确替换时，以下标签不需要<span class="codeph"> gsname </span>属性： </p> 
    <ul id="ul_5B5ACAFD2B8848DDB27471AB9DA7BE6E"> 
     <li id="li_5A07E78D51FE4708879DD742C877FFFF">向导小平面 </li> 
     <li id="li_B875DCACD7AB4FC890A456A6939AB657">向导 — facet-display-name </li> 
     <li id="li_B70450749E864DE7BA401E3CD6EF5EB3">向导 — facet-total-count </li> 
     <li id="li_DECDF5EF6FF7454F86C236D322F2BFEA">向导 — facet-undo-link </li> 
     <li id="li_176949227AC14E8CA643A419E10F7B5A">向导 — facet-undo-path </li> 
     <li id="li_B32D981281744462BC680F6EFEAC0069">向导 — facet-behavior </li> 
    </ul> <p><span class="wintitle">彩块化边栏</span>页面上的排序标准确定彩块化的位置。 您可以从“排序彩块化方法”下拉式列表中选择排序顺序。 </p> <p> 
     <!--NEW 02/27/2014-->此标记可以选择接受_dynamic_facets的gsname <span class="codeph"> 属性值， </span>为此搜索的任何动态彩块化提供循环上下文。此预定义的facet边栏也会在Business Rules用户界面中显示，以便在facet边栏“_dynamic_facets”中执行<span class="codeph">推ffacet X以定位Y </span>”。 </p> <p>请参阅<a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local">关于 Facet Rail</a>。 </p> <p>另请参阅<a href="../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local">关于动态彩块化</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match current search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet gsname=" <span class="varname"> facetname </span>" height=" <span class="varname"> 60px </span>" width=" <span class="varname"> 120px </span>"&gt;&lt;/guided-facet&gt; </span> </p> </td> 
   <td colname="col2"> <p>使用<span class="codeph">导向facet </span>标签可定义一个区域，其中所有facet标签都与特定facet相关。 此标签也是一个布尔标签，如果facet中不存在值，则隐藏所有内容。 在这种情况下，没有输出小平面值的点)。 </p> <p>高度和宽度属性是可选的，尺寸以像素(px)为单位指定。 可视规则生成器(VRB)使用这两个属性，并在隐藏facet时将虚线框显示为交互式占位符。 </p> <p> 当显示名称位于facet中且facet处于隐藏状态时，该名称也会隐藏。 但是，如果名称位于facet之外，则仅当<span class="codeph">区域</span>标签或<span class="codeph"> guided-if-facet-visible </span>标签绕在facet周围时，才可隐藏该名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-if&gt;&lt;/guided-if&gt; </span> </p> </td> 
   <td colname="col2"> <p>当facet值的数量超过配置中定义的长度阈值时，此条件标签为true。 当列表过长时，使用它将facet显示为其他UI元素(如截断的列表或滚动框)。 </p> <p> <code class="syntax xml"> &lt;guided-facet&nbsp;name="category"&gt; 
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
      &lt;/guided-facet&gt; </code> </p> <p>您还可以在名为<span class="codeph">的向导facet </span>块的上下文之外使用此条件，方法是通过使用<span class="codeph"> gsname </span>属性直接引用特定facet。 </p> <p> <code class="syntax html"> &lt;guided-if-facet-long&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;The&nbsp;category&nbsp;facet&nbsp;is&nbsp;very&nbsp;long! 
      &lt;/guided-if-facet-long&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-if&gt;&lt;/guided-if&gt; </span> </p> </td> 
   <td colname="col2"> <p>当点击facet至少一次且当前已选择facet值时，此条件标签为true。 它用于显示或隐藏HTML或gs标记，具体取决于是否单击了facet。 </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;name="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This&nbsp;facet&nbsp;has&nbsp;been&nbsp;selected.&nbsp;&nbsp;You&nbsp;can&nbsp;no&nbsp;longer&nbsp;refine&nbsp;it. 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-value-link&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-selected&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>您还可以在名为<span class="codeph">的向导facet </span>块的上下文之外使用此条件，方法是通过使用<span class="codeph"> gsname </span>属性直接引用特定facet。 </p> <p> <code> &lt;guided-if-facet-selected&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;The&nbsp;category&nbsp;facet&nbsp;is&nbsp;selected! 
      &lt;/guided-if-facet-selected&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-if&gt;&lt;/guided-if&gt; </span> </p> </td> 
   <td colname="col2"> <p>当只有一个facet值时，此条件标签为true。 当无法优化结果时，使用标记更改facet的显示。 </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;name="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-single&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Facet&nbsp;is&nbsp;not&nbsp;refinable. 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-single&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-value-link&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-single&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>您还可以在名为<span class="codeph">的向导facet </span>块的上下文之外使用此条件，方法是通过使用<span class="codeph"> gsname </span>属性直接引用特定facet。 </p> <p> <code class="syntax html"> &lt;guided-if-facet-single&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;There&nbsp;is&nbsp;only&nbsp;one&nbsp;value&nbsp;in&nbsp;the&nbsp;category&nbsp;facet! 
      &lt;/guided-if-facet-single&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--Added 7/15/2014--> <span class="codeph"> &lt;guided-if&gt;&lt;/guided-if&gt; </span> </p> </td> 
   <td colname="col2"> <p>当facet为多选时，此条件标签为true。 使用标签可更改<span class="codeph"> &lt;guided-facet-rail&gt; </span>或<span class="codeph"> &lt;guided-dynamic-facets&gt; </span>标签内facet的显示。 </p> <p> 

    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;lt;guided-if-facet-multiselect&amp;gt;
    &amp;nbsp;...
    &amp;nbsp;&amp;lt;guided-else-facet-multiselect&amp;gt;
    &amp;nbsp;...
    &amp;nbsp;&amp;lt;/guided-if-facet-multiselect&amp;gt;
    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;...
    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;lt;/guided-facet&amp;gt;
    &amp;nbsp;&amp;nbsp;&amp;lt;/guided-facet-rail&amp;gt;   &lt;/p>  &lt;/td>
</tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-values&gt; facetname  </span>"]&gt;&lt;/guided-facet-values&gt; </span><span class="varname"> </span></p> </td> 
   <td colname="col2"> <p>这是facet value循环迭代器标签。 您可以在名为<span class="codeph">的向导facet </span>块的上下文中定义它，在这种情况下，可以省略<span class="codeph"> <span class="varname"> gsname </span> </span>。 或者，您可以在任何<span class="codeph">导向facet </span>块外部定义它，但它需要<span class="codeph"> <span class="varname"> gsname </span> </span>属性来标识显示哪组facet值。 </p> <p>您还可以使用此标记在名为<span class="codeph">的guided-facet </span>块的上下文外显示facet值。 使用<span class="codeph"> <span class="varname"> gsname </span> </span>属性直接引用特定facet。 </p> <p> <code class="syntax html"> &lt;script&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;registerFacetValues('category',&nbsp;'&lt;guided-facet-values&nbsp;gsname="category"&gt;&lt;guided-facet-value/&gt;,&lt;/guided-facet-values&gt;'); 
      &lt;/script&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-value&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出当前facet值的字符串。 </p> <p>默认情况下，该值为HTML转义。 您可以使用转义选项更改转义值的方式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-count /&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出与当前facet值匹配的结果数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-facet-value-link&gt;&lt;/guided-facet-value-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>为要单击的站点访客在facet值字符串周围创建链接。 将自动生成路径，以按当前facet值缩小结果。 它支持将任何属性直接传递给锚点标签。 </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
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
   <td colname="col2"> <p>更改当前选定的facet值时的显示。 如果已经选择，在大多数情况下，它不再可链接。 </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
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

    &amp;lt;/guided-if[-not]-facet-value-ghost&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>当facet值为重影值时，更改其显示。 当facet值是重影值时，它通常以斜体文本显示，以指示该值缺失或“重影”。 </p> <p>以下代码摘录是facet块的示例： </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
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
   <td colname="col2"> <p>显示给定小平面的撤消链接。 如果存在多选彩块化，则此链接将取消选择给定彩块化的所有值。 为facet指定名称。 如果当前未选择facet，则链接是当前路径。 </p> <p>以下是此标记用法的示例： </p> <p> <code class="syntax html"> &lt;guided-if-facet-selected&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-undo-link&nbsp;gsname="category"&gt;Undo&nbsp;Category&lt;/guided-facet-undo-link&gt; 
      &lt;/guided-if-facet-selected&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-facet-long [gsname="facetname"]&gt; 
      &lt;guided-else-facet-long&gt;&lt;/guided-if-facet-long&gt; </code> </p> </td> 
   <td colname="col2"> <p>当facet值的数量超过配置中定义的长度阈值时，此条件标签为true。 当列表过长时，使用它将facet显示为其他用户界面元素(如截断的列表或滚动框)。 </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;gsname="category"&gt; 
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
      &nbsp;&lt;/guided-facet&gt; </code> </p> <p>您还可以在名为<span class="codeph">的向导facet </span>块的上下文之外使用此条件，方法是通过使用<span class="codeph"> <span class="varname"> gsname </span> </span>属性直接引用特定facet。 </p> <p> <code class="syntax html"> &lt;guided-if-facet-long&nbsp;gsname="category"&gt; 
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
      &lt;/guided-facet&gt; </code> </p> <p>您还可以在名为<span class="codeph">的向导facet </span>块的上下文之外使用此条件，方法是通过使用<span class="codeph"> gsname </span>属性直接引用特定facet。 </p> <p> <code class="syntax html"> &lt;guided-if-facet-selected&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The&nbsp;category&nbsp;facet&nbsp;is&nbsp;selected! 
      &lt;/guided-if-facet-selected&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-facet-single [gsname="facetname"]&gt; 
      &lt;guided-else-facet-single&gt;&lt;/guided-if-facet-single&gt; </code> </p> </td> 
   <td colname="col2"> <p>当只有一个facet值时，此条件标签为true。 当无法优化结果时，它可用于更改facet的显示。 </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-single&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Facet&nbsp;is&nbsp;not&nbsp;refinable. 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-single&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-single&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>您还可以在名为<span class="codeph">的向导facet </span>块的上下文之外使用此条件，方法是通过使用<span class="codeph"> <span class="varname"> gsname </span> </span>属性直接引用特定facet。 </p> <p> <code class="syntax html"> &lt;guided-if-facet-single&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;There&nbsp;is&nbsp;only&nbsp;one&nbsp;value&nbsp;in&nbsp;the&nbsp;category&nbsp;facet! 
      &lt;/guided-if-facet-single&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-facet-has-values [gsname="facetname"]&gt; 
      &lt;guided-else-facet-has-values&gt;&lt;/guided-if-facet-has-values&gt; </code> </p> </td> 
   <td colname="col2"> <p>此条件允许您检查指定的facet是否具有任何值。 您可以使用它来显示另一个facet而不是空的facet。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>20 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-total-count gsname=" <span class="varname"> facetname </span>" /&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出给定方面内的结果总数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>21 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value gsname=" <span class="varname"> associated custom facet value </span>"&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出与facet关联的值的字符串。 您可以有0个或多个与facet关联的字段。 具有关联字段非常罕见，为了支持这样，您需要配置传输模板。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>22 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-facet-value gsname=" <span class="varname"> associated custom facet value </span>" /&gt;&lt;guided-else-facet-value&gt;&lt;/guided-if-facet-value&gt; </span> </p> </td> 
   <td colname="col2"> <p>测试facet值是否具有关联的字段值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>23 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-link&gt; value  </span>"]+&gt;&lt;/guided-facet-link&gt; </span><span class="varname"> </span></p> </td> 
   <td colname="col2"> <p>在facet值字符串周围创建一个链接，供客户单击。 将自动生成路径，以按当前facet值缩小结果。 它支持将任何属性直接传递给锚点标签。 </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&nbsp;class="facetlink"&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &lt;/guided-facet-values&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>24 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-path&gt; </span> </p> </td> 
   <td colname="col2"> <p>创建指向facet值的您自己的链接。 </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-lt/&gt;a&nbsp;href="&lt;guided-facet-value-path/&gt;"&lt;guided-gt/&gt;&lt;guided-facet-value/&gt;&lt;/a&gt; 
      &lt;/guided-facet-values&gt; </code> </p> <p>默认情况下，该值为URL转义。 但是，可以通过通过转义参数指定要使用的转义模式来添加另一个编码层。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>25 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-children&gt;&lt;/guided-facet-value-children&gt; </span> </p> </td> 
   <td colname="col2"> <p>当<span class="codeph"> &lt;guided-facet-values&gt; </span>迭代每个facet值时，此标签迭代嵌套facet的所有子值。 在此标记中，使用典型的facet标记创建链接、创建撤消链接和显示facet值。 此标签必须位于<span class="codeph"> &lt;guided-facet-values&gt; </span>内，因为它确实进行嵌套循环。 </p> <p>使用此标记的示例如下： </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
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
   <td colname="col2"> <p>测试当前facet值是否具有子值。 建议在使用<span class="codeph"> &lt;guided-facet-value-children&gt; </span>标签之前使用。 “else”子句是可选的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>27 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;guided-else[-not]-facet-value-abote-length-threshold&amp;gt;
    
    &amp;lt;/guided-if[-not]-facet-value-abote-length-threshold&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>确定facet-values循环中的当前facet值是否高于长度阈值。 它通常用于仅在长facet上显示低于阈值的值（除非用户先前选择了facet下方显示的“查看更多”链接）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>28 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;guided-else[-not]-facet-value-equals-length-threshold&amp;gt;
    
    &amp;lt;/guided-if[-not]-facet-value-equals-length-threshold&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>确定facet-values循环中的当前facet值是否等于长度阈值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>29 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-undo-link&gt;&lt;/guided-facet-value-undo-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>显示给定选定facet值的撤消链接。 使用它可在选定的facet值旁边显示撤消链接。 由于此撤消链接仅取消选择该特定的选定值，因此它与取消选择所有选定值的<span class="codeph"> &lt;guided-facet-undo-link&gt; </span>不同。 </p> <p> <p>注意： 如果facet没有多选行为，则两个撤消链接具有相同的行为。 即，facet只能有一个选定值。 </p> </p> <p>如果当前未选择facet，则链接是当前路径。 仅在<span class="codeph"> guided-facet-values </span>循环中使用此标签。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>30 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-undo-path /&gt; </span> </p> </td> 
   <td colname="col2"> <p>创建您自己的facet值撤消链接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>31 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-undo-path gsname=" <span class="varname"> facetname </span>" /&gt; </span> </p> </td> 
   <td colname="col2"> <p>创建您自己的facet撤消链接。 </p> <p> 与<span class="codeph"> &lt;guided-facet-undo-link&gt; </span>标签类似，只是它为您提供了构建您自己的撤消链接的原始路径。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>32 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-facet-value-matches facetname="facetname" value="value"&gt;&lt;guided-else-facet-value-matches&gt; 
      &lt;/guided-if-facet-value-matches&gt; </code> </p> </td> 
   <td colname="col2"> <p>当给定facet具有选定值或单个值“value”时，有条件显示HTML。 此标签集通常用于根据在另一个facet中选定的值显示facet。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>33 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-behavior gsname=" <span class="varname"> facetname </span>" /&gt; </span> </p> </td> 
   <td colname="col2"> <p>确定小平面的行为，如正常、粘滞或多选。 对于收到XML结果并希望根据facet行为动态更改facet显示方式的客户而言，此功能非常有用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>34 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;/guided-if-facet[-not]-visible&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>此标记所包裹的内容会根据facet的可见性状态进行隐藏或显示。 如果业务规则直接隐藏或显示facet，则facet内的任何内容将隐藏或显示。 不需要这些标签绕排facet。 </p> <p> 此标记的常用用途是当名称位于facet外部时隐藏显示名称。 将此标记环绕在显示名称周围会使名称在facet隐藏时消失。 </p> <p>此标签替换区域，具有与使用区域相同的许多性能优势。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 痕迹导航{#section_9B39B71FA6EC49FA8D88AD8A3BA987F7}

请参阅[关于痕迹导航](../c-about-design-menu/c-about-breadcrumbs.md#concept_FB8A943C594A4A1593B118141DA61F03)。

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
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-breadcrumb&gt; breadcrumbname  </span>"&gt;&lt;/guided-breadcrumb&gt; </span><span class="varname"> </span></p> </td> 
   <td colname="col2"> <p>痕迹导航的循环标签。 对于当前状态的每个查询数，在开始和结束标签之间的任何内容都会重复。 </p> <p>如果省略<span class="codeph"> <span class="varname"> gsname </span> </span> ，则使用名为“default”的痕迹导航。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-breadcrumb-link&gt;&lt;/guided-breadcrumb-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>在痕迹导航中创建链接。 默认行为是“goto”行为。 如果链接的行为不同，请使用<span class="codeph"> <span class="varname"> gsname </span> </span>可选属性指定“remove”或“drop”。 标记中包含的任何属性都会传递到生成的锚点标记。 </p> <p> <code class="syntax html"> &lt;guided-breadcrumb&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-link&nbsp;gsname="remove"&nbsp;class="bc_link"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-value/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-breadcrumb-value /&gt; </span> </p> </td> 
   <td colname="col2"> <p>value标签将打印出当前痕迹导航小版本的转换值。 它仅用于<span class="codeph">导向痕迹导航</span>块的上下文。 </p> <p> <code class="syntax html"> &lt;guided-breadcrumb&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-value/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-breadcrumb-label /&gt; </span> </p> </td> 
   <td colname="col2"> <p>标签标签输出一个标签，用于描述已选择哪个facet来生成该痕迹导航项的痕迹导航值。 它仅用于<span class="codeph">导向痕迹导航</span>块的上下文。 </p> <p> <code class="syntax html"> &lt;guided-breadcrumb&gt; 
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
   <td colname="col2"> <p>如果当前痕迹导航值具有标签，则此条件标签用于有条件地显示内容。 当标签实际存在时，它仅用于显示标签和相关内容。 它仅用于<span class="codeph">导向痕迹导航</span>块的上下文。 </p> <p> <code class="syntax html"> &lt;guided-breadcrumb&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-breadcrumb-label&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-label/&gt;: 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-breadcrumb-label&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-value/&gt;&lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-breadcrumb-path&gt; </span> </p> </td> 
   <td colname="col2"> <p>用于构建您自己的痕迹导航链接。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 菜单{#section_1D489ADF041F4351A66E5D5742125CA8}

请参阅[关于菜单](../c-about-design-menu/c-about-menus.md#concept_68123CE5CF4447B59217B5D721424E32)。

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
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu gsname="menuname"&gt;&lt;/guided-menu&gt; </span> </p> </td> 
   <td colname="col2"> <p>这是菜单值循环迭代器标签。 使用<span class="codeph"> gsname </span>属性可标识显示的菜单项集。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-link&gt;&lt;/guided-menu-item-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>为您提供用于优化当前菜单项搜索的URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-option&gt; </span> </p> </td> 
   <td colname="col2"> <p>通常，菜单显示在模板的选择控件中。 此标签使构建选择控件变得更简单，因为它生成用于为选择控件生成选项的HTML。 </p> <p>例如，以下代码块： </p> <p> <code class="syntax html"> &lt;select&nbsp;name="sort"&nbsp;onchange="gcGo(this);"&gt; 
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
   <td colname="col2"> <p>返回路径字符串。 如果要向路径添加参数并创建自定义链接，请使用标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if-menu-item-selected&gt; 
      &lt;guided-else-menu- 
      item-selected&gt; 
      &lt;/guided-if-menu-item-selected&gt; </code> </p> </td> 
   <td colname="col2"> <p>返回1或0，指示是否选择了当前菜单项。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Pagenav {#section_2EE397635C514BBC8D668278EA314F35}

页面导航标签可用于构建一组链接，允许用户通过搜索结果进行页面。

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
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-pages&gt;&lt;/guided-pages&gt; </span> </p> </td> 
   <td colname="col2"> <p>页面导航的循环标签。 每个页面都会重复显示开始标记和结束标记之间的任何内容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-link&gt;&lt;/guided-page-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>在页面导航中创建链接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-link gsname="first|prev|next|last|viewall|viewpages"&gt;&lt;/guided-page-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>创建指向第一页、上一页、下一页或最后一页的链接。 它还可以创建一个链接，用于视图一个页面上的所有页面。 </p> </td> 
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
   <td colname="col2"> <p>如果选择了当前重复的页面，则此条件标签集为true。 它通常用于在页面导航控件中以不同方式显示页码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-page-prev&gt; 
      &lt;guided-else-page- 
      prev&gt; 
      &lt;/guided-if[-not]-page-prev&gt; </code> </p> </td> 
   <td colname="col2"> <p> 如果当前页面有上一页，则此条件标记集为true。 它通常用于在有意义时显示页面导航中的上一个链接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-page-next&gt; 
      &lt;guided-else-page- 
      next&gt; 
      &lt;/guided-if[-not]-page-next&gt; </code> </p> </td> 
   <td colname="col2"> <p> 如果当前页面有下一页，则此条件标记集为true。 它通常用于在有意义时显示页面导航中的上一个链接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-page-viewall&gt; 
      &lt;guided-else-page- 
      viewall&gt; 
      &lt;/guided-if[-not]-page-viewall&gt; </code> </p> </td> 
   <td colname="col2"> <p> 当搜索返回大的结果集时，您可能不想优惠视图所有结果的功能。 因此，您可以使用这组条件标签来确定何时显示“全部视图”链接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-page-viewpages&gt; 
      &lt;guided-else-page- 
      viewpages&gt; 
      &lt;/guided-if[-not]-page-viewpages&gt; </code> </p> </td> 
   <td colname="col2"> <p>您可以使用这组条件标签来确定何时显示视图页链接。 它通常用于允许客户视图特定页面。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 

    &amp;lt;guided-else-page-link&amp;gt;
    &amp;lt;/guided-if[-not]-page-link&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>测试页面导航是否包含第一页、上一页、下一页等。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-total /&gt; </span> </p> </td> 
   <td colname="col2"> <p> 返回包含搜索结果总页数的字符串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-pagination gsname= 
      "pagination_name"&gt;&lt;/guided-pagination&gt; </code> </p> </td> 
   <td colname="col2"> <p>使用<span class="codeph">导向分页</span>标签可定义一个区域，在您定义的页面导航设置很少的情况下，所有分页标签都与特定分页设置相关。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> 

    next|last|viewall|viewpages]/&amp;gt;   &lt;/p>  &lt;/td>
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

## 最近搜索{#section_8CD907521F584257B475595B01A5964B}

您可以使用最近搜索标记来构建一组链接，让用户快速运行以前的搜索，如下例所示：

```
<guided-if-recent-searches> 
    <span>Recent Searches</span><br/> 
    <guided-recent-searches> 
        <guided-recent-searches-link><guided-recent-searches-value></guided-recent-searches-link><br/> 
    </guided-recent-searches> 
    <guided-recent-searches-clear-link>Clear Recent Searches</guided-recent-searches-clear-link> 
</guided-if-recent-searches>
```

请参阅[配置最近搜索](../c-about-design-menu/t-configuring-recent-searches.md#task_E9E8ACA04C90484F8AFD5262167B2562)。

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
   <td colname="col2"> <p>最近搜索的循环标签。 每个页面都会重复显示开始标记和结束标记之间的任何内容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-recent-searches-link [attr="value"]+&gt; 
      &lt;/guided-recent-searches-link&gt; </code> </p> </td> 
   <td colname="col2"> <p>允许您构建指向最近搜索的链接。 它支持将任何HTML属性直接传递到锚点标签。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-path /&gt; </span> </p> </td> 
   <td colname="col2"> <p>允许您在<span class="codeph">向导 — 最近搜索</span>循环中获取最近搜索的相对URL路径。 通常，您会使用<span class="codeph"> guided-recent-search-link </span>。 但是，如果您想构建自己的链接，可以使用此标签。 以下是一个示例： </p> <p> <code class="syntax html"> &lt;guided-lt/&gt;a&amp;nbsp;href="&lt;guided_recent_searches_path&gt;"&gt;&lt;guided-recent-searches-value&gt;&lt;/a&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-value&gt; </span> </p> </td> 
   <td colname="col2"> <p>允许您获取与最近搜索关联的查询词。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-clear-link&gt;&lt;/guided-recent-searches-clear-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>允许您优惠客户清除最近保存的搜索的功能。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-clear-path /&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回<span class="codeph"> &lt;guided-recent-searches-clear-link&gt; </span>使用的路径，以便您能够构建自己的链接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;/guided-if-recent-searches&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>允许您在客户执行最近搜索时显示最近搜索。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Did You Mean {#section_C1EB3B9D8E1242798A6E04609D1E3543}

当搜索未返回任何结果且搜索词未在帐户的词典中时，您可以使用“您的意思是”标记来构建指向建议的链接集。 以下是使用“您是错误”标记的示例：

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
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matches search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-suggestions&gt;&lt;/guided-suggestions&gt; </span> </p> </td> 
   <td colname="col2"> <p>这是循环播放建议的循环标签。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matches search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-suggestion-link&gt;&lt;/guided-suggestion-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>创建指向给定建议的链接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Newly added from search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-suggestion-value /&gt; </span> </p> </td> 
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
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-suggestion-path /&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回建议的路径字符串。 您可以使用它构建自己的锚点标签。 通常，使用<span class="codeph"> guided-succement-link </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-suggestion /&gt; </span> </p> </td> 
   <td colname="col2"> <p>建议。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-suggestion-result-count /&gt; </span> </p> </td> 
   <td colname="col2"> <p>建议的结果计数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-suggestion-autosearch&gt; 
      &lt;guided-else[-not]-suggestion-autosearch&gt; 
      &lt;/guided-if[-not]-suggestion-autosearch&gt; </code> </p> </td> 
   <td colname="col2"> <p>允许您测试是否执行了基于建议的自动搜索（在此功能处于开启状态时），结果为零。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-suggestion-original-query /&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果执行了自动搜索，则返回原始查询。 </p> <p>使用示例： </p> <p> <code class="syntax html"> &lt;guided-if-suggestion-autosearch&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;Search&nbsp;for&nbsp;&lt;guided-query-param&nbsp;gsname="q"&nbsp;/&gt;&nbsp;instead&nbsp;of&nbsp;&lt;guided-suggestion-original-query&nbsp;/&gt; 
      &lt;/guided-if-suggestion-autosearch&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-suggestion-low-results&gt; 
      &lt;guided-else[-not]-suggestion-low-results&gt; 
      &lt;/guided-if[-not]-suggestion-low-results&gt; </code> </p> </td> 
   <td colname="col2"> <p>如果由于结果计数较低而有建议，则此条件为true，如果此功能已打开。 </p> <p>以下是使用此标记的示例： </p> <p> <code class="syntax html"> &lt;guided-if-suggestion-low-results&gt; 
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

## 自动完成{#section_897316BEE1454E839A56B565CA4AF018}

以下标记可用于向搜索表单添加自动完成功能。 需要头内容和表单内容标签才能正确实现自动完成功能。 建议您使用这些标记，而不是将自动完成的Javascript和CSS硬编码到演示文稿模板中。 原因是，每当您更改自动完成设置时，标记使模板能够拾取任何新的失败缓存ID，而无需手动更新模板。

请参阅[关于自动完成](../c-about-auto-complete.md#concept_093A9CD754864BA79B456FE4BEB64578)。

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
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-autocomplete&gt; &lt;guided-else-autocomplete&gt; &lt;/guided-if-autocomplete&gt; </span> </p> </td> 
   <td colname="col2"> <p>检测是否启用自动完成功能。 您可以使用标记（可选）拾取自动完成所需的头部和表单内容。 反过来，这又可让您打开和关闭功能，而不必更改演示文稿模板。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-ac-css /&gt; </span> </p> </td> 
   <td colname="col2"> <p>在演示文稿模板的头中使用，并替换为相应的CSS脚本，以便自动完成。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-ac-form-content /&gt; </span> </p> </td> 
   <td colname="col2"> <p>在演示文稿模板的搜索表单（在<span class="codeph"> &lt;form&gt; </span>和<span class="codeph"> &lt;/form&gt; </span>标签之间）中使用，而不是硬编码表单中的自动完成标签。 标签将替换为完成自动完成工作所需的相应HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-ac-javascript /&gt; </span> </p> </td> 
   <td colname="col2"> <p>生成指向自动完成JavaScript的链接。 为获得最佳性能，建议将此标签放在页面底部附近的结束“body”标签之前。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 存储{#section_A33E25DB5E67404A823BD9618665B773}

使用以下标签来测试和显示用户当前所在的商店。

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
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-store /&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出当前存储。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-store-defined&gt; &lt;guided-else-store-defined&gt; &lt;/guided-if-store-defined&gt; </span> </p> </td> 
   <td colname="col2"> <p>检测用户是否在商店中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-store gsname="store"&gt; &lt;guided-else-store&gt; &lt;/guided-if-store&gt; </span> </p> </td> 
   <td colname="col2"> <p>检测用户是否在存储中，<span class="codeph"> gsname </span>参数指定。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 区域{#section_B9B3179E000C42D492E1541F2FE44CB5}

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
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-zone gsname="zone area"&gt; </span> </p> </td> 
   <td colname="col2"> <p>您可以用区域标签中的任何内容换行，以创建该区域之外的区域。 这样，您就可以使用业务规则根据需要显示区域。 默认情况下，始终显示区域。 您可以使用可选的搜索和facet参数来指示与区域关联的搜索或facet。 此类功能可让软件在隐藏区域时跳过搜索或彩块化，从而提高搜索时间性能。 高度和宽度属性是可选的，用于配置在删除区域时占位符在可视规则生成器中的显示方式。 </p> <p> 使用<span class="codeph"> guided-if-facet[-not]-visible </span>标记，而不是尽可能使用区域。 它简化了演示文稿模板。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-zone gsname="zone area"&gt; &lt;guided-else-zone&gt; &lt;/guided-if-zone&gt; </span> </p> </td> 
   <td colname="col2"> <p>这组标记允许测试当前是否显示区域。 当您在页面上的其他位置有您仅希望在显示区域时显示的内容时，此功能非常有用。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 循环指示器{#section_387322CA0AA843A2ACF2795C328673E9}

您可以在以下任何循环块中使用以下每个循环指示符：

* 导向结果
* 向导化彩块化值
* 向导式痕迹导航
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
   <td colname="col2"> <p>当当前迭代是循环的第一次迭代时，此条件为true。 这不一定意味着第一个结果或第一页，而是显示的第一个结果。 如果站点访客位于每页10的结果集的第2页，则第一次迭代为结果11。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-last&gt;&lt;guided-else[-not]-last&gt; 
      &lt;/guided-if[-not]-last&gt; </code> </p> </td> 
   <td colname="col2"> <p>当当前迭代是循环的上次迭代时，此条件为true。 这不一定意味着最后一个结果或最后一页，而是当前上下文（页面）中显示的最后一个结果。 如果站点访客位于包含200个结果但每页仅有10个结果的结果集的第1页，则上次迭代的结果是结果10而不是结果200。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-odd&gt;&lt;guided-else[-not]-odd&gt; 
      &lt;/guided-if[-not]-odd&gt; </code> </p> </td> 
   <td colname="col2"> <p>当当前迭代是循环的奇数迭代时（与偶数迭代相比），此条件为true。 这对于显示不同的行颜色很有帮助。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-even&gt;&lt;guided-else[-not]-even&gt; 
      &lt;/guided-if[-not]-even&gt; </code> </p> </td> 
   <td colname="col2"> <p>当当前迭代为循环的偶次迭代时（与奇次迭代相比），此条件为true。 这对于显示不同的行颜色很有帮助。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-alt&gt;&lt;guided-else[-not]-alt&gt; 
      &lt;/guided-if[-not]-alt&gt; </code> </p> </td> 
   <td colname="col2"> <p>当当前迭代为循环的偶次迭代时，此条件为true。 这对于显示不同的行颜色很有帮助。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-inner&gt;&lt;guided-else[-not]-inner&gt; 
      &lt;/guided-if[-not]-inner&gt; </code> </p> </td> 
   <td colname="col2"> <p>如果当前小版本不是第一个小版本或最后一个小版本，则包括它们之间的文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-outer&gt;&lt;guided-else[-not]-outer&gt; 
      &lt;/guided-if[-not]-outer&gt; </code> </p> </td> 
   <td colname="col2"> <p>如果当前小版本是第一个或最后一个，则包括它们之间的文本。 </p> </td> 
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

## 其他语言{#section_BFE8DC98E26F4D7BB60FEC54D9A5DC6C}

以下标签可用于让您使用模板执行更高级的操作，例如构建自己的微型facet。

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
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng, 2/1/2013--> <span class="codeph"> &lt;guided-current-path&gt; </span> </p> </td> 
   <td colname="col2"> <p>为您提供当前使用的路径。 通常，它用于创建一个链接，将新参数添加到现有搜索。 默认情况下，路径为URL转义。 您可以通过转义参数指定要使用的转义模式。 </p> <p>示例： </p> <p> <code class="syntax html"> &lt;a&nbsp;href="&lt;guided-current-path&nbsp;/&gt;&amp;lang=fr"&gt; 
      French&nbsp;Version </code> </p> <p>在此示例中，搜索处理规则使用lang来选择法语版本。 </p> <p>当前路径始终至少具有一个查询参数。 如果不存在其他查询参数，则将其设置为<span class="codeph"> q=* </span>，以便更轻松地添加更多参数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> 基本路径  </span> </p> </td> 
   <td colname="col2"> <p> 如果要使用基路径创建链接，请在<span class="codeph"> href </span>开始使用<span class="codeph"> / </span>并添加参数。 </p> <p> <code class="syntax html"> &lt;a&nbsp;href="/"&gt;All&nbsp;Products&lt;/a&gt; 
      Would&nbsp;create&nbsp;a&nbsp;link&nbsp;"All&nbsp;Products"&nbsp;to&nbsp;your 
      basepath,&nbsp;for&nbsp;example&nbsp;https://search.mycompany.com/ 
       </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng, 2/1/2013--> <span class="codeph"> &lt;guided-query-param gsname="query_parameter"&gt; </span> </p> </td> 
   <td colname="col2"> <p>允许您获取URL上的查询参数的现有值。 如果参数不存在，则此标签返回空字符串。 如果未指定转义选项，则返回的字符串将自动转义为HTML转义，则可以指定HTML转义或URL转义。 </p> <p>示例： </p> <p> 

    &amp;lt;guided-查询-param&amp;nbsp;gsname=&quot;q&quot;&amp;nbsp;/&amp;gt;
    给&amp;nbsp;&amp;nbsp；值&amp;nbsp;pants
    
    &amp;lt;guid-查询-param&amp;n;gsname=&quot;lang&quot;&amp;nbsp;/&amp;gt；给&amp;nbsp;
    给&amp;nbsp;nbsp;en
    
    &amp;lt;gsname=&quot;test&quot;&amp;nbsp;/&amp;gt;
    提供&amp;nbsp;&amp;nbsp；空&amp;nbsp；字符串
    &amp;nbsp;
    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;   &lt;/p>  &lt;/td>
</tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-query-param-name gsname="param#" offset="offset_number" /&gt; </span> </p> </td> 
   <td colname="col2"> <p>“导向搜索”具有查询号的概念，该编号用于痕迹导航控件。 <span class="codeph"> guided-查询-param-name允许您将参 </span> 数定义为演示文稿模板中链接的一部分，在该链接中，“向导搜索”会为您绘制出正确的查询编号。<span class="codeph"> gsname </span>中有一个“x”，“向导式搜索”将替换为正确的数字。 偏移值可以是0 - 15，其中0表示使用下一个可用查询号。 A 1表示您要向它添加1，依此类推。 </p> <p>与<span class="codeph"> gived-current-path </span>相结合，您可以构建自己的微型facet链接或允许额外的向下钻取级别。 </p> <p>示例： </p> <p> <code class="syntax html"> &lt;a&nbsp;href="&lt;guided-current-path 
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
   <td colname="col2"> <p> 允许您包含其他模板文件。 此功能意味着您可以使用子模板作为模块创建多个模板。 </p> <p>在以下示例中，包含<span class="filepath">痕迹导航</span>和<span class="filepath"> facets </span>文件： </p> <p> <code class="syntax html"> &lt;guided-include&nbsp;gsfile='breadcrumbs.tmpl'&nbsp;/&gt; 
      &lt;guided-include&nbsp;gsfile='facets.tmpl'&nbsp;/&gt; </code> </p> <p>不支持动态包含。 换句话说，<span class="codeph"> gsfile </span>不能是变量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 1/17/2013--> <span class="codeph"> &lt;guided-search-time&gt; </span> </p> </td> 
   <td colname="col2"> <p> 确定搜索所花的时间。 返回的搜索时间值以毫秒为单位指定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 1/17/2013--> <span class="codeph"> &lt;guided-fall-through-searches&gt; </span> </p> </td> 
   <td colname="col2"> <p> 返回用于生成搜索结果页面的核心搜索计数。 </p> </td> 
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
   <td colname="col2"> <p>当当前迭代为循环的偶次迭代时（与奇次迭代相比），此条件为true。 这对于显示不同的行颜色很有帮助。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-alt&gt;&lt;guided-else[-not]-alt&gt; 
      &lt;/guided-if[-not]-alt&gt; </code> </p> </td> 
   <td colname="col2"> <p>当当前迭代为循环的偶次迭代时，此条件为true。 这对于显示不同的行颜色很有帮助。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-inner&gt;&lt;guided-else[-not]-inner&gt; 
      &lt;/guided-if[-not]-inner&gt; </code> </p> </td> 
   <td colname="col2"> <p>如果当前小版本不是第一个小版本或最后一个小版本，则包括它们之间的文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-outer&gt;&lt;guided-else[-not]-outer&gt; 
      &lt;/guided-if[-not]-outer&gt; </code> </p> </td> 
   <td colname="col2"> <p>如果当前小版本是第一个或最后一个，则包括它们之间的文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-first-search&gt;&lt;guided-else-first-search&gt; 
      &lt;/guided-if-first-search&gt; </code> </p> </td> 
   <td colname="col2"> <p>允许您检查是否进行初始搜索(查询是搜索框中搜索的结果)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-search-url /&gt; </span> </p> </td> 
   <td colname="col2"> <p>您可以在模板中使用此标记，以免硬编码搜索表单的操作。 它会检测您何时处于“暂存”或“实时”环境，并相应地进行更改。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-query-param-defined gsname="query_parameter"&gt; &lt;guided-else-query-param-defined&gt; &lt;/guided-if-query-param-defined&gt; </span> </p> </td> 
   <td colname="col2"> <p>这组标签允许您测试在搜索路径中定义的CGI参数。 只有在定义了参数的值时，才能测试这些参数的值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-next-query-number&gt; </span> </p> </td> 
   <td colname="col2"> <p>驱动模板的引导式搜索引擎的概念是浮动查询号，引擎生成的每个新链接都使用下一个可用查询号。 通过此标签，您可以获取下一个查询号或偏移，以便构建可钻取到结果集的自定义链接。 偏移允许您偏移到下一个查询编号。 例如，如果您选择了一个彩块化，则下一个查询编号为2，偏移量为1，则返回的查询编号为3。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-custom-var gsname="custom_variable"&gt; </span> </p> </td> 
   <td colname="col2"> <p>允许您获取处理规则定义的自定义变量的现有值。 如果未指定转义选项，则返回的字符串将自动转义为HTML转义，则可指定<span class="codeph"> html </span>、<span class="codeph"> url </span>、<span class="codeph"> js </span>或<span class="codeph"> 0 </span>。 如果您使用处理规则将传入的CGI参数复制到自定义变量，然后在模板中显示或使用该变量，并将转义设置为none或js，那么您可以在搜索中创建XSS漏洞。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-custom-var-defined gsname="custom_variable"&gt; &lt;guided-else-custom-var-defined&gt; &lt;/guided-if-custom-var-defined&gt; </span> </p> </td> 
   <td colname="col2"> <p>在处理规则(查询清除、搜索前处理和搜索后处理)中定义自定义变量时启用测试。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-general-field gsname="searchname" field="fieldname"&gt; </span> </p> </td> 
   <td colname="col2"> <p>允许您显示传输模板中定义的常规字段的内容。 如果未指定转义选项，则返回的字符串将按照您在该字段的传输模板中指定的格式进行编码。 指定转义选项适用于编码字段的任何格式（如传输模板中）。 您可以指定<span class="codeph"> html </span>、<span class="codeph"> url </span>、<span class="codeph"> js </span>、<span class="codeph"> json </span>或<span class="codeph"> 0 </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>20 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-general-field gsname="searchname" field="fieldname"&gt; &lt;guided-else-general-field&gt; &lt;/guided-if-general-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>启用测试，如果传输模板中定义的常规字段的内容存在。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>21 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-cookie-value gsname="cookie_name"&gt; </span> </p> </td> 
   <td colname="col2"> <p>允许您获取Cookie的值（假定Cookie可用）。 如果未指定转义选项，则返回的字符串将自动转义为HTML转义，则可指定<span class="codeph"> html </span>、<span class="codeph"> url </span>、<span class="codeph"> js </span>、<span class="codeph"> json </span>或<span class="codeph"> 0 </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>22 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-cookie gsname="cookie_name"&gt; &lt;guided-else-cookie&gt; &lt;/guided-if-cookie&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果Cookie存在，则启用测试。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>23 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-banner gsname="banner area"&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出给定区域的横幅。 可视规则生成器中使用可选的宽度和高度属性，以显示有意义的占位符，以便用户选择横幅。 默认情况下，横幅不会转义。 而是要将HTML插入演示文稿模板。 但是，如果要构建JSON模板，请考虑使用js转义选项。 </p> <p>示例： </p> <p> <code class="syntax html"> &lt;guided-banner&nbsp;gsname="top"&nbsp;width="400px" 
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
   <td colname="col2"> <p>允许您检测是否有任何引用<span class="keyword"> Adobe Target </span>活动的业务规则。 它通常用作与<span class="keyword"> Adobe Target </span>集成的一部分，以防止在不需要时对<span class="keyword"> 目标 </span>服务器进行攻击。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>27 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-redirect /&gt; </span> </p> </td> 
   <td colname="col2"> <p>默认情况下，会自动执行重定向。 但是，如果您已配置网站搜索/促销以将XML或JSON响应返回到Web应用程序，则可以选择在Web应用程序中分析302/301响应，或将重定向作为结果集的一部分传递到您。 如果您作为结果集的一部分传递重定向，则可以在模板中使用此标记来输出重定向位置。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>28 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-redirect&gt; &lt;guided-else-redirect&gt; &lt;/guided-if-redirect&gt; </span> </p> </td> 
   <td colname="col2"> <p>当您已配置网站搜索/促销以在结果集中返回重定向时，此标签集可用于确定是否存在指向输出的重定向。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>29 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-lt /&gt; &lt;guided-gt /&gt; </span> </p> </td> 
   <td colname="col2"> <p>这组标签允许您在HTML属性中嵌入引导模板标签。 </p> <p>示例： </p> <p> <code class="syntax html"> &lt;guided-lt/&gt;div&nbsp;&lt;guided-if-facet-long&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;style="height:&nbsp;125px;&nbsp;overflow: 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;auto;"&lt;/guided-if-facet-long&gt;&lt;guided-gt/&gt; </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 传输模板标签{#reference_227D199F5A7248049BE1D405C0584751}

传输模板是XML模板，可将数据从后端搜索传递到引导搜索表示层。

<!-- 

r_transport_template_tags.xml

 -->

在您的表示层中，您可以有一个表示多个搜索结果的表示模板。 每个搜索可以使用相同的传输模板或自定义传输模板将数据传递到表示层。

由于传输模板仅用于将数据传递到表示层，因此它没有任何与显示搜索结果相关的HTML。 传输模板使用传输模板XML标记传递搜索结果以填充“导向搜索”组件，如彩块化、痕迹导航和菜单。 在这些标记中，标准搜索模板标记用于显示实际值。

请参阅[编辑演示文稿或传输模板](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3)。

请参阅[搜索模板标记](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

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
   <td colname="col2"> <p>表示层用来检测从传输模板中分析的内容的根XML标签。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;general&gt;&lt;/general&gt; </span> </p> </td> 
   <td colname="col2"> <p>标记环绕搜索模板标记，这些标记根据结果集提供摘要数据。 通常，这些标签包含搜索标签，用于查找结果总数、较低结果和最高结果。 您可以使用<span class="codeph"> general-field </span>标记定义所需的任意数量的附加全局字段，如下例所示： </p> <p> <code class="syntax html"> &lt;general&gt; 
      &nbsp;&nbsp;&lt;total&gt;&lt;search-total&nbsp;/&gt;&lt;/total&gt; 
      &nbsp;&nbsp;&lt;lower&gt;&lt;search-lower&nbsp;/&gt;&lt;/lower&gt; 
      &nbsp;&nbsp;&lt;upper&gt;&lt;search-upper&nbsp;/&gt;&lt;/upper&gt; 
      &nbsp;&nbsp;&lt;general-field&nbsp;name="my_custom_field"&gt;Some&nbsp;global&nbsp;content&lt;/general-field&gt; 
      &lt;/general&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;results&gt;&lt;/results&gt; </span> </p> </td> 
   <td colname="col2"> <p>搜索结果周围会包含标记，以便“向导式搜索”知道在何处查找它们。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result&gt;&lt;/result&gt; </span> </p> </td> 
   <td colname="col2"> <p>每个搜索结果周围都包含标签，因此“向导式搜索”可识别单个搜索结果开始和结尾的内容的位置，如以下示例中所示： </p> <code class="syntax html"> &lt;results&gt; 
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
   <td colname="col2"> <p>允许您在多值列表中循环查看每个项目，以获得单个结果。 仅在结果中使用此标记。 其目的是让您对属于结果字段的属性进行迭代，如下例所示： </p> <code class="syntax html"> &lt;results&gt; 
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
   <td colname="col2"> <p>对填充彩块化的结果进行传递。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <!--NEW 2/27/2014--> <span class="codeph"> &lt;dynamic-facet&gt;&lt;/dynamic-facet&gt; </span> </p> </td> 
   <td colname="col2"> <p> 可以将一个facet指定为动态facet和facet边栏的成员。 但是，在相关的演示模板标签方面，他们的待遇是独立的。 </p> <p>换句话说，不允许在动态facet循环上下文中嵌套facet边栏循环上下文，反之亦然。 </p> <p>对于既是动态的又是有栏的彩块化，只有为给定搜索返回的那些动态彩块化才会显示在彩块化循环上下文中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet name="name"&gt;&lt;/facet&gt; </span> </p> </td> 
   <td colname="col2"> <p> 每个facet都有其自己的facet标签，其中name参数与facet名称匹配。 搜索标记在facet值的facet标记中使用，如以下示例中所示： </p> <code class="syntax html"> &lt;facets&gt; 
     &nbsp;&nbsp;&lt;facet&nbsp;name="brand"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
     &nbsp;&nbsp;&lt;/facet&gt; 
     &nbsp;&nbsp;&lt;facet&nbsp;name="category"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
     &nbsp;&nbsp;&lt;/facet&gt; 
     &lt;/facets&gt; </code> <p> 使用开槽彩块化的帐户可以使用动态标记和显示名称标记。 这两个标签都有助于在创建业务规则时简化时隙彩块化和实际彩块化之间的映射。 </p> <code class="syntax html"> &lt;facets&gt; 
     &nbsp;&nbsp;&lt;facet&nbsp;name="facet_values01"&gt; 
     &nbsp;&lt;dynamic&gt;1&lt;/dynamic&gt; 
     &nbsp;&lt;display-names&gt;&lt;search-field-value-list&nbsp;name="facet_names01"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/display-names&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="facet_values01"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="facet_values01"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
     &nbsp;&nbsp;&lt;/facet&gt; </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field separator=","&gt; </span> </p> </td> 
   <td colname="col2"> <p>通过<span class="codeph">分隔符</span>属性，可以更改在输出列表的search-display-field数据时使用的分隔符。 默认值为逗号。 </p> <p>通常，您使用的分隔符应是字段内容中不易显示的内容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;suggestions&gt;&lt;/suggestions&gt; </span> </p> </td> 
   <td colname="col2"> <p> 将您的意思所在的建议用标签包装起来，以便“向导式搜索”能够识别哪些XML节点包含建议。 </p> <p>请参阅<a href="../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E" type="concept" format="dita" scope="local">关于 Did You Mean</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;suggestion&gt;&lt;/suggestion&gt; </span> </p> </td> 
   <td colname="col2"> <p>将每个“您的意思”建议与标签一起换行，如下例所示： </p> <code class="syntax html"> &lt;search-if-suggestions&gt; 
     &nbsp;&nbsp;&lt;suggestions&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;search-suggestions&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;suggestion&gt;&lt;search-suggestion-text&nbsp;/&gt;&lt;/suggestion&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-suggestions&gt; 
     &nbsp;&nbsp;&lt;/suggestions&gt; 
     &lt;/search-if-suggestions&gt; </code> <p>请参阅<a href="../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E" type="concept" format="dita" scope="local">关于 Did You Mean</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 搜索模板标记{#reference_F7AA3FF602314E42842BBC740D2CA1A4}

搜索模板是包含网站搜索/促销所定义的模板标记的HTML文件。 这些标记指示搜索结果的格式。 以下参考包含每个搜索模板标记及其属性的简短说明。

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
* [字段值列表循环标签](../c-appendices/c-templates.md#section_0717FA09F0FC449CB916883B0500A60E)
* [建议标记](../c-appendices/c-templates.md#section_C28EB8B4F7DC4E278A0F143BCFEEB1AC)
* [模板字符串标签](../c-appendices/c-templates.md#section_67E3D529661F4F03A1FF469D9D658CAF)
* [模板锚点链接标记](../c-appendices/c-templates.md#section_3A51D27616C541E2B818CC52B2B856BA)
* [模板条件标记](../c-appendices/c-templates.md#section_18D9BC66DE484881932FD2F7EA9D170D)
* [模板表单控件标签](../c-appendices/c-templates.md#section_45AFC414ACA74825B72FEAA8456F8DD2)

搜索模板引用主题

* [日期格式字符串](../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4)
* [语言标识符](../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911)
* [指定内容类型HTTP头](../c-appendices/c-templates.md#section_AEED823E9938448A9EDB2F286D9CFD90)
* [在HTML模板中指定字符集](../c-appendices/c-templates.md#section_E0D1816ABB5846BEBE9C26D5980CCBE6)
* [在XML模板中指定字符集](../c-appendices/c-templates.md#section_17DC31CDCC104F5F8081466B41A96E9D)
* [在其他模板中包含搜索模板](../c-appendices/c-templates.md#section_7D1FCD3D9E2340C291E354C9720E8BC0)

## 关于结果循环标签{#section_D4DC7B4560144663972E8DBC3369C629}

结果循环标签是模板系统的主要功能。 在搜索过程中遇到标记时，会重复该HTML，并在开始和结束结果循环标记之间重复其他标记，用搜索结果替换任何其他标记。

`<search-results> ... </search-results>`

显示搜索结果的HTML周围有结果循环标签。 标记之间的HTML会针对每个结果重复，并显示在页面上。

以下标记仅在结果循环中有效：

* [结果循环字符串标签](../c-appendices/c-templates.md#section_80D68334E8D04A33937A6E58ABAAA320)
* [结果循环条件标签](../c-appendices/c-templates.md#section_35C367969E384A06A9865E388F1F9360)
* [结果循环锚点链接标签](../c-appendices/c-templates.md#section_C5FAEF520E9E42ADAD1F90651922AA02)
* [循环位置条件标签](../c-appendices/c-templates.md#section_E0C29DDA09E043C9A396F36334F05EBB)

## 结果循环字符串标签{#section_80D68334E8D04A33937A6E58ABAAA320}

以下标签返回一个字符串。

请参阅[关于结果循环标签](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629)。

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
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-index&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回当前结果的数值索引。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-title length="XX"&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回当前结果的页面标题。 可选length属性用于限制显示的字符串长度，默认值为80个字符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-bodytext length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回从页面顶部开始的正文文本。 相关术语以粗体显示。 可选length属性用于限制显示的字符串长度，默认值为80个字符。 编码属性是可选的，它可以使用HTML编码（默认）、Javascript编码、Perl编码或无编码对输出字符进行编码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-description length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p> 返回当前结果的描述。 如果meta description标签存在且内容属性不为空，则显示该文本。 否则，将显示页面正文文本的开头。 可选length属性用于限制显示的字符串长度，默认值为80个字符。 </p> <p>可选的<span class="codeph">编码</span>属性控制输出是否是HTML编码、JavaScript编码、Perl编码、URL编码或未编码，以在结果页上输出。 <span class="codeph">编码</span>的默认值为<span class="codeph"> html </span>。 通常，您无需指定编码属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-score rank="dynamic/static/dynamic-raw/static-raw/final-raw" precision="XX"&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回当前结果的得分，即数字0 - 100。 如果您已在<span class="uicontrol">选项</span> &gt; <span class="uicontrol">元数据</span> &gt; <span class="uicontrol">定义</span>下定义了排名字段，则可以通过将排名属性设置为动态(<span class="codeph"> &lt;search-score rank="dynamic"&gt; </span>)来显示动态页面排名。 通过将rank属性设置为static(<span class="codeph"> &lt;search-score rank="static"&gt; </span>)，可显示静态页面排名。 您可以使用可选的precision属性指定要显示的小数位数。 默认值为0，显示整数得分)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-date length="XX" none="text" date-format="date-format-string" gmt="yes/no" language="0/2/language-id"&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回当前结果的日期。 如果没有与当前结果关联的日期，则显示可选的“无”文本值。 如果未提供可选的“无”值，则如果没有与当前结果关联的日期，则显示文本“无日期”。 </p> <p>"date-format"属性采用UNIX样式的日期格式字符串，如"%A， %B %d， %Y"（对于"2016年7月25日，星期一"）。 "gmt"默认为"yes"，并控制日期字符串的时间部分应以GMT("yes")或帐户的时区("no")输出。 </p> <p>“language”属性控制输出日期字符串的语言和区域设置约定。 “0”（默认）是指“使用帐户语言”。 “2”指“使用文档语言”。 "语言"值"1"保留供将来使用。 任何其他“语言”值都解释为特定语言标识符，例如，“en_US”表示“英语（美国）”。 </p> <p>可选length属性用于限制显示的字符串长度，默认值为80个字符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-size&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回当前结果的大小（以字节为单位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-url length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回当前结果的URL。 </p> <p>使用可选的<span class="codeph"> length </span>属性限制显示的字符串长度，默认字符数不限。 </p> <p><span class="codeph">编码</span>属性是可选的，它可以使用HTML编码、Javascript编码、Perl编码或无编码对输出字符进行编码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-url-path-query length="XX"&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回路径和查询部分，包括当前结果URL的问号。 </p> <p>使用可选的<span class="codeph"> length </span>属性限制显示的字符串长度，默认字符数不限。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-context length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回搜索词的下一行上下文。 相关术语以粗体显示。 重复调用此标记可显示当前结果的多个上下文行。 </p> <p>使用可选的<span class="codeph"> length </span>属性限制显示的字符串长度，默认值为80个字符。 如果此标签由<span class="codeph"> &lt;search-if-context&gt; </span>或<span class="codeph"> &lt;search-if-any-context&gt; </span>标签集包含，则忽略<span class="codeph">长度</span>属性。 </p> <p><span class="codeph">编码</span>属性是可选的，它可以使用HTML编码（默认）、Javascript编码、Perl编码或无编码对输出字符进行编码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field name="field-name" length="XX" none="text" date-format="date-format-string" gmt="yes/no" language="0/2/language-id" encoding="html/javascript/json/perl/url/none" quotes="yes/no" commas="yes/no" units="miles/kilometers" separator="|"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此高级标记显示当前结果中在<span class="codeph">名称</span>属性中指定的选项</span> &gt; <span class="uicontrol">元数据</span> &gt;定义)下定义的元数据字段(url、标题、desc、键、目标、正文、alt、日期、字符集和语言或字段)的内容。 <span class="uicontrol">例如： </span></p> <p> <span class="codeph"> &lt;search-display-field name="title" length="70" none="no title"&gt; </span> </p> <p>输出搜索结果的页面标题。 如果未指定可选的<span class="codeph"></span>属性，则仅当没有与字段关联的内容时，其值才会显示在结果页上。 </p> <p><span class="codeph"> date-format </span>、<span class="codeph"> gmt </span>和<span class="codeph">语言</span>属性仅在指定字段的内容类型为<span class="codeph"> date </span>时才相关。 </p> <p><span class="codeph"> date-format </span>属性采用UNIX样式日期格式字符串，如<span class="codeph"> %A、%B %d、%Y </span>（2016年7月25日星期一）。 <span class="codeph"> gmt </span> 默 <span class="codeph"> 认为 </span> 是，并控制日期字符串的时间部分是以GMT（是）输 <span class="codeph"> 出 </span>还是帐户的时区( <span class="codeph"> 否 </span>)输出。 </p> <p>请参阅<a href="../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4" type="section" format="dita" scope="local">日期格式字符串</a>。 </p> <p><span class="codeph">语言</span>属性控制输出日期字符串的语言和区域设置约定。 <span class="codeph"> 0( </span> 默认)是指“使用帐户语言”。<span class="codeph"> 2 </span> 表示“使用文档语言”。<span class="codeph">语言</span>值<span class="codeph"> 1 </span>保留供将来使用)。 任何其他<span class="codeph">语言</span>值都解释为特定语言标识符，例如，<span class="codeph"> en_US </span>表示“英语（美国）”。 </p> <p>请参阅<a href="../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911" type="section" format="dita" scope="local">语言标识符</a>。 </p> <p>可选的<span class="codeph"> length </span>属性用于限制显示的字符串长度，默认值为80个字符。 </p> <p>可选的<span class="codeph">编码</span>属性控制输出是否是HTML编码、JavaScript编码、Perl编码、URL编码或未编码，以在结果页上输出。 <span class="codeph">编码</span>的默认值为<span class="codeph"> html </span>。 通常，您无需指定编码属性。 </p> <p>可选<span class="codeph">引号</span>属性控制各个项输出是否用多次引号（或单引号，如果<span class="codeph"> encoding=perl </span>）括起来。 <span class="codeph">引号</span>的默认值为<span class="codeph"> no </span>。 </p> <p>可选的<span class="codeph">逗号</span>属性控制各个项目输出是否以逗号分隔。 <span class="codeph">逗号</span>的默认值为<span class="codeph">是</span>。 对于非列表类型字段，将忽略<span class="codeph">逗号</span>属性。 </p> <p>可选的<span class="codeph">单位</span>属性控制应用于邻近搜索输出字段的距离单位。 <span class="codeph">单位</span>的默认值由与给定邻近搜索输出字段关联的位置类型字段的“默认单位”设置确定。 </p> <p>请参阅<a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local">关于proximity search</a>。 </p> <p>可选的<span class="codeph">分隔符</span>属性定义在列表类型字段的输出值之间插入的单个字符或分隔符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-values name="field-name"&gt; ...&lt;search-display-field-values&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签创建一个循环，用于枚举当前结果的元数据字段值（url、title、desc、keys、body、alt、date、charset和在<span class="uicontrol">选项</span> &gt; <span class="uicontrol">元数据</span> &gt; <span class="uicontrol">定义</span>下定义的语言或字段）。 请勿将此标记嵌套在另一个<span class="codeph"> &lt;search-display-field-values&gt; </span>标记中。 <span class="codeph">名称</span>属性指定包含要枚举的值的字段的名称。 对于已选中<span class="uicontrol">允许列表</span>属性的字段，此标签最有用（在<span class="uicontrol">选项</span> &gt; <span class="uicontrol">元数据</span> &gt; <span class="uicontrol">定义</span>下）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-value date-format="date-format-string" gmt="yes/no" language="0/language-id" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签输出当前<span class="codeph"> &lt;search-display-field-values&gt; </span>循环迭代的元数据字段值(url、title、desc、keys、目标、body、alt、date、charset和在<span class="uicontrol">选项</span> &gt; <span class="uicontrol">元数据</span> &gt; <span class="uicontrol">定义</span>下定义的语言或字段。 此标记仅在<span class="codeph"> &lt;search-display-field-values&gt; </span>循环内有效。 <span class="codeph"> date-format </span>、<span class="codeph"> gmt </span>和<span class="codeph">语言</span>属性仅在封闭<span class="codeph"> &lt;search-display-field-values&gt; </span>标签中指定字段名称的内容类型为<span class="codeph"> date </span>时才相关。 <span class="codeph"> date-format </span>属性采用UNIX样式日期格式字符串，如<span class="codeph"> "%A </span>, <span class="codeph"> %B </span> <span class="codeph"> %d </span>, <span class="codeph"> %Y </span>"（201年7月25日，星期一）6”)。 <span class="codeph"> gmt </span>属性默认为<span class="codeph">是</span>，并控制日期字符串的时间部分是以GMT（<span class="codeph">是</span>）输出还是以帐户的时区（<span class="codeph">否</span>）输出。 </p> <p><span class="codeph">语言</span>属性控制输出日期字符串的语言和区域设置约定。 <span class="codeph"> 0( </span> 默认)是指“使用帐户语言”。任何其他<span class="codeph">语言</span>值都解释为特定语言标识符，例如，<span class="codeph"> en_US </span>表示“英语（美国）”。 </p> <p>可选的<span class="codeph">编码</span>属性控制输出是否是HTML编码、JavaScript编码、Perl编码、URL编码或未编码，以在结果页上输出。 <span class="codeph">编码</span>的默认值为<span class="codeph"> html </span>。 通常，您无需指定编码属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-value-count name="field-name"&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出当前结果中使用名称属性指定的元数据字段（url、title、desc、keys、body、alt、date、charset和在<span class="uicontrol">选项</span> &gt; <span class="uicontrol">元数据</span> &gt; <span class="uicontrol">定义</span>下定义的语言或字段）的值总数。 此标签可显示在结果循环中的任意位置。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-value-counter&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出当前<span class="codeph"> &lt;search-display-field-values&gt; </span>循环迭代的序数计数器（1、2、3等）。 此标记仅在<span class="codeph"> &lt;search-display-field-values&gt; </span>循环内有效。 </p> </td> 
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
     <!--NEW for S&P 8.17.0 release on October 30 2014--> <span class="codeph"> &lt;search-result-trace encoding="html/javascript/ json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>输出与当前结果放置相关的信息，例如影响结果位置的任何基于结果的操作。 </p> <p>此标记的输出格式为JSON，如以下示例所示： </p> <p> <code> { 
      &nbsp;&nbsp;"sliceID":&nbsp;5, 
      &nbsp;&nbsp;"indexID":&nbsp;5894, 
      &nbsp;&nbsp;"finalScore":&nbsp;98.5, 
      &nbsp;&nbsp;"dynamicScore":&nbsp;15.3, 
      &nbsp;&nbsp;"staticScore":&nbsp;55.456, 
      &nbsp;&nbsp;"position":&nbsp;1, 
      &nbsp;&nbsp;"rbtaActionListID":&nbsp;117, 
      &nbsp;&nbsp;"rbtaActionID":&nbsp;57 
      } </code> </p> 
    <!--<p> Results added to the results set by way of <codeph>rbta</codeph> have a "naturalPosition" value of -1. </p>--> <p><span class="codeph">编码</span>属性是可选的；默认值为<span class="codeph"> html </span>。 </p> <p> <p>注意： 仅当使用核心搜索查询参数指定了<span class="codeph"> sp_trace=1 </span>时，此标签才具有输出。 </p> </p> <p>请参见<a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" format="dita" scope="local">后端搜索CGI参数</a>中的表中的第48行。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 结果循环条件标签{#section_35C367969E384A06A9865E388F1F9360}

以下标签有条件地包括它们之间的HTML。

请参阅[关于结果循环标签](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629)。

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
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-title&gt; ...  &lt;/search-if-title&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-title&gt; ...  &lt;/search-if-not-title&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果对<span class="codeph"> &lt;search-title&gt; </span>的下次调用从文档标题返回（或不返回）文本，则这些标签包括它们之间的HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-description length="XX"&gt; ... /search-if-description&gt;  </span> </p> <p> <span class="codeph"> &lt;search-if-not-description&gt; ...  &lt;/search-if-not-description&gt; </span> </p> </td> 
   <td colname="col2"> <p> 如果对<span class="codeph"> &lt;search-description&gt; </span>的下次调用从文档描述返回（或不返回）文本，则这些标签包括它们之间的HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-bodytext&gt; ...  &lt;/search-if-bodytext&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-bodytext&gt; ...  &lt;/search-if-not-bodytext&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果对<span class="codeph"> &lt;search-bodytext&gt; </span>的下次调用从文档正文返回（或不返回）文本，则这些标签包括它们之间的HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-context length="XX"&gt; ...  &lt;/search-if-context&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-context&gt; ...  &lt;/search-if-not-context&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果对<span class="codeph"> &lt;search-context&gt; </span>的下次调用返回（或不返回）非空的上下文字符串，则这些标签包括它们之间的HTML。 length属性覆盖任何封闭的<span class="codeph"> &lt;search-context&gt; </span>标签上的length属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-any-context length="XX"&gt; ... /search-if-any-context&gt;  </span> </p> <p> <span class="codeph"> &lt;search-if-not-any-context&gt; ...  &lt;/search-if-not-any-context&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果存在（或不存在）与结果关联的上下文字符串，则这些标签包括它们之间的HTML。 length属性覆盖任何封闭的<span class="codeph"> &lt;search-context&gt; </span>标签上的length属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-score lower="XX" upper="yy" rank="dynamic/static/dynamic-raw/static-raw/final-raw"&gt; ...  &lt;/search-if-score&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-score lower="XX" upper="yy" rank="dynamic/static"&gt; ...  &lt;/search-if-not-score&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果当前结果的得分介于XX和YY之间，则这些标签包括它们之间的HTML。 对于添加项目符号或图形以显示结果的相关性非常有用。 如果您已在<span class="uicontrol">选项</span> &gt; <span class="uicontrol">元数据</span> &gt; <span class="uicontrol">定义</span>下定义了排名类型字段，则可以通过将排名属性设置为动态(<span class="codeph"> &lt;search-if-score rank="dynamic" lower=XX upper=YY&gt; </span>)来检查动态页面排名。 通过将rank属性设置为static(<span class="codeph"> &lt;search-if-score rank="static" lower=XX upper=YY&gt; </span>)，可以检查静态页面排名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-field name="field-name" value="value"&gt; ...  &lt;/search-if-field&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-field name="field-name" value="value"&gt; ...  &lt;/search-if-not-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>这些高级标签包括它们之间的HTML，具体取决于在“name”属性中指定的字段是否包含内容。 如果指定了可选的“value”属性，则根据给定值是否与当前结果中字段的值匹配（或不匹配），标签将在它们之间包含HTML。 这些标签仅在结果循环中起作用（在<span class="codeph"> &lt;search-results&gt; </span>和<span class="codeph"> &lt;/search-results&gt; </span>标签之间）。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 结果循环锚点链接标签{#section_C5FAEF520E9E42ADAD1F90651922AA02}

请参阅[关于结果循环标签](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629)。

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
   <td colname="col1"> <p> <span class="codeph"> &lt;search-link target="frame-name" hbx-enable="yes/no" hbx-linkid-name="field-name" hbx-linkid-none="text" hbx-linkid-length="XX"&gt; ...  &lt;/search-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>这对标签在它们之间的HTML周围创建一个锚点链接。 单击链接时，将显示结果页。 可选的目标属性指定了指定的窗口，支持帧的浏览器应在其中显示结果页。 </p> <p>将hbx-enable属性设置为“是”，以利用通过HBX提供的分析。 将hbx-linkid-name设置为要跟踪的元数据字段的名称。 例如，要按SKU编号跟踪搜索结果，请将hbx-linkid-name设置为包含SKU信息的元数据字段的名称。 </p> <p>当前不支持日期类型字段。 hbx-linkid-name的值将附加到生成的锚点中的链接ID。 只要命名的元数据字段为空，就会将hbx-linkid-none属性的值附加到链接ID。 hbx-linkid-length的值限制从Meta标签中获取和显示的字符数。 默认的字符数为12。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-smart-link target="frame-name" hbx-enable="yes/no" hbx-linkid-name="field-name" hbx-linkid-none="text" hbx-linkid-length="XX"&gt; ...  &lt;/search-smart-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>这对标记与<span class="codeph"> &lt;search-link&gt; ... &lt;/search-link&gt; </span>标记类似。 单击生成的锚点链接时，将显示结果页，但该页滚动到结果前最近的锚点标签。 对于PDF链接，Acrobat查看器显示包含结果的页面。 可选的目标属性指定了指定的窗口，支持帧的浏览器应在其中显示结果页。 </p> <p>将hbx-enable属性设置为“是”，以利用通过HBX提供的分析。 将hbx-linkid-name设置为要跟踪的元数据字段的名称。 例如，要按SKU编号跟踪搜索结果，请将hbx-linkid-name设置为包含SKU信息的元数据字段的名称。 </p> <p>当前不支持日期类型字段。 hbx-linkid-name的值将附加到生成的锚点中的链接ID。 只要命名的元数据字段为空，就会将hbx-linkid-none属性的值附加到链接ID。 hbx-linkid-length的值限制从Meta标签中获取和显示的字符数。 默认的字符数为12。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-link-extension&gt; ...  &lt;/search-if-link-extension&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-link-extension&gt; ...  &lt;/search-if-not-link-extension&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果值属性指定的扩展与结果的URL结尾相匹配，则这些标签包括它们之间的HTML。 此标签对于在基于链接扩展的搜索结果中包含图形很有用。 value属性是一个或多个扩展（空格分隔）的列表，如下所示：VALUE="。pdf"或VALUE="。html .htm"。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 循环位置条件标签{#section_E0C29DDA09E043C9A396F36334F05EBB}

以下标记有条件地包括它们之间的文本。 它们只能显示在“循环”标记中：`search-results>`和`<search-field-values>`。 它们用于测试当前结果在结果集中的位置。

请参阅[关于结果循环标签](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629)。

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
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-first&gt; ...  &lt;/search-if-first&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-first&gt; ...  &lt;/search-if-not-first&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果当前结果是（或不是）页面上的第一个结果（在<span class="codeph"> &lt;search-results&gt; </span>中使用）或第一个字段值（在<span class="codeph"> &lt;search-field-values&gt; </span>中使用），则这些标签包括它们之间的文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-last&gt; ...  &lt;/search-if-last&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-last&gt; ...  &lt;/search-if-not-last&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果当前结果是（或不是）页面上的最后一个结果（在<span class="codeph"> &lt;search-results&gt; </span>中使用）或最后一个字段值（在<span class="codeph"> &lt;search-field-values&gt; </span>中使用），则这些标签包括它们之间的文本。 此标签可用于在结果之间插入分隔符。 例如，这会在结果之间插入一个<span class="codeph"> &lt;hr&gt; </span>标签： </p> <p> <code class="syntax html"> &lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&lt;search-lt&gt;tr&lt;search-if-alt&gt;&nbsp;class="alt"&lt;/search-if-alt&gt;&lt;search-gt&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td&gt;&lt;search-url&gt;&lt;/td&gt; 
      &nbsp;&nbsp;&nbsp;&lt;/tr&gt; 
      &lt;/search-results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-inner&gt; ...  &lt;/search-if-inner&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-inner&gt; ...  &lt;/search-if-not-inner&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果当前结果不是页面上的第一个或最后一个结果（在<span class="codeph"> &lt;search-results&gt; </span>中使用）或不是第一个或最后一个字段值（在<span class="codeph"> &lt;search-field-values&gt; </span>中使用），则这些标签包括它们之间的文本。 标签的not版本测试结果是第一个还是最后一个。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-alt&gt; ...  &lt;/search-if-alt&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-alt&gt; ...  &lt;/search-if-not-alt&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果当前结果是（或不是）页面上的替代结果（在<span class="codeph"> &lt;search-results&gt; </span>中使用）或替代字段值（在<span class="codeph"> &lt;search-field-values&gt; </span>中使用），则这些标签包括它们之间的文本。 “替代”结果是页面上的第二、第四、第六等。 此示例对替代表行应用不同的类。 请注意，使用<span class="codeph"> &lt;search-lt&gt; </span>和<span class="codeph"> &lt;search-gt&gt; </span>可允许将<span class="codeph"> &lt;search-if-alt&gt; </span>标签放在<span class="codeph"> &lt;tr&gt; </span>标签的“内部”。 </p> <p> <code class="syntax html"> &nbsp;&nbsp;&nbsp;&nbsp;&lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-lt&gt;tr&lt;search-if-alt&gt;&nbsp;class="alt"&lt;/search-if-alt&gt;&lt;search-gt&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td&gt;&lt;search-url&gt;&lt;/td&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/tr&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-even&gt; ...  &lt;/search-if-even&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-even&gt; ...  &lt;/search-if-not-even&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果当前结果是（或不是）偶数编号结果（在<span class="codeph"> &lt;search-results&gt; </span>中使用）或偶数编号字段值（在<span class="codeph"> &lt;search-field-values&gt; </span>中使用），则这些标签包括它们之间的文本。 如果搜索结果的<span class="codeph"> &lt;search-index&gt; </span>值为偶数，则搜索结果为偶数。 换句话说，如果它在整个结果集中的位置是均匀的。 这可能与<span class="codeph"> &lt;search-if-alt&gt; </span>不同，后者测试结果在页面上的位置，而不是在整个结果集中。 下面两个表说明了差异： </p> </td> 
  </tr> 
 </tbody> 
</table>

### 第一页，sp_n=1

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
   <td colname="col1"> <p>3 </p> </td> 
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
   <td colname="col1"> <p>1 </p> </td> 
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

### 稍后页，sp_n=10

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

最后，请注意，`<search-if-even>`始终与`<search-if-alt>`相同，因为字段值不分页。

## 字段值列表标签{#section_D3298B5F976447DBA0032B883DCC91B1}

以下高级标记输出字段值以及整个搜索结果集中的相关数据。 这些标签只针对搜索查询中的`sp-sfvl-field` CGI参数指定的字段生成输出。

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
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-list name="field-name" quotes="yes/no" commas="yes/no" data="values/counts/results" separator="X" sortby="none/values/counts/results" max-items="XX" date-format="date-format-string" gmt="yes/no" language="0/language-id" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签显示整个结果集中唯一字段值、值计数或结果计数的列表。 </p> <p>此标签仅生成由搜索查询中的<span class="codeph"> sp_sfvl_field </span> CGI参数指定的字段的输出。 可选的“quotes”属性控制各个项目输出是否用多次引号（或单引号，如果encoding=perl）括起来。 “quotes”的默认值为“yes”。 可选的“逗号”属性控制各个项目输出是否以逗号分隔。 “逗号”的默认值为“是”。 可选的"data"属性控制是输出每个唯一字段值(data="values")，输出每个唯一字段值的总计数(data="counts")，还是输出包含每个唯一值的结果数(data="results")。 “data”的默认值为“values”。 对于非列表类型字段，data="counts"和data="results"是等效的。 separator属性定义要插入输出值之间的单个字符或分隔符。 可选的“sortby”属性控制输出的顺序；sortby="none"表示没有特定顺序，sortby="values"表示按字段值排序（根据字段的“排序”属性按升序或降序排序），sortby="counts"表示按字段值计数的降序排序，sortby="results"表示按包含每个值的结果数的降序排序。 </p> <p>请注意，sortby="counts"和sortby="results"对于非列表类型字段是等效的。 可选的“max-items”属性限制要输出的项目数。 “max-items”的默认值为–1，表示“输出所有项目”。 </p> <p>最大项目的绝对限制为100。 仅当指定字段的内容类型为“date”时，“date-format”、“gmt”和“language”属性才相关。 "date-format"属性采用UNIX样式的日期格式字符串，如"%A， %B %d， %Y"（对于"2016年7月25日，星期一"）。 "gmt"默认为"yes"，并控制日期字符串的时间部分应以GMT("yes")或帐户的时区("no")输出。 </p> <p>请参阅<a href="../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4" type="section" format="dita" scope="local">日期格式字符串</a>。 </p> <p>“language”属性控制输出日期字符串的语言和区域设置约定。 “0”（默认）是指“使用帐户语言”。 任何其他“语言”值都解释为特定语言标识符，例如，“en_US”表示“英语（美国）”。 可选的“encoding”属性控制输出字符串字符是HTML编码、JavaScript编码、Perl编码、URL编码还是未编码，以在结果页上输出。 “encoding”的默认值为“html”。 </p> <p>请参阅<a href="../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911" type="section" format="dita" scope="local">语言标识符</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-list-count name="field-name" value="field-value" results="yes/no"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签显示给定搜索字段值列表的计数信息。 此标签有三种不同的用途。 如果仅提供“name”属性，则此标签输出整个结果集中命名字段的唯一值数。 如果同时提供"name"和"value"属性，则此标签输出整个结果集中给定值的总计数（对于results="no"），或包含整个结果集中给定值的结果总计数（对于results="yes"）。 “results”的默认值为“no”。 注意：对于非列表类型字段，results="yes"和results="no"是等效的。 如果未提供“value”属性，则忽略“results”的值。 此标签仅生成由搜索查询中的<span class="codeph"> sp-sfvl-field </span> CGI参数指定的字段的输出。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-field-value-list-count name="field-name" value="field-value"&gt; ...  &lt;/search-if-field-value-list-count&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-field-value-list-count name="field-name" value="field-value"&gt; ...  &lt;/search-if-not-field-value-list-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果对具有给定属性的<span class="codeph"> &lt;search-field-value-列表-count name="field-name" value="field-value"&gt; </span>的等效调用将（或不会）返回大于零的值，则这些标签会显示它们之间的HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-single-field-value-list-count name="field-name"&gt; ...  &lt;/search-if-single-field-value-list-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果对<span class="codeph"> &lt;search-field-value-列表-count name="field-name" value="field-value"&gt; </span>的等效调用（给定属性将返回或不返回）单个值，则这些标签会显示它们之间的内容。 这通常在帐户使用facet插槽时使用。 对于facet插槽，您通常只希望在关联的名称插槽具有单个项目时显示值插槽。 在传输模板中进行此检查比在表示层中进行检查更有效。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 字段值列表循环标签{#section_0717FA09F0FC449CB916883B0500A60E}

以下高级标签使用循环构造枚举和输出整个搜索结果集中的字段值和相关数据。 这些标签只针对搜索查询中的`sp-sfvl-field` CGI参数指定的字段生成输出。

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
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-values name="field-name" sortby="none/values/counts/results" max-items="XX"&gt; ...  &lt;/search-field-values&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签创建一个循环，用于枚举整个结果集中特定字段的字段值和相关数据。 请勿将此标记嵌套在另一个<span class="codeph"> &lt;search-field-values&gt; </span>标记中。 “name”属性指定包含要枚举的值的字段的名称。 可选的“sortby”属性控制明细列表顺序："none"表示没有特定顺序，"values"表示按字段值排序（根据字段的“排序”属性按升序或降序排序），sortby="counts"表示按字段值计数的降序排序，sortby="results"表示按包含每个值的结果数的降序排序。 </p> <p>请注意，sortby="counts"和sortby="results"对于非列表类型字段是等效的。. 可选的“max-items”属性将迭代次数限制为给定值。 “max-items”的默认值为–1，表示“枚举所有值”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value date-format="date-format-string" encoding="html/javascript/json/perl/url/none" gmt="yes/no" language="0/language-id"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签输出当前&lt;search-field-values&gt;循环迭代的字段值。 此标记仅在<span class="codeph"> &lt;search-field-values&gt; </span>循环内有效。 仅当封闭&lt;search-field-values&gt;标记中指定的字段名称的内容类型为"date"时，“date-format”、“gmt”和“language”属性才相关。 "date-format"属性采用UNIX样式的日期格式字符串，如"%A， %B %d， %Y"（对于"2020年7月25日，星期一"）。 </p> <p>请参阅<a href="../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4" type="section" format="dita" scope="local">日期格式字符串</a>。 </p> <p>可选的“encoding”属性控制输出字符串字符是HTML编码、JavaScript编码、Perl编码、URL编码还是未编码，以在结果页上输出。 “encoding”的默认值为“none”。 通常，您无需指定编码属性。 "gmt"默认为"yes"，并控制日期字符串的时间部分应以GMT("yes")或帐户的时区("no")输出。 “language”属性控制输出日期字符串的语言和区域设置约定。 “0”（默认）是指“使用帐户语言”。 任何其他“语言”值都解释为特定语言标识符，例如，“en_US”表示“英语（美国）”。 </p> <p>请参阅<a href="../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911" type="section" format="dita" scope="local">语言标识符</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-count results="yes/no"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签输出与当前<span class="codeph"> &lt;search-field-values&gt; </span>循环迭代关联的计数。 输出计数是包含字段值的整个结果集中的结果数（结果="yes"），或整个结果集中字段值的总计数。 “results”的默认值为“no”。 </p> <p>对于非列表类型字段，results="yes"和results="no"是等效的。 此标记仅在<span class="codeph"> &lt;search-field-values&gt; </span>循环内有效。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-counter&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签输出当前<span class="codeph"> &lt;search-field-values&gt; </span>循环迭代的序数计数器。 此标记仅在<span class="codeph"> &lt;search-field-values&gt; </span>循环内有效。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 建议标记{#section_C28EB8B4F7DC4E278A0F143BCFEEB1AC}

Sembley提供用户友好的“您是说吗？” 服务。 例如，如果用户拼写错误了搜索词，“建议”可以通过建议正确的拼写来帮助用户查找结果。 系统还可以建议相关关键字，以帮助用户发现结果。 在生成建议时，建议服务使用两个词典：一个基于帐户语言（设置在&#x200B;**[!UICONTROL Indexing]** > **[!UICONTROL Words and Languages]** > **[!UICONTROL Language]**&#x200B;下），另一个基于帐户索引中的关键字唯一构建。

>[!NOTE]
>
>“建议”服务不适用于中文、日文或韩文。

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
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-suggestions&gt; ...  &lt;/search-if-suggestions&gt; </span> </p> </td> 
   <td colname="col2"> <p>在这些标签周围添加任何“建议”模板标签，如<span class="codeph"> &lt;search-seccuption&gt; </span> 、 <span class="codeph"> &lt;search-seccuption-link&gt; </span>等。 如果搜索生成建议，则搜索引擎输出并处理开放标记和结束标记之间的所有内容。 如果搜索未生成建议，则不会输出任何嵌套内容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestions&gt; ...  &lt;/search-suggestions&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签生成“建议”循环，该循环包含建议搜索词的列表(例如，“打算”、“预期”和“打算”，对于最初输入为“意向”的查询)。 在生成术语列表时，搜索引擎最多重复五次任何嵌套的HTML和/或模板标记，这是建议的最大数目。 使用count属性指定生成的建议数（在0到5之间）。 </p> <p><span class="codeph"> &lt;search-sugmentiss&gt; </span>标记可在页面上多次显示以重复建议的列表。 根据每个结果的数量对多个建议进行排序。 </p> <p>将<span class="codeph"> &lt;search-segments&gt; </span>标记嵌套在open和close <span class="codeph"> &lt;search-if-segments&gt; </span>标记之间。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestion-link&gt; ...  &lt;/search-suggestion-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标记使用选定的建议搜索词而不是原始词生成指向原始搜索查询的链接。 标签接受并直接打印任何HTML属性，如类、目标和样式。 标记还可以接受URL属性，该属性的值用作生成链接的基本URL。 这些标记只能显示在<span class="codeph"> &lt;search-segmenties&gt; </span>循环中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestion-text /&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标签将打印出当前建议的查询词(例如，最初作为“意图”输入的查询的“打算”)。 标记没有属性，只能显示在<span class="codeph"> &lt;search-segcuments&gt; </span>循环中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-not-suggestions&gt; ...  &lt;/search-if-not-suggestions&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果搜索不生成任何建议，则搜索引擎输出并处理开放标记和结束标记之间的所有内容。 如果搜索生成建议，则不会输出任何嵌套内容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if&gt; ...  &lt;/search-if&gt; </span> </p> </td> 
   <td colname="col2"> <p>这些条件标签包括它们之间的HTML，具体取决于建议的术语是否是建议循环中的第一个术语。 标签必须显示在open和close <span class="codeph"> &lt;search-seccuption&gt; </span>标签之间。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if&gt; ...  &lt;/search-if&gt; </span> </p> </td> 
   <td colname="col2"> <p>这些条件标签包括它们之间的HTML，具体取决于建议的术语是否是建议循环中的最后一个术语。 标签必须显示在open和close <span class="codeph"> &lt;search-seccuption&gt; </span>标签之间。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestion-index&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标记返回当前建议搜索词的数值索引。 标记必须显示在open和close <span class="codeph"> &lt;search-seccuption&gt; </span>标记之间。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestion-total&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标记返回生成的建议搜索词的总数。 标记必须显示在open和close <span class="codeph"> &lt;search-seccuption&gt; </span>标记之间。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestion-result-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>此标记返回建议搜索词的结果总数。 标记必须显示在open和close <span class="codeph"> &lt;search-seccuption&gt; </span>标记之间。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 模板字符串标签{#section_67E3D529661F4F03A1FF469D9D658CAF}

以下标签在模板中该点将字符串输出到HTML中。

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
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-body&gt; </span> </p> </td> 
   <td colname="col2"> <p>具有“基本外观”部分在“模板”链接下设置的任何“搜索链接颜色”设置的HTML正文标签。 为此标签添加一个背景属性，以在结果页上显示背景图像。 添加到此标签的任何颜色属性都会覆盖“基本外观”部分设置的“搜索链接颜色”设置。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-header&gt; </span> </p> </td> 
   <td colname="col2"> <p>在“模板”链接下的“基本外观”部分中设置的“搜索结果标题”的HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-cdata&gt; ...  &lt;/search-cdata&gt; </span> </p> </td> 
   <td colname="col2"> <p>search-cdata标记被替换为其XML等效项：<span class="codeph"> &lt;search_cdata&gt; </span>替换为<span class="codeph"> &lt;![CDATA["和&lt;/search-cdata&gt; </span>标记替换为" <span class="codeph"> ]&gt; </span>"。 XML分析器不解析开放标签和关闭标签之间的任何信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-query query-number="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>访客输入的查询。 高级、可选的“查询编号”属性控制此标签输出带编号的查询字符串。 例如，<span class="codeph"> &lt;search-查询 查询-number=1&gt; </span>输出<span class="codeph"> sp_q_1 </span> cgi参数的内容。 如果未指定“查询编号”，或者查询编号为“0”，则输出主查询(<span class="codeph"> sp_q </span>)。 可选的“encoding”属性控制输出是否是HTML编码、JavaScript编码、Perl编码、URL编码或未编码，以在结果页上输出。 “encoding”的默认值为“html”。 通常，您无需指定编码属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-total&gt; </span> </p> </td> 
   <td colname="col2"> <p>此搜索的结果总数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>为此页面报告的结果计数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-lower&gt; </span> </p> </td> 
   <td colname="col2"> <p>为此页面报告的第一个结果的编号。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-upper&gt; </span> </p> </td> 
   <td colname="col2"> <p>为此页面报告的最后一个结果的数量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-prev-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>为上一页报告的结果数。 </p> </td> 
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
   <td colname="col2"> <p>为您的帐户配置的“搜索”徽标的HTML（如果有）。 此徽标是给予网站搜索/促销信誉的图像 </p> <p>目前，大多数帐户没有关联的搜索徽标。 </p> </td> 
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
   <td colname="col2"> <p>插入指定库编号的表单输入标签。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-query query-number="XX"&gt; </span> </p> </td> 
   <td colname="col2"> <p>插入指定查询字符串的表单输入标记。 高级、可选的“查询编号”属性控件用于表单输入标签的编号查询。 例如，<span class="codeph"> &lt;search-input-查询查询编号=1&gt; </span>输出<span class="codeph"> sp_q_1 </span>查询的表单输入标签。 如果未指定“查询编号”，或“查询编号”为“0”，则插入主<span class="codeph"> sp_q </span>查询的输入标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-collections all="name"&gt; </span> </p> </td> 
   <td colname="col2"> <p>插入一个表单选择标记和关联的HTML，用于显示集合选择菜单。 可选的“all”属性用于指定表示整个网站的集合的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-lt&gt; </span> </p> </td> 
   <td colname="col2"> <p>在结果页上的其他HTML或模板标记中插入一个“搜索”模板标记的输出。 <span class="codeph"> &lt;search-lt&gt; </span> 插入一个小于字符。使用<span class="codeph"> &lt;search-lt&gt; </span>和<span class="codeph"> &lt;search-gt&gt; </span>提供了一种对标记定义进行转义的方法，以便您可以使用Search模板标记作为属性值。 当响应搜索而呈现模板时，小于号(&lt;)将替换<span class="codeph"> &lt;search-lt&gt; </span>标签。 例如，<span class="codeph"> &lt;search-link&gt; </span>等效于<span class="codeph"> &lt;search-lt&gt; a href="&lt;search-url&gt;"&lt;search-gt&gt; </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>20 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-gt&gt; </span> </p> </td> 
   <td colname="col2"> <p>在结果页上的其他HTML或模板标记中插入一个“搜索”模板标记的输出。 <span class="codeph"> &lt;search-gt&gt; </span> 插入大于字符。使用<span class="codeph"> &lt;search-lt&gt; </span>和<span class="codeph"> &lt;search-gt&gt; </span>提供了一种方法，可以转义标记的定义，以便您可以使用其他模板标记作为属性值。 当响应搜索而渲染模板时，大于号(&gt;)将替换<span class="codeph"> &lt;search-gt&gt; </span>标记。 例如，<span class="codeph"> &lt;search-link&gt; </span>等效于<span class="codeph"> &lt;search-lt&gt; a href="&lt;search-url&gt;"&lt;search-gt&gt; </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>21 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-param name="param-name" length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回当前搜索请求中名为“param-name”的cgi参数的值。 可选的“encoding”属性控制输出是否是HTML编码、JavaScript编码、Perl编码、URL编码或未编码，以在结果页上输出。 “encoding”的默认值为“html”。 通常，您无需指定编码属性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>22 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release on October 30 2014--> <span class="codeph"> &lt;search-trace encoding="html/javascript/ json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> 
    <!--<p>This global core search template tag outputs a representation of the submitted core search query, including any "fuzzy-search" query term expansions that happen by way of synonyms, sound-alikes, and so forth. </p>--> <p><span class="codeph">编码</span>属性是可选的；默认值为<span class="codeph">json </span>。 </p> <p> <p>注意： 仅当使用核心搜索查询参数指定了<span class="codeph"> sp_trace=1 </span>时，此标签才具有输出。 </p> </p> <p>请参见<a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" format="dita" scope="local">后端搜索CGI参数</a>中的表中的第48行。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 模板锚点链接标签{#section_3A51D27616C541E2B818CC52B2B856BA}

以下是导致锚点链接环绕在它们之间的HTML周围的标签。 单击时，锚点链接会请求显示另一页结果。 可选属性“count”要求在页面上显示许多结果。 如果未指定，则使用当前页面上请求的计数。 高级的可选“URL”属性控制关联链接指向的域。 默认情况下，域为`https://search.atomz.com/search/`，但可以使用URL属性更改。

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
   <td colname="col1"> <p> <span class="codeph"> &lt;search-next URL="https://search.yourdomain.com/search/"&gt; ...  &lt;/search-next&gt; </span> </p> <p> <span class="codeph"> &lt;search-prev URL="https://search.yourdomain.com/search/"&gt; ...  &lt;/search-prev&gt; </span> </p> </td> 
   <td colname="col2"> <p>显示结果的下一页或上一页。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-sort-by-date URL="https://search.yourdomain.com/search/"&gt; ...  &lt;/search-sort-by-date&gt; </span> </p> <p> <span class="codeph"> &lt;search-sort-by-score URL="https://search.yourdomain.com/search/"&gt; ...  &lt;/search-sort-by-score&gt; </span> </p> </td> 
   <td colname="col2"> <p>按日期或相关性对结果排序。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-show-summaries URL="https://search.yourdomain.com/search/"&gt; ...  &lt;/search-show-summaries&gt; </span> </p> <p> <span class="codeph"> &lt;search-hide-summaries URL="https://search.yourdomain.com/search/"&gt; ...  &lt;/search-hide-summaries&gt; </span> </p> </td> 
   <td colname="col2"> <p>显示或隐藏摘要。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 模板条件标签{#section_18D9BC66DE484881932FD2F7EA9D170D}

用于在它们之间有条件地包含HTML的标记。

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
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-results&gt; ...  &lt;/search-if-results&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-results&gt; ...&lt;/search-if-not-results&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果当前页面包含任何（或不包含）搜索结果，则这些标签包含HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-prev-count&gt; ...  &lt;/search-if-prev-count&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-prev-count&gt; ...  &lt;/search-if-not-prev-count&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-next-count&gt; ...  &lt;/search-if-next-count&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-next-count&gt; ...  &lt;/search-if-not-next-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果上一页或下一页具有与其关联的任何（或无）结果，则这些标签包括HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-sort-by-score&gt; ...  &lt;/search-if-sort-by-score&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-sort-by-score&gt; ...  &lt;/search-if-not-sort-by-score&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-sort-by-date&gt; ...  &lt;/search-if-sort-by-date&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-sort-by-date&gt; ...  &lt;/search-if-not-sort-by-date&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果当前页面是否按相关性或日期排序，则这些标记包括HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-show-summaries&gt; ...  &lt;/search-if-show-summaries&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-hide-summaries&gt; ...  &lt;/search-if-hide-summaries&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果当前页面显示或隐藏摘要，则这些标签包含HTML。 您可以使用这些标记来包含或排除搜索结果的任何部分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-input-collections&gt; ...  &lt;/search-if-input-collections&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-input-collections&gt; ...  &lt;/search-if-not-input-collections&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果在生成当前页面的搜索结果时指定了集合，则这些标签包括HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-advanced&gt; ...  &lt;/search-if-advanced&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-advanced&gt; ...  &lt;/search-if-not-advanced&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果为搜索查询指定了<span class="codeph"> sp_advanced=1 </span> CGI参数，则这些标签包括HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-bad-param name="parameter-name"&gt; ...  &lt;/search-if-bad-param&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-bad-param name="parameter-name"&gt; ...  &lt;/search-if-not-bad-param&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果给定参数无效或无效，则这些标签会在它们之间包含或排除HTML。 </p> <p>目前仅支持<span class="codeph"> sp_q_location[_#] </span>参数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-param name="param-name" value="param-value"&gt; ...  &lt;/search-if-param&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-param name="param-name" value="param-value"&gt; ...  &lt;/search-if-not-param&gt; </span> </p> </td> 
   <td colname="col2"> <p>这些高级标签包括它们之间的HTML，这取决于在"name"属性中指定的CGI参数是否具有在"value"属性中指定的值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-sort-by-field name="field-name"&gt; ...  &lt;/search-if-sort-by-field&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-sort-by-field name="field-name"&gt; ...  &lt;/search-if-not-sort-by-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果当前页面是按给定字段名称排序的，或者不是按给定字段名称排序的，这些高级标签包括它们之间的HTML。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 模板表单控件标签{#section_45AFC414ACA74825B72FEAA8456F8DD2}

用于控制搜索模板上`<form>`中复选框、单选按钮和列表框的默认选择状态的标签。

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
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input&gt; </span> </p> </td> 
   <td colname="col2"> <p>在模板中用于代替<span class="codeph"> &lt;input&gt; </span>标记。 将标记写入浏览器时，单词<span class="codeph">输入</span>将替换<span class="codeph">搜索输入</span>，并且标记中的所有其他信息将按原样输出。 此外，如果标签中指定的<span class="codeph">名称</span>被列为CGI参数，并且标签中指定的<span class="codeph">值</span>是该CGI参数的值，则在标签末尾添加选中的<span class="codeph">词。 </span>这样，您可以自动使搜索结果中的默认单选按钮或复选框状态与当前查询相同。 </p> <p>例如，复选框的HTML代码可能如下所示： </p> <p> <span class="codeph"> &lt;input type="checkbox" name="sp_w" value="exact"&gt;无相似声音匹配  </span> </p> <p>该复选框的相应模板代码如下所示： </p> <p> <span class="codeph"> &lt;search-input type="checkbox" name="sp_w" value="exact"&gt;无相似声音匹配  </span> </p> <p>如果查询的CGI参数字符串包含<span class="codeph"> sp_w=exact </span>，则写入浏览器的搜索结果的标签如下（检查的<span class="codeph">字词</span>将插入标签末尾）： </p> <p> <span class="codeph"> &lt;input type="checkbox" name="sp_w" value="exact" checked=""&gt;无相似声音匹配  </span> </p> <p>如果查询的CGI参数字符串不包含<span class="codeph"> sp_w=exact </span>，则写入浏览器的搜索结果的标签如下所示（标记中未列出选中的<span class="codeph">词</span>）： </p> <p> <span class="codeph"> &lt;input type="checkbox" name="sp_w" value="exact"&gt;无相似声音匹配  </span> </p> <p><span class="codeph"> &lt;search-input&gt; </span>标记可用于将复选框和单选按钮放入搜索模板中。 如果您有要添加到搜索模板中的<span class="codeph"> &lt;form&gt; </span>的复选框或单选按钮，请使用<span class="codeph"> &lt;search-input...&gt; </span>代替<span class="codeph"> &lt;input..&gt; </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-select&gt; ...  &lt;/search-select&gt; </span> </p> <p> <span class="codeph"> &lt;search-option&gt; ...  &lt;/search-option&gt; </span> </p> </td> 
   <td colname="col2"> <p><span class="codeph"> &lt;form&gt; </span>标签中的下拉列表框以<span class="codeph"> &lt;select&gt; </span>标签开始，并以<span class="codeph"> &lt;/select&gt; </span>标签结束。 关联的CGI参数的<span class="codeph">名称</span>列在<span class="codeph"> &lt;select&gt; </span>标签中。 在<span class="codeph"> &lt;select&gt; </span>标签后面是<span class="codeph"> &lt;option&gt; </span>标签的列表，这些标签指定要在列表框中显示的值。 </p> <p><span class="codeph"> &lt;search-select&gt; </span>、<span class="codeph"> &lt;/search-select&gt; </span>、<span class="codeph"> &lt;search-option&gt; </span>和<span class="codeph"> &lt;/search-option&gt; </span>标签提供与<span class="codeph"> &lt;search-input&gt; </span>标签类似的功能。 即，如果<span class="codeph"> &lt;search-select&gt; </span>标签中的<span class="codeph">名称</span>被列为CGI参数，且该CGI的<span class="codeph">值</span>为</span>&lt;search-select&gt; ，则在发送到浏览器的<span class="codeph"> &lt;option&gt; </span>标签的末尾自动添加选定的单词<span class="codeph">参数列为特定<span class="codeph"> &lt;search-option&gt; </span>标记中的<span class="codeph">值</span>。 这样，您就可以自动在搜索结果中使默认列表框选项与当前查询相同。 </span></p> <p>例如，典型的列表框如下所示： </p> <p> <code class="syntax html"> &lt;select&nbsp;name="sp_x"&nbsp;size=1&gt; 
      &lt;option&nbsp;value="any"&nbsp;selected&gt;Anywhere&lt;/option&gt; 
      &lt;option&nbsp;value="title"&gt;Title&lt;/option&gt; 
      &lt;option&nbsp;value="desc"&gt;Description&lt;/option&gt; 
      &lt;option&nbsp;value="keys"&gt;Keywords&lt;/option&gt; 
      &lt;option&nbsp;value="body"&gt;Body&lt;/option&gt; 
      &lt;option&nbsp;value="alt"&gt;Alternate&nbsp;text&lt;/option&gt; 
      &lt;option&nbsp;value="url"&gt;URL&lt;/option&gt; 
      &lt;option&nbsp;value="target"&gt;Target&lt;/option&gt; 
      &lt;/select&gt; </code> </p> <p>该列表框的相应模板代码如下： </p> <p> <code class="syntax html"> &lt;search-select&nbsp;name="sp_x"&nbsp;size=1&gt; 
      &lt;search-option&nbsp;value="any"&gt;Anywhere&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="title"&gt;Title&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="desc"&gt;Description&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="keys"&gt;Keywords&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="body"&gt;Body&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="alt"&gt;Alternate&nbsp;text&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="url"&gt;URL&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="target"&gt;Target&lt;/search-option&gt; 
      &lt;/search-select&gt; </code> </p> <p>如果要将列表框添加到搜索模板的<span class="codeph"> &lt;form&gt; </span>中，请使用<span class="codeph"> &lt;search-select...&gt; </span>代替<span class="codeph"> &lt;select...&gt; </span>、<span class="codeph"> &lt;/search-select&gt; </span> <span class="codeph"> &lt;/select&gt;a9/&gt;、<span class="codeph"> &lt;search-option...&gt; </span>代替<span class="codeph"> &lt;option...&gt; </span>,<span class="codeph"> </span>代替<span class="codeph"> &lt;/option&gt; </span>.</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-sort-by-field name="field-name" count="XX"&gt; ...  &lt;/search-sort-by-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>这些高级标签在它们之间的HTML周围创建一个锚点链接。 单击此锚点时，将显示在给定字段中排序的结果页。 可选的<span class="codeph"> count </span>属性指定要在结果页上显示的结果数。 如果省略<span class="codeph">计数</span>，则使用当前页上使用的计数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 日期格式字符串{#section_4BBDBBEF2B96414497617CD4B52D96E4}

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
   <td colname="col2"> <p> 匹配完整工作日名称（例如，“星期一”）的国家代表。 <span class="uicontrol">语言学</span> &gt; <span class="uicontrol">单词和语言</span> &gt; <span class="uicontrol">语言</span>中的设置确定国家代表。 </p> <p>请参阅<a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local">关于单词和语言</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a </p> </td> 
   <td colname="col2"> <p> 匹配缩写工作日名称的国家代表，其中缩写是前三个字符，例如“Mon”。 <span class="uicontrol">语言学</span> &gt; <span class="uicontrol">单词和语言</span> &gt; <span class="uicontrol">语言</span>中的设置确定国家代表。 </p> <p>请参阅<a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local">关于单词和语言</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%B </p> </td> 
   <td colname="col2"> <p> 匹配整月名称的国家代表，例如“June”。 <span class="uicontrol">语言学</span> &gt; <span class="uicontrol">单词和语言</span> &gt; <span class="uicontrol">语言</span>中的设置确定国家代表。 </p> <p>请参阅<a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local">关于单词和语言</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%b </p> </td> 
   <td colname="col2"> <p> 匹配缩写月份名称的国家代表，其中缩写是前三个字符，例如“Jun”。 <span class="uicontrol">语言学</span> &gt; <span class="uicontrol">单词和语言</span> &gt; <span class="uicontrol">语言</span>中的设置确定国家代表。 </p> <p>请参阅<a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local">关于单词和语言</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%D </p> </td> 
   <td colname="col2"> <p>等效于“%m/%d/%y”，例如“07/25/13”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%d </p> </td> 
   <td colname="col2"> <p> 将月中的某天与小数(01-31)匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%e </p> </td> 
   <td colname="col2"> <p> 将月日与小数(1-31)匹配。 空在单位数之前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%H </p> </td> 
   <td colname="col2"> <p> 将24小时时钟与小数(00-23)匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%h </p> </td> 
   <td colname="col2"> <p> 匹配缩写月份名称的国家代表，其中缩写是前三个字符，例如"Jun"（与%b相同）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%I </p> </td> 
   <td colname="col2"> <p> 将12小时时钟与小数(01-12)匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%j </p> </td> 
   <td colname="col2"> <p> 将年中的某天与小数(001-366)匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%k </p> </td> 
   <td colname="col2"> <p> 将(24小时时钟作为小数(0-23)匹配。 空在单位数之前。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%l </p> </td> 
   <td colname="col2"> <p> 将12小时时钟作为小数(1-12)匹配。 空在单位数之前。 </p> </td> 
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
   <td colname="col2"> <p> 根据需要匹配“ante meridiem”或“post meridiem”的国家代表，例如“PM”。 <span class="uicontrol">语言学</span> &gt; <span class="uicontrol">单词和语言</span> &gt; <span class="uicontrol">语言</span>中的设置确定国家代表。 </p> <p>请参阅<a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local">关于单词和语言</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%R </p> </td> 
   <td colname="col2"> <p>等效于“%H:%M”，例如“13:23”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%r </p> </td> 
   <td colname="col2"> <p>等效于“%I:%M:%S %p”，例如“01:23:45 PM”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%S </p> </td> 
   <td colname="col2"> <p> 将第二个数字与十进制数字(00-60)匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%T </p> </td> 
   <td colname="col2"> <p>等效于“%H:%M:%S”，例如“13:26:47”。 </p> </td> 
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
   <td colname="col2"> <p> 将年份与世纪作为十进制数字进行匹配，例如“2013”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%y </p> </td> 
   <td colname="col2"> <p> 将不含世纪的年份与小数(00-99)匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Z </p> </td> 
   <td colname="col2"> <p> 匹配时区名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>% </p> </td> 
   <td colname="col2"> <p> 匹配 "%". </p> </td> 
  </tr> 
 </tbody> 
</table>

## 语言标识符{#section_0490DECC00E34691ADE5A9ED90A6D911}

下表包含每个支持语言的语言标识符。 您可以在以下模板标记中将这些标识符用作可选“语言”属性的值：

* `search-date` 和 `search-display-field`.

   请参阅[结果循环字符串标签](../c-appendices/c-templates.md#section_80D68334E8D04A33937A6E58ABAAA320)。

* `search-field-value-list` 请参 [阅字段值列表标记](../c-appendices/c-templates.md#section_D3298B5F976447DBA0032B883DCC91B1)。

* `search-field-value` 请参 [阅字段值列表循环标签](../c-appendices/c-templates.md#section_0717FA09F0FC449CB916883B0500A60E)。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>语言 </p> </th> 
   <th colname="col2" class="entry"> <p>语言 identifier </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>保加利亚语 </p> </td> 
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
   <td colname="col2"> <p> zh_CA </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>英语（大不列颠） </p> </td> 
   <td colname="col2"> <p> en_GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>英语（美国） </p> </td> 
   <td colname="col2"> <p> zh_CN </p> </td> 
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
   <td colname="col1"> <p>俄语(前苏联合并) </p> </td> 
   <td colname="col2"> <p> ru_SU </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>斯洛伐克语（斯洛伐克） </p> </td> 
   <td colname="col2"> <p> sk_SK </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>斯洛伐克（斯洛文尼亚） </p> </td> 
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

## 指定内容类型HTTP头{#section_AEED823E9938448A9EDB2F286D9CFD90}

可以使用以下标签指定Content-Type HTTP响应头：

`<search-content-type-header [content="MIME-type"] [charset="charset-name"]>`

`content`和`charset`属性是可选的。 此标记应尽早显示在模板中。 还建议在`<search-html-meta-charset>`或`<search-xml-decl>`之前显示，因为它会影响这些标签的行为。

如果未指定`content`属性，则`MIME-type`的值将默认为在&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**&#x200B;中设置的值。 如果指定`content`属性，则它将用作`<search-html-meta-charset>`标签的默认`content`属性。

如果未指定`charset`属性，则不会将`charset`值写入`content-type`标头。

如果指定`charset="1"`，则`charset-name`的实际值是`sp_f` CGI参数的值。 如果搜索中未提交`sp_f` CGI参数，则会从帐户设置中读取`charset-name`的实际值。 您可以视图或更改与您的帐户关联的字符集，该字符集位于&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]** > **[!UICONTROL Character Encoding]**&#x200B;下。

请参阅[配置您的个人用户信息](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6)。

可以通过将特定字符集名称列为`charset`值（如`charset="iso-8859-1"`或`charset="Shift-JIS"`）来选择该名称。

如果指定`charset`属性，则它将用作`<search-html-meta-charset>`和`<search-xml-decl>`标签的默认`charset`属性，并输出到`content-type`标题。

## 在HTML模板{#section_E0D1816ABB5846BEBE9C26D5980CCBE6}中指定字符集

默认的HTML搜索结果模板通过以下标记指定与当前帐户关联的字符集：

`<search-html-meta-charset [content="MIME-type"] [charset="charset-name"]>`

内容和字符集属性是可选的。 此标记必须显示在模板的HTML `<head>`部分中。 此标签在从模板生成的HTML页上生成以下标签：

`<meta http-equiv="content-type" content="MIME-type; charset=charset-name">`

如果未指定content属性，则`MIME-type`的实际值将默认为两个值之一。 如果`<search-content-type-header>`标签指定了`content`属性，则使用该值。 否则，使用的值是&#x200B;**[!UICONTROL Templates]** > **[!UICONTROL Settings]** > **[!UICONTROL Content Type]**&#x200B;选项卡中的值集。

如果未指定`charset`属性，则`charset-name`的实际值默认为两个值之一。 如果`<search-content-type-header>`标签指定了`charset`属性，则使用该值。 否则，将从帐户设置中读取`charset-name`的实际值。 您可以视图或更改与您的帐户关联的字符集，该字符集位于&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]** > **[!UICONTROL Character Encoding]**&#x200B;下。

请参阅[配置您的个人用户信息](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6)。

如果指定`charset="1"`，则`charset-name`的实际值是`sp_f` CGI参数的值。 如果搜索中未提交`sp_f` CGI参数，则`charset-name`的实际值是在`<search-content-type-header>`标签中设置的值（如果已指定），或是在帐户设置中设置的值。

可以指定特定字符集名称，如`charset="charset-name"`中所示。 例如，`charset="iso-8859-1"`或`charset="Shift-JIS"`。

`<search-html-meta-charset>`标记是可选的。 如果删除它，浏览器将采用`content-type`的默认值，如下所示：`content="text/html; charset=ISO-8859-1"`。 您还可以选择将`<search-html-meta-charset>`标签替换为您自己的`http-equiv`标签。

## 在XML模板{#section_17DC31CDCC104F5F8081466B41A96E9D}中指定字符集

默认的XML搜索结果模板通过以下标记指定与当前帐户关联的字符集：

`<search-xml-decl [charset="charset-name"]>`

`charset`属性是可选的。 此标记必须显示在模板顶部，但位于任何`<search-content-type-header>`标记之后。 此标签在从模板生成的XML文档上生成以下标签：

`<?xml version="1.0" encoding="charset-name" standalone="yes" ?>`

如果未指定`charset`，则`charset-name`的实际值默认为两个值之一。 如果`<search-content-type-header>`指定了`charset`属性，则使用该值。 否则，将从帐户设置中读取`charset-name`的实际值。 您可以视图或更改与您的帐户关联的字符集，该字符集位于&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]** > **[!UICONTROL Character Encoding]**&#x200B;下。

请参阅[配置您的个人用户信息](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6)。

如果指定`charset="1"`，则`charset-name`的实际值是`sp_f` CGI参数的值。 如果搜索中未提交`sp_f` CGI参数，则`charset-name`的实际值是在`<search-content-type-header>`标签中设置的值（如果已指定）或在帐户设置中设置的值。

如果需要，可以指定特定字符集名称，如`charset="charset-name"`中所示。 例如，`charset="iso-8859-1" or charset="Shift-JIS"`。

您可以选择将`<search-xml-decl>`标签替换为您自己的`?xml`标签。

## 在另一个{#section_7D1FCD3D9E2340C291E354C9720E8BC0}中包括搜索模板

要将一个搜索模板包含在另一个中，请使用`<search-include>`标记，将file属性设置为要包含的模板文件的名称，如下例所示：

`<search-include file="seo/seo_search_title.tpl" />`

SEO搜索模板段位于`seo/`子文件夹中，普通搜索模板位于`templates/`子文件夹中。 只有.tpl文件有意要包含在此上下文中。

## 管理网站{#reference_12AAB3B9F4C74C11956F1DBA95714C2F}的多个传输模板

您可以通过为每个区域使用不同的搜索传输模板来控制网站中搜索结果的外观。

<!-- 

r_managing_multiple_templates.xml

 -->

要实现这种搜索功能，您可以在网站搜索/促销中管理传输模板。 或者，您也可以在“发布”中管理传输模板。 与网站搜索/促销一样，“发布”允许您编辑、预览和发布多个搜索传输模板。

要设置搜索表单以使用特定传输模板（默认模板除外），请使用`sp_t`查询参数。 例如，假设您有一个名为“clearance”的搜索模板，用于您网站的已标记销售区域。 您可将标准HTML搜索表单与以下附加表单代码一起使用：

`<input type=hidden name="sp_t" value="clearance">`

当客户单击包含此行代码的标准表单时，将显示“清除”搜索传输模板及其搜索结果。

请参阅[在搜索表单中使用集合](../c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3)。

请参阅[使用具有表单的帧](../c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5)。

请参阅[高级搜索表单示例](../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A)。
