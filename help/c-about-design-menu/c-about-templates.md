---
description: 您可以使用模板来管理您的演示文稿模板和传输模板。
seo-description: 您可以使用模板来管理您的演示文稿模板和传输模板。
seo-title: 关于模板
solution: Target
title: 关于模板
topic: Design,Site search and merchandising
uuid: f5805d3e-43bf-4e13-95df-b6bd6b762d11
translation-type: tm+mt
source-git-commit: 60cedaac1846e384a37699a42bf7fda33828e1c0

---


# 关于模板{#about-templates}

您可以使用 **[!UICONTROL Templates]** 来管理演示文稿模板和传输模板。

## 关于模板 {#concept_06EB481B14864E18A8AE2BCD1D6EF0B5}

<!-- 

c_about_templates.xml

 -->

您可以添加、编辑、复制、重命名或删除演示文稿模板和传输模板。 单击“模板”(Templates)表中的现有模板名称后，该模板将在编辑器（或查看器）窗口中打开，您可以在该窗口中进行更改。

您可以使用“模板”(Templates)表格中模板名称的下拉列表中的“历史记录”(History)功能还原您对模板所做的任何更改。

您可以通过选中模板表中模板的相应复选框来降低演示文稿模 **[!UICONTROL Minimize]** 板的页面粗细。 通过减少模板的页面粗细，可动态地最小化内联JavaScript和CSS。 您还可以删除HTML中的多余空白。 最小化演示文稿模板的页面粗细有助于更快地交付搜索结果。

通过单击文件名旁边的下拉列表，然后单击，可预览最小化的模板的外观 **[!UICONTROL Preview minimized]**。 如果最小化主演示文稿模板，请确保记住为包含的（带有标记）模板启用最小化，因为 `guided-include` 此选项不可继承。

即使您最小化了演示文稿模板，您仍然可以编辑同一模板的“未最小化”版本。

您可以使用搜索前规则、搜索后规则和业务规则确定何时使用其他演示模板。 通常有一个规则，如“对于每次搜索，将目标模板设置为xxxx”。 在实施此类规则后，当您在“模板”表中更改“默认”模板时，它似乎不起作用。

See [About Pre-Search Rules](../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F).

