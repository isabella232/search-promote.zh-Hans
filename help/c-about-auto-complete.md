---
description: 您可以配置“自动完成”的各个区域以控制生成启用自动完成的搜索表单以及作为支持自动完成的搜索表单的一部分包含的文件autocomplete_data.js。
seo-description: 您可以配置“自动完成”的各个区域以控制生成启用自动完成的搜索表单以及作为支持自动完成的搜索表单的一部分包含的文件autocomplete_data.js。
seo-title: 关于自动完成
solution: Target
subtopic: Auto-Complete
title: 关于自动完成
topic: Design,Site search and merchandising
uuid: 3dfdd14d-2044-4f01-a5bc-fcb2eb0d5068
translation-type: tm+mt
source-git-commit: 439100ab96f4b597c55b1c1ae38a5778c208e896

---


# 关于自动完成{#about-auto-complete}

您可以配置“自动完成”的各个区域以控制生成启用自动完成的搜索表单以及作为支持自动完成的搜索表单的一部分包含的文件autocomplete_data.js。

## 关于自动完成 {#concept_093A9CD754864BA79B456FE4BEB64578}

每次“自 [!DNL autocomplete_data.js] 动完成设置”页面已保存更改时，都会重新生成文件并将其发布到搜索内容网络。

## 配置自动完成 {#task_F491F2BFC4D24A61BBDC48B9059C11BB}

您可以配置和设置选项，以控制自动生成已启用的搜索表单和文件。

<!-- 

t_configuring_auto-complete.xml

 -->

配置自动完成后，您可以查看生成的HTML源以供审阅。 HTML源是您复制并粘贴到网站页面中的内容。

