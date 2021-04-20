---
description: 您可以配置“自动完成”的各个区域，以控制生成启用自动完成的搜索表单以及作为支持自动完成的搜索表单的一部分包含的文件autocomplete_data.js。
solution: Target
subtopic: Auto-Complete
title: 关于自动完成
topic: Design,Site search and merchandising
uuid: 3dfdd14d-2044-4f01-a5bc-fcb2eb0d5068
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1499'
ht-degree: 1%

---


# 关于自动完成{#about-auto-complete}

您可以配置“自动完成”的各个区域，以控制生成启用自动完成的搜索表单以及作为支持自动完成的搜索表单的一部分包含的文件autocomplete_data.js。

## 关于自动完成{#concept_093A9CD754864BA79B456FE4BEB64578}

每当“自动完成设置”页面已保存更改时，将重新生成文件[!DNL autocomplete_data.js]并将其发布到搜索内容网络。

## 配置自动完成{#task_F491F2BFC4D24A61BBDC48B9059C11BB}

您可以配置和设置选项，以控制生成已启用自动完成的搜索表单和文件。

<!-- 

t_configuring_auto-complete.xml

 -->

配置自动完成后，可以视图生成的HTML源以供审阅。 HTML源是您复制并粘贴到网站页面中的内容。

请参阅[预览搜索表单在您的表单上的显示效果……](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714)。

请参阅[配置自动完成Word列表](c-about-auto-complete.md#task_1F8E0F346263443383F8CFD2C7AB35D4)。

请参阅[配置自动完成CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96)。

**配置自动完成**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete Setup]**。
1. 在[!DNL Auto-Complete Setup]页面上，设置所需的选项。

   另请参阅[预览搜索表单在您的表单上的显示效果……](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714)。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>最大建议数 </p> </td> 
      <td colname="col2"> <p>指定要在自动完成建议列表中显示的最大项目数。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最小输入字符数 </p> </td> 
      <td colname="col2"> <p>指定客户在显示建议之前必须在自动完成搜索表单中键入的字符数。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最大缓存条目数 </p> </td> 
      <td colname="col2"> <p>指定先前请求的要在客户浏览器中缓存的自动完成建议的最大数目。 通常，应将此设置保留为默认值1000。 </p> <p>虽然可以通过将此选项设置为0来完全禁用浏览器缓存，但不建议这样做。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>表单名称 </p> </td> 
      <td colname="col2"> <p>指定启用自动完成的搜索表单的“表单”标签的“name”属性。 例如： </p> <p> <span class="filepath"> &lt;form name="SiteSearch" method="get" action="https://sp1004337c.guided.t1.atomz.com" target="_blank"&gt; </span> </p> <p>其中，<span class="filepath"> SiteSearch </span>是表单标签的名称属性。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Div标签ID </p> </td> 
      <td colname="col2"> <p>指定启用自动完成的搜索表单的“div”标签的ID属性。 例如： </p> <p> <span class="filepath"> &lt;div id="autocomplete"&gt; </span> </p> <p>其中，<span class="filepath"> autocomplete </span>是div标签的属性。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>输入标记ID </p> </td> 
      <td colname="col2"> <p>指定启用自动完成的搜索表单的“input”标签的ID属性。 例如： </p> <p> <span class="filepath"> &lt;input type="text" id="q" name="q" /&gt; </span> </p> <p>其中，<span class="filepath"> q </span>是输入标记的id属性。 </p> </td> 
      </tr> 
      <tr>
      <td colname="col1"> <p>显示阴影 </p> </td>
      <td colname="col2"> <p>向自动完成建议列表添加外观投影。 </p> </td>
      </tr>
      <tr>
      <td colname="col1"> <p>仅在短语开头匹配 </p> </td>
      <td colname="col2"> <p>仅建议与输入文本开头匹配的结果。 </p> </td>
      </tr>
      <tr>
      <td colname="col1"> <p>支持UTF-8字符集 </p> </td>
      <td colname="col2"> <p>正确处理术语中的非ASCII字符。 </p> </td>
      </tr>
    </tbody> 
   </table>

