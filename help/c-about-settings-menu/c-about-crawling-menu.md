---
description: 使用搜索菜单设置日期和URL蒙版、密码、内容类型、连接、表单定义和URL入口点。
seo-description: 使用搜索菜单设置日期和URL蒙版、密码、内容类型、连接、表单定义和URL入口点。
seo-title: 关于爬网菜单
solution: Target
subtopic: Crawling
title: 关于爬网菜单
topic: Settings,Site search and merchandising
uuid: a58c03bf-90f7-4b5b-91ff-988b95c246b0
translation-type: tm+mt
source-git-commit: e080a61e24a3809beff7c212ff3d088b2a8ad3b6
workflow-type: tm+mt
source-wordcount: '11115'
ht-degree: 1%

---


# 关于爬网菜单{#about-the-crawling-menu}

使用搜索菜单设置日期和URL蒙版、密码、内容类型、连接、表单定义和URL入口点。

## 关于URL入口点 {#concept_5D857E3B5C124E85BC0B5AE77A509573}

大多数网站都有一个客户最初访问的主要入口点或主页。 此主入口点是搜索自动机开始索引搜索的URL地址。 但是，如果您的网站有多个域或子域，或者您的站点的某些部分没有从主入口点链接，则可以使用URL入口点添加更多入口点。

将索引每个指定URL入口点下的所有网站页面。 您可以将URL入口点与蒙版组合，以准确控制要索引的网站的哪些部分。 在客户看到URL入口点设置的效果之前，必须重新构建网站索引。

主要入口点通常是要索引和搜索的网站的URL。 您可以在帐户设置中配置此主入口点。

请参 [阅配置帐户设置](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

指定主URL入口点后，可以选择指定要按顺序爬网的其他入口点。 通常，您会为未从主入口点下的页面链接的网页指定其他入口点。 如以下示例所示，当您的网站跨越多个域时指定其他入口点：

`https://www.domain.com/`

`https://www.domain.com/not_linked/but_search_me_too/`

`https://more.domain.com/`

您可以在下表中使用一个或多个以空格分隔的关键字限定每个入口点。 这些关键字影响页面的索引方式。

**重要说明**: 请确保将给定关键字与入口点分开，并用空格相隔； 逗号不是有效的分隔符。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>关键词 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>noindex </p> </td> 
   <td colname="col2"> <p> 如果不想在入口点页面上为文本编制索引，但想要遵循该页面的链接，请添加 
     <userinput>
       noindex 
     </userinput> 进入点之后。 </p> <p>如以下示例所示，将关键字与入口点分隔为空格： </p> <p> <code> https://www.my-additional-domain.com/more_pages/main.html&amp;nbsp;noindex </code> </p> <p>此关键字等效于具有 
     <userinput>
       content="noindex" 
     </userinput>) 
     <userinput>
       &lt;head&gt; 
     </userinput>... 
     <userinput>
       &lt;/head&gt; 
     </userinput> 入口点页面的标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofoly </p> </td> 
   <td colname="col2"> <p> 如果要为入口点页面中的文本编制索引，但不希望跟踪该页面的任何链接，请添加 
     <userinput>
       nofoly 
     </userinput> 进入点之后。 </p> <p>如以下示例所示，将关键字与入口点分隔为空格： </p> <p> <code> https://www.domain.com/not_linked/directory_listing&amp;nbsp;nofollow </code> </p> <p>此关键字等效于具有 
     <userinput>
       content="nofollow" 
     </userinput> 在 
     <userinput>
       &lt;head&gt; 
     </userinput>... 
     <userinput>
       &lt;/head&gt; 
     </userinput> 入口点页面的标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>表单 </p> </td> 
   <td colname="col2"> <p> 当入口点为登录页面时， 
     <userinput>
       表单 
     </userinput> 搜索自动机可以提交登录表单，并在搜索网站之前接收相应的cookie。 当使用“form”关键字时，入口点页面不进行索引，搜索自动机不会将入口点页面标记为已爬网。 使用 
     <userinput>
       nofoly 
     </userinput> 如果您不希望搜索机器人跟踪页面链接。 </p> </td> 
  </tr> 
 </tbody> 
</table>

另请参阅 [关于内容类型](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07)。