See [About Post-Search Rules](../c-about-rules-menu/c-about-post-search-rules.md#concept_AF6ADFCC0ADF4A788003964939917FDE).

See [About Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

## 关于演示文稿模板 {#section_ACDDEA5C499E481C828A517C230D4596}

演示文稿模板是客户在您的网站上查看搜索结果时看到的HTML模板。

在表示层中，您可以有一个表示模板，用于显示来自不同来源的多个搜索的结果。 您可以根据需要定义任意数量的演示文稿模板，甚至可以使用命令定义其他模板共享的演示文稿 `include` 模板。 演示文稿模板是所有设计组件（如彩块化、菜单和痕迹导航）汇集在一起的地方。 要显示各种设计组件，必须使用演示文稿模板标记。

请参阅演 [示文稿模板标记](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)

当您有多个演示文稿模板时，您可以在何种条件下定义使用各种演示文稿模板。 您可以根据传入的CGI参数和cookies选择要使用的演示模板。 或者，您可以根据之前搜索的结果切换您使用的演示文稿模板。

使用多个演示文稿模板时，请务必指明最初希望显示搜索结果的模板。 您可以使用“模板”(Templates) **[!UICONTROL Default]** 表格的列执行此操作。

## 关于传输模板 {#section_35FD3E8AAA4E4695A737DB7E00C3258B}

传输模板可以是XML或JSON模板，它们将数据从后端搜索传递到“向导式搜索”表示层。

默认情况下，您的帐户配置为使用XML传输模板。 但是，如果您希望使用JSON将数据传递到引导搜索，请与可以为您提供协助的Adobe Consulting联系。

在表示层中，您可以有一个表示多个搜索结果的表示模板。 每个搜索都可以使用相同的传输模板或自定义传输模板将数据传递到表示层。 由于传输模板仅用于向表示层传递数据，因此它不得有任何用于显示搜索结果的HTML。 模板使用传输模板标记传递搜索结果和结果以填充彩块化。 在这些标记中，标准搜索模板标记用于显示实际值。

请参阅 [搜索模板标记](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

**特定于XML传输模板的标签**

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>XML传输模板标签 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-xml&gt;&lt;/guided-xml&gt; </span> </p> </td> 
   <td colname="col2"> <p>这些是表示层用来检测其必须从传输模板中解析的内容的根XML标签。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;general&gt;&lt;&lt;general&gt; </span> </p> </td> 
   <td colname="col2"> <p>搜索模板标记周围有这组标记，这些标记根据结果集提供摘要数据。 通常，这些标记包含搜索标记，用于搜索结果总数、最低结果和最高结果。 您可以使用常规字段标签定义任意数量的其 <span class="codeph"> 他全局字 </span> 段。 </p> <p> <b>示例</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;general&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;total&gt;&lt;search-total&nbsp;/&gt;&lt;/total&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;lower&gt;&lt;search-lower&nbsp;/&gt;&lt;/lower&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;upper&gt;&lt;search-upper&nbsp;/&gt;&lt;/upper&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;general-field&nbsp;name="my_custom_field"&gt;Some&nbsp;global&nbsp;content&lt;/general-field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/general&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;results&gt;&lt;/results&gt; </span> </p> </td> 
   <td colname="col2"> <p>这组标记围绕搜索结果进行包装，以便“向导式搜索”知道在何处查找它们。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result&gt;&lt;/result&gt; </span> </p> </td> 
   <td colname="col2"> <p>这组标记围绕每个搜索结果进行包装，以便“向导式搜索”可识别单个搜索结果的内容开始和结束的位置。 </p> <p> <b>示例</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;index&gt;&lt;search-index&nbsp;/&gt;&lt;/index&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;loc&gt;&lt;search-cdata&gt;&lt;search-url&nbsp;length="500"&nbsp;/&gt;&lt;/search-cdata&gt;&lt;/loc&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;attribute-table name="tablename"&gt; </span> </p> </td> 
   <td colname="col2"> <p>通过此标签，您可以循环查看多值列表中的每个项目以获得单个结果。 仅在结果中使用标记。 其主要目的是让您对属于结果字段的属性进行迭代。 </p> <p> <b>示例</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;index&gt;&lt;search-index&nbsp;/&gt;&lt;/index&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;loc&gt;&lt;search-url&nbsp;/&gt;&lt;/loc&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;title&gt;&lt;search-title&nbsp;/&gt;&lt;/title&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;attribute-table&nbsp;name="downloads"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;field&nbsp;name="download_title"&gt;&lt;search-display-field&nbsp;name="download_title"&nbsp;/&gt;&lt;/field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;field&nbsp;name="download_link"&nbsp;delimiter="|"&gt;&lt;search-display-field&nbsp;name="download_link"&nbsp;/&gt;&lt;/field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/attribute-table&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facets&gt;&lt;/facets&gt; </span> </p> </td> 
   <td colname="col2"> <p>这组标记传递给填充彩块化的结果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet name="name"&gt;&lt;/facet&gt; </span> </p> </td> 
   <td colname="col2"> <p>每个facet必须有其自己的facet标签，其中name参数与facet名称匹配。 搜索标记在facet值的facet标记内使用。 </p> <p>请参阅 <a href="../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5" type="concept" format="dita" scope="local"> 关于彩块化 </a>。 </p> <p> <b>示例</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;facets&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;facet&nbsp;name="brand"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/facet&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;facet&nbsp;name="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/facet&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/facets&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;建议&gt;&lt;建议&gt; </span> </p> </td> 
   <td colname="col2"> <p>这组标记包含您的“您的意思”建议，以便“向导式搜索”可识别哪些XML节点包含建议。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;建议&gt;&lt;/建议&gt; </span> </p> </td> 
   <td colname="col2"> <p>这组标签用每个“您的意思”建议来包装。 </p> <p> <b>示例</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;search-if-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;suggestion&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;value&gt;&lt;search-suggestion-text&nbsp;/&gt;&lt;/value&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;count&gt;&lt;search-suggestion-result-count&nbsp;/&gt;&lt;/count&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/suggestion&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-if-suggestions&gt; </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**JSON传输模板特定的标记**

从搜索引擎传递JSON与XML的速度之快众所周知，因为它的有效负荷更小，分析器速度更快。 但是，在您使用JSON时，请务必小心，以确保输出内容为严格的JSON，因为分析器不会原谅。

如果您是JSON的新手，则可以使用以下链接和示例帮助您入门：

* JSON简介。 请参 [阅https://www.json.org/](https://www.json.org/)。
* 测试JSON以确保其有效。 请参 [阅https://jsonlint.com/](https://jsonlint.com/)。

**示例JSON模板**

```
{ 
 "general": 
 { 
  "total" : "<search-total />", 
  "lower" : "<search-lower />", 
  "upper" : "<search-upper />", 
  "rbt-trigger-list" : "<search-rbta-trigger-id-list>", 
  "fields" :  
  [ 
   { 
    "name" : "seo_search_title", 
    "value" : "<search-include file="seo/seo_search_title.tpl" />" 
   }, 
   { 
    "name" : "seo_search_keywords", 
    "value" : "<search-include file="seo/seo_search_keywords.tpl" />" 
   } 
  ] 
 }, 
 
 <search-if-suggestions> 
 "suggestions": 
  [ 
  <search-suggestions> 
  { 
   "suggestion":"<search-suggestion-text />", 
   "count": "<search-suggestion-result-count>" 
  }<search-if-not-last-suggestion>,</search-if-not-last-suggestion> 
  </search-suggestions> 
 ], 
 </search-if-suggestions> 
 
 "facets" : 
 [ 
  { 
   "name" : "leveli", 
   "values" : [ <search-field-value-list name="leveli" quotes="yes" sortby="values" data="values" encoding="json"/>], 
   "counts" : [<search-field-value-list name="leveli" quotes="no" sortby="values" data="results" />] 
  }, 
  { 
   "name" :"levelii", 
   "values" : [<search-field-value-list name="levelii" quotes="yes" sortby="values" data="values" encoding="json"/>], 
   "counts" : [<search-field-value-list name="levelii" quotes="no" sortby="values" data="results" />] 
  }, 
  { 
   "name" : "brand", 
   "values" : [<search-field-value-list name="brand" quotes="yes" sortby="values" data="values" encoding="json"/>], 
   "counts" : [<search-field-value-list name="brand" quotes="no" sortby="values" data="results" />] 
  }, 
 ], 
 "results" : 
 [ 
  <search-results> 
  { 
   "fields" : 
   [ 
    { 
     "name" : "index", 
     "value" : "<search-index />" 
    }, 
    { 
     "name" : "loc", 
     "value" : "<search-display-field name="url" length="500" encoding="json"/>" 
    }, 
    { 
     "name" : "title", 
     "value" : "<search-display-field name="title" encoding="json"/>" 
    }, 
    { 
     "name" : "img_url_thumbnail", 
     "value" : "<search-display-field name="img_url_thumbnail" encoding="json"/>" 
    }, 
    { 
     "name" : "description", 
     "value" : "<search-display-field name="description" encoding="json"/>" 
    }, 
    { 
     "name" : "mdi", 
     "value" : "<SEARCH-RBTA-DISPLAY-MDI-FIELD>" 
    } 
   ] 
  }<search-if-not-last>,</search-if-not-last>  
  </search-results> 
 ] 
}
```

**带有结果属性表的JSON结果部分示例**

```
{ 
 "results" : 
 [ 
  <search-results> 
  { 
   "fields" : 
   [ 
    { 
     "name" : "index", 
     "value" : "<search-index />" 
    }, 
    { 
     "name" : "loc", 
     "value" : "<search-display-field name="url" length="500" encoding="json"/>" 
    } 
   ], 
   "tables" : 
   [ 
    { 
     "name" : "downloads", 
     "fields" : 
     [ 
      { 
       "name" : "download_title", 
       "value" : <search-display-field name="download_title" encoding="json"/> 
      }, 
      { 
       "name" : "download_link", 
       "value" : <search-display-field name="download_link" encoding="json"/> 
      } 
     ] 
    } 
   ] 
  }<search-if-not-last>,</search-if-not-last>  
  </search-results> 
 ] 
}
```

**具有关联字段的facet的JSON Facet部分示例**

```
{ 
 facets" : 
 [ 
  { 
   "name" : "t1", 
   "values" : [<search-field-value-list name="t1" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />], 
   "counts" : [<search-field-value-list name="t1" quotes="yes" commas="yes" data="results" sortby="values" />], 
   "custom-fields" : 
   [ 
    { 
     "name" : "taxonmyId", 
     "value" : [<search-field-value-list name="tax1" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />] 
    } 
   ] 
  } 
 ] 
}
```

**时隙facet的JSON Facet部分示例**

```
{ 
  "facets" : 
  [  
   { 
    "name" : "fvalue0", 
                  "dynamic" : 1, 
                  "display-names" : [<search-field-value-list name="fname0" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />], 
    "values" : [<search-field-value-list name="fvalue0" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />], 
    "counts" : [<search-field-value-list name="fvalue0" quotes="no" commas="yes" data="results" sortby="values" />] 
   } 
  ] 
} 
```

## 添加新演示文稿或传输模板文件 {#task_73199757B6E748CAA604902FF913F012}

您可以使 **[!UICONTROL Add Template]** 用将演示文稿模板(.tmpl)或传输模板(.tpl)添加到页 [!DNL Templates] 面。

<!-- 

t_adding_a_new_presentation_or_transport_template_file.xml

 -->

**添加新演示文稿或传输模板文件**

1. 在产品菜单中，单击 **[!UICONTROL Design]** > **[!UICONTROL Templates]**。
1. 在页面 [!DNL Templates] 上，单击 **[!UICONTROL Add New Template]**。
1. 在对 [!DNL Add Template] 话框中，设置所需的选项。

   <!-- 
   
   r_add_template_options.xml
   
   -->

   | 选项 | 描述 |
   |--- |--- |
   | 新文件名 | 指定要添加的模板的名称。 根据您选择的模板类型，相应的文件扩展名会自动添加到文件名中。  演示文稿模板的文件扩展名为。tmpl;传输模板的文件扩展名为。tpl。 |
   | 新模板类型 | 允许您选择要添加的演示文稿或传输模板。  请参阅 [关于模板](../c-about-design-menu/c-about-templates.md)。 |

   另请参阅 [编辑演示文稿或传输模板](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3)。
1. 单击 **[!UICONTROL Add]**.
1. （可选）在页 [!DNL Templates] 面上，执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 编辑演示文稿或传输模板 {#task_800E0E2265C34C028C92FEB5A1243EC3}

您可以使用模板编辑器查看和编辑演示文稿和传输模板文件的内容。

<!-- 

t_editing_a_template.xml

 -->

您可以编辑和测试分阶段演示和传输模板，而网站访问者则继续使用模板的实时版本。 您可以使用搜索域URL的分阶段版本测试分阶段模板。 例如，您可以通过运行设置为传输模板名称的分阶段查询( `sp_staged=1`)来 `sp_t` 测试分阶段传输模板。 当您对布局的显示方式感到满意时，您可以从模 **[!UICONTROL Push Live]** 板编辑器中使用该模板来实时推送。 模板实时生成后，站点访问者开始使用它。

使用演示文稿模板标记参考可了解如何将演示文稿模板关联到向导式搜索组件，如彩块化、痕迹导航和菜单。

请参阅演 [示文稿模板标记](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)

使用传输模板标记参考进一步了解要在传输模板中使用的标记。

请参阅 [传输模板标记](../c-appendices/c-templates.md#reference_227D199F5A7248049BE1D405C0584751)

**[!UICONTROL To edit a presentation or a transport template]**

1. 在产品菜单中，单击 **[!UICONTROL Design]** > **[!UICONTROL Templates]**。
1. 在页面 [!DNL Templates] 上，单击演示文稿或传输模板文件名。
1. 在页 [!DNL Template Editor] 面上，对标记和编码进行更改。

   注意您在中所做的更改 [!DNL Template Editor];没有“撤消”功能。 如果您做出不需要的更改，并且希望返回到文件的先前版本，则可以单击以返回到模板表（假定您在此之前未保存任何更改）。 **[!UICONTROL Cancel]** 如果已保存更改，则可以在编辑 **[!UICONTROL History]** 器中使用还原这些更改。
1. （可选）单击 **[!UICONTROL Insert Symbol]** 以输入在美国英语键盘上没有相应键的特殊字符和符号。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

1. 完成后，关闭“模板编辑器”页面；您将返回到“模板”页面。

## 复制演示文稿或传输模板文件 {#task_B744AB3384C84DD59C33CD25E18C2C90}

您可以使 **[!UICONTROL Copy Template]** 用复制现有演示文稿模板(.tmpl)或传输模板(.tpl)来节省时间，并将其添加到模板页面。

<!-- 

t_copying_a_presentation_or_a_transport_template.xml

 -->

必须更改模板名称、模板类型或两者。 如果不进行任何更改，则不会复制模板。

必须已添加模板，才能复制模板。

请参 [阅添加新演示文稿或传输模板文件](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)。

**复制演示文稿或传输模板文件**

1. 在产品菜单中，单击 **[!UICONTROL Design]** > **[!UICONTROL Templates]**。
1. 在页 [!DNL Templates] 面上，在要复制的模板名称旁边的下拉列表中，单击 **[!UICONTROL Copy]**。
1. 在对 [!DNL Copy Template] 话框中，设置一个或多个所需的选项。
1. 单击 **[!UICONTROL Copy]**.
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 重命名演示文稿或传输模板文件 {#task_CC30050FC2DE4898BF44379D8378EB31}

您可以使用 [!DNL Rename Template] 更改现有演示文稿模板(.tmpl)或传输模板(.tpl)的名称。

<!-- 

t_renaming_a_presentation_or_a_transport_template_file.xml

 -->

您还可以根据需要更改模板类型。

必须已添加模板才能重命名模板。

请参 [阅添加新演示文稿或传输模板文件](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)。

**重命名演示文稿或传输模板文件**

1. 在产品菜单中，单击 **[!UICONTROL Design]** > **[!UICONTROL Templates]**。
1. 在页 [!DNL Templates] 面上，在要重命名的模板名称旁边的下拉列表中，单击 **[!UICONTROL Rename]**。
1. 在对 [!DNL Rename Template] 话框中，设置一个或多个所需的选项。
1. 单击 **[!UICONTROL Rename]**.
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 删除演示文稿或传输模板文件 {#task_67E532C2B83A449687737E3B06C5AA58}

您可以使用 **[!UICONTROL Delete Template]** 删除现有演示文稿模板(.tmpl)或传输模板(.tpl)。

<!-- 

t_deleting_a_presentation_or_a_transport_template_file.xml

 -->

您可能已经拥有被实时推送的已暂存模板的相应版本。 如果是，请确保使用将已删除的模板实时推 **[!UICONTROL Staging]** 送，以便也从实时环境中删除它。 或者，您也可以在“模 **[!UICONTROL Push Live]** 板”页面上使用。

请参阅 [关于暂存](../c-about-staging.md#concept_08B8F3CA1F4241108F14BA7FC7806CA7)

请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)

必须已添加模板，才能删除模板。

请参 [阅添加新演示文稿或传输模板文件](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)

**删除演示文稿或传输模板文件**

1. 在产品菜单中，单击 **[!UICONTROL Design]** > **[!UICONTROL Templates]**。
1. 在页 [!DNL Templates] 面上，在要删除的模板名称旁边的下拉列表中，单击 **[!UICONTROL Delete]**。
1. 在对话 [!DNL Delete Template] 框中，单击 **[!UICONTROL Delete.]**
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 预览演示文稿模板已最小化 {#task_1757B6207CC74221AE4BFFE5674D320B}

如果您选 **[!UICONTROL Preview minimized]** 择将演示文稿模板的页面粗细减到最小，您可以使用它来查看缩减后的效果。

<!-- 

t_previewing_the_presentation_template_minimized.xml

 -->

如果最小化主演示文稿模板，请务必记住启用最小化（带有向导式包含标记）模板，因为此选项不可继承。

请参 [阅降低您的演示文稿模板的页面粗细……](../c-about-design-menu/c-about-templates.md#task_B09BB3CE89714DEAAE8D9A899CF3009E)

必须已添加一个模板，才能将模板预览最小化。

请参 [阅添加新演示文稿或传输模板文件](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)

您可以预览传输模板文件的XML代码。

请参 [阅预览传输模板文件的XML](../c-about-design-menu/c-about-templates.md#task_58C6C52078E14AD88D2B2F0B3C439AE8)

**要预览最小化的演示文稿模板，请执行以下操作：**

1. 在产品菜单中，单击 **[!UICONTROL Design]** > **[!UICONTROL Templates]**。
1. 在页 [!DNL Templates] 面上，在演示文稿模板名称旁边的下拉列表中，单击 **[!UICONTROL Preview minimized]**。

   使用“模 **[!UICONTROL Type]** 板”(Templates)表格中的列按演示和传输对模板进行排序。
1. （可选）在页 [!DNL Preview Minimized Template] 面上，选 **[!UICONTROL Wrap lines]** 中以阅读定义的窗口中的标记。
1. 单击 **[!UICONTROL Close]**.
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 降低网站上演示文稿模板的页面重量 {#task_B09BB3CE89714DEAAE8D9A899CF3009E}

您可以使用模板表中的选项来降低演示文稿模 **[!UICONTROL Minimize]** 板的页面粗细。

<!-- 

t_reducing_the_page_weight_of_a_presentation_template.xml

 -->

通过减少模板的页面粗细，可动态地最小化内联JavaScript和CSS。 您还可以删除HTML中的多余空白。 最小化演示文稿模板的页面粗细有助于更快地交付搜索结果。

您还可以使用预览最小化的演示文稿模板的外观 **[!UICONTROL Preview minimized]**。

请参阅 [预览最小化的演示文稿模板](../c-about-design-menu/c-about-templates.md#task_1757B6207CC74221AE4BFFE5674D320B)。

**[!UICONTROL To reduce the page weight of a presentation template on your website]**

1. 在产品菜单中，单击 **[!UICONTROL Design]** > **[!UICONTROL Templates]**。
1. 在页 [!DNL Templates] 面的列下，选中要在网站上以最小化 [!DNL Minimize] 方式推送的一个或多个演示文稿模板文件的框。

   使用表 **[!UICONTROL Type]** 格中的列按 [!DNL Templates] “演示和传输”对模板进行排序。
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 设置要在网站中使用的默认演示文稿模板文件 {#task_C1E8CE817E4D43E096167A347C54DD53}

当您有多个演示文稿模板时，您可以指示最初用于显示搜索结果的模板。

<!-- 

t_setting_the_default_presentation_template_file_to_use.xml

 -->

您可以使用搜索前规则、搜索后规则和业务规则来确定何时应使用其他演示文稿模板之一。

See [About Pre-Search Rules](../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F).

See [About Post-Search Rules](../c-about-rules-menu/c-about-post-search-rules.md#concept_AF6ADFCC0ADF4A788003964939917FDE).

See [About Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

通常有一个规则，如“对于每次搜索，将目标演示文稿模板设置为xxxx”。 在实施此类规则后，在“模板”页面上更改“默认”模板似乎不起作用。

**[!UICONTROL To set the default presentation template file to use on your website]**

1. 在产品菜单中，单击 **[!UICONTROL Design]** > **[!UICONTROL Templates]**。
1. 在页 [!DNL Templates] 面的列下，单击要 [!DNL Default] 用作默认值的相应演示文稿模板文件的单选按钮。

   使用表 **[!UICONTROL Type]** 格中的列按 [!DNL Templates] “演示和传输”对模板进行排序。
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 预览传输模板文件的XML {#task_58C6C52078E14AD88D2B2F0B3C439AE8}

您可以使用 [!DNL Preview] 查看已添加的传输模板的XML。

<!-- 

t_previewing_the_xml_of_a_transport_template_file.xml

 -->

必须已添加传输模板才能预览模板的XML。

请参 [阅添加新演示文稿或传输模板文件](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)。

您可以预览最小化的演示文稿模板文件，以查看其缩减的页面粗细。

请参阅 [预览最小化的演示文稿模板](../c-about-design-menu/c-about-templates.md#task_1757B6207CC74221AE4BFFE5674D320B)。

**预览传输模板文件的XML**

1. 在产品菜单中，单击 **[!UICONTROL Design]** > **[!UICONTROL Templates]**。
1. 在页 [!DNL Templates] 面上，在传输模板名称旁边的下拉列表中，单击 **[!UICONTROL Preview]**。

   使用表 **[!UICONTROL Type]** 格中的列按 [!DNL Templates] “演示和传输”对模板进行排序。
1. 关闭查看窗口并返回 [!DNL site search/merchandising]。
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

