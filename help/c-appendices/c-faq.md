---
description: 'null'
seo-description: 'null'
seo-title: 常见问题解答
solution: Target
title: 常见问题解答
topic: Appendices,Site search and merchandising
uuid: 4ce454a4-e770-4587-91a0-a25491818ac6
translation-type: tm+mt
source-git-commit: 4270ea66ba645ad0f71c9c8b5c2a1fcc6eb02ad2

---


# 常见问题解答{#frequently-asked-questions}

## Adobe Flash {#reference_4A25BBDE32214AF5A1A454F38FD51243}

一个常见问题解答页，讨论对网站上SWF文件的索引和搜索的支持。

以下是有关SWF文件的常见问题：

* [何时对SWF文件进行爬网和索引？](#section_01BB5259140D4D5FB04CCB7A1A63DE99)
* [为SWF编制索引时，我该做什么……](#section_0A6A52CC70D4495BBE14D91906318F95)
* [如何识别SWF文件？](#section_B36C0536AB544F509601DC6A11A8E656)
* [如何索引SWF文件？](#section_36856058A4B54FA5ABF921344F50410C)
* [SWF文件算作页面吗？](#section_0158D6DE70BC40D78E2374787B9F58AB)
* [如何防止对单个SWF文件进行索引……](#section_E38AD37989EF410B97AF5125057BFD22)
* [如何防止SWF文件被索引到……](#section_DF2606A50E9A44859CFA0D44D7C5F2E4)
* [为什么我无法在我的网站上搜索中文、日文或韩文SWF文件？](#section_EE1A3A705AE74148BD195A0CE513A5C4)

## 何时对SWF文件进行爬网和索引？ {#section_01BB5259140D4D5FB04CCB7A1A63DE99}

如果SWF文件包含在HTML页面的embed或object标签中，则会对其进行爬网和索引，如下例所示：

```
<embed src="Flash-file-URL">  
 
<object>  
<param name=movie value="Flash-file-URL">  
</object> 
```

如果将文件URL列为入口点，也可以识别SWF文件。

请参 [阅添加要索引的多个URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)。

## 为SWF文件编制索引时，我必须做什么？ {#section_0A6A52CC70D4495BBE14D91906318F95}

要搜索和索引SWF文件，请选择内容类 **[!UICONTROL Adobe Flash Movies]** 型( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)。

只要Flash文件从HTML文档中的标 `<embed>``<object>` 签或标签引用，就会索引文本，并爬取文件中列出的所有URL。

如果文件未从标记或标 `<embed>` 记引用， `<object>` 则可以将SWF文件列在HTML文档的 `<a href=...>` 标记中或作为URL入口点。

请参 [阅添加要索引的多个URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)。

## 如何识别SWF文件？ {#section_B36C0536AB544F509601DC6A11A8E656}

SWF文件由以下MIME类型标识：

`application/x-shockwave-flash`

SWF文件也可以用“” `application/octet-stream`或 `text/plain` MIME类型进行识别，前提是文件扩展名为。swf。

配置错误的服务器可能对SWF文件使用不同的MIME类型。 如果搜索和索引SWF文件时遇到问题，请务必检查服务器配置。

## 如何索引SWF文件？ {#section_36856058A4B54FA5ABF921344F50410C}

SWF文件中包含的文本会像在封闭的HTML页 `<body>` 面中的文本一样索引。 如果搜索结果找到嵌入的SWF文件中包含的文本，则结果实际上会链接到包含该HTML页面，而不是SWF文件。 这样，SWF文件就会显示在正确的上下文中。

如果SWF文件包含URL作为“加载影片”动作，则引用的SWF文件中的文本将作为封闭HTML页的一部分进行索引。

如果SWF文件包含URL作为“Get URL”动作，则稍后将对URL进行爬网和索引，就像HTML引用在以后进行爬 `<a href=...>` 网和索引一样。

如果SWF文件作为URL入口点列出，则SWF文件文本将作为单页索引。 从入口点SWF中查找文本的搜索结果会直接链接到电影，而不是链接到封闭的HTML页。

请参 [阅添加要索引的多个URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)。

## SWF文件算作页面吗？ {#section_0158D6DE70BC40D78E2374787B9F58AB}

否. SWF文件被视为其封闭HTML页面的一部分。 SWF文件中包含的所有“加载电影”URL也被视为封闭的HTML页的一部分。 因此，从HTML页面引用的SWF文件不计为帐户的页面总数的“页面”。

如果SWF文件列为URL入口点，则该SWF文件和该SWF文件中列出的所有“加载电影”URL将计为帐户页面总数的一个“页面”。

## 如何防止为单个SWF文件编制索引？ {#section_E38AD37989EF410B97AF5125057BFD22}

要防止对SWF文件进行索引，可以向封闭的HTML文档添加robots meta标签( `<meta name="ROBOTS" content="NOINDEX">`) `<noindex>` 或标签。 即包含或标签的 `<embed>` 文 `<object>` 档。

您还可以使用robotmeta标签( `<meta name="ROBOTS" content="NOFOLLOW">`)来防止SWF文件中包含的以下URL。 如果封闭的HTML文档已禁用以下功能，则SWF文件中列为“获取URL”操作的URL将不跟随。

## 如何防止在我的网站上索引SWF文件？ {#section_DF2606A50E9A44859CFA0D44D7C5F2E4}

要禁用SWF索引，请取消选择内 **[!UICONTROL Adobe Flash Movies]** 容类型( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)。

您还可以选择使用 [!DNL URL Masks] 来禁用SWF文件的索引。

请参 [阅将URL蒙版添加到……的索引部分或非索引部分](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

要禁用SWF索引，请输入以下URL蒙版之一：

* `exclude *.swf` （如果您不使用正则表达式）
* `exclude regexp ^.*\.swf$` （如果您使用正则表达式）

请参阅 [正则表达式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

## 为什么我无法在我的网站上搜索中文、日文或韩文SWF文件？ {#section_EE1A3A705AE74148BD195A0CE513A5C4}

站点搜索／销售从使用Adobe Flash创建的SWF文件中获取UTF-8。 UTF-8不包含任何语言指示。 如果选择了内容类 **[!UICONTROL Adobe Flash Movies]** 型( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]****[!UICONTROL Content Types]**>)，则必须使用元数据注入指定SWF文件使用的语言。

请参 [阅添加字段注入定义](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

旧版SWF文件也不指定字符集。 如果选择了SWF内容类 **[!UICONTROL Adobe Flash Movies]** 型( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)，则必须使用元数据注入来指定在SWF文件中使用的字符集。

## 常规搜索 {#reference_E2C675162789452A9B99C6633B12CBEF}

一个常见问题解答页面，其中讨论了网站搜索／销售如何帮助访问您网站的客户找到他们正在寻找的内容。

以下是有关常规搜索的常见问题：

* [我是否必须安装任何软件才能使用站点……](#section_02AB2AFF71984F9DAA3AF2B7C0847A22)
* [当我的站点超出页面限制时会发生什么情况？](#section_ECA5FA01032D4322BABA4E2C7FE498C1)
* [如何更改每周……](#section_AE27F63DD13F425B940C8E7D9ED5C614)
* [我的客户信息在网站搜索／销售方面的安全性如何？](#section_5484CB954167412BB7F0480CB0C504B8)
* [我的客户信息的隐私权如何？](#section_8FB493F15E51454BA92A0C83E14C0CC7)
* [能否在搜索中显示自己的横幅广告……](#section_611EB8B32C16418386CB7DC7FB6954B8)

以下是与搜索功能有关的常见问题：

* [我是否可以为我的站点自定义搜索结果？](#section_A64B3A621B794DF78D35ED06D9C43D0B)
* [我能否看到客户在我的……](#section_73709E1B0E82478DA7B4D15B6C845F33)
* [如何控制哪些内容类型（PDF、文本、Flash、MP3和Microsoft Office）被索引和搜索？](#section_0AB8CB4B6BFA4286AA082055FEBFBE1C)
* [是否支持通过基于ASP、JSP、PHP、CFM或Perl的内容动态生成网页？](#section_E279F004F1C542A2B9773B832E7B013F)
* [如何使用同义词来改进搜索结果……](#section_E6E36E12514F4D7BAB01F8D1AB61D57B)
* [我是否可以控制搜索结果的顺序……](#section_C6361048502745779D9749A842C4C370)
* [我是否可以更改搜索结果页面的语言……](#section_6EE41DA8241247D48BBEB061A50599C5)
* [我是否可以在Adobe上拥有多个站点……](#section_AFA8825182094660A71EEC84B8329D6D)
* [是否可以搜索多个域？](#section_BFBB0E9861D942F095B56CF0A8F16596)
* [能否将我的站点细分为单独的部分，以便……](#section_52153A9DE9F9493B967A70583848B2A4)
* [如何排除我网站的某些部分……](#section_D452EDE153654EF398F4A87780C6D43B)
* [支持哪些字符集？](#section_A62A6F8F15804F968C77F2DEBDE8F8FD)
* [如果我更改或更新我的网站怎么办？](#section_489050E0EBC14D0594DBBAA0CCF4F6BA)
* [是否可以自动索引我的网站？](#section_9C7D41636238488691ECDFEE4D4E5103)
* [我在我的网站上使用密码。 我是否仍可以使用网站搜索／销售？](#section_4618EB5B66704640B5502D1B5CB4B32E)
* [您是否支持搜索和索引https或……](#section_D5BB8B8FBEA4405583E86B4AEC37151B)
* [站点search/merchandising是否遵守我网站上的robots.txt文件？](#section_73BBF6FE93C64C109F45CBC2FA394DB2)
* [我网站的某些部分必须经常更新，因此……](#section_6D2FB1DE1B8A49729F9CCAE2A2770AB3)
* [我是否可以使用脚本或程序来启动增量……](#section_0B6BB039557A42AA876D35D748E17DD0)

## 我是否必须安装任何软件才能使用站点搜索／销售？ {#section_02AB2AFF71984F9DAA3AF2B7C0847A22}

否. 这是网站搜索／销售的主要优势。 该引擎是一个专业应用程序，完全托管并维护在我们的高性能服务器上。 这使软件比其他搜索解决方案更易于使用。 您只需向页面添加少量HTML代码，这样网站的客户就可以输入搜索。 网站搜索／销售将负责其余所有工作。

## 当我的站点超出页面限制时会发生什么情况？ {#section_ECA5FA01032D4322BABA4E2C7FE498C1}

我们继续为您的搜索提供服务，以便您的访客可以无中断地搜索您的网站。 要查看您的网站是否超出页面限制，请查看“完整索引”状态或“实时日志”。

请参 [阅关于完整索引](../c-about-index-menu/c-about-full-index.md#concept_C69BD21863FD4856B49326F35DB570D3)。

请参 [阅查看实时或分阶段的完整索引日志……](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8).

## 如何更改发送每周报告的电子邮件地址？ {#section_AE27F63DD13F425B940C8E7D9ED5C614}

每周报告将发送给每个活动帐户的所有者。 您可以通过单击> **[!UICONTROL Settings]****[!UICONTROL My Profile]** >来更改电子邮件地址 **[!UICONTROL Personal Information]**。 如果您有多个活动的搜索帐户，则所有新闻稿都会发送到新地址。

请参 [阅配置您的个人用户信息](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6)。

## 我的客户信息在网站搜索／销售方面的安全性如何？ {#section_5484CB954167412BB7F0480CB0C504B8}

网站搜索／销售安全、快速、稳定且易于使用。 您不会被迫使用Cookie（但如果您愿意，您可以）来使用我们的产品，并且敏感信息（如密码）永远不会放在任何URL链接上，以后可以从您的浏览器中检索到这些链接。

## 我的客户信息的隐私权如何？ {#section_8FB493F15E51454BA92A0C83E14C0CC7}

Adobe致力于尊重其客户和访客的隐私。 请参阅Adobe隐 [私中心](https://www.adobe.com/privacy.html)。

## 能否在搜索结果页面上显示自己的横幅广告？ {#section_611EB8B32C16418386CB7DC7FB6954B8}

是. 您可以控制搜索结果的外观和内容。 在网站的搜索结果模板中，您可以创建指向您自己的横幅交换网络（如LinkExchange或SmartClicks）的链接。 访客点击的所有内容均正确计入您的横幅交换帐户。

## 我是否可以为我的站点自定义搜索结果？ {#section_A64B3A621B794DF78D35ED06D9C43D0B}

是. 这是网站搜索／销售的独家功能。 借助我们先进的模板技术和对HTML的一点了解，您可以准确地控制搜索结果的显示方式。

请参阅 [搜索模板标记](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

在您自己的服务器和网站搜索／销售服务器之间的过渡是完全无缝的，客户不可见的。 如果您不知道HTML，或者您没有时间创建自定义模板，您可以从Adobe的内部专业Web开发人员团队创建的各种极具吸引力的、随时可用的模板中进行选择。

## 能否查看客户在我的网站上搜索哪些内容？ {#section_73709E1B0E82478DA7B4D15B6C845F33}

是. 我们会保留过去两个月内访客在您的网站上进行搜索的搜索统计数据。 您可以随时在产品菜单的“报告”下查看这些统计数据。 搜索报告为您提供关于访客在您的网站上寻找哪些内容的重要信息。 您可以使用这些信息来改进设计或调整网站搜索／销售引擎以更好地为访客服务。

## 如何控制哪些内容类型（PDF、文本、Flash、MP3和Microsoft Office）被索引和搜索？ {#section_0AB8CB4B6BFA4286AA082055FEBFBE1C}

您可以轻松配置帐户，以启用或禁用在PDF文档、纯文本文档、Flash电影、MP3文件或Microsoft Office文档中找到的文本的索引和搜索功能。

这些设置在页面上受 [!DNL Staged Content Types] 控。

请参 [阅关于内容类型](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07)。

## 是否支持通过基于ASP、JSP、PHP、CFM或Perl的内容动态生成网页？ {#section_E279F004F1C542A2B9773B832E7B013F}

对静态或动态生成的HTML网页进行索引，包括从数据库或任何其他后端进程构建的页面。 由于浏览器看到的HTML代码已编制索引，因此只要这些后端架构导致HTML页面，您就可以在网站上使用站点搜索／推销。

搜索自动机从中指定的网站地址的第一页开始，对您的网站进行爬行 [!DNL Account Settings]，并跟踪页面之间的链接。

请参 [阅配置帐户设置](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

当搜索自动机对网站的所有页面进行爬行和索引时，您可以使用搜索引擎搜索您的网站。 换句话说，如果动态生成的文档被编入您的网站，并且其中包含来自其他页面的链接，则搜索机器人仍可以爬行并索引动态内容。

在对网站内容进行爬网和索引后，您网站的客户可以在索引内容中搜索信息。

## 如何使用同义词来改进网站的搜索结果？ {#section_E6E36E12514F4D7BAB01F8D1AB61D57B}

当您希望访客查找与其搜索查询相关的页面时，可以使用同义词。

例如，假定您的网站上有一个页面，其中包含要销售的产品的价目表。 但是，在检查网站搜索／销售提供的搜索报告后，您会发现客户在搜索中查找“成本”、“费用”、“费用”或“费用”一词。 这些词不会在搜索结果中显示您的价目表页面。 通过中 [!DNL Add Synonyms] 的功 [!DNL Dictionaries]能，您可以指定这些单词都是同义词，而且客户可以找到价目表，而不管他们使用哪个搜索词。

请参 [阅关于字典](../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034)。

## 我是否可以控制搜索结果的顺序？ {#section_C6361048502745779D9749A842C4C370}

是. 使用高级相关性界面，您可以控制为特定搜索查询返回的页面。 如果您希望确保客户在查询特定单词时看到特定页面，则此功能非常有用。

请参 [阅添加新的元标记字段](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。

## 我是否可以更改搜索结果页面的语言？ {#section_6EE41DA8241247D48BBEB061A50599C5}

是. 在允许您构建使用所选语言且与网站外观匹配的结果页面时，站点搜索／销售模板是灵活的。

模板由文本、标准HTML标记和特殊标记组合组成，这些标记定义为显示搜索结果。 当客户执行搜索时，搜索自动机读取模板，使用标准HTML标记输出文本，并基于特殊的模板标记插入结果链接。

请参阅 [搜索模板标记](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

如果要更改结果语言，可编辑模板上显示的英语文本。

请参 [阅编辑演示文稿或传输模板](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3)。

## 我是否可以在Adobe客户登录名中拥有多个站点？ {#section_AFA8825182094660A71EEC84B8329D6D}

是. 通过单次Adobe客户登录，您可以为许多不同的网站管理不同的搜索引擎。 选择并管理“帐户”下的帐户。

请参 [阅选择要使用的其他帐户](../c-about-accounts-menu.md#task_03C0FE918E2D44529CDC3B8DB75D1B26)。

## 是否可以搜索多个域？ {#section_BFBB0E9861D942F095B56CF0A8F16596}

是. 您可以使用配置访问多个域 [!DNL URL Entrypoints]。 为您拥有的其他域提供URL入口点。 请记住，您必须拥有对您不拥有的域进行索引的权限。

请参 [阅关于URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

## 我是否可以将我的站点细分为单独的部分，以便客户可以单独或整个站点搜索其中的任何区域？ {#section_52153A9DE9F9493B967A70583848B2A4}

是. “集合”功能让客户搜索网站的特定区域以快速找到其所寻找的内容。

请参阅 [关于集合](../c-about-settings-menu/c-about-searching-menu.md#concept_62E42ACE53D54EEE9273433B86259127)。

例如，客户可以搜索与产品销售信息相关的URL集合或与支持服务相关的URL集合。 您可以设置收藏集，以便您的客户能够看到收藏集的下拉列表或一组复选框。

## 如何从搜索中排除我网站的某些部分？ {#section_D452EDE153654EF398F4A87780C6D43B}

是. 指定URL蒙版，以确定要包含或排除在索引中的网站页面。 URL蒙版决定网站页面是否显示在搜索结果中。

请参阅 [关于URL蒙版](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164)。

请参阅 [关于URL蒙版脚本](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B)。

要防止搜索个别网页的某些部分，可以从索引中排除页面的某些部分。 在文本周围添加 `<noindex>` 和标 `</noindex>` 记。 如果要从搜索中排除导航文本，则此方法很有用。

## 支持哪些字符集？ {#section_A62A6F8F15804F968C77F2DEBDE8F8FD}

网页通常使用类似于以下内容的meta标签指定字符集：

`<META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=iso-8859-1">`

网站搜索／销售引擎使用目前因特网上使用的所有常用字符集对网页进行正确索引。 某些支持的字符集包括：

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>阿拉伯语(ISO-8859-6) </p> </td> 
   <td colname="col2"> <p>繁体中文；Big5) </p> </td> 
   <td colname="col3"> <p>日语(Shift_JIS) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>阿拉伯语(Windows-1256) </p> </td> 
   <td colname="col2"> <p>繁体中文；EUC-TW) </p> </td> 
   <td colname="col3"> <p>俄语(KOI8-R) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>波罗的语(ISO-8859-4) </p> </td> 
   <td colname="col2"> <p>西里尔语(ISO-8859-5) </p> </td> 
   <td colname="col3"> <p>南欧语(ISO-8859-3) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>波罗的语(Windows-1257) </p> </td> 
   <td colname="col2"> <p>西里尔语(Windows-1251) </p> </td> 
   <td colname="col3"> <p>土耳其语(ISO-8859-9) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中欧语言(ISO-8859-2) </p> </td> 
   <td colname="col2"> <p>希腊语(ISO-8859-7) </p> </td> 
   <td colname="col3"> <p>土耳其语(Windows-1254) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中欧语言(Windows-1250) </p> </td> 
   <td colname="col2"> <p>希腊语(Windows-1253) </p> </td> 
   <td colname="col3"> <p>Unicode(UTF-8) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中文(ISO-2022-CN) </p> </td> 
   <td colname="col2"> <p>希伯来语(ISO-8859-8) </p> </td> 
   <td colname="col3"> <p>US-ASCII(us-ascii) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中文(ISO-2022-CN-EXT) </p> </td> 
   <td colname="col2"> <p>希伯来语(Windows-1255) </p> </td> 
   <td colname="col3"> <p>西欧语(ISO-8859-1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中文(简体；EUC-CN) </p> </td> 
   <td colname="col2"> <p>日语(EUC-JP) </p> </td> 
   <td colname="col3"> <p>西欧语(ISO-8859-15) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中文(简体；GB2312) </p> </td> 
   <td colname="col2"> <p>日语(ISO-2022-JP) </p> </td> 
   <td colname="col3"> <p>西欧语言(Windows-1252) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中文(简体；GBK) </p> </td> 
   <td colname="col2"> <p>日语(ISO-2022-JP-1) </p> </td> 
   <td colname="col3"> <p>西欧语(x-mac-roman) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中文(简体；HZ-GB-2312) </p> </td> 
   <td colname="col2"> <p>日语(ISO-2022-JP-2) </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

请联系技术支持以询问有关以上未列出的字符集的信息。

## 如果我更改或更新我的网站怎么办？ {#section_489050E0EBC14D0594DBBAA0CCF4F6BA}

更改网站内容后，可以执行完整索引或增量索引。 网站搜索／销售下载和索引任何更改的网站内容。 索引构建完成后，您的客户可以搜索新内容。 您还可以计划在特定时间和特定日期对站点进行自动索引。

请参 [阅运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

请参 [阅运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

请参 [阅为实时网站设置完整索引计划](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0)。

请参 [阅设置实时网站的增量索引计划](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33)。

## 是否可以自动索引我的网站？ {#section_9C7D41636238488691ECDFEE4D4E5103}

是. 您可以每天计划站点的自动索引。

除了每日自动索引外，您还可以选择频繁更改其站点的部分，以增量方式索引。 在计划了自动索引的天数内，您可以控制索引的发生时间。 此外，您始终可以根据需要手动启动站点索引。

请参 [阅为实时网站设置完整索引计划](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0)。

请参 [阅设置实时网站的增量索引计划](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33)。

## 我在我的网站上使用密码。 我是否仍可以使用网站搜索／销售？ {#section_4618EB5B66704640B5502D1B5CB4B32E}

如果使用HTTP基本身份验证对网站的某些部分进行口令保护，则可指定站点搜索／销售可用于为站点编制索引的领域和口令。

请参 [阅为访问网站中需要的区域添加密码……](../c-about-settings-menu/c-about-crawling-menu.md#task_DED19D476FF04B48BB6456D5ECB8628A).

## 您是否支持搜索和索引https或安全服务器内容？ {#section_D5BB8B8FBEA4405583E86B4AEC37151B}

是. 您可以在安全服务器(https)上搜索内容并为其编制索引。

## 站点search/merchandising是否遵守我网站上的robots.txt文件？ {#section_73BBF6FE93C64C109F45CBC2FA394DB2}

是. 机器人排除协议符合要求。 搜索自动机检查robots.txt文件（如果它在您的网站上存在）。 如果您的robots.txt文件排除了搜索您的站点的所有机器人，则站点搜索／销售机器人也将被排除。 要仅允许站点搜索／销售自动机爬行您的站点，请将robots.txt文件的内容设置为：

```
User-agent: Atomz/1.0 
Disallow:
```

```
User-agent: * 
Disallow: /
```

您可以通过以下链接进一步了解Web机器人和机器人排除协议：

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

## 我网站的某些部分必须经常更新，以便我的客户获得最准确的搜索结果。 增量索引是否有助于解决此问题？ {#section_6D2FB1DE1B8A49729F9CCAE2A2770AB3}

是. 此方案是为便于网站搜索／销售而构建的增量索引功能。 增量索引的主要好处是它允许公司经常对网站中不断变化的部分进行动态索引。 此类功能可确保您以“最快”的准确度显示搜索结果。

请参 [阅运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

请参 [阅设置实时网站的增量索引计划](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33)。

## 是否支持从后端数据库（如产品目录或库存管理系统）动态生成的网页？ {#section_26896C556483457E879785E751583B16}

对静态或动态生成的HTML网页（包括从数据库构建的页面或任何其他后端进程）进行索引。 由于浏览器查看的HTML代码已编制索引，因此只要后端数据库信息生成HTML页，您就可以在网站上使用站点搜索／推销。

搜索自动机从中指定的网站地址的第一页开始，对您的网站进行爬行 [!DNL Account Settings]，并跟踪页面之间的链接。

请参 [阅配置帐户设置](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

当搜索自动机对网站的所有页面进行爬行和索引时，您可以使用搜索引擎搜索您的网站。 换句话说，如果动态生成的文档被编入您的网站，并且其中包含来自其他页面的链接，则搜索机器人仍可以爬行并索引动态数据库内容。

在对网站内容进行爬网和索引后，您网站的客户可以在索引内容中搜索信息。

您可以轻松地启用完整内容搜索，或者仅限于标题中的信息、元描述、元关键字文档标记或全部三个标记，或者更窄的基于主题的搜索。 使用元数据定义，您还可以在实际搜索结果中创建自定义显示字段，如产品图像。

请参 [阅添加新的元标记字段](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。

## 我是否可以使用脚本或程序来启动站点的增量索引？ {#section_0B6BB039557A42AA876D35D748E17DD0}

是. 您可以使用脚本或程序启动网站的增量索引，以及在内容发生更改或更新时ping服务器以索引站点。

请参阅 [关于脚本索引](../c-about-index-menu/c-about-scripted-index.md#concept_34F58D551BC04BFB8ADC294B9DA9199D)。

## 功能实现 {#reference_2D0C4A80B8D64051BA9694D562DCE663}

常见问题解答页面，讨论中的各种功能实现 [!DNL Search&Promote]。

以下是关于网站中功能实现的 [!DNL Search&Promote] 常见问题：

* [为什么我的商业规则没有运行？](#section_7FEB60383D8A4B11A60DFF9067274699)
* [为什么我在计划索引、启动索引时出错以及启动分阶段索引时遇到问题？](#section_E05758193DF5436784B0145839989F75)
* [我的索引大小限制超出了我允许的范围。 为什么会发生这种情况，我如何解决？](#section_12E7DA979C4C4B1D8A3A6415FC3DDA70)

## 为什么我的商业规则没有运行？ {#section_7FEB60383D8A4B11A60DFF9067274699}

在显示横幅时配置业务规则，或帮助确定显示的结果和顺序。 您还可以配置facet中项目的位置以及用于给定搜索的模板。
对业务规则重新排序以更改它们在演示文稿模板上运行的顺序。 商业规则按照定义的顺序运行；也就是说，一个规则的订单编号越高，它在该过程中运行得越晚，就超越了之前的规则。 要对规则重新排序，请在“业务规则”页面的表的“顺序”列中输入新编号。

See [About Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

## 为什么我在计划索引、启动索引时出错以及启动分阶段索引时遇到问题？ {#section_E05758193DF5436784B0145839989F75}

生成索引时，无论该索引是完整索引还是增量索引爬行状态信息都会实时显示。 例如，您可以查看开始时间、已用时间以及索引过程中发生的任何错误。 还会显示有关上一个索引状态的信息。 使用此信息可排除您遇到的任何索引编制错误。

有关计划索引的信息，请参 [阅设置实时网站的完整索引计划](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0) , [以及设置实时网站的增量索引计划](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33)。

有关启动分阶段索引的信息，请 [参阅运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D) 或 [运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

## 我的索引大小限制超出了我允许的范围。 为什么会发生这种情况，我如何解决？ {#section_12E7DA979C4C4B1D8A3A6415FC3DDA70}

网站可能会不断增长，并且随着时间推移，Search&amp;Promote会“发现”更多已添加的文档和网页。 最终，您的帐户可能会超出索引大小限制。在这种情况下，您可以考虑使用 **[!UICONTROL URL Mask]**。 此功能可从您不希望或不需要索引的索引搜索中隐藏文档和网页，从而缩小索引大小。 另一种选择是与技术支持部门联系，让帐户中的索引大小限制设置得更大。

请参阅 [关于URL蒙版](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164)。

如果不确定要做什么，应与技术支持联系。 可能有许多其他变量影响您的索引大小，如果进行了调整，这些变量也可能影响您帐户的计费。

## 国际 {#reference_F017C2968BFB446499EF1D3CE2CAC0FE}

一个常见问题解答页面，讨论了对超过19种语言（包括多字节亚洲语言，如简体中文和繁体中文）、日语和朝鲜语)的索引和搜索的支持。

以下是有关语言和字符集的常见问题：

* [用于控制搜索查询的字符集编码……](#section_DF2E8570AFC2480FA199FD26C941A22F)
* [仅搜索其编码与……编码匹配的页面](#section_9E544F3DB7DE41618DC1BC8224B32C5A)
* [搜索结果页面使用什么编码？](#section_DA68670F35D54EAABF7DBB010F4409BF)
* [我是否可以在Unicode、UTF-8、编码页面上使用站点搜索／销售？](#section_130997CB08934A13A5261D85CF88040C)
* [为什么我无法在我的网站上搜索中文、日文或韩文PDF文件？](#section_539AFF482F814D28B5929F683D2F2175)
* [为什么我无法在我的网站上搜索中文、日文或韩文SWF文件？](#section_9C0849528AFF4C10AA97A2C912992638)
* [为什么我无法在我的网站上搜索中文、日文或韩文Microsoft Office文件？](#section_6764BA6863AF492EBA9BE5CCC12CDD1F)
* [为什么我无法在我的网站上搜索中文、日文或韩文MP3文件？](#section_DB6D60CF46F94125BF4E54AF3036DBFC)
* [我需要做点特别的事……](#section_A8BA6DDD3A6048319D3530BCFD6DA1A5)
* [为什么在Netscape 4.7及更早版本下的搜索结果中显示中文、日文或韩文字体？](#section_DF42567063304F918D406AC76529DFB7)

## 什么控制搜索查询的字符集编码？ {#section_DF2E8570AFC2480FA199FD26C941A22F}

搜索帐户的“Web表单”部分包含用于向网站添加搜索功能的示例搜索表单。 如果查看此搜索表单代码，您可以找到与以下代码类似的行：

`<input type=hidden name="sp_f" value="iso-8859-1">`

此代码行告诉搜索引擎传入的查询采用iso-8859-1编码，这是西欧语言的常用编码。 您可以通过转到产品菜单并单击 **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** >来更改此设 **[!UICONTROL Personal Information]**&#x200B;置。 在页 [!DNL Personal Information] 面的下拉列表 **[!UICONTROL Character Encoding]** 中，选择新编码。

请参 [阅配置您的个人用户信息](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6)。

您还可以通过编辑搜索表单的行来手动更改网 `sp_f` 页上的编码值。 请记住， `sp_f` 搜索表单的值必须与显示该表单的页面的字符集编码匹配。

## 是否只搜索编码与搜索查询的编码匹配的页面？ {#section_9E544F3DB7DE41618DC1BC8224B32C5A}

默认情况下，否。 只要网站页面正确识别其字符集编码，即使页面使用多种编码，搜索查询的编码和页面的编码之间也会进行必要的转换。

## 搜索结果页面使用什么编码？ {#section_DA68670F35D54EAABF7DBB010F4409BF}

帐户的字符集编码决定了结果模板的默认编码。

请参 [阅配置您的个人用户信息](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6)。

您可以进一步了解如何在HTML模板中指定字符集。

请参阅 [搜索模板标记](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

## 我是否可以在Unicode、UTF-8、编码页面上使用站点搜索／销售？ {#section_130997CB08934A13A5261D85CF88040C}

是. 但是，Unicode字符集（如UTF-8）没有提供足够的信息来确定页面所用的语言。 要正确搜索这些页面，必须指定语言。 要确定文档语言，将按以下顺序处理信息：

* 服务器为文档提供的内容语言HTTP头。
* META元素(例如， `META HTTP-EQUIV="Content-Language" Content="ja_JP"`)在文档 `<HEAD>` 的一节中。

* 标记的LANG `<HTML>` 属性(例如 `<HTML LANG="ja_JP">`)。

如果您的服务器未配置为传送内容语言HTTP头，且您的文档既不包含语言META元素，也不包含标记的语言属性，则可以使用元数据注入来指定相应的语言。 `<HTML>`

请参 [阅添加字段注入定义](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

## 为什么我无法在我的网站上搜索中文、日文或韩文PDF文件？ {#section_539AFF482F814D28B5929F683D2F2175}

站点搜索／销售从Adobe PDF文件获得UTF-8，而不显示任何语言。 如果选择 **[!UICONTROL PDF Documents]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)，则必须使用元数据注入指定在PDF文件中使用的语言。

请参 [阅添加字段注入定义](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

## 为什么我无法在我的网站上搜索中文、日文或韩文SWF文件？ {#section_9C0849528AFF4C10AA97A2C912992638}

站点搜索／销售从使用Adobe Flash创建的Adobe Flash电影文件中获取UTF-8，而不显示语言。 如果选择了内容类 **[!UICONTROL Adobe Flash Movies]** 型( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]****[!UICONTROL Content Types]**>)，则必须使用元数据注入指定在SWF文件中使用的语言。

对于Flash版本4或更早版本的SWF文件，不指定文件中字符的字符集。 如果选择了内容类 **[!UICONTROL Adobe Flash Movies]** 型( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]****[!UICONTROL Content Types]**>)，则必须使用元数据注入来指定在SWF文件中使用的字符集。

请参 [阅添加字段注入定义](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

## 为什么我无法在我的网站上搜索中文、日文或韩文Microsoft Office文件？ {#section_6764BA6863AF492EBA9BE5CCC12CDD1F}

站点搜索／销售从Microsoft Office文件（Microsoft Word、Microsoft Excel和Microsoft PowerPoint）中获得UTF-8，而不显示任何语言。 如果选择了内容类 **[!UICONTROL Microsoft Office Files]** 型( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)，则必须使用元数据注入指定Microsoft Office文件中使用的语言。

请参 [阅添加字段注入定义](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

## 为什么我无法在我的网站上搜索中文、日文或韩文MP3文件？ {#section_DB6D60CF46F94125BF4E54AF3036DBFC}

如果选择内容类 **[!UICONTROL Text in MP3 Music Files]** 型( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]****[!UICONTROL Content Types]**>)，则必须使用元数据注入指定用于对MP3文件进行编码的字符集。

请参 [阅添加字段注入定义](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

## 我是否需要执行任何特殊操作才能在我的网站上获取正确的索引。txt文件？ {#section_A8BA6DDD3A6048319D3530BCFD6DA1A5}

如果选择了内容类 **[!UICONTROL Text Documents]** 型( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]****[!UICONTROL Content Types]**>)，则必须使用元数据注入来指定用于编码。txt文件的字符集。

请参 [阅添加字段注入定义](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

## 为什么在Netscape 4.7及更早版本下的搜索结果中显示中文、日文或韩文字体？ {#section_DF42567063304F918D406AC76529DFB7}

如果您的帐户使用默认模板、某个现成的模板或基于这些模板中的任何一个的模板，则可能包含将Arial或Helvetica指定为字体的字体标签。 例如，`<font face="arial, helvetica" size="+1">`。当使用Arial或Helvetica字体时，Netscape 4.7及早期版本不显示中文、日文或韩文字符。 删除 `face` 属性或将字体替换为更适合中文、日文或朝鲜语的字体。

## 页数少 {#reference_4344E3E3CB2948939860F8C078BD7773}

一个常见问题解答页面，它讨论与低索引页面计数相关的常见问题。

以下是关于低索引页面计数的常见问题：

* [你检查过索引日志了吗？](#section_D6626536DC3D40DDA4A1224F1CB276BF)
* [您的URL中是否有键入错误？](#section_BD2CEABC5D0F4A0DA38F3AD72ABBA676)
* [入口点网页是否包含指向其他页面的链接……](#section_1C2D6ED54E7249268B555D9DC33352B3)
* [是指向您网站上嵌入的其他页面的链接……](#section_EE34A67D60A844EBB0921C03544FF63E)
* [网页上的HTML标记是否位于……](#section_F31A2F5D2C284AC084158A5BD763DC5D)
* [您的……中是否有格式不正确的HTML注释标记？](#section_D1C39D79341845CB9C38579AABDF3A24)
* [网页是否包含指向其他页面的链接……](#section_F8082759184049AAA8FA6342C1F84389)
* [您是否正在为您的URL使用虚拟域服务……](#section_2861F09EA21A45E6B7E15F032739CDF3)
* [网页是否使用meta刷新标记？](#section_5A2F544C237C49B8B1A7FE0C45371C0D)
* [您的网页是否使用meta robots标签？](#section_36275A33DDFE4620BABA948F8A63DBD2)
* [您的网站是否使用机器人排除文件？](#section_BF7B663347814F58AD736066C86B7D25)

## 你检查过索引日志了吗？ {#section_D6626536DC3D40DDA4A1224F1CB276BF}

索引日志包含站点搜索／销售机器人在为您的网站建立索引时收集的详细信息。 日志包含已搜索的链接和遇到的错误的列表。 检查索引日志是确定网站上所有页面未编制索引的最佳起点。

请参 [阅查看实时或分阶段的完整索引日志……](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8).

请参 [阅查看实时或分阶段的增量索引日志……](../c-about-index-menu/c-about-incremental-index.md#task_E668E1F1240C476DAA1CA783DC728232).

## 您的URL中是否有键入错误？ {#section_BD2CEABC5D0F4A0DA38F3AD72ABBA676}

在HTML表单中键入长URL时，可能会引入一个或多个排版错误。 请记住，URL不应包含任何空格。 另外，请注意，某些Web服务器会以区分大小写的方式处理URL。

在产品菜单中，单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**。 在页 [!DNL Staged URL Entrypoints] 面中，验证以下内容：

* 您的URL中没有任何排版错误。
* URL中的字符均使用正确的大小写。
* URL中没有空格字符。

要测试URL入口点，请将URL复制并粘贴到Web浏览器中，以查看您的网站是否出现。 如果未显示，请再次检查以确保您的URL路径中没有出错。

请参 [阅关于URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

## 入口点网页是否包含指向您网站上其他页面的链接？ {#section_1C2D6ED54E7249268B555D9DC33352B3}

网站搜索／推销机器人像客户一样对网站进行爬行；通过跟踪页面之间的链接。 在搜索自动机能够查找并索引站点上的其他页面之前，入口点网页中必须存在链接。

请参 [阅添加要索引的多个URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)。

## 指向网站上其他页面的链接是否嵌入了JavaScript? {#section_EE34A67D60A844EBB0921C03544FF63E}

您可以在网站上使用复杂的导航技术，如滚动操作和菜单，它们使用JavaScript链接到其他页面。 但是，站点搜索／销售自动机无法遵循JavaScript中嵌入的链接。

您可以使用的一个解决方案是将指向其他页面的隐藏链接放入包含JavaScript的HTML中。 尽管您网站的客户看不到这些链接，但搜索自动机仍会查找和爬行这些链接。 您可以将隐藏标记放在页面底部的标记前 `</body>` 面。 它们可能如下所示：

```
<a href="/mydir/mypag1.html"></a> 
<a href="/mydir/mypag2.html"></a>
```

另一个解决方案是将网站上其他页面的URL列为要搜索和索引的入口点。 URL的开头 `https://` 如下所示：

```
https://www.mydomain.com/mydir/mypag1.html 
https://www.mydomain.com/mydir/mypag2.html
```

请参 [阅添加要索引的多个URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)。

## 网页上的HTML标记是否按无效顺序排列？ {#section_F31A2F5D2C284AC084158A5BD763DC5D}

HTML规范要求HTML文 `<html>`档中的 `<head>`、 `<body>` 和标记遵循特定序列。 所有网页中的标记必须具有以下序列：

```
<html> 
<head> 
...  
<i>head tags go here</i> ... 
</head> 
<body> 
...  
<i>body tags go here</i> ... 
</body> 
</html>
```

如果HTML标记顺序不正确，则站点搜索／销售自动机无法正确解析和索引网页。 以下是不在正确序列中的标记示例：

```
<body> 
<head> 
...  
<i>head tags are here</i> ... 
</head> 
...  
<i>body tags are here</i> ... 
</body>
```

在这种情况下，请将 `<html>`、 `<head>`和 `<body>` 标记放入网页的正确序列中。

## 网页中的HTML注释标签是否格式不正确？ {#section_D1C39D79341845CB9C38579AABDF3A24}

请确保仔细查看并更正网页中的任何无效HTML注释。

HTML规范要求HTML注释以字符开头， `<!--` 以字符结尾 `-->`。 很容易忽略格式不正确的注释，这些注释会导致网站搜索／销售自动机错误地解析网页上的标记。 格式不正确的注释可能导致站点搜索／销售机器人错过必须解析的其他重要标记。 注意网页中标记之 `<body>` 前的注释。

以下是格式正确的注释的示例：

`<!-- This HTML comment is OK. -->`

以下是格式不正确的注释示例：

```
<!- This HTML comment is improperly formed. -> 
<! This HTML comment is also improperly formed. >
```

## 网页是否包含指向其他域上的页面的链接？ {#section_F8082759184049AAA8FA6342C1F84389}

通常，网站可以由实际存在于具有不同域地址的Web服务器上的页面组成。 例如，如果您的主网站地址如下：

`https://www.mydomain.com/`

您的网站可能还在其他域上有页面，如：

`https://www.otherdomain.com/`

默认情况下，站点搜索／销售机器人不跟踪除主域之外的域上的链接。 但是，通过为搜索帐户设置其他入口点，您可以轻松地为多个域编制索引。

在产品菜单中，单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**。 添加站点的“主网站入口点”URL。 然后，将其他URL入口点添加到包含站点页面的任何其他域。 例如，您应将主URL入口点设置为：

`https://www.mydomain.com/`

并添加以下其他站点URL入口点：

`https://www.otherdomain.com/`

## 您是否在为URL使用虚拟域服务？ {#section_2861F09EA21A45E6B7E15F032739CDF3}

您可能使用虚拟域服务（有时称为“域重定向服务”）为客户提供更好的URL以访问您的网站。 例如，假设您网站的真实地址如下：

`https://www.myispdomain.com/~myname/mywebpages/`

但是，您使用虚拟域服务，以便客户能够通过以下地址访问您的站点：

`https://myname.adomain.com/`

或

`https://adomain.com/myname/`

默认情况下，站点搜索／销售机器人不跟踪除主域之外的域上的链接。 但是，通过为搜索帐户设置其他入口点，您可以轻松地为多个域编制索引。

在产品菜单中，单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**。 将“主网站URL入口点”添加到站点的虚拟域名。 然后，将其他入口点添加到网站实际所在的域。

例如，您应将主URL入口点设置为：

`https://myname.adomain.com/`

并添加以下其他网站URL入口点：

`https://www.myispdomain.com/~myname/mywebpages/`

## 网页是否使用meta刷新标记？ {#section_5A2F544C237C49B8B1A7FE0C45371C0D}

许多网站的首页在标记之间包含一个元刷新标 `<head>...</head>` 记，类似于以下内容：

`<meta http-equiv="Refresh" content="0;URL=https://www.adomain.com/apath/afile.html">`

在某些情况下，站点搜索／销售自动机无法通过元刷新URL来索引您网站的内容。 通过设置其他入口点，可轻松解决此问题。

在产品菜单中，单击 **[!UICONTROL Settings]** >搜索> **[!UICONTROL URL Entrypoints]**。 将另一个入口点添加到meta refresh标记的URL。

## 您的网页是否使用meta robots标签？ {#section_36275A33DDFE4620BABA948F8A63DBD2}

有时网页使用元机器人标签来控制定期尝试爬网的网络机器人。 元自动机标记显示在网 `<head>...</head>` 页的标记之间，其外观与以下标记类似：

`<meta name="robots" content="noindex, nofollow">`

由于网站搜索／推销机器人本身就是一个Web机器人，它会遵循元机器人标签的方向。 通过以这种方式排除其他机器人，您也排除站点搜索／销售机器人。

您可以通过以下链接进一步了解Web机器人和机器人排除协议：

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

删除或修改网页上要在网站上编制索引的元机器人标签。

## 您的网站是否使用机器人排除文件？ {#section_BF7B663347814F58AD736066C86B7D25}

有时，网站的页面名为robots.txt，该页面会排除所有或某些机器人进行爬行。 要查看您的网站是否有robots.txt文件，请在顶级域下查找它，如下所示：

`https://www.yourdomain.com/robots.txt`

robots.txt文件的内容与以下文本类似：

```
User-agent: * 
Disallow: /
```

由于站点搜索／推销机器人本身是一个Web机器人，它遵循robots.txt文件中的方向——它不包括站点搜索／推销机器人。 要解决此问题，请编辑robots排除文件(robots.txt)，以允许站点搜索／销售自动机按如下方式搜索和索引您的网站：

```
User-agent: Atomz/1.0 
Disallow: 
 
User-agent: * 
Disallow: /
```

## Microsoft Office {#reference_A85FCC8A96514A7584F4D2A8AC8111D1}

一个常见问题解答页面，讨论对网站上Microsoft® Office文件的索引和搜索的支持。

以下是与Microsoft Office文件有关的常见问题：

* [Microsoft Office文件中有哪些内容已编制索引？](#section_8681DADFCFE24B7787B1FC08D431EE28)
* [未在Microsoft Office文件中索引的内容……](#section_BD53BDABFDD94D7EB0E1F55EC18017BB)
* [Microsoft Office文件与HTML页面的索引方式如何不同……](#section_C104B44684F340549A6B9EB8F39EDDBB)
* [如何防止Microsoft Office文件被索引……](#section_FEBA71274CD14CB99731ADF982087F4C)

## Microsoft Office文件中有哪些内容已编制索引？ {#section_8681DADFCFE24B7787B1FC08D431EE28}

Microsoft Word文件、Microsoft Excel文件和Microsoft PowerPoint文件的完整内容已编制索引。

Microsoft Word文件的以下部分已编制索引：

* 标题
* 关键字
* 主题（说明）
* 基于文本的内容
* 指向其他文档的超链接

Microsoft Excel文件的以下部分已编制索引：

* 标题
* 关键字
* 主题（说明）
* 单元格中的文本
* 单元格中数字公式的值

Microsoft PowerPoint文件的以下部分已编制索引：

* 标题
* 关键字
* 主题（说明）
* 每张幻灯片上的文本

## Microsoft Office文件中没有哪些索引？ {#section_BD53BDABFDD94D7EB0E1F55EC18017BB}

包含在Microsoft Office文件中的图形或包含的图形中包含的任何文本均不会编制索引。 自定义属性定义不作为元数据编制索引。 特殊字段中的某些文本（如PowerPoint文件中的页眉和页脚）也不会编制索引。

## Microsoft Office文件与HTML页面的索引有何不同？ {#section_C104B44684F340549A6B9EB8F39EDDBB}

搜索机器人对Microsoft Office文件和HTML文件进行索引的不同之处在于，每个HTML文件都是一个单独的页面，而单个Microsoft Office文件可以代表数百个页面。 因此，在Microsoft Office文件中，每个页面都会作为搜索帐户下的单独页面计数。

## 如何防止在我的网站上索引Microsoft Office文件？ {#section_FEBA71274CD14CB99731ADF982087F4C}

如果不希望搜索自动机对Microsoft Office文件进行爬行和索引，请取消选择内容类 **[!UICONTROL Microsoft Office Files]** 型( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)。

您还可以使 [!DNL URL Masks] 用禁用Microsoft Office文件的索引。

输入以下URL蒙版：

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>如果您不使用正则表达式 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_DFEC911DA11C484C8E4671A0F00E1F88"> 
     <li id="li_2E50374E3869426B97353A5A8CBE09EC">exclude *.doc </li> 
     <li id="li_9089D11161524D90849CA88F703772B6">exclude *.xls </li> 
     <li id="li_7F6CFC6212E64C04AAF38E21A667C763">exclude *.ppt </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>如果您使用正则表达式 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_012A45C3EC04460EA09C0ECFB49A8FA9"> 
     <li id="li_0C239F0A536D465F85A98EBF7B6ADF27">排除regexp^。*\.doc$ </li> 
     <li id="li_9F91DA35A2A646ACAFF2BA37F9136E2A">排除regexp^。*\.xls$ </li> 
     <li id="li_9D768D9EA2DB44FBB00A1979E21672E2">排除regexp^。*\.ppt$ </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

请参 [阅将URL蒙版添加到……的索引部分或非索引部分](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

请参阅 [正则表达式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

## MP3 {#reference_7614250EE81C4EEFA43E57A6A74E83D7}

一个常见问题解答页面，讨论对网站上MP3音乐文件的索引和搜索的支持。

以下是有关MP3文件的常见问题。

* [何时对MP3文件进行爬网和索引？](#section_538EA1682C9C47E3A62640BB25D84C36)
* [我该做什么才能爬爬和索引……](#section_3CD794446E3545379C14E9F222118665)
* [如何识别MP3文件？](#section_230E7336965A424F96C5CCF1D3C2D103)
* [MP3文件中有哪些索引？](#section_E99D252B27CA4946AED3FCD3ABD8779D)
* [MP3文件是否计为页面？](#section_9910BEB6617D4D2090558CDF6C65D16B)
* [如何防止对单个MP3文件进行索引……](#section_C989DC1D3D3841B38F683A462195DC05)
* [如何防止对MP3文件进行索引？](#section_305D2B28D1124776B6DC0C62A17827C6)
* [为什么我无法在我的站点上搜索中文、日文或韩文MP3文件？](#section_06A48DA3F9E742CC93CC8B5CCD7382FA)

## 何时对MP3文件进行爬网和索引？ {#section_538EA1682C9C47E3A62640BB25D84C36}

MP3文件通过两种方式之一进行爬网和索引。 最常见的方法是从HTML文件中的锚点href标签中：

`<a href="MP3-file-URL"></a>`

第二种方法是输入MP3文件的URL作为URL入口点。

请参 [阅关于URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

## 我需要做什么才能爬动和索引站点上的MP3文件？ {#section_3CD794446E3545379C14E9F222118665}

要激活帐户的MP3搜索和索引，请在产品菜单上单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**。 在页面 [!DNL Staged Content Types] 上，选择 **[!UICONTROL Text in MP3 Music Files]**。

请参 [阅关于内容类型](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07)。

## 如何识别MP3文件？ {#section_230E7336965A424F96C5CCF1D3C2D103}

MP3文件的MIME类型是“audio/mpeg”，可以识别该文件。

## MP3文件中有哪些索引？ {#section_E99D252B27CA4946AED3FCD3ABD8779D}

MP3文件可以选择性地存储少量文本信息。 该信息可以包括专辑名称、艺术家姓名、歌名、歌曲流派、发行年份和评论。 此信息存储在文件最末端称为TAG的位置。 包含TAG信息的MP3文件通过以下方式编制索引：

* 歌曲标题的处理方式与HTML页面的标题相同。
* 该注释被视为为HTML页面定义的描述。
* 流派被视为为HTML页面定义的关键字。
* 艺术家姓名、专辑名称和发布年份被视为HTML文档的正文。

## MP3文件是否计为页面？ {#section_9910BEB6617D4D2090558CDF6C65D16B}

是的，在您的网站上搜索和索引的每个MP3文件计为一个页面。

## 如何防止为单个MP3文件编制索引？ {#section_C989DC1D3D3841B38F683A462195DC05}

在链接到MP3文件的锚点标签周围添加 `<nofollow>` 和标 `</nofollow>` 签。 搜索自动机不遵循这些标记之间的链接。

另一种方法是将MP3文件的URL添加为排除蒙版。

请参阅 [关于URL蒙版](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164)。

请参阅 [关于URL蒙版脚本](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B)。

## 如何防止对MP3文件进行索引？ {#section_305D2B28D1124776B6DC0C62A17827C6}

控制帐户MP3索引的最简单方法是取消选择页 **[!UICONTROL Text in MP3 Music Files]** 面上的 [!DNL Staged Content Types] 项。

请参 [阅选择要搜索和索引的内容类型](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8)。

您还可以使用URL蒙版功能按文件扩展名禁用MP3索引。 为此，请在产品菜单上单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**。 输入以下蒙版之一：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>如果您的帐户…… </p> </th> 
   <th colname="col2" class="entry"> <p>输入以下URL掩码 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>不使用正则表达式 </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> exclude *.mp3 </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用正则表达式 </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> 排除regexp^。*\.mp3$ </span> </p> </td> 
  </tr> 
 </tbody> 
</table>

请参阅 [正则表达式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

## 为什么我无法在我的站点上搜索中文、日文或韩文MP3文件？ {#section_06A48DA3F9E742CC93CC8B5CCD7382FA}

要搜索中文、日文或韩文MP3文件，请在产品菜单上单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]** > **[!UICONTROL Text in MP3 Music Files]**。 然后，单 **[!UICONTROL Settings]** 击> **[!UICONTROL Metadata]** > **[!UICONTROL Injections]**，并指定用于对MP3文件进行编码的字符集。

请参 [阅选择要搜索和索引的内容类型](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8)。

请参 [阅关于注射](../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5)。

## PDF {#reference_F127C4915A0D436DA34E5D75ABFBB21B}

常见问题解答页面讨论了在网站上对PDF文件进行索引和搜索的支持。

以下是有关PDF文件的常见问题：

* [在PDF文件中编制哪些内容的索引？](#section_62BFCD7158B44F2BB3B1864224B50174)
* [哪些内容在PDF文件中未编制索引？](#section_A14B353AE503408896BACBBF3F748FA0)
* [索引PDF文件如何计数？](#section_C35DE36A65D649BD8FF314E9EFD990A6)
* [搜索结果是否可显示PDF图标？](#section_829CE82CC3544502A13D27C4DB820189)
* [搜索结果能否链接到中的特定页面？](#section_A06E7F7017E6441E98209D288EE57BF6)
* [如何防止在上对PDF文件进行索引……](#section_96671419A822486AAC654D8DAD819940)
* [为什么我无法在我的网站上搜索中文、日文或韩文PDF文件？](#section_D41CA8EFCA0242EA8CF5F8F1924E4CD8)

## 在PDF文件中编制哪些内容的索引？ {#section_62BFCD7158B44F2BB3B1864224B50174}

PDF文件的完整内容已编制索引。 PDF文件的以下部分已编制索引：

* 标题
* 关键字
* 主题（说明）
* 基于文本的内容

## 哪些内容在PDF文件中未编制索引？ {#section_A14B353AE503408896BACBBF3F748FA0}

PDF目录、文件中的任何图形或包含的图形中的任何文本均不会编制索引。

## 索引PDF文件如何计数？ {#section_C35DE36A65D649BD8FF314E9EFD990A6}

将每个PDF文件（包括包含多个页面的PDF）计为一个文档。

## 搜索结果是否可显示PDF图标？ {#section_829CE82CC3544502A13D27C4DB820189}

是. 使用模 `<search-if-link-extension>` 板中的标签在搜索结果中包含PDF图标或其他图形或文本：

```
<search-results> 
  ... 
  <search-if-link-extension value=".pdf"> 
    <img src="/search/i/pdficon.gif"> 
  </search-if-link-extension> 
  ... 
</search-results>
```

PDF图标可帮助您的客户知道搜索结果链接到可能非常大的PDF文件。 对于通过调制解调器或移动设备访问您网站的客户来说，文件大小可能很重要。

## 搜索结果是否可以链接到PDF文件中的特定页面？ {#section_A06E7F7017E6441E98209D288EE57BF6}

是. 使用智能链接模板标签( `<search-smart-link>...</search-smart-link>`)，客户可以单击打开包含搜索结果的第一个PDF页面。

要使用智能链接，请将模 `<search-link>...</search-link>` 板搜索结果部分中的标记替换为标 `<search-smart-link>...</search-smart-link>` 记。 当客户单击智能链接标签生成的链接时，他们将转到与其搜索查询相关的第一个PDF页面。

>[!NOTE]
>
>要使用此功能，客户必须使用Adobe Acrobat或Adobe Acrobat Reader的最新版本，其中必须包括高亮显示插件和外部窗口处理程序(EWH)插件。 此外，他们的Web浏览器必须使用Adobe Acrobat插件for Netscape Navigator（您可以使用任何接受此Netscape Navigator插件的浏览器）或Acrobat ActiveX控件for Internet Explorer 4.0及更高版本。

请参阅 [搜索模板标记](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

## 如何防止在我的网站上对PDF文件进行索引？ {#section_96671419A822486AAC654D8DAD819940}

如果不希望搜索自动机对PDF文件进行爬行和索引，请取消选择内容类 **[!UICONTROL PDF Documents]** 型( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)。

您还可以选择使用 [!DNL URL Masks] 来禁用PDF索引。

请参 [阅将URL蒙版添加到……的索引部分或非索引部分](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

要禁用PDF索引，请输入以下URL蒙版之一：

* `exclude *.pdf` （如果您不使用正则表达式）
* `exclude regexp ^.*\.pdf$` （如果您使用正则表达式）

请参阅 [正则表达式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

## 为什么我无法在我的网站上搜索中文、日文或韩文PDF文件？ {#section_D41CA8EFCA0242EA8CF5F8F1924E4CD8}

站点搜索／销售从PDF文件获取UTF-8，而不显示语言。 如果选择了内容类 **[!UICONTROL PDF Documents]** 型( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]****[!UICONTROL Content Types]**>)，则必须使用元数据注入指定在PDF文件中使用的语言。

请参 [阅添加字段注入定义](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

## 页面过多 {#reference_48A748BC1ED14844ACAC2735C8388E8A}

常见问题解答页面，其中解释了索引器计数页面数量多于实际数量的部分原因以及每种情况下的解决方案。

如果您确定网站低于页面限制，但索引者告诉您已达到限制，则应查看这些常见问题和答案以了解可能的解决方案。

* [您检查过各种索引日志吗？](#section_C929BF9FDA6B4C9A9078C45AFE80EFE8)
* [CGI程序是否正在您的网站上编制索引？](#section_86ED8A641B3841EC80153B4F107548FD)
* [服务器是否启用了目录浏览？](#section_073C88EEE74F4CA0AD2C7145D4810B22)
* [您的网站上是否有论坛或新闻组？](#section_8DCB94F0850A41B9B2EA885F779E2F84)
* [您的网站上是否有PDF或Microsoft Office文件……](#section_455FC5438DF74E68AB9A31D359EAD4D9)
* [您有多个URL入口点？](#section_8C54AFD7DF56472A9364D516482B534C)
* [您是否已超出内部字节或时间限制……](#section_AE1BE61A58864FFE81F0BCEED2EBB15D)

## 您检查过各种索引日志吗？ {#section_C929BF9FDA6B4C9A9078C45AFE80EFE8}

索引日志包含由站点搜索／销售机器人在为您的网站建立索引时收集的详细信息。 日志包含所有已搜索链接和遇到的错误的列表。 检查索引日志是确定要索引哪些页面时最好开始的位置。

请参 [阅查看实时或分阶段的完整索引日志……](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8).

请参 [阅查看实时或分阶段的增量索引日志……](../c-about-index-menu/c-about-incremental-index.md#task_E668E1F1240C476DAA1CA783DC728232).

请参 [阅查看实时或……的脚本增量索引日志。](../c-about-index-menu/c-about-scripted-index.md#task_CBFCE9B9A87B4DF7A2A35A6E83DE93D7).

请参 [阅查看实时或分阶段的重新生成索引日志……](../c-about-index-menu/c-about-regenerate-index.md#task_61CE8F9E7BF84BA89A8D482B2106BB15).

请参 [阅查看实时网站或分阶段网站的重排索引日志](../c-about-index-menu/c-about-re-rank-index.md#task_3C76107DFAC1495FACD3ABB0A688208D)。

## CGI程序是否正在您的网站上编制索引？ {#section_86ED8A641B3841EC80153B4F107548FD}

CGI程序使用URL参数，这些参数有时会导致索引器抓取多个“假”URL。 如果网站搜索／销售正在读取您的CGI程序，并在其中使用CGI参数的URL后，可能有数倍的页面被搜索和索引，这对您的搜索索引无用。 典型CGI参数显示在带有或 `?` 字符的 `&` URL中。

您可以使用URL掩码功能遮住CGI程序的索引。 您可以遮住URL前缀或使用正则表达式遮住CGI脚本。

请参阅 [关于URL蒙版](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164)。

请参阅 [关于URL蒙版脚本](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B)。

请参阅 [正则表达式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

## 服务器是否启用了目录浏览？ {#section_073C88EEE74F4CA0AD2C7145D4810B22}

当Web服务器启用了目录浏览且给定目录中没有index.html文件时，访问该目录可显示该目录中的文件列表。 通常，页面顶部有链接，允许您通过单击、 **[!UICONTROL Name]****[!UICONTROL Last modified]****[!UICONTROL Size]**、等等按不同方式对列表排序。 通常，这些URL在站点搜索／销售索引日志中显示为URL，其中包含 `?M=A` 末尾字符。 站点搜索／销售索引器将这些链接作为链接跟踪，这会导致索引多个“假”URL。

通常，设计良好的网站要么在每个目录中都有索引文件，要么对于那些没有索引文件的目录禁用了目录浏览。 幸运的是，如果您无法更改页面或禁用服务器端的目录列表，有一种简单的方法可以遮住这些“假”URL。

要完成此任务，请单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**。 添加遮罩以遮住包含该字符的任何URL `?`。 您可以通过输入以下正则表达式掩码来执行此任务：

`exclude regexp ^.*\?.*$`

创建蒙版后，请确保重新为网站编制索引。

请参 [阅运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

请参 [阅运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

## 您的网站上是否有论坛或新闻组？ {#section_8DCB94F0850A41B9B2EA885F779E2F84}

如果论坛或新闻组正在您的网站上进行爬网，则它可能会遵循不同显示选项或排序选项的URL。 此行为意味着同一页面已多次索引。

通常，论坛或新闻组会自带搜索引擎。 在这种情况下，您可以使 [!DNL URL Masks] 用来从网站搜索／销售中遮住论坛。

在产品菜单中，单击 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**。 在页面 [!DNL Staged URL Masks] 上，通过将论坛的URL输入为排除URL蒙版来遮住论坛。

请参 [阅将URL蒙版添加到……的索引部分或非索引部分](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

创建蒙版后，请务必重新为网站编制索引。

请参 [阅运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

请参 [阅运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

## 您的网站上是否有PDF或Microsoft Office文件？ {#section_455FC5438DF74E68AB9A31D359EAD4D9}

如果您的网站上有PDF [!DNL Microsoft Office] 文件或文件，您可能会注意到，只有几个文件的索引大小会计入许多页面。 比文档索引更多页面的原因是，PDF或Microsoft Office文件中的每页被计为单独的页面。

在产品菜单中，单击 **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Index]**。 在页面 [!DNL Full Index] 上，选择 **[!UICONTROL Count All Pages]**，然后单击 **[!UICONTROL Full Index Now]** 以查看总页数。 如果不希望PDF文件或Microsoft Office文件编制索引，可以在 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** >下禁用此内容类型 **[!UICONTROL Content Types]**。

请参 [阅运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

请参 [阅关于内容类型](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07)。

## 您有多个URL入口点？ {#section_8C54AFD7DF56472A9364D516482B534C}

站点搜索／销售自动机开始在指定的URL入口点搜索，并跟踪指向该特定域中所有内容的所有找到的链接。 如果您指定了许多URL入口点，可能会搜索大量页面。

在附加域上的入口点文 `nofollow` 档的标题中使用Robots Exclusion Protocol的标签，如下所示：

```
<html> 
<head> 
<meta name="robots" content="nofollow"> 
</head>
```

上面的代码告知站点搜索／销售自动机为页面内容编制索引，但不要跟踪指向其他页面的链接。

您可以通过以下链接进一步了解Web机器人和机器人排除协议：

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

如果您无权访问其他域上的页面源，则可以删除多个URL入口点。 这样做有助于您仅将索引编制活动限制在您希望客户能够搜索其内容的那些域。

请参 [阅关于URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

## 您是否超出了网站搜索／销售的内部字节数或时间限制？ {#section_AE1BE61A58864FFE81F0BCEED2EBB15D}

检查帐户在“Full Index Status”屏幕上是否已达到其限制。 如果状态报告您的索引大于允许数量或超出允许数量，则您的网站将不会完全编制索引。 您可以更正此错误，以便获得正确的覆盖范围和网站页面计数。

为保护网站搜索／销售服务器，对字节和时间有内部限制。 只有在爬网文件非常大，或当站点搜索／销售尝试访问的服务器速度较慢时，才会达到这些限制。

如果达到时间限制，请确保您的服务器处于联机状态，并在以后再次尝试索引。 如果达到字节限制，请通过查看索引日志检查已搜索的文件。 它们超大吗？ 如果您看到其中任一消息，请与技术支持联系。
