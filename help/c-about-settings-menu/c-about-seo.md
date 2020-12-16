---
description: 您可以使用SEO（搜索引擎优化）元标记来帮助定制页面的某些元素，从而改进搜索引擎的放置。
seo-description: 您可以使用SEO（搜索引擎优化）元标记来帮助定制页面的某些元素，从而改进搜索引擎的放置。
seo-title: 关于SEO
solution: Target
subtopic: SEO
title: 关于SEO
topic: Settings,Site search and merchandising
uuid: 5c5d64f5-fe79-4489-85c6-399d1437f2c4
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a
workflow-type: tm+mt
source-wordcount: '1226'
ht-degree: 1%

---


# 关于SEO{#about-seo}

您可以使用SEO（搜索引擎优化）元标记来帮助定制页面的某些元素，从而改进搜索引擎的放置。

## 使用SEO {#concept_C58BFCE720824A2B9B5F5E613CFD4C0B}

您可以将每个此类元素定义为一段开始文本，后跟一列表字。 单词列表可以包括：

* 在所选时间段（例如，“上个月”）内网站上的常用搜索短语，以自定义排除为前提。
* 页面所来自搜索的一个或多个字段的值集。
* 在列表中定义的静态单词和短语

人们用于SEO的最常用的页面元素是页面标题、“关键字”和“描述”元标记。 您可以定义这三个页面元素的设置。 此外，您还可以为三种类型的页面分别定义以下三种设置：搜索结果页面、浏览页面和项目详细信息页面。

在保存或预览SEO设置时，会生成搜索（传输）模板的小段，这些小段可以包含在具有`<search-include>`模板标记的其他搜索模板中。 例如，您可以将搜索结果页面标题字段包含到另一个模板中，其中包含以下内容：

```
<search-include file="seo/seo_search_title.tpl" />
```

SEO字段的`<search-include>`标记`file`属性的九个可能值如下：

* `seo/seo_search_title.tpl`
* `seo/seo_search_description.tpl`
* `seo/seo_search_keywords.tpl`
* `seo/seo_browse_title.tpl`
* `seo/seo_browse_description.tpl`
* `seo/seo_browse_keywords.tpl`
* `seo/seo_item_title.tpl`
* `seo/seo_item_description.tpl`
* `seo/seo_item_keywords.tpl`

要在演示文稿模板中使用SEO字段，请完成多个步骤。

首先，如上所述，使用`<search-include>`将所需字段包括在`<general>`元素中的XML搜索模板中。

然后，将每个`<search-include>`标记都包含`<general-field>`和`</general-field>`标记，如以下示例所示，在`name`属性中提供字段名称：

```
<general> 
    <general-field name="seo_search_title"><search-include file="seo/seo_search_title.tpl" /></general-field> 
    <general-field name="seo_search_description"><search-include file="seo/seo_search_description.tpl" /></general-field> 
    <general-field name="seo_search_keywords"><search-include file="seo/seo_search_keywords.tpl" /></general-field> 
</general>
```

然后，在演示文稿模板中，您可以使用`<guided-general-field>`标记在您需要时插入命名字段，如以下示例所示：

```
<title><guided-general-field gsname="default" field="seo_search_title"></title> 
<meta name="description" content="<guided-general-field gsname="default" field="seo_search_description">"/> 
<meta name="keywords" content="<guided-general-field gsname="default" field="seo_search_keywords">"/>
```

注意使用`gsname`属性指定“default”搜索。

您总共可以定义九个可在网页中使用的不同SEO字段。 包括：

* 搜索结果页面——标题、说明和关键字
* 浏览页面——标题、说明和关键字
* 项目详细信息页面——标题、说明和关键字

所有九个字段都使用类似设置进行定义。 事实上，九个字段的名称（如“搜索结果页面”中的“标题”字段）只是关于您如何使用这些字段的建议。 您可以在演示文稿模板和搜索模板中的任何上下文中使用任何字段。

另请参阅[关于模板](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5)。

另请参阅[演示文稿模板标记](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)。

