---
description: 您可以使用“单词和语言”来确定如何将搜索词与网页内容进行匹配。
solution: Target
title: 关于词语和语言
topic-legacy: Linguistics,Site search and merchandising
uuid: 793d7a40-4609-44b8-a170-536eb1434537
exl-id: bfc84879-1fd1-4c86-beab-353469014c64
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 0%

---

# 关于单词和语言{#about-words-language}

可使用[!DNL Words & Language]确定如何将搜索词与网页内容进行匹配。

## 使用单词和语言{#concept_CEB4B9576F3C4E2EB87B352EEC738D79}

在[!DNL Words & Language]设置的效果可用于站点访客之前，包括您对这些设置所做的任何更改，必须重新生成站点索引。 与索引不同，重新生成不涉及搜索网页，只需几秒钟。

## 配置搜索词与Web内容的匹配方式{#task_351A9144A51F4B41923BDBACDEF3B616}

您可以使用“单词和语言”来确定网站搜索/促销如何将搜索词与网页内容匹配。

<!-- 

t_configuring_how_search_terms_matched_to_your_web_content.xml

 -->

**配置搜索词与Web内容的匹配方式**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Linguistics]** > **[!UICONTROL Words & Language]**。
1. 在[!DNL Words & Languages]页面上，设置所需的选项。

   <!-- 
   
   r_words_and_languages_options.xml
   
   -->

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>区分大小写 </p> </td> 
      <td colname="col2"> <p>默认情况下未选中。 </p> <p>确定是否区分大写字母与小写字母。 例如，选择“成功”时，会将“成功”与“成功”区分开来，并且搜索结果可能会在两者之间有所不同。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>音符 </p> </td> 
      <td colname="col2"> <p>默认选中。 </p> <p> 确定是否将包含变音符的词与不包含变音符的词区分开。 例如，当选择时，“pagina”与“página”区分开。 如果您的网站使用非英语语言，请取消选择此选项。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>数字 </p> </td> 
      <td colname="col2"> <p>默认选中。 </p> <p>确定是否对包含数字的词进行索引。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>忽略撇号 </p> </td> 
      <td colname="col2"> <p>默认情况下未选中。 </p> <p>撇号将从查询中删除。 例如，搜索“树”将返回与搜索“树”相同的结果。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>忽略连字符 </p> </td> 
      <td colname="col2"> <p>默认情况下未选中。 </p> <p>从查询中删除连字符。 例如，搜索“blue-bell”将返回与搜索“bluebell”相同的结果。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>部分字母数字匹配 </p> </td> 
      <td colname="col2"> <p>默认情况下未选中。 </p> <p>选择此选项后，您可以在字母数字过渡上拆分令牌，以允许部分或产品令牌上的自由文本匹配。 </p> <p>例如，假定网站上一个或多个页面的正文内容中有一个产品标识符<span class="codeph"> 910XT </span>。 当此选项<i>未</i>被选中时，在搜索<span class="codeph"> 910XT </span>时，<span class="keyword">AdobeSearch&amp;Promote</span>会查找此产品标识符的匹配项。 在<span class="uicontrol">“搜索连接 — Div — 启用</span>”打开的情况下，<span class="keyword">AdobeSearch&amp;Promote</span>还会找到<span class="codeph"> 910 XT </span>。 但是，它不会只找到<span class="codeph"> 910 </span>或<span class="codeph"> XT </span>的实例。 </p> <p>当您选择<span class="uicontrol">部分字母数字匹配</span>时，索引器会将这些混合字母数字令牌分为多个令牌。 例如，将产品标识符（如<span class="codeph"> XYZ123 </span>）索引到三个令牌中：<span class="codeph"> XYZ123 </span>、<span class="codeph"> XYZ </span>和<span class="codeph"> 123 </span>。 此类功能允许在任何这些变体上进行搜索时自由文本匹配。 </p> <p>在另一个示例中，假设您具有产品标识符<span class="codeph"> AB910XT </span>。 如果选择<span class="uicontrol">部分字母数字匹配</span> <i>和</i>的<span class="uicontrol">已打开搜索连接 — Div — 启用</span>,<span class="keyword">AdobeSearch&amp;Promote</span>将其索引为<span class="codeph"> AB910XT </span>和<span class="codeph"> AB </span>、<span class="codeph"> 910 </span>和<span class="codeph"> XT </span>。 然后，例如，当用户搜索<span class="codeph"> 910XT </span>时，搜索会扩展以同时查找<span class="codeph"> 910XT </span>、<span class="codeph"> 910 </span>或<span class="codeph"> XT </span>的实例。 </p> <p> <p>注意： <span class="uicontrol">默认情况下，未启用搜索连接 — Div — 启用</span>。 请联系技术支持以激活该功能以供您使用。 </p> </p> <p> <p>注意： <span class="uicontrol">部分字母数字匹配</span>将全局应用于所有索引字段。 但是，它只影响自由文本匹配；它不会影响精确匹配或范围匹配。 </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>相似声音匹配 </p> </td> 
      <td colname="col2"> <p>默认选中。 </p> <p>声音相似的词语是相配的，如"健康"和"健康"。 尽管拼写错误，但客户仍可轻松搜索。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>备用字Forms </p> </td> 
      <td colname="col2"> <p>默认值为<b>默认备用字Forms</b>。 </p> <p>您可以在“替代单词Forms”下拉列表中从以下选项中进行选择： 
      <ul id="ul_CAC73FB4D1384312BB5DD327D3D66948"> 
      <li id="li_F4E76CD27EA34AC5BC81E648BC6CBA4C"><b>None</b> <p>在索引过程中不应用词干或替代词表单。 </p> </li> 
      <li id="li_3186FD1F3BC94A5CB66FFF8EA6726D81"><b>默认替代字Forms</b> <p>在索引过程中会自动完成词干。 </p> </li> 
      <li id="li_5815DE0795E0423C9C84C62B96A3F841"><b>域词典</b> <p>您设置为词干词典的任何域词典都将用作替代词形的源。 </p> <p>请参阅<a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" type="concept" format="dita" scope="local">关于字典</a>。 </p> <p>请参阅<a href="../c-about-linguistics-menu/c-about-dictionaries.md#task_541E8453A12F4A8E89CF6F595469F074" type="task" format="dita" scope="local">将词典配置为词干词典</a>。 </p> </li> 
      </ul> </p> <p>如果在<span class="keyword">AdobeSearch&amp;Promote</span>中启用了短语词干，请注意，短语中也会出现替代词形式。 </p> <p>请参阅<a href="../c-searchpromote-release-notes/c-rn-06-19-14-version-815.md#concept_E8CEBC65A28A4E61BDE69B4B4DA55E73" format="dita" scope="local">Search&amp;Promote8.15.0发行说明(6/19/2014)</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>语言 </p> </td> 
      <td colname="col2"> <p>默认值为<b>英语（美国）</b>。 </p> <p>所选语言确保根据世界所选部分使用的惯例分析日期和数值。 </p> <p>当<span class="uicontrol">替代单词Forms </span>设置为<span class="uicontrol">默认替代单词Forms </span>或设置为<span class="uicontrol">域词典</span>时，单词形式和词尾会根据所选语言的语言规则而改变。 </p> <p>默认情况下，“语言”设置不用于确定从您的网站读取的页面的语言。 读取页面的语言由其HTTP头或页面本身的元标记确定。 您的网站可能包含多种不同语言的页面。 无论此处选择的语言如何，都可以正确阅读和索引每个页面。 </p> <p>如果对网站上的某些页面使用Unicode字符集编码（如UTF-8），请确保正确指定了这些页面的语言。 如果Unicode文档不存在相应的HTTP头或元标记，则可以使用<span class="uicontrol">设置</span> &gt; <span class="uicontrol">元数据</span> &gt; <span class="uicontrol">注入</span>来指定相应的语言。 </p> <p>选中<span class="uicontrol">应用于没有指定语言的文档? </span> 对从您的网站读取的没有明确设置的页面使用语言设置。当您的文档中只有<i>某些</i>没有语言设置时，请使用此设置。 如果您的文档的<i>没有</i>具有语言设置，或者受影响的文档集是众所周知且可管理的小列表，请使用<span class="uicontrol">设置</span> &gt; <span class="uicontrol">元数据</span> &gt; <span class="uicontrol">注入</span>。 </p> <p>请参阅<a href="../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5" type="concept" format="dita" scope="local">关于Injections </a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>使用反编译器？ </p> </td> 
      <td colname="col2"> <p> <p>注意： 此功能仅用于丹麦语和德语。 此外，默认情况下不启用此功能。 请联系技术支持以激活该功能以供您使用。 启用后，<b>使用Decompounder?</b> 选项仅在您从此表前面所述的“语 <span class="uicontrol"> 言”下 </span> 拉 <span class="uicontrol"> 式列表 </span> 中选 <span class="uicontrol"> 择丹麦语或德 </span> 语时才显示在用户界面中。 </p> </p> <p>当您选择<span class="uicontrol">使用Decompounder时？ </span>，该服务将丹麦语或德语复合词分解，允许在原始复合词的同时索引组件词。 </p> <p>要了解此功能的工作方式，请在文本字段中输入单词，然后单击<span class="uicontrol">测试</span>。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Save Settings]**.
1. 要预览更改的结果，请单击&#x200B;**[!UICONTROL regenerate your staged site index]**&#x200B;以重新构建分阶段网站索引。
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。