请参 [阅预览搜索表单在您的表单上的外观……](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

请参 [阅配置自动完成单词列表](c-about-auto-complete.md#task_1F8E0F346263443383F8CFD2C7AB35D4)。

请参 [阅配置自动完成CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96)。

**配置自动完成**

1. 在产品菜单中，单击 **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete Setup]**。
1. 在页 [!DNL Auto-Complete Setup] 面上，设置所需的选项。

   另请参 [阅预览搜索表单在您的表单上的显示方式……](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

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
      <td colname="col1"> <p>最少输入字符数 </p> </td> 
      <td colname="col2"> <p>指定客户在显示建议之前必须在自动完成搜索表单中键入的字符数。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最大缓存条目数 </p> </td> 
      <td colname="col2"> <p>指定先前请求的自动完成建议在客户的浏览器中缓存的最大数量。 通常，应将此设置保留为默认值1000。 </p> <p>虽然可以通过将此选项设置为0来完全禁用浏览器缓存，但不建议这样做。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>表单名称 </p> </td> 
      <td colname="col2"> <p>指定启用自动完成的搜索表单的“表单”标签的“名称”属性。 例如： </p> <p> <span class="filepath"> &lt;form name="SiteSearch" method="get" action="https://sp1004337c.guided.t1.atomz.com" target="_blank"&gt; </span> </p> <p>其中 <span class="filepath"> SiteSearch </span> 是表单标记的名称属性。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Div标签ID </p> </td> 
      <td colname="col2"> <p>指定启用自动完成的搜索表单的“div”标签的ID属性。 例如： </p> <p> <span class="filepath"> &lt;div id="autocomplete"&gt; </span> </p> <p>其中 <span class="filepath"> 自 </span> 动完成是div标签的属性。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>输入标记ID </p> </td> 
      <td colname="col2"> <p>指定启用自动完成的搜索表单的“input”标签的ID属性。 例如： </p> <p> <span class="filepath"> &lt;input type="text" id="q" name="q" /&gt; </span> </p> <p>其中 <span class="filepath"> q </span> 是输入标记的id属性。 </p> </td> 
      </tr> 
      <tr>
      <td colname="col1"> <p>显示阴影 </p> </td>
      <td colname="col2"> <p>向自动完成建议列表添加外观投影。 </p> </td>
      </tr>
      <tr>
      <td colname="col1"> <p>仅在短语开头匹配 </p> </td>
      <td colname="col2"> <p>仅建议与输入文本的开头匹配的结果。 </p> </td>
      </tr>
      <tr>
      <td colname="col1"> <p>支持UTF-8字符集 </p> </td>
      <td colname="col2"> <p>正确处理非ASCII字符。 </p> </td>
      </tr>
    </tbody> 
   </table>

1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 配置自动完成单词列表 {#task_1F8E0F346263443383F8CFD2C7AB35D4}

配置“自动完成”作为建议显示给客户的单词和短语列表。

<!-- 

t_configuring_auto-complete_word_list.xml

 -->

请参 [阅配置自动完成](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB)。

请参 [阅配置自动完成CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96)。

**配置自动完成单词列表**

1. 在产品菜单中，单击 **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete Word List]**。
1. 在页 [!DNL Auto-Complete Word List] 面上，设置所需的选项。

   请参 [阅预览搜索表单在您的表单上的外观……](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

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
      <td colname="col2"> <p>控制要包含在自动完成单词列表中的搜索单词和短语的最大数量。 其中包含最受欢迎的顶级词语和短语。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>字段名称 </p> </td> 
      <td colname="col2"> <p>每个字段名称定义一个要包含索引值的字段的名称。 使用+和——可添加或删除字段名称。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最大值计数 </p> </td> 
      <td colname="col2"> <p>定义所选字段名称允许的字段值的最大计数。 其中包括顶部值（也是最引用的值）。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>添加这些单词和短语 </p> </td> 
      <td colname="col2"> <p> 自动完成单词列表会填充此区域中列出的单词和短语。 </p> <p> 单击 <span class="uicontrol"> “编 </span> 辑”可查看列表，或向列表添加单词和短语。 完成后，单击“保 <span class="uicontrol"> 存更改” </span>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>删除这些单词和短语 </p> </td> 
      <td colname="col2"> <p> 此区域中的条目不会显示在自动完成单词列表中。 </p> <p> 单击 <span class="uicontrol"> “编 </span> 辑”可查看列表，或向列表添加单词和短语。 完成后，单击“保 <span class="uicontrol"> 存更改” </span>。 </p> <p> 此列表中允许使用正则表达式。 要在此列表中指定正则表达式，请将行开头为 
        <userinput>
          regexp 
        </userinput> 后跟一个空格，后跟正则表达式。 将删除单词列表中与正则表达式匹配的任何行。 </p> <p> <b>重要说明</b>:仅当您之前在其他应用程序中使用过正则表达式时，才应使用正则表达式。 </p> <p>请参阅 <a href="c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> 正则表达式 </a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>忽略大小写 </p> </td> 
      <td colname="col2"> <p>自动完成单词列表中仅按字母大小写不同的重复条目被删除；所有单词列表条目都强制为小写。 </p> <p>如果希望“自动完成”建议显示为“大写字母”或“全部大写”，请添加 
        <userinput>
          text-transform:资本化； 
        </userinput> 或 
        <userinput>
          text-transform:大写； 
        </userinput> “自动完成CSS内容”下的CSS文本属性，位于“/*样式的结果项*/”下。 </p> <p>请参 <a href="c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96" type="task" format="dita" scope="local"> 阅配置自动完成CSS </a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>重新索引时更新 </p> </td> 
      <td colname="col2"> <p>每次成功重新索引帐户后，将自动重新生成自动完成单词列表。 </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列任一操作：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。
   * 单 **[!UICONTROL Preview Word List]** 击以保存所做的任何更改，然后打开页 [!DNL Auto-Complete Word List Preview] 面，您可以在其中查看自动完成建议列表。 使用页面顶部附近的导航选项来查看和细化显示的列表。 完成后，单击以 **[!UICONTROL Close]** 返回到该页 [!DNL Auto-Complete Word List] 面。

      请参 [阅使用历史记录选项](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 配置自动完成CSS {#task_EECE35DEB6C94F4A8A5B42B4DED76D96}

使用“自动完成CSS”配置要使用的自动完成层叠样式表。

<!-- 

t_configuring_auto-complete_css.xml

 -->

“自动完成”CSS控制其内容 [!DNL autocomplete_styles.css]，该内容作为支持自动完成的搜索表单的一部分提供。 您在此处指定的CSS控制自动完成建议列表的可视化演示。 有关可能的可视化演示构思的示例，请参阅以下内容：

[https://developer.yahoo.com/yui/examples/autocomplete/ac_skinning.html](https://developer.yahoo.com/yui/examples/autocomplete/ac_skinning.html)。

[配置自动完成单词列表](c-about-auto-complete.md#task_1F8E0F346263443383F8CFD2C7AB35D4)。

[配置自动完成](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB)。

完成“自动完成CSS”配置后，可预览搜索表单以查看您指定的CSS在外观和布局中是否可接受。

请参 [阅预览搜索表单在您的表单上的外观……](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

**重要说明**:要应用自定义自动完成的CSS，您需要从HTML代码中显示的第二行中删除注释标记。 然后，您将同一行移动到包含搜索表单的页面的标题部分内。

请参 [阅将搜索表单的HTML代码复制到……](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

**配置自动完成CSS**

1. 在产品菜单中，单击 **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete CSS]**。
1. 在文本 [!DNL Auto-Complete CSS] 字段中，粘贴或键入要与自动完成建议列表关联的层叠样式表信息。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列任一操作：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 预览搜索表单在网站上的显示效果 {#task_437B35EFA5424603A08AF8E79E6B4714}

根据“自动完成”和“自动完成CSS”的配置，如果要将HTML代码添加到网站，您可以预览搜索表单的显示方式。

<!-- 

t_previewing_the_search_form_as_it_would_appear_on_your_website.xml

 -->

请参 [阅配置自动完成](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB)。

请参 [阅配置自动完成CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96)。

请参 [阅将搜索表单的HTML代码复制到……](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

请参阅 [在搜索表单中使用集合](c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3)。

请参 [阅将框架与表单一起使用](c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5)。

请参 [阅示例高级搜索表单](c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A)。

请参 [阅高级搜索表单HTML代码](c-appendices/c-searchforms.md#reference_9AAD4A46B68D4D48865508982CB86DB9)。

请参阅 [高级搜索表单模板代码](c-appendices/c-searchforms.md#reference_D762C22E754E462DBEECD88D2C3FA579)。

**要预览搜索表单在网站上的显示效果，请执行以下操作：**

1. 在产品菜单中，单击 **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Search Form]**。
1. （可选）单 **[!UICONTROL HTML code]** 击以查看复制并粘贴到网站页面中的HTML。

## 将搜索表单的HTML代码复制到网站的页面中 {#task_A3A01EA800F24C0AA33902387E0362C7}

根据“自动完成”和“自动完成CSS”的配置，如果要将HTML代码添加到网站，您可以预览搜索表单的显示方式。

<!-- 

t_copying_the_html_code_of_the_search_form_into_the_pages_of_your_website.xml

 -->

请参 [阅配置自动完成](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB)。

请参 [阅配置自动完成CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96)。

请参 [阅将搜索表单的HTML代码复制到……](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

请参阅 [在搜索表单中使用集合](c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3)。

请参 [阅将框架与表单一起使用](c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5)。

请参 [阅示例高级搜索表单](c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A)。

请参 [阅高级搜索表单HTML代码](c-appendices/c-searchforms.md#reference_9AAD4A46B68D4D48865508982CB86DB9)。

请参阅 [高级搜索表单模板代码](c-appendices/c-searchforms.md#reference_D762C22E754E462DBEECD88D2C3FA579)。

**将搜索表单的HTML代码复制到网站的页面中**

1. 在产品菜单中，单击 **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**。

   >[!NOTE]
   >
   >请勿更改表 `form name=` 单源中的值。

1. （可选）执行下列任一操作：

   * 如果您配置了自动完成CSS并希望样式应用于搜索表单，请从HTML代码中显示的第二行删除注释标签。 接下来，将同一行移动到包含搜索表单的页面的标题部分内。
   * 为获得最佳性能，请移动HTML代码底部列出的标记，并将它们放置在包含搜索表单的每个页面的正文部分的底部。

1. 复制代码并将其粘贴到您希望显示搜索表单的网站网页中。