另请参阅[搜索模板标记](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

另请参阅[配置搜索结果单词列表](../c-about-settings-menu/c-about-seo.md#task_A459A3734EC04042BA52C81184251DD4)。

## 配置搜索结果单词列表{#task_A459A3734EC04042BA52C81184251DD4}

您可以配置包含在页面标题、说明和关键字中的搜索结果单词和短语的列表。

**配置搜索结果单词列表**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Search Result Pages]**。
1. 在[!DNL SEO Browse Pages Word List]页面中，在相应的[!DNL Title]、[!DNL Description]和[!DNL Keywords]组中，设置所需的选项。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>标题 |说明 |关键字开始 </p> </td> 
      <td colname="col2"> <p>要在单词列表前面显示的文本。 </p> <p>例如，您可能希望关键字列表以单词“Brands”开头。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>在 </p> </td> 
      <td colname="col2"> <p>包含搜索的时间段。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最大搜索数 </p> </td> 
      <td colname="col2"> <p>包含的最大搜索数。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>包括字段值 </p> </td> 
      <td colname="col2"> <p>结果字列表中包含的字段值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>添加这些单词和短语 </p> </td> 
      <td colname="col2"> <p>列表要添加到搜索结果页面标题、浏览页面标题或项目详细信息页面标题的词。 </p> <p>单击<b>编辑</b>向列表添加单词。 </p> <p>每行可添加一个单词或短语。 完成后，单击<b>保存更改</b>，然后关闭页面以返回到主SEO页面。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>删除这些单词和短语（包括的字段值除外） </p> </td> 
      <td colname="col2"> <p>列表要从搜索结果页面标题、浏览页面标题或项目详细信息页面标题中删除的词。 </p> <p>单击<b>编辑</b>将单词添加到删除列表。 </p> <p>每行可添加一个单词或短语。 完成后，单击<b>保存更改</b>，然后关闭页面以返回到主SEO页面。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. （可选）单击&#x200B;**预览示例输出**&#x200B;以预览您设置的SEO字段的结果值。

   请参阅[预览您配置的SEO meta标记](../c-about-settings-menu/c-about-seo.md#task_3F97949E193C4F92A104AD117FE49621)。
1. 单击&#x200B;**保存更改**。
1. （可选）如果要预览结果，请重新构建分阶段站点索引。

   请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在[!DNL SEO Search Results Word List]页面上，执行下列任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;以还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 配置浏览页面单词列表{#task_D7A1D765A92A4D6C94E672B3A86ECB5A}

您可以配置浏览页面标题、说明和关键字中包含的字词和短语的列表。

**配置浏览页面单词列表**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Browse Pages]**。
1. 在[!DNL SEO Browse Pages Word List]页面中，在相应的[!DNL Title]、[!DNL Description]和[!DNL Keywords]组中，设置所需的选项。

   请参阅[配置搜索结果单词列表](../c-about-settings-menu/c-about-seo.md#task_A459A3734EC04042BA52C81184251DD4)下的选项表。
1. （可选）单击&#x200B;**预览示例输出**&#x200B;以预览您设置的SEO字段的结果值。

   请参阅[预览您配置的SEO meta标记](../c-about-settings-menu/c-about-seo.md#task_3F97949E193C4F92A104AD117FE49621)。
1. 单击&#x200B;**保存更改**。
1. （可选）如果要预览结果，请重新构建分阶段站点索引。

   请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在[!DNL SEO Browse Pages Word List]页面上，执行下列任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;以还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 配置项目详细信息字列表{#task_761538C519B34164BE189F13C39B2495}

您可以配置页面标题、说明和关键字中包含的项目详细信息单词和短语的列表。

**配置项目详细信息字列表**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Item Detail Pages]**。
1. 在[!DNL SEO Item Detail Word List]页面中，在相应的[!DNL Title]、[!DNL Description]和[!DNL Keywords]组中，设置所需的选项。

   请参阅[配置搜索结果单词列表](../c-about-settings-menu/c-about-seo.md#task_A459A3734EC04042BA52C81184251DD4)下的选项表。
1. （可选）单击&#x200B;**预览示例输出**&#x200B;以预览您设置的SEO字段的结果值。

   请参阅[预览您配置的SEO meta标记](../c-about-settings-menu/c-about-seo.md#task_3F97949E193C4F92A104AD117FE49621)。
1. 单击&#x200B;**保存更改**。
1. （可选）如果要预览结果，请重新构建分阶段站点索引。

   请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在[!DNL SEO Item Detail Word List]页面上，执行下列任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;以还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 预览您配置的{#task_3F97949E193C4F92A104AD117FE49621} SEO meta标记

您可以预览设置的SEO字段的结果值，以查看在何处插入了哪些内容。

SEO字段可以包含包含的字段值，因此搜索结果可能取决于您指定的搜索查询。

**预览您配置的SEO meta标记**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Search Result Pages]**。
1. 在SEO页上，单击&#x200B;**预览示例输出**。
1. 在[!DNL SEO Preview]页面的[!DNL Enter sample query]字段中，键入要搜索的查询词。
1.  单击&#x200B;**搜索**。

   生成的标题、描述和关键字字段会根据您刚刚输入的搜索查询显示插入到页面中的内容。
1. 单击&#x200B;**关闭**&#x200B;以返回主SEO页。
