---
description: 使用“爬网”菜单集日期和URL掩码、密码、内容类型、连接、表单定义和URL入口点。
solution: Target
subtopic: Crawling
title: 关于爬网菜单
topic-legacy: Settings,Site search and merchandising
uuid: a58c03bf-90f7-4b5b-91ff-988b95c246b0
exl-id: 22dbbc30-bf1c-4d51-8fb0-708115ba844b
source-git-commit: 95bf92df17d7832df72e8d883a22f9063e53a18d
workflow-type: tm+mt
source-wordcount: '11015'
ht-degree: 0%

---

# 关于爬网菜单{#about-the-crawling-menu}

使用“爬网”菜单集日期和URL掩码、密码、内容类型、连接、表单定义和URL入口点。

## 关于URL入口点 {#concept_5D857E3B5C124E85BC0B5AE77A509573}

大多数网站有一个客户最初访问的主要入口点或主页。 此主要入口点是搜索机器人开始索引爬网的URL地址。 但是，如果您的网站具有多个域或子域，或者您网站的某些部分未从主入口点链接，则可以使用URL入口点添加更多入口点。

每个指定URL入口点下的所有网站页面都已编入索引。 您可以将URL入口点与掩码组合，以准确控制要索引的网站的哪些部分。 客户必须先重建网站索引，然后才能看到URL入口点设置的效果。

主要入口点通常是要索引和搜索的网站的URL。 您可以在帐户设置中配置此主入口点。

请参阅[配置帐户设置](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

指定主URL入口点后，您可以选择指定要按顺序爬网的其他入口点。 通常，您会为未从主入口点下的页面链接的网页指定其他入口点。 如以下示例所示，当您的网站跨多个域时，指定其他入口点：

`https://www.domain.com/`

`https://www.domain.com/not_linked/but_search_me_too/`

`https://more.domain.com/`

您可以在下表中使用一个或多个以空格分隔的关键词来限定每个入口点。 这些关键字会影响页面的索引方式。

**重要信息**:请确保将给定的关键字与入口点分开，并用空格将其彼此分开；逗号不是有效的分隔符。

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
   <td colname="col2"> <p> 如果您不想在登入点页面上为文本编制索引，但是确实希望遵循页面的链接，请添加 
     <code>
       noindex 
     </code>。 </p> <p>与入口点分隔关键字，并带空格，如以下示例中所示： </p> <p> <code> https://www.my-additional-domain.com/more_pages/main.html&amp;nbsp;noindex </code> </p> <p>此关键字等同于带有的机器人元标记 
     <code>
       content="noindex" 
     </code>) 
     <code>
       &lt;head&gt; 
     </code>... 
     入口点页面的<code>
       &lt;/head&gt; 
     </code>标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofollow </p> </td> 
   <td colname="col2"> <p> 如果要在入口点页面中索引文本，但不希望跟踪该页面的任何链接，请添加 
     <code>
       nofollow 
     </code>。 </p> <p>与入口点分隔关键字，并带空格，如以下示例中所示： </p> <p> <code> https://www.domain.com/not_linked/directory_listing&amp;nbsp;nofollow </code> </p> <p>此关键字等同于带有的机器人元标记 
     <code>
       content="nofollow" 
     </code> 
     <code>
       &lt;head&gt; 
     </code>... 
     入口点页面的<code>
       &lt;/head&gt; 
     </code>标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>表单 </p> </td> 
   <td colname="col2"> <p> 当入口点为登录页面时， 
     通常使用<code>
       form 
     </code>，以便搜索机器人在爬网网站之前能够提交登录表单并接收相应的Cookie。 当使用“form”关键字时，入口点页面不会编入索引，并且搜索机器人不会将入口点页面标记为已爬网。 使用 
     <code>
       nofollow 
     </code>如果您不希望搜索机器人跟踪页面的链接。 </p> </td> 
  </tr> 
 </tbody> 
</table>

另请参阅[关于内容类型](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07)。

