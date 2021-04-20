---
description: 了解如何以任何基于文本的格式（包括XML或JSON）自定义输出。
solution: Target
title: 导向搜索输出
topic: Appendices,Site search and merchandising
uuid: 234fd563-f249-42b0-88ca-c89b44f8df77
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '6289'
ht-degree: 2%

---


# 导向搜索输出{#guided-search-output}

您可以以任何基于文本的格式自定义输出，包括XML或JSON。

## 使用导向搜索输出{#concept_2A1BA3AD413848A1AC2A3ABC4FFE481F}

输出格式可自定义，以支持在设计过程中做出的分面、排序和其他特定于实施的决策。 如有必要，您可以调整格式本身以简化客户前端的开发。

整个输出包含在`<result>`标记中，而大多数动态数据都包含在`<![CDATA[ ]]>`标记中。 这种组织允许结果包含HTML和其他非XML实体。

如果提供了指向其他页面的链接，则这些链接将以相对URL的形式显示。 此结果还包括传递的查询字符串参数，以生成所需结果。

## 了解向导式搜索实现{#section_95483980930C4325BAB50A40BD47245A}

当您开始“引导式搜索”实施时，请记住[!DNL Adobe Search&Promote]负责业务层。 即，围绕在任何给定时间向客户展示哪些结果和方面的逻辑。

当您实现分析结果并将结果显示为HTML的Web 应用程序前端时，将功能限制为仅显示。 换句话说，您用于创建表示层的任何服务器端逻辑不会决定向客户展示什么，除非有必要。 如果前端脚本正在更改搜索结果，则业务规则将无法按预期工作。

[!DNL Adobe Search&Promote] 通过URL参数保持所选搜索优化选项的用户状态。所有`<link>`节点都包含客户选择的相关参数。 这些参数可以包括痕迹导航、分页、排序和彩块化选择。 如果适用，将返回`<undolink>`节点以允许客户“退出”选择。 彩块化和痕迹导航可优惠这些类型的链接。

## 使用搜索服务器{#section_8DBEACDECD714E59BDED6315E6041B8D}

使用类似REST的API，您可以与它交互以执行搜索和接收结果。 最常用的结果格式是XML或JSON。

基本URI与特定帐户和暂存或实时环境关联。 您可以从帐户管理器请求基本URI的多个别名。 例如，名为Megacorp的虚构公司具有以下两个基本URL与其帐户关联：

* `https://search.megacorp.com `
* `https://stage.megacorp.com`

前一个URI针对其活动索引执行搜索，后一个URI针对其分阶段索引执行搜索。

搜索请求由基本URI和一组CGI参数或键值对组成，这些参数或键值对指示对与基本URI关联的帐户进行所需搜索。

支持三种格式的CGI参数。 默认情况下，您的帐户配置为使用分号(`;`)分隔CGI参数，如下例所示：

* `https://search.megacorp.com?q=shoes ;page=2`

如果您愿意，您可以让您的客户经理将您的帐户配置为使用&amp;号(`&`)来分隔CGI参数，如下例所示：

* `https://search.megacorp.com?q=shoes &page=2`

还支持第三种格式，称为SEO格式，其中使用正斜杠(`/`)代替分隔符并使用等号生成“clean”链接，如下例所示：

* `https://search.megacorp.com/q/shoes/page/2`

每当使用SEO格式发送请求时，所有输出链接都以相同的格式返回。

## 搜索查询参数{#section_7ADA5E130E3040C9BE85D0D68EDD3223}

下表描述了您可以使用的标准“现成”搜索查询参数。 可以基于用户定义的查询参数构建处理规则和业务规则，以实施与您的公司相关的自定义业务逻辑。 您可以与咨询团队合作，获取有关这些参数的文档。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>搜索查询参数 </p> </th> 
   <th colname="col2" class="entry"> <p>示例 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> q </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> q=字符串  </span> </p> </td> 
   <td colname="col3"> <p> 指定搜索的查询字符串。 此参数映射到<span class="codeph"> sp_q </span>后端搜索参数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> q# </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> q#=字符串  </span> </p> </td> 
   <td colname="col3"> <p>编号<span class="codeph"> q </span>和<span class="codeph"> x </span>的参数可完成分页或在给定字段内搜索。 </p> <p><span class="codeph"> q </span>参数将您在facet中搜索的词定义为相应的编号<span class="codeph"> x </span>参数。 例如，如果您有两个彩块化，它们分别命名为大小和颜色，则您可能会有以下内容： </p> <p> <span class="codeph"> q1=small;x1=size;q2=red;x2=color  </span> </p> <p>此参数映射到<span class="codeph"> sp_q_exact_# </span>后端搜索参数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> x# </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> x#=字符串  </span> </p> </td> 
   <td colname="col3"> <p> 编号<span class="codeph"> q </span>和<span class="codeph"> x </span>的参数可完成分页或在给定字段内搜索。 </p> <p><span class="codeph"> q </span>参数将您在facet中搜索的词定义为相应的编号<span class="codeph"> x </span>参数。 例如，如果您有两个彩块化，它们分别命名为大小和颜色，则您可能会有以下内容： </p> <p> <span class="codeph"> q1=small;x1=size;q2=red;x2=color  </span> </p> <p>此参数映射到<span class="codeph"> sp_x_# </span>后端搜索参数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> collection（集合） </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> collection=字符串  </span> </p> </td> 
   <td colname="col3"> <p> 指定要用于搜索的集合。 此参数映射到<span class="codeph"> sp_k </span>后端搜索参数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> count（计数） </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> 计数=数字  </span> </p> </td> 
   <td colname="col3"> <p> 指定所显示结果的总计数。 默认值在<span class="uicontrol">设置</span> &gt; <span class="uicontrol">搜索</span> &gt; <span class="uicontrol">搜索</span>中定义。 此参数映射到<span class="codeph"> sp_c </span>后端搜索参数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> page </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> page= number  </span> </p> </td> 
   <td colname="col3"> <p> 指定返回的结果页。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> 排名  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> 排名  </span> </p> </td> 
   <td colname="col3"> <p> 指定用于静态排名的排名字段。 该字段必须是关联度大于0的“排名”类型字段。 此参数映射到<span class="codeph"> sp_sr </span>后端参数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> gs_store  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> gs_store=字符串  </span> </p> </td> 
   <td colname="col3"> <p> 指定要搜索的存储。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> 排序  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> 排序=数字  </span> </p> </td> 
   <td colname="col3"> <p> 指定排序顺序。 “0”是默认值，按相关性得分排序；“1”按日排序；“–1”不排序。 </p> <p>用户可以为<span class="codeph"> sp_s </span>参数的值指定字段名。 例如，<span class="codeph"> sp_s=title </span>会根据标题字段中包含的值对结果进行排序。 当使用字段名称作为<span class="codeph"> sp_s </span>参数的值时，结果将按该字段排序，然后按相关性进行子排序。 </p> <p>要启用此功能，请执行以下操作： </p> 
    <ol id="ol_3894F81EA7BF4827A84DE8662111ABEF"> 
     <li id="li_C040C0B88F174A4885E1A8E721FD032A">在产品菜单上，单击<span class="uicontrol">设置</span> &gt; <span class="uicontrol">元数据</span> &gt; <span class="uicontrol">定义</span>。 </li> 
     <li id="li_2E83C3A46D1B4BF991EABAD9D3E52B7D">在“<span class="wintitle">分阶段定义</span>”页中，执行下列操作之一： 
      <ul id="ul_8018FEE10E0A4C96A74F84A897080580"> 
       <li id="li_E9A7CE43E2734F4D9522A1283CA111FB">单击<span class="uicontrol">添加新字段</span>。 </li> 
       <li id="li_9D2434A321924FBD874569CA9AD2EEF7">单击<span class="uicontrol">编辑</span>以查找特定字段名称。 </li> 
      </ul> </li> 
     <li id="li_90D5E3F4AC0A4A6189934A5589F69903">在<span class="wintitle">排序</span>下拉列表中，单击升序</span>或<span class="uicontrol">降序</span>。<span class="uicontrol"> </span><p>此参数映射到<span class="codeph"> sp_s </span>后端搜索参数。 </p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

## 与系统{#section_91261B19A44A4E579B3FC9FAB9AD3665}集成

以下是与系统集成的建议。

* 与搜索服务器通信。

   您可以使用httpGET请求与[!DNL Adobe Search&Promote] Web服务器通信。 您的服务器生成这些请求或在客户端执行Ajax请求。
* 保存搜索历史记录。

[!DNL Adobe Search&Promote] 在http请求中传递整个状态时为无状态。
* 分析返回的结果。

   建议使用基于SAX的XML分析器分析XML响应。 如果您正在生成Ajax请求，请配置[!DNL Adobe Search&Promote]以返回这些请求的JSON响应，以便更轻松地分析响应。

## 向导式搜索JSON输出{#reference_EB8182A564DE4374BB84158F2AABEF74}

描述标准JSON响应输出的表。