另请参阅 [关于索引连接器](../c-about-settings-menu/c-about-crawling-menu.md#concept_CA6921E2FBF641F9B4F60C92B32AFA84)。

## 添加要索引的多个URL入口点 {#task_2338A47387D74CFDAC4D4EF4A367ED45}

如果您的网站有多个域或子域，并且您希望对它们进行爬网，则可以使用URL入口点添加更多URL。

要设置网站的主URL入口点，请使用“帐户设置”。

请参 [阅配置帐户设置](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

**添加要编制索引的多个URL入口点**

1. 在产品菜单上，单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**。
1. 在页 [!DNL URL Entrypoints] 面的字段中， [!DNL Entrypoints] 每行输入一个URL地址。
1. （可选）在下 **[!UICONTROL Add Index Connector Configurations]** 拉列表中，选择要添加为索引入口点的索引连接器。

   下拉列表仅在您之前添加了一个或多个索引连接器定义时才可用。

   ![](assets/url_entrypoints_index_connector.png)

   请参 [阅添加索引连接器定义](../c-about-settings-menu/c-about-crawling-menu.md#task_96779B651A654E1F871F55D6DBBC8886)。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列任一操作：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于URL蒙版 {#concept_8039DFC53FF3410AA494D602F71BA164}

URL蒙版是一种模式，它们决定您的网站中哪个文档搜索自动机索引或不是索引。

请确保重新构建站点索引，以便您的客户能够看到URL蒙版的结果。

请参 [阅配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

以下是两种可以使用的URL蒙版：

* 包括URL蒙版
* 排除URL蒙版

包括URL蒙版，告知搜索自动机为与蒙版模式匹配的任何文档编制索引。

排除URL蒙版会通知搜索自动机为匹配文档建立索引。

当搜索机器人从链接穿行到网站的链接时，它会遇到URL并查找与这些URL匹配的蒙版。 第一个匹配项确定是将该URL包含在索引中还是从索引中排除。 如果没有与遇到的URL匹配的遮罩，则该URL将从索引中丢弃。

将自动生成入口点URL的URL蒙版。 此行为可确保您网站上遇到的所有文档都已建立索引。 它还可以方便地删除“离开”您网站的链接。 例如，如果索引页面链接到https://www.yahoo.com，则搜索自动机不会对该URL进行索引，因为它与入口点URL自动生成的包含蒙版不匹配。

您指定的每个URL掩码都必须位于单独的行上。

遮罩可以指定以下任一项：

* 完整路径 `https://www.mydomain.com/products.html`。
* 部分路径(如中所示 `https://www.mydomain.com/products`)。
* 使用通配符的URL，如 `https://www.mydomain.com/*.html`中。
* 常规表达式（适用于高级用户）。

   要使遮罩成为常规表达式，请在遮罩类 `regexp` 型（或）和URL遮 `exclude` 罩之 `include`间插入关键字。

以下是一个简单的排除URL掩码示例：

```
exclude https://www.mydomain.com/photos
```

由于此示例是排除URL掩码，因此不会为与该模式匹配的任何文档编制索引。 该模式与遇到的任何项目（文件和文件夹）匹 `https://www.mydomain.com/photos.html` 配， `https://www.mydomain.com/photos/index.html`因此和（两者均与排除URL匹配）不进行索引。 要仅与文件夹中的文 `/photos/` 件匹配，URL掩码必须包含尾随斜杠，如下例所示：

```
exclude https://www.mydomain.com/photos/
```

以下排除遮罩示例使用通配符。 它告诉搜索自动机忽略扩展名为“.pdf”的文件。 搜索自动机不会将这些文件添加到索引中。

```
exclude *.pdf
```

简单的包含URL掩码如下：

```
include https://www.mydomain.com/news/
```

只有通过URL入口点中的一系列链接链接链接的文档，或者本身用作URL入口点的链接，才会建立索引。 仅将文档的URL列为包含URL掩码不会为未链接的文档编制索引。 要向索引中添加未链接的文档，可使用URL入口点功能。

请参 [阅关于URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

包括蒙版和排除蒙版可以协同工作。 您可以通过创建排除URL掩码并包含一个或多个带有包含URL掩码的被排除页面，将网站的很大一部分排除在索引之外。 例如，假定您的入口点URL如下：

```
https://www.mydomain.com/photos/
```

搜索自动机对下面的所有页面进行爬 `/photos/summer/`行 `/photos/spring/` 和索引 `/photos/fall/` (假定文件夹中的每个目录中至少有一个页面的链接 `photos` )。 出现此行为是因为链接路径使搜索自动机能够在、 `/summer/`和 `/spring/`、文 `/fall/`件夹中查找文档，并且文件夹URL与入口点URL自动生成的包含掩码匹配。

您可以选择排除文件夹中具有排 `/fall/` 除URL蒙版的所有页面，如下例所示：

```
exclude https://www.mydomain.com/photos/fall/
```

或者，有选择地仅将 `/photos/fall/redleaves4.html` 以下URL掩码包含为索引的一部分：

```
include https://www.mydomain.com/photos/fall/redleaves4.html
```

要使上述两个蒙版示例按预期工作，首先列出包括蒙版，如下所示：

```
include https://www.mydomain.com/photos/fall/redleaves4.html 
exclude https://www.mydomain.com/photos/fall/
```

由于搜索机器人按照它们的列出顺序遵循方向，因此搜索机器人首先 `/photos/fall/redleaves4.html`包括，然后排除文件夹中的其余文 `/fall` 件。

如果指令的指定方式与下面相反：

```
exclude https://www.mydomain.com/photos/fall/ 
include https://www.mydomain.com/photos/fall/redleaves4.html
```

即 `/photos/fall/redleaves4.html` 使蒙版指定包含该蒙版，也不会包含该蒙版。

首先显示的URL掩码始终优先于稍后在掩码设置中显示的URL掩码。 此外，如果搜索自动机遇到与包含URL蒙版和排除URL蒙版匹配的页面，则首先列出的蒙版始终优先。

请参 [阅配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

## 关于将关键字与URL蒙版一起使用 {#section_7609A7A6D79B482ABCA8900886541AAB}

您可以使用一个或多个空格分隔的关键字限定每个包含蒙版，这些关键字会影响匹配页面的索引方式。

逗号不能作为遮罩和关键字之间的分隔符； 只能使用空格。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>关键词 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>noindex </p> </td> 
   <td colname="col2"> <p> 如果不想为与URL掩码匹配的页面上的文本编制索引，但想要遵循匹配的页面链接，请添加 
     <userinput>
       noindex 
     </userinput> 包含URL掩码之后。 请确保将关键字与遮罩分隔，并且空格如以下示例所示： </p> <p> <code> include&amp;nbsp;*.swf&amp;nbsp;noindex </code> </p> <p>上面的示例指定搜索机器人使用 
     <userinput>
       .swf 
     </userinput> 扩展名，但禁用对包含在这些文件中的所有文本编制索引。 </p> <p>The 
     <userinput>
       noindex 
     </userinput> 关键字等效于具有 
     <userinput>
       content="noindex" 
     </userinput> 在 
     <userinput>
       &lt;head&gt;...&lt;/head&gt; 
     </userinput> 匹配页面的标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofoly </p> </td> 
   <td colname="col2"> <p> 如果要为与URL掩码匹配的页面上的文本编制索引，但不想遵循匹配页面的链接，请添加 
     <userinput>
       nofoly 
     </userinput> 包含URL掩码之后。 请确保将关键字与遮罩分隔，并且空格如以下示例所示： </p> <p> <code> include&amp;nbsp;https://www.mydomain.com/photos&amp;nbsp;nofollow </code> </p> <p>The 
     <userinput>
       nofoly 
     </userinput> 关键字等效于具有 
     <userinput>
       content="nofollow" 
     </userinput> 在 
     <userinput>
       &lt;head&gt;...&lt;/head&gt; 
     </userinput> 匹配页面的标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>regexp </p> </td> 
   <td colname="col2"> <p>用于包括和排除蒙版。 </p> <p>前面带有任何URL掩码 
     <userinput>
       regexp 
     </userinput> 被视为常规表达式。 如果搜索自动机遇到与排除常规文档URL掩码匹配的文档，则不对这些表达式编制索引。 如果搜索自动机遇到与包含常规文档URL掩码匹配的文档，则对这些表达式进行索引。 例如，假定您具有以下URL掩码： </p> <p> <code> exclude&amp;nbsp;regexp&amp;nbsp;^.*/products/.*\.html$ </code> </p> <p>搜索自动机排除匹配文件，如 
     <userinput>
       https://www.mydomain.com/products/page1.html 
     </userinput> </p> <p>如果您具有以下排除常规表达式URL掩码： </p> <p> <code> exclude&amp;nbsp;regexp&amp;nbsp;^.*\?..*$ </code> </p> <p>搜索自动机不包含任何包含CGI参数的URL，如 
     <userinput>
       https://www.mydomain.com/cgi/prog/?arg1=val1&amp;arg2=val2 
     </userinput>. </p> <p>如果您具有以下各项，则包括常规表达式URL掩码： </p> <p> <code> include&amp;nbsp;regexp&amp;nbsp;^.*\.swf$&amp;nbsp;noindex </code> </p> <p>搜索自动机会跟踪扩展名为“.swf”的文件中的所有链接。 The 
     <userinput>
       noindex 
     </userinput> 关键字还指定不索引匹配文件的文本。 </p> <p>请参阅 <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> 常规表达式 </a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 添加URL蒙版以索引网站的各个部分或不为其索引 {#task_E1AFC17C746048B8843013D979E082C1}

您可以使用 [!DNL URL Masks] 定义要或不要对网站的哪些部分进行爬网和索引。

使用“测试URL蒙版”字段测试索引后是否包含文档。

请确保重新构建站点索引，以便您的客户能够看到URL蒙版的结果。

请参 [阅配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**添加URL蒙版以索引网站的各个部分或不为其索引**

1. 在产品菜单上，单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**。
1. （可选）在页 [!DNL URL Masks] 面的字 **[!UICONTROL Test URL Masks]** 段中，输入网站中的测试URL掩码，然后单击 **[!UICONTROL Test]**。
1. 在字 [!DNL URL Masks] 段中，键 `include` 入（添加要进行爬网和索引的网站）或键入( `exclude` 阻止网站进行爬网和索引)，后跟URL掩码地址。

   每行输入一个URL掩码地址。 示例：

   ```
   include https://www.mycompany.com/summer 
   include https://www.mycompany.com/spring 
   exclude regexp .*\.xml 
   exclude https://www.mycompany.com/fall
   ```

1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列任一操作：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于日期蒙版 {#concept_F4F1F58A646F4A86B8650EC46FDCEF66}

您可以使用日期蒙版根据文件的年龄，在搜索结果中包含或排除文件。

请确保重新构建站点索引，以便您的客户能够看到URL蒙版的结果。

请参 [阅配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

以下是两种日期蒙版，您可以使用它们：

* 包括日期蒙版（“include-days”和“include-date”）

   包括日期掩码索引文件，它们在指定日期或指定日期之前进行日期设置。
* 排除日期掩码（“exclude-days”和“exclude-date”）

   排除日期蒙版索引文件，它们在指定日期或指定日期之前进行日期标记。

默认情况下，文件日期由元标记信息确定。 如果找不到Meta标记，则根据在搜索机器人下载文件时从服务器接收的HTTP头确定文件的日期。

您指定的每个日期蒙版必须位于单独的行上。

遮罩可以指定以下任一项：

* 完整路径，如 `https://www.mydomain.com/products.html`
* 部分路径，如 `https://www.mydomain.com/products`
* 使用通配符的URL `https://www.mydomain.com/*.html`
* 一个普通表达式。 要使蒙版成为常规表达式，请在URL前 `regexp` 插入关键字。

包括和排除日期蒙版都可以通过以下两种方式之一指定日期。 仅当在指定日期或之前创建了匹配的文件时，才应用蒙版：

1. 几天。 例如，假定日期掩码如下：

   ```
   exclude-days 30 https://www.mydomain.com/docs/archive/)
   ```

   将返回指定天数。 如果文件在到达日期的当天或之前过期，则应用掩码。

1. 使用YYYY-MM-DD格式的实际日期。 例如，假定日期掩码如下：

   ```
   include-date 2011-02-15 https://www.mydomain.com/docs/archive/)
   ```

   如果匹配文档的日期在指定日期或之前，则应用日期掩码。

以下是一个简单的排除日期蒙版示例：

```
exclude-days 90 https://www.mydomain.com/docs/archive
```

由于这是排除日期掩码，因此与该模式匹配的任何文件都不会编制索引，并且旧版本或旧版本都为90天。 排除文档时，不会索引任何文本，也不会跟踪该文件中的链接。 文件会被有效忽略。 在此示例中，文件和文件夹可能与指定的URL模式匹配。 请注意， `https://www.mydomain.com/docs/archive.html` 与模 `https://www.mydomain.com/docs/archive/index.html` 式匹配，如果90天或90天以上，则不索引。 要仅与文件夹中的文 `/docs/archive/` 件匹配，日期掩码必须包含尾随斜杠，如下所示：

```
exclude-days 90 https://www.mydomain.com/docs/archive/
```

日期蒙版还可与通配符一起使用。 以下排除蒙版告知搜索自动机忽略扩展名为“.pdf”、日期在2011-02-15年或之前的文件。 搜索自动机不会向索引中添加任何匹配的文件。

```
exclude-date 2011-02-15 *.pdf
```

包含日期蒙版的外观类似，只向索引添加匹配的文件。 以下包括日期掩码示例告诉搜索机器人从网站区域中任何已过期或已过期零天的文件 `/docs/archive/manual/` 中索引文本。

```
include-days 0 https://www.mydomain.com/docs/archive/manual/
```

包括蒙版和排除蒙版可以协同工作。 例如，您可以通过创建排除日期掩码并包含一个或多个带有包含URL掩码的被排除页面，将网站的大部分排除在索引之外。 如果入口点URL如下：

```
https://www.mydomain.com/archive/
```

搜索自动机对、和下的所有页面进行爬 `/archive/summer/`索 `/archive/spring/`和索引 `/archive/fall/``archive` （假定文件夹中的每个文件夹中至少有一个页面的链接）。 出现此行为是因为链接路径使搜索自动机能够“查找”文件夹 `/summer/`、 `/spring/`和 `/fall/` 文件夹中的文件，并且文件夹URL与入口点URL自动生成的包含掩码匹配。

请参 [阅关于URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

请参 [阅配置帐户设置](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

您可以选择排除文件夹中存在90天以上的所有页面，其 `/fall/` 中包含排除日期掩码，如下所示：

```
exclude-days 90 https://www.mydomain.com/archive/fall/
```

您只能选择性地 `/archive/fall/index.html` 将（不管文件的旧版本如何——任何文件0天或更旧的版本都匹配）包含在包含以下日期掩码的索引中：

```
include-days 0 https://www.mydomain.com/archive/fall/index.html
```

要使上述两个蒙版示例按预期工作，您必须首先列表包含蒙版，如下所示：

```
include-days 0 https://www.mydomain.com/archive/fall/index.html 
exclude-days 90 https://www.mydomain.com/archive/fall/
```

由于搜索机器人按照它们指定的顺序遵循方向，因此搜索机器人首先包括 `/archive/fall/index.html`，然后排除文件夹中的其余文 `/fall` 件。

如果指令的指定方式与下面相反：

```
exclude-days 90 https://www.mydomain.com/archive/fall/ 
include-days 0 https://www.mydomain.com/archive/fall/index.html 
```

然 `/archive/fall/index.html` 后不包括，即使遮罩指定应包括它。 首先出现的日期蒙版始终优先于稍后在蒙版设置中显示的日期蒙版。 此外，如果搜索自动机遇到与包含日期掩码和排除日期掩码两者匹配的页面，则首先列出的掩码始终优先。

请参 [阅配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

## 关于将关键字与日期蒙版一起使用 {#section_CCBB3E3FDBDE4725B2B571FD6594470C}

您可以使用一个或多个空格分隔的关键字限定每个包含蒙版，这些关键字会影响匹配页面的索引方式。

逗号不能作为遮罩和关键字之间的分隔符； 只能使用空格。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>关键词 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>noindex </p> </td> 
   <td colname="col2"> <p> 如果不想为日期在包含蒙版指定的日期或之前的页面上的文本编制索引，请添加 
     <userinput>
       noindex 
     </userinput> 在包含日期掩码之后，如下所示： </p> <p> <code> include-days&amp;nbsp;10&amp;nbsp;*.swf&amp;nbsp;noindex </code> </p> <p>请确保将关键字与遮罩分隔为空格。 </p> <p>上例指定搜索自动机遵循扩展名为“.swf”（10天或更旧）的文件中的所有链接。 但是，它会禁用对包含在这些文件中的所有文本进行索引。 </p> <p>您可能希望确保未为旧文件的文本编制索引，但仍遵循这些文件中的所有链接。 在这种情况下，请将包含日期掩码与“noindex”关键字一起使用，而不是使用排除日期掩码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofoly </p> </td> 
   <td colname="col2"> <p> 如果要为日期在包含蒙版指定的日期或之前的页面上的文本编制索引，但您不希望遵循匹配页面的链接，请添加 
     <userinput>
       nofoly 
     </userinput> 在包含日期掩码之后，如下所示： </p> <p> <code> include-days&amp;nbsp;8&amp;nbsp;https://www.mydomain.com/photos&amp;nbsp;nofollow </code> </p> <p>请确保将关键字与遮罩分隔为空格。 </p> <p>The 
     <userinput>
       nofoly 
     </userinput> 关键字等效于具有 
     <userinput>
       content="nofollow" 
     </userinput> 在 
     <userinput>
       &lt;head&gt;...&lt;/head&gt; 
     </userinput> 匹配页面的标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>server-date </p> </td> 
   <td colname="col2"> <p>用于包括和排除蒙版。 </p> <p>搜索机器人通常在检查日期掩码之前下载并解析每个文件。 发生此行为是因为某些文件类型可以在文件本身中指定日期。 例如，HTML文档可以包含设置文件日期的meta标签。 </p> <p>如果要根据文件的日期排除许多文件，并且不想在服务器上增加不必要的负载，则可以使用 
     <userinput>
       server-date 
     </userinput> 的URL。 </p> <p>此关键字指示搜索机器人信任服务器返回的文件的日期，而不是分析每个文件。 例如，如果文档为90天或更早，则以下排除日期掩码会忽略与URL匹配的页，这取决于服务器在HTTP头中返回的日期： </p> <p> <code> exclude-days&amp;nbsp;90&amp;nbsp;https://www.mydomain.com/docs/archive&amp;nbsp;server-date </code> </p> <p> 如果服务器返回的日期已过90天或更久， 
     <userinput>
       server-date 
     </userinput> 指定不从服务器下载排除的文档。 这意味着文档的索引创建时间更短，服务器的负载也更轻。 如果显示 
     <userinput>
       server-date 
     </userinput> 未指定，搜索自动机将忽略服务器在HTTP头中返回的日期。 而是下载每个文件并检查是否指定了日期。 如果文件中未指定日期，则搜索自动机将使用服务器返回的日期。 </p> <p>您不应使用 
     <userinput>
       server-date 
     </userinput> 文件包含覆盖服务器日期的命令。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>regexp </p> </td> 
   <td colname="col2"> <p> 用于包括和排除蒙版。 </p> <p>前面的任何日期掩码 
     <userinput>
       regexp 
     </userinput> 被视为常规表达式。 </p> <p>如果搜索自动机遇到与排除常规表达式日期掩码匹配的文件，它不会为这些文件编制索引。 </p> <p>如果搜索自动机遇到与包含常规表达式日期蒙版匹配的文件，它将为这些文档建立索引。 </p> <p>例如，假定您具有以下日期掩码： </p> <p> <code> exclude-days&amp;nbsp;180&amp;nbsp;regexp&amp;nbsp;.*archive.* </code> </p> <p>遮罩告知搜索自动机排除180天或更早的匹配文件。 即，URL中包含“archive”一词的文件。 </p> <p>请参阅 <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> 常规表达式 </a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 添加日期蒙版以索引网站的各个部分或不为其索引 {#task_0010543C55F648D2B5DEFEFAD60FAF04}

您可以使用日期蒙版根据文件的年龄，在客户搜索结果中包含或排除文件。

使用和 **[!UICONTROL Test Date]** 字 **[!UICONTROL Test URL]** 段测试在索引后是否包含文件。

请确保重新构建站点索引，以便您的客户能够看到URL蒙版的结果。

请参 [阅配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**添加日期蒙版以索引或不索引网站的各个部分**

1. 在产品菜单上，单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Date Masks]**。
1. （可选）在页 [!DNL Date Masks] 面的字 **[!UICONTROL Test Date]** 段中，输入格式为YYYY-MM-DD的日期(例如 `2011-07-25`); 在字 **[!UICONTROL Test URL]** 段中，输入网站的URL掩码，然后单击 **[!UICONTROL Test]**。
1. 在字段 [!DNL Date Masks] 中，每行输入一个日期掩码地址。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列任一操作：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于密码 {#concept_3EDBD731725D46B891F834D4472774DC}

要访问受HTTP基本身份验证保护的网站部分，可以添加一个或多个口令。

在客户看到“密码”设置的效果之前，您必须重新构建站点索引。

请参 [阅配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

在页面 [!DNL Passwords] 上，只需在一行中键入每个口令。 密码由URL或领域、用户名和密码组成，如下例所示：

```
https://www.mydomain.com/ myname mypassword
```

除了使用URL路径（如上所示），您还可以指定领域。

要确定要使用的正确领域，请使用浏览器打开受密码保护的网页，然后查看“输入网络密码”对话框。

![](assets/realms.gif)

领域名称，在本例中为“我的站点领域”。

使用上面的领域名称，您的密码可能如下所示：

```
My Site Realm myusername mypassword
```

如果您的网站有多个领域，您可以通过在单独的行上为每个领域输入用户名和密码来创建多个口令，如下例所示：

```
Realm1 name1 password1 
Realm2 name2 password2 
Realm3 name3 password3
```

您可以混合使用包含URL或领域的口令，这样您的口令列表可能如下所示：

```
Realm1 name1 password1 
https://www.mysite.com/path1/path2 name2 password2 
Realm3 name3 password3 
Realm4 name4 password4 
https://www.mysite.com/path1/path5 name5 password5 
https://www.mysite.com/path6 name6 password6
```

在上述列表中，使用第一个密码，它包含与服务器的身份验证请求相匹配的领域或URL。 例如，即使位于 `https://www.mysite.com/path1/path2/index.html` 的文 `Realm3`件在中，也 `name2``password2` 会被使用，因为用URL定义的密码列在用领域定义的密码之上。

## 为访问网站中需要身份验证的区域添加口令 {#task_DED19D476FF04B48BB6456D5ECB8628A}

您可以使用“口令”访问网站中受口令保护的区域，以便进行搜索和索引。

在客户看到密码的添加效果之前，请确保重新构建站点索引

请参 [阅配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**为访问网站中需要身份验证的区域添加口令**

1. 在产品菜单上，单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Passwords]**。
1. 在页 [!DNL Passwords] 面上的字 **[!UICONTROL Passwords]** 段中，输入领域或URL及其关联的用户名和密码（以空格分隔）。

   领域密码和URL密码在单独行上的示例：

   ```
   Realm1 name1 password1 
   https://www.mysite.com/path1/path2 name2 password2
   ```

   每行只添加一个密码。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列任一操作：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于内容类型 {#concept_6FEA1355C0374500B4C53090C34A8A07}

可以使 [!DNL Content Types] 用选择要为此帐户爬网和索引的文件类型。

您可以选择爬网和索引的内容类型包括PDF文档、文本文档、Adobe Flash电影、来自Microsoft Office应用程序（如Word、Excel和Powerpoint）的文件以及MP3文件中的文本。 在所选内容类型内找到的文本与网站上的所有其他文本一起搜索。

在客户看到“内容类型”设置的效果之前，您必须重新构建站点索引。

请参 [阅配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

## 关于为MP3音乐文件编制索引 {#section_AD2E28BEEE3E46629E2B05C34A963673}

如果在页面上选 **[!UICONTROL Text in MP3 Music Files]** 择该选 [!DNL Content Types] 项，将通过两种方式之一对MP3文件进行爬网和索引。 第一种也是最常见的方式是通过HTML文件中的锚点href标签进行处理，如下所示：

```
<a href="MP3-file-URL"></a>
```

第二种方法是输入MP3文件的URL作为URL入口点。

请参 [阅关于URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

MP3文件的MIME类型“audio/mpeg”可识别。

请注意，MP3音乐文件大小可能很大，即使它们通常只包含少量文本。 例如，MP3文件可以选择存储专辑名称、艺术家姓名、歌名、歌曲流派、发布年份和评论等内容。 此信息存储在文件末尾的称为TAG的地方。 包含TAG信息的MP3文件按以下方式编制索引：

* 歌曲标题会被视为HTML页面的标题。
* 注释被视为为HTML页面定义的描述。
* 流派被视为为HTML页面定义的关键字。
* 艺术家姓名、专辑名称和发布年份被视为HTML页面的正文。

请注意，在您的网站上爬网和编制索引的每个MP3文件都计为一页。

如果您的网站包含许多大型MP3文件，则可能超出帐户的索引字节限制。 如果发生这种情况，您可以 **[!UICONTROL Text in MP3 Music Files]** 在页 [!DNL Content Types] 面上取消选择，以阻止对网站上的所有MP3文件进行索引。

如果只想阻止在网站上为某些MP3文件编制索引，可以执行下列操作之一：

* 在链接到MP3文件的锚点标签周围添加 `<nofollow>` 和标 `</nofollow>` 签。 搜索自动机不遵循这些标记之间的链接。

* 将MP3文件的URL添加为排除蒙版。

   请参 [阅关于URL蒙版](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164)。

## 选择要爬网和索引的内容类型 {#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8}

可以使 [!DNL Content Types] 用选择要为此帐户爬网和索引的文件类型。

您可以选择爬网和索引的内容类型包括PDF文档、文本文档、Adobe Flash电影、来自Microsoft Office应用程序（如Word、Excel和Powerpoint）的文件以及MP3文件中的文本。 在所选内容类型内找到的文本与网站上的所有其他文本一起搜索。

在客户看到“内容类型”设置的效果之前，您必须重新构建站点索引。

请参 [阅配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

要爬网和索引中文、日文或韩文MP3文件，请完成以下步骤。 然后，在 **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]**&#x200B;中，指定用于对MP3文件进行编码的字符集。

请参 [阅注射](../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5)。

**选择要爬网和索引的内容类型**

1. 在产品菜单上，单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**。
1. 在页面 [!DNL Content Types] 上，检查要在网站上爬网和索引的文件类型。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列任一操作：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于连接 {#concept_E2F3B7E7521147479E5948A94BB3A40B}

您可以使用“连接”来添加最多十个HTTP连接，搜索自动机使用这些连接来为您的网站建立索引。

增加连接数可以显着减少完成爬网和索引所需的时间。 但是，请注意，每个附加连接都会增加服务器上的负载。

## 添加连接以提高索引速度 {#task_3E9B83E43C1842A19066355A15C4A6FB}

您可以通过使用连接来增加Crawler同时使用的HTTP连接数，减少为网站编制索引所花费的时间。 最多可以添加十个连接。

请注意，每个附加连接都会增加服务器上的负载。

**添加连接以提高索引速度**

1. 在产品菜单上，单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Connections]**。
1. 在页 [!DNL Parallel Indexing Connections] 面上的字 **[!UICONTROL Number of Connections]** 段中，输入要添加的连接数(1-10)。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列任一操作：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于表单提交 {#concept_CADD5D7CF373497DAA6F8564D7BC8502}

您可以使用表单提交来帮助您识别和处理网站上的表单。

在网站的搜索和索引过程中，会将遇到的每个表单与您添加的表单定义进行比较。 如果表单与表单定义匹配，则提交表单以进行索引。 如果表单与多个定义匹配，则对于每个匹配的定义，表单将提交一次。

## 在网站上添加表单定义以索引表单 {#task_62FBCE9E6DBE4BDA8D1249233ADFC00F}

您可以使 [!DNL Form Submission] 用来帮助处理在网站上识别的用于索引的表单。

请确保重新构建站点索引，以便您的客户能够看到更改结果。

请参 [阅配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**在网站上添加表单定义以索引表单**

1. 在产品菜单上，单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**。
1. 在页面 [!DNL Form Submission] 上，单击 **[!UICONTROL Add New Form]**。
1. 在页面 [!DNL Add Form Definition] 上，设置和 [!DNL Form Recognition] 选 [!DNL Form Submission] 项。

   页面部分中 [!DNL Form Recognition] 的五个选 [!DNL Form Definition] 项用于标识网页中可处理的表单。

   此部分中的三个 [!DNL Form Submission] 选项用于指定随表单一起提交到Web服务器的参数和值。

   每行输入一个确认或提交参数。 每个参数都必须包括名称和值。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p> <b>表单识别</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>页面URL掩码 </p> </td> 
      <td colname="col2"> <p>标识包含表单的网页。 要标识在单个页面上显示的表单，请输入该页面的URL，如下例所示： </p> <p> <code> https://www.mydomain.com/login.html </code> </p> <p>要标识在多个页面上显示的表单，请指定使用通配符来描述这些页面的URL掩码。 例如，要标识在任何ASP页面下 <code> https://www.mydomain.com/register/ </code>遇到的表单，您应指定以下内容： </p> <p> <code> https://www.mydomain.com/register/*.asp&amp;nbsp; </code> </p> <p>您还可以使用常规表达式来标识多个页面。 只需指定 
      <userinput>
        regexp 
      </userinput> 关键字，如以下示例所示： </p> <p> <code> regexp&amp;nbsp;^https://www\.mydomain\.com/.*/login\.html$ </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>操作URL掩码 </p> </td> 
      <td colname="col2"> <p>标识操作属性 
      <userinput>
        &lt;form&gt; 
      </userinput> 标记之前。 </p> <p>与页面URL掩码一样，操作URL掩码可以采用单个URL、带通配符的URL或常规表达式。 </p> <p>URL掩码可以是以下任一掩码： 
      <ul id="ul_EDFE7688D3DD4C0BBACCE5D4648D8E44"> 
      <li id="li_77550A448D954EF29FF33EE5E8B5E0F5"> 完整路径，如下所示： <code> https://www.mydomain.com/products.html </code> </li> 
      <li id="li_F84E25553BBA41419BE153DC0709E011"> 部分路径，如下所示： <code> https://www.mydomain.com/products </code> </li> 
      <li id="li_8DADA1C8604740FCACBA30B4AAADB2A1"> 使用通配符的URL，如下所示： <code> https://www.mydomain.com/*.html </code> </li> 
      <li id="li_1EF637B450654B509AA4B618F7FD3C2B"> 常规表达式，如下所示： <code> regexp&amp;nbsp^https://www\.mydomain\.com/.*/login\.html$ </code> </li> 
      </ul> </p> <p>如果您不想为通过URL掩码或操作URL掩码标识的页面上的文本编制索引，或者如果您不希望在这些页面上跟踪链接，则可以使用 
      <userinput>
        noindex 
      </userinput> 和 
      <userinput>
        nofoly 
      </userinput> 关键字。 您可以使用URL蒙版或入口点将这些关键字添加到蒙版。 </p> <p>请参 <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573" type="concept" format="dita" scope="local"> 阅关于URL入口 </a>点。 </p> <p>请参阅 <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164" type="concept" format="dita" scope="local"> 关于URL蒙 </a>版。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>表单名称蒙版 </p> </td> 
      <td colname="col2"> <p>在 
      <userinput>
        &lt;form&gt; 
      </userinput> 网页中的标记包含名称属性。 </p> <p>您可以使用简单名称( 
      <userinput>
        login_form 
      </userinput>)，带通配符的名称( 
      <userinput>
        表单* 
      </userinput>)或常规表达式( 
      <userinput>
        regexp ^。*授权。*$ 
      </userinput>) 来访问。 </p> <p>您通常可以将此字段留空，因为表单通常没有名称属性。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>表单ID蒙版 </p> </td> 
      <td colname="col2"> <p>在 
      <userinput>
        &lt;form&gt; 
      </userinput> 网页中的标记包含id属性。 </p> <p>您可以使用简单名称( 
      <userinput>
        login_form 
      </userinput>)，带通配符的名称( 
      <userinput>
        表单* 
      </userinput>)或常规表达式( 
      <userinput>
        regexp ^。*授权。*$ 
      </userinput>) 来访问。 </p> <p>您通常可以将此字段留空，因为表单通常没有名称属性。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>参数 </p> </td> 
      <td colname="col2"> <p>标识包含或不包含指定参数或具有特定值的指定参数的表单。 </p> <p>例如，要标识包含预设为rick_brough@mydomain.com的电子邮件参数、口令参数而非名称参数的表单，您应指定以下参数设置，每行一个： </p> <p> <code> email=rick_brough@mydomain.com password  not&nbsp;first-name </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>表单提交</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>覆盖操作URL </p> </td> 
      <td colname="col2"> <p>指定表单提交的目标何时与表单的操作属性中指定的内容不同。 </p> <p>例如，当通过JavaScript函数提交表单时，您可以使用此选项，该函数构造的URL值与在表单中找到的URL值不同。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>覆盖方法 </p> </td> 
      <td colname="col2"> <p>指定表单提交的目标何时与表单的action属性中使用的内容不同，以及提交JavaScript更改方法的时间。 </p> <p>所有表单参数的默认值( 
      <userinput>
        &lt;input&gt; 
      </userinput> 标记，包括隐藏字段)，默认 
      <userinput>
        &lt;选项&gt; 
      </userinput> 从 
      <userinput>
        &lt;选择&gt; 
      </userinput> 标记和 
      <userinput>
        &lt;textarea&gt;...&lt;/textarea&gt; 
      </userinput> 标记)。 但是，在“参数”字段的“表 <span class="wintitle"> 单提交” </span> 部分中列出的 <span class="uicontrol"> 任何 </span> 参数都将替换为表单默认值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>参数 </p> </td> 
      <td colname="col2"> <p>您可以在表单提交参数前添加前缀 
      <userinput>
        操作 
      </userinput> keyword. </p> <p>在参数前加前缀时 
      <userinput>
        操作 
      </userinput>，它不会作为表单提交的一部分提交。 此行为对于应取消选择提交的复选框很有用。 </p> <p>例如，假定您要提交以下参数： </p> <p> 
      <ul id="ul_962D12BACF464FF189DB12BFAFCC93A6"> 
      <li id="li_830C6C3EC8D2448388A453BB8EDE5940"> 具有值的电子邮件参数 
      <userinput>
        nobody@mydomain.com 
      </userinput> </li> 
      <li id="li_905497E3FACE472DBDD49392D5B45E01"> 带值的口令参数 
      <userinput>
        试 
      </userinput> </li> 
      <li id="li_AAA411708ADC464793EADF0D821E282E"> 取消选择mycheckbox参数。 </li> 
      <li id="li_0D3DDE641E2B4BEF9F570C03FDB40ED2"> <p>所有其它 
      <userinput>
        &lt;form&gt; 
      </userinput> 参数作为默认值 </p> </li> 
      </ul> </p> <p>表单提交参数如下所示： </p> <p> <code> email=nobody@mydomain.com 
        password=tryme 
        not&nbsp;mycheckbox </code> </p> <p>的方法属性 
      <userinput>
        &lt;form&gt; 
      </userinput> 网页上的标签用于确定数据是使用GET方法还是POST方法发送到服务器。 </p> <p>如果在单击第一个日期的同时按住 
      <userinput>
        &lt;form&gt; 
      </userinput> 标记不包含方法属性，表单是使用GET方法提交的。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Add]**.
1. （可选）执行下列任一操作：

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 编辑表单定义 {#task_9FB34E9C8A814DFE9BF7F8F8F69BF314}

如果网站上的表单已更改，或者您只需更改定义，则可以编辑现有表单定义。

请注意，页面上没 [!DNL History] 有可还 [!DNL Form Submission] 原您对表单定义所做的任何更改的功能。

请确保重新构建站点索引，以便您的客户能够看到更改结果。

请参 [阅配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**编辑表单定义**

1. 在产品菜单上，单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**。
1. 在页 [!DNL Form Submission] 面上， **[!UICONTROL Edit]** 单击要更新的表单定义右侧。
1. 在页面 [!DNL Edit Form Definition] 上，设置和 [!DNL Form Recognition] 选 [!DNL Form Submission] 项。

   请参阅在网站上添加表单 [定义以为表单建立索引下的选项表](../c-about-settings-menu/c-about-crawling-menu.md#task_62FBCE9E6DBE4BDA8D1249233ADFC00F)。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列任一操作：

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 删除表单定义 {#task_C350FC0CDE344F2786215D544C048B5E}

如果您的网站上不再存在表单，或者您不再希望处理和索引特定表单，则可以删除现有表单定义。

请注意，页面上没 [!DNL History] 有可还 [!DNL Form Submission] 原您对表单定义所做的任何更改的功能。

请确保重新构建站点索引，以便您的客户能够看到更改结果。

请参 [阅配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**删除表单定义**

1. 在产品菜单上，单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**。
1. 在页 [!DNL Form Submission] 面上， **[!UICONTROL Delete]** 单击要删除的表单定义右侧。

   确保选择要删除的正确表单定义。 在下一步中单击时，不会出现 **[!UICONTROL Delete]** 删除确认对话框。
1. 在页面 [!DNL Delete Form Definition] 上，单击 **[!UICONTROL Delete]**。
1. （可选）执行下列任一操作：

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于索引连接器 {#concept_CA6921E2FBF641F9B4F60C92B32AFA84}

使 [!DNL Index Connector] 用定义其他输入源，为XML页面或任何类型的源编制索引。

您可以使用数据馈送输入源访问以不同于网站上通常使用的爬网方法之一发现的表单中存储的内容。 对每个文档进行爬网和索引后，都会直接与您网站上的内容页面对应。 但是，数据源来自XML文档或逗号分隔或制表符分隔的文本文件，并包含要索引的内容信息。

XML数据源由XML标准或记录组成，这些标准或记录包含与单个文档对应的信息。 这些单个文档符将添加到索引中。 文本数据馈送包含与单个文档对应的单独新行分隔记录。 这些单个文档也添加到索引中。 无论哪种情况，索引连接器配置都描述如何解释源。 每个配置都描述文件所在的位置以及服务器如何访问它。 配置还描述“映射”信息。 即，如何使用每个记录的项来填充生成索引中的元数据字段。

在将索引连接器定义添加到页 [!DNL Staged Index Connector Definitions] 面后，可以更改任何配置设置， *但* “名称”或“类型”值除外。

该页 [!DNL Index Connector] 面会向您显示以下信息：

* 已配置和添加的已定义索引连接器的名称。
* 已添加的每个连接器的以下数据源类型之一：

   * **文本** -简单的“平面”文件、逗号分隔、制表符分隔或其他一致的分隔格式。
   * **源** - XML源。
   * **XML** - XML文档集合。

* 是否为下次爬网和索引完成启用连接器。
* 数据源的地址。

另请参阅 [关于索引连接器](../c-about-settings-menu/c-about-crawling-menu.md#concept_CA6921E2FBF641F9B4F60C92B32AFA84)

## 索引过程如何用于索引连接器中的文本和源配置 {#section_E059A33D61EE4DB0972A37B8A35E9E16}

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
   <td colname="col3"> <p>对于文本和源配置，它只是一个简单的文件下载。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>将下载的数据源分解为单个伪文档。 </p> </td> 
   <td colname="col3"> <p>对于 <span class="uicontrol"> 文 </span>本，每行以换行符分隔的文本都对应单个文档，并使用指定的分隔符进行分析，如逗号或制表符。 </p> <p>对于 <span class="uicontrol"> 源 </span>，每个文档的数据都使用以下形式的常规表达式模式提取： </p> <p> <code> &lt;${Itemtag}&gt;(.*?)&lt;/${Itemtag}&gt; </code> </p> <p>使用 <span class="uicontrol"> “索 </span> 引连接器 <span class="wintitle"> 添加”页上的映射， </span> 创建数据的缓存副本，然后为Crawler创建链接列表。 数据存储在本地缓存中，并填充配置的字段。 </p> <p>解析的数据被写入本地高速缓存。 </p> <p>稍后将读取此缓存，以创建Crawler需要的简单HTML文档。 例如： </p> <p> <code> &lt;html&gt;&lt;head&gt; 
      &lt;title&gt;{title}&lt;/title&gt; 
      &lt;meta&nbsp;name="{field}"&nbsp;content="{data}"&nbsp;/&gt; 
      ... 
      &lt;/head&gt;&lt;body&gt; 
      {body} 
      &lt;/body&gt;&lt;/html&gt; </code> </p> <p>仅当 <span class="codeph"> 存在到 </span> “标题”元数据字段的映射时，才会生成&lt;title&gt;元素。 同样，仅 <span class="codeph"> 当存在 </span> 到“正文”元数据字段的映射时，才会生成&lt;正文&gt;元素。 </p> <p> <b>重要说明</b>: 不支持为预定义的URL meta标签分配值。 </p> <p>对于所有其他映射 <span class="codeph"> ，将为 </span> 每个在原始文档中找到数据的字段生成&lt;meta&gt;标签。 </p> <p>每个文档的字段将添加到缓存。 对于写入缓存的每个文档，也会生成一个链接，如以下示例所示： </p> <p> <code> &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      .... </code> </p> <p>配置的映射必须有一个字段标识为主键。 此映射构成从缓存读取数据时使用的键。 </p> <p>Crawler可识别URL <span class="codeph"> 索引： </span> 方案前缀，然后访问本地缓存的数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>爬网缓存的文档集。 </p> </td> 
   <td colname="col3"> <p>索 <span class="codeph"> 引： </span> 链接将添加到Crawler的待处理列表，并以普通爬网序列进行处理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>处理每个文档。 </p> </td> 
   <td colname="col3"> <p>每个链接的键值都与缓存中的一个条目相对应，因此搜索每个链接会导致从缓存中获取该文档的数据。 然后，它将“组合”为HTML图像，并进行处理并添加到索引中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 索引过程如何用于索引连接器中的XML配置 {#section_7F1551EA51854C5C99F284CE260526EB}

XML配置的索引创建过程与文本和源配置的创建过程类似，只有以下细微更改和例外。

由于XML爬网的文档已分为单个文件，因此上表中的步骤1和步骤2不直接适用。 如果在页面的和字 **[!UICONTROL Host Address]** 段中 **[!UICONTROL File Path]** 指定 [!DNL Index Connector Add] URL，则会下载URL并将其作为普通HTML文档进行处理。 期望下载文档包含一组链接，每 `<a href="{url}"...` 个链接都指向要处理的XML文档。 此类链接将转换为以下表单：

```
<a href="index:<ic_config_name>?url="{url}">
```

例如，如果Adobe安装程序返回了以下链接：

```
<a href="https://www.adobe.com/somepath/doc1.xml">doc 1</a> 
<a href="https://www.adobe.com/otherpath/doc2.xml">doc 2</a>
```

在上表中，步骤3不适用，步骤4在搜索和索引时完成。

或者，您也可以将XML文档与通过爬网过程自然发现的其他文档混合。 在这种情况下，可以使用重写规 **[!UICONTROL Settings]** 则( **[!UICONTROL Rewrite Rules]** > > **[!UICONTROL Crawl List Retrieve URL Rules]**)来更改XML文档的URL，将其定向到索引连接器。

请参 [阅关于爬网列表检索URL规则](../c-about-settings-menu/c-about-rewrite-rules-menu.md#concept_EC8E2E48B99A458D8567B526C9827CBA)。

例如，假设您有以下重写规则：

```
RewriteRule (^http.*[.]xml$) index:Adobe?key=$1
```

此规则将以索引连接器链 `.xml` 接结尾的任何URL转换为。 爬网程序识别并重写 `index:` URL方案。 下载过程将通过主服务器上的Index Connector Apache服务器重定向。 每个下载的文档都使用与源使用的相同常规表达式模式进行检查。 但是，在这种情况下，制造的HTML文档不会保存在缓存中。 而是直接交给爬虫进行索引处理。

## 如何配置多个索引连接器 {#section_C2B14C0F06354A57AEF6238FF3814E5D}

您可以为任何帐户定义多个索引连接器配置。 这些配置会自动添加到>中的下拉 **[!UICONTROL Settings]** 列表 **[!UICONTROL Crawl]** 中 **[!UICONTROL URL Entrypoints]** ，如下图所示：

![](assets/url_entrypoints_index_connector.png)

从下拉列表中选择配置会将值添加到URL入口点列表的末尾。

>[!NOTE]
>
>禁用的索引连接器配置添加到下拉列表时，您无法选择它们。 如果再次选择同一索引连接器配置，则会将其添加到列表的末尾，并删除以前的实例。

要指定增量爬网的索引连接器入口点，可以使用以下格式添加条目：

```
index:<indexconnector_configuration_name>
```

如果在“索引连接器”页上找到并启用了每个添加的条目，爬网程序将处理它。

注意： 由于每个文档的URL都是使用索引连接器配置名称和文档的主键构建的，因此，在执行增量更新时，请确保使用相同的索引连接器配置名称！ 这样做可以正 [!DNL Adobe Search&Promote] 确更新以前已编制索引的文档。

另请参阅 [关于URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

**在添加索引连接器时使用设置映射**

在添加索引连接器时，您可以选择使用该功 **[!UICONTROL Setup Maps]** 能下载数据源的示例。 检查数据是否适合索引。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>如果选择“索引连接器”类型…… </p> </th> 
   <th colname="col2" class="entry"> <p>设置映射功能…… </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>文本 </p> </td> 
   <td colname="col2"> <p>通过先试用制表符，然后使用竖条( <span class="codeph"> | </span>)，最后是逗号( <span class="codeph"> , </span>)。 如果您在单击“设置映射”之前已指 <span class="uicontrol"> 定了 </span>分隔符值，则会改用该值。 </p> <p>最适合方案的结果是，在Map字段中填充适当的Tag和Field值的猜测。 此外，显示所分析数据的采样。 如果知道文 <span class="uicontrol"> 件包含标题行， </span> 请务必在第一行中选择标题。 设置函数使用此信息来更好地标识生成的映射条目。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>信息源 </p> </td> 
   <td colname="col2"> <p>下载数据源并执行简单的XML分析。 </p> <p>生成的XPath标识符显示在Map表的Tag行中，在Fields中显示类似值。 这些行只标识可用数据，不生成更复杂的XPath定义。 但是，它仍然很有帮助，因为它描述了XML数据并标识了Itemtag值。 </p> <p> <p>注意：  “设置映射”功能下载整个XML源以执行其分析。 如果文件很大，此操作可能超时。 </p> </p> <p>成功后，此函数将标识所有可能的XPath项，其中许多项不值得使用。 请务必检查生成的映射定义并删除不需要或需要的映射定义。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>XML </p> </td> 
   <td colname="col2"> <p>下载代表个人文档的URL，而非主链接列表。 此单个文档将使用与源一起使用的相同机制进行分析，并显示结果。 </p> <p>单击添 <span class="uicontrol"> 加以 </span> 保存配置之前，请确保将URL更改回主链接列表文档。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**重要说明**: “设置映射”功能可能不适用于大型XML数据集，因为其文件分析器会尝试将整个文件读入内存。 因此，您可能会遇到内存不足的情况。 但是，当在索引时处理同一文档时，它不会读入内存。 相反，大型文档会“在旅途中”进行处理，而不会完全在内存中先读取。

**在添加索引连接器时使用预览**

在添加索引连接器时，您可以选择使用该功 **[!UICONTROL Preview]** 能验证数据，就像保存数据一样。 它针对配置运行测试，但不将配置保存到帐户。 测试访问配置的数据源。 但是，它将下载缓存写入临时位置； 它与索引爬网程序使用的主缓存文件夹不冲突。

预览仅处理由Acct:IndexConnector-文档-最大文档控制的5个预览的默认值。 预览的文档以源形式显示，就像它们呈现给索引爬虫一样。 显示屏类似于Web浏览器中的“视图源”功能。 您可以使用标准导航链接导航文档集中的预览。

预览不支持XML配置，因为此类文档会直接处理，而不会下载到缓存中。

## 添加索引连接器定义 {#task_96779B651A654E1F871F55D6DBBC8886}

每个索引连接器配置定义一个数据源和映射，以将为该源定义的数据项与索引中的元数据字段相关联。

在新的已启用定义的效果对客户可见之前，请重新构建站点索引。

**添加索引连接器定义**

1. 在产品菜单上，单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**。
1. 在页面 [!DNL Stage Index Connector Definitions] 上，单击 **[!UICONTROL Add New Index Connector]**。
1. 在页面 [!DNL Index Connector Add] 上，设置所需的连接器选项。 可用的选项取决于您选 **[!UICONTROL Type]** 择的选项。

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
      <td colname="col2"> <p>索引连接器配置的唯一名称。 您可以使用字母数字字符。 还允许使用字符“_”和“-”。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>类型 </p> </td> 
      <td colname="col2"> <p>数据源。 您选择的数据源类型会影响“索引连接器添加”页上可用 <span class="wintitle"> 的结果 </span> 选项。 您可以从以下选项中进行选择： </p> <p> 
      <ul id="ul_1ADC3DFBC929467385F7465BE8E13635"> 
      <li id="li_64FCD749F55442BAB316BD474128D4F9"> <span class="uicontrol"> 文本 </span> <p>简单的平面文本文件、逗号分隔、制表符分隔或其他一致的分隔格式。 每行以换行符分隔的文本对应于单个文档，并使用指定的分隔符进行分析。 </p> <p>您可以将每个值或列映射到由列号引用的元数据字段，从1(1)开始。 </p> </li> 
      <li id="li_2A4F16CE6DCE4114B7F8E4FE156252BB"> <span class="uicontrol"> 信息源 </span> <p>下载包含多个“行”信息的主XML文档。 </p> </li> 
      <li id="li_5A61C53522D74D4C9A5F65989604BDEF"> <span class="uicontrol"> XML </span> <p>下载包含链接的主XML文档( 
      <userinput>
        &lt;a&gt; 
      </userinput>)到单个XML文档。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>数据源类型： 文本</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>启用 </p> </td> 
      <td colname="col2"> <p>将配置“打开”以爬网和索引。 或者，您可以关闭配置以防止搜索和索引。 </p> <p> <b>注意</b>: 如果在入口点列表中找到禁用的索引连接器配置，则忽略它们。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>主机地址 </p> </td> 
      <td colname="col2"> <p>指定数据所在的服务器主机的地址。 </p> <p>如果需要，您可以指定数据源文档的完整URI（统一资源标识符）路径，如以下示例所示： </p> <p> <code> https://www.somewhere.com/some_path/some_file.xml </code> </p> <p>或 </p> <p> <code> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.xml </code> </p> <p>URI将被细分为“主机地址”、“文件路径”、“协议”以及（可选）“用户名”和“口令”字段的相应条目。 </p> <p>指定在其中找到数据源文件的主机系统的IP地址或URL地址。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>文件路径 </p> </td> 
      <td colname="col2"> <p>指定简单的平面文本文件、逗号分隔、制表符分隔或其他一致的分隔格式文件的路径。 </p> <p>路径相对于主机地址的根。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>增量文件路径 </p> </td> 
      <td colname="col2"> <p>指定简单的平面文本文件、逗号分隔、制表符分隔或其他一致的分隔格式文件的路径。 </p> <p>路径相对于主机地址的根。 </p> <p>如果指定，则在增量索引操作期间下载并处理此文件。 如果未指定文件，则使用“文件路径”下列出的文件。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>垂直文件路径 </p> </td> 
      <td colname="col2"> <p>指定在垂直更新期间使用的简单平面文本文件、逗号分隔的制表符分隔的格式文件或其他一致分隔的格式文件的路径。 </p> <p>路径相对于主机地址的根。 </p> <p>如果指定，则会在“垂直更新”操作期间下载并处理此文件。 </p> <p> <b>注意</b>: 默认情况下，此功能未启用。 请与技术支持联系以激活该功能供您使用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>删除文件路径 </p> </td> 
      <td colname="col2"> <p>指定简单平面文本文件的路径，每行包含一个文档标识符值。 </p> <p>路径相对于主机地址的根。 </p> <p>如果指定，则在增量索引操作期间下载并处理此文件。 此文件中找到的值用于构建“删除”请求以删除先前已索引的文档。 此文件中的值必须与“完整文件路径”或“增量文件路径”文件（在标识为“主键”的列中）中的值 <span class="uicontrol"> 相对应 </span>。 </p> <p> <b>注意</b>: 默认情况下，此功能未启用。 请与技术支持联系以激活该功能供您使用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>协议 </p> </td> 
      <td colname="col2"> <p>指定用于访问文件的协议。 您可以从以下选项中进行选择： </p> <p> 
      <ul id="ul_F6BC10FD51CA4A1D855B2B3212838A9C"> 
      <li id="li_79FB7DC65E774ABBB23E57BF98AD9738"> HTTP <p>如有必要，可输入正确的身份验证凭据以访问HTTP服务器。 </p> </li> 
      <li id="li_BAA9AD5E4B014E09B3A66C94022B7225"> HTTPS <p>如有必要，可输入正确的身份验证凭据以访问HTTPS服务器。 </p> </li> 
      <li id="li_E716ABB169DD408BA91F1CA27F445A16"> FTP <p>必须输入正确的身份验证凭据才能访问FTP服务器。 </p> </li> 
      <li id="li_FD7143019C5244C3B8A5B1B5AA84859A"> SFTP <p>必须输入正确的身份验证凭据才能访问SFTP服务器。 </p> </li> 
      <li id="li_38E0036C1365419F9D00083CACA34AFB"> File（文件） </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>超时 </p> </td> 
      <td colname="col2"> <p>指定FTP、SFTP、HTTP或HTTPS连接的超时（以秒为单位）。 此值必须介于30和300之间。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>重试 </p> </td> 
      <td colname="col2"> <p>指定失败的FTP、SFTP、HTTP或HTTPS连接的最大重试数。 此值必须介于0和10之间。 </p> <p>值为零(0)将阻止重试尝试。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>编码 </p> </td> 
      <td colname="col2"> <p>指定在指定的数据源文件中使用的字符编码系统。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Delimiter（分隔符） </p> </td> 
      <td colname="col2"> <p>指定要用于描绘指定数据源文件中每个字段的字符。 </p> <p>逗号字符( <span class="codeph"> , </span>)是分隔符的示例。 逗号用作字段分隔符，有助于在指定的数据源文件中分隔数据字段。 </p> <p>选择 <span class="uicontrol"> 选项卡？ </span> 使用“水平”选项卡字符作为分隔符。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>第一行中的标题 </p> </td> 
      <td colname="col2"> <p>指示数据源文件中的第一行仅包含标题信息，而不包含数据。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>索引的最小文档数 </p> </td> 
      <td colname="col2"> <p>如果设置为正值，则指定下载的文件中所需的最小记录数。 如果接收的记录较少，则索引操作将中止。 </p> <p> <b>注意</b>: 默认情况下，此功能未启用。 请与技术支持联系以激活该功能供您使用。 </p> <p> <b>注意</b>: 此功能仅在完整索引操作期间使用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>地图 </p> </td> 
      <td colname="col2"> <p>使用列号指定列到元数据的映射。 </p> <p> 
      <ul id="ul_981AE2C6D30443BDBFC6575D413732A2"> 
      <li id="li_A42CB9DFFF8C45A7BAC2D471FE96CEBE"> <span class="uicontrol"> 列 </span> <p> 指定列号，第一列为1(1)。 要为每个列添加新的映射行，请在“操作” <span class="wintitle"> 下 </span>单击 <span class="uicontrol"> + </span>。 </p> <p>您无需引用数据源中的每列。 相反，您可以选择跳过值。 </p> </li> 
      <li id="li_26E8C9554A5D4BC5A5073D6385E3626F"> <span class="uicontrol"> 字段 </span> <p>定义用于每个生成的&lt;meta&gt;标记的名称属性值。 </p> </li> 
      <li id="li_5DFA514B7F9549B98D6CBC095A66033C"> <span class="uicontrol"> 元数据? </span> <p>使字 <span class="uicontrol"> 段 </span> 成为下拉列表列表，您可以从中为当前帐户选择定义的元数据字段。 </p> <p>如果 <span class="uicontrol"> 需 </span> 要，字段值可以是未定义的元数据字段。 未定义的元数据字段有时对创建筛选脚本使用的 <span class="wintitle"> 内容很有用 </span>。 </p> <p>请参 <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> 阅关于筛选 </a>脚本。 </p> <p>当索引连接器在任何映射字段中处理具有多个点击的XML文档时，这些多个值将连接到生成的缓存文档中的单个值。 默认情况下，这些值使用逗号分隔符组合。 但是，假定相应的字段 <span class="wintitle"> 值 </span> 是定义的元数据字段。 此外，该字段还设置了“允 <span class="wintitle"> 许列表 </span> ”属性。 在这种情况下，该字段的列表分隔符值（定义的第一个分隔符）将用在级联中。 </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892C95"> <span class="uicontrol"> 主键？ </span> <p>只有一个映射定义被标识为主键。 此字段成为将此文档添加到索引时显示的唯一引用。 此值用于索引中文档的URL。 </p> <p>主 <span class="uicontrol"> 键值 </span> 在由索引连接器配置表示的所有文档中必须是唯一的——遇到的任何重复都将被忽略。 如果源文档不包含用作主键的唯一值，但两个或多个字段合并在一起 <span class="uicontrol"> 可以构成唯一标 </span>识符，则可以通过将多个列值与分隔值的垂直条(“|”) <i></i><span class="uicontrol"></span><span class="uicontrol"></span> 组合来定义主键。 </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892D96"> <span class="uicontrol"> 删除HTML? </span> <p>选中此选项后，将删除在此字段数据中找到的任何HTML标记。 </p> </li> 
      <li id="li_359D2902859B4C5BADB0BA26F0BA4DC0"> <span class="uicontrol"> 操作 </span> <p>允许您向映射中添加行或从映射中删除行。 行的顺序不重要。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>数据源类型： 源</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>启用 </p> </td> 
      <td colname="col2"> <p>将配置“打开”以爬网和索引。 或者，您可以关闭配置以防止搜索和索引。 </p> <p> <b>注意</b>: 如果在入口点列表中找到禁用的索引连接器配置，则忽略它们。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>主机地址 </p> </td> 
      <td colname="col2"> <p>指定在其中找到数据源文件的主机系统的IP地址或URL地址。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>文件路径 </p> </td> 
      <td colname="col2"> <p>指定包含多个“行”信息的主XML文档的路径。 </p> <p>路径相对于主机地址的根。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>增量文件路径 </p> </td> 
      <td colname="col2"> <p>指定包含多个“行”信息的增量XML文档的路径。 </p> <p>路径相对于主机地址的根。 </p> <p>如果指定，则在增量索引操作期间下载并处理此文件。 如果未指定文件，则使用“文件路径”下列出的文件。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>垂直文件路径 </p> </td> 
      <td colname="col2"> <p>指定XML文档的路径，该路径包含在垂直更新期间要使用的多个稀疏“行”信息。 </p> <p>路径相对于主机地址的根。 </p> <p>如果指定，则会在“垂直更新”操作期间下载并处理此文件。 </p> <p> <b>注意</b>: 默认情况下，此功能未启用。 请与技术支持联系以激活该功能供您使用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>删除文件路径 </p> </td> 
      <td colname="col2"> <p>指定简单平面文本文件的路径，每行包含一个文档标识符值。 </p> <p>路径相对于主机地址的根。 </p> <p>如果指定，则在增量索引操作期间下载并处理此文件。 此文件中找到的值用于构建“删除”请求以删除先前已索引的文档。 此文件中的值必须与“完整文件路径”或“增量文件路径”文件（在标识为“主键”的列中）中的值 <span class="uicontrol"> 相对应 </span>。 </p> <p> <b>注意</b>: 默认情况下，此功能未启用。 请与技术支持联系以激活该功能供您使用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>协议 </p> </td> 
      <td colname="col2"> <p>指定用于访问文件的协议。 您可以从以下选项中进行选择： </p> <p> 
      <ul id="ul_976A34FD14A841F2B610C1C0CCBB82B9"> 
      <li id="li_05BBA0F670F14431A89AE4178F1A6F94"> HTTP <p>如有必要，可输入正确的身份验证凭据以访问HTTP服务器。 </p> </li> 
      <li id="li_100446691F304572B8FC3F083F86A2CB"> HTTPS <p>如有必要，可输入正确的身份验证凭据以访问HTTPS服务器。 </p> </li> 
      <li id="li_027088A8E30444DAA8CCCC5B0BAA74C1"> FTP <p>必须输入正确的身份验证凭据才能访问FTP服务器。 </p> </li> 
      <li id="li_DCEF9D5C99354990B03E29083C2ED8DC"> SFTP <p>必须输入正确的身份验证凭据才能访问SFTP服务器。 </p> </li> 
      <li id="li_44E34FF2AB0D429EB3408106E6FCF780"> File（文件） </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Itemtag </p> </td> 
      <td colname="col2"> <p>标识可用于标识您指定的数据源文件中各个XML行的XML元素。 </p> <p>例如，在Adobe XML文档的以下源片段中，Itemtag值是记 <span class="codeph"> 录 </span>: </p> <p> <code> &lt;?xml&nbsp;version="1.0"&nbsp;encoding="utf-8"?&gt; 
        &lt;!DOCTYPE&nbsp;gsafeed&nbsp;PUBLIC&nbsp;"-//Google//DTD&nbsp;GSA&nbsp;Feeds//EN"&nbsp;""&gt; &lt;gsafeed&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;datasource&gt;marketplace&lt;/datasource&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;feedtype&gt;incremental&lt;/feedtype&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;group&nbsp;action="add"&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=1&nbsp;action="add"&nbsp;mimetype="text/html"displayurl="https://www.adobe.com/cfusion/marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=1"&gt;&lt;metadata&gt; 
        &lt;meta&nbsp;name="mp_mkt"&nbsp;content="1"/&gt; 
        &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
        dbreferenced/marketplaceicons/icn_air.png"/&gt; 
        &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;AIR&nbsp;Marketplace"/&gt; 
        &lt;meta&nbsp;name="description"&nbsp;content="Discover&nbsp;new&nbsp;applications&nbsp;..."/&gt; &lt;/metadata&gt; 
        &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;AIR&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Discover&nbsp;new&nbsp;applications&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;&lt;/cntent&gt; 
        &lt;/record&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa/
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=2&nbsp;action="add"&nbsp;mimetype="text/html"&nbsp;displayurl="https://www.adobe.com/cfusion/ 
        marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=2"&gt; 
        &lt;metadata&gt; 
        &lt;meta&nbsp;name="mp_mkt"&nbsp;content="2"/&gt; 
        &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
        dbreferenced/marketplaceicons/icn_photoshop.png"/&gt;         &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;Photoshop&nbsp;Marketplace"/&gt;         &lt;meta&nbsp;name="description"&nbsp;content="Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;..."/&gt; 
        &lt;/metadata&gt;         &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;Photoshop&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;/content&gt; 
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
      <td colname="col1"> <p>索引的最小文档数 </p> </td> 
      <td colname="col2"> <p>如果设置为正值，则指定下载的文件中所需的最小记录数。 如果接收的记录较少，则索引操作将中止。 </p> <p> <b>注意</b>: 默认情况下，此功能未启用。 请与技术支持联系以激活该功能供您使用。 </p> <p> <b>注意</b>: 此功能仅在完整索引操作期间使用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>地图 </p> </td> 
      <td colname="col2"> <p>允许您使用XPath表达式指定XML元素到元数据的映射。 </p> <p> 
      <ul id="ul_604108C0277C4892AE8A40CA39889ABD"> 
      <li id="li_0AF92270AE9F4BA8B2C7EE41FABC0F34"> <span class="uicontrol"> 标记 </span> <p>指定已解析的XML数据的XPath表示形式。 使用上面的示例Adobe XML文档，在选项Itemtag下，可以使用以下语法映射它： </p> <p> <code> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
      /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
      /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
      /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>以上语法的转换如下： </p> <p> 
      <ul id="ul_6400EBD08D424EADA1612FE4F7EFB640"> 
      <li id="li_9958F9B40D42434195597DBA9F2AF28F"> <code> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p>记 <span class="codeph"> 录元素 </span> 的displayurl属性 <span class="codeph"> 映射 </span> 到元数据字段 <span class="codeph"> page-url </span>。 </p> </li> 
      <li id="li_759013EA02CD48BE971A55B0A6A11424"> <code> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>元数 <span class="codeph"> 据元素中包含的任 </span> 何元 <span class="codeph"> 素的内容，该元素包含记录元 </span> 素，该记录元素的名称属性为标题，映射到元数据字段标题 <span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span>中。 </p> </li> 
      <li id="li_E741CA59197D462EB2946EDE874AFDC8"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>元数 <span class="codeph"> 据元素中包含的任 </span> 何元 <span class="codeph"> 素的内容，该元素包含在记 </span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span>录元素中，其名称属性是描述，映射到元数据字段。 </p> </li> 
      <li id="li_E35EAE3D284D46D485D9064D7BB6AB13"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>元数 <span class="codeph"> 据元素中包含的任 </span> 何元元 <span class="codeph"> 素的内容，该元数据元素包含在 </span> 记录元素中，其名称属性为 <span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span>描述，映射到元数据字段主体。 </p> </li> 
      </ul> </p> <p>XPath是一个相对复杂的表示法。 有关更多信息，请访问以下位置： </p> <p>请参阅 <a href="https://www.w3schools.com/xpath/" scope="external" format="html"> https://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_8147075D7ACD4811A7ED335F23FE62A6"> <span class="uicontrol"> 字段 </span> <p>定义用于每个生成的&lt;meta&gt;标记 <span class="codeph"> 的名称属 </span> 性值。 </p> </li> 
      <li id="li_2380199D63BF425A919606D8232FA6E2"> <span class="uicontrol"> 元数据? </span> <p>使字 <span class="uicontrol"> 段 </span> 成为下拉列表列表，您可以从中为当前帐户选择定义的元数据字段。 </p> <p>如果 <span class="uicontrol"> 需 </span> 要，字段值可以是未定义的元数据字段。 未定义的元数据字段有时对创建筛选脚本使用的 <span class="wintitle"> 内容很有用 </span>。 </p> <p>请参 <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> 阅关于筛选 </a>脚本。 </p> <p>当索引连接器在任何映射字段中处理具有多个点击的XML文档时，这些多个值将连接到生成的缓存文档中的单个值。 默认情况下，这些值使用逗号分隔符组合。 但是，假定相应的字段 <span class="wintitle"> 值 </span> 是定义的元数据字段。 此外，该字段还设置了“允 <span class="wintitle"> 许列表 </span> ”属性。 在这种情况下，该字段的列表分隔符值（定义的第一个分隔符）将用在级联中。 </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC70E"> <span class="uicontrol"> 主键？ </span> <p>只有一个映射定义被标识为主键。 此字段成为将此文档添加到索引时显示的唯一引用。 此值用于索引中文档的URL。 </p> <p>主 <span class="uicontrol"> 键值 </span> 在由索引连接器配置表示的所有文档中必须是唯一的——遇到的任何重复都将被忽略。 如果源文档不包含用作主键的唯一值，但两个或多个字段合并在一起 <span class="uicontrol"></span>，则可以通过将多个标签定义与 <i>分隔值的垂直条(“|”)组合</i><span class="uicontrol"></span><span class="uicontrol"></span> 来定义主键。 </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC81F"> <span class="uicontrol"> 删除HTML? </span> <p>选中此选项后，将删除在此字段数据中找到的任何HTML标记。 </p> </li> 
      <li id="li_5E829D1D0DBD4BB7AAB5DB983053D248"> <span class="uicontrol"> 是否用于删除？ </span> <p>仅在增量索引操作期间使用。 与此XPath模式匹配的记录标识要删除的项。 每个 <span class="uicontrol"> 此类记 </span> 录的主键值用于构建“删除”请求，与删除文件路径一样。 </p> <p> <b>注意</b>: 默认情况下，此功能未启用。 请与技术支持联系以激活该功能供您使用。 </p> </li> 
      <li id="li_D40E2F9AD8AD49FC9AC4B8C75BA31E28"> <span class="uicontrol"> 操作 </span> <p>允许您向映射中添加行或从映射中删除行。 行的顺序不重要。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>数据源类型： XML</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>启用 </p> </td> 
      <td colname="col2"> <p>将配置“打开”以爬网和索引。 或者，您可以关闭配置以防止搜索和索引。 </p> <p> <b>注意</b>: 如果在入口点列表中找到禁用的索引连接器配置，则忽略它们。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>主机地址 </p> </td> 
      <td colname="col2"> <p>指定在其中找到数据源文件的主机系统的URL地址。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>文件路径 </p> </td> 
      <td colname="col2"> <p>指定包含链接的主XML文档的路径( 
      <userinput>
        &lt;a&gt; 
      </userinput>)到单个XML文档。 </p> <p>路径相对于主机地址的根。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>协议 </p> </td> 
      <td colname="col2"> <p>指定用于访问文件的协议。 您可以从以下选项中进行选择： </p> <p> 
      <ul id="ul_EA4EB7953D68483FAD75753B2EE70E74"> 
      <li id="li_537F24C6B2AB435CB7C14117663D7B3F"> HTTP <p>如有必要，可输入正确的身份验证凭据以访问HTTP服务器。 </p> </li> 
      <li id="li_8C13C93C52364FFA8B9B18830CDB223C"> HTTPS <p>如有必要，可输入正确的身份验证凭据以访问HTTPS服务器。 </p> </li> 
      <li id="li_2F967B5675254C949B31EAB19910751C"> FTP <p>必须输入正确的身份验证凭据才能访问FTP服务器。 </p> </li> 
      <li id="li_C24BE4C1DE79488AA64C7133D78CD3A6"> SFTP <p>必须输入正确的身份验证凭据才能访问SFTP服务器。 </p> </li> 
      <li id="li_7581C21CFC104986A361F62BD7A370C1"> File（文件） </li> 
      </ul> </p> <p> <b>注意</b>: 只有在“主机地址”和／或“文件路径”字段中指定信息时，才使用协议设置。 单个XML文档根据其URL规范使用HTTP或HTTPS进行下载。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Itemtag </p> </td> 
      <td colname="col2"> <p>标识在您指定的数据源文件中定义“行”的XML元素。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>地图 </p> </td> 
      <td colname="col2"> <p>允许您使用列号指定列到元数据的映射。 </p> <p> 
      <ul id="ul_06F50CBA0AA64C7CB1AFAE076E629A64"> 
      <li id="li_0FA2502869BA40DC93D790B79E15A9D2"> <span class="uicontrol"> 标记 </span> <p>指定已解析的XML数据的XPath表示形式。 使用上面的Adobe XML文档示例，在选项Itemtag下，可以使用以下语法映射它： </p> <p> <code> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
        /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>以上语法的转换如下： </p> <p> 
      <ul id="ul_F8C536E6E54546D9AA5B22B879C0AF39"> 
      <li id="li_78A35DFFF1B4496CAC6EDC7B1E991F29"> <code> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p>记 <span class="codeph"> 录元素 </span> 的displayurl属性 <span class="codeph"> 映射 </span> 到元数据字段 <span class="codeph"> page-url </span>。 </p> </li> 
      <li id="li_FA7DF3D1942248B98660F3D0C82F4563"> <code> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>元数 <span class="codeph"> 据元素中包含的任 </span> 何元 <span class="codeph"> 素的内容，该元素包含记录元 </span> 素，该记录元素的名称属性为标题，映射到元数据字段标题 <span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span>中。 </p> </li> 
      <li id="li_D8000A116FF84DE59ED19C656DDD3BC1"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>元数 <span class="codeph"> 据元素中包含的任 </span> 何元 <span class="codeph"> 素的内容，该元素包含在记 </span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span>录元素中，其名称属性是描述，映射到元数据字段。 </p> </li> 
      <li id="li_7FA6A53DFD3D42A98B7BA17CC29DDB81"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>元数 <span class="codeph"> 据元素中包含的任 </span> 何元元 <span class="codeph"> 素的内容，该元数据元素包含在 </span> 记录元素中，其名称属性为 <span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span>描述，映射到元数据字段主体。 </p> </li> 
      </ul> </p> <p>XPath是一个相对复杂的表示法。 有关更多信息，请访问以下位置： </p> <p>请参阅 <a href="https://www.w3schools.com/xpath/" scope="external" format="html"> https://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_84999D07E0AE4265BC7928BBB49957B9"> <span class="uicontrol"> 字段 </span> <p>定义用于每个生成的&lt;meta&gt;标记的名称属性值。 </p> </li> 
      <li id="li_E125788D0F5242958BD790E26A675C20"> <span class="uicontrol"> 元数据? </span> <p>使字 <span class="uicontrol"> 段 </span> 成为下拉列表列表，您可以从中为当前帐户选择定义的元数据字段。 </p> <p>如果 <span class="uicontrol"> 需 </span> 要，字段值可以是未定义的元数据字段。 未定义的元数据字段有时对创建筛选脚本使用的 <span class="wintitle"> 内容很有用 </span>。 </p> <p>请参 <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> 阅关于筛选 </a>脚本。 </p> <p>当索引连接器在任何映射字段中处理具有多个点击的XML文档时，这些多个值将连接到生成的缓存文档中的单个值。 默认情况下，这些值使用逗号分隔符组合。 但是，假定相应的字段 <span class="wintitle"> 值 </span> 是定义的元数据字段。 此外，该字段还设置了“允 <span class="wintitle"> 许列表 </span> ”属性。 在这种情况下，该字段的列表分隔符值（定义的第一个分隔符）将用在级联中。 </p> </li> 
      <li id="li_9F435EFB3EC74B409EC82A851824609F"> <span class="uicontrol"> 主键？ </span> <p>只有一个映射定义被标识为主键。 此字段成为将此文档添加到索引时显示的唯一引用。 此值用于索引中文档的URL。 </p> <p>主 <span class="uicontrol"> 键值 </span> 在由索引连接器配置表示的所有文档中必须是唯一的——遇到的任何重复都将被忽略。 如果源文档不包含用作主键的唯一值，但两个或多个字段合并在一起 <span class="uicontrol"></span>，则可以通过将多个标签定义与 <i>分隔值的垂直条(“|”)组合</i><span class="uicontrol"></span><span class="uicontrol"></span> 来定义主键。 </p> </li> 
      <li id="li_9F435EFB3EC74B409EC82A851824610G"> <span class="uicontrol"> 删除HTML? </span> <p>选中此选项后，将删除在此字段数据中找到的任何HTML标记。 </p> </li> 
      <li id="li_6302D18971AD439FBECE27742649C56B"> <span class="uicontrol"> 操作 </span> <p>允许您向映射中添加行或从映射中删除行。 行的顺序不重要。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. （可选）单 **[!UICONTROL Setup Maps]** 击以下载数据源的示例。 检查数据是否适合索引。 此功能仅适用于文本和源类型。
1. （可选）单 **[!UICONTROL Preview]** 击以测试配置的实际工作。 此功能仅适用于文本和源类型。
1. 单 **[!UICONTROL Add]** 击将配置添加到页 [!DNL Index Connector Definitions] 面和页 [!DNL Index Connector Configurations] 面的下拉列表 [!DNL URL Entrypoints] 中。

   请参 [阅关于URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。
1. 在页面 [!DNL Index Connector Definitions] 上，单击 **[!UICONTROL rebuild your staged site index]**。
1. （可选）在页 [!DNL Index Connector Definitions] 面上，执行下列任一操作：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 编辑索引连接器定义 {#task_DCFC9C6A9964421DB5AB6C25DEE98DE9}

可以编辑已定义的现有索引连接器。

>[!NOTE]
>
>并非所有选项都可供您更改，如下拉列表中的“索引连接器名称”或“ [!DNL Type] 类型”。

**编辑索引连接器定义**

1. 在产品菜单上，单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**。
1. 在页 [!DNL Index Connector] 面的列标题 [!DNL Actions] 下，单击 **[!UICONTROL Edit]** 要更改其设置的索引连接器定义名称。
1. 在页面 [!DNL Index Connector Edit] 上，设置所需的选项。

   请参阅添加索引连接 [器定义下的选项表](../c-about-settings-menu/c-about-crawling-menu.md#task_96779B651A654E1F871F55D6DBBC8886)。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）在页 [!DNL Index Connector Definitions] 面上，单击 **[!UICONTROL rebuild your staged site index]**。
1. （可选）在页 [!DNL Index Connector Definitions] 面上，执行下列任一操作：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 查看索引连接器定义的设置 {#task_D0B71A7426E54247BDB3468EC576D871}

可以查看现有索引连接器定义的配置设置。

在将索引连接器定义添加到页面 [!DNL Index Connector Definitions] 后，无法更改其类型设置。 相反，您必须删除定义，然后添加新定义。

**视图索引连接器定义的设置**

1. 在产品菜单上，单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**。
1. 在页 [!DNL Index Connector] 面的列标题 [!DNL Actions] 下，单击以查 **[!UICONTROL Edit]** 看或编辑其设置的索引连接器定义名称。

## 复制索引连接器定义 {#task_3AD55DF07FC44A748D0EFDAB7B35699B}

您可以复制现有索引连接器定义，以用作要创建的新索引连接器的基础。

在复制索引连接器定义时，默认情况下会禁用复制的定义。 要启用或“打开”定义，您必须从页面中编辑该定 [!DNL Index Connector Edit] 义，然后选择 **[!UICONTROL Enable]**。

请参 [阅编辑索引连接器定义](../c-about-settings-menu/c-about-crawling-menu.md#task_DCFC9C6A9964421DB5AB6C25DEE98DE9)。

**复制索引连接器定义**

1. 在产品菜单上，单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**。
1. 在页 [!DNL Index Connector] 面的列标题 [!DNL Actions] 下，单击以查 **[!UICONTROL Copy]** 找要重复其设置的索引连接器定义名称。
1. 在页 [!DNL Index Connector Copy] 面中，输入定义的新名称。
1. 单击 **[!UICONTROL Copy]**.
1. （可选）在页 [!DNL Index Connector Definitions] 面上，执行下列任一操作：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 重命名索引连接器定义 {#task_5132118FC21B47D99881E0ED425225D7}

可以更改现有索引连接器定义的名称。

重命名定义后，选 **[!UICONTROL Settings]** 中> **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**。 您需要确保新定义名称反映在页面上的下拉列表 [!DNL URL Entrypoints] 中。

请参 [阅添加要索引的多个URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)。

**重命名索引连接器定义**

1. 在产品菜单上，单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**。
1. 在页 [!DNL Index Connector] 面的列标题 [!DNL Actions] 下，单击要更 **[!UICONTROL Rename]** 改的索引连接器定义名称。
1. 在页 [!DNL Index Connector Rename] 面中，在字段中输入定义的新名 [!DNL Name] 称。
1. 单击 **[!UICONTROL Rename]**.
1. 单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. 如果列表中存在以前的索引连接器名称，请删除该名称，然后添加新重命名的条目。

   请参 [阅添加要索引的多个URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)。 1. （可选）在页 [!DNL Index Connector Definitions] 面上，执行下列任一操作：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 删除索引连接器定义 {#task_6B0BD5D0C09F4597A401B0F3AC7C7EA7}

您可以删除不再需要或不再使用的现有索引连接器定义。

**删除索引连接器定义**

1. 在产品菜单上，单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**。
1. 在页 [!DNL Index Connector Definitions] 面的列标题 [!DNL Actions] 下，单击 **[!UICONTROL Delete]** 要删除的索引连接器定义名称。
1. 在页面 [!DNL Index Connector Delete] 上，单击 **[!UICONTROL Delete]**。