另请参阅[关于索引连接器](../c-about-settings-menu/c-about-crawling-menu.md#concept_CA6921E2FBF641F9B4F60C92B32AFA84)。

## 添加要索引的多个URL入口点 {#task_2338A47387D74CFDAC4D4EF4A367ED45}

如果您的网站有多个域或子域，并且您希望爬网这些域或子域，则可以使用URL入口点添加更多URL。

要设置网站的主URL入口点，请使用“帐户设置”。

请参阅[配置帐户设置](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

**添加要编入索引的多个URL入口点**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**。
1. 在[!DNL URL Entrypoints]页面的[!DNL Entrypoints]字段中，为每行输入一个URL地址。
1. （可选）在&#x200B;**[!UICONTROL Add Index Connector Configurations]**&#x200B;下拉列表中，选择要添加为索引入口点的索引连接器。

   仅当您之前添加了一个或多个索引连接器定义时，下拉列表才可用。

   ![](assets/url_entrypoints_index_connector.png)

   请参阅[添加索引连接器定义](../c-about-settings-menu/c-about-crawling-menu.md#task_96779B651A654E1F871F55D6DBBC8886)。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行以下任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;还原您所做的任何更改。

      请参阅[使用History选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送阶段设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于URL掩码 {#concept_8039DFC53FF3410AA494D602F71BA164}

URL掩码是确定搜索机器人索引或不索引的网站文档的模式。

请确保重新构建网站索引，以便客户能够看到URL掩码的结果。

请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

以下是两种URL掩码，您可以使用：

* 包含URL掩码
* 排除URL掩码

包括URL掩码可让搜索机器人对任何与掩码模式匹配的文档进行索引。

排除URL掩码会告知搜索机器人对匹配的文档进行索引。

当搜索机器人从链接到链接通过您的网站时，它会遇到URL并查找与这些URL匹配的掩码。 第一个匹配项确定是在索引中包含还是排除该URL。 如果没有掩码与遇到的URL匹配，则该URL将从索引中丢弃。

包括入口点URL的URL掩码将自动生成。 此行为可确保网站上遇到的所有文档都已建立索引。 它还可方便地删除“离开”您网站的链接。 例如，如果已索引的页面链接到https://www.yahoo.com，则搜索机器人不会对该URL进行索引，因为它与由入口点URL自动生成的包含掩码不匹配。

您指定的每个URL掩码都必须位于单独的行中。

掩码可以指定以下任一项：

* `https://www.mydomain.com/products.html`中的完整路径。
* `https://www.mydomain.com/products`中的部分路径。
* 使用通配符的URL，如`https://www.mydomain.com/*.html`中所示。
* 正则表达式（适用于高级用户）。

   要使掩码成为正则表达式，请在掩码类型（`exclude`或`include`）和URL掩码之间插入关键字`regexp`。

以下是一个简单的排除URL掩码示例：

```
exclude https://www.mydomain.com/photos
```

由于此示例是排除URL掩码，因此与该模式匹配的任何文档都不会编入索引。 该模式匹配所有遇到的项目（文件和文件夹），因此不会对`https://www.mydomain.com/photos.html`和`https://www.mydomain.com/photos/index.html`（两者均与排除URL匹配）进行索引。 要仅匹配`/photos/`文件夹中的文件，URL掩码必须包含尾随斜杠，如以下示例中所示：

```
exclude https://www.mydomain.com/photos/
```

以下排除蒙版示例使用通配符。 它会告知搜索机器人忽略扩展名为“.pdf”的文件。 搜索机器人不会将这些文件添加到您的索引中。

```
exclude *.pdf
```

一个简单的包含URL掩码如下所示：

```
include https://www.mydomain.com/news/
```

只有通过URL入口点中的一系列链接链接或本身用作URL入口点的文档才会建立索引。 仅将文档的URL列为包含URL掩码不会为未链接的文档编入索引。 要将未链接的文档添加到索引中，您可以使用URL入口点功能。

请参阅[关于URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

包含蒙版和排除蒙版可以一起使用。 您可以通过创建排除URL掩码并包含一个或多个具有包含URL掩码的排除页面，将网站的大部分内容从索引中排除。 例如，假定您的入口点URL如下：

```
https://www.mydomain.com/photos/
```

搜索机器人爬网并索引`/photos/summer/`、`/photos/spring/`和`/photos/fall/`下的所有页面（假定`photos`文件夹中每个目录中至少有一个页面的链接）。 出现此行为的原因是，链接路径使搜索机器人能够在`/summer/`、`/spring/`和`/fall/`、文件夹和文件夹URL中查找文档，这些文档与入口点URL自动生成的包含掩码匹配。

您可以选择排除`/fall/`文件夹中具有排除URL掩码的所有页面，如以下示例中所示：

```
exclude https://www.mydomain.com/photos/fall/
```

或者，选择性地仅将`/photos/fall/redleaves4.html`作为索引的一部分，并使用以下URL掩码：

```
include https://www.mydomain.com/photos/fall/redleaves4.html
```

为了使上述两个掩码示例按预期工作，首先列出了包含掩码，如下所示：

```
include https://www.mydomain.com/photos/fall/redleaves4.html 
exclude https://www.mydomain.com/photos/fall/
```

由于搜索机器人按照其列出的顺序遵循方向，因此搜索机器人首先包括`/photos/fall/redleaves4.html`，然后排除`/fall`文件夹中的其余文件。

如果以相反的方式指定说明，如下所示：

```
exclude https://www.mydomain.com/photos/fall/ 
include https://www.mydomain.com/photos/fall/redleaves4.html
```

然后，即使掩码指定包含`/photos/fall/redleaves4.html`，也不会包含。

首先显示的URL掩码始终优先于稍后在掩码设置中显示的URL掩码。 此外，如果搜索机器人遇到与包含URL掩码和排除URL掩码匹配的页面，则首先列出的掩码将始终优先。

请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

## 关于将关键词与URL掩码结合使用 {#section_7609A7A6D79B482ABCA8900886541AAB}

您可以使用一个或多个空格分隔的关键字来限定每个包含掩码，这会影响匹配页面的索引方式。

逗号分隔和关键词之间的分隔符无效；只能使用空格。

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
   <td colname="col2"> <p> 如果您不想在与URL掩码匹配的页面上索引文本，但想要遵循匹配的页面链接，请添加 
     <code>
       noindex 
     </code>。 请确保将关键字与蒙版分开，并像以下示例中一样带有空格： </p> <p> <code> include&amp;nbsp;*.swf&amp;nbsp;noindex </code> </p> <p>上例指定搜索机器人跟踪来自文件的所有链接，这些链接使用 
     <code>
       .swf 
     </code>扩展名，但会禁用这些文件中包含的所有文本的索引。 </p> <p>的 
     <code>
       noindex 
     </code>关键字等同于带有的机器人元标记 
     <code>
       content="noindex" 
     </code> 
     匹配页面的<code>
       &lt;head&gt;...&lt;/head&gt; 
     </code>标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofollow </p> </td> 
   <td colname="col2"> <p> 如果要在与URL掩码匹配的页面上索引文本，但不希望跟踪匹配页面的链接，请添加 
     <code>
       nofollow 
     </code>。 请确保将关键字与蒙版分开，并像以下示例中一样带有空格： </p> <p> <code> include&amp;nbsp;https://www.mydomain.com/photos&amp;nbsp;nofollow </code> </p> <p>的 
     <code>
       nofollow 
     </code>关键字等同于带有的机器人元标记 
     <code>
       content="nofollow" 
     </code> 
     匹配页面的<code>
       &lt;head&gt;...&lt;/head&gt; 
     </code>标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>regexp </p> </td> 
   <td colname="col2"> <p>用于包含和排除掩码。 </p> <p>前面有任何URL掩码 
     <code>
       regexp 
     </code>被视为正则表达式。 如果搜索机器人遇到与排除正则表达式URL掩码匹配的文档，则这些文档不会编入索引。 如果搜索机器人遇到与包含正则表达式URL掩码匹配的文档，则这些文档将被编入索引。 例如，假定您具有以下URL掩码： </p> <p> <code> exclude&amp;nbsp;regexp&amp;nbsp;^.*/products/.*\.html$ </code> </p> <p>搜索机器人排除匹配文件，例如 
     <code>
       https://www.mydomain.com/products/page1.html 
     </code> </p> <p>如果您具有以下排除正则表达式URL掩码： </p> <p> <code> exclude&amp;nbsp;regexp&amp;nbsp;^.*\?..*$ </code> </p> <p>搜索机器人不包含任何包含CGI参数(如 
     <code>
       https://www.mydomain.com/cgi/prog/?arg1=val1&amp;arg2=val2 
     </code>。 </p> <p>如果您具有以下包含正则表达式URL掩码： </p> <p> <code> include&amp;nbsp;regexp&amp;nbsp;^.*\.swf$&amp;nbsp;noindex </code> </p> <p>搜索机器人会跟踪扩展名为“.swf”的文件中的所有链接。 的 
     <code>
       noindex 
     </code>关键字还指定未对匹配文件的文本进行索引。 </p> <p>请参阅<a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local">正则表达式</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 添加URL掩码以索引网站的某些部分或不为其索引 {#task_E1AFC17C746048B8843013D979E082C1}

您可以使用[!DNL URL Masks]定义您希望或不希望爬网和索引的网站部分。

使用“测试URL掩码”字段测试索引后文档是否包含在文档中。

请确保重新构建网站索引，以便客户能够看到URL掩码的结果。

请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**添加URL掩码以索引网站的某些部分或不为其索引**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**。
1. （可选）在[!DNL URL Masks]页面的&#x200B;**[!UICONTROL Test URL Masks]**&#x200B;字段中，输入网站中的测试URL掩码，然后单击&#x200B;**[!UICONTROL Test]**。
1. 在[!DNL URL Masks]字段中，键入`include`（添加要爬网和索引的网站），或键入`exclude`（阻止网站爬网和索引），然后键入URL掩码地址。

   每行输入一个URL掩码地址。 示例：

   ```
   include https://www.mycompany.com/summer 
   include https://www.mycompany.com/spring 
   exclude regexp .*\.xml 
   exclude https://www.mycompany.com/fall
   ```

1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行以下任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;还原您所做的任何更改。

      请参阅[使用History选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送阶段设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于日期掩码 {#concept_F4F1F58A646F4A86B8650EC46FDCEF66}

您可以使用日期掩码根据文件的年龄在搜索结果中包含或排除文件。

请确保重新构建网站索引，以便客户能够看到URL掩码的结果。

请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

以下是两种日期掩码，您可以使用：

* 包括日期掩码（“include-days”和“include-date”）

   包括日期掩码索引文件，日期在指定日期或之前。
* 排除日期掩码（“exclude-days”和“exclude-date”）

   排除日期掩码索引文件，其日期在指定日期或之前。

默认情况下，文件日期由元标记信息确定。 如果找不到Meta标记，则根据在搜索机器人下载文件时从服务器接收的HTTP标头来确定文件的日期。

您指定的每个日期掩码必须位于单独的行中。

掩码可以指定以下任一项：

* 与`https://www.mydomain.com/products.html`中一样的完整路径
* `https://www.mydomain.com/products`中的部分路径
* 使用通配符的URL `https://www.mydomain.com/*.html`
* 正则表达式。 要将掩码设为正则表达式，请在URL前插入关键字`regexp`。

包含和排除日期掩码都可以通过以下两种方式之一指定日期。 仅当在指定的日期或之前创建了匹配的文件时，才应用掩码：

1. 几天。 例如，假定日期掩码为：

   ```
   exclude-days 30 https://www.mydomain.com/docs/archive/)
   ```

   指定天数会被计回。 如果文件日期在到达日期之日或之前，则应用掩码。

1. 使用YYYY-MM-DD格式的实际日期。 例如，假定日期掩码为：

   ```
   include-date 2011-02-15 https://www.mydomain.com/docs/archive/)
   ```

   如果匹配的文档日期在指定日期或之前，则应用日期掩码。

以下是一个简单的排除日期掩码示例：

```
exclude-days 90 https://www.mydomain.com/docs/archive
```

由于这是排除日期掩码，因此任何与该模式匹配的文件都不会建立索引，并且其旧版或旧版均为90天。 排除文档时，不会编入任何文本索引，且不会从该文件中添加任何链接。 文件会被有效忽略。 在本例中，文件和文件夹可能都与指定的URL模式匹配。 请注意，`https://www.mydomain.com/docs/archive.html`和`https://www.mydomain.com/docs/archive/index.html`都与模式匹配，并且如果它们90天或更早，则不会编入索引。 要仅匹配`/docs/archive/`文件夹中的文件，日期掩码必须包含尾随斜杠，如下所示：

```
exclude-days 90 https://www.mydomain.com/docs/archive/
```

日期掩码也可与通配符一起使用。 以下排除掩码告知搜索机器人忽略扩展名为“.pdf”且日期在2011-02-15或之前的文件。 搜索自动机不会向索引添加任何匹配的文件。

```
exclude-date 2011-02-15 *.pdf
```

“包含日期掩码”看起来类似，只有匹配的文件才会添加到索引中。 以下包含日期掩码示例告知搜索机器人从网站`/docs/archive/manual/`区域中任何已过或已过零天的文件中索引文本。

```
include-days 0 https://www.mydomain.com/docs/archive/manual/
```

包含蒙版和排除蒙版可以一起使用。 例如，您可以通过创建排除日期掩码并包含一个或多个具有包含URL掩码的排除页面，将网站的大部分内容从索引中排除。 如果您的入口点URL为：

```
https://www.mydomain.com/archive/
```

搜索机器人爬网并索引`/archive/summer/`、`/archive/spring/`和`/archive/fall/`下的所有页面（假定`archive`文件夹中每个文件夹中至少有一个页面的链接）。 出现此行为的原因是，链接路径使搜索机器人能够“查找”`/summer/`、`/spring/`和`/fall/`文件夹中的文件，并且文件夹URL与入口点URL自动生成的包含掩码匹配。

请参阅[关于URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

请参阅[配置帐户设置](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

您可以选择在`/fall/`文件夹中排除90天以上的所有页面，并且其日期掩码如下所示：

```
exclude-days 90 https://www.mydomain.com/archive/fall/
```

在具有以下日期掩码的索引中，您可以选择仅包含`/archive/fall/index.html`（不管它有多老 — 任何0天或更早的文件都匹配）：

```
include-days 0 https://www.mydomain.com/archive/fall/index.html
```

要使上述两个掩码示例按预期工作，您必须首先列出包含掩码，如下所示：

```
include-days 0 https://www.mydomain.com/archive/fall/index.html 
exclude-days 90 https://www.mydomain.com/archive/fall/
```

由于搜索机器人按照指定的顺序遵循方向，因此搜索机器人首先包括`/archive/fall/index.html`，然后排除`/fall`文件夹中的其余文件。

如果以相反的方式指定说明，如下所示：

```
exclude-days 90 https://www.mydomain.com/archive/fall/ 
include-days 0 https://www.mydomain.com/archive/fall/index.html 
```

然后，即使掩码指定`/archive/fall/index.html`应该包含，也不会包含。 首先显示的日期掩码始终优先于稍后在掩码设置中显示的日期掩码。 此外，如果搜索机器人遇到与包含日期掩码和排除日期掩码都匹配的页面，则首先列出的掩码将始终优先。

请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

## 关于将关键字与日期掩码一起使用 {#section_CCBB3E3FDBDE4725B2B571FD6594470C}

您可以使用一个或多个空格分隔的关键字来限定每个包含掩码，这会影响匹配页面的索引方式。

逗号分隔和关键词之间的分隔符无效；只能使用空格。

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
   <td colname="col2"> <p> 如果您不想在日期在包含掩码指定的日期或之前的页面上索引文本，请添加 
     <code>
       noindex 
     </code> ，如下所示： </p> <p> <code> include-days&amp;nbsp;10&amp;nbsp;*.swf&amp;nbsp;noindex </code> </p> <p>请确保将关键词与蒙版分开，并留有空格。 </p> <p>上例指定搜索机器人会跟踪扩展名为“.swf”且年龄为10天或更早的文件中的所有链接。 但是，它会禁用对这些文件中包含的所有文本的索引。 </p> <p>您可能需要确保较旧文件的文本未编入索引，但仍然遵循这些文件中的所有链接。 在这种情况下，请使用包含日期掩码和“noindex”关键字，而不是使用排除日期掩码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofollow </p> </td> 
   <td colname="col2"> <p> 如果要在日期在包含掩码指定的日期之前或之前的页面上索引文本，但您不希望跟踪匹配页面的链接，请添加 
     <code>
       nofollow 
     </code> ，如下所示： </p> <p> <code> include-days&amp;nbsp;8&amp;nbsp;https://www.mydomain.com/photos&amp;nbsp;nofollow </code> </p> <p>请确保将关键词与蒙版分开，并留有空格。 </p> <p>的 
     <code>
       nofollow 
     </code>关键字等同于带有的机器人元标记 
     <code>
       content="nofollow" 
     </code> 
     <code>
       &lt;head&gt;...&lt;/head&gt; 
     </code>匹配页面的标记。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>server-date </p> </td> 
   <td colname="col2"> <p>用于包含和排除掩码。 </p> <p>搜索机器人通常在检查日期掩码之前下载并解析每个文件。 出现此行为是因为某些文件类型可以在文件本身中指定日期。 例如，HTML文档可以包含设置文件日期的元标记。 </p> <p>如果您要根据文件的日期排除许多文件，并且不希望在服务器上加载不必要的文件，则可以使用 
     <code>
       server-date 
     </code>。 </p> <p>此关键字指示搜索机器人信任服务器返回的文件的日期，而不是解析每个文件。 例如，如果文档为90天或更早，则以下排除日期掩码会忽略与URL匹配的页面（根据服务器在HTTP标头中返回的日期）： </p> <p> <code> exclude-days&amp;nbsp;90&amp;nbsp;https://www.mydomain.com/docs/archive&amp;nbsp;server-date </code> </p> <p> 如果服务器返回的日期已过90天或更久， 
     <code>
       server-date 
     </code>指定不从服务器下载排除的文档。 因此，您可以加快文档的索引时间，并减少服务器上的负载。 如果 
     未指定<code>
       server-date 
     </code>，则搜索自动机会忽略服务器在HTTP标头中返回的日期。 而是会下载并检查每个文件，以查看是否指定了日期。 如果未在文件中指定日期，则搜索机器人将使用服务器返回的日期。 </p> <p>您不应使用 
     <code>
       server-date 
     </code>如果文件包含覆盖服务器日期的命令。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>regexp </p> </td> 
   <td colname="col2"> <p> 用于包含和排除掩码。 </p> <p>前面任何日期掩码 
     <code>
       regexp 
     </code>被视为正则表达式。 </p> <p>如果搜索机器人遇到与排除正则表达式日期掩码匹配的文件，则不会为这些文件编入索引。 </p> <p>如果搜索机器人遇到与包含正则表达式日期掩码匹配的文件，则它会为这些文档编制索引。 </p> <p>例如，假定您具有以下日期掩码： </p> <p> <code> exclude-days&amp;nbsp;180&amp;nbsp;regexp&amp;nbsp;.*archive.* </code> </p> <p>掩码会告知搜索机器人排除180天或更早的匹配文件。 即，在其URL中包含“archive”一词的文件。 </p> <p>请参阅<a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local">正则表达式</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 添加日期掩码以索引或不索引网站的某些部分 {#task_0010543C55F648D2B5DEFEFAD60FAF04}

您可以使用日期掩码根据文件的年龄在客户搜索结果中包含或排除文件。

使用&#x200B;**[!UICONTROL Test Date]**&#x200B;和&#x200B;**[!UICONTROL Test URL]**&#x200B;字段来测试索引后文件是否包含在内。

请确保重新构建网站索引，以便客户能够看到URL掩码的结果。

请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**添加日期掩码以索引或不索引网站的某些部分**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Date Masks]**。
1. （可选）在[!DNL Date Masks]页面的&#x200B;**[!UICONTROL Test Date]**&#x200B;字段中，输入格式为YYYY-MM-DD的日期（例如，`2011-07-25`）；在&#x200B;**[!UICONTROL Test URL]**&#x200B;字段中，输入您网站的URL掩码，然后单击&#x200B;**[!UICONTROL Test]**。
1. 在[!DNL Date Masks]字段中，为每行输入一个日期掩码地址。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行以下任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;还原您所做的任何更改。

      请参阅[使用History选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送阶段设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于密码 {#concept_3EDBD731725D46B891F834D4472774DC}

要访问受HTTP基本身份验证保护的网站部分，可以添加一个或多个密码。

在“密码”设置的效果对客户可见之前，您必须重新构建站点索引。

请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

在[!DNL Passwords]页面上，只需在一行中键入每个密码。 密码由URL或领域、用户名和密码组成，如以下示例所示：

```
https://www.mydomain.com/ myname mypassword
```

与使用URL路径（如上所示）不同，您还可以指定领域。

要确定要使用的正确领域，请使用浏览器打开受密码保护的网页，然后查看“输入网络密码”对话框。

![](assets/realms.gif)

领域名称，在本例中为“我的网站领域”。

使用上述领域名称，您的密码可能如下所示：

```
My Site Realm myusername mypassword
```

如果您的网站有多个领域，则可以通过在单独的行上输入每个领域的用户名和密码来创建多个密码，如以下示例中所示：

```
Realm1 name1 password1 
Realm2 name2 password2 
Realm3 name3 password3
```

您可以混合使用包含URL或域的密码，以便密码列表可能如下所示：

```
Realm1 name1 password1 
https://www.mysite.com/path1/path2 name2 password2 
Realm3 name3 password3 
Realm4 name4 password4 
https://www.mysite.com/path1/path5 name5 password5 
https://www.mysite.com/path6 name6 password6
```

在上面的列表中，使用第一个密码，该密码包含与服务器的身份验证请求匹配的领域或URL。 即使`https://www.mysite.com/path1/path2/index.html`处的文件位于`Realm3`中，例如，使用`name2`和`password2`，因为使用URL定义的密码列在使用领域定义的密码的上方。

## 为访问网站中需要身份验证的区域添加密码 {#task_DED19D476FF04B48BB6456D5ECB8628A}

您可以使用密码访问网站中受密码保护的区域，以便进行爬网和索引。

在客户看到密码增加的效果之前，请确保重新构建网站索引

请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**添加密码以访问网站中需要身份验证的区域**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Passwords]**。
1. 在[!DNL Passwords]页面的&#x200B;**[!UICONTROL Passwords]**&#x200B;字段中，输入领域或URL及其关联的用户名和密码，并用空格分隔。

   领域密码和URL密码在单独行上的示例：

   ```
   Realm1 name1 password1 
   https://www.mysite.com/path1/path2 name2 password2
   ```

   每行只添加一个密码。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行以下任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;还原您所做的任何更改。

      请参阅[使用History选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送阶段设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于内容类型 {#concept_6FEA1355C0374500B4C53090C34A8A07}

可以使用[!DNL Content Types]选择要为此帐户爬网和索引的文件类型。

您可以选择爬网和索引的内容类型包括PDF文档、文本文档、AdobeFlash影片、来自Microsoft Office应用程序（如Word、Excel和Powerpoint）的文件，以及MP3文件中的文本。 在选定内容类型中找到的文本与您网站上的所有其他文本一起搜索。

在客户看到“内容类型”设置的效果之前，必须重新构建网站索引。

请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

## 关于索引MP3音乐文件 {#section_AD2E28BEEE3E46629E2B05C34A963673}

如果在[!DNL Content Types]页面上选择&#x200B;**[!UICONTROL Text in MP3 Music Files]**&#x200B;选项，则会通过以下两种方式之一爬网并索引MP3文件。 第一种也是最常见的方法来自HTML文件中的锚点href标记，如下所示：

```
<a href="MP3-file-URL"></a>
```

第二种方法是将MP3文件的URL作为URL入口点输入。

请参阅[关于URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

MP3文件的MIME类型为“audio/mpeg”。

请注意，MP3音乐文件的大小可能非常大，即使它们通常只包含少量文本。 例如，MP3文件可以选择存储相册名称、艺术家名称、歌名、歌曲流派、发行年份和评论等内容。 此信息存储在文件末尾的TAG中。 包含TAG信息的MP3文件会按以下方式编入索引：

* 歌曲标题的处理方式与HTML页面的标题类似。
* 注释的处理方式与为HTML页面定义的描述方式相同。
* 流派被视为为HTML页面定义的关键词。
* 艺人名称、专辑名称和发行年份被视为HTML页面的正文。

请注意，您网站上爬网和索引的每个MP3文件都计为一页。

如果您的网站包含许多大型MP3文件，则您可能会超出帐户的索引字节限制。 如果发生这种情况，您可以在[!DNL Content Types]页面上取消选择&#x200B;**[!UICONTROL Text in MP3 Music Files]** ，以阻止对您网站上的所有MP3文件进行索引。

如果您只想阻止在您的网站上索引某些MP3文件，则可以执行以下操作之一：

* 为链接到MP3文件的锚点标记加上`<nofollow>`和`</nofollow>`标记。 搜索机器人不会跟踪这些标记之间的链接。

* 将MP3文件的URL添加为排除掩码。

   请参阅[关于URL掩码](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164)。

## 选择要爬网和索引的内容类型 {#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8}

可以使用[!DNL Content Types]选择要为此帐户爬网和索引的文件类型。

您可以选择爬网和索引的内容类型包括PDF文档、文本文档、AdobeFlash影片、来自Microsoft Office应用程序（如Word、Excel和Powerpoint）的文件，以及MP3文件中的文本。 在选定内容类型中找到的文本与您网站上的所有其他文本一起搜索。

在客户看到“内容类型”设置的效果之前，必须重新构建网站索引。

请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

要爬网和索引中文、日语或韩语MP3文件，请完成以下步骤。 然后，在&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]**&#x200B;中，指定用于对MP3文件进行编码的字符集。

请参阅[关于Incentations](../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5)。

**选择要爬网和索引的内容类型**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**。
1. 在[!DNL Content Types]页面中，检查要在网站上爬网和索引的文件类型。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行以下任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;还原您所做的任何更改。

      请参阅[使用History选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送阶段设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于连接 {#concept_E2F3B7E7521147479E5948A94BB3A40B}

您可以使用连接来添加多达十个HTTP连接，搜索机器人使用这些连接来索引您的网站。

增加连接数可以显着减少完成爬网和索引所花费的时间。 但是，请注意，每增加一个连接都会增加服务器的负载。

## 添加连接以提高索引速度 {#task_3E9B83E43C1842A19066355A15C4A6FB}

使用连接可增加Crawler同时使用的HTTP连接数，从而减少索引网站所花费的时间。 最多可以添加10个连接。

请注意，每增加一个连接都会增加服务器上的负载。

**添加连接以提高索引速度**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Connections]**。
1. 在[!DNL Parallel Indexing Connections]页面的&#x200B;**[!UICONTROL Number of Connections]**&#x200B;字段中，输入要添加的连接数(1-10)。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行以下任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;还原您所做的任何更改。

      请参阅[使用History选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送阶段设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于表单提交 {#concept_CADD5D7CF373497DAA6F8564D7BC8502}

您可以使用表单提交来帮助您识别和处理网站上的表单。

在网站的爬取和索引过程中，会将遇到的每个表单与您添加的表单定义进行比较。 如果表单与表单定义匹配，则提交表单以进行索引。 如果表单与多个定义匹配，则会为每个匹配的定义提交表单一次。

## 在网站上添加用于索引表单的表单定义 {#task_62FBCE9E6DBE4BDA8D1249233ADFC00F}

您可以使用[!DNL Form Submission]来帮助处理网站上可识别的用于索引的表单。

请确保重新构建站点索引，以便客户能够看到所做更改的结果。

请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**添加表单定义以在您的网站上索引表单**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**。
1. 在[!DNL Form Submission]页面上，单击&#x200B;**[!UICONTROL Add New Form]**。
1. 在[!DNL Add Form Definition]页面上，设置[!DNL Form Recognition]和[!DNL Form Submission]选项。

   [!DNL Form Definition]页面[!DNL Form Recognition]部分中的五个选项用于标识网页中可处理的表单。

   [!DNL Form Submission]部分中的三个选项用于指定随表单一起提交到Web服务器的参数和值。

   在每行输入一个确认或提交参数。 每个参数都必须包括名称和值。

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
      <td colname="col2"> <p>识别包含表单的一个或多个网页。 要识别显示在单个页面上的表单，请输入该页面的URL，如以下示例中所示： </p> <p> <code> https://www.mydomain.com/login.html </code> </p> <p>要识别显示在多个页面上的表单，请指定使用通配符描述这些页面的URL掩码。 例如，要识别在<code> https://www.mydomain.com/register/ </code>下的任何ASP页面上遇到的表单，您应指定以下内容： </p> <p> <code> https://www.mydomain.com/register/*.asp&amp;nbsp; </code> </p> <p>您还可以使用正则表达式来识别多个页面。 只需指定 
      <code>
        regexp 
      </code>关键字，如以下示例所示： </p> <p> <code> regexp&amp;nbsp;^https://www\.mydomain\.com/.*/login\.html$ </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>操作URL掩码 </p> </td> 
      <td colname="col2"> <p>标识的操作属性 
      <code>
        &lt;form&gt; 
      </code>标记。 </p> <p>与页面URL掩码类似，操作URL掩码也可以采用单个URL、带通配符的URL或正则表达式的形式。 </p> <p>URL掩码可以是以下任一掩码： 
      <ul id="ul_EDFE7688D3DD4C0BBACCE5D4648D8E44"> 
      <li id="li_77550A448D954EF29FF33EE5E8B5E0F5"> 完整路径，如下所示：<code> https://www.mydomain.com/products.html </code> </li> 
      <li id="li_F84E25553BBA41419BE153DC0709E011"> 部分路径，如下所示：<code> https://www.mydomain.com/products </code> </li> 
      <li id="li_8DADA1C8604740FCACBA30B4AAADB2A1"> 使用以下通配符的URL:<code> https://www.mydomain.com/*.html </code> </li> 
      <li id="li_1EF637B450654B509AA4B618F7FD3C2B"> 下面所示的正则表达式：<code> regexp&amp;nbsp^https://www\.mydomain\.com/.*/login\.html$ </code> </li> 
      </ul> </p> <p>如果您不想在通过URL掩码或操作URL掩码标识的页面上索引文本，或者如果您不希望在这些页面上跟随链接，则可以使用 
      <code>
        noindex 
      </code>和 
      <code>
        nofollow 
      </code>关键词。 您可以使用URL掩码或入口点将这些关键词添加到您的掩码中。 </p> <p>请参阅<a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573" type="concept" format="dita" scope="local">关于URL入口点</a>。 </p> <p>请参阅<a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164" type="concept" format="dita" scope="local">关于URL掩码</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>表单名称蒙版 </p> </td> 
      <td colname="col2"> <p>在 
      网页中的<code>
        &lt;form&gt; 
      </code>标记包含名称属性。 </p> <p>您可以使用简单的名称( 
      <code>
        login_form 
      </code>)，带通配符的名称( 
      <code>
        form* 
      </code>)或正则表达式( 
      <code>
        regexp ^.*authorize.*$ 
      </code>)。 </p> <p>您通常可以将此字段留空，因为表单通常没有名称属性。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>表单ID掩码 </p> </td> 
      <td colname="col2"> <p>在 
      网页中的<code>
        &lt;form&gt; 
      </code>标记包含id属性。 </p> <p>您可以使用简单的名称( 
      <code>
        login_form 
      </code>)，带通配符的名称( 
      <code>
        form* 
      </code>)或正则表达式( 
      <code>
        regexp ^.*authorize.*$ 
      </code>)。 </p> <p>您通常可以将此字段留空，因为表单通常没有名称属性。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>参数 </p> </td> 
      <td colname="col2"> <p>识别包含或不包含指定参数或具有特定值的指定参数的表单。 </p> <p>例如，要标识包含预设为rick_brough@mydomain.com的电子邮件参数（密码参数，但不是名字参数）的表单，您可以指定以下参数设置（每行一个）： </p> <p> <code> email=rick_brough@mydomain.com password  not&nbsp;first-name </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>表单提交</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>覆盖操作URL </p> </td> 
      <td colname="col2"> <p>指定表单提交目标与表单操作属性中指定的目标不同的时间。 </p> <p>例如，当通过JavaScript函数提交表单时，您可以使用此选项来构建与在表单中找到的URL值不同的URL值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>覆盖方法 </p> </td> 
      <td colname="col2"> <p>指定提交表单的目标何时与表单的操作属性中使用的目标不同，以及提交JavaScript何时更改了方法。 </p> <p>所有表单参数的默认值( 
      <code>
        &lt;input&gt; 
      </code>标记（包括隐藏字段），默认 
      <code>
        &lt;option&gt; 
      </code>来自 
      <code>
        &lt;select&gt; 
      </code>标记，以及 
      <code>
        &lt;textarea&gt;...&lt;/textarea&gt; 
      </code>标记)。 但是，在<span class="wintitle">表单提交</span>部分的<span class="uicontrol">参数</span>字段中列出的任何参数都将替换为表单默认值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>参数 </p> </td> 
      <td colname="col2"> <p>您可以在表单提交参数的前缀中使用 
      <code>
        not 
      </code>关键字。 </p> <p>为参数添加前缀时 
      <code>
        not 
      </code>，它不会作为表单提交的一部分提交。 此行为对于应取消选中提交的复选框非常有用。 </p> <p>例如，假定您要提交以下参数： </p> <p> 
      <ul id="ul_962D12BACF464FF189DB12BFAFCC93A6"> 
      <li id="li_830C6C3EC8D2448388A453BB8EDE5940"> 具有值的电子邮件参数 
      <code>
        nobody@mydomain.com 
      </code> </li> 
      <li id="li_905497E3FACE472DBDD49392D5B45E01"> 具有值的密码参数 
      <code>
        tryme 
      </code> </li> 
      <li id="li_AAA411708ADC464793EADF0D821E282E"> 取消选中mycheckbox参数。 </li> 
      <li id="li_0D3DDE641E2B4BEF9F570C03FDB40ED2"> <p>所有其他 
      <code>
        &lt;form&gt; 
      </code>参数作为默认值 </p> </li> 
      </ul> </p> <p>表单提交参数如下所示： </p> <p> <code> email=nobody@mydomain.com 
        password=tryme 
        not&nbsp;mycheckbox </code> </p> <p>的方法属性 
      网页上的<code>
        &lt;form&gt; 
      </code>标记用于确定数据是使用GET方法还是POST方法发送到服务器。 </p> <p>如果 
      <code>
        &lt;form&gt; 
      </code>标记不包含方法属性，则使用GET方法提交表单。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Add]**.
1. （可选）执行以下任一操作：

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送阶段设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 编辑表单定义 {#task_9FB34E9C8A814DFE9BF7F8F8F69BF314}

如果您网站上的表单已更改，或者您只需更改定义，则可以编辑现有表单定义。

请注意，[!DNL Form Submission]页面上没有[!DNL History]功能可还原您对表单定义所做的任何更改。

请确保重新构建站点索引，以便客户能够看到所做更改的结果。

请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**编辑表单定义**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**。
1. 在[!DNL Form Submission]页面上，单击要更新的表单定义右侧的&#x200B;**[!UICONTROL Edit]**。
1. 在[!DNL Edit Form Definition]页面上，设置[!DNL Form Recognition]和[!DNL Form Submission]选项。

   请参阅[添加表单定义以在您的网站上索引表单](../c-about-settings-menu/c-about-crawling-menu.md#task_62FBCE9E6DBE4BDA8D1249233ADFC00F)下的选项表。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行以下任一操作：

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送阶段设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 删除表单定义 {#task_C350FC0CDE344F2786215D544C048B5E}

如果表单在您的网站上不再存在，或者您不再希望处理和索引特定表单，则可以删除现有表单定义。

请注意，[!DNL Form Submission]页面上没有[!DNL History]功能可还原您对表单定义所做的任何更改。

请确保重新构建站点索引，以便客户能够看到所做更改的结果。

请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**删除表单定义**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**。
1. 在[!DNL Form Submission]页面上，单击要删除的表单定义右侧的&#x200B;**[!UICONTROL Delete]**。

   确保选择要删除的正确表单定义。 在下一步中单击&#x200B;**[!UICONTROL Delete]**&#x200B;时，没有删除确认对话框。
1. 在[!DNL Delete Form Definition]页面上，单击&#x200B;**[!UICONTROL Delete]**。
1. （可选）执行以下任一操作：

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送阶段设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于索引连接器 {#concept_CA6921E2FBF641F9B4F60C92B32AFA84}

使用[!DNL Index Connector]定义用于索引XML页面或任何类型信息源的其他输入源。

您可以使用数据馈送输入源访问以不同于使用一种可用爬网方法在网站上通常发现的表单形式存储的内容。 每个已爬网和已编入索引的文档都直接对应于您网站上的内容页面。 但是，数据馈送来自XML文档或以逗号分隔或制表符分隔的文本文件，并包含要索引的内容信息。

XML数据源由XML标准或记录组成，这些标准或记录包含与单个文档对应的信息。 这些单个文档将添加到索引中。 文本数据馈送包含与单个文档对应的单独新行分隔记录。 这些单个文档也会添加到索引中。 无论哪种情况，索引连接器配置都描述了如何解释馈送。 每个配置都描述文件所在的位置以及服务器如何访问该文件。 配置还描述了“映射”信息。 也就是说，如何使用每个记录的项目来填充结果索引中的元数据字段。

在将索引连接器定义添加到[!DNL Staged Index Connector Definitions]页面后，可以更改名称或类型值的任何配置设置，*除*&#x200B;之外。

[!DNL Index Connector]页面显示以下信息：

* 已配置和添加的已定义索引连接器的名称。
* 您添加的每个连接器的以下数据源类型之一：

   * **文本**  — 简单的“平面”文件、以逗号分隔、制表符分隔或其他一致分隔的格式。
   * **信息源**  - XML信息源。
   * **XML**  - XML文档的集合。

* 是否为下次爬网和索引完成启用连接器。
* 数据源的地址。

另请参阅[关于索引连接器](../c-about-settings-menu/c-about-crawling-menu.md#concept_CA6921E2FBF641F9B4F60C92B32AFA84)

## 索引过程如何用于索引连接器中的文本和信息源配置 {#section_E059A33D61EE4DB0972A37B8A35E9E16}

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
   <td colname="col3"> <p>对于<span class="uicontrol">文本</span>，每行以换行符分隔的文本都对应于单个文档，并使用指定的分隔符（如逗号或制表符）进行解析。 </p> <p>对于<span class="uicontrol">馈送</span>，使用以下形式的正则表达式模式提取每个文档的数据： </p> <p> <code> &lt;${Itemtag}&gt;(.*?)&lt;/${Itemtag}&gt; </code> </p> <p>在<span class="wintitle">索引连接器添加</span>页上使用<span class="uicontrol">映射</span> ，创建数据的缓存副本，然后为Crawler创建链接列表。 数据存储在本地缓存中，并填充配置的字段。 </p> <p>解析后的数据被写入本地缓存。 </p> <p>稍后会读取此缓存，以创建Crawler需要的简单HTML文档。 例如： </p> <p> <code> &lt;html&gt;&lt;head&gt; 
      &lt;title&gt;{title}&lt;/title&gt; 
      &lt;meta&nbsp;name="{field}"&nbsp;content="{data}"&nbsp;/&gt; 
      ... 
      &lt;/head&gt;&lt;body&gt; 
      {body} 
      &lt;/body&gt;&lt;/html&gt; </code> </p> <p><span class="codeph"> &lt;title&gt; </span>元素仅在映射存在于“标题”元数据字段时生成。 同样，仅当存在到Body元数据字段的映射时，才会生成<span class="codeph"> &lt;body&gt; </span>元素。 </p> <p> <b>重要信息</b>:不支持为预定义的URL元标记分配值。 </p> <p>对于所有其他映射，将为每个包含原始文档中找到数据的字段生成<span class="codeph"> &lt;meta&gt; </span>标记。 </p> <p>每个文档的字段都会添加到缓存中。 对于写入到缓存的每个文档，也会生成一个链接，如以下示例中所示： </p> <p> <code> &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
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

## 索引过程如何用于索引连接器中的XML配置 {#section_7F1551EA51854C5C99F284CE260526EB}

XML配置的索引过程与文本和信息源配置的过程类似，只有以下细微更改和例外。

由于XML爬网的文档已分为单个文件，因此上表中的步骤1和2不直接适用。 如果在[!DNL Index Connector Add]页面的&#x200B;**[!UICONTROL Host Address]**&#x200B;和&#x200B;**[!UICONTROL File Path]**&#x200B;字段中指定URL，则会将其下载并作为普通HTML文档进行处理。 预期是下载文档包含`<a href="{url}"...`链接的集合，每个链接指向已处理的XML文档。 此类链接将转换为以下形式：

```
<a href="index:<ic_config_name>?url="{url}">
```

例如，如果Adobe设置返回了以下链接：

```
<a href="https://www.adobe.com/somepath/doc1.xml">doc 1</a> 
<a href="https://www.adobe.com/otherpath/doc2.xml">doc 2</a>
```

在上表中，步骤3不适用，并且在爬网和索引时已完成步骤4。

或者，您也可以将XML文档与通过爬网过程自然发现的其他文档混合使用。 在这种情况下，您可以使用重写规则(**[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Retrieve URL Rules]**)来更改XML文档的URL，以将它们定向到索引连接器。

请参阅[关于爬网列表检索URL规则](../c-about-settings-menu/c-about-rewrite-rules-menu.md#concept_EC8E2E48B99A458D8567B526C9827CBA)。

例如，假定您具有以下重写规则：

```
RewriteRule (^http.*[.]xml$) index:Adobe?key=$1
```

此规则会将以`.xml`结尾的任何URL转换为索引连接器链接。 Crawler识别并重写`index:` URL方案。 下载过程将通过主服务器上的Index Connector Apache服务器进行重定向。 使用与信息源中使用的相同正则表达式模式检查每个下载的文档。 但是，在这种情况下，制造的HTML文档不会保存在缓存中。 而是直接交给爬网程序进行索引处理。

## 如何配置多个索引连接器 {#section_C2B14C0F06354A57AEF6238FF3814E5D}

您可以为任何帐户定义多个索引连接器配置。 这些配置会自动添加到&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawl]** > **[!UICONTROL URL Entrypoints]**&#x200B;的下拉列表中，如下图所示：

![](assets/url_entrypoints_index_connector.png)

从下拉列表中选择配置会将该值添加到URL入口点列表的末尾。

>[!NOTE]
>
>禁用的索引连接器配置将添加到下拉列表中，但您无法选择它们。 如果再次选择同一索引连接器配置，则该配置将添加到列表末尾，并删除前一个实例。

要为增量爬网指定索引连接器入口点，可以使用以下格式添加条目：

```
index:<indexconnector_configuration_name>
```

如果在“索引连接器”页面上找到并启用了每个添加的条目，则Crawler会处理该条目。

注意：由于每个文档的URL是使用索引连接器配置名称和文档的主键构建的，因此在执行增量更新时，请务必使用相同的索引连接器配置名称！ 这样做允许[!DNL Adobe Search&Promote]正确更新先前已索引的文档。

另请参阅[关于URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

**在添加索引连接器时使用设置图**

在添加索引连接器时，您可以选择使用功能&#x200B;**[!UICONTROL Setup Maps]**&#x200B;下载数据源的示例。 检查数据是否适合索引。

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
   <td colname="col2"> <p>通过先尝试制表符，然后再尝试垂直条(<span class="codeph"> | </span>)，最后用逗号(<span class="codeph"> 、 </span>)。 如果在单击<span class="uicontrol">设置图</span>之前已指定分隔符值，则将改用该值。 </p> <p>最适合方案会在映射字段中填充相应标记和字段值的猜测值。 此外，还显示所解析数据的采样。 如果您知道文件包含标题行，请务必在第一行</span>中选择<span class="uicontrol">标题。 设置函数使用此信息来更好地识别生成的映射条目。 </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>信息源 </p> </td> 
   <td colname="col2"> <p>下载数据源并执行简单的XML解析。 </p> <p>生成的XPath标识符显示在映射表的标记行中，并在字段中显示类似值。 这些行仅标识可用数据，并且不会生成更复杂的XPath定义。 但是，它仍然很有用，因为它描述了XML数据并标识了项目标记值。 </p> <p> <p>注意： “设置映射”功能下载整个XML源以执行其分析。 如果文件较大，此操作可能会超时。 </p> </p> <p>成功后，此函数将标识所有可能的XPath项目，其中许多项目是不想使用的。 请务必检查生成的映射定义，并删除您不需要或不需要的映射定义。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>XML </p> </td> 
   <td colname="col2"> <p>下载代表性单个文档的URL，而不是主链接列表。 此单个文档将使用与“馈送”一起使用的相同机制进行解析，并显示结果。 </p> <p>在单击<span class="uicontrol">添加</span>以保存配置之前，请确保将URL更改回主链接列表文档。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**重要信息**:“设置映射”功能可能不适用于大型XML数据集，因为其文件解析器尝试将整个文件读入内存。因此，您可能会遇到内存不足的情况。 但是，当在索引时处理同一文档时，它不会读入内存。 相反，大文档会“在移动中”进行处理，而不会首先完全读入内存。

**添加索引连接器时使用“预览”**

在添加索引连接器时，您可以选择使用功能&#x200B;**[!UICONTROL Preview]**&#x200B;来验证数据，就像在保存它一样。 它会针对配置运行测试，但不会将配置保存到帐户。 测试访问配置的数据源。 但是，它会将下载缓存写入临时位置；它与索引爬网程序使用的主缓存文件夹不冲突。

“预览”仅处理由Acct:IndexConnector-Preview-Max-Documents控制的5个文档的默认值。 预览的文档以源形式显示，如向索引爬网程序显示。 显示内容类似于Web浏览器中的“查看源”功能。 您可以使用标准导航链接导航预览集中的文档。

预览不支持XML配置，因为此类文档是直接处理的，不会下载到缓存中。

## 添加索引连接器定义 {#task_96779B651A654E1F871F55D6DBBC8886}

每个索引连接器配置定义一个数据源和映射，以将为该源定义的数据项与索引中的元数据字段相关联。

在客户看到新的已启用定义的效果之前，请重新构建网站索引。

**添加索引连接器定义**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**。
1. 在[!DNL Stage Index Connector Definitions]页面上，单击&#x200B;**[!UICONTROL Add New Index Connector]**。
1. 在[!DNL Index Connector Add]页面上，设置所需的连接器选项。 可用的选项取决于您选择的&#x200B;**[!UICONTROL Type]**。

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
      <td colname="col2"> <p>索引连接器配置的唯一名称。 您可以使用字母数字字符。 还允许使用字符“_”和“ — ”。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>类型 </p> </td> 
      <td colname="col2"> <p>数据源。 您选择的数据源类型会影响<span class="wintitle">索引连接器添加</span>页面上可用的生成选项。 您可以从以下选项中进行选择： </p> <p> 
      <ul id="ul_1ADC3DFBC929467385F7465BE8E13635"> 
      <li id="li_64FCD749F55442BAB316BD474128D4F9"> <span class="uicontrol"> 文本 </span> <p>简单的平面文本文件、以逗号分隔、制表符分隔或其他一致分隔的格式。 每个以换行符分隔的文本行对应于单个文档，并使用指定的分隔符进行解析。 </p> <p>您可以从1(1)开始，将每个值或列映射到由列号引用的元数据字段。 </p> </li> 
      <li id="li_2A4F16CE6DCE4114B7F8E4FE156252BB"> <span class="uicontrol"> 信息源 </span> <p>下载包含多个“行”信息的主XML文档。 </p> </li> 
      <li id="li_5A61C53522D74D4C9A5F65989604BDEF"> <span class="uicontrol"> XML </span> <p>下载包含链接的主XML文档( 
      <code>
        &lt;a&gt; 
      </code>)到单个XML文档。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>数据源类型：文本</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>启用 </p> </td> 
      <td colname="col2"> <p>将配置“打开”以爬网和编入索引。 或者，您也可以“关闭”配置以阻止爬网和索引。 </p> <p> <b>注意</b>:如果在入口点列表中找到已禁用的索引连接器配置，则将忽略这些配置。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>主机地址 </p> </td> 
      <td colname="col2"> <p>指定数据所在的服务器主机的地址。 </p> <p>如果需要，您可以指定数据源文档的完整URI（统一资源标识符）路径，如以下示例中所示： </p> <p> <code> https://www.somewhere.com/some_path/some_file.xml </code> </p> <p>或 </p> <p> <code> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.xml </code> </p> <p>URI将划分为主机地址、文件路径、协议以及用户名和密码（可选）字段的相应条目。 </p> <p>指定找到数据源文件的主机系统的IP地址或URL地址。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>文件路径 </p> </td> 
      <td colname="col2"> <p>指定简单平面文本文件、以逗号分隔、制表符分隔或其他一致分隔格式文件的路径。 </p> <p>路径相对于主机地址的根。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>增量文件路径 </p> </td> 
      <td colname="col2"> <p>指定简单平面文本文件、以逗号分隔、制表符分隔或其他一致分隔格式文件的路径。 </p> <p>路径相对于主机地址的根。 </p> <p>如果已指定，则会在增量索引操作期间下载并处理此文件。 如果未指定文件，则将使用“文件路径”下列出的文件。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>垂直文件路径 </p> </td> 
      <td colname="col2"> <p>指定在垂直更新期间使用的简单平面文本文件、以逗号分隔、制表符分隔或其他一致分隔格式文件的路径。 </p> <p>路径相对于主机地址的根。 </p> <p>如果已指定，则会在“垂直更新”操作期间下载并处理此文件。 </p> <p> <b>注意</b>:默认情况下，此功能未启用。联系技术支持以激活该功能以供您使用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>删除文件路径 </p> </td> 
      <td colname="col2"> <p>指定简单平面文本文件的路径，其中包含每行一个文档标识符值。 </p> <p>路径相对于主机地址的根。 </p> <p>如果已指定，则会在增量索引操作期间下载并处理此文件。 此文件中的值用于构造“删除”请求，以删除以前索引的文档。 此文件中的值必须与“完整文件路径”或“增量文件路径”文件中的值相对应，该文件中的列标识为<span class="uicontrol">主键</span>。 </p> <p> <b>注意</b>:默认情况下，此功能未启用。联系技术支持以激活该功能以供您使用。 </p> </td> 
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
      <td colname="col1"> <p>用于索引的最少文档数 </p> </td> 
      <td colname="col2"> <p>如果设置为正值，则会指定下载的文件中所需的最小记录数。 如果收到的记录较少，则索引操作将中止。 </p> <p> <b>注意</b>:默认情况下，此功能未启用。联系技术支持以激活该功能以供您使用。 </p> <p> <b>注意</b>:此功能仅在完整索引操作期间使用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>地图 </p> </td> 
      <td colname="col2"> <p>使用列号指定列到元数据的映射。 </p> <p> 
      <ul id="ul_981AE2C6D30443BDBFC6575D413732A2"> 
      <li id="li_A42CB9DFFF8C45A7BAC2D471FE96CEBE"> <span class="uicontrol"> 列 </span> <p> 指定列号，第一列为1(1)。 要为每列添加新映射行，请在<span class="wintitle">操作</span>下，单击<span class="uicontrol"> + </span>。 </p> <p>您无需引用数据源中的每个列。 相反，您可以选择跳过值。 </p> </li> 
      <li id="li_26E8C9554A5D4BC5A5073D6385E3626F"> <span class="uicontrol"> 字段 </span> <p>定义用于每个生成的&lt;meta&gt;标记的名称属性值。 </p> </li> 
      <li id="li_5DFA514B7F9549B98D6CBC095A66033C"> <span class="uicontrol"> 元数据? </span> <p>使<span class="uicontrol">字段</span>成为下拉列表，您可以从中为当前帐户选择定义的元数据字段。 </p> <p>如果需要，<span class="uicontrol">字段</span>值可以是未定义的元数据字段。 未定义的元数据字段有时对创建<span class="wintitle">筛选脚本</span>使用的内容非常有用。 </p> <p>请参阅<a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local">关于筛选脚本</a>。 </p> <p>当索引连接器在任意映射字段上处理具有多个点击的XML文档时，将多个值合并到生成的缓存文档中的单个值中。 默认情况下，这些值使用逗号分隔符组合。 但是，假定相应的<span class="wintitle">字段</span>值是定义的元数据字段。 此外，该字段还设置了<span class="wintitle">允许列表</span>属性。 在这种情况下，将在串联中使用字段的列表分隔符值（定义的第一个分隔符）。 </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892C95"> <span class="uicontrol"> 主键？  </span> <p>只有一个映射定义被标识为主键。 此字段将成为将此文档添加到索引时显示的唯一引用。 此值用于索引中文档的URL中。 </p> <p><span class="uicontrol">主键</span>值在由索引连接器配置表示的所有文档中必须是唯一的 — 遇到的任何重复项都将被忽略。 如果您的源文档不包含用作<span class="uicontrol">主键</span>的唯一值，但是将两个或多个字段合并在一起<i>可以形成唯一标识符</i>，则可以通过将多个<span class="uicontrol">列</span>值与分隔值的垂直条("|")组合在一起来定义<span class="uicontrol">主键</span>。 </p> </li> 
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
      <td colname="col2"> <p>将配置“打开”以爬网和编入索引。 或者，您也可以“关闭”配置以阻止爬网和索引。 </p> <p> <b>注意</b>:如果在入口点列表中找到已禁用的索引连接器配置，则将忽略这些配置。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>主机地址 </p> </td> 
      <td colname="col2"> <p>指定找到数据源文件的主机系统的IP地址或URL地址。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>文件路径 </p> </td> 
      <td colname="col2"> <p>指定包含多个“行”信息的主XML文档的路径。 </p> <p>路径相对于主机地址的根。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>增量文件路径 </p> </td> 
      <td colname="col2"> <p>指定包含多个“行”信息的增量XML文档的路径。 </p> <p>路径相对于主机地址的根。 </p> <p>如果已指定，则会在增量索引操作期间下载并处理此文件。 如果未指定文件，则将使用“文件路径”下列出的文件。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>垂直文件路径 </p> </td> 
      <td colname="col2"> <p>指定XML文档的路径，该文档包含要在垂直更新期间使用的多个稀疏“行”信息。 </p> <p>路径相对于主机地址的根。 </p> <p>如果已指定，则会在“垂直更新”操作期间下载并处理此文件。 </p> <p> <b>注意</b>:默认情况下，此功能未启用。联系技术支持以激活该功能以供您使用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>删除文件路径 </p> </td> 
      <td colname="col2"> <p>指定简单平面文本文件的路径，其中包含每行一个文档标识符值。 </p> <p>路径相对于主机地址的根。 </p> <p>如果已指定，则会在增量索引操作期间下载并处理此文件。 此文件中的值用于构造“删除”请求，以删除以前索引的文档。 此文件中的值必须与“完整文件路径”或“增量文件路径”文件中的值相对应，该文件中的列标识为<span class="uicontrol">主键</span>。 </p> <p> <b>注意</b>:默认情况下，此功能未启用。联系技术支持以激活该功能以供您使用。 </p> </td> 
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
      <td colname="col2"> <p>标识可用于标识您指定的数据源文件中各个XML行的XML元素。 </p> <p>例如，在AdobeXML文档的以下馈送片段中，Itemtag值为<span class="codeph">记录</span>: </p> <p> <code> &lt;?xml&nbsp;version="1.0"&nbsp;encoding="utf-8"?&gt; 
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
      <td colname="col1"> <p>用于索引的最少文档数 </p> </td> 
      <td colname="col2"> <p>如果设置为正值，则会指定下载的文件中所需的最小记录数。 如果收到的记录较少，则索引操作将中止。 </p> <p> <b>注意</b>:默认情况下，此功能未启用。联系技术支持以激活该功能以供您使用。 </p> <p> <b>注意</b>:此功能仅在完整索引操作期间使用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>地图 </p> </td> 
      <td colname="col2"> <p>允许您使用XPath表达式指定XML元素到元数据的映射。 </p> <p> 
      <ul id="ul_604108C0277C4892AE8A40CA39889ABD"> 
      <li id="li_0AF92270AE9F4BA8B2C7EE41FABC0F34"> <span class="uicontrol"> 标记 </span> <p>指定解析的XML数据的XPath表示形式。 使用上面的示例AdobeXML文档，在选项Itemtag下，可以使用以下语法映射该文档： </p> <p> <code> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
      /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
      /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
      /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>上述语法的转换如下： </p> <p> 
      <ul id="ul_6400EBD08D424EADA1612FE4F7EFB640"> 
      <li id="li_9958F9B40D42434195597DBA9F2AF28F"> <code> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p><span class="codeph">显示<span class="codeph">记录</span>元素的</span>属性映射到元数据字段<span class="codeph"> page-url </span>。 </p> </li> 
      <li id="li_759013EA02CD48BE971A55B0A6A11424"> <code> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>任何<span class="codeph">元</span>元素的<span class="codeph">内容</span>属性（包含在<span class="codeph">元数据</span>元素内），该元素包含在<span class="codeph">记录</span>元素内，其名称属性为<span class="codeph">标题</span>，并映射到元数据字段<span class="codeph">标题</span>。 </p> </li> 
      <li id="li_E741CA59197D462EB2946EDE874AFDC8"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>任何<span class="codeph">元</span>元素的<span class="codeph">内容</span>属性（包含在<span class="codeph">元数据</span>元素内），该元素包含在<span class="codeph">记录</span>元素内，其名称属性为<span class="codeph">描述</span>，并映射到元数据字段<span class="codeph"> desc </span>。 </p> </li> 
      <li id="li_E35EAE3D284D46D485D9064D7BB6AB13"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>包含在<span class="codeph">元数据</span>元素内的任何<span class="codeph">元元素的</span>内容<span class="codeph">属性（该元素包含在<span class="codeph">记录</span>元素内，其名称属性为<span class="codeph">描述</span>）映射到元数据字段<span class="codeph">正文</span>。</span> </p> </li> 
      </ul> </p> <p>XPath是一种相对复杂的表示法。 有关更多信息，请访问以下位置： </p> <p>请参阅<a href="https://www.w3schools.com/xml/xpath_intro.asp" scope="external" format="html"> https://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_8147075D7ACD4811A7ED335F23FE62A6"> <span class="uicontrol"> 字段 </span> <p>定义用于每个生成的<span class="codeph"> &lt;meta&gt; </span>标记的名称属性值。 </p> </li> 
      <li id="li_2380199D63BF425A919606D8232FA6E2"> <span class="uicontrol"> 元数据? </span> <p>使<span class="uicontrol">字段</span>成为下拉列表，您可以从中为当前帐户选择定义的元数据字段。 </p> <p>如果需要，<span class="uicontrol">字段</span>值可以是未定义的元数据字段。 未定义的元数据字段有时对创建<span class="wintitle">筛选脚本</span>使用的内容非常有用。 </p> <p>请参阅<a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local">关于筛选脚本</a>。 </p> <p>当索引连接器在任意映射字段上处理具有多个点击的XML文档时，将多个值合并到生成的缓存文档中的单个值中。 默认情况下，这些值使用逗号分隔符组合。 但是，假定相应的<span class="wintitle">字段</span>值是定义的元数据字段。 此外，该字段还设置了<span class="wintitle">允许列表</span>属性。 在这种情况下，将在串联中使用字段的列表分隔符值（定义的第一个分隔符）。 </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC70E"> <span class="uicontrol"> 主键？  </span> <p>只有一个映射定义被标识为主键。 此字段将成为将此文档添加到索引时显示的唯一引用。 此值用于索引中文档的URL中。 </p> <p><span class="uicontrol">主键</span>值在由索引连接器配置表示的所有文档中必须是唯一的 — 遇到的任何重复项都将被忽略。 如果您的源文档不包含用作<span class="uicontrol">主键</span>的单个唯一值，但是将两个或多个字段合在一起后，<i>可以形成唯一标识符</i>，则可以通过将多个<span class="uicontrol">标记</span>定义与分隔值的垂直条("|")组合在一起来定义<span class="uicontrol">主键</span>。 </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC81F"> <span class="uicontrol"> 删除HTML?  </span> <p>选中此选项后，在此字段数据中找到的任何HTML标记都将被删除。 </p> </li> 
      <li id="li_5E829D1D0DBD4BB7AAB5DB983053D248"> <span class="uicontrol"> 是否用于删除？  </span> <p>仅在增量索引操作期间使用。 与此XPath模式匹配的记录标识要删除的项目。 每个此类记录的<span class="uicontrol">主键</span>值用于构建“delete”请求，与“删除文件路径”一样。 </p> <p> <b>注意</b>:默认情况下，此功能未启用。联系技术支持以激活该功能以供您使用。 </p> </li> 
      <li id="li_D40E2F9AD8AD49FC9AC4B8C75BA31E28"> <span class="uicontrol"> 操作 </span> <p>用于向映射中添加行或从映射中删除行。 行的顺序不重要。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>数据源类型：XML</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>启用 </p> </td> 
      <td colname="col2"> <p>将配置“打开”以爬网和编入索引。 或者，您也可以“关闭”配置以阻止爬网和索引。 </p> <p> <b>注意</b>:如果在入口点列表中找到已禁用的索引连接器配置，则将忽略这些配置。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>主机地址 </p> </td> 
      <td colname="col2"> <p>指定找到数据源文件的主机系统的URL地址。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>文件路径 </p> </td> 
      <td colname="col2"> <p>指定包含链接的主XML文档的路径( 
      <code>
        &lt;a&gt; 
      </code>)到单个XML文档。 </p> <p>路径相对于主机地址的根。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>协议 </p> </td> 
      <td colname="col2"> <p>指定用于访问文件的协议。 您可以从以下选项中进行选择： </p> <p> 
      <ul id="ul_EA4EB7953D68483FAD75753B2EE70E74"> 
      <li id="li_537F24C6B2AB435CB7C14117663D7B3F"> HTTP <p>如有必要，您可以输入正确的身份验证凭据来访问HTTP服务器。 </p> </li> 
      <li id="li_8C13C93C52364FFA8B9B18830CDB223C"> HTTPS <p>如有必要，您可以输入正确的身份验证凭据来访问HTTPS服务器。 </p> </li> 
      <li id="li_2F967B5675254C949B31EAB19910751C"> FTP <p>您必须输入正确的身份验证凭据才能访问FTP服务器。 </p> </li> 
      <li id="li_C24BE4C1DE79488AA64C7133D78CD3A6"> SFTP <p>您必须输入正确的身份验证凭据才能访问SFTP服务器。 </p> </li> 
      <li id="li_7581C21CFC104986A361F62BD7A370C1"> File（文件） </li> 
      </ul> </p> <p> <b>注意</b>:只有在主机地址和/或文件路径字段中指定了信息时，才使用协议设置。根据各个XML文档的URL规范，使用HTTP或HTTPS下载它们。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Itemtag </p> </td> 
      <td colname="col2"> <p>标识在您指定的数据源文件中定义“row”的XML元素。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>地图 </p> </td> 
      <td colname="col2"> <p>允许您使用列编号指定列到元数据映射。 </p> <p> 
      <ul id="ul_06F50CBA0AA64C7CB1AFAE076E629A64"> 
      <li id="li_0FA2502869BA40DC93D790B79E15A9D2"> <span class="uicontrol"> 标记 </span> <p>指定解析的XML数据的XPath表示形式。 使用上面的示例AdobeXML文档，在选项Itemtag下，可以使用以下语法映射它： </p> <p> <code> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
        /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>上述语法的转换如下： </p> <p> 
      <ul id="ul_F8C536E6E54546D9AA5B22B879C0AF39"> 
      <li id="li_78A35DFFF1B4496CAC6EDC7B1E991F29"> <code> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p><span class="codeph">显示<span class="codeph">记录</span>元素的</span>属性映射到元数据字段<span class="codeph"> page-url </span>。 </p> </li> 
      <li id="li_FA7DF3D1942248B98660F3D0C82F4563"> <code> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>任何<span class="codeph">元</span>元素的<span class="codeph">内容</span>属性（包含在<span class="codeph">元数据</span>元素内），该元素包含在<span class="codeph">记录</span>元素内，其名称属性为<span class="codeph">标题</span>，并映射到元数据字段<span class="codeph">标题</span>。 </p> </li> 
      <li id="li_D8000A116FF84DE59ED19C656DDD3BC1"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>任何<span class="codeph">元</span>元素的<span class="codeph">内容</span>属性（包含在<span class="codeph">元数据</span>元素内），该元素包含在<span class="codeph">记录</span>元素内，其名称属性为<span class="codeph">描述</span>，并映射到元数据字段<span class="codeph"> desc </span>。 </p> </li> 
      <li id="li_7FA6A53DFD3D42A98B7BA17CC29DDB81"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>包含在<span class="codeph">元数据</span>元素内的任何<span class="codeph">元元素的</span>内容<span class="codeph">属性（该元素包含在<span class="codeph">记录</span>元素内，其名称属性为<span class="codeph">描述</span>）映射到元数据字段<span class="codeph">正文</span>。</span> </p> </li> 
      </ul> </p> <p>XPath是一种相对复杂的表示法。 有关更多信息，请访问以下位置： </p> <p>请参阅<a href="https://www.w3schools.com/xml/xpath_intro.asp" scope="external" format="html"> https://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_84999D07E0AE4265BC7928BBB49957B9"> <span class="uicontrol"> 字段 </span> <p>定义用于每个生成的&lt;meta&gt;标记的名称属性值。 </p> </li> 
      <li id="li_E125788D0F5242958BD790E26A675C20"> <span class="uicontrol"> 元数据? </span> <p>使<span class="uicontrol">字段</span>成为下拉列表，您可以从中为当前帐户选择定义的元数据字段。 </p> <p>如果需要，<span class="uicontrol">字段</span>值可以是未定义的元数据字段。 未定义的元数据字段有时对创建<span class="wintitle">筛选脚本</span>使用的内容非常有用。 </p> <p>请参阅<a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local">关于筛选脚本</a>。 </p> <p>当索引连接器在任意映射字段上处理具有多个点击的XML文档时，将多个值合并到生成的缓存文档中的单个值中。 默认情况下，这些值使用逗号分隔符组合。 但是，假定相应的<span class="wintitle">字段</span>值是定义的元数据字段。 此外，该字段还设置了<span class="wintitle">允许列表</span>属性。 在这种情况下，将在串联中使用字段的列表分隔符值（定义的第一个分隔符）。 </p> </li> 
      <li id="li_9F435EFB3EC74B409EC82A851824609F"> <span class="uicontrol"> 主键？  </span> <p>只有一个映射定义被标识为主键。 此字段将成为将此文档添加到索引时显示的唯一引用。 此值用于索引中文档的URL中。 </p> <p><span class="uicontrol">主键</span>值在由索引连接器配置表示的所有文档中必须是唯一的 — 遇到的任何重复项都将被忽略。 如果您的源文档不包含用作<span class="uicontrol">主键</span>的单个唯一值，但是将两个或多个字段合在一起后，<i>可以形成唯一标识符</i>，则可以通过将多个<span class="uicontrol">标记</span>定义与分隔值的垂直条("|")组合在一起来定义<span class="uicontrol">主键</span>。 </p> </li> 
      <li id="li_9F435EFB3EC74B409EC82A851824610G"> <span class="uicontrol"> 删除HTML?  </span> <p>选中此选项后，在此字段数据中找到的任何HTML标记都将被删除。 </p> </li> 
      <li id="li_6302D18971AD439FBECE27742649C56B"> <span class="uicontrol"> 操作 </span> <p>用于向映射中添加行或从映射中删除行。 行的顺序不重要。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. （可选）单击&#x200B;**[!UICONTROL Setup Maps]**&#x200B;下载数据源的示例。 检查数据是否适合索引。 此功能仅适用于文本和信息源类型。
1. （可选）单击&#x200B;**[!UICONTROL Preview]**&#x200B;以测试配置的实际工作情况。 此功能仅适用于文本和信息源类型。
1. 单击&#x200B;**[!UICONTROL Add]**&#x200B;将配置添加到[!DNL Index Connector Definitions]页面和[!DNL URL Entrypoints]页面的[!DNL Index Connector Configurations]下拉列表中。

   请参阅[关于URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。
1. 在[!DNL Index Connector Definitions]页面上，单击&#x200B;**[!UICONTROL rebuild your staged site index]**。
1. （可选）在[!DNL Index Connector Definitions]页面上，执行以下任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;还原您所做的任何更改。

      请参阅[使用History选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送阶段设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 编辑索引连接器定义 {#task_DCFC9C6A9964421DB5AB6C25DEE98DE9}

您可以编辑已定义的现有索引连接器。

>[!NOTE]
>
>并非所有选项都可供您更改，例如[!DNL Type]下拉列表中的“索引连接器名称”或“类型”。

**编辑索引连接器定义**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**。
1. 在[!DNL Index Connector]页面的[!DNL Actions]列标题下，单击&#x200B;**[!UICONTROL Edit]**&#x200B;以获取要更改其设置的索引连接器定义名称。
1. 在[!DNL Index Connector Edit]页面上，设置所需的选项。

   请参阅[添加索引连接器定义](../c-about-settings-menu/c-about-crawling-menu.md#task_96779B651A654E1F871F55D6DBBC8886)下的选项表。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）在[!DNL Index Connector Definitions]页面上，单击&#x200B;**[!UICONTROL rebuild your staged site index]**。
1. （可选）在[!DNL Index Connector Definitions]页面上，执行以下任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;还原您所做的任何更改。

      请参阅[使用History选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送阶段设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 查看索引连接器定义的设置 {#task_D0B71A7426E54247BDB3468EC576D871}

您可以查看现有索引连接器定义的配置设置。

将索引连接器定义添加到[!DNL Index Connector Definitions]页面后，便无法更改其类型设置。 您而是必须删除定义，然后添加新定义。

**查看索引连接器定义的设置**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**。
1. 在[!DNL Index Connector]页面的[!DNL Actions]列标题下，单击&#x200B;**[!UICONTROL Edit]**&#x200B;以查看或编辑其设置的索引连接器定义名称。

## 复制索引连接器定义 {#task_3AD55DF07FC44A748D0EFDAB7B35699B}

您可以复制现有索引连接器定义以用作要创建的新索引连接器的基础。

复制索引连接器定义时，默认情况下会禁用复制的定义。 要启用或“打开”定义，必须从[!DNL Index Connector Edit]页面对其进行编辑，然后选择&#x200B;**[!UICONTROL Enable]**。

请参阅[编辑索引连接器定义](../c-about-settings-menu/c-about-crawling-menu.md#task_DCFC9C6A9964421DB5AB6C25DEE98DE9)。

**复制索引连接器定义**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**。
1. 在[!DNL Index Connector]页面的[!DNL Actions]列标题下，单击&#x200B;**[!UICONTROL Copy]** ，以获取要复制其设置的索引连接器定义名称。
1. 在[!DNL Index Connector Copy]页面上，输入定义的新名称。
1. 单击 **[!UICONTROL Copy]**.
1. （可选）在[!DNL Index Connector Definitions]页面上，执行以下任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;还原您所做的任何更改。

      请参阅[使用History选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送阶段设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 重命名索引连接器定义 {#task_5132118FC21B47D99881E0ED425225D7}

可以更改现有索引连接器定义的名称。

重命名定义后，请检查&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**。 您希望确保新定义名称反映在[!DNL URL Entrypoints]页面的下拉列表中。

请参阅[添加要索引的多个URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)。

**重命名索引连接器定义**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**。
1. 在[!DNL Index Connector]页面的[!DNL Actions]列标题下，单击&#x200B;**[!UICONTROL Rename]**&#x200B;以获取要更改的索引连接器定义名称。
1. 在[!DNL Index Connector Rename]页面的[!DNL Name]字段中，输入定义的新名称。
1. 单击 **[!UICONTROL Rename]**.
1. 单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. 如果列表中存在以前的索引连接器名称，请将其删除，然后添加新重命名的条目。

   请参阅[添加要索引的多个URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)。 1. （可选）在[!DNL Index Connector Definitions]页面上，执行以下任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;还原您所做的任何更改。

      请参阅[使用History选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送阶段设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 删除索引连接器定义 {#task_6B0BD5D0C09F4597A401B0F3AC7C7EA7}

您可以删除不再需要或使用的现有索引连接器定义。

**删除索引连接器定义**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**。
1. 在[!DNL Index Connector Definitions]页面的[!DNL Actions]列标题下，单击&#x200B;**[!UICONTROL Delete]**&#x200B;以获取要删除的索引连接器定义名称。
1. 在[!DNL Index Connector Delete]页面上，单击&#x200B;**[!UICONTROL Delete]**。