另请参阅[引导搜索JSON输出](../c-appendices/c-guidedsearchoutput.md#reference_EB8182A564DE4374BB84158F2AABEF74)。

您可以查看以下JSON响应：

* [横幅广告](../c-appendices/c-guidedsearchoutput.md#section_88519CAAD25F4BD49D5E517077745B0E)
* [痕迹导航](../c-appendices/c-guidedsearchoutput.md#section_A7DB0F1DA9ED4CBCAE18395122F3E01E)
* [彩块化](../c-appendices/c-guidedsearchoutput.md#section_65932C95931743A1BFAF1DF16D7E6D92)
* [标题和查询](../c-appendices/c-guidedsearchoutput.md#section_1D57062259CA46E0B4F598FA4EB37065)
* [分页](../c-appendices/c-guidedsearchoutput.md#section_504E7AB570BD49AF9839530DC438EE96)
* [最近搜索](../c-appendices/c-guidedsearchoutput.md#section_525816A0355C48F8970D89B8FC3F1FFF)
* [结果](../c-appendices/c-guidedsearchoutput.md#section_41AC56BB0A084BF59379B06C8BEF2157)
* [搜索表单](../c-appendices/c-guidedsearchoutput.md#section_434DA13EA295474C99FFE9F14801CD0E)
* [排序](../c-appendices/c-guidedsearchoutput.md#section_558853CD376F4D71BACF211D53085D55)
* [建议](../c-appendices/c-guidedsearchoutput.md#section_6EC104E1DDD94AC799B65E6E61A2FB3C)
* [Zones](../c-appendices/c-guidedsearchoutput.md#section_AE53A498B440465EAF2286F2AE87D548)

## 横幅广告 {#section_88519CAAD25F4BD49D5E517077745B0E}

示例：

```xml
<banners> 
 <banner> 
  <area><![CDATA[top-left]]></area> 
  <content><![CDATA[<img src="https://www.megacorp.com/discount.gif"/>]]></content> 
 </banner> 
</banners>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>横幅中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;banner&gt; </span> </p> </td> 
   <td colname="col2"> <p> 单个横幅节点。 您可以有多个横幅节点。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;area&gt; </span> </p> </td> 
   <td colname="col2"> <p> 网页上显示横幅的区域。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;content（内容）&gt; </span> </p> </td> 
   <td colname="col2"> <p> 横幅区域的HTML内容。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 痕迹导航{#section_A7DB0F1DA9ED4CBCAE18395122F3E01E}

在以下示例中，每次客户通过facet进一步缩小范围时，所做的选择都会添加到痕迹导航中。 每个项目都表示为`<breadcrumb-item>`。

示例：

```xml
 <breadcrumb> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year]]></link> 
   <value><![CDATA[new year]]></value> 
  </breadcrumb-item> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year;q1=Articles;x1=content-type]]></link> 
   <value><![CDATA[Articles]]></value> 
  </breadcrumb-item> 
 </breadcrumb> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>痕迹导航中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> 显示所需视图的搜索结果的相对链接。 单击痕迹导航链接可将客户带到视图，随后所有的细化都将被删除。 还提供其他选项。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> 痕迹导航项的面向客户的文本。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 彩块化{#section_65932C95931743A1BFAF1DF16D7E6D92}

彩块化是细化选项，让客户能够对结果进行筛选。 彩块化通常用于分类、价格范围、颜色选择和其他属性细化。 索引中的元数据是驱动器彩块化的原因。

客户在分类中向下移动时，通常会隐藏或显示分类彩块化。 最高级别的分类(类别)称为第1层。 当客户单击第1层选项时，将显示第2层（子类别）优化选项，而第1层选项将消失。 当客户单击第2层选项时，将显示第3层（子子类别）优化选项，而第2层选项将消失。 如上所述，这些选项是隐藏的并且显示的 — 您的Web应用程序不受这些选项的影响。

每个facet都包含在`<facet-item>`标记中。 在以下示例中，它显示了一个允许客户按“假日”优化搜索结果的方面。

示例：

```xml
 <facets> 
  <facet-item> 
   <facet-title><![CDATA[Holidays]]></facet-title> 
   <facet-value> 
    <label><![CDATA[New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[11]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Christmas]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Christmas;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Chinese New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Chinese+New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Thanksgiving]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Thanksgiving;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[4th of July]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=4th+of+July;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Father&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Father's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Hanukkah]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Hanukkah;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Mother&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Mother's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Valentine&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Valentine's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
  </facet-item> 
  <facet-item> 
   <facet-title><![CDATA[Seasons]]></facet-title> 
   <facet-value> 
    <label><![CDATA[Winter]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Winter;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[20]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Summer]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Summer;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Autumn]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Autumn;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[4]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Spring]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Spring;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
  </facet-item> 
 </facets> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>彩块化中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> facet的面向客户的标题。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> facet选项的面向客户的标签。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> 相对链接，可使选项缩小。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;count（计数）&gt; </span> </p> </td> 
   <td colname="col2"> <p> 该精化结果集中的结果数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;undolink&gt; </span> </p> </td> 
   <td colname="col2"> <p> 选择facet值后，节点将返回一个“撤消链接”，允许客户退出结果。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 标头和查询{#section_1D57062259CA46E0B4F598FA4EB37065}

示例：

```xml
<result> 
 <query> 
  <user-query><![CDATA[new year]]></user-query> 
  <lower-results><![CDATA[1]]></lower-results> 
  <upper-results><![CDATA[16]]></upper-results> 
  <total-results><![CDATA[621]]></total-results> 
 </query> 
```

这些标签一起使用时会显示如下消息：“‘新年’的621项中，显示结果1-16项。”

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>标题和查询中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;user-query&gt; </span> </p> </td> 
   <td colname="col2"> <p> 随请求一起提交的关键字查询。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;lower-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> 此页上第一个结果的项目编号。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;upper-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> 此页上最后一个结果的项目编号。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> 匹配用户查询的结果总数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;custom-field&gt; </span> </p> </td> 
   <td colname="col2"> <p> 全局应用于搜索结果的可选字段。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 分页{#section_504E7AB570BD49AF9839530DC438EE96}

示例：

```xml
<pagination> 
 <total-pages><39></total-pages> 
 <pages> 
   <page position="first"></page> 
   <page position="last">?i=1;page=39;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="previous"></page> 
   <page position="next">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="1" selected="true">?i=1;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="2">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="3">?i=1;page=3;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="4">?i=1;page=4;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="5">?i=1;page=5;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="6">?i=1;page=6;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="7">?i=1;page=7;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="8">?i=1;page=8;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="9">?i=1;page=9;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="10">?i=1;page=10;q=new+year;q1=Articles;x1=content-type]]></page> 
 </pages> 
</pagination> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>分页中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-pages&gt; </span> </p> </td> 
   <td colname="col2"> <p> 结果页总数，基于结果数除以每页结果数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="first"&gt; </span> </p> </td> 
   <td colname="col2"> <p> 包含指向结果集中第一页的相对链接，除非客户已查看第1页。 在这种情况下，它是空的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="last"&gt; </span> </p> </td> 
   <td colname="col2"> <p> 包含指向结果集中最后一页的相对链接，除非客户正在查看最后一页。 在这种情况下，它是空的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="previous"&gt; </span> </p> </td> 
   <td colname="col2"> <p> 包含指向结果集中上一页的相对链接，除非客户正在查看第1页；在这种情况下，它是空的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="next"&gt; </span> </p> </td> 
   <td colname="col2"> <p> 包含指向结果集中最后一页的相对链接，除非客户正在查看最后一页。 在这种情况下，它是空的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="x"&gt;</span> </p> </td> 
   <td colname="col2"> <p> 包含指向特定页码的相对链接。 显示十个连续的页码。 在第1页，是第1-10页。 在结果集（本例中为39页）末尾，将是第30-39页。 例如，在结果集的中心（第15页），它应该是第11-20页。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> selected="true"&gt;  </span> </p> </td> 
   <td colname="col2"> <p> 应用为当前选定页面的属性。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最近搜索{#section_525816A0355C48F8970D89B8FC3F1FFF}

“最近搜索”是基于Cookie的功能，仅在您将Cookie信息中继到服务器时才有效。

示例：

```xml
<recent-searches> 
 <recent-search> 
  <search-term><![CDATA[shoes]]></search-term> 
  <link><![CDATA[?q=shoes]]></link> 
 </recent-search> 
</recent-searches> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>最近搜索中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;recent-search&gt; </span> </p> </td> 
   <td colname="col2"> <p> 单个最近搜索节点。 您可以有多个最近搜索节点。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-term&gt; </span> </p> </td> 
   <td colname="col2"> <p> 客户之前搜索的词。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> 指向上一搜索的链接。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 结果 {#section_41AC56BB0A084BF59379B06C8BEF2157}

结果集是JSON响应的可自定义区域。 每个索引在元数据的字段命名机制中都是唯一的。 每个结果都返回了常用字段，如标题、说明和URL。 但是，为索引中的页面定义的任何元数据都可以在每个结果节点中使用。 分类、价格、颜色和缩略图只是一些选项，您可以将它们应用于结果，从而生成更引人注目的搜索结果。

根据特定于您的实施的元数据自定义结果格式。 此处包含结果中显示的所有结果数据，包括缩略图图像URL。

此外，还可以在页面中配置多个结果区域，如“特色结果”，或单独的“产品”和“内容”结果部分。 在这些情况下，HTML中会提供多个结果区域，但facet仅与主结果集关联。

示例：

```xml
 <results> 
  <result> 
    <index><![CDATA[1]]></index> 
    <result-title><![CDATA[New Year's Eve Slumber Party]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/new-years-eve-slumber-party-705199/]]></url> 
    <meta-description><![CDATA[Fun New Year's celebration ideas for your kids]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/new-years-eve-

slumber-party-parties-photo-80-FF1200SLEEPA18.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/new-years-eve- 
slumber-party-parties-photo-160-FF1200SLEEPA18.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Nancy Mades]]></byline> 
    <blurb><![CDATA[Fun New Year's celebration ideas for your kids]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[2]]></index> 
    <result-title><![CDATA[10 Holiday Traditions to Start This Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/10-holiday-traditions-to-start-this-year-704781/]]></url> 
    <meta-description><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/10-holiday- 
traditions-to-start-this-year-parties-photo-80-FF1107HOLIA01.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/10-holiday- 
traditions-to-start-this-year-parties-photo-160-FF1107HOLIA01.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Julie Taylor]]></byline> 
    <blurb><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[3]]></index> 
    <result-title><![CDATA[A Perfect New Year's Eve]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/a-perfect-new-years-eve-705258/]]></url> 
    <meta-description><![CDATA[You can turn New Year's into a celebration for the whole family.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Teri Keough]]></byline> 
    <blurb><![CDATA[You can turn New Year's into a celebration for the whole family.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[4]]></index> 
    <result-title><![CDATA[New Year's Fun and Games]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/new-years-fun-and-games-705220/]]></url> 
    <meta-description><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Charlotte Meryman]]></byline> 
    <blurb><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[5]]></index> 
    <result-title><![CDATA[11 Great Ways to Start the New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/11-great-ways-to-start-the-new-year-705552/]]></url> 
    <meta-description><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Emily Block]]></byline> 
    <blurb><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[6]]></index> 
    <result-title><![CDATA[Celebrating Chinese New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/celebrating-chinese-new-year-705260/]]></url> 
    <meta-description><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[7]]></index> 
    <result-title><![CDATA[New Year's Eve, Family Style]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/new-years-eve-family-style-701283/]]></url> 
    <meta-description><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[8]]></index> 
    <result-title><![CDATA[Chinese New Year Activities]]></result-title> 
    <url><![CDATA[https://mysite.com/crafts/chinese-new-year-activities-710345/]]></url> 
    <meta-description><![CDATA[Activities for celebrating Chinese New Year.]]></meta-description> 
    <category><![CDATA[crafts]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Activities for celebrating Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[9]]></index> 
    <result-title><![CDATA[More Organized in the New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/more-organized-in-the-new-year-701284/]]></url> 
    <meta-description><![CDATA[Tips for getting your household more organized--and getting the kids to help.]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Tips for getting your household more organized--and getting your kids to help out.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[10]]></index> 
    <result-title><![CDATA[Checklists: Year-End Safety Checklist]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/checklists-year-end-safety-checklist-701352/]]></url> 
    <meta-description><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></blurb> 
  </result>   
 </results> 
</customer-result> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>结果中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;index&gt; </span> </p> </td> 
   <td colname="col2"> <p> 此结果集中结果的序列号。 在此示例中，每页显示十个结果，在结果的第2页上，第一个项的索引为11。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> 此页面的面向客户的标题。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;url&gt; </span> </p> </td> 
   <td colname="col2"> <p> 此页面的URL。 它用于创建允许客户点击结果的超链接。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 搜索表单{#section_434DA13EA295474C99FFE9F14801CD0E}

示例：

```xml
<search-form> 
 <include-tnt-mbox>1 </included-tnt-mbox> 
 <autocomplete> 
  <css><![CDATA[<!--link rel="stylesheet" type="te 
        xt/css"href="//content.atomz.com/sp000000a8/publish/autoc 
        omplete_styles.css?sp_css_cache_ver=2" /-->]]> 
  </css> 
  <form-content><![CDATA[<div id="autocomplete"></div>]]> 
  </form-content> 
  <js><![CDATA[<script type="text/javascript" 
   src="//content.atomz.com/sp100491de/publish/autoc 
   omplete_data.js?sp_js_cache_ver=3"></script>]]> 
  </js> 
 </autcomplete> 
 <hidden-parameters> 
  <parameter> 
   <name><![CDATA[store]]></name> 
   <value><![CDATA[mens]]></value> 
  </parameter> 
 </hidden-parameters> 
</search-form>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>搜索表单中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;include-tnt-mbox&gt; </span> </p> </td> 
   <td colname="col2"> <p> 可选. 如果JSON中存在值1，则它表示您的帐户已链接到<span class="keyword"> Test&amp;目标 </span>，并且至少有一个业务规则位于A:B测试中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;autocomplete&gt; </span> </p> </td> 
   <td colname="col2"> <p> 可选. 使用自动完成时，此节点会显示在页面上，指示CSS和JavaScript以及表单中的内容存在。 除非某人更改了自动完成设置，否则这些字段通常不会更改。 在这种情况下，xxx_cache_ver字段会递增，以强制客户浏览器上缓存的内容失效。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;css&gt; </span> </p> </td> 
   <td colname="col2"> <p> 与自动完成关联的CSS。 建议您将此标记放在页面的高处以改进页面渲染。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;form-content&gt; </span> </p> </td> 
   <td colname="col2"> <p> 搜索自中所需的内容，以自动完成实用程序与正确的控件关联。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;js&gt; </span> </p> </td> 
   <td colname="col2"> <p> 自动完成所需的自定义JavaScript。 建议您将此标记放在页面中低位以改进页面渲染。 自动完成也需要YUI JavaScript。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;hidden-parameters&gt; </span> </p> </td> 
   <td colname="col2"> <p> 包含要包含在搜索表单中的所有隐藏参数（名称和值）。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 排序 {#section_558853CD376F4D71BACF211D53085D55}

以下示例显示了三选项排序菜单的数据。 该菜单允许客户按相关性、标题或评级进行排序。 当前选定的项目包含属性“selected=true”。 &quot; 始终优惠相关选项，以允许客户返回到最初显示的默认搜索结果。

示例：

```xml
 <sort> 
  <sort-item selected="true"> 
   <label><![CDATA[Relevance]]></label> 
   <value><![CDATA[relevance]]></value> 
   <link><![CDATA[]]></link> 
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Title]]></label> 
   <value><![CDATA[title]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=title;x1=content-type]]></link>     
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Rating]]></label> 
   <value><![CDATA[user-rating]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=user-rating;x1=content-type]]></link>     
  </sort-item> 
 </sort>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>“排序”菜单中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> 选项的面向客户的文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> 表示此选项的"sort"查询字符串参数的值。 如果使用<span class="codeph"> &lt;link&gt; </span>值，则不需要此标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> 对于未选择的选项，<span class="codeph"> &lt;link&gt; </span>参数包含返回相同结果集的相对链接，该链接按新排序参数排序。 此字段对于当前选定的排序选项为空。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 建议{#section_6EC104E1DDD94AC799B65E6E61A2FB3C}

当结果很少或没有结果时，将返回建议。 此节点包含的术语会生成成功的查询，并可在“无结果”页面上显示。 此时还会返回链接，以便客户可以跳转到新查询。

示例：

```xml
 <suggestions> 
  <suggestion-item> 
   <link><![CDATA[?q=video]]></link> 
   <word><![CDATA[video]]> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>建议中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p>用于创建用于搜索建议词结果的超链接的相对链接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;word&gt; </span> </p> </td> 
   <td colname="col2"> <p>建议的术语。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 区域{#section_AE53A498B440465EAF2286F2AE87D548}

示例：

```xml
<zones> 
 <zone> 
  <name><![CDATA[best-sellers]]></name> 
  <display><![CDATA[1]]></display> 
 </zone> 
</zones> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>区域中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;zone&gt; </span> </p> </td> 
   <td colname="col2"> <p> 单个区域节点。 您可以有多个区域节点。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;name&gt; </span> </p> </td> 
   <td colname="col2"> <p> 区域的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;display&gt; </span> </p> </td> 
   <td colname="col2"> <p> 1或0表示区域是否显示。 实际区域内容可以是网页或搜索结果中的静态区域，如最畅销商品或相关产品。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 向导式搜索XML输出{#reference_D93E859A277643068B10AE7A61C973EA}

描述标准XML响应输出的表。

您可以查看以下XML响应：

* [横幅广告](../c-appendices/c-guidedsearchoutput.md#section_6A19EC26DD3B494194AAA788151B78B5)
* [痕迹导航](../c-appendices/c-guidedsearchoutput.md#section_E48A71B0EBDB4EDDA7587009AD865488)
* [彩块化](../c-appendices/c-guidedsearchoutput.md#section_5CEB1F966C004FFEA3CF675638966E25)
* [标题和查询](../c-appendices/c-guidedsearchoutput.md#section_802835E19BCB48239C6770A1B72DFFF8)
* [分页](../c-appendices/c-guidedsearchoutput.md#section_72DB86DDE1284B1EA295CFFBC16A3150)
* [最近搜索](../c-appendices/c-guidedsearchoutput.md#section_BCA2DDD17F264CF6BA11634E1A514E28)
* [结果](../c-appendices/c-guidedsearchoutput.md#section_EC496F5CA2634158891455E2F6DF6833)
* [搜索表单](../c-appendices/c-guidedsearchoutput.md#section_F92D8C3D37174A10A4E26CAFF3F3DF89)
* [排序](../c-appendices/c-guidedsearchoutput.md#section_32DC50A103BF491BA3665A5CADCCAADE)
* [建议](../c-appendices/c-guidedsearchoutput.md#section_D81BCE46F0AF443695DF9C4BA084B716)
* [Zones](../c-appendices/c-guidedsearchoutput.md#section_15D8AA585F3246799968BA88EE2C9FC2)

## 横幅广告 {#section_6A19EC26DD3B494194AAA788151B78B5}

示例：

```xml
<banners> 
 <banner> 
  <area><![CDATA[top-left]]></area> 
  <content><![CDATA[<img src="https://www.megacorp.com/discount.gif"/>]]></content> 
 </banner> 
</banners>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>横幅中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;banner&gt; </span> </p> </td> 
   <td colname="col2"> <p> 单个横幅节点。 您可以有多个横幅节点。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;area&gt; </span> </p> </td> 
   <td colname="col2"> <p> 网页上显示横幅的区域。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;content（内容）&gt; </span> </p> </td> 
   <td colname="col2"> <p> 横幅区域的HTML内容。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 痕迹导航{#section_E48A71B0EBDB4EDDA7587009AD865488}

在以下示例中，每次客户通过facet进一步缩小范围时，所做的选择都会添加到痕迹导航中。 每个项目都表示为`<breadcrumb-item>`。

示例：

```xml
 <breadcrumb> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year]]></link> 
   <value><![CDATA[new year]]></value> 
  </breadcrumb-item> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year;q1=Articles;x1=content-type]]></link> 
   <value><![CDATA[Articles]]></value> 
  </breadcrumb-item> 
 </breadcrumb> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>痕迹导航中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> 显示所需视图的搜索结果的相对链接。 单击痕迹导航链接可将客户带到视图，随后所有的细化都将被删除。 还提供其他选项。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> 痕迹导航项的面向客户的文本。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 彩块化{#section_5CEB1F966C004FFEA3CF675638966E25}

彩块化是细化选项，让客户能够对结果进行筛选。 彩块化通常用于分类、价格范围、颜色选择和其他属性细化。 索引中的元数据是驱动器彩块化的原因。

客户在分类中向下移动时，通常会隐藏或显示分类彩块化。 最高级别的分类(类别)称为第1层。 当客户单击第1层选项时，将显示第2层（子类别）优化选项，而第1层选项将消失。 当客户单击第2层选项时，将显示第3层（子子类别）优化选项，而第2层选项将消失。 如上所述，这些选项是隐藏的并且显示的 — 您的Web应用程序不受这些选项的影响。

每个facet都包含在`<facet-item>`标记中。 在以下示例中，它显示了一个允许客户按“假日”优化搜索结果的方面。

示例：

```xml
 <facets> 
  <facet-item> 
   <facet-title><![CDATA[Holidays]]></facet-title> 
   <facet-value> 
    <label><![CDATA[New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[11]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Christmas]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Christmas;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Chinese New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Chinese+New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Thanksgiving]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Thanksgiving;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[4th of July]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=4th+of+July;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Father&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Father's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Hanukkah]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Hanukkah;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Mother&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Mother's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Valentine&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Valentine's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
  </facet-item> 
  <facet-item> 
   <facet-title><![CDATA[Seasons]]></facet-title> 
   <facet-value> 
    <label><![CDATA[Winter]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Winter;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[20]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Summer]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Summer;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Autumn]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Autumn;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[4]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Spring]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Spring;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
  </facet-item>  
 </facets> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>彩块化中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> facet的面向客户的标题。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> facet选项的面向客户的标签。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> 相对链接，可使选项缩小。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;count（计数）&gt; </span> </p> </td> 
   <td colname="col2"> <p> 该精化结果集中的结果数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;undolink&gt; </span> </p> </td> 
   <td colname="col2"> <p> 选择facet值后，节点将返回一个“撤消链接”，允许客户退出结果。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 标头和查询{#section_802835E19BCB48239C6770A1B72DFFF8}

示例：

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes" ?> 
<result> 
 <query> 
  <user-query><![CDATA[new year]]></user-query> 
  <lower-results><![CDATA[1]]></lower-results> 
  <upper-results><![CDATA[16]]></upper-results> 
  <total-results><![CDATA[621]]></total-results> 
 </query> 
```

这些标签一起使用时会显示如下消息：“‘新年’的621项中，显示结果1-16项。”

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>标题和查询中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;user-query&gt; </span> </p> </td> 
   <td colname="col2"> <p> 随请求一起提交的关键字查询。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;lower-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> 此页上第一个结果的项目编号。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;upper-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> 此页上最后一个结果的项目编号。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> 匹配用户查询的结果总数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;custom-field&gt; </span> </p> </td> 
   <td colname="col2"> <p> 全局应用于搜索结果的可选字段。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 分页{#section_72DB86DDE1284B1EA295CFFBC16A3150}

示例：

```xml
<pagination> 
 <total-pages><39></total-pages> 
 <pages> 
   <page position="first"></page> 
   <page position="last">?i=1;page=39;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="previous"></page> 
   <page position="next">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="1" selected="true">?i=1;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="2">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="3">?i=1;page=3;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="4">?i=1;page=4;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="5">?i=1;page=5;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="6">?i=1;page=6;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="7">?i=1;page=7;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="8">?i=1;page=8;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="9">?i=1;page=9;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="10">?i=1;page=10;q=new+year;q1=Articles;x1=content-type]]></page> 
 </pages> 
</pagination> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>分页中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-pages&gt; </span> </p> </td> 
   <td colname="col2"> <p> 结果页总数，基于结果数除以每页结果数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="first"&gt; </span> </p> </td> 
   <td colname="col2"> <p> 包含指向结果集中第一页的相对链接，除非客户已查看第1页。 在这种情况下，它是空的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="last"&gt; </span> </p> </td> 
   <td colname="col2"> <p> 包含指向结果集中最后一页的相对链接，除非客户正在查看最后一页。 在这种情况下，它是空的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="previous"&gt; </span> </p> </td> 
   <td colname="col2"> <p> 包含指向结果集中上一页的相对链接，除非客户正在查看第1页；在这种情况下，它是空的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="next"&gt; </span> </p> </td> 
   <td colname="col2"> <p> 包含指向结果集中最后一页的相对链接，除非客户正在查看最后一页。 在这种情况下，它是空的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="x"&gt;</span> </p> </td> 
   <td colname="col2"> <p> 包含指向特定页码的相对链接。 显示十个连续的页码。 在第1页，是第1-10页。 在结果集（本例中为39页）末尾，将是第30-39页。 例如，在结果集的中心（第15页），它应该是第11-20页。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> selected="true"&gt;  </span> </p> </td> 
   <td colname="col2"> <p> 应用为当前选定页面的属性。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最近搜索{#section_BCA2DDD17F264CF6BA11634E1A514E28}

“最近搜索”是基于Cookie的功能，仅在您将Cookie信息中继到服务器时才有效。

示例：

```xml
<recent-searches> 
 <recent-search> 
  <search-term><![CDATA[shoes]]></search-term> 
  <link><![CDATA[?q=shoes]]></link> 
 </recent-search> 
</recent-searches> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>最近搜索中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;recent-search&gt; </span> </p> </td> 
   <td colname="col2"> <p> 单个最近搜索节点。 您可以有多个最近搜索节点。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-term&gt; </span> </p> </td> 
   <td colname="col2"> <p> 客户之前搜索的词。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> 指向上一搜索的链接。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 结果 {#section_EC496F5CA2634158891455E2F6DF6833}

“结果”集是XML响应的可自定义区域。 每个索引在元数据的字段命名机制中都是唯一的。 每个结果都返回了常用字段，如标题、说明和URL。 但是，为索引中的页面定义的任何元数据都可以在每个结果节点中使用。 分类、价格、颜色和缩略图只是一些选项，您可以将它们应用于结果，从而生成更引人注目的搜索结果。

根据特定于您的实施的元数据自定义结果格式。 此处包含结果中显示的所有结果数据，包括缩略图图像URL。

此外，还可以在页面中配置多个结果区域，如“特色结果”，或单独的“产品”和“内容”结果部分。 在这些情况下，HTML中会提供多个结果区域，但facet仅与主结果集关联。

示例：

```xml
 <results> 
  <result> 
    <index><![CDATA[1]]></index> 
    <result-title><![CDATA[New Year's Eve Slumber Party]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/new-years-eve-slumber-party-705199/]]></url> 
    <meta-description><![CDATA[Fun New Year's celebration ideas for your kids]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/new-years-eve-

slumber-party-parties-photo-80-FF1200SLEEPA18.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/new-years-eve- 
slumber-party-parties-photo-160-FF1200SLEEPA18.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Nancy Mades]]></byline> 
    <blurb><![CDATA[Fun New Year's celebration ideas for your kids]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[2]]></index> 
    <result-title><![CDATA[10 Holiday Traditions to Start This Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/10-holiday-traditions-to-start-this-year-704781/]]></url> 
    <meta-description><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/10-holiday- 
traditions-to-start-this-year-parties-photo-80-FF1107HOLIA01.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/10-holiday- 
traditions-to-start-this-year-parties-photo-160-FF1107HOLIA01.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Julie Taylor]]></byline> 
    <blurb><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[3]]></index> 
    <result-title><![CDATA[A Perfect New Year's Eve]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/a-perfect-new-years-eve-705258/]]></url> 
    <meta-description><![CDATA[You can turn New Year's into a celebration for the whole family.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Teri Keough]]></byline> 
    <blurb><![CDATA[You can turn New Year's into a celebration for the whole family.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[4]]></index> 
    <result-title><![CDATA[New Year's Fun and Games]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/new-years-fun-and-games-705220/]]></url> 
    <meta-description><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Charlotte Meryman]]></byline> 
    <blurb><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[5]]></index> 
    <result-title><![CDATA[11 Great Ways to Start the New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/11-great-ways-to-start-the-new-year-705552/]]></url> 
    <meta-description><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Emily Block]]></byline> 
    <blurb><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[6]]></index> 
    <result-title><![CDATA[Celebrating Chinese New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/celebrating-chinese-new-year-705260/]]></url> 
    <meta-description><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[7]]></index> 
    <result-title><![CDATA[New Year's Eve, Family Style]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/new-years-eve-family-style-701283/]]></url> 
    <meta-description><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[8]]></index> 
    <result-title><![CDATA[Chinese New Year Activities]]></result-title> 
    <url><![CDATA[https://mysite.com/crafts/chinese-new-year-activities-710345/]]></url> 
    <meta-description><![CDATA[Activities for celebrating Chinese New Year.]]></meta-description> 
    <category><![CDATA[crafts]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Activities for celebrating Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[9]]></index> 
    <result-title><![CDATA[More Organized in the New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/more-organized-in-the-new-year-701284/]]></url> 
    <meta-description><![CDATA[Tips for getting your household more organized--and getting the kids to help.]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Tips for getting your household more organized--and getting your kids to help out.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[10]]></index> 
    <result-title><![CDATA[Checklists: Year-End Safety Checklist]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/checklists-year-end-safety-checklist-701352/]]></url> 
    <meta-description><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></blurb> 
  </result>   
 </results> 
</customer-result> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>结果中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;index&gt; </span> </p> </td> 
   <td colname="col2"> <p> 此结果集中结果的序列号。 在此示例中，每页显示十个结果，在结果的第2页上，第一个项的索引为11。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> 此页面的面向客户的标题。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;url&gt; </span> </p> </td> 
   <td colname="col2"> <p> 此页面的URL。 它用于创建允许客户点击结果的超链接。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 搜索表单{#section_F92D8C3D37174A10A4E26CAFF3F3DF89}

示例：

```xml
<search-form> 
 <include-tnt-mbox>1 </included-tnt-mbox> 
 <autocomplete> 
  <css><![CDATA[<!--link rel="stylesheet" type="te 
        xt/css"href="//content.atomz.com/sp000000a8/publish/autoc 
        omplete_styles.css?sp_css_cache_ver=2" /-->]]> 
  </css> 
  <form-content><![CDATA[<div id="autocomplete"></div>]]> 
  </form-content> 
  <js><![CDATA[<script type="text/javascript" 
   src="//content.atomz.com/sp100491de/publish/autoc 
   omplete_data.js?sp_js_cache_ver=3"></script>]]> 
  </js> 
 </autcomplete> 
 <hidden-parameters> 
  <parameter> 
   <name><![CDATA[store]]></name> 
   <value><![CDATA[mens]]></value> 
  </parameter> 
 </hidden-parameters> 
</search-form>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>搜索表单中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;include-tnt-mbox&gt; </span> </p> </td> 
   <td colname="col2"> <p> 可选. 当XML中存在值1时，它表示您的帐户已链接到<span class="keyword"> Test&amp;目标 </span>，并且至少有一个业务规则位于A:B测试中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;autocomplete&gt; </span> </p> </td> 
   <td colname="col2"> <p> 可选. 使用自动完成时，此节点会显示在页面上，指示CSS和JavaScript以及表单中的内容存在。 除非某人更改了自动完成设置，否则这些字段通常不会更改。 在这种情况下，xxx_cache_ver字段会递增，以强制客户浏览器上缓存的内容失效。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;css&gt; </span> </p> </td> 
   <td colname="col2"> <p> 与自动完成关联的CSS。 建议您将此标记放在页面的高处以改进页面渲染。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;form-content&gt; </span> </p> </td> 
   <td colname="col2"> <p> 搜索自中所需的内容，以自动完成实用程序与正确的控件关联。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;js&gt; </span> </p> </td> 
   <td colname="col2"> <p> 自动完成所需的自定义JavaScript。 建议您将此标记放在页面中低位以改进页面渲染。 自动完成也需要YUI JavaScript。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;hidden-parameters&gt; </span> </p> </td> 
   <td colname="col2"> <p> 包含要包含在搜索表单中的所有隐藏参数（名称和值）。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 排序 {#section_32DC50A103BF491BA3665A5CADCCAADE}

以下示例显示了三选项排序菜单的数据。 该菜单允许客户按相关性、标题或评级进行排序。 当前选定的项目包含属性“selected=true”。 &quot; 始终优惠相关选项，以允许客户返回到最初显示的默认搜索结果。

示例：

```xml
 <sort> 
  <sort-item selected="true"> 
   <label><![CDATA[Relevance]]></label> 
   <value><![CDATA[relevance]]></value> 
   <link><![CDATA[]]></link> 
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Title]]></label> 
   <value><![CDATA[title]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=title;x1=content-type]]></link>     
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Rating]]></label> 
   <value><![CDATA[user-rating]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=user-rating;x1=content-type]]></link>     
  </sort-item> 
 </sort>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>“排序”菜单中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> 选项的面向客户的文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> 表示此选项的"sort"查询字符串参数的值。 如果使用<span class="codeph"> &lt;link&gt; </span>值，则不需要此标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> 对于未选择的选项，<span class="codeph"> &lt;link&gt; </span>参数包含返回相同结果集的相对链接，该链接按新排序参数排序。 此字段对于当前选定的排序选项为空。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 建议{#section_D81BCE46F0AF443695DF9C4BA084B716}

当结果很少或没有结果时，将返回建议。 此节点包含的术语会生成成功的查询，并可在“无结果”页面上显示。 此时还会返回链接，以便客户可以跳转到新查询。

示例：

```xml
 <suggestions> 
  <suggestion-item> 
   <link><![CDATA[?q=video]]></link> 
   <word><![CDATA[video]]> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>建议中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p>用于创建用于搜索建议词结果的超链接的相对链接。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;word&gt; </span> </p> </td> 
   <td colname="col2"> <p>建议的术语。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 区域{#section_15D8AA585F3246799968BA88EE2C9FC2}

示例：

```xml
<zones> 
 <zone> 
  <name><![CDATA[best-sellers]]></name> 
  <display><![CDATA[1]]></display> 
 </zone> 
</zones> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>区域中的标记 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;zone&gt; </span> </p> </td> 
   <td colname="col2"> <p> 单个区域节点。 您可以有多个区域节点。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;name&gt; </span> </p> </td> 
   <td colname="col2"> <p> 区域的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;display&gt; </span> </p> </td> 
   <td colname="col2"> <p> 1或0表示区域是否显示。 实际区域内容可以是网页或搜索结果中的静态区域，如最畅销商品或相关产品。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Adobe Experience Manager {#reference_DBE13C606C3A4BB185DE53F88D0D3048}的向导式搜索XML输出

描述AEM(Adobe Experience Manager)标准XML响应输出的表。

另请参阅 . [向导式搜索XML输出](../c-appendices/c-guidedsearchoutput.md#reference_D93E859A277643068B10AE7A61C973EA)

您可以查看以下XML响应：

* [横幅广告](../c-appendices/c-guidedsearchoutput.md#section_B16EDC5533FA4494AC9983AA7357CBE3)
* [Breadcrumb](../c-appendices/c-guidedsearchoutput.md#section_49EA7043FBE44315A79A4E738BE30114)
* [自定义字段](../c-appendices/c-guidedsearchoutput.md#section_38DD31AFE5DD4263A63644AFF484E0F4)
* [彩块化](../c-appendices/c-guidedsearchoutput.md#section_BE98990E3DD748A1BD4E0CA322314B79)
* [头](../c-appendices/c-guidedsearchoutput.md#section_5305B1DC5774439485CA0665DB683F9C)
* [菜单和排序](../c-appendices/c-guidedsearchoutput.md#section_A34CBB645DBF4C70A12A5B7E81211295)
* [分页](../c-appendices/c-guidedsearchoutput.md#section_E52F81C6A6EB4B8F996157B657EC540F)
* [查询](../c-appendices/c-guidedsearchoutput.md#section_3DAA1013F09742869B80F6A361816E6C)
* [最近搜索](../c-appendices/c-guidedsearchoutput.md#section_17F942F6EC07456DABED7A483AC08446)
* [结果](../c-appendices/c-guidedsearchoutput.md#section_155A80B8C4F641678DD9C8F257108412)
* [搜索表单](../c-appendices/c-guidedsearchoutput.md#section_9E4B99D4FEDC49629F6C7E866F3A7493)
* [建议](../c-appendices/c-guidedsearchoutput.md#section_2899FACB9AD84F60B3687C1B4EF09E15)
* [模板](../c-appendices/c-guidedsearchoutput.md#section_1E2BB2F274B04F5491A4CCCC38F507BD)
* [Zones](../c-appendices/c-guidedsearchoutput.md#section_26C4A947E7B1474A8E37D86D9579B93E)

## 横幅广告 {#section_B16EDC5533FA4494AC9983AA7357CBE3}

网站搜索/促销可以管理客户的横幅，将横幅插入网页的各个部分。

示例横幅：

以下是放置在名为“top”的页面区域中的横幅的示例。

```xml
   <banners> 
       <banner> 
           <area><![CDATA[top]]></area> 
           <content><![CDATA[<div style="color:#70A100">We have custom shipping</div>]]></content> 
       </banner> 
    </banners> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>节点 </p> </th> 
   <th colname="col2" class="entry"> <p>父节点 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>横幅 </p> </td> 
   <td colname="col2"> <p>客户成果 </p> </td> 
   <td colname="col3"> <p>包含0-n个横幅节点，指示每个横幅区域以及插入该区域的内容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>横幅 </p> </td> 
   <td colname="col2"> <p>横幅 </p> </td> 
   <td colname="col3"> <p>单个横幅节点。 您可以有多个横幅节点。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>面积 </p> </td> 
   <td colname="col2"> <p>横幅 </p> </td> 
   <td colname="col3"> <p>网页上显示横幅的区域。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>content </p> </td> 
   <td colname="col2"> <p>横幅 </p> </td> 
   <td colname="col3"> <p>横幅内容。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Breadcrumb {#section_49EA7043FBE44315A79A4E738BE30114}

支持多个痕迹导航。 您可以在&#x200B;**[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**&#x200B;中定义痕迹导航及其相应行为。 此外，您需要为定义的每个痕迹导航指定唯一的名称。 痕迹导航XML节点迭代所有定义的痕迹导航。 建议在搜索结果中只显示一个痕迹导航。

在以下示例中，每次客户通过facet进一步缩小范围时，所做的选择都会添加到痕迹导航中。 每个项目都表示为`<breadcrumb-item>`。

痕迹导航节点示例：

```xml
    <breadcrumbs> 
  <breadcrumb> 
            <name><![CDATA[default]]></name> 
     <breadcrumb-item> 
   <link><![CDATA[?i=1;q=mens;sp_cs=UTF-8;view=xml]]></link> 
   <value><![CDATA[mens]]></value> 
                <label><![CDATA[]]></label> 
      </breadcrumb-item> 
     <breadcrumb-item> 
   <link><![CDATA[?i=1;q=mens;q1=Channel;sp_cs=UTF-8;view=xml;x1=brand]]></link> 
   <value><![CDATA[Channel]]></value> 
                <label><![CDATA[brand]]></label> 
      </breadcrumb-item> 
   </breadcrumb> 
    </breadcrumbs> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>节点 </p> </th> 
   <th colname="col2" class="entry"> <p>父节点 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>痕迹 </p> </td> 
   <td colname="col2"> <p>客户成果 </p> </td> 
   <td colname="col3"> <p> 包含定义每个痕迹导航的0-n痕迹导航节点。 大多数客户只有一个痕迹导航。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>痕迹 </p> </td> 
   <td colname="col2"> <p>痕迹 </p> </td> 
   <td colname="col3"> <p> 包含定义痕迹导航定义的子节点。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p>痕迹 </p> </td> 
   <td colname="col3"> <p> 痕迹导航的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>breadcrumb项目 </p> </td> 
   <td colname="col2"> <p>痕迹导航中的单个项。 每个项目表示跟踪中的步骤，因为用户会缩小结果集的范围。 </p> </td> 
   <td colname="col3"> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>breadcrumb项目 </p> </td> 
   <td colname="col3"> <p> 显示所需视图的搜索结果的相对链接。 单击痕迹导航链接可将客户带到视图，随后所有的细化都将被删除。 还提供了其他选项，如删除和删除。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>value </p> </td> 
   <td colname="col2"> <p>breadcrumb项目 </p> </td> 
   <td colname="col3"> <p> 痕迹导航项的面向客户的文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>标签 </p> </td> 
   <td colname="col2"> <p>breadcrumb项目 </p> </td> 
   <td colname="col3"> <p> 标签标签输出一个标签，用于描述已选择哪个facet来生成该痕迹导航项的痕迹导航值。 它仅用于向导式痕迹导航块的上下文。 对于查询术语步骤，此值为空。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 自定义字段{#section_38DD31AFE5DD4263A63644AFF484E0F4}

自定义字段是具有全局上下文的变量的杂项集合。 它通常用于传递在搜索结果页面的元数据中设置的用于SEO的变量。

自定义字段节点示例：

```xml
    <custom-fields> 
        <custom-field name="seo-search-title"><![CDATA[Geometrixx Search Results]]></custom-field> 
        <custom-field name="seo-search-keywords"><![CDATA[]]></custom-field> 
    </custom-fields> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>节点 </p> </th> 
   <th colname="col2" class="entry"> <p>父节点 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>custom-fields </p> </td> 
   <td colname="col2"> <p>客户成果 </p> </td> 
   <td colname="col3"> <p> 可以包含定义自定义字段的0-n子节点。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>custom-field </p> </td> 
   <td colname="col2"> <p>custom-fields </p> </td> 
   <td colname="col3"> <p> 可选. 包含由name属性指示的给定自定义字段的值。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 彩块化{#section_BE98990E3DD748A1BD4E0CA322314B79}

彩块化是细化选项，让客户能够对结果进行筛选。 彩块化通常用于分类、价格范围、颜色选择和其他属性细化。 彩块化构建在索引中的元数据之上。

客户在分类中向下移动时，通常会隐藏或显示分类彩块化。 最高级别的分类(类别)称为第1层。 当客户单击第1层选项时，将显示第2层（子类别）优化选项，而第1层选项将消失。 当客户单击第2层选项时，将显示第3层（子子类别）优化选项，而第2层选项将消失。 如上所述，这些选项被隐藏和显示；您的web应用程序不会影响它们。

每个facet都包含在`<facet-item>`标记中。 在以下示例中，它显示了一个允许客户按“假日”优化搜索结果的方面。

彩块示例：

```xml
<facets>          
     <facet> 
         <facet-title><![CDATA[Department]]></facet-title> 
                <behavior><![CDATA[sticky]]></behavior> 
                <selected>1</selected> 
                <undo-link><![CDATA[?i=1;lang=enus;q=*;q1=Armora+Jeans;sp_staged=1;view=xml;x1=brand]]></undo-link> 
      <facet-value> 
          <selected><![CDATA[true]]></selected> 
              <label><![CDATA[Mens]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Armora+Jeans;q2=Mens;sp_staged=1;view=xml;x1=brand;x2=leveli]]></link> 
       <count><![CDATA[3]]></count> 
                        <undolink><![CDATA[?i=1;lang=enus;q=*;q1=Armora+Jeans;sp_staged=1;view=xml;x1=brand]]></undolink> 
      </facet-value> 
      </facet> 
     <facet> 
         <facet-title><![CDATA[Sub-Category]]></facet-title> 
                <behavior><![CDATA[sticky]]></behavior> 
                <selected>0</selected> 
      <facet-value>           
              <label><![CDATA[Apparel]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans;q3=Apparel;sp_staged=1;view=xml;x1=leveli;x2=brand;x3=levelii]]></link> 
       <count><![CDATA[3]]></count>                         
      </facet-value>   
      </facet>         
     <facet> 
         <facet-title><![CDATA[Brand]]></facet-title> 
                <behavior><![CDATA[multi-select]]></behavior> 
                <selected>1</selected> 
                <undo-link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;sp_staged=1;view=xml;x1=leveli]]></undo-link> 
      <facet-value>        
              <label><![CDATA[Amoura]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Amoura;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[9]]></count>                         
      </facet-value>   
      <facet-value>         
              <label><![CDATA[Armora]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Armora;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[12]]></count>                        
      </facet-value>   
      <facet-value> 
          <selected><![CDATA[true]]></selected> 
              <label><![CDATA[Armora Jeans]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Armora+Jeans;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
 
       <count><![CDATA[3]]></count> 
                        <undolink><![CDATA[?i=1;lang=enus;q=*;q1=Mens;sp_staged=1;view=xml;x1=leveli]]></undolink> 
      </facet-value>   
      <facet-value>           
              <label><![CDATA[Art of Grooming]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Art+of+Grooming;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[4]]></count>                         
      </facet-value>   
      <facet-value>          
              <label><![CDATA[Bear Co.]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Bear+Co.;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[1]]></count> 
      </facet-value> 
      <facet-value>      
              <label><![CDATA[Citizens]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Citizens;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[4]]></count> 
      </facet-value> 
      <facet-value> 
              <label><![CDATA[D&amp;B]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|D%26B;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[17]]></count> 
      </facet-value> 
      <facet-value> 
              <label><![CDATA[David Yuri]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|David+Yuri;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[2]]></count>    
      </facet-value>   
      </facet> 
    </facets> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>节点 </p> </th> 
   <th colname="col2" class="entry"> <p>父节点 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>facet </p> </td> 
   <td colname="col2"> <p>客户成果 </p> </td> 
   <td colname="col3"> <p>容器facet节点，具有0-n个子节点，表示每个facet。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>fact </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p> 单个facet实例。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>facet-title </p> </td> 
   <td colname="col2"> <p>fact </p> </td> 
   <td colname="col3"> <p>facet的面向客户的标题。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>行为 </p> </td> 
   <td colname="col2"> <p>fact </p> </td> 
   <td colname="col3"> <p>Facet的行为。 例如，普通、粘滞或多选。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>selected </p> </td> 
   <td colname="col2"> <p>fact </p> </td> 
   <td colname="col3"> <p>1，否则为0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>还原链接 </p> </td> 
   <td colname="col2"> <p>fact </p> </td> 
   <td colname="col3"> <p> 仅当选择了小平面时显示。 撤消链接会还原整个彩块化。 例如，当它是多选facet时，它会取消选择该facet的所有选项。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>facet-value </p> </td> 
   <td colname="col2"> <p>fact </p> </td> 
   <td colname="col3"> <p>包含属于该facet的所有单个facet项。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>选定 </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>如果选择了具有facet的当前项，则此节点存在并设置为“true”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>标签 </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>facet选项的面向客户的标签。 默认情况下，这应已由HTML转义。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>链接 </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p> 相对链接，以便选项进一步细化。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>count（计数） </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>该精化结果集中的结果数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>还原链接 </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>选择facet值后，节点将返回“撤消链接”，允许客户退出选择单个facet选择。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 头 {#section_5305B1DC5774439485CA0665DB683F9C}

示例：

```xml
xml version="1.0" encoding="utf-8" standalone="yes" 
```

## 菜单和排序{#section_A34CBB645DBF4C70A12A5B7E81211295}

支持用于对结果进行排序的菜单，以及更改每页返回的结果数。 它还支持一个导航菜单，该菜单对于使用“搜索为导航”很有用。 帐户可以定义同一类型的多个菜单，并使用其中的任意菜单进行演示。

“示例菜单”节点：

以下示例显示了三选项排序菜单和导航菜单的数据。 通过“排序”菜单，客户可以按相关性、标题或评级进行排序。 当前选定的项目包含属性“selected=true”。 &quot; 始终优惠相关选项，以允许客户返回到最初显示的默认搜索结果。

```xml
<menus> 
        <menu> 
           <name><![CDATA[sort]]></name>         
             <item selected="true"> 
          <label><![CDATA[Relevance]]></label> 
          <value><![CDATA[relevance]]></value> 
          <link><![CDATA[ ]]></link> 
             </item> 
             <item> 
          <label><![CDATA[Lowest Price]]></label> 
          <value><![CDATA[Price]]></value> 
          <link><![CDATA[?i=1;q=mens;sort=Price;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item> 
             <item> 
          <label><![CDATA[Highest Price]]></label> 
          <value><![CDATA[Price_r]]></value> 
          <link><![CDATA[?i=1;q=mens;sort=Price_r;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item> 
             <item> 
          <label><![CDATA[Brand]]></label> 
          <value><![CDATA[brand]]></value> 
          <link><![CDATA[?i=1;q=mens;sort=brand;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item> 
        </menu> 
        <menu> 
            <name><![CDATA[ss_head_nav]]></name>   
                    <item> 
                        <label><![CDATA[WOMEN'S]]></label> 
          <value><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1;i=1;m_ss_head_nav=WOMEN'S]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[MEN'S]]></label> 
          <value><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></value> 
          <link><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[JEWELRY & ACCESSORIES]]></label> 
          <value><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1]]></value> 
          <link><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1;i=1;m_ss_head_nav=JEWELRY+%26+ACCESSORIES]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[BEAUTY & FRAGRANCE]]></label> 
          <value><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=BEAUTY+%26+FRAGRANCE]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[GIFTS & HOME]]></label> 
          <value><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=GIFTS+%26+HOME]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[CHILDREN & TOYS]]></label> 
          <value><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=CHILDREN+%26+TOYS]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[ELECTRONICS]]></label> 
          <value><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=ELECTRONICS]]></link> 
                    </item> 
        </menu> 
    </menus> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>节点 </p> </th> 
   <th colname="col2" class="entry"> <p>父节点 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>菜单 </p> </td> 
   <td colname="col2"> <p>客户成果 </p> </td> 
   <td colname="col3"> <p>包含定义每个菜单的0-n个子节点。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>菜单 </p> </td> 
   <td colname="col2"> <p>菜单 </p> </td> 
   <td colname="col3"> <p>菜单的单个实例（对应于在<span class="uicontrol">设计</span> &gt; <span class="uicontrol">导航</span> &gt; <span class="uicontrol">菜单</span>中定义的菜单）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>名称 </p> </td> 
   <td colname="col2"> <p>菜单 </p> </td> 
   <td colname="col3"> <p>菜单的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>项目 </p> </td> 
   <td colname="col2"> <p>菜单 </p> </td> 
   <td colname="col3"> <p>定义菜单中的每个项。 如果当前选择了给定的菜单项，则选定的可选属性将设置为true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>标签 </p> </td> 
   <td colname="col2"> <p>项目 </p> </td> 
   <td colname="col3"> <p>菜单项的面向客户的文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>值 </p> </td> 
   <td colname="col2"> <p>项目 </p> </td> 
   <td colname="col3"> <p>表示菜单项的值(也设置菜单的查询参数值)。 如果使用&lt;link&gt;值，则不需要此标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>链接 </p> </td> 
   <td colname="col2"> <p>项目 </p> </td> 
   <td colname="col3"> <p>对于未选择的选项，&lt;link&gt;参数包含返回相同结果集但应用了菜单选项的相对链接。 此字段对于当前选定的排序选项为空。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 分页{#section_E52F81C6A6EB4B8F996157B657EC540F}

结果集将拆分到多个页面。 通常，客户在单个页面上显示10 - 20个结果。 后续结果将显示在下一页。 分页XML允许您构建一组导航链接，以便客户可以逐页浏览结果集。 有四个可用的导航链接：first、last、next和previous。 每种类型的链接都可让客户快速浏览页面，以便轻松地审阅和优化所需内容。

以下示例显示了在第一页上搜索的分页，其中将分页配置为显示指向五个页面的链接。

分页示例：

```xml
    <pagination> 
        <total-pages><![CDATA[112]]></total-pages> 
        <pages> 
     <page position="first"><![CDATA[]]></page> 
     <page position="last"><![CDATA[?i=1;page=112;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
     <page position="next"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="1" selected="true"><![CDATA[?i=1;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="2"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="3"><![CDATA[?i=1;page=3;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="4"><![CDATA[?i=1;page=4;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="5"><![CDATA[?i=1;page=5;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
        </pages> 
    </pagination> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>节点 </p> </th> 
   <th colname="col2" class="entry"> <p>父节点 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>分页 </p> </td> 
   <td colname="col2"> <p>客户成果 </p> </td> 
   <td colname="col3"> <p> 结果页总数，基于结果数除以每页结果数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>总页数 </p> </td> 
   <td colname="col2"> <p>分页 </p> </td> 
   <td colname="col3"> <p>将搜索结果分布到的页面总数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>页面 </p> </td> 
   <td colname="col2"> <p>分页 </p> </td> 
   <td colname="col3"> <p>包含0-n个页面节点，用于定义分页中的每个页面。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>page </p> </td> 
   <td colname="col2"> <p>页面 </p> </td> 
   <td colname="col3"> <p>存在四个特殊页面节点：第一个、最后一个、上一个和下一个。 这四个页面是可选的，仅在有意义时才显示在结果集中。 例如，如果您位于第1页，则不存在“上一个”链接。 所有其他页面都指示一个位置。 列出的页数取决于在分页用户界面中配置的“页面链接数”。 “选定”属性指示客户当前所在的页面。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 查询 {#section_3DAA1013F09742869B80F6A361816E6C}

示例查询节点：

```xml
    <query> 
        <user-query><![CDATA[mens]]></user-query> 
 <lower-results><![CDATA[1]]></lower-results> 
 <upper-results><![CDATA[12]]></upper-results> 
 <total-results><![CDATA[265]]></total-results> 
    </query> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>节点 </p> </th> 
   <th colname="col2" class="entry"> <p>父节点 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>query </p> </td> 
   <td colname="col2"> <p>客户成果 </p> </td> 
   <td colname="col3"> <p> 提供查询概述的全局节点。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>用户查询 </p> </td> 
   <td colname="col2"> <p>查询 </p> </td> 
   <td colname="col3"> <p> 搜索的关键字。 如果“<span class="uicontrol">是否是You Mean </span>”由于原始词未产生结果而自动搜索建议词，则会反映在搜索的新关键词中（请参阅建议节点以获取原始关键词）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>低结果 </p> </td> 
   <td colname="col2"> <p>查询 </p> </td> 
   <td colname="col3"> <p> 此页上第一个结果的项目编号。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>上结果 </p> </td> 
   <td colname="col2"> <p>查询 </p> </td> 
   <td colname="col3"> <p> 此页上最后一个结果的项目编号。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>总结果 </p> </td> 
   <td colname="col2"> <p>查询 </p> </td> 
   <td colname="col3"> <p> 匹配用户查询的结果总数。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最近搜索{#section_17F942F6EC07456DABED7A483AC08446}

“最近搜索”是基于Cookie的功能，仅当您将Cookie信息中继至网站搜索/促销服务器时才有效。

最近搜索的示例：

```xml
    <recent-searches> 
        <clear-link><![?q=womens&gscr=clear]]></clear-link> 
        <recent-search> 
            <link><![?q=mens]]></link> 
            <label><![CDATA[mens]]></label> 
        <recent-search> 
    </recent-searches> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>节点 </p> </th> 
   <th colname="col2" class="entry"> <p>父节点 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>最近搜索 </p> </td> 
   <td colname="col2"> <p>客户成果 </p> </td> 
   <td colname="col3"> <p>仅当搜索有最近搜索时，节点才存在。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>清除链接 </p> </td> 
   <td colname="col2"> <p>最近搜索 </p> </td> 
   <td colname="col3"> <p>清除所有客户最近搜索的相对路径。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>最近搜索 </p> </td> 
   <td colname="col2"> <p>最近搜索 </p> </td> 
   <td colname="col3"> <p>定义最近搜索。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>链接 </p> </td> 
   <td colname="col2"> <p>最近搜索 </p> </td> 
   <td colname="col3"> <p>创建链接的路径，该链接执行用户最近执行的搜索。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>标签 </p> </td> 
   <td colname="col2"> <p>最近搜索 </p> </td> 
   <td colname="col3"> <p>最近搜索的面向客户的显示标签。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 结果 {#section_155A80B8C4F641678DD9C8F257108412}

“结果”集是XML响应的可自定义区域。 每个索引在元数据的字段命名机制中都是唯一的。 每个结果都返回了常用字段，如标题、说明和URL。 但是，为索引中的页面定义的任何元数据都可以在每个结果节点中使用。 分类、价格、颜色和缩略图只是一些选项，您可以将它们应用于结果，从而生成更引人注目的搜索结果。

根据特定于您的实施的元数据自定义结果格式。 此处包含结果中显示的所有结果数据，包括缩略图图像URL。

此外，还可以在页面中配置多个结果区域，如“特色结果”，或单独的“产品”和“内容”结果部分。 在这些情况下，HTML中会提供多个结果区域，但facet仅与主结果集关联。

示例结果节点：

```xml
    <results> 
        <result-set> 
            <name><![CDATA[default]]></name> 
         <result> 
                    <field name="index"><![CDATA[1]]></field> 
                    <field name="sku"><![CDATA[200190]]></field> 
                    <field name="pagename"><![CDATA[Relaxed Paint Splattered]]></field> 
 
                    <field name="img_sm_url"><![CDATA[https://geometrixx.com/images/08_geometrixx_icon_men.jpg]]></field> 
      <field name="brand"><![CDATA[Armora Jeans]]></field> 
      <field name="price"><![CDATA[195]]></field> 
      <field name="foundIn"><![CDATA[Mens,  
            Apparel,  
          Denim]]></field> 
         </result>   
         <result> 
                    <field name="index"><![CDATA[2]]></field> 
                    <field name="sku"><![CDATA[200195]]></field> 
                    <field name="pagename"><![CDATA[Tumbled Jeans]]></field> 
 
                    <field name="img_sm_url"><![CDATA[https://geometrixx.com/images/08_geometrixx_icon_men.jpg]]></field> 
      <field name="brand"><![CDATA[Armora Jeans]]></field> 
      <field name="price"><![CDATA[235]]></field> 
      <field name="foundIn"><![CDATA[Mens,  
            Apparel,  
          Denim]]></field> 
         </result>    
         <result> 
                    <field name="index"><![CDATA[3]]></field> 
                    <field name="sku"><![CDATA[200196]]></field> 
                    <field name="pagename"><![CDATA[Montana Relaxed]]></field> 
 
                    <field name="img_sm_url"><![CDATA[https://geometrixx.com/images/08_geometrixx_icon_men.jpg]]></field> 
      <field name="brand"><![CDATA[Armora Jeans]]></field> 
      <field name="price"><![CDATA[220]]></field> 
      <field name="foundIn"><![CDATA[Mens,  
            Apparel,  
          Denim]]></field> 
         </result>         
        </result-set>   
    </results> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>节点 </p> </th> 
   <th colname="col2" class="entry"> <p>父节点 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>结果 </p> </td> 
   <td colname="col2"> <p>客户成果 </p> </td> 
   <td colname="col3"> <p>0-n个结果集的容器节点。 零结果集意味着您处于特殊的无结果登陆页。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>结果集 </p> </td> 
   <td colname="col2"> <p>结果 </p> </td> 
   <td colname="col3"> <p>传入的搜索可触发多个搜索。 每个结果集都包含执行的特定命名搜索的结果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>名称 </p> </td> 
   <td colname="col2"> <p>结果集 </p> </td> 
   <td colname="col3"> <p>结果集所属的搜索的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>结果 </p> </td> 
   <td colname="col2"> <p>结果集 </p> </td> 
   <td colname="col3"> <p>包含与结果集的单个结果关联的所有字段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>字段 </p> </td> 
   <td colname="col2"> <p>结果 </p> </td> 
   <td colname="col3"> <p>name属性定义所显示索引中字段的名称。 该值是该字段的实际值。 某些结果可能缺少与单个结果无关的字段。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 搜索表单{#section_9E4B99D4FEDC49629F6C7E866F3A7493}

搜索表单包含在结果集中，让客户动态地构建其搜索表单。 此步骤是可选的。 大多数客户都有固定的搜索表单。 但是，它确实允许客户根据至少一个执行A:B测试的业务规则来确定搜索表单是否需要Test&amp;目标 mbox。 同样，它允许客户自动获取最新的自动完成CSS和JavaScript。

搜索表单XML的示例：

```xml
    <search-form> 
        <include-tnt-mbox>1</include-tnt-mbox> 
        <autocomplete> 
            <enabled>1</enabled> 
            <css><![CDATA[<link rel="stylesheet" type="text/css" href="https://content.t1.atomz.com/sp10043554/stage/autocomplete_styles.css?sp_js_param=2" /> 
]]></css> 
 
            <form-content><![CDATA[<div id="autocomplete"></div> 
<input type="hidden" name="sp_staged" id="sp_staged" value="1" /> 
]]></form-content> 
            <javascript><![CDATA[<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/utilities/utilities.js"></script> 
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/datasource/datasource-min.js"></script> 
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/autocomplete/autocomplete-min.js"></script> 
<script type="text/javascript" src="https://content.t1.atomz.com/sp10043554/stage/autocomplete_data.js?sp_js_param=3"></script>]]></javascript> 
        </autocomplete> 
    </search-form> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>节点 </p> </th> 
   <th colname="col2" class="entry"> <p>父节点 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>搜索表单 </p> </td> 
   <td colname="col2"> <p>客户成果 </p> </td> 
   <td colname="col3"> <p>包含用于驱动搜索表单的数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>include-tnt-mbox </p> </td> 
   <td colname="col2"> <p> 搜索表单 </p> </td> 
   <td colname="col3"> <p>从技术上讲，只有在至少有一个执行Test&amp;目标 A:B测试的业务规则时，您才需要在搜索表单中使用mbox。 此节点指示您是否需要mbox，或是否允许您减少Test&amp;目标服务器上的点击次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自动完成 </p> </td> 
   <td colname="col2"> <p>搜索表单 </p> </td> 
   <td colname="col3"> <p>容纳与自动完成相关的子节点。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>已启用 </p> </td> 
   <td colname="col2"> <p>自动完成 </p> </td> 
   <td colname="col3"> <p>当搜索帐户使用自动完成时，设置为1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>css </p> </td> 
   <td colname="col2"> <p> 自动完成 </p> </td> 
   <td colname="col3"> <p> CSS实现自动完成。 将此节点放在页面上。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 表单内容 </p> </td> 
   <td colname="col2"> <p>自动完成 </p> </td> 
   <td colname="col3"> <p>插入到搜索表单中的内容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javascript </p> </td> 
   <td colname="col2"> <p>自动完成 </p> </td> 
   <td colname="col3"> <p>JavaScript实现自动完成。 将此节点放在页面上尽可能低。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 建议{#section_2899FACB9AD84F60B3687C1B4EF09E15}

客户可以通过以下三种方式配置&#x200B;**[!UICONTROL Did You Mean]**&#x200B;功能：由于没有结果而提出建议，在没有结果时自动搜索第一个建议，或由于结果低而提出建议（如果建议的结果数较高）。 所有建议都会产生结果。

此建议节点包含的术语会生成成功的查询。 此时还会返回链接，以便客户可以跳转到新查询。

由于0个结果而建议的输出示例：

```xml
    <suggestions> 
        <auto-searched>0</auto-searched> 
        <suggestions-low-results>0</suggestions-low-results> 
 <suggestion-item> 
     <link><![CDATA[?i=1;q=arcade;sp_cs=UTF-8;view=xml]]></link> 
     <word><![CDATA[arcade]]></word> 
 </suggestion-item>    
    </suggestions>
```

根据建议自动搜索的输出示例：

```xml
    <suggestions> 
        <auto-searched>1</auto-searched> 
        <orig-query><![CDATA[arcace]]></orig-query> 
        <suggestions-low-results>0</suggestions-low-results>         
    </suggestions> 
```

由于结果低而建议的输出示例：

```xml
   <suggestions> 
        <auto-searched>0</auto-searched> 
        <suggestions-low-results>1</suggestions-low-results> 
 <suggestion-item> 
     <link><![CDATA[?i=1;q=coffee;sp_cs=UTF-8;view=xml]]></link> 
     <word><![CDATA[coffee]]></word> 
 </suggestion-item>  
    </suggestions> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>节点 </p> </th> 
   <th colname="col2" class="entry"> <p>父节点 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>建议 </p> </td> 
   <td colname="col2"> <p>客户成果 </p> </td> 
   <td colname="col3"> <p> 包含定义建议的子节点（如果存在）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自动搜索 </p> </td> 
   <td colname="col2"> <p>建议 </p> </td> 
   <td colname="col3"> <p> 如果存在，则指示网站搜索/促销是否因没有结果而自动搜索新词。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>原始查询 </p> </td> 
   <td colname="col2"> <p>建议 </p> </td> 
   <td colname="col3"> <p> 当站点搜索/促销自动根据第一建议搜索时，查询节点中的用户查询显示所搜索的关键字。 此节点显示原始查询词。 将二者结合起来，让客户可以创建“搜索游戏机而不是游戏机”等结构。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>建议 — 低结果 </p> </td> 
   <td colname="col2"> <p>建议 </p> </td> 
   <td colname="col3"> <p>如果存在，则指示网站搜索/促销是否正在提出建议，因为当前搜索词产生的结果较低，而建议产生的结果要高得多。 可在<span class="uicontrol">中配置这两个阈值。</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>建议项 </p> </td> 
   <td colname="col2"> <p>建议 </p> </td> 
   <td colname="col3"> <p>包含0-n个节点，表示各种建议。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>链接 </p> </td> 
   <td colname="col2"> <p>建议项 </p> </td> 
   <td colname="col3"> <p>包含用于创建指向建议术语的链接的路径。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>词 </p> </td> 
   <td colname="col2"> <p>建议项 </p> </td> 
   <td colname="col3"> <p> 包含建议的字。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 模板 {#section_1E2BB2F274B04F5491A4CCCC38F507BD}

支持根据结果切换客户搜索体验的功能。 部分操作涉及在具有不同搜索结果布局的不同模板之间进行切换。 例如，您可能有一个模板，其中含有大量产品时的产品网格视图。 或者，在显示包含更多详细信息的单个结果时，您可能有一个“聚焦”模板。 当搜索不产生任何结果时，您也可能有“无结果”模板。 模板节点指示用于显示搜索结果的模板。

示例模板：

```xml
<template><![CDATA[grid]]></template>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>节点 </p> </th> 
   <th colname="col2" class="entry"> <p>父节点 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>模板 </p> </td> 
   <td colname="col2"> <p>客户成果 </p> </td> 
   <td colname="col3"> <p>指示用于显示搜索结果的模板的名称。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 区域{#section_26C4A947E7B1474A8E37D86D9579B93E}

区域是可通过业务规则打开或关闭的页面部分。 区域可以包含任何内容，包括（但不限于）彩块化、搜索、痕迹导航和静态内容。 客户网页上的区域应与网站搜索/促销相同。

区域节点示例：

```xml
    <zones> 
        <zone> 
            <name><![CDATA[brand-facet]]></name> 
            <display>1</display> 
        </zone> 
    </zones> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>节点 </p> </th> 
   <th colname="col2" class="entry"> <p>父节点 </p> </th> 
   <th colname="col3" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>区域 </p> </td> 
   <td colname="col2"> <p>客户成果 </p> </td> 
   <td colname="col3"> <p>包含0-n个区域。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>区域 </p> </td> 
   <td colname="col2"> <p>区域 </p> </td> 
   <td colname="col3"> <p> 单个区域节点。 您可以有多个区域节点。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>名称 </p> </td> 
   <td colname="col2"> <p>区域 </p> </td> 
   <td colname="col3"> <p>区域的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>显示 </p> </td> 
   <td colname="col2"> <p>1或0，指示显示还是隐藏与区域名称对应的区域。 </p> </td> 
   <td colname="col3"> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 示例 {#reference_64B7D8D228AF4B8D90EDF4DE507B0F84}

*搜索在虚构网站(称为“Geometrixx”)上的示例输出以及用于生成示例输出的示例演示模板。

* [输出示例](../c-appendices/c-guidedsearchoutput.md#section_515C000A18B847D59097D0A9CCC02636)
* [演示文稿模板示例](../c-appendices/c-guidedsearchoutput.md#section_AD42571DFB88491AA7F0FDF0929EBE97)

## 输出示例{#section_515C000A18B847D59097D0A9CCC02636}

*搜索在虚构网站(称为Geometrixx)上的输出示例。

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes" ?> 
<customer-results> 
    <query> 
        <user-query><![CDATA[*]]></user-query> 
 <lower-results><![CDATA[1]]></lower-results> 
 <upper-results><![CDATA[12]]></upper-results> 
 <total-results><![CDATA[1337]]></total-results> 
    </query> 
 
    <custom-fields> 
 
        <custom-field name="seo-search-title"><![CDATA[Geometrixx Search Results]]></custom-field> 
        <custom-field name="seo-search-keywords"><![CDATA[]]></custom-field> 
    </custom-fields> 
 
    <menus> 
 
        <menu> 
           <name>sort</name>

             <item selected="true"> 
 
          <label><![CDATA[Relevance]]></label> 
          <value><![CDATA[relevance]]></value> 
          <link><![CDATA[ ]]></link> 
             </item>

             <item> 
          <label><![CDATA[Lowest Price]]></label> 
          <value><![CDATA[Price]]></value> 
          <link><![CDATA[?i=1;q=*;sort=Price;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item>

             <item> 
          <label><![CDATA[Highest Price]]></label> 
          <value><![CDATA[Price_r]]></value> 
          <link><![CDATA[?i=1;q=*;sort=Price_r;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item>

             <item> 
          <label><![CDATA[Brand]]></label> 
          <value><![CDATA[brand]]></value> 
          <link><![CDATA[?i=1;q=*;sort=brand;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item>

        </menu> 
        <menu> 
            <name><![CDATA[ss_head_nav]]></name>

                    <label><![CDATA[WOMEN'S]]></label> 
      <value><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1;i=1;m_ss_head_nav=WOMEN'S]]></link>

                    <label><![CDATA[MEN'S]]></label> 
      <value><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></value> 
      <link><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></link>

                    <label><![CDATA[JEWELRY & ACCESSORIES]]></label> 
      <value><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1]]></value> 
      <link><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1;i=1;m_ss_head_nav=JEWELRY+%26+ACCESSORIES]]></link>

                    <label><![CDATA[BEAUTY & FRAGRANCE]]></label> 
      <value><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=BEAUTY+%26+FRAGRANCE]]></link>

                    <label><![CDATA[GIFTS & HOME]]></label> 
      <value><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=GIFTS+%26+HOME]]></link>

                    <label><![CDATA[CHILDREN & TOYS]]></label> 
      <value><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=CHILDREN+%26+TOYS]]></link>

                    <label><![CDATA[ELECTRONICS]]></label> 
      <value><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=ELECTRONICS]]></link>

        </menu> 
    </menus> 
 
    <breadcrumbs> 
  <breadcrumb> 
            <name><![CDATA[default]]></name> 
       
  <breadcrumb-item> 
    <link><![CDATA[?i=1;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></link> 
    <value><![CDATA[*]]></value> 
                        <label><![CDATA[]]></label> 
   </breadcrumb-item> 
          
   </breadcrumb> 
 
    </breadcrumbs> 
 
    <suggestions> 
        <auto-searched>0</auto-searched> 
         
        <suggestions-low-results>0</suggestions-low-results> 
         
    </suggestions> 
 
    <pagination> 
        <total-pages><![CDATA[112]]></total-pages> 
 
        <pages> 
     <page position="first"><![CDATA[]]></page> 
     <page position="last"><![CDATA[?i=1;page=112;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
      
     <page position="next"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="1" selected="true"><![CDATA[?i=1;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="2"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="3"><![CDATA[?i=1;page=3;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="4"><![CDATA[?i=1;page=4;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="5"><![CDATA[?i=1;page=5;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

        </pages> 
    </pagination> 
 
    <facets>  
         
     <facet-item> 
         <facet-title><![CDATA[Department]]></facet-title> 
                <selected>0</selected>

      <facet-value> 
           
              <label><![CDATA[Womens]]></label> 
 
       <link><![CDATA[?i=1;q=*;q1=Womens;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[219]]></count> 
                         
      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Mens]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Mens;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[202]]></count> 
                         
      </facet-value> 
   
      <facet-value>

              <label><![CDATA[Beauty &amp; Fragrance]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Beauty+%26+Fragrance;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[169]]></count> 
                         
      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Children &amp; Toys]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Children+%26+Toys;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[209]]></count> 
                         
      </facet-value>

      <facet-value> 
           
              <label><![CDATA[Electronics &amp; Toys]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Electronics+%26+Toys;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[200]]></count> 
                         
      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Gifts &amp; Home]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Gifts+%26+Home;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[156]]></count>

      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Jewelry &amp; Accessories]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Jewelry+%26+Accessories;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[182]]></count> 
                         
      </facet-value> 
   
      </facet-item> 
  
    </facets> 
 
    <results> 
        <result-set> 
            <name><![CDATA[default]]></name> 
               
         <result> 
                    <field name="index"><![CDATA[1]]></field> 
      <field name="brand"><![CDATA[Citizens]]></field> 
      <field name="price"><![CDATA[149]]></field> 
      <field name="foundIn"><![CDATA[Womens,  
            Apparel,  
          Denim]]></field> 
         </result>   
        
         <result> 
 
                    <field name="index"><![CDATA[2]]></field> 
      <field name="brand"><![CDATA[One For All]]></field> 
      <field name="price"><![CDATA[145]]></field> 
      <field name="foundIn"><![CDATA[Womens,  
            Apparel,  
          Denim]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[3]]></field> 
      <field name="brand"><![CDATA[Citizens]]></field> 
      <field name="price"><![CDATA[208]]></field> 
 
      <field name="foundIn"><![CDATA[Womens,  
            Apparel,  
          Denim]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[4]]></field> 
      <field name="brand"><![CDATA[Vera Watson]]></field> 
      <field name="price"><![CDATA[850]]></field> 
      <field name="foundIn"><![CDATA[Womens,  
            Dresses,  
          Day]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[5]]></field> 
 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[195]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[6]]></field> 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[80]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[7]]></field> 
      <field name="brand"><![CDATA[Petrol]]></field> 
      <field name="price"><![CDATA[85]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[8]]></field> 
      <field name="brand"><![CDATA[Woolberry]]></field> 
 
      <field name="price"><![CDATA[280]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[9]]></field> 
      <field name="brand"><![CDATA[Petrol]]></field> 
      <field name="price"><![CDATA[149]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
 
                    <field name="index"><![CDATA[10]]></field> 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[55]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[11]]></field> 
      <field name="brand"><![CDATA[Petrol]]></field> 
      <field name="price"><![CDATA[45]]></field> 
 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[12]]></field> 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[47]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
      
        </result-set>   
    </results>

    <banners> 
         
            <banner> 
                <area><![CDATA[top]]></area> 
                <content><![CDATA[<div style="color:#70A100">We have custom shipping</div>]]></content> 
            </banner>

    </banners> 
 
    <zones> 
        <zone> 
 
            <name><![CDATA[brand-facet]]></name> 
            <display>1</display> 
        </zone> 
    </zones> 
 
    <search-form> 
        <include-tnt-mbox>1</include-tnt-mbox> 
        <autocomplete> 
 
            <enabled>1</enabled> 
            <css><![CDATA[<link rel="stylesheet" type="text/css" href="https://content.t1.atomz.com/sp10043554/stage/autocomplete_styles.css?sp_js_param=2" /> 
]]></css> 
            <form-content><![CDATA[<div id="autocomplete"></div> 
<input type="hidden" name="sp_staged" id="sp_staged" value="1" /> 
]]></form-content> 
            <javascript><![CDATA[<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/utilities/utilities.js"></script> 
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/datasource/datasource-min.js"></script> 
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/autocomplete/autocomplete-min.js"></script> 
<script type="text/javascript" src="https://content.t1.atomz.com/sp10043554/stage/autocomplete_data.js?sp_js_param=3"></script>]]></javascript> 
        </autocomplete> 
    </search-form> 
 
</customer-results> 
```

## 演示文稿模板示例{#section_AD42571DFB88491AA7F0FDF0929EBE97}

以下是用于生成上述示例输出的示例演示模板。

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes" ?> 
<customer-results> 
    <query> 
        <user-query><![CDATA[<guided-query-param gsname="q" />]]></user-query> 
 <lower-results><![CDATA[<guided-results-lower>]]></lower-results> 
 <upper-results><![CDATA[<guided-results-upper>]]></upper-results> 
 <total-results><![CDATA[<guided-results-total>]]></total-results> 
    </query> 
 
    <custom-fields> 
        <custom-field name="seo-search-title"><![CDATA[Geometrixx Search Results]]></custom-field> 
        <custom-field name="seo-search-keywords"><![CDATA[<guided-general-field gsname="default" field="seo_search_keywords"/>]]></custom-field> 
    </custom-fields> 
 
    <menus> 
 
        <menu> 
           <name>sort</name> 
     <guided-menu gsname="sort"> 
         <guided-if-menu-item-selected> 
             <item selected="true"> 
          <label><![CDATA[<guided-menu-item-label />]]></label> 
          <value><![CDATA[<guided-menu-item-value />]]></value> 
          <link><![CDATA[ ]]></link> 
             </item> 
        <guided-else-menu-item-selected> 
             <item> 
          <label><![CDATA[<guided-menu-item-label />]]></label> 
          <value><![CDATA[<guided-menu-item-value />]]></value> 
          <link><![CDATA[<guided-menu-item-path />]]></link>     
             </item> 
        </guided-if-menu-item-selected> 
    </guided-menu> 
        </menu> 
        <menu> 
            <name><![CDATA[ss_head_nav]]></name> 
            <guided-menu gsname="ss_head_nav"> 
                <guided-if-menu-item-selected> 
                    <item selected="true"> 
                    <label><![CDATA[<guided-menu-item-label />]]></label> 
      <value><![CDATA[<guided-menu-item-value />]]></value> 
      <link><![CDATA[<guided-menu-item-path />]]></link> 
                <guided-else-menu-item-selected> 
                    <label><![CDATA[<guided-menu-item-label />]]></label> 
      <value><![CDATA[<guided-menu-item-value />]]></value> 
      <link><![CDATA[<guided-menu-item-path />]]></link> 
                </guided-if-menu-item-selected> 
            </guided-menu>  
        </menu> 
    </menus> 
 
    <breadcrumbs> 
  <breadcrumb> 
            <name><![CDATA[default]]></name> 
      <guided-breadcrumb gsname="default"> 
  <breadcrumb-item> 
    <link><![CDATA[<guided-breadcrumb-path gsname="goto">]]></link> 
    <value><![CDATA[<guided-breadcrumb-value />]]></value> 
                        <label><![CDATA[<guided-breadcrumb-label>]]></label> 
   </breadcrumb-item> 
         </guided-breadcrumb> 
   </breadcrumb> 
    </breadcrumbs> 
 
    <suggestions> 
        <auto-searched><guided-if-suggestion-autosearch>1<guided-else-suggestion-autosearch>0</guided-if-suggestion-autosearch></auto-searched> 
        <guided-if-suggestion-autosearch><orig-query><![CDATA[<guided-suggestion-original-query/>]]></orig-query></guided-if-suggestion-autosearch> 
        <suggestions-low-results><guided-if-suggestion-low-results>1<guided-else-suggestion-low-results>0</guided-if-suggestion-low-results></suggestions-low-results> 
        <guided-suggestions> 
     <suggestion-item> 
         <link><![CDATA[<guided-suggestion-path />]]></link> 
  <word><![CDATA[<guided-suggestion />]]></word> 
     </suggestion-item> 
 </guided-suggestions> 
    </suggestions> 
 
    <pagination> 
        <total-pages><![CDATA[<guided-page-total />]]></total-pages> 
        <pages> 
     <page position="first"><![CDATA[<guided-page-path gsname="first" />]]></page> 
     <page position="last"><![CDATA[<guided-page-path gsname="last" />]]></page> 
     <guided-if-page-prev><page position="prev"><![CDATA[<guided-page-path gsname="prev" />]]></page></guided-if-page-prev> 
     <guided-if-page-next><page position="next"><![CDATA[<guided-page-path gsname="next" />]]></page></guided-if-page-next> 
     <guided-if-page-viewall><page position="viewall"><![CDATA[<guided-page-path gsname="viewall" />]]></page></guided-if-page-viewall> 
     <guided-if-page-viewpages><page position="viewall"><![CDATA[<guided-page-path gsname="viewpages" />]]></page></guided-if-page-viewpages> 
 
     <guided-pages> 
                <guided-if-page-selected><page position="<guided-page-number />" selected="true"><![CDATA[<guided-page-path />]]></page> 
  <guided-else-page-selected><page position="<guided-page-number />"><![CDATA[<guided-page-path />]]></page> 
  </guided-if-page-selected> 
     </guided-pages> 
        </pages> 
    </pagination> 
 
    <facets>  
        <guided-facet gsname="leveli"> 
     <facet-item> 
         <facet-title><![CDATA[Department]]></facet-title> 
                <selected><guided-if-facet-selected>1<guided-else-facet-selected>0</guided-if-facet-selected></selected> 
                <guided-if-facet-selected><undo-link><![CDATA[<guided-facet-undo-path gsname="leveli">]]></undo-link></guided-if-facet-selected> 
  <guided-facet-values> 
      <facet-value> 
          <guided-if-facet-value-selected><selected><![CDATA[true]]></selected></guided-if-facet-value-selected> 
              <label><![CDATA[<guided-facet-value>]]></label> 
       <link><![CDATA[<guided-facet-value-path />]]></link> 
       <count><![CDATA[<guided-facet-count>]]></count> 
                        <guided-if-facet-value-selected><undolink><![CDATA[<guided-facet-value-undo-path />]]></undolink></guided-if-facet-value-selected> 
      </facet-value> 
  </guided-facet-values> 
      </facet-item> 
 </guided-facet> 
    </facets> 
 
    <results> 
        <result-set> 
            <name><![CDATA[default]]></name> 
            <guided-results gsname="default">   
         <result> 
                    <field name="index"><![CDATA[<guided-result-index />]]></field> 
      <field name="brand"><![CDATA[<guided-result-field gsname="brand" />]]></field> 
      <field name="price"><![CDATA[<guided-result-field gsname="price" />]]></field> 
      <field name="foundIn"><![CDATA[<guided-if-result-field gsname="leveli"><!--tmpl_var name='leveli'-->, </guided-if-result-field> 
            <guided-if-result-field gsname="levelii"><!--tmpl_var name='levelii'-->, </guided-if-result-field> 
          <guided-if-result-field gsname="leveliii"><!--tmpl_var name='leveliii'--></guided-if-result-field>]]></field> 
         </result>   
     </guided-results> 
        </result-set>   
    </results> 
 
    <guided-if-recent-searches> 
    <recent-searches> 
        <clear-link><guided-recent-searches-clear-path/></clear-link> 
        <guided-recent-searches> 
            <recent-search> 
                <link><guided-recent-searches-path></link> 
                <label><guided-recent-searches-value></label> 
            <recent-search> 
        </guided-recent-searches> 
    </recent-searches> 
    </guided-if-recent-searches> 
 
    <banners> 
        <guided-if-banner-set gsname="top"> 
            <banner> 
                <area><![CDATA[top]]></area> 
                <content><![CDATA[<guided-banner gsname="top">]]></content> 
            </banner> 
        </guided-if-banner-set> 
        <guided-if-banner-set gsname="bottom"> 
            <banner> 
                <area><![CDATA[bottom]]></area> 
                <content><![CDATA[<guided-banner gsname="bottom">]]></content> 
            </banner> 
        </guided-if-banner-set> 
    </banners> 
 
    <zones> 
        <zone> 
            <name><![CDATA[brand-facet]]></name> 
            <display><guided-if-zone gsname="brand-facet">1<guided-else-zone>0</guided-if-zone></display> 
        </zone> 
    </zones> 
 
    <search-form> 
        <include-tnt-mbox><guided-if-tnt-business-rules>1<guided-else-tnt-business-rules>0</guided-if-tnt-business-rules></include-tnt-mbox> 
        <autocomplete> 
            <enabled><guided-if-autocomplete>1<guided-else-autocomplete>0</guided-if-autocomplete></enabled> 
            <css><![CDATA[<guided-ac-css/>]]></css> 
            <form-content><![CDATA[<guided-ac-form-content/>]]></form-content> 
            <javascript><![CDATA[<guided-ac-javascript/>]]></javascript> 
        </autocomplete> 
    </search-form> 
 
</customer-results> 
```

