---
description: 'null'
seo-description: 'null'
seo-title: 搜索表单
solution: Target
title: 搜索表单
topic: Appendices,Site search and merchandising
uuid: 91153e3a-c437-47f3-8c2a-d9ac02965b8c
translation-type: tm+mt
source-git-commit: 55f48748f8c0a2f739dfbe30e8d42b73c8106b81

---


# 搜索表单{#search-forms}

## 在搜索表单中使用集合 {#reference_5A079AEEEFB84457892EF0870D0605C3}

集合可让客户搜索网站的特定区域。 根据您是实施下拉列表还是复选框列表，您可以让客户搜索单个集合或多个集合。

另请参 [阅关于集合](../c-about-settings-menu/c-about-searching-menu.md#concept_62E42ACE53D54EEE9273433B86259127)。

以下示例显示了四个不同的集合名称及其所覆盖网站的关联区域：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>集合名称 </p> </th> 
   <th colname="col2" class="entry"> <p> </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>产品 </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_7AE70789C0914EBFBCCC7695C6F53B9E"> 
      <li id="li_72525BAA34E2442D86152F2FD8CA83D5"> https://www.mycompany.com/products.htm </li> 
      <li id="li_5CA4152239124BDBB251E6C94B15D45B"> https://www.mycompany.com/publish/ </li> 
      <li id="li_6E266736B3494696A3AFD841C4AFEC57"> https://www.mycompany.com/search/ </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>客户 </p> </td> 
   <td colname="col2"> <p>https://www.mycompany.com/customers/ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>新闻 </p> </td> 
   <td colname="col2"> <p>https://www.mycompany.com/news/ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>关于Adobe </p> </td> 
   <td colname="col2"> <p>https://www.mycompany.com/company/ </p> </td> 
  </tr> 
 </tbody> 
</table>

通过下拉式搜索表单界面，用户可以选择一个集合，其外观如下所示：

![](assets/DropdownsearchformUI.png)

下拉搜索表单是使用以下HTML代码生成的：

```
<select name="sp_k"> 
<option value="">All of Adobe</option> 
<option value="Products">Products</option> 
<option value="Customers">Customers</option> 
<option value="News">News</option> 
<option value="About Adobe">About Adobe</option> 
</select>
```

或者，您也可以在搜索表单中使用一组复选框，以便访客可以选择多个集合：

![](assets/checkboxes.png)

复选框搜索表单将使用以下HTML代码生成：

```
<input type="checkbox" name="sp_k" value="">All of Adobe<br> 
<input type="checkbox" name="sp_k" value="Products">Products<br> 
<input type="checkbox" name="sp_k" value="Customers">Customers<br> 
<input type="checkbox" name="sp_k" value="News">News<br> 
<input type="checkbox" name="sp_k" value="About Adobe">About Adobe<br>
```

## Search results {#section_BBDD5B44E2B349BC88D937F44583D350}

搜索模板标 `<search-input-collections>` 签在搜索结果中生成集合列表框HTML，并自动选择在搜索中指定的集合。 如果要生成复选框，请使用标 `<search-input>` 记而不是标记， `<input>` 如下所示：

```
<search-input type="checkbox" name="sp_k" value="">All of Adobe<br> 
<search-input type="checkbox" name="sp_k" value="Products">Products<br> 
<search-input type="checkbox" name="sp_k" value="Customers">Customers<br> 
<search-input type="checkbox" name="sp_k" value="News">News<br> 
<search-input type="checkbox" name="sp_k" value="About Adobe">About Adobe<br>
```

如果 `<search-input>` 在搜索中指 `<input>` 定了集合，则标 `checked` 签将输出一个标签并包括该属性。

## 将框架与表单结合使用 {#reference_82CDDDA1E37042E4849EBF7EA05407C5}

您可以配置框架集以处理站点搜索／销售。

要进一步了解HTML框架和HTML框架集元素，请参阅以下URL:

[https://www.w3schools.com/html/html_frames.asp](https://www.w3schools.com/html/html_frames.asp)

如果站点使用帧，则可以为搜索结果链接指定目标帧。 默认目标为_self，它在当前框架或浏览器窗口中打开链接。 而是可以指定站点特定的或浏览器保留的目标:

* _top（浏览器保留）结果在当前浏览器窗口中打开并替换所有当前帧。
* _blank（浏览器保留）结果在新的浏览器窗口中打开。
* _parent（浏览器保留）结果在当前框架的父框架中打开。
* frame2（站点特定）结果在名为“frame2”的帧中打开。 您可以将任何框架的名称指定为值（例如，主框架或内容）。

如果您的站点不使用框架，则最好不要更改默认目标名称。

如果为网站创建自定义搜索结果模板，则可以使用标记的属性覆盖 `target` 指定的设 `<search-link>` 置。

配置框架集的过程如下：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>处理步骤 </p> </th> 
   <th colname="col02" class="entry"> <p>流程说明 </p> </th> 
   <th colname="col2" class="entry"> <p>链接 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col02"> <p>将表单添加到网页中的所需框架。 </p> </td> 
   <td colname="col2"> <p> <a href="#section_BAA8A502BB2243F8B5FF9783CDF2BFFD" type="section" format="dita" scope="local"> 将搜索表单代码添加到您的…… </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col02"> <p>为搜索结果页面设置目标框架。 </p> </td> 
   <td colname="col2"> <p> <a scope="local" href="#section_532CACB90888467093D95EACB64FDFA1" type="section" format="dita"> 为搜索结果页面设置目标框架 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col02"> <p>设置从搜索结果页面创建的链接的目标。 </p> </td> 
   <td colname="col2"> <p> <a scope="local" href="#section_523248C5AC424D878321C21A23A5CD66" type="section" format="dita"> 设置从搜索结果创建的链接的目标... </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col02"> <p>编辑导航框架页面，以防止对它们进行索引。 </p> </td> 
   <td colname="col2"> <p> <a scope="local" href="#section_C62E5F0EE1294D5EBD97E123E54433FC" type="section" format="dita"> 编辑导航框架页面以防止它们…… </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col02"> <p>测试搜索表单。 </p> </td> 
   <td colname="col2"> <p> <a scope="local" href="../c-appendices/c-searchforms.md#section_43D8D4A7BF524DC480DFE5442F6A2E3C" type="section" format="dita"> 测试搜索表单 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 将搜索表单代码添加到网页中的框架 {#section_BAA8A502BB2243F8B5FF9783CDF2BFFD}

1. 在产品菜单中，单击 **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**。

   HTML搜索表单代码的外观与以下内容类似：

   ```
   <!-- Adobe Target HTML for [your customer name] --> 
   <form method="get" action="https://search.atomz.com/search/"> 
   <input size=15 name="sp_q"><br> 
   <input type=submit value="Search"> 
   <input type=hidden name="sp_a" value="[your account number]"> 
   </form>
   ```

1. 在页面 [!DNL Standard Form Source] 上，选择并复制文本字段中显示的HTML搜索表单代码。
1. 将搜索表单代码粘贴到框架集中所需的框架中。

   在以下示例中，搜索表单代码被粘贴到导航框架中——屏幕左侧的窄小垂直框架。

   ![](assets/frames1.gif)

## 为搜索结果页面设置目标框架 {#section_532CACB90888467093D95EACB64FDFA1}

如果如上所示将搜索表单代码放入垂直导航框架中，则可以在较大的主框架中显示搜索结果。 在此示例中，您将主框架称为“body”，并将其设置为目标框架。

![](assets/frames2.gif)

1. 要为结果页指定目标框，请通过从以下代码更改搜索表单代码中的以下行，向表单添加目标和值：

   `<form method="get" action="https://search.atomz.com/search/">`

   至：

   `<form target="body" method="get" action="https://search.atomz.com/search/">`

   请确保在表单目标值周围加引号。

当客户对您的网站进行搜索时，搜索结果将显示在网页的“正文”框架中。

## 为从搜索结果页面创建的链接设置目标 {#section_523248C5AC424D878321C21A23A5CD66}

您可以通过直接编辑模板来设置目标框架。

如果搜索结果显示在“body”框架中，您可能也希望在“body”框架中打开链接。 因为这是同一帧(即默认设 `"_self"` 置的目标值)，所以您无需进行任何更改。

您还可以为结果链接设置目标框架。 以下是您可以执行的操作的几个示例：

* 为搜索结果及其链接指定不同的帧，以便当每个单击的结果在单独的帧中打开时，搜索结果在各自的帧中保持活动状态。
* 指定将搜索结果打开到新的空白窗口中，这样旧窗口将保持活动状态并保留其原始内容，同时保留搜索结果。

目标名称可以是在HTML中指定的框架的名称，也可以是以下几个HTML默认值之一：

* `target="_blank"` 在未命名的空白新窗口中打开链接。

* `target="_self"` 默认. 在搜索结果所在的同一窗口中打开链接。 在这种情况下，将显示原始搜索结果窗口。 使用此选项可覆盖全局分配的基本目标。

* `target="_parent"` 在链接页面的父框架集中打开链接。 如果文档没有父项，则此函数类似于默 `"_self"` 认值。

* `target="_top"` 在完整窗口中打开链接。 如果文档已位于顶部，则此函数类似于默 `"_self"` 认值。 使用此选项可打破任意深度的框架嵌套。

例如，要设置目标目标框架， `_blank` 您可以按照以下方式编辑模板：

1. 在产品菜单中，单击 **[!UICONTROL Design]** > **[!UICONTROL Templates]**。

1. 在页 [!DNL Staged Templates] 面的表中，单击目标目标目标框架的模板名称。
1. 找到标 `<search-link>` 记。 Your default `<search-link>` tag should look similar to the following:

   `<search-link><search-title length=100></search-link>`

1. 将帧目标添加到标 `<search-link>` 记。 在以上示例中，输入 `target="_blank"`。 请务必在目标值周围加下划线和引号。

   标记 `<search-link>` 现在显示为如下所示：

   `<search-link target="_blank"><search-title length=100></search-link>`

当站点访客选择搜索结果链接时，链接的页面现在会打开一个新的空白窗口。

## 编辑导航框架页面以防止它们被索引 {#section_C62E5F0EE1294D5EBD97E123E54433FC}

通常，您希望不要使用搜索结果为导航框架编制索引。 要实现此功能，可向这些页 `noindex` 面添加meta标记。

1. 打开导航框架的HTML页面源。
1. 在HTML的部分中添加 `<head>` 以下meta标签：

   `<meta name="robots" content="noindex">`

   例如：

   ```
   <html> 
   <head> 
   <title>This page is a frameset that I do not want indexed</title> 
   <meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1"> 
   <meta name="robots" content="noindex"> 
   </head>
   ```

## 测试搜索表单 {#section_43D8D4A7BF524DC480DFE5442F6A2E3C}

1. 转到您的网站并导航到表单。
1. 在搜索字段中，输入一些搜索词，然后单击 **[!UICONTROL Search]**。

   以下是事实：

   * 搜索结果页面显示在指定的目标框架中。
   * 搜索结果中的链接位于指定的目标框架中。
   * 不显示导航框架结果。
   如果您在测试搜索表单后遇到框架问题，请与客户支持联系。

## 范例高级搜索表单 {#reference_82E1051918744EBA88A01E9E6AE42C4A}

您可以编辑高级表单代码以满足您的设计和内容需求，或者添加或删除其他搜索参数。

您的主页是插入高级搜索表单的好地方，因为许多客户希望在那里找到搜索功能。 您还可以创建包含搜索表单和其他有用信息的HTML页面，然后链接到整个网站中的该页面。

如果为安全内容编制索引，则可以从安全搜索Web服务器提供搜索结果。 将搜索表单操作属性中的URL更改为：action=&quot;https://search.atomz.com/search/&quot;来执行此操作。

>[!NOTE]
>
>某些HTML编辑器在从其他应用程序粘贴HTML代码时遇到问题。 如果HTML代码以文本形式显示在网页上，则将搜索代码复制并粘贴到简单的文本编辑器中（如Windows上的记事本或Mac上的简单文本），然后再次从简单文本编辑器复制并粘贴到HTML编辑器中。

搜索参数用于高级搜索表单代码中，以创建单选按钮、复选框和列表框，客户可使用它们自定义单个搜索。 客户可以指定显示的搜索结果数，例如，日期范围，或者是否通过高级搜索表单上显示的选项显示包含搜索结果的摘要。

使用以下范例高级搜索表单，本主题的其余部分向您显示如何使用搜索参数创建表单上的每个选项。

![](assets/advancedsearchform.png)

您可以视图上述示例的整个高级搜索表单HTML代码。

请参 [阅高级搜索表单HTML代码](../c-appendices/c-searchforms.md#reference_9AAD4A46B68D4D48865508982CB86DB9)。

请参 [阅配置自动完成CSS](../c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96)。

请参 [阅将搜索表单的HTML代码复制到……](../c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

<table> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> <p>表单上的位置 </p> </th> 
   <th colname="col1" class="entry"> <p>参数 </p> </th> 
   <th colname="col3" class="entry"> <p>HTML代码 </p> </th> 
   <th colname="col4" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p>启用高级搜索表单选项（隐藏字段） </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_advanced </span> </p> </td> 
   <td colname="col3"> <p> <span class="syntax html codeph"> &lt;input type=hidden name="sp_advanced" value=1&gt; </span> </p> </td> 
   <td colname="col4"> <p>启用或禁用高级搜索选项。 例如，您可以在主页上放置一个标准搜索表单，其中包含指向包含高级表单的第二页的链接。 在这种情况下，您应将标准表单的副本放入 <span class="codeph"> &lt;search-if-not-advanced&gt;...&lt;/search-if-not-advanced&gt;模板标 </span> 记。 </p> <p>在显示搜索结果时，从标准表单执行搜索的客户会看到标准的搜索表单。 在高级搜索表单屏幕上，您将 <span class="codeph"> &lt;input type=hidden name="sp_advanced" value=1&gt;标记与其他高级表单选项 </span> 一起包含。 </p> <p>您还可以在&lt;search-if-advanced&gt;中包含高级搜索表单的副本……&lt;/search-if-advanced&gt;模板标记。 在显示搜索结果时，从高级搜索表单执行搜索的客户会看到高级搜索表单。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> 匹配任何、全部或短语 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_p </span> </p> <p> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--&nbsp;Allow&nbsp;"any,"&nbsp;"all,"&nbsp;or&nbsp;"phrase"&nbsp;--&gt; 
      &lt;input&nbsp;type=radio&nbsp;name="sp_p"&nbsp;value="any"&gt;Any&nbsp;word 
      &lt;input&nbsp;type=radio&nbsp;name="sp_p"&nbsp;value="all"&nbsp;checked&gt;All&nbsp;words 
      &lt;input&nbsp;type=radio&nbsp;name="sp_p"&nbsp;value="phrase"&gt;Exact&nbsp;phrase </code> </p> </td> 
   <td colname="col4"> <p>允许您的客户指定“任何单词”、“所有单词”或“精确短语”必须存在，文档才能匹配。 指定 <span class="codeph"> sp_p参 </span> 数后，客户无需在搜索查询中使用“+”或“-”，或同时使用两者。 </p> <p> 如果忽略 <span class="codeph"> sp_p参数，或 </span> 将其设置为“”或“any”，则客户仍可使用“+”和“-”说明符。 如果 <span class="codeph"> sp_p参 </span> 数设置为“all”或“phrase”，则将忽略指定的“+”和“-”。 </p> <p>您可以进一步了解在搜索中使用“+”和“-”。 </p> <p>请参阅<a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local">关于搜索</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> 类似声匹配 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_w </span> </p> <p>和 </p> <p> <span class="codeph"> sp_w_control </span> </p> <p> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--&nbsp;Checkbox&nbsp;enables&nbsp;sound-alike&nbsp;matching&nbsp;--&gt; 
      &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value=1&gt; 
      &lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="alike"&gt;&nbsp;Sound-alike&nbsp;matching </code> </p> </td> 
   <td colname="col4"> <p>允许客户启用或禁用类似声音匹配。 类似声匹配允许拼写错误的搜索查询匹配文档中“类似声音”的单词。 </p> <p>当 <span class="codeph"> sp_w_control参数设置 </span><span class="codeph"></span> 为1且sp_w参数设置为“alike”时，将选中生成的复选框，默认情况下启用类似声匹配。 </p> <p>如果 <span class="codeph"> sp_w参 </span> 数设置为“”，则不选中该复选框。 </p> <p>如果在最近的索引操作中未启用类似声音匹配，则无法进行类似声音匹配，并忽略 <span class="codeph"> sp_w </span> 参数。 要启用类似声音匹配，请在产品菜单中，单击“语 <span class="uicontrol"> 言学 </span> ”&gt;“单词和语言” <span class="uicontrol"> &gt;“类 </span> 似声音匹配” <span class="uicontrol"></span>。 </p> <p>您还可以通过以 <span class="codeph"> 下方式指 </span> 定 <span class="codeph"> 参数sp_w和sp_w_control </span> 参数： </p> <p> <code class="syntax html"> &lt;!--&nbsp;Checkbox&nbsp;disables&nbsp;sound-alike&nbsp;matching&nbsp;--&gt; 
      &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value=0&gt; 
      &lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="exact"&gt; 
      No&nbsp;sound-alike&nbsp;matching </code> </p> <p>在这种情况下，当 <span class="codeph"> sp_w_control参数设置为 </span> 0且 <span class="codeph"></span> sp_w参数设置为“exact”时，默认情况下将禁用类似声音匹配。 如果 <span class="codeph"> sp_w参 </span> 数设置为“”，则启用类似声音匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>日期范围匹配 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_d </span> </p> <p> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--Specifies&nbsp;type&nbsp;of&nbsp;date&nbsp;range&nbsp;searching&nbsp;to&nbsp;perform.--&gt; 
      &lt;input&nbsp;type=radio&nbsp;name="sp_d"&nbsp;value="custom"&nbsp;checked&gt; 
      &lt;input&nbsp;type=radio&nbsp;name="sp_d"&nbsp;value="specific"&gt; </code> </p> </td> 
   <td colname="col4"> <p>sp_d <span class="codeph"> 参数指定 </span> 要执行的自定义数据范围匹配或要执行的特定日期范围匹配。 </p> <p>在默认的高级搜索表单上，此选项显示为单选按钮组，其下拉列表为使用 <span class="codeph"> sp_date_range参数生成的“自定义”日期 </span> 范围。 它还包括一组“特定”开始和结束日期，这些日期包括 <span class="codeph"> sp_开始日、 </span>sp_开始月、sp_ <span class="codeph"> 开始月、sp_year年、sp_结束日、 </span>sp_结束日、sp_结束日、 <span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span> sp_结束月和sp_year参数。 </p> <p>“自定义”日期范围是要搜索的指定日期范围。 例如，“Anytime”、“Today”、“Inthing the last in year”等。 </p> <p>“特定”日期范围包括开始日期和结束日期。 例如，从“2009年9月8日至2011年10月18日”。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>日期范围匹配：自定义日期范围 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_date_range </span> </p> <p> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--Selection&nbsp;list&nbsp;for&nbsp;custom&nbsp;date&nbsp;range.--&gt; 
      &lt;select&nbsp;name="sp_date_range"&nbsp;size=1&gt; 
      &lt;option&nbsp;value=-1&nbsp;selected&gt;Anytime&lt;/option&gt; 
      &lt;option&nbsp;value=7&gt;Within&nbsp;the&nbsp;last&nbsp;week&lt;/option&gt; 
      &lt;option&nbsp;value=14&gt;Within&nbsp;the&nbsp;last&nbsp;2&nbsp;weeks&lt;/option&gt; 
      &lt;option&nbsp;value=30&gt;Within&nbsp;the&nbsp;last&nbsp;30&nbsp;days&lt;/option&gt; 
      &lt;option&nbsp;value=60&gt;Within&nbsp;the&nbsp;last&nbsp;60&nbsp;days&lt;/option&gt; 
      &lt;option&nbsp;value=90&gt;Within&nbsp;the&nbsp;last&nbsp;90&nbsp;days&lt;/option&gt; 
      &lt;option&nbsp;value=180&gt;Within&nbsp;the&nbsp;last&nbsp;180&nbsp;days&lt;/option&gt; 
      &lt;option&nbsp;value=365&gt;Within&nbsp;the&nbsp;last&nbsp;year&lt;/option&gt; 
      &lt;option&nbsp;value=730&gt;Within&nbsp;the&nbsp;last&nbsp;two&nbsp;years&lt;/option&gt; 
      &lt;/select&gt; </code> </p> </td> 
   <td colname="col4"> <p>sp_ <span class="codeph"> date_range参 </span> 数用于创建“自定义”日期范围。 例如，“Anytime”、“Today”、“Inthing the last year”等。 </p> <p>大于或等于零的值指定今天之前要搜索的天数。 例如，值0指定“今天”，值“1”指定“今天和昨天”，值“30”指定“最近30天内”，依此类推。 小于零的值指定自定义范围，如下所示： </p> <p> 
     <ul id="ul_E65DDE33883F441F9730F315E485AD98"> 
      <li id="li_83E9466AB9D7438A8544001F6B007186"> <p>-1 = "Anytime"，与指定无日期范围相同。 </p> </li> 
      <li id="li_38AB8D97179A47F9B860A96EA09119BB"> <p>-2 = “本周”，从周日到周六搜索。 </p> </li> 
      <li id="li_F4C3A8658428418A8A06FBAAB4733C68"> <p>-3 = "Last week"，从当周前一周的星期日到星期六进行搜索。 </p> </li> 
      <li id="li_DF2D0B043A4E4DE9BE8D82E69A76E793"> <p>-4 = "本月"，搜索日期为当月。 </p> </li> 
      <li id="li_76BC4C2CED574E2A81448158828BFF1B"> <p>-5 = "上个月"，搜索日期在当月前一个月内。 </p> </li> 
      <li id="li_17FF849384FB46D58AF6FF1D3BC408C8"> <p>-6 =“今年”，其搜索日期为当年。 </p> </li> 
      <li id="li_E2B8B4DFF3914BBDB86D0EB77F52B305"> <p>-7 = "Last year"，其搜索日期在当前年份的前一年。 </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>日期范围匹配：开始日期 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_开始_day、sp_开始_month、sp_开始_year </span> </p> <p> </p> </td> 
   <td colname="col3"> </td> 
   <td colname="col4"> <p>这三个数字值指定要搜索的特定日期范围的开始日期。 请务必指定所有三个值，因为忽略部分指定的日期。 </p> <p>只指定开始日期、结束日期或同时指定开始日期和结束日期是合法的。 如果仅指定开始日期，则搜索包括日期在开始日期或之后的匹配文档。 如果仅指定结束日期，则搜索将包括结束日期或结束日期之前的匹配文档。 如果同时指定了开始日期和结束日期，则搜索将包括从开始日期到结束日期的匹配文档。 </p> <p>所有日期均相对于格林威治标准时间进行搜索。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> 日期范围匹配：结束日期 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_end_day、sp_end_month、sp_end_year </span> </p> <p> </p> </td> 
   <td colname="col3"> </td> 
   <td colname="col4"> <p>这三个数字值指定要搜索的特定日期范围的结束日期。 请务必指定所有三个值，因为忽略部分指定的日期。 </p> <p>只指定开始日期、结束日期或开始日期和结束日期是合法的。 如果仅指定开始日期，则搜索包括日期在开始日期或之后的匹配文档。 如果仅指定结束日期，则搜索将包括结束日期或结束日期之前的匹配文档。 如果同时指定开始和结束日期，则搜索将包括从开始日期到结束日期的匹配文档。 </p> <p>所有日期均相对于格林威治标准时间进行搜索。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>在搜索字段内 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_x </span> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--&nbsp;List&nbsp;box&nbsp;selects&nbsp;the&nbsp;search&nbsp;field&nbsp;--&gt; 
      Within&nbsp;&lt;select&nbsp;name="sp_x"&nbsp;size=1&gt; 
      &lt;option&nbsp;value="any"&nbsp;selected&gt;Anywhere&lt;/option&gt; 
      &lt;option&nbsp;value="title"&gt;Title&lt;/option&gt; 
      &lt;option&nbsp;value="desc"&gt;Description&lt;/option&gt; 
      &lt;option&nbsp;value="keys"&gt;Keywords&lt;/option&gt; 
      &lt;option&nbsp;value="body"&gt;Body&lt;/option&gt; 
      &lt;option&nbsp;value="alt"&gt;Alternate&nbsp;text&lt;/option&gt; 
      &lt;option&nbsp;value="url"&gt;URL&lt;/option&gt; 
      &lt;option&nbsp;value="target"&gt;Target&lt;/option&gt; 
      &lt;option&nbsp;value="date"&gt;Date&lt;/option&gt;* 
      &lt;/select&gt; </code> </p> </td> 
   <td colname="col4"> <p>您的 <span class="codeph"> 客户可以在sp_x </span> 列表框中指定要在其中搜索查询字符串的字段。 </p> <p>客户可以选择所有字段、标题、文档说明、文档关键字、正文、替代文本、文档的URL、日期或目标关键字。 </p> <p>使用 <span class="codeph"></span> sp_x参数时，客户无需在搜索查询字符串中指定“title:”、“desc:”、“keys:”、“body:”、“alt:”、“url:”和“目标:”。 </p> <p>如果忽 <span class="codeph"> 略sp_x参 </span> 数，或将其设置为“”或“any”，则客户仍可使用字段说明符字符串。 如果 <span class="codeph"> sp_x参数设 </span> 置为特定字段，则忽略所有其他字段说明符字符串。 </p> <p>请参阅<a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local">关于搜索</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>显示结果计数 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_c </span> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--&nbsp;List&nbsp;box&nbsp;selects&nbsp;number&nbsp;of&nbsp;results&nbsp;to&nbsp;show&nbsp;per&nbsp;page&nbsp;--&gt; 
      Show&nbsp;&lt;select&nbsp;name="sp_c"&nbsp;size=1&gt; 
      &lt;option&nbsp;value=5&gt;5&lt;/option&gt; 
      &lt;option&nbsp;value=10&nbsp;selected&gt;10&lt;/option&gt; 
      &lt;option&nbsp;value=25&gt;25&lt;/option&gt; 
      &lt;option&nbsp;value=50&gt;50&lt;/option&gt; 
      &lt;option&nbsp;value=100&gt;100&lt;/option&gt; 
      &lt;/select&gt;&nbsp;results </code> </p> </td> 
   <td colname="col4"> <p>允许客户选择在每个搜索结果页面上显示的搜索结果数量。 </p> <p>表单中可以有任意数量或任意数量的选项。 确保“value=”值与显示的值匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>显示或隐藏摘要 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_m </span> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--&nbsp;Show&nbsp;or&nbsp;hide&nbsp;summaries&nbsp;in&nbsp;search&nbsp;results&nbsp;--&gt; 
      &lt;select&nbsp;name="sp_m"&nbsp;size=1&gt; 
      &lt;option&nbsp;value=1&nbsp;selected&gt;with&lt;/option&gt; 
      &lt;option&nbsp;value=0&gt;without&lt;/option&gt; 
      &lt;/select&gt;&nbsp;summaries&nbsp; </code> </p> </td> 
   <td colname="col4"> <p>允许客户选择是否显示每个匹配项的摘要文本。 </p> <p>如果要显示摘要，请将值设置为1。 如果要隐藏摘要，请将值设置为0。 您还可以将该参数与一组单选按钮一起使用，如下例所示： </p> <p> <code class="syntax html"> &lt;!--&nbsp;Show&nbsp;or&nbsp;hide&nbsp;summaries&nbsp;in&nbsp;search&nbsp;results&nbsp;--&gt; 
      &lt;input&nbsp;type=radio&nbsp;name="sp_m"&nbsp;value=1&nbsp;selected&gt;Show&nbsp;summaries 
      &lt;input&nbsp;type=radio&nbsp;name="sp_m"&nbsp;value=0&gt;Hide&nbsp;summaries </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>按结果排序 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_s </span> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--&nbsp;Sort&nbsp;results&nbsp;by&nbsp;relevance&nbsp;or&nbsp;by&nbsp;date&nbsp;--&gt; 
      Sort&nbsp;by&nbsp;&lt;select&nbsp;name="sp_s"&nbsp;size=1&gt; 
      &lt;option&nbsp;value=0&nbsp;selected&gt;relevance&lt;/option&gt; 
      &lt;option&nbsp;value=1&gt;date&lt;/option&gt; 
      &lt;/select&gt; </code> </p> </td> 
   <td colname="col4"> <p>允许客户选择结果是按相关性还是日期顺序列出。 </p> <p>当该值设置为1时，结果将从最近更改的文档列出到最近更改的文档。 当该值设置为0时，结果将从最相关和最不相关中列出。 您还可以将此参数与单选按钮一起使用，如下例所示： </p> <p> <code class="syntax html"> &lt;!--&nbsp;Sort&nbsp;results&nbsp;by&nbsp;relevance&nbsp;or&nbsp;by&nbsp;date&nbsp;--&gt; 
      &lt;input&nbsp;type=radio&nbsp;name="sp_s"&nbsp;value=0&nbsp;selected&gt;Sort&nbsp;by&nbsp;relevance 
      &lt;input&nbsp;type=radio&nbsp;name="sp_s"&nbsp;value=1&gt;Sort&nbsp;by&nbsp;date </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 高级搜索表单HTML代码 {#reference_9AAD4A46B68D4D48865508982CB86DB9}

用于生成高级搜索表单的HTML表单代码，该表单显示在示例高级搜索表单主题的顶部。

请参 [阅示例高级搜索表单](../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A)。

如果您使用此代码，请记住将 `sp_a` 的值替 `sp99999999` 换为实际的帐号。

要查找您的帐号，请在产品菜单上单击 **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Account Settings]**。

```
<form method="get" action="https://search.atomz.com/search/"> 
<table cellspacing=0 cellpadding=0 border=0> 
<tr><td colspan=4> 
<b>Search For:</b><br> 
<input size=35 name="sp_q"> 
<!-- The "Search" button --> 
<input type=submit value="Search"> 
<input type=hidden name="sp_a" value="sp99999999"> 
<input type=hidden name="sp_f" value="ISO-8859-1"> 
</td></tr> 
<input type=hidden name="sp_advanced" value=1> 
<!-- Allow "any," "all," or "phrase" --> 
<tr><td valign=top> 
<b>Match: </b> 
</td><td colspan=4> 
<input type=radio name="sp_p" value="any">Any word 
<input type=radio name="sp_p" value="all" checked>All words 
<input type=radio name="sp_p" value="phrase">Exact phrase<br> 
<!-- Checkbox enables sound-alike matching --> 
<input type=hidden name="sp_w_control" value=1> 
<input type=checkbox name="sp_w" value="alike" checked> 
Sound-alike matching 
</td></tr> 
<!-- Date range criteria --> 
<tr><td><b>Dated:</b></td><td colspan=4> 
<input type=radio name="sp_d" value="custom" checked> 
<select name="sp_date_range" size=1> 
<option value=-1 selected>Anytime</option> 
<option value=7>Within the last week</option> 
<option value=14>Within the last 2 weeks</option> 
<option value=30>Within the last 30 days</option> 
<option value=60>Within the last 60 days</option> 
<option value=90>Within the last 90 days</option> 
<option value=180>Within the last 180 days</option> 
<option value=365>Within the last year</option> 
<option value=730>Within the last two years</option> 
</select> 
</td></tr> 
<tr><td></td><td rowspan=2> 
<input type=radio name="sp_d" value=specific> 
</td><td align=right>From:</td><td> 
<select name="sp_start_month" size=1> 
<option value=0 selected></option> 
<option value=1>January</option> 
<option value=2>February</option> 
<option value=3>March</option> 
<option value=4>April</option> 
<option value=5>May</option> 
<option value=6>June</option> 
<option value=7>July</option> 
<option value=8>August</option> 
<option value=9>September</option> 
<option value=10>October</option> 
<option value=11>November</option> 
<option value=12>December</option> 
</select> 
<select name="sp_start_day" size=1> 
<option value=0 selected></option> 
<option value=1>1</option> 
<option value=2>2</option> 
<option value=3>3</option> 
<option value=4>4</option> 
<option value=5>5</option> 
<option value=6>6</option> 
<option value=7>7</option> 
<option value=8>8</option> 
<option value=9>9</option> 
<option value=10>10</option> 
<option value=11>11</option> 
<option value=12>12</option> 
<option value=13>13</option> 
<option value=14>14</option> 
<option value=15>15</option> 
<option value=16>16</option> 
<option value=17>17</option> 
<option value=18>18</option> 
<option value=19>19</option> 
<option value=20>20</option> 
<option value=21>21</option> 
<option value=22>22</option> 
<option value=23>23</option> 
<option value=24>24</option> 
<option value=25>25</option> 
<option value=26>26</option> 
<option value=27>27</option> 
<option value=28>28</option> 
<option value=29>29</option> 
<option value=30>30</option> 
<option value=31>31</option> 
</select> 
<!--comma-->, 
<input size=4 name="sp_start_year"> 
</td></tr> 
<tr><td></td> 
<td align=right>To:</td><td> 
<select name="sp_end_month" size=1> 
<option value=0 selected></option> 
<option value=1>January</option> 
<option value=2>February</option> 
<option value=3>March</option> 
<option value=4>April</option> 
<option value=5>May</option> 
<option value=6>June</option> 
<option value=7>July</option> 
<option value=8>August</option> 
<option value=9>September</option> 
<option value=10>October</option> 
<option value=11>November</option> 
<option value=12>December</option> 
</select> 
<select name="sp_end_day" size=1> 
<option value=0 selected></option> 
<option value=1>1</option> 
<option value=2>2</option> 
<option value=3>3</option> 
<option value=4>4</option> 
<option value=5>5</option> 
<option value=6>6</option> 
<option value=7>7</option> 
<option value=8>8</option> 
<option value=9>9</option> 
<option value=10>10</option> 
<option value=11>11</option> 
<option value=12>12</option> 
<option value=13>13</option> 
<option value=14>14</option> 
<option value=15>15</option> 
<option value=16>16</option> 
<option value=17>17</option> 
<option value=18>18</option> 
<option value=19>19</option> 
<option value=20>20</option> 
<option value=21>21</option> 
<option value=22>22</option> 
<option value=23>23</option> 
<option value=24>24</option> 
<option value=25>25</option> 
<option value=26>26</option> 
<option value=27>27</option> 
<option value=28>28</option> 
<option value=29>29</option> 
<option value=30>30</option> 
<option value=31>31</option> 
</select> 
<!--comma-->, 
<input size=4 name="sp_end_year"> 
</td></tr> 
<!-- List box selects the search field --> 
<tr><td valign=top> 
<b>Within: </b> 
</td><td colspan=4><select name="sp_x" size=1> 
<option value="any" selected>Anywhere</option> 
<option value="title">Title</option> 
<option value="desc">Description</option> 
<option value="keys">Keywords</option> 
<option value="body">Body</option> 
<option value="alt">Alternate text</option> 
<option value="url">URL</option> 
<option value="target">Target</option> 
</select> 
</td></tr> 
<!-- List box selects number of results to show per page --> 
<tr><td valign=top> 
<b>Show: </b> 
</td><td colspan=4><select name="sp_c" size=1> 
<option value=5>5</option> 
<option value=10 selected>10</option> 
<option value=25>25</option> 
<option value=50>50</option> 
<option value=100>100</option> 
</select> results  
<!-- Show or hide summaries in search results --> 
<select name="sp_m" size=1> 
<option value=1 selected>with</option> 
<option value=0>without</option> 
</select> summaries<br> 
</td></tr> 
<!-- Sort results by relevance or by date --> 
<tr><td valign=top> 
<b>Sort by: </b> 
</td><td colspan=4><select name="sp_s" size=1> 
<option value=0 selected>relevance</option> 
<option value=1>date</option> 
</select> 
</td></tr> 
</table> 
</form>
```

## 高级搜索表单模板代码 {#reference_D762C22E754E462DBEECD88D2C3FA579}

您可以向模板添加高级搜索表单HTML代码，这样，任何参数的默认选择都与之前的搜索相同。

换句话说，如果客户单击单选按钮， **[!UICONTROL Exact phrase]** 则您可以确保在显示搜索结果时，单选按钮在默认情况下处于选中状态。

通过从标准HTML标签中删除所有“已选中”或“已选定”说明符，然后替换以下HTML标签，即可实现此功能：

* `<input>`
* `<select>`
* `<option>`
* `</option>`
* `</select>`

具有以下相应的模板标记：

* `<search-input>`
* `<search-select>`
* `<search-option>`
* `</search-option>`
* `</search-select>`

为此，请使用以下代码作为搜索模 `<form>` 板上的标记。

```
<!-- Adobe Target results section.--> 
 
<!-- Show heading and logo graphic. --> 
<SEARCH-IF-RESULTS> 
<b>SEARCH RESULTS <SEARCH-LOWER> - <SEARCH-UPPER></b> 
of <SEARCH-TOTAL> total results for <b><SEARCH-QUERY></b><br> 
</SEARCH-IF-RESULTS> 
<SEARCH-IF-NOT-RESULTS> 
<b>SEARCH RESULTS</b> for <b><SEARCH-QUERY></b><br> 
</SEARCH-IF-NOT-RESULTS> 
<SEARCH-LOGO><br> 
 
<!-- Display Results. --> 
<SEARCH-RESULTS LENGTH=160> 
<p><b><SEARCH-LINK><SEARCH-TITLE LENGTH=160></SEARCH-LINK></b><br> 
<SEARCH-IF-SHOW-SUMMARIES> 
<SEARCH-IF-CONTEXT LENGTH=240><SEARCH-CONTEXT><br></SEARCH-IF-CONTEXT> 
<font size="-1"><SEARCH-URL LENGTH=60></font><br> 
</SEARCH-IF-SHOW-SUMMARIES> 
</SEARCH-RESULTS> 
 
<!-- If no results, show a message. --> 
<SEARCH-IF-NOT-RESULTS><p> 
Sorry, no matches were found containing <b><SEARCH-QUERY>.</b> 
</SEARCH-IF-NOT-RESULTS> 
<!-- Show By Relevance, By Date links, Show/Hide Summaries links. --> 
<SEARCH-IF-RESULTS><p> 
<SEARCH-IF-SORT-BY-DATE> 
<b><SEARCH-SORT-BY-SCORE COUNT=10>Sort By Relevance</SEARCH-SORT-BY-SCORE></b> 
</SEARCH-IF-SORT-BY-DATE> 
<SEARCH-IF-SORT-BY-SCORE> 
<b><SEARCH-SORT-BY-DATE COUNT=10>Sort By Date</SEARCH-SORT-BY-DATE></b> 
</SEARCH-IF-SORT-BY-SCORE> 
| <b> 
<SEARCH-IF-SHOW-SUMMARIES> 
<SEARCH-HIDE-SUMMARIES COUNT=20>Hide Summaries</SEARCH-HIDE-SUMMARIES> 
</SEARCH-IF-SHOW-SUMMARIES> 
<SEARCH-IF-HIDE-SUMMARIES> 
<SEARCH-SHOW-SUMMARIES COUNT=10>Show Summaries</SEARCH-SHOW-SUMMARIES> 
</SEARCH-IF-HIDE-SUMMARIES> 
</b><br> 
</SEARCH-IF-RESULTS> 
 
<!-- Display Prev & Next links. --> 
<SEARCH-IF-RESULTS> 
<SEARCH-IF-PREV-COUNT> 
<b><SEARCH-PREV>Prev <SEARCH-PREV-COUNT></SEARCH-PREV></b> 
<SEARCH-IF-NEXT-COUNT> | </SEARCH-IF-NEXT-COUNT> 
</SEARCH-IF-PREV-COUNT> 
<SEARCH-IF-NEXT-COUNT> 
<b><SEARCH-NEXT>Next <SEARCH-NEXT-COUNT></SEARCH-NEXT></b><br> 
</SEARCH-IF-NEXT-COUNT><p> 
</SEARCH-IF-RESULTS> 
 
<!-- Put up the next form. --> 
<form method="get" action="https://search.atomz.com/search/"> 
<SEARCH-IF-NOT-ADVANCED> 
<SEARCH-INPUT-ACCOUNT> 
<SEARCH-INPUT-GALLERY> 
<SEARCH-INPUT-QUERY SIZE=25> 
<SEARCH-INPUT type=hidden name=sp_p> 
<input type=submit value="New Search"> 
<SEARCH-IF-INPUT-COLLECTIONS> 
<br><SEARCH-INPUT-COLLECTIONS> 
</SEARCH-IF-INPUT-COLLECTIONS> 
</SEARCH-IF-NOT-ADVANCED> 
<SEARCH-IF-ADVANCED> 
<table cellspacing=0 cellpadding=0 border=0> 
<tr><td colspan=4> 
<b>Search For:</b><br> 
<SEARCH-INPUT-QUERY SIZE=35> 
 
<!-- The "Search" button --> 
<input type=submit value="New Search"> 
<SEARCH-INPUT-ACCOUNT> 
<SEARCH-INPUT-GALLERY> 
</td></tr> 
<SEARCH-IF-INPUT-COLLECTIONS> 
<!-- Collections --> 
<tr><td> 
<b>In: </b> 
</td><td colspan=4> 
<SEARCH-INPUT-COLLECTIONS> 
</td></tr> 
</SEARCH-IF-INPUT-COLLECTIONS> 
<input type=hidden name="sp_advanced" value=1> 
 
<!-- Allow "any," "all," or "phrase" --> 
<tr><td valign=top> 
<b>Match: </b> 
</td><td colspan=4> 
<SEARCH-INPUT type=radio name="sp_p" value="any">Any word 
<SEARCH-INPUT type=radio name="sp_p" value="all">All words 
<SEARCH-INPUT type=radio name="sp_p" value="phrase">Exact phrase<br> 
<!-- Checkbox enables sound-alike matching --> 
<input type=hidden name="sp_w_control" value=1> 
<SEARCH-INPUT type=checkbox name="sp_w" value="alike">Sound-alike matching 
</td></tr> 
 
<!-- Date range section --> 
<tr> 
<td><b>Dated:</b></td> 
<td colspan=3> 
<SEARCH-INPUT type=radio name="sp_d" value="custom"> 
<SEARCH-SELECT name="sp_date_range" size=1> 
<SEARCH-OPTION value=-1>Anytime</SEARCH-OPTION> 
<SEARCH-OPTION value=7>Within the last week</SEARCH-OPTION> 
<SEARCH-OPTION value=14>Within the last 2 weeks</SEARCH-OPTION> 
<SEARCH-OPTION value=30>Within the last 30 days</SEARCH-OPTION> 
<SEARCH-OPTION value=60>Within the last 60 days</SEARCH-OPTION> 
<SEARCH-OPTION value=90>Within the last 90 days</SEARCH-OPTION> 
<SEARCH-OPTION value=180>Within the last 180 days</SEARCH-OPTION> 
<SEARCH-OPTION value=365>Within the last year</SEARCH-OPTION> 
<SEARCH-OPTION value=730>Within the last two years</SEARCH-OPTION> 
</SEARCH-SELECT> 
</td></tr> 
<tr><td></td><td rowspan=2> 
<SEARCH-INPUT type=radio name="sp_d" value=specific></td> 
<td align=right>From:</td><td> 
<SEARCH-SELECT name="sp_start_month" size=1> 
<SEARCH-OPTION value=0></SEARCH-OPTION> 
<SEARCH-OPTION value=1>January</SEARCH-OPTION> 
<SEARCH-OPTION value=2>February</SEARCH-OPTION> 
<SEARCH-OPTION value=3>March</SEARCH-OPTION> 
<SEARCH-OPTION value=4>April</SEARCH-OPTION> 
<SEARCH-OPTION value=5>May</SEARCH-OPTION> 
<SEARCH-OPTION value=6>June</SEARCH-OPTION> 
<SEARCH-OPTION value=7>July</SEARCH-OPTION> 
<SEARCH-OPTION value=8>August</SEARCH-OPTION> 
<SEARCH-OPTION value=9>September</SEARCH-OPTION> 
<SEARCH-OPTION value=10>October</SEARCH-OPTION> 
<SEARCH-OPTION value=11>November</SEARCH-OPTION> 
<SEARCH-OPTION value=12>December</SEARCH-OPTION> 
</SEARCH-SELECT> 
<SEARCH-SELECT name="sp_start_day" size=1> 
<SEARCH-OPTION value=0></SEARCH-OPTION> 
<SEARCH-OPTION value=1>1</SEARCH-OPTION> 
<SEARCH-OPTION value=2>2</SEARCH-OPTION> 
<SEARCH-OPTION value=3>3</SEARCH-OPTION> 
<SEARCH-OPTION value=4>4</SEARCH-OPTION> 
<SEARCH-OPTION value=5>5</SEARCH-OPTION> 
<SEARCH-OPTION value=6>6</SEARCH-OPTION> 
<SEARCH-OPTION value=7>7</SEARCH-OPTION> 
<SEARCH-OPTION value=8>8</SEARCH-OPTION> 
<SEARCH-OPTION value=9>9</SEARCH-OPTION> 
<SEARCH-OPTION value=10>10</SEARCH-OPTION> 
<SEARCH-OPTION value=11>11</SEARCH-OPTION> 
<SEARCH-OPTION value=12>12</SEARCH-OPTION> 
<SEARCH-OPTION value=13>13</SEARCH-OPTION> 
<SEARCH-OPTION value=14>14</SEARCH-OPTION> 
<SEARCH-OPTION value=15>15</SEARCH-OPTION> 
<SEARCH-OPTION value=16>16</SEARCH-OPTION> 
<SEARCH-OPTION value=17>17</SEARCH-OPTION> 
<SEARCH-OPTION value=18>18</SEARCH-OPTION> 
<SEARCH-OPTION value=19>19</SEARCH-OPTION> 
<SEARCH-OPTION value=20>20</SEARCH-OPTION> 
<SEARCH-OPTION value=21>21</SEARCH-OPTION> 
<SEARCH-OPTION value=22>22</SEARCH-OPTION> 
<SEARCH-OPTION value=23>23</SEARCH-OPTION> 
<SEARCH-OPTION value=24>24</SEARCH-OPTION> 
<SEARCH-OPTION value=25>25</SEARCH-OPTION> 
<SEARCH-OPTION value=26>26</SEARCH-OPTION> 
<SEARCH-OPTION value=27>27</SEARCH-OPTION> 
<SEARCH-OPTION value=28>28</SEARCH-OPTION> 
<SEARCH-OPTION value=29>29</SEARCH-OPTION> 
<SEARCH-OPTION value=30>30</SEARCH-OPTION> 
<SEARCH-OPTION value=31>31</SEARCH-OPTION> 
</SEARCH-SELECT><!--comma-->, 
<SEARCH-INPUT size=4 name="sp_start_year"> 
</td></tr> 
<tr><td></td> 
<td align=right>To:</td><td> 
<SEARCH-SELECT name="sp_end_month" size=1> 
<SEARCH-OPTION value=0></SEARCH-OPTION> 
<SEARCH-OPTION value=1>January</SEARCH-OPTION> 
<SEARCH-OPTION value=2>February</SEARCH-OPTION> 
<SEARCH-OPTION value=3>March</SEARCH-OPTION> 
<SEARCH-OPTION value=4>April</SEARCH-OPTION> 
<SEARCH-OPTION value=5>May</SEARCH-OPTION> 
<SEARCH-OPTION value=6>June</SEARCH-OPTION> 
<SEARCH-OPTION value=7>July</SEARCH-OPTION> 
<SEARCH-OPTION value=8>August</SEARCH-OPTION> 
<SEARCH-OPTION value=9>September</SEARCH-OPTION> 
<SEARCH-OPTION value=10>October</SEARCH-OPTION> 
<SEARCH-OPTION value=11>November</SEARCH-OPTION> 
<SEARCH-OPTION value=12>December</SEARCH-OPTION> 
</SEARCH-SELECT> 
<SEARCH-SELECT name="sp_end_day" size=1> 
<SEARCH-OPTION value=0></SEARCH-OPTION> 
<SEARCH-OPTION value=1>1</SEARCH-OPTION> 
<SEARCH-OPTION value=2>2</SEARCH-OPTION> 
<SEARCH-OPTION value=3>3</SEARCH-OPTION> 
<SEARCH-OPTION value=4>4</SEARCH-OPTION> 
<SEARCH-OPTION value=5>5</SEARCH-OPTION> 
<SEARCH-OPTION value=6>6</SEARCH-OPTION> 
<SEARCH-OPTION value=7>7</SEARCH-OPTION> 
<SEARCH-OPTION value=8>8</SEARCH-OPTION> 
<SEARCH-OPTION value=9>9</SEARCH-OPTION> 
<SEARCH-OPTION value=10>10</SEARCH-OPTION> 
<SEARCH-OPTION value=11>11</SEARCH-OPTION> 
<SEARCH-OPTION value=12>12</SEARCH-OPTION> 
<SEARCH-OPTION value=13>13</SEARCH-OPTION> 
<SEARCH-OPTION value=14>14</SEARCH-OPTION> 
<SEARCH-OPTION value=15>15</SEARCH-OPTION> 
<SEARCH-OPTION value=16>16</SEARCH-OPTION> 
<SEARCH-OPTION value=17>17</SEARCH-OPTION> 
<SEARCH-OPTION value=18>18</SEARCH-OPTION> 
<SEARCH-OPTION value=19>19</SEARCH-OPTION> 
<SEARCH-OPTION value=20>20</SEARCH-OPTION> 
<SEARCH-OPTION value=21>21</SEARCH-OPTION> 
<SEARCH-OPTION value=22>22</SEARCH-OPTION> 
<SEARCH-OPTION value=23>23</SEARCH-OPTION> 
<SEARCH-OPTION value=24>24</SEARCH-OPTION> 
<SEARCH-OPTION value=25>25</SEARCH-OPTION> 
<SEARCH-OPTION value=26>26</SEARCH-OPTION> 
<SEARCH-OPTION value=27>27</SEARCH-OPTION> 
<SEARCH-OPTION value=28>28</SEARCH-OPTION> 
<SEARCH-OPTION value=29>29</SEARCH-OPTION> 
<SEARCH-OPTION value=30>30</SEARCH-OPTION> 
<SEARCH-OPTION value=31>31</SEARCH-OPTION> 
</SEARCH-SELECT><!--comma-->, 
<SEARCH-INPUT size=4 name="sp_end_year"> 
</td></tr> 
<!-- List box selects the search field --> 
<tr><td valign=top> 
<b>Within: </b> 
</td><td colspan=4><SEARCH-SELECT name="sp_x" size=1> 
<SEARCH-OPTION value="any">Anywhere</SEARCH-OPTION> 
<SEARCH-OPTION value="title">Title</SEARCH-OPTION> 
<SEARCH-OPTION value="desc">Description</SEARCH-OPTION> 
<SEARCH-OPTION value="keys">Keywords</SEARCH-OPTION> 
<SEARCH-OPTION value="body">Body</SEARCH-OPTION> 
<SEARCH-OPTION value="alt">Alternate text</SEARCH-OPTION> 
<SEARCH-OPTION value="url">URL</SEARCH-OPTION> 
<SEARCH-OPTION value="target">Target</SEARCH-OPTION> 
</SEARCH-SELECT></td></tr> 
<!-- List box selects number of results to show per page --> 
<tr><td valign=top> 
<b>Show:</b> 
</td><td colspan=4><SEARCH-SELECT name="sp_c" size=1> 
<SEARCH-OPTION value=5>5</SEARCH-OPTION> 
<SEARCH-OPTION value=10>10</SEARCH-OPTION> 
<SEARCH-OPTION value=25>25</SEARCH-OPTION> 
<SEARCH-OPTION value=50>50</SEARCH-OPTION> 
<SEARCH-OPTION value=100>100</SEARCH-OPTION> 
</SEARCH-SELECT> results  
<!-- Show or hide summaries in search results --> 
<SEARCH-SELECT name="sp_m" size=1> 
<SEARCH-OPTION value=1>with</SEARCH-OPTION> 
<SEARCH-OPTION value=0>without</SEARCH-OPTION> 
</SEARCH-SELECT> summaries<br></td></tr> 
<!-- Sort results by relevance or by date --> 
<tr><td valign=top> 
<b>Sort by: </b> 
</td><td colspan=4><SEARCH-SELECT name="sp_s" size=1> 
<SEARCH-OPTION value=0>relevance</SEARCH-OPTION> 
<SEARCH-OPTION value=1>date</SEARCH-OPTION> 
</SEARCH-SELECT></td></tr> 
</table> 
</SEARCH-IF-ADVANCED> 
</form>
```

