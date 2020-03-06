---
description: 您可以使用“单词和语言”来确定如何将搜索词与网页内容相匹配。
seo-description: 您可以使用“单词和语言”来确定如何将搜索词与网页内容相匹配。
seo-title: 关于单词和语言
solution: Target
title: 关于单词和语言
topic: Linguistics,Site search and merchandising
uuid: 793d7a40-4609-44b8-a170-536eb1434537
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# 关于单词和语言{#about-words-language}

您可以使 [!DNL Words & Language] 用来确定如何将搜索词与网页内容相匹配。

## 使用单词和语言 {#concept_CEB4B9576F3C4E2EB87B352EEC738D79}

在设置的效果 [!DNL Words & Language] 对站点访客可用（包括您对这些设置所做的任何更改）之前，您必须重新生成站点索引。 与索引不同，重新生成不涉及搜索网页，只需几秒钟。

## 配置搜索词与Web内容的匹配方式 {#task_351A9144A51F4B41923BDBACDEF3B616}

您可以使用“单词和语言”来确定网站搜索／销售如何将搜索词与网页内容相匹配。

<!-- 

t_configuring_how_search_terms_matched_to_your_web_content.xml

 -->

**配置搜索词与Web内容的匹配方式**

1. 在产品菜单中，单击 **[!UICONTROL Linguistics]** > **[!UICONTROL Words & Language]**。
1. 在页 [!DNL Words & Languages] 面上，设置所需的选项。

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
      <td colname="col2"> <p>默认情况下未选中。 </p> <p>确定是否区分大写字母和小写字母。 例如，选择“成功”时，会将“成功”与“成功”区分开来，并且搜索结果可能因两者而异。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>音调符号敏感度 </p> </td> 
      <td colname="col2"> <p>默认选中。 </p> <p> 确定包含变音符的单词是否与不包含变音符的单词区分开来。 例如，当选择“pagina”时，会将“página”与“página”区分开来。 如果您的网站使用非英语语言，请取消选择此选项。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>数字 </p> </td> 
      <td colname="col2"> <p>默认选中。 </p> <p>确定是否对包含数字的单词进行索引。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>忽略撇号 </p> </td> 
      <td colname="col2"> <p>默认情况下未选中。 </p> <p>从查询中删除撇号。 例如，搜索“Tree's”将返回与搜索“Trees”相同的结果。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>忽略连字符 </p> </td> 
      <td colname="col2"> <p>默认情况下未选中。 </p> <p>从查询中删除连字符。 例如，搜索“blue-bell”将返回与搜索“bluebell”相同的结果。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>部分字母数字匹配 </p> </td> 
      <td colname="col2"> <p>默认情况下未选中。 </p> <p>选择此选项后，您可以在字母数字转换上拆分令牌，以允许部分或产品令牌上的自由文本匹配。 </p> <p>例如，假定您在网站上一个或多个页面的正文 <span class="codeph"> 内 </span> 容中具有910XT的产品标识符。 如果未选择此 <i>选项</i> , <span class="keyword"> Adobe Search&amp;Promote在搜索 </span> 910XT时会查找此产品标识符的 <span class="codeph"> 匹配项 </span>。 而且，在 <span class="uicontrol"> 打开“启用搜索” </span> 后， <span class="keyword"> Adobe Search&amp;Promote还 </span> 会找到 <span class="codeph"> 910 XT </span>。 但是，它不会只找到910或 <span class="codeph"> XT的 </span><span class="codeph"></span> 实例。 </p> <p>当您选择“部分字 <span class="uicontrol"> 母数字匹配” </span>时，索引器会将这些混合字母数字令牌分为多个令牌。 例如，将产品标识符(如 <span class="codeph"> XYZ123)索引 </span> 到三个令牌中： <span class="codeph"> XYZ 123 </span>、 <span class="codeph"> XYZ </span>和 <span class="codeph"> 123 </span>。 这种功能允许在任何这些变体上进行搜索时间自由文本匹配。 </p> <p>在另一个示例中，假定您的产品标识符 <span class="codeph"> 为AB910XT </span>。 如果选择“部分字 <span class="uicontrol"> 母数字匹配”，并打开 </span> “搜索关联- <i></i><span class="uicontrol"></span><span class="keyword"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span>Concat-Adobe”索引，将其作为AB91XT,AB引导，AB引导，90个引导，并且已经打开Div,Div的搜索引起Adobe索引。 然后，当用户搜索 <span class="codeph"> 910XT时 </span>，搜索会展开以同时查找 <span class="codeph"> 910XT、910或 </span><span class="codeph"></span><span class="codeph"></span>XT的实例。 </p> <p> <p>注意： 默 <span class="uicontrol"> 认情况下，“搜索连接 </span> -Div-启用”未启用。 请联系技术支持以激活该功能供您使用。 </p> </p> <p> <p>注意： “部 <span class="uicontrol"> 分字母数字匹 </span> 配”将全局应用于所有索引字段。 但是，它只影响自由文本匹配；它不会影响精确匹配或范围匹配。 </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>相似声音匹配 </p> </td> 
      <td colname="col2"> <p>默认选中。 </p> <p>类似声音的词语，如“健康”和“健康”。 尽管单词拼写错误，但此功能使客户能轻松搜索。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>替代Word表单 </p> </td> 
      <td colname="col2"> <p>默认为“ <b>默认替代字表单”</b>。 </p> <p>您可以从“备用单词表单”下拉列表中选择以下选项： 
      <ul id="ul_CAC73FB4D1384312BB5DD327D3D66948"> 
      <li id="li_F4E76CD27EA34AC5BC81E648BC6CBA4C"><b>None</b> <p>在索引过程中不应用词干或替代单词表单。 </p> </li> 
      <li id="li_3186FD1F3BC94A5CB66FFF8EA6726D81"><b>默认替代字表单</b> <p>在索引过程中会自动完成词干提取。 </p> </li> 
      <li id="li_5815DE0795E0423C9C84C62B96A3F841"><b>域词典</b> <p>您设置为词干词典的任何域词典都将用作替代单词表单的源。 </p> <p>请参 <a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" type="concept" format="dita" scope="local"> 阅关于字典 </a>。 </p> <p>请参 <a href="../c-about-linguistics-menu/c-about-dictionaries.md#task_541E8453A12F4A8E89CF6F595469F074" type="task" format="dita" scope="local"> 阅将词典配置为词干词典 </a>。 </p> </li> 
      </ul> </p> <p>如果在 <span class="keyword"> Adobe Search&amp;Promote中启用了短语词干，请注意 </span>替代单词表单也会出现在短语中。 </p> <p>请参 <a href="../c-searchpromote-release-notes/c-rn-06-19-14-version-815.md#concept_E8CEBC65A28A4E61BDE69B4B4DA55E73" format="dita" scope="local"> 阅Search&amp;Promote 8.15.0发行说明(2014/6/19) </a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>语言 </p> </td> 
      <td colname="col2"> <p>默认为 <b>英语（美国）</b>。 </p> <p>所选语言确保根据世界所选部分使用的惯例分析日期和数值。 </p> <p>当“替 <span class="uicontrol"> 代单词表单”设 </span><span class="uicontrol"></span><span class="uicontrol"></span>置为“默认替代单词表单”或“域词典”时，单词表单和单词结尾会根据所选语言的语言规则而发生变化。 </p> <p>默认情况下，“语言”设置不用于确定从您的网站读取的页面的语言。 读取页面的语言由其HTTP头或页面本身中的元标记确定。 您的网站可能包含多种不同语言的页面。 无论此处选择的语言如何，都可以正确阅读和索引每个页面。 </p> <p>如果对网站上的某些页面使用Unicode字符集编码（如UTF-8），请确保正确指定每个页面的语言。 如果Unicode文档不存在相应的HTTP头或元标记，则可以使用 <span class="uicontrol"> “设置” </span> &gt; <span class="uicontrol"> “元数据” </span> &gt; <span class="uicontrol"> “注入” </span> 指定相应的语言。 </p> <p>选中“ <span class="uicontrol"> 应用于没有指定语言的文档”? </span> 对从您的网站读取的没有明确设置的页面使用“语言”设置。 仅在某些文档 <i>没有语言</i> 设置时，使用此设置。 如果您的 <span class="uicontrol"> 文档没有语言设 </span> 置，或者您的文档包含一组众所周知、规模 <span class="uicontrol"></span><span class="uicontrol"></span><i></i> 可管理的小列表，请使用“设置” &gt; “元数据” &gt; “注入”。 </p> <p>请参 <a href="../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5" type="concept" format="dita" scope="local"> 阅注射 </a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>使用反编译程序？ </p> </td> 
      <td colname="col2"> <p> <p>注意： 此功能仅用于丹麦语和德语。 此外，默认情况下不启用此功能。 请联系技术支持以激活该功能供您使用。 启用后，使用反编 <b>译程序？</b> 选项仅在您从此表前面所述的“语言”下拉 <span class="uicontrol"> 列表中选 </span> 择“丹麦语”或“ <span class="uicontrol"> 德语” </span> 时，才 <span class="uicontrol"></span> 会显示在用户界面中。 </p> </p> <p>当您选择“使 <span class="uicontrol"> 用反编译器”时？ </span>，该服务将分解丹麦语或德语复合词，这允许将组件词与原始复合词一起索引。 </p> <p>要了解此功能的工作方式，请在文本字段中输入单词，然后单击“测 <span class="uicontrol"> 试” </span>。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Save Settings]**.
1. 要预览更改的结果，请单击以重 **[!UICONTROL regenerate your staged site index]** 新构建分阶段的网站索引。
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

