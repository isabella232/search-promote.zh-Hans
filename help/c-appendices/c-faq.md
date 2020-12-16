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
workflow-type: tm+mt
source-wordcount: '8639'
ht-degree: 0%

---


# 常见问题解答{#frequently-asked-questions}

## AdobeFlash{#reference_4A25BBDE32214AF5A1A454F38FD51243}

一个常见问题页，讨论对网站上SWF文件的索引和搜索的支持。

以下是有关SWF文件的常见问题：

* [何时对SWF文件进行爬网和索引？](#section_01BB5259140D4D5FB04CCB7A1A63DE99)
* [为SWF编制索引时，我该做什么……](#section_0A6A52CC70D4495BBE14D91906318F95)
* [如何识别SWF文件？](#section_B36C0536AB544F509601DC6A11A8E656)
* [如何对SWF文件编制索引？](#section_36856058A4B54FA5ABF921344F50410C)
* [SWF文件是否计为页面？](#section_0158D6DE70BC40D78E2374787B9F58AB)
* [我如何防止为单个SWF文件编制索引……](#section_E38AD37989EF410B97AF5125057BFD22)
* [如何防止对SWF文件编制索引……](#section_DF2606A50E9A44859CFA0D44D7C5F2E4)
* [为什么我无法在我的网站上搜索中文、日文或韩文SWF文件？](#section_EE1A3A705AE74148BD195A0CE513A5C4)

## 何时对SWF文件进行爬网和索引？{#section_01BB5259140D4D5FB04CCB7A1A63DE99}

如果SWF文件包含在HTML页的embed或object标记中，则会对其进行爬网和索引，如下例所示：

```
<embed src="Flash-file-URL">  
 
<object>  
<param name=movie value="Flash-file-URL">  
</object> 
```

如果将文件URL列表为入口点，也会识别SWF文件。

请参阅[添加要索引的多个URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)。

## 为SWF文件编制索引时需要做什么？{#section_0A6A52CC70D4495BBE14D91906318F95}

要爬网和索引SWF文件，请选择内容类型&#x200B;**[!UICONTROL Adobe Flash Movies]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)。

只要Flash文件从HTML文档中的`<embed>`标记或`<object>`标记引用，就会为文本编制索引，并爬网文件中列出的所有URL。

如果文件未从`<embed>`标记或`<object>`标记引用，则可以将SWF文件列表到HTML文档的`<a href=...>`标记中或作为URL入口点。

请参阅[添加要索引的多个URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)。

## 如何识别SWF文件？{#section_B36C0536AB544F509601DC6A11A8E656}

SWF文件由以下MIME类型标识：

`application/x-shockwave-flash`

SWF文件也可以用`application/octet-stream`&quot;或`text/plain` MIME类型进行识别，前提是文件扩展名为。swf。

配置错误的服务器可能对SWF文件使用不同的MIME类型。 如果搜索和索引SWF文件时出现问题，请务必检查服务器配置。

## 如何对SWF文件编制索引？{#section_36856058A4B54FA5ABF921344F50410C}

SWF文件中包含的文本将作为封闭的HTML页中的`<body>`文本进行索引。 如果搜索结果找到嵌入的SWF文件中包含的文本，则结果实际链接到封闭的HTML页而不是SWF文件。 这样，SWF文件就会在正确的上下文中显示。

如果SWF文件包含URL作为“加载电影”动作，则引用的SWF文件中的文本将作为封闭HTML页的一部分进行索引。

如果SWF文件包含URL作为“Get URL”操作，则稍后将对URL进行爬网和索引，就像对HTML `<a href=...>`引用进行爬网和稍后索引一样。

如果SWF文件作为URL入口点列出，则SWF文件文本将作为单页索引。 从入口点SWF中查找文本的搜索结果直接链接到电影，而不是包含在外面的HTML页。

请参阅[添加要索引的多个URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)。

## SWF文件是否计为页面？{#section_0158D6DE70BC40D78E2374787B9F58AB}

否. SWF文件被视为其封闭HTML页的一部分。 SWF文件中包含的所有“加载电影”URL也作为封闭HTML页的一部分。 因此，从HTML页面引用的SWF文件不计为帐户的页面总数的“页面”。

如果SWF文件列为URL入口点，则该SWF文件和该SWF文件中列出的所有“加载电影”URL将计为帐户页面总数的一个“页面”。

## 如何防止为单个SWF文件编制索引？{#section_E38AD37989EF410B97AF5125057BFD22}

要防止对SWF文件进行索引，可向封闭的HTML文档添加robotmeta标签(`<meta name="ROBOTS" content="NOINDEX">`)或`<noindex>`标签。 即包含`<embed>`或`<object>`标记的文档。

您还可以使用robots meta标签(`<meta name="ROBOTS" content="NOFOLLOW">`)来阻止SWF文件中包含的以下URL。 如果封闭的HTML文档已禁用，则SWF文件中列为“获取URL”操作的URL将不被跟踪。

## 如何防止在我的网站上对SWF文件编制索引？{#section_DF2606A50E9A44859CFA0D44D7C5F2E4}

要禁用SWF索引，请取消选择内容类型&#x200B;**[!UICONTROL Adobe Flash Movies]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)。

您还可以选择使用[!DNL URL Masks]禁用SWF文件的索引。

请参阅[将URL蒙版添加到……的索引部分或非索引部分……](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1)。

要禁用SWF索引，请输入以下URL掩码之一：

* `exclude *.swf` (如果您不使用常规表达式)
* `exclude regexp ^.*\.swf$` (如果您使用常规表达式)

请参阅[常规表达式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

## 为什么我无法在我的网站上搜索中文、日文或韩文SWF文件？{#section_EE1A3A705AE74148BD195A0CE513A5C4}

站点搜索／销售从使用AdobeFlash创建的SWF文件中获取UTF-8。 UTF-8不包含任何语言指示。 如果选择了内容类型&#x200B;**[!UICONTROL Adobe Flash Movies]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)，则必须使用元数据注入指定SWF文件使用的语言。

请参阅[添加字段注入定义](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

旧版SWF文件也不指定字符集。 如果选择了SWF内容类型&#x200B;**[!UICONTROL Adobe Flash Movies]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)，则必须使用元数据注入指定在SWF文件中使用的字符集。

## 常规搜索{#reference_E2C675162789452A9B99C6633B12CBEF}

一个常见问题页面，讨论网站搜索／销售如何帮助访问您网站的客户找到他们正在寻找的内容。

以下是有关一般搜索的常见问题：

* [我是否必须安装任何软件才能使用站点……](#section_02AB2AFF71984F9DAA3AF2B7C0847A22)
* [当我的站点超出页面限制时会发生什么情况？](#section_ECA5FA01032D4322BABA4E2C7FE498C1)
* [如何更改每周的电子邮件地址……](#section_AE27F63DD13F425B940C8E7D9ED5C614)
* [我的客户信息在网站搜索／销售方面的安全性如何？](#section_5484CB954167412BB7F0480CB0C504B8)
* [我的客户信息的隐私如何？](#section_8FB493F15E51454BA92A0C83E14C0CC7)
* [能否在搜索中显示自己的横幅广告……](#section_611EB8B32C16418386CB7DC7FB6954B8)

以下是与搜索功能相关的常见问题：

* [能否为我的站点自定义搜索结果？](#section_A64B3A621B794DF78D35ED06D9C43D0B)
* [我能否看到客户在我的……](#section_73709E1B0E82478DA7B4D15B6C845F33)
* [如何控制哪些内容类型(PDF、文本、Flash、MP3和Microsoft Office)进行索引和搜索？](#section_0AB8CB4B6BFA4286AA082055FEBFBE1C)
* [是否支持通过基于ASP、JSP、PHP、CFM或Perl的内容动态生成网页？](#section_E279F004F1C542A2B9773B832E7B013F)
* [如何使用同义词来改进搜索结果……](#section_E6E36E12514F4D7BAB01F8D1AB61D57B)
* [我是否可以控制搜索结果的顺序……](#section_C6361048502745779D9749A842C4C370)
* [我是否可以更改搜索结果页面的语言……](#section_6EE41DA8241247D48BBEB061A50599C5)
* [我能在Adobe上有多个站点吗……](#section_AFA8825182094660A71EEC84B8329D6D)
* [能否搜索多个域？](#section_BFBB0E9861D942F095B56CF0A8F16596)
* [能否将我的站点细分为单独的部分……](#section_52153A9DE9F9493B967A70583848B2A4)
* [如何排除我网站的某些部分……](#section_D452EDE153654EF398F4A87780C6D43B)
* [支持哪些字符集？](#section_A62A6F8F15804F968C77F2DEBDE8F8FD)
* [如果我更改或更新我的网站怎么办？](#section_489050E0EBC14D0594DBBAA0CCF4F6BA)
* [能否自动为我的网站编制索引？](#section_9C7D41636238488691ECDFEE4D4E5103)
* [我在我的网站上使用密码。我是否仍可以使用网站搜索／销售？](#section_4618EB5B66704640B5502D1B5CB4B32E)
* [是否支持搜索和索引https或……](#section_D5BB8B8FBEA4405583E86B4AEC37151B)
* [站点搜索／销售是否遵守我网站上的robots.txt文件？](#section_73BBF6FE93C64C109F45CBC2FA394DB2)
* [网站的某些部分必须经常更新，因此……](#section_6D2FB1DE1B8A49729F9CCAE2A2770AB3)
* [我是否可以使用脚本或项目启动增量……](#section_0B6BB039557A42AA876D35D748E17DD0)

## 我是否必须安装任何软件才能使用网站搜索／销售？{#section_02AB2AFF71984F9DAA3AF2B7C0847A22}

否. 这是网站搜索／销售的主要优势。 该引擎是完全托管并维护在我们高性能服务器上的专业应用程序。 这使软件比其他搜索解决方案更易于使用。 您唯一需要做的就是向页面添加少量HTML代码，以便网站的客户可以输入搜索。 网站搜索／销售将处理所有其余事务。

## 当我的站点超出页面限制时会发生什么情况？{#section_ECA5FA01032D4322BABA4E2C7FE498C1}

我们继续为您的搜索提供服务，以便您的访客可以不间断地搜索您的网站。 要查看您的网站是否超出页面限制，请查看“完整索引”状态或“实时日志”。

请参阅[关于完整索引](../c-about-index-menu/c-about-full-index.md#concept_C69BD21863FD4856B49326F35DB570D3)。

请参阅[查看实时或暂存的完整索引日志……](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8)。

## 如何更改发送每周报告的电子邮件地址？{#section_AE27F63DD13F425B940C8E7D9ED5C614}

每周报告会发送给每个有效帐户的所有者。 单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]**&#x200B;可以更改电子邮件地址。 如果您有多个活动搜索帐户，则所有新闻稿都会发送到新地址。

请参阅[配置您的个人用户信息](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6)。

## 我的客户信息在网站搜索／销售方面的安全性如何？{#section_5484CB954167412BB7F0480CB0C504B8}

网站搜索／销售安全、快速、稳定且易于使用。 您不必使用cookies（尽管您可以使用）来使用我们的产品，并且敏感信息（如密码）永远不会放在任何URL链接上，以后可以从您的浏览器中检索到。

## 我的客户信息的隐私如何？{#section_8FB493F15E51454BA92A0C83E14C0CC7}

Adobe致力于尊重其客户和访客的隐私。 请参阅Adobe[隐私中心](https://www.adobe.com/privacy.html)。

## 能否在搜索结果页面上显示自己的横幅广告？{#section_611EB8B32C16418386CB7DC7FB6954B8}

是. 您可以控制搜索结果的外观和内容。 在网站的搜索结果模板中，您可以创建指向您自己的横幅交换网络（如LinkExchange或SmartClicks）的链接。 访客点击的任何内容均正确计入您的横幅交换帐户。

## 能否为我的站点自定义搜索结果？{#section_A64B3A621B794DF78D35ED06D9C43D0B}

是. 这是网站搜索／销售的独家功能。 借助我们先进的模板技术和对HTML的了解，您可以准确控制搜索结果的显示方式。

请参阅[搜索模板标记](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

您自己的服务器与网站搜索／销售服务器之间的过渡对客户而言是完全无缝和不可见的。 如果您不了解HTML或没有时间创建自定义模板，您可以从一系列有吸引力的、随时可用的模板中进行选择，这些模板是Adobe的内部专业Web开发人员团队创建的。

## 能否查看客户在我的网站上搜索的内容？{#section_73709E1B0E82478DA7B4D15B6C845F33}

是. 我们会对过去两个月来由访客在您的网站上进行的搜索进行搜索统计。 您可以随时在产品菜单的报告下查看这些统计信息。 搜索报告可为您提供与访客在您的网站上查找的内容相关的重要信息。 您可以使用这些信息来改进设计或调整网站搜索／销售引擎，从而更好地为访客服务。

## 如何控制哪些内容类型(PDF、文本、Flash、MP3和Microsoft Office)进行索引和搜索？{#section_0AB8CB4B6BFA4286AA082055FEBFBE1C}

您可以轻松配置帐户，以启用或禁用在PDF文档、纯文本文档、Flash电影、MP3文件或Microsoft Office文档中查找的文本的索引和搜索。

这些设置在[!DNL Staged Content Types]页面上进行控制。

请参阅[关于内容类型](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07)。

## 是否支持通过基于ASP、JSP、PHP、CFM或Perl的内容动态生成网页？{#section_E279F004F1C542A2B9773B832E7B013F}

对静态或动态生成的HTML网页进行索引，包括从数据库或任何其他后端流程构建的网页。 由于浏览器看到的HTML代码已编制索引，因此，只要这些后端架构导致HTML页面，您就可以在网站上使用站点搜索／推销。

搜索自动机从[!DNL Account Settings]中指定的网站地址的第一页开始爬网，并跟踪页面之间的链接。

请参阅[配置帐户设置](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

当搜索自动机对网站的所有页面进行爬网和索引时，您可以使用搜索引擎搜索您的网站。 换言之，如果动态生成的文档与来自其他页面的链接交织在您的网站中，搜索机器人仍可以爬行并索引动态内容。

在对网站内容进行爬网和索引后，您网站的客户可以在索引内容中搜索信息。

## 如何使用同义词来改进网站的搜索结果？{#section_E6E36E12514F4D7BAB01F8D1AB61D57B}

当您希望访客查找与其搜索查询相关的页面时，可以使用同义词。

例如，假定您的网站上有一个页面，其中包含要销售的产品的价格列表。 但是，在检查网站搜索／销售提供的搜索报告后，您会发现客户在搜索中查找“成本”、“费用”、“费用”或“费用”一词。 这些词不会在搜索结果中显示您的价格列表页。 使用[!DNL Dictionaries]中的[!DNL Add Synonyms]功能，您可以指定这些单词都是同义词，而且客户可以找到您的价格列表，无论他们使用哪个搜索词。

请参阅[关于字典](../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034)。

## 我是否可以控制搜索结果的顺序？{#section_C6361048502745779D9749A842C4C370}

是. 使用高级相关性界面，您可以控制为特定搜索查询返回的页面。 如果您希望确保客户在查询特定单词时看到特定页面，则此功能非常有用。

请参阅[添加新的元标记字段](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。

## 我是否可以更改搜索结果页面的语言？{#section_6EE41DA8241247D48BBEB061A50599C5}

是. 在允许您构建使用所选语言并匹配网站外观的结果页面时，站点搜索／销售模板是灵活的。

模板由文本、标准HTML标记和特殊标记组合组成，这些标记定义为显示搜索结果。 当客户执行搜索时，搜索自动机会读取模板，使用标准HTML标记输出文本，并基于特殊的模板标记插入结果链接。

请参阅[搜索模板标记](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

如果要更改结果语言，可以编辑模板上显示的英语文本。

请参阅[编辑演示文稿或传输模板](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3)。

## 我是否可以在Adobe客户登录中拥有多个站点？{#section_AFA8825182094660A71EEC84B8329D6D}

是. 通过单个Adobe客户登录，您可以为许多不同的网站管理不同的搜索引擎。 选择并管理“帐户”下的帐户。

请参阅[选择其他帐户以使用](../c-about-accounts-menu.md#task_03C0FE918E2D44529CDC3B8DB75D1B26)。

## 能否搜索多个域？{#section_BFBB0E9861D942F095B56CF0A8F16596}

是. 可以使用[!DNL URL Entrypoints]配置访问多个域。 为您拥有的其他域提供URL入口点。 请记住，您必须具有对您没有的域进行索引的权限。

请参阅[关于URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

## 能否将我的站点细分为单独的部分，以便客户可以单独或整个站点搜索其中的任何区域？{#section_52153A9DE9F9493B967A70583848B2A4}

是. “集合”功能让客户可以搜索网站的特定区域，快速找到所需内容。

请参阅[关于集合](../c-about-settings-menu/c-about-searching-menu.md#concept_62E42ACE53D54EEE9273433B86259127)。

例如，客户可以搜索与产品销售信息相关的URL集合或与支持服务相关的URL集合。 您可以设置收藏集，以便您的客户看到收藏集的下拉列表或一组复选框。

## 如何排除搜索网站的某些部分？{#section_D452EDE153654EF398F4A87780C6D43B}

是. 指定URL蒙版，以确定要包含或排除在索引中的网站页面。 URL蒙版决定网站页面是否显示在搜索结果中。

请参阅[关于URL掩码](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164)。

请参阅[关于URL掩码脚本](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B)。

要防止搜索单个网页的部分，可以从索引中排除页面的部分。 用`<noindex>`和`</noindex>`标记环绕文本。 如果要从搜索中排除导航文本，此方法很有用。

## 支持哪些字符集？{#section_A62A6F8F15804F968C77F2DEBDE8F8FD}

网页通常使用类似于以下内容的meta标签指定字符集：

`<META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=iso-8859-1">`

网站搜索／销售引擎使用目前因特网上使用的所有常用字符集对网页进行正确索引。 一些支持的字符集包括：

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>阿拉伯语(ISO-8859-6) </p> </td> 
   <td colname="col2"> <p>繁体中文；大5) </p> </td> 
   <td colname="col3"> <p>日语(Shift_JIS) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>阿拉伯语(Windows-1256) </p> </td> 
   <td colname="col2"> <p>繁体中文；EUC-TW) </p> </td> 
   <td colname="col3"> <p>俄语(KOI8-R) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>波罗的语(ISO-8859-4) </p> </td> 
   <td colname="col2"> <p>西里尔文(ISO-8859-5) </p> </td> 
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
   <td colname="col3"> <p>西欧语(Windows-1252) </p> </td> 
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

请与技术支持联系，询问有关以上未列出的字符集的信息。

## 如果我更改或更新我的网站怎么办？{#section_489050E0EBC14D0594DBBAA0CCF4F6BA}

更改网站内容后，可以执行完整索引或增量索引。 网站搜索／销售下载和索引任何更改的网站内容。 索引完成后，客户可以搜索新内容。 您还可以在特定时间和特定日期计划站点的自动索引。

请参阅[运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

请参阅[运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。

请参阅[设置实时网站的完整索引计划](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0)。

请参阅[设置实时网站的增量索引计划](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33)。

## 能否自动为我的网站编制索引？{#section_9C7D41636238488691ECDFEE4D4E5103}

是. 您可以每天计划站点的自动索引。

除了每日自动索引外，您还可以选择频繁更改其网站的某些部分，按增量索引。 计划自动索引的天数时，可以控制索引发生的时间。 此外，您始终可以根据需要手动启动站点索引。

请参阅[设置实时网站的完整索引计划](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0)。

请参阅[设置实时网站的增量索引计划](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33)。

## 我在我的网站上使用密码。 我是否仍可以使用网站搜索／销售？{#section_4618EB5B66704640B5502D1B5CB4B32E}

如果您使用HTTP基本身份验证对网站的某些部分进行口令保护，则可以指定网站搜索／销售可用来为网站编制索引的领域和口令。

请参阅[添加用于访问网站中需要的区域的口令……](../c-about-settings-menu/c-about-crawling-menu.md#task_DED19D476FF04B48BB6456D5ECB8628A)。

## 您支持搜索和索引https或安全服务器内容吗？{#section_D5BB8B8FBEA4405583E86B4AEC37151B}

是. 可以在安全服务器(https)上爬网和索引内容。

## 站点搜索／销售是否遵守我网站上的robots.txt文件？{#section_73BBF6FE93C64C109F45CBC2FA394DB2}

是. 机器人排除协议符合要求。 搜索robot会检查您的网站上是否存在robots.txt文件。 如果您的robots.txt文件排除了搜索您的站点的所有机器人，则站点搜索／销售机器人也将被排除。 要仅允许站点搜索／销售机器人爬网您的站点，请将robots.txt文件的内容设置为：

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

## 网站的某些部分必须经常更新，以便我们的客户获得最准确的搜索结果。 增量索引是否有助于解决此问题？{#section_6D2FB1DE1B8A49729F9CCAE2A2770AB3}

是. 此方案是为便于网站搜索／销售而构建的增量索引功能。 增量索引的主要优点是它允许公司经常对网站中不断变化的部分进行动态索引。 此类功能可确保您以“最快”的准确度显示搜索结果。

请参阅[运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。

请参阅[设置实时网站的增量索引计划](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33)。

## 是否支持从后端数据库动态生成的网页，如产品目录或库存管理系统？{#section_26896C556483457E879785E751583B16}

对静态或动态生成的HTML网页（包括从数据库构建的页面或任何其他后端进程）进行索引。 由于浏览器查看的HTML代码已编制索引，因此，只要后端数据库信息在HTML页中生成，您就可以在网站上使用站点搜索／销售。

搜索自动机从[!DNL Account Settings]中指定的网站地址的第一页开始爬网，并跟踪页面之间的链接。

请参阅[配置帐户设置](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

当搜索自动机对网站的所有页面进行爬网和索引时，您可以使用搜索引擎搜索您的网站。 换言之，如果动态生成的文档与来自其他页面的链接交织到您的网站中，搜索机器人仍可以爬行并索引动态数据库内容。

在对网站内容进行爬网和索引后，您网站的客户可以在索引内容中搜索信息。

您可以轻松启用完整内容搜索，或者仅限于标题中的信息、元描述、元关键字文档标签或全部三个信息的更窄的基于主题的搜索。 使用元数据定义，您还可以在实际搜索结果中创建自定义显示字段，如产品图像。

请参阅[添加新的元标记字段](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。

## 我是否可以使用脚本或项目来启动站点的增量索引？{#section_0B6BB039557A42AA876D35D748E17DD0}

是. 您可以使用脚本或项目启动网站的增量索引，并在内容发生更改或更新时ping服务器为站点编制索引。

请参阅[关于脚本索引](../c-about-index-menu/c-about-scripted-index.md#concept_34F58D551BC04BFB8ADC294B9DA9199D)。

## 功能实现{#reference_2D0C4A80B8D64051BA9694D562DCE663}

一个常见问题页，讨论[!DNL Search&Promote]中的各种功能实现。

以下是与网站[!DNL Search&Promote]中的功能实现相关的常见问题：

* [我的商业规则为什么没有运行？](#section_7FEB60383D8A4B11A60DFF9067274699)
* [为什么在编制索引时遇到问题、启动索引时出错以及启动分阶段索引时出现问题？](#section_E05758193DF5436784B0145839989F75)
* [我的索引大小限制超出了我允许的边界。为什么会发生这种情况，如何修复它？](#section_12E7DA979C4C4B1D8A3A6415FC3DDA70)

## 我的商业规则为什么没有运行？{#section_7FEB60383D8A4B11A60DFF9067274699}

在显示横幅时配置业务规则，或帮助确定显示结果和顺序。 您还可以配置facet中项目的位置以及用于给定搜索的模板。
对业务规则重新排序，以更改在演示文稿模板上运行的顺序。 商业规则按照定义的顺序运行；也就是说，一个规则的订单编号越高，它在该过程中运行得越晚，就超越了之前的规则。 要对规则进行重新排序，请在“业务规则”页的表的“顺序”列中输入新编号。

请参阅[关于Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD)。

## 为什么在编制索引时遇到问题、启动索引时出错以及启动分阶段索引时出现问题？{#section_E05758193DF5436784B0145839989F75}

生成索引时，无论该索引是完整索引还是增量索引爬网状态信息都会实时显示。 例如，您可以视图开始时间、已用时间以及在索引过程中发生的任何错误。 还会显示有关上一个索引状态的信息。 使用此信息可排除您遇到的任何索引错误。

有关计划索引，请参阅[设置实时网站的完整索引计划](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0)和[设置实时网站的增量索引计划](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33)。

有关启动分阶段索引的信息，请参阅[运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)或[正在运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。

## 我的索引大小限制超出了我允许的边界。 为什么会发生这种情况，我该如何解决？{#section_12E7DA979C4C4B1D8A3A6415FC3DDA70}

网站可能会不断增长，随着时间的推移，Search&amp;Promote会“发现”已添加的更多文档和网页。 最终，您的帐户可能会超出索引大小限制。在这种情况下，您可以考虑使用&#x200B;**[!UICONTROL URL Mask]**。 此功能可从您不希望或不需要索引的索引搜索中隐藏文档和网页，从而减小索引大小。 另一种选择是与技术支持联系，在您的帐户中设置更大的索引大小限制。

请参阅[关于URL掩码](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164)。

如果您不确定要做什么，应与技术支持联系。 可能还有许多其他变量影响索引大小，如果调整了这些变量，可能会影响帐户的计费。

## 国际{#reference_F017C2968BFB446499EF1D3CE2CAC0FE}

一个常见问题页，讨论对19种以上语言(包括多字节亚洲语言，如中文（简体和繁体）、日语和朝鲜语)的索引和搜索的支持。

以下是有关语言和字符集的常见问题：

* [控制搜索查询的字符集编码的内容……](#section_DF2E8570AFC2480FA199FD26C941A22F)
* [仅搜索其编码与……编码匹配的页面](#section_9E544F3DB7DE41618DC1BC8224B32C5A)
* [搜索结果页面使用什么编码？](#section_DA68670F35D54EAABF7DBB010F4409BF)
* [我是否可以在Unicode、UTF-8、编码页面上使用站点搜索／推销？](#section_130997CB08934A13A5261D85CF88040C)
* [为什么我无法在我的网站上搜索中文、日文或韩文PDF文件？](#section_539AFF482F814D28B5929F683D2F2175)
* [为什么我无法在我的网站上搜索中文、日文或韩文SWF文件？](#section_9C0849528AFF4C10AA97A2C912992638)
* [为什么我无法在我的网站上搜索中文、日文或韩文Microsoft Office文件？](#section_6764BA6863AF492EBA9BE5CCC12CDD1F)
* [为什么我无法在我的网站上搜索中文、日文或韩文MP3文件？](#section_DB6D60CF46F94125BF4E54AF3036DBFC)
* [我需要做点特别的事来……](#section_A8BA6DDD3A6048319D3530BCFD6DA1A5)
* [中文、日文或韩文字体如何在Netscape 4.7及更早版本的搜索结果中显示？](#section_DF42567063304F918D406AC76529DFB7)

## 什么控制搜索查询的字符集编码？{#section_DF2E8570AFC2480FA199FD26C941A22F}

搜索帐户的“Web 窗体”部分包含用于向网站添加搜索功能的示例搜索表单。 如果查看此搜索表单代码，您可以找到与以下代码类似的行：

`<input type=hidden name="sp_f" value="iso-8859-1">`

此代码行告诉搜索引擎传入的查询以iso-8859-1编码，这是西欧语言的常用编码。 您可以通过转到产品菜单并单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]**&#x200B;来更改此设置。 在[!DNL Personal Information]页面的&#x200B;**[!UICONTROL Character Encoding]**&#x200B;下拉列表中，选择新编码。

请参阅[配置您的个人用户信息](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6)。

您还可以通过编辑搜索表单的`sp_f`行手动更改网页上的编码值。 请记住，搜索表单的`sp_f`值必须与显示该表单的页面的字符集编码相匹配。

## 是否只搜索编码与搜索查询编码匹配的页面？{#section_9E544F3DB7DE41618DC1BC8224B32C5A}

默认情况下，不。 只要网站页面正确识别其字符集编码，即使页面使用多个编码，搜索查询的编码和页面的编码之间也会进行必要的转换。

## 搜索结果页面使用什么编码？{#section_DA68670F35D54EAABF7DBB010F4409BF}

帐户的字符集编码决定结果模板的默认编码。

请参阅[配置您的个人用户信息](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6)。

您可以进一步了解如何在HTML模板中指定字符集。

请参阅[搜索模板标记](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

## 我是否可以在Unicode、UTF-8、编码页面上使用站点搜索／推销？{#section_130997CB08934A13A5261D85CF88040C}

是. 但是，Unicode字符集（如UTF-8）不提供足够的信息来确定页面所用的语言。 要正确搜索这些页面，必须指定语言。 要确定文档语言，将按以下顺序处理信息：

* 服务器为文档提供的内容语言HTTP头。
* 文档`<HEAD>`部分中的META元素（例如`META HTTP-EQUIV="Content-Language" Content="ja_JP"`）。

* `<HTML>`标记的LANG属性（例如，`<HTML LANG="ja_JP">`）。

如果服务器未配置为传送内容语言HTTP头，且文档既不包含语言META元素，也不包含`<HTML>`标记的语言属性，则可以使用元数据注入来指定相应的语言。

请参阅[添加字段注入定义](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

## 为什么我无法在我的网站上搜索中文、日文或韩文PDF文件？{#section_539AFF482F814D28B5929F683D2F2175}

网站搜索／销售从Adobe PDF文件获取UTF-8，不显示任何语言。 如果选择&#x200B;**[!UICONTROL PDF Documents]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)，则必须使用元数据注入指定PDF文件中使用的语言。

请参阅[添加字段注入定义](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

## 为什么我无法在我的网站上搜索中文、日文或韩文SWF文件？{#section_9C0849528AFF4C10AA97A2C912992638}

站点搜索／销售从AdobeFlash电影文件中获取UTF-8，这些文件是使用AdobeFlash创建的，没有语言指示。 如果选择了内容类型&#x200B;**[!UICONTROL Adobe Flash Movies]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)，则必须使用元数据注入指定SWF文件中使用的语言。

对于Flash版本4或旧版SWF文件，不指定文件中字符的字符集。 如果选择了内容类型&#x200B;**[!UICONTROL Adobe Flash Movies]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)，则必须使用元数据注入指定SWF文件中使用的字符集。

请参阅[添加字段注入定义](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

## 为什么我无法在我的网站上搜索中文、日文或韩文Microsoft Office文件？{#section_6764BA6863AF492EBA9BE5CCC12CDD1F}

站点搜索／销售从Microsoft Office文件（Microsoft Word、Microsoft Excel和Microsoft PowerPoint）中获取UTF-8，而不显示任何语言。 如果您选择了内容类型&#x200B;**[!UICONTROL Microsoft Office Files]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)，则必须使用元数据注入指定Microsoft Office文件中使用的语言。

请参阅[添加字段注入定义](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

## 为什么我无法在我的网站上搜索中文、日文或韩文MP3文件？{#section_DB6D60CF46F94125BF4E54AF3036DBFC}

如果选择内容类型&#x200B;**[!UICONTROL Text in MP3 Music Files]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)，则必须使用元数据注入指定用于对MP3文件进行编码的字符集。

请参阅[添加字段注入定义](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

## 我是否需要执行任何特殊操作才能在我的网站上获取。txt文件以正确编制索引？{#section_A8BA6DDD3A6048319D3530BCFD6DA1A5}

如果选择了内容类型&#x200B;**[!UICONTROL Text Documents]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)，则必须使用元数据注入指定用于对。txt文件进行编码的字符集。

请参阅[添加字段注入定义](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

## 中文、日文或韩文字体如何在Netscape 4.7及更早版本的搜索结果中显示？{#section_DF42567063304F918D406AC76529DFB7}

如果您的帐户使用默认模板、一个随时可用的模板或基于这些模板中的任何一个的模板，则可能包含将Arial或Helvetica指定为字体的字体标签。 例如，`<font face="arial, helvetica" size="+1">`。当使用Arial或Helvetica字体时，Netscape 4.7及更早版本不显示中文、日文或韩文字符。 删除`face`属性，或将字体替换为更适合中文、日语或朝鲜语的字体。

## 页数低{#reference_4344E3E3CB2948939860F8C078BD7773}

一个常见问题页面，讨论与低索引页面计数相关的常见问题。

以下是关于低索引页面计数的常见问题：

* [你检查过索引日志吗？](#section_D6626536DC3D40DDA4A1224F1CB276BF)
* [您的URL中是否有键入错误？](#section_BD2CEABC5D0F4A0DA38F3AD72ABBA676)
* [入口点网页是否具有指向其他页面的链接……](#section_1C2D6ED54E7249268B555D9DC33352B3)
* [是指链接到您网站上嵌入的其他页面……](#section_EE34A67D60A844EBB0921C03544FF63E)
* [网页上的HTML标记是否位于……](#section_F31A2F5D2C284AC084158A5BD763DC5D)
* [您的HTML注释标记是否格式不正确……](#section_D1C39D79341845CB9C38579AABDF3A24)
* [网页是否包含指向其他网页的链接……](#section_F8082759184049AAA8FA6342C1F84389)
* [您是否正在为您的URL使用虚拟域服务……](#section_2861F09EA21A45E6B7E15F032739CDF3)
* [您的网页是否使用meta refresh标记？](#section_5A2F544C237C49B8B1A7FE0C45371C0D)
* [您的网页是否使用元机器人标签？](#section_36275A33DDFE4620BABA948F8A63DBD2)
* [您的网站是否使用机器人排除文件？](#section_BF7B663347814F58AD736066C86B7D25)

## 你检查过索引日志吗？{#section_D6626536DC3D40DDA4A1224F1CB276BF}

索引日志包含网站搜索／销售机器人在为网站编制索引时收集的详细信息。 日志包含已爬网的列表链接和遇到的错误。 检查索引日志是确定为何网站上的所有页面未编制索引的最佳开始位置。

请参阅[查看实时或暂存的完整索引日志……](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8)。

请参阅[查看实时或暂存的增量索引日志……](../c-about-index-menu/c-about-incremental-index.md#task_E668E1F1240C476DAA1CA783DC728232)。

## 您的URL中是否有键入错误？{#section_BD2CEABC5D0F4A0DA38F3AD72ABBA676}

在HTML表单中键入长URL时，可能会引入一个或多个排版错误。 请记住，URL不应包含任何空格。 另外，请注意，某些Web服务器会以区分大小写的方式处理URL。

在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**。 在[!DNL Staged URL Entrypoints]页面上，验证以下内容：

* 您的URL中没有任何排版错误。
* URL中的字符均使用正确的大写。
* URL中没有空格字符。

要测试URL入口点，请将URL复制并粘贴到Web浏览器中，以查看您的网站是否出现。 如果未显示，请再次检查以确保您的URL路径中没有出错。

请参阅[关于URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

## 入口点网页是否包含指向您网站上其他页面的链接？{#section_1C2D6ED54E7249268B555D9DC33352B3}

网站搜索／销售机器人像客户一样对您的网站进行爬网；通过跟踪页面之间的链接。 在搜索自动机能够查找并索引站点上的其他页面之前，入口点网页中必须存在链接。

请参阅[添加要索引的多个URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)。

## 网站上其他页面的链接是否嵌入到JavaScript中？{#section_EE34A67D60A844EBB0921C03544FF63E}

您可以在网站上使用复杂的导航技术，如滚动操作和菜单，这些技术使用JavaScript链接到其他页面。 但是，站点搜索／销售机器人无法遵循嵌入在JavaScript中的链接。

您可以用来解决此问题的一个解决方案是在包含JavaScript的HTML中放置到其他页面的隐藏链接。 尽管您网站的客户看不到这些链接，但搜索机器人仍会查找和爬网这些链接。 您可以将隐藏标记放置在页面底部的`</body>`标记之前。 它们可能如下所示：

```
<a href="/mydir/mypag1.html"></a> 
<a href="/mydir/mypag2.html"></a>
```

另一种解决方案是将网站上其他页面的URL列表为入口点进行爬网和索引。 URL以`https://`开头，如下所示：

```
https://www.mydomain.com/mydir/mypag1.html 
https://www.mydomain.com/mydir/mypag2.html
```

请参阅[添加要索引的多个URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)。

## 网页上的HTML标记是否顺序无效？{#section_F31A2F5D2C284AC084158A5BD763DC5D}

HTML规范要求`<html>`、`<head>`和`<body>`标签在HTML文档中遵循特定序列。 所有网页中的标记必须具有以下顺序：

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

如果HTML标记顺序不正确，则站点搜索／销售自动机无法正确解析和索引您的网页。 以下是不在正确序列中的标记示例：

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

在这种情况下，请将`<html>`、`<head>`和`<body>`标记放入网页的正确序列中。

## 网页中的HTML注释标记是否格式不正确？{#section_D1C39D79341845CB9C38579AABDF3A24}

请确保仔细查看并更正网页中的任何无效HTML注释。

HTML规范要求HTML注释以字符`<!--`开头，以字符`-->`结尾。 很容易忽略格式不正确的注释，这些注释会导致网站搜索／销售自动机不正确地分析网页上的标记。 格式不正确的注释可能导致网站搜索／销售机器人错过必须分析的其他重要标记。 请注意网页中`<body>`标记之前的注释。

以下是格式正确的注释的示例：

`<!-- This HTML comment is OK. -->`

以下是格式不正确的注释的示例：

```
<!- This HTML comment is improperly formed. -> 
<! This HTML comment is also improperly formed. >
```

## 网页是否包含指向其他域上的页面的链接？{#section_F8082759184049AAA8FA6342C1F84389}

通常，网站可以包含实际存在于具有不同域地址的Web服务器上的页面。 例如，如果您的主网站地址如下：

`https://www.mydomain.com/`

您的网站可能还在其他域上具有以下页面：

`https://www.otherdomain.com/`

默认情况下，站点搜索／销售机器人不跟踪除主域之外的域上的链接。 但是，通过为搜索帐户设置其他入口点，您可以轻松为多个域编制索引。

在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**。 添加您网站的“主网站入口点”URL。 然后，将其他URL入口点添加到包含网页的任何其他域。 例如，您应将主URL入口点设置为：

`https://www.mydomain.com/`

并添加以下其他站点URL入口点：

`https://www.otherdomain.com/`

## 您是否正在为您的URL使用虚拟域服务？{#section_2861F09EA21A45E6B7E15F032739CDF3}

您可能使用虚拟域服务（有时称为“域重定向服务”）为客户提供更好的URL以访问您的网站。 例如，假定网站的真实地址如下：

`https://www.myispdomain.com/~myname/mywebpages/`

但是，您使用虚拟域服务，以便客户可以通过以下地址访问您的站点：

`https://myname.adomain.com/`

或

`https://adomain.com/myname/`

默认情况下，站点搜索／销售机器人不跟踪除主域之外的域上的链接。 但是，通过为搜索帐户设置其他入口点，您可以轻松为多个域编制索引。

在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**。 将“主网站URL入口点”添加到站点的虚拟域名中。 然后，向网站实际所在的域添加其他入口点。

例如，您应将主URL入口点设置为：

`https://myname.adomain.com/`

并添加以下其他网站URL入口点：

`https://www.myispdomain.com/~myname/mywebpages/`

## 您的网页是否使用meta refresh标记？{#section_5A2F544C237C49B8B1A7FE0C45371C0D}

许多网站的首页中都包含`<head>...</head>`标记之间的元刷新标记，类似于：

`<meta http-equiv="Refresh" content="0;URL=https://www.adomain.com/apath/afile.html">`

在某些情况下，网站搜索／销售自动机无法使用元刷新URL为网站内容编制索引。 通过设置其他入口点，可轻松解决此问题。

在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** >搜索> **[!UICONTROL URL Entrypoints]**。 将另一个入口点添加到meta refresh标记的URL。

## 您的网页是否使用元机器人标签？{#section_36275A33DDFE4620BABA948F8A63DBD2}

有时网页会使用元机器人标签来控制定期尝试爬网的网站机器人。 元自动机标签显示在网页的`<head>...</head>`标签之间，与以下标签类似：

`<meta name="robots" content="noindex, nofollow">`

由于网站搜索／销售机器人本身就是一个网络机器人，它遵循元机器人标签的方向。 通过以这种方式排除其他机器人，您也排除站点搜索／销售机器人。

您可以通过以下链接进一步了解Web机器人和机器人排除协议：

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

删除或修改网页上要在网站上编制索引的元机器人标签。

## 您的网站是否使用机器人排除文件？{#section_BF7B663347814F58AD736066C86B7D25}

有时，网站的页面名为robots.txt，它排除所有或某些机器人搜索它。 要查看您的网站是否有robots.txt文件，请在顶级域下查找它，如下所示：

`https://www.yourdomain.com/robots.txt`

robots.txt文件的内容与以下文本类似：

```
User-agent: * 
Disallow: /
```

由于网站搜索／推销机器人本身就是一个Web机器人，它遵循robots.txt文件中的方向——它不包括网站搜索／推销机器人。 要解决此问题，请编辑robots排除文件(robots.txt)，以允许站点搜索／销售机器人按如下方式爬网和索引您的网站：

```
User-agent: Atomz/1.0 
Disallow: 
 
User-agent: * 
Disallow: /
```

## Microsoft Office {#reference_A85FCC8A96514A7584F4D2A8AC8111D1}

一个常见问题页，讨论对网站上Microsoft® Office文件的索引和搜索的支持。

以下是有关Microsoft Office文件的常见问题：

* [Microsoft Office文件中有哪些内容被索引？](#section_8681DADFCFE24B7787B1FC08D431EE28)
* [未在Microsoft Office文件中建立索引的内容……](#section_BD53BDABFDD94D7EB0E1F55EC18017BB)
* [Microsoft Office文件与HTML页面的索引方式如何不同……](#section_C104B44684F340549A6B9EB8F39EDDBB)
* [如何防止对Microsoft Office文件进行索引……](#section_FEBA71274CD14CB99731ADF982087F4C)

## Microsoft Office文件中有哪些内容被索引？{#section_8681DADFCFE24B7787B1FC08D431EE28}

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

## 哪些内容未在Microsoft Office文件中建立索引？{#section_BD53BDABFDD94D7EB0E1F55EC18017BB}

包含在Microsoft Office文件中的图形或包含图形中的任何文本都不会编制索引。 自定义属性定义不作为元数据进行索引。 特殊字段中的某些文本（如PowerPoint文件中的页眉和页脚）也不进行索引。

## Microsoft Office文件与HTML页面的索引方式有何不同？{#section_C104B44684F340549A6B9EB8F39EDDBB}

搜索机器人对Microsoft Office文件和HTML文件进行索引的不同之处在于，每个HTML文件都是一个单独的页面，单个Microsoft Office文件可以代表数百个页面。 因此，在Microsoft Office文件中，每个页面都计为搜索帐户下的单独页面。

## 如何防止在我的网站上对Microsoft Office文件编制索引？{#section_FEBA71274CD14CB99731ADF982087F4C}

如果不希望搜索自动机爬网和索引Microsoft Office文件，请取消选择内容类型&#x200B;**[!UICONTROL Microsoft Office Files]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)。

您还可以使用[!DNL URL Masks]禁用Microsoft Office文件的索引。

输入以下URL蒙版：

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>如果您不使用常规表达式 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_DFEC911DA11C484C8E4671A0F00E1F88"> 
     <li id="li_2E50374E3869426B97353A5A8CBE09EC">exclude *.doc </li> 
     <li id="li_9089D11161524D90849CA88F703772B6">exclude *.xls </li> 
     <li id="li_7F6CFC6212E64C04AAF38E21A667C763">exclude *.ppt </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>如果您使用常规表达式 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_012A45C3EC04460EA09C0ECFB49A8FA9"> 
     <li id="li_0C239F0A536D465F85A98EBF7B6ADF27">排除regexp ^。*\.doc$ </li> 
     <li id="li_9F91DA35A2A646ACAFF2BA37F9136E2A">排除regexp ^。*\.xls$ </li> 
     <li id="li_9D768D9EA2DB44FBB00A1979E21672E2">排除regexp ^。*\.ppt$ </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

请参阅[将URL蒙版添加到……的索引部分或非索引部分……](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1)。

请参阅[常规表达式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

## MP3 {#reference_7614250EE81C4EEFA43E57A6A74E83D7}

一个常见问题页，讨论对网站上MP3音乐文件的索引和搜索的支持。

以下是有关MP3文件的常见问题。

* [何时对MP3文件进行爬网和索引？](#section_538EA1682C9C47E3A62640BB25D84C36)
* [我该做什么来爬网和索引……](#section_3CD794446E3545379C14E9F222118665)
* [如何识别MP3文件？](#section_230E7336965A424F96C5CCF1D3C2D103)
* [MP3文件中有哪些索引？](#section_E99D252B27CA4946AED3FCD3ABD8779D)
* [MP3文件是否计为页面？](#section_9910BEB6617D4D2090558CDF6C65D16B)
* [如何防止为单个MP3文件编制索引……](#section_C989DC1D3D3841B38F683A462195DC05)
* [如何防止对MP3文件进行索引？](#section_305D2B28D1124776B6DC0C62A17827C6)
* [为什么无法在我的站点上搜索中文、日文或韩文MP3文件？](#section_06A48DA3F9E742CC93CC8B5CCD7382FA)

## 何时对MP3文件进行爬网和索引？{#section_538EA1682C9C47E3A62640BB25D84C36}

MP3文件通过两种方式之一进行爬网和索引。 最常见的方法是从HTML文件中的锚点href标签中：

`<a href="MP3-file-URL"></a>`

第二种方法是输入MP3文件的URL作为URL入口点。

请参阅[关于URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

## 要爬网和索引站点上的MP3文件，我必须做什么？{#section_3CD794446E3545379C14E9F222118665}

要激活帐户的MP3搜索和索引，请在产品菜单上单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**。 在[!DNL Staged Content Types]页面上，选择&#x200B;**[!UICONTROL Text in MP3 Music Files]**。

请参阅[关于内容类型](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07)。

## 如何识别MP3文件？{#section_230E7336965A424F96C5CCF1D3C2D103}

MP3文件的MIME类型是“audio/mpeg”。

## MP3文件中有哪些索引？{#section_E99D252B27CA4946AED3FCD3ABD8779D}

MP3文件可以选择性地存储少量文本信息。 该信息可包括专辑名称、艺术家姓名、歌名、歌曲流派、发行年份和评论。 此信息存储在文件末尾的称为TAG的地方。 包含TAG信息的MP3文件通过以下方式进行索引：

* 歌曲标题会被视为HTML页面的标题。
* 注释被视为为HTML页面定义的描述。
* 流派被视为为HTML页面定义的关键字。
* 艺术家姓名、专辑名称和发行年份被视为HTML文档的正文。

## MP3文件是否计为页面？{#section_9910BEB6617D4D2090558CDF6C65D16B}

是，在您的网站上爬网和编制索引的每个MP3文件计为一页。

## 如何防止为单个MP3文件编制索引？{#section_C989DC1D3D3841B38F683A462195DC05}

用`<nofollow>`和`</nofollow>`标记环绕链接到MP3文件的锚点标记。 搜索自动机不遵循这些标记之间的链接。

另一种方法是将MP3文件的URL添加为排除蒙版。

请参阅[关于URL掩码](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164)。

请参阅[关于URL掩码脚本](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B)。

## 如何防止对MP3文件进行索引？{#section_305D2B28D1124776B6DC0C62A17827C6}

控制帐户MP3索引的最简单方法是取消选择[!DNL Staged Content Types]页面上的&#x200B;**[!UICONTROL Text in MP3 Music Files]**。

请参阅[选择要爬网和索引的内容类型](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8)。

您还可以使用URL蒙版功能按文件扩展名禁用MP3索引。 为此，请在产品菜单上单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**。 输入以下蒙版之一：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>如果您的帐户…… </p> </th> 
   <th colname="col2" class="entry"> <p>输入以下URL掩码 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>不使用常规表达式 </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> exclude *.mp3  </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用常规表达式 </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> 排除regexp ^。*\.mp3$ </span> </p> </td> 
  </tr> 
 </tbody> 
</table>

请参阅[常规表达式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

## 为什么无法在我的站点上搜索中文、日文或韩文MP3文件？{#section_06A48DA3F9E742CC93CC8B5CCD7382FA}

要搜索中文、日文或韩文MP3文件，请在产品菜单上单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]** > **[!UICONTROL Text in MP3 Music Files]**。 然后，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]**，并指定用于对MP3文件进行编码的字符集。

请参阅[选择要爬网和索引的内容类型](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8)。

请参阅[关于Injections](../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5)。

## PDF {#reference_F127C4915A0D436DA34E5D75ABFBB21B}

常见问题解答页面讨论了在网站上对PDF文件进行索引和搜索的支持。

以下是有关PDF文件的常见问题：

* [PDF文件中哪些内容已编制索引？](#section_62BFCD7158B44F2BB3B1864224B50174)
* [哪些内容在PDF文件中未建立索引？](#section_A14B353AE503408896BACBBF3F748FA0)
* [索引PDF文件如何计数？](#section_C35DE36A65D649BD8FF314E9EFD990A6)
* [搜索结果能否显示PDF图标？](#section_829CE82CC3544502A13D27C4DB820189)
* [搜索结果能否链接到中的特定页面……](#section_A06E7F7017E6441E98209D288EE57BF6)
* [如何防止对PDF文件编制索引……](#section_96671419A822486AAC654D8DAD819940)
* [为什么我无法在我的网站上搜索中文、日文或韩文PDF文件？](#section_D41CA8EFCA0242EA8CF5F8F1924E4CD8)

## PDF文件中哪些内容已编制索引？{#section_62BFCD7158B44F2BB3B1864224B50174}

PDF文件的完整内容已编制索引。 PDF文件的以下部分已编制索引：

* 标题
* 关键字
* 主题（说明）
* 基于文本的内容

## 哪些内容在PDF文件中未建立索引？{#section_A14B353AE503408896BACBBF3F748FA0}

PDF目录、文件中的任何图形或包含图形的任何文本都不会编制索引。

## 索引PDF文件如何计数？{#section_C35DE36A65D649BD8FF314E9EFD990A6}

每个PDF文件（包括包含多个页面的PDF）计为一个文档。

## 搜索结果能否显示PDF图标？{#section_829CE82CC3544502A13D27C4DB820189}

是. 使用模板中的`<search-if-link-extension>`标签在搜索结果中加入PDF图标或其他图形或文本：

```
<search-results> 
  ... 
  <search-if-link-extension value=".pdf"> 
    <img src="/search/i/pdficon.gif"> 
  </search-if-link-extension> 
  ... 
</search-results>
```

PDF图标可帮助您的客户知道搜索结果链接到可能非常大的PDF文件。 通过调制解调器或移动设备访问您网站的客户可能需要文件大小。

## 搜索结果能否链接到PDF文件中的特定页面？{#section_A06E7F7017E6441E98209D288EE57BF6}

是. 使用智能链接模板标签(`<search-smart-link>...</search-smart-link>`)，客户可以单击打开包含搜索结果的第一个PDF页面。

要使用智能链接，请将模板的搜索结果部分中的`<search-link>...</search-link>`标记替换为`<search-smart-link>...</search-smart-link>`标记。 当客户单击智能链接标签生成的链接时，他们将转到与其搜索查询相关的第一个PDF页面。

>[!NOTE]
>
>要使用此功能，客户必须使用Adobe AcrobatReader(或Adobe Acrobat)的最新版本，其中必须包括突出显示插件和外部窗口处理程序(EWH)插件。 此外，其Web浏览器必须使用Netscape Navigator的Adobe Acrobat插件（您可以使用任何接受此Netscape Navigator插件的浏览器）或Internet Explorer 4.0及更高版本的AcrobatActiveX控件。

请参阅[搜索模板标记](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

## 如何防止在我的网站上对PDF文件编制索引？{#section_96671419A822486AAC654D8DAD819940}

如果不希望搜索自动机对PDF文件进行爬网和索引，请取消选择内容类型&#x200B;**[!UICONTROL PDF Documents]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)。

您还可以选择使用[!DNL URL Masks]禁用PDF索引。

请参阅[将URL蒙版添加到……的索引部分或非索引部分……](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1)。

要禁用PDF索引，请输入以下URL蒙版之一：

* `exclude *.pdf` (如果您不使用常规表达式)
* `exclude regexp ^.*\.pdf$` (如果您使用常规表达式)

请参阅[常规表达式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

## 为什么我无法在我的网站上搜索中文、日文或韩文PDF文件？{#section_D41CA8EFCA0242EA8CF5F8F1924E4CD8}

网站搜索／销售从PDF文件获取UTF-8，而不显示任何语言。 如果选择了内容类型&#x200B;**[!UICONTROL PDF Documents]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)，则必须使用元数据注入指定PDF文件中使用的语言。

请参阅[添加字段注入定义](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

## 页数{#reference_48A748BC1ED14844ACAC2735C8388E8A}太多

常见问题页，用于解释索引器计数页面数量多于实际数量的部分原因以及每种情况下的解决方案。

如果您确定网站低于页面限制，但索引器告诉您已达到限制，则应查看这些常见问题和答案以了解可能的解决方案。

* [你检查过各种索引日志吗？](#section_C929BF9FDA6B4C9A9078C45AFE80EFE8)
* [CGI项目是否正在您的网站上编制索引？](#section_86ED8A641B3841EC80153B4F107548FD)
* [服务器是否启用了目录浏览？](#section_073C88EEE74F4CA0AD2C7145D4810B22)
* [您的网站上是否有论坛或新闻组？](#section_8DCB94F0850A41B9B2EA885F779E2F84)
* [您的网站上是否有PDF或Microsoft Office文件……](#section_455FC5438DF74E68AB9A31D359EAD4D9)
* [您有多个URL入口点？](#section_8C54AFD7DF56472A9364D516482B534C)
* [是否已超出内部字节或时间限制……](#section_AE1BE61A58864FFE81F0BCEED2EBB15D)

## 你检查过各种索引日志吗？{#section_C929BF9FDA6B4C9A9078C45AFE80EFE8}

索引日志包含由站点搜索／销售机器人在对您的网站进行索引时收集的详细信息。 日志包含所有已爬网链接的列表，并且遇到错误。 检查索引日志是确定要索引哪些页面时开始的最佳位置。

请参阅[查看实时或暂存的完整索引日志……](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8)。

请参阅[查看实时或暂存的增量索引日志……](../c-about-index-menu/c-about-incremental-index.md#task_E668E1F1240C476DAA1CA783DC728232)。

请参阅[查看实时或的脚本增量索引日志……](../c-about-index-menu/c-about-scripted-index.md#task_CBFCE9B9A87B4DF7A2A35A6E83DE93D7)。

请参阅[查看实时或暂存的已重新生成索引日志……](../c-about-index-menu/c-about-regenerate-index.md#task_61CE8F9E7BF84BA89A8D482B2106BB15)。

请参阅[查看实时网站或分阶段网站的重新排名索引日志](../c-about-index-menu/c-about-re-rank-index.md#task_3C76107DFAC1495FACD3ABB0A688208D)。

## CGI项目是否正在您的网站上编制索引？{#section_86ED8A641B3841EC80153B4F107548FD}

CGI项目使用URL参数，这些参数有时会导致索引器爬网多个“假”URL。 如果网站搜索／推销正在读取您的CGI项目，并在其中使用CGI参数跟踪URL，则可能有好几倍的页面被爬网和索引，这对您的搜索索引来说并不有用。 典型CGI参数显示在字符数为`?`或`&`的URL中。

您可以使用URL掩码功能遮住CGI项目的索引。 您可以遮住URL前缀或使用常规表达式遮住CGI脚本。

请参阅[关于URL掩码](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164)。

请参阅[关于URL掩码脚本](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B)。

请参阅[常规表达式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

## 服务器是否启用了目录浏览？{#section_073C88EEE74F4CA0AD2C7145D4810B22}

当Web服务器启用了目录浏览并且给定目录中不存在index.html文件时，访问该目录可显示该目录中的文件列表。 通常，页面顶部有链接，您只需单击&#x200B;**[!UICONTROL Name]**、**[!UICONTROL Last modified]**、**[!UICONTROL Size]**&#x200B;等，即可按不同方式对列表进行排序。 通常，这些URL在站点搜索／销售索引日志中以URL的形式显示，末尾带有`?M=A`等字符。 网站搜索／销售索引器将这些链接作为链接，这会导致为多个“假”URL建立索引。

通常，设计良好的网站要么在每个目录中都有索引文件，要么对于那些没有索引文件的目录禁用了目录浏览。 幸运的是，如果您无法更改页面或禁用服务器端的目录列表，有一种简单的方法可以遮住这些“假”URL。

要完成此任务，请单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**。 添加一个遮罩以遮住包含字符`?`的任何URL。 您可以通过输入以下常规任务掩码来执行此表达式:

`exclude regexp ^.*\?.*$`

创建遮罩后，请确保重新为网站编制索引。

请参阅[运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

请参阅[运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。

## 您的网站上是否有论坛或新闻组？{#section_8DCB94F0850A41B9B2EA885F779E2F84}

如果论坛或新闻组正在您的网站上进行爬网，则可能会按照不同显示选项或排序选项的URL进行搜索。 此行为意味着同一页面被多次索引。

通常，论坛或新闻组会自带搜索引擎。 在这种情况下，您可以使用[!DNL URL Masks]从网站搜索／推销中遮住论坛。

在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**。 在[!DNL Staged URL Masks]页面上，通过将论坛的URL输入为排除的URL掩码来对其进行掩码。

请参阅[将URL蒙版添加到……的索引部分或非索引部分……](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1)。

创建蒙版后，请确保重新为网站编制索引。

请参阅[运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

请参阅[运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。

## 您的网站上是否有PDF或Microsoft Office文件？{#section_455FC5438DF74E68AB9A31D359EAD4D9}

如果您的网站上有PDF文件或[!DNL Microsoft Office]文件，您可能会注意到，仅几个文件的索引大小会计算很多页。 编入索引的页面数之所以比文档多，是因为PDF或Microsoft Office文件中的每个页面都计为单独的页面。

在产品菜单中，单击&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Index]**。 在[!DNL Full Index]页面上，选择&#x200B;**[!UICONTROL Count All Pages]**，然后单击&#x200B;**[!UICONTROL Full Index Now]**&#x200B;以查看总页数。 如果不希望对PDF文件或Microsoft Office文件建立索引，可在&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**&#x200B;下禁用此内容类型。

请参阅[运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

请参阅[关于内容类型](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07)。

## 您有多个URL入口点？{#section_8C54AFD7DF56472A9364D516482B534C}

站点搜索／推销自动机开始在指定的URL入口处搜索，并跟踪到该特定域中所有内容的所有找到的链接。 如果指定了许多URL入口点，可能会爬网大量页面。

在附加域的入口点文档的标头中使用Robots Exclusion Protocol的`nofollow`标签，如下所示：

```
<html> 
<head> 
<meta name="robots" content="nofollow"> 
</head>
```

上面的代码告诉网站搜索／销售自动机为页面内容编制索引，但不要跟踪指向其他页面的链接。

您可以通过以下链接进一步了解Web机器人和机器人排除协议：

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

如果您无权访问其他域上的页面源，则可以删除多个URL入口点。 这样做有助于您仅将索引活动限制在您希望客户能够搜索其内容的域。

请参阅[关于URL入口点](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

## 您是否超出了网站搜索／销售的内部字节数或时间限制？{#section_AE1BE61A58864FFE81F0BCEED2EBB15D}

检查帐户在“Full Index Status”屏幕上是否已达到其限制。 如果状态报告您的索引大于允许范围，或者花费的时间大于允许范围，则您的网站将没有完全编制索引。 您可以更正此错误，以获得正确的覆盖范围和网站页面计数。

为保护网站搜索／销售服务器，对字节和时间有内部限制。 只有当爬网的文件非常大，或者当站点搜索／推销尝试访问的服务器速度较慢时，才能达到这些限制。

如果达到某个时间限制，请确保服务器处于联机状态，稍后再次尝试索引。 如果达到字节限制，请通过查看索引日志检查已爬网的文件。 它们超大吗？ 如果您看到其中一条消息，请与技术支持联系。