1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 配置自动完成Word列表{#task_1F8E0F346263443383F8CFD2C7AB35D4}

配置自动完成作为建议显示给客户的词和短语的列表。

<!-- 

t_configuring_auto-complete_word_list.xml

 -->

请参阅[配置自动完成](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB)。

请参阅[配置自动完成CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96)。

**配置自动完成Word列表**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete Word List]**。
1. 在[!DNL Auto-Complete Word List]页面上，设置所需的选项。

   请参阅[预览搜索表单在您的表单上的显示效果……](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714)。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>热门搜索时段 </p> </td> 
      <td colname="col2"> <p> 控制包含客户最近搜索中的词语和短语的时间段。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> 最大搜索数 </p> </td> 
      <td colname="col2"> <p>控制要包含在自动完成单词列表中的搜索词和短语的最大数量。 其中包括最受欢迎的顶级词语和短语。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>字段名称 </p> </td> 
      <td colname="col2"> <p>每个字段名称定义一个要包含索引值的字段的名称。 使用+和 — 可添加或删除字段名称。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最大值计数 </p> </td> 
      <td colname="col2"> <p>定义所选字段名称允许的最大字段值计数。 其中包括顶部值（也是引用最多的值）。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>添加这些词和短语 </p> </td> 
      <td colname="col2"> <p> 自动完成的单词列表会填充此区域中列出的单词和短语。 </p> <p> 单击<span class="uicontrol">编辑</span>可查看列表或向列表添加单词和短语。 完成后，单击<span class="uicontrol">保存更改</span>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>删除这些单词和短语 </p> </td> 
      <td colname="col2"> <p> 此区域中的条目不会显示在自动完成的单词列表中。 </p> <p> 单击<span class="uicontrol">编辑</span>可查看列表或向列表添加单词和短语。 完成后，单击<span class="uicontrol">保存更改</span>。 </p> <p> 此列表中允许使用常规表达式。 要在此列表中指定常规表达式，请将行开始为<code>regexp</code>，后跟一个空格，后跟常规表达式。 单词列表中与常规表达式匹配的任何行都将被删除。 </p> <p> <b>重要说明</b>:仅当您以前在其他应用程序中使用过常规表达式时，才应使用它们。 </p> <p>请参阅<a href="c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local">常规表达式</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>忽略大小写 </p> </td> 
      <td colname="col2"> <p>自动完成单词列表中仅按大小写字母不同的重复项被删除；所有单词列表项都被强制为小写。 </p> <p>如果您希望“自动完成”建议显示为“首字母大写”或“所有大写字母”，请添加 
        <code>
          text-transform : capitalize; 
        </code>或 
        <code>
          text-transform : uppercase; 
        </code> CSS文本属性至“自动完成CSS”内容，位于结果项*/的“/*样式”下。 </p> <p>请参阅<a href="c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96" type="task" format="dita" scope="local">配置自动完成CSS </a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>重新索引时更新 </p> </td> 
      <td colname="col2"> <p>每次成功重新索引帐户后，将自动重新生成自动完成的单词列表。 </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。
   * 单击&#x200B;**[!UICONTROL Preview Word List]**&#x200B;以保存您所做的任何更改，然后打开[!DNL Auto-Complete Word List Preview]页面，在该页面中可以查看自动完成建议列表。 使用页面顶部附近的导航选项查看和优化显示的列表。 完成后，单击&#x200B;**[!UICONTROL Close]**&#x200B;返回至[!DNL Auto-Complete Word List]页面。

      请参阅[使用历史记录选项](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 配置自动完成CSS {#task_EECE35DEB6C94F4A8A5B42B4DED76D96}

使用“自动完成CSS”配置要使用的自动完成级联样式表。

<!-- 

t_configuring_auto-complete_css.xml

 -->

“自动完成CSS”控制[!DNL autocomplete_styles.css]的内容，它作为支持自动完成的搜索表单的一部分包含在其中。 您在此处指定的CSS控制自动完成建议列表的可视演示。 有关可能的可视化演示构思的示例，请参阅以下内容：

[https://developer.yahoo.com/yui/examples/autocomplete/ac_skinning.html](https://developer.yahoo.com/yui/examples/autocomplete/ac_skinning.html)。

[配置自动完成Word列表](c-about-auto-complete.md#task_1F8E0F346263443383F8CFD2C7AB35D4)。

[配置自动完成](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB)。

配置完“自动完成CSS”后，您可以预览搜索表单以查看您指定的CSS在外观和布局中是否可接受。

请参阅[预览搜索表单在您的表单上的显示效果……](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714)。

**重要说明**:要应用自定义自动完成的CSS，您需要从HTML代码中显示的第二行删除注释标签。然后，将同一行移动到包含搜索表单的页面的标题部分内。

请参阅[将搜索表单的HTML代码复制到……](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7)。

**配置自动完成CSS**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete CSS]**。
1. 在[!DNL Auto-Complete CSS]文本字段中，粘贴或键入要与自动完成建议列表关联的级联样式表信息。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 预览搜索表单，它将像在您的网站{#task_437B35EFA5424603A08AF8E79E6B4714}中一样显示

根据“自动完成”和“自动完成CSS”的配置，如果要将HTML代码添加到网站，您可以预览搜索表单的显示方式。

<!-- 

t_previewing_the_search_form_as_it_would_appear_on_your_website.xml

 -->

请参阅[配置自动完成](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB)。

请参阅[配置自动完成CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96)。

请参阅[将搜索表单的HTML代码复制到……](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7)。

请参阅[在搜索表单中使用集合](c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3)。

请参阅[使用具有表单的帧](c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5)。

请参阅[高级搜索表单示例](c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A)。

请参阅[高级搜索表单HTML代码](c-appendices/c-searchforms.md#reference_9AAD4A46B68D4D48865508982CB86DB9)。

请参阅[高级搜索表单模板代码](c-appendices/c-searchforms.md#reference_D762C22E754E462DBEECD88D2C3FA579)。

**要预览搜索表单在您网站上的显示效果**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Search Form]**。
1. （可选）单击&#x200B;**[!UICONTROL HTML code]**&#x200B;查看复制并粘贴到网站页面中的HTML。

## 将搜索表单的HTML代码复制到网站{#task_A3A01EA800F24C0AA33902387E0362C7}的页面

根据“自动完成”和“自动完成CSS”的配置，如果要将HTML代码添加到网站，您可以预览搜索表单的显示方式。

<!-- 

t_copying_the_html_code_of_the_search_form_into_the_pages_of_your_website.xml

 -->

请参阅[配置自动完成](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB)。

请参阅[配置自动完成CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96)。

请参阅[将搜索表单的HTML代码复制到……](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7)。

请参阅[在搜索表单中使用集合](c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3)。

请参阅[使用具有表单的帧](c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5)。

请参阅[高级搜索表单示例](c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A)。

请参阅[高级搜索表单HTML代码](c-appendices/c-searchforms.md#reference_9AAD4A46B68D4D48865508982CB86DB9)。

请参阅[高级搜索表单模板代码](c-appendices/c-searchforms.md#reference_D762C22E754E462DBEECD88D2C3FA579)。

**将搜索表单的HTML代码复制到网站页面**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**。

   >[!NOTE]
   >
   >请勿更改表单源中的`form name=`值。

1. （可选）执行下列任一操作：

   * 如果您配置了自动完成CSS并希望将样式应用于搜索表单，请从HTML代码中显示的第二行删除注释标签。 接下来，将同一行移动到包含搜索表单的页面的标题部分内。
   * 为获得最佳性能，请移动HTML代码底部列出的标记，并将它们放置在包含搜索表单的每个页面的正文部分底部。

1. 复制代码并将其粘贴到您希望显示搜索表单的网站的网页中。
