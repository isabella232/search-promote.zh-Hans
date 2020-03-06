---
description: 您可以使用字典来管理字典的集合及其关联的同义词和同义词。
seo-description: 您可以使用字典来管理字典的集合及其关联的同义词和同义词。
seo-title: 关于词典
solution: Target
title: 关于词典
topic: Linguistics,Site search and merchandising
uuid: d4463896-30fe-4385-a283-c930c8264a02
translation-type: tm+mt
source-git-commit: 4531970404c189ffa1d4359d1431c97df893ba35

---


# 关于词典{#about-dictionaries}

您可以使用字典来管理字典的集合及其关联的同义词和同义词。

## 使用词典 {#concept_B8028B71EC8144669614C64578EDB034}

同义词是指具有相同或相似含义的词，如裤子、牛仔裤、裤子和长裤，或者购买、购买、获取和订购。

地名是单向的同义词，在同义词不合适时提供解决方案。 例如，服装零售网站的首要搜索词是“pants”。 但是，搜索结果中不显示牛仔裤。 在这种情况下，您可以使用混音将牛仔裤和裤子关联起来，但允许搜索牛仔裤以仅返回牛仔裤。 使用混音字还可以为终止产品或竞争条款提供匹配。 此策略确保对其他搜索结果的影响最小。 例如，如果“S2000”产品已停止，且“S3000”是其后继名，则使用hyponym而不是同义词来确保“S3000”的搜索结果不包含任何杂散的“S2000”结果。

当客户输入网页上不存在的非精确匹配术语时，同义词和hyonomys帮助客户查找相关的搜索结果。 例如，如果整个网站都使用“裤子”一词，您可以创建将“裤子”和“裤子”结合在一起的同义词。 反之，当客户搜索“裤子”时，将返回与裤子相关的搜索结果。

同义词和同义词作为域词典分组在一起。 这些是您为特定主题或目的创建的特殊词典。

“词典菜单”页列出您的帐户当前已定义的所有域词典。 在此主页中，您可以重命名、编辑、删除或启用和禁用域词典。

## 理解同义词和同义符号 {#section_B459CCB850974F4FB16A14E489BBBEC0}

下图是一组同义词和同义词关系的术语的示例。

![](assets/synonym1.png)

明确定义了6个主要的同义词关系。 每个术语以等号(=)分隔。

* “汽车”是汽车的代名词。
* &quot;轿车&quot;是轿车的代名词。
* &quot;货车&quot;是房产的代名词。
* “ASP”是Active Server Pages和Application Service提供商的同义词。
* “购买”、“购买”和“采购”是彼此的同义词。
* “US”、“USA”和“United States of America”是彼此的同义词。

包含单个单词的行是纯同义词。 具有可扩展树的行形成混合关系。 在示例中，第二棵树将轿车、轿车、货车和房产定义为汽车和汽车的假名。 相反，汽车和汽车是树中其余术语的超链接。

第三棵树将汽车和摩托车定义为汽车的假名。

您可以在每个同义词中包含多个首字母缩略词和／或多词扩展，如上面的“US”同义词示例所示。 当单词或首字母缩略词具有多个含义时，请为每个含义创建一个同义词，如上面的“ASP”示例中所示。 通过添加多个同义词，您可以确保搜索“应用程序服务提供者”时不会返回“活动服务器页”的搜索结果。

“地名”不会随其他地名而扩展。 地名的同义词最多只会扩展一个级别。 例如，搜索“vehicle”将返回“car”和“automabile”的结果，但不返回“sedan”和“tastion wagon”的结果。

## 关于跨词典搜索术语 {#section_28E7F80CE68D4481BBF4F51EED237C67}

您可以在您添加的所有词典中搜索地名和同义词。 此功能非常有用，因为您希望编辑或删除可能存在于多个词典中的特定术语。 每个具有匹配结果的字典都显示有其匹配的字集。 如果查询返回的集数超过1000个，则只显示前1000个集合或树。

请参 [阅跨字典搜索](../c-about-linguistics-menu/c-about-dictionaries.md#task_8D2BACC6F9B4487FA82367CBEDEE306F)。

请参 [阅编辑词典](../c-about-linguistics-menu/c-about-dictionaries.md#task_7B349B2D385048D7A06E754FAB75316A)。

## 关于将词典配置为词干词典 {#section_B859E2E957674F558AC6F8D05A0ED190}

词干，即搜索可以有多个结尾的词的根的能力，可以在以下三种模式之一中运行：域词典、默认替代单词表单和无。

请参阅 [关于单词和语言](../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79)。

以下信息假定您的帐户已 **[!UICONTROL Alternative Word Forms]** 设置为 **[!UICONTROL Domain Dictionaries]**，以便您可以将特定域词典配置为源。

你可以把任何域词典变成&quot;词干词典&quot; 它的同义词和地名继续按预期扩大，但还有其他副作用。 如果在另一本词典甚至本身中找到任何通用术语，它就会将其词组与这些同义词或同义词合并。 你可以把它看成另一个级别的词扩展。

如果没有词干、同义词和hyonomis，则必须冗长而完整，将每个相关单词列为成员。

以下是同义词和无词干的示例：

* 同义词：慢速=正在运行
* 对“慢速”的查询会生成带有“running”和“jog”字样的文档。
* 对“运行”的查询会生成与“慢速”相同的文档。
* 没有“jog”和“running”的网页，但有“runs”和“run”等其他单词表单的网页在查询结果中缺失。

在此示例中，除非查询词是特定同义词或同义词的成员，否则该词不展开。

以下是同义词和词干的示例：

* 同义词：慢速=正在运行
* 词干词典中的同义词条目：运行=运行=运行
* 查询“jog”或“running”将返回所有包含“runs”、“running”、“run”和“jog”字样的网页。
* “runs”和“run”的查询返回相同或类似的结果。

在本例中，词干词典的同义词能够将其组对等词与至少一个词的任何其他词典中的任何其他同义词或同义词合并。

指定词数过多的字典可能会产生性能影响。 您应将域词典指定为词干词典。 在搜索过程中，词干还可以创建意想不到的词扩展，并使调试和跟踪词扩展的过程变得复杂。

请参 [阅将词典配置为词干词典](../c-about-linguistics-menu/c-about-dictionaries.md#task_541E8453A12F4A8E89CF6F595469F074)。

## Adding a new dictionary {#task_F31AC6723E894C4F91D12AB2A4CEE9FB}

您可以添加新的同义词和同义词词典，以帮助客户找到相关的搜索结果。 当客户输入的术语与网页上可能不存在的术语不精确匹配时，此功能特别有用。

另请参阅 [添加新业务规则](../c-about-rules-menu/c-about-business-rules.md#task_BD3B31ED48BB4B1B8F1DCD3BFA2528E7)。

**添加新词典**

1. 在产品菜单中，单击 **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]**。
1. 在页面 **[!UICONTROL Dictionary Menu]** 上，单击 **[!UICONTROL Add New Dictionary]**。
1. 在页 **[!UICONTROL Dictionary]** 面上的字 **[!UICONTROL Name]** 段中，输入新词典的名称。
1. 单击 **[!UICONTROL Add Synonyms]**.
1. 在对 **[!UICONTROL Add Terms]** 话框中，执行下列操作之一：

   * 要添加同义词，请在主文本字段中输入两个或多个术语，每个单词或短语之间用等号(=)分隔。 例如，裤子=裤子=宽松裤。
   * 要添加地名，请在主文本字段中输入超名词。 单 **[!UICONTROL Add Hyponym]**&#x200B;击，然后输入与您输入的超链接相关的hyponym。 例如，“轿车”、“轿车”、“旅行车”和“房产”可以是“汽车”和“汽车”（两者都是超大号）的假名，如下所示。

      ![](assets/synonym2.png)

      Hyponym条目还可以形成“sedan”和“saloon”等同义词。

1. 单击 **[!UICONTROL Save]**.
1. 执行以下操作之一：

   * 重复第4-6步，以添加更多同义词和同义词。
   * 继续下一步。

1. 要预览更改的结果，请单击以重 **[!UICONTROL regenerate your staged site index]** 新构建分阶段的网站索引。

   请参 [阅运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   请参 [阅运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. （可选）在产品菜单上，单击 **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]**，然后执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 启用或禁用词典 {#task_EC282EA0846942F6913918EA8218220B}

每个单词的关系在您为网站编制索引时生成。 在下一个索引操作之前，您可以打开或关闭已添加的任何词典。

**启用或禁用词典**

1. 在产品菜单中，单击 **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]**。
1. 在页 **[!UICONTROL Dictionary Menu]** 面上，在表的 **[!UICONTROL Enabled]** 列下，执行下列操作之一：

   * 选中要打开并已编制索引的词典的框。
   * 取消选中要关闭但尚未索引的词典的框。

1. 单击 **[!UICONTROL Save Changes]**.
1. 要预览更改的结果，请单击以重 **[!UICONTROL regenerate your staged site index]** 新构建分阶段的网站索引。

   请参 [阅运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   请参 [阅运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. （可选）在产品菜单上，单击 **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]**，然后执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 编辑词典 {#task_7B349B2D385048D7A06E754FAB75316A}

您可以编辑或删除组成特定词典的同义词和hyponym组。

<!-- 

t_editing_a_dictionary.xml

 -->

您还可以使用 **[!UICONTROL Find]** 查找要在所有词典中编辑或删除的特定同义词和同义词。

**编辑词典**

1. 在产品菜单中，单击 **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]**。
1. 执行以下操作之一：

   * 在页 [!DNL Dictionary Menu] 面的表中，单击要编辑或删除其术语的单个词典的超链接名称。
   * 在页 [!DNL Dictionary Menu] 面的文本字 **[!UICONTROL Find]** 段中，键入要在所有词典中查找的术语，然后单击 **[!UICONTROL Find]**。

      在页 [!DNL Find in Dictionaries] 面中，使用随附的下拉列表设置所需的细化选项。

      <table> 
      <thead> 
        <tr> 
        <th colname="col1" class="entry"> <p>选项 </p> </th> 
        <th colname="col2" class="entry"> <p>描述 </p> </th> 
        </tr> 
      </thead>
      <tbody> 
        <tr> 
        <td colname="col1"> <p>查找 </p> </td> 
        <td colname="col2"> <p>允许您输入要在所有词典中搜索的词。 </p> </td> 
        </tr> 
        <tr> 
        <td colname="col1"> <p>匹配下拉列表 </p> </td> 
        <td colname="col2"> <p>允许您从以下四种类型的匹配中进行选择： 
        <ul id="ul_D656F159677946938050115F610EEF4B"> 
        <li id="li_2D6B302E021A4CE7A47F028812633EDC"> <span class="uicontrol"> 精确匹配 </span> <p>查询必须与同义词或同义词完全匹配。 </p> </li> 
        <li id="li_30AD5976E43041E98190F4757E821092"> <span class="uicontrol"> 包含文本 </span> <p>查询只需要一个子字符串匹配；同义词或同义词中的匹配。 </p> </li> 
        <li id="li_9BF911EFB54345BB82679BDE51DDF8AF"> <span class="uicontrol"> 开始于 </span> <p>查询仅与每个子名和同义词的开头匹配。 </p> </li> 
        <li id="li_CB791C7F5B5A4496B329ED505E7D97BC"> <span class="uicontrol"> Word匹配 </span> <p>查询与同义词或同义词中的每个单词进行比较，但该单词必须完全匹配。 </p> </li> 
        </ul> </p> </td> 
        </tr> 
        <tr> 
        <td colname="col1"> <p>启用／禁用词典下拉列表 </p> </td> 
        <td colname="col2"> <p>允许您从以下选项中进行选择： 
        <ul id="ul_EBBD3F3A2D854952A35CBDDBECB40958"> 
        <li id="li_7F5654C284BE485EAC9B000A663C6C60"> <span class="uicontrol"> 启用和禁用词典 </span> <p>在已启用和已禁用的词典中搜索指定的术语。 </p> </li> 
        <li id="li_4A83EECF38044287A923EC0AAF639079"> <span class="uicontrol"> 仅启用词典 </span> <p>仅搜索启用的词典有助于调试当前索引。 </p> </li> 
        </ul> </p> <p>请参 <a href="../c-about-linguistics-menu/c-about-dictionaries.md#task_EC282EA0846942F6913918EA8218220B" type="task" format="dita" scope="local"> 阅启用或禁用词典 </a>。 </p> </td> 
        </tr> 
        <tr> 
        <td colname="col1"> <p>分阶段／实时下拉列表 </p> </td> 
        <td colname="col2"> <p>允许您从以下选项中进行选择： 
        <ul id="ul_BD0733A30E6B470E942B21F499A4373B"> 
        <li id="li_F9A8C39C22EA4FBF86536F5924ED973C"> <span class="uicontrol"> 暂存／实时词典 </span> <p>在分阶段和实时词典中搜索指定术语。 但是，仅在词典存在时搜索分阶段版本。 如果分阶段版本不存在，则搜索词典的实时版本。 </p> </li> 
        <li id="li_DB0944DB18564269AA10676BDFDB0460"> <span class="uicontrol"> 实时词典 </span> <p>仅在实时词典中搜索指定术语。 </p> </li> 
        </ul> </p> </td> 
        </tr> 
      </tbody> 
      </table>

1. 在表中，执行下列操作之一：

   * 单 ![](assets/icon_edit.gif) 击与要更新的术语关联的术语。 在对 **[!UICONTROL Edit Terms]** 话框中，更改所需的术语。 完成后，单击 **[!UICONTROL Save]**。

   * 单 ![](assets/icon_delete.gif) 击与要删除的词关联的词。 在对话 **[!UICONTROL Delete Terms]** 框中，单击 **[!UICONTROL Delete]**。 请务必删除正确的术语；没有删除确认对话框。

1. 要预览更改的结果，请单击以重 **[!UICONTROL regenerate your staged site index]** 新构建分阶段的网站索引。

   请参 [阅运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   请参 [阅运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. （可选）在产品菜单上，单击 **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]**，然后执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 重命名词典 {#task_7F1F372B337B4853BFA2A60AD267B092}

您可以更改已添加的词典的名称。

<!-- 

t_renaming_a_dictionary.xml

 -->

如果将选项 **[!UICONTROL Alternate Word Forms]** 设置为 **[!UICONTROL Domain Dictionaries]** “入” **[!UICONTROL Words & Language]**，则使用 **[!UICONTROL Configure]** 该选项代替 **[!UICONTROL Rename]**。

请参阅 [关于单词和语言](../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79)。

**重命名词典**

1. 在产品菜单中，单击 **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]**。
1. 在页 **[!UICONTROL Dictionary Menu]** 面上，在表的 **[!UICONTROL Actions]** 列下，执行下列操作之一：

   * 单 **[!UICONTROL Rename]** 击以查看要更改其名称的关联词典。

      中。 **[!UICONTROL Rename Dictionary]** 在字 **[!UICONTROL Name]** 段中，输入词典的新名称。

      单击 **[!UICONTROL Rename File]**.

   * 单 **[!UICONTROL Configure]** 击以查看要更改其名称的关联词典。

      中。 **[!UICONTROL Configure Dictionary]** 在字 **[!UICONTROL Name]** 段中，输入词典的新名称。

      单击 **[!UICONTROL Save Configuration]**.

1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 将词典配置为词干词典 {#task_541E8453A12F4A8E89CF6F595469F074}

您可以将词典设置为高级词干模式以利用搜索中的词干。

<!-- 

t_configuring_a_dictionary_as_a_stemming_dictionary.xml

 -->

这种模式会返回与客户正在搜索的内容的变体匹配的网页。

请参 [阅关于字典](../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034)。

请参阅 [关于单词和语言](../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79)。

**将词典配置为词干词典**

1. 在产品菜单中，单击 **[!UICONTROL Linguistics]** > **[!UICONTROL Words & Language]**。
1. 在页 [!DNL Words & Languages] 面的下拉列 **[!UICONTROL Alternate Words Forms]** 表中，选择 **[!UICONTROL Domain Dictionaries]**。

   任何设置为词干词典的域词典（请参阅下面的步骤7）都用作替代词表单的源。

1. 单击 **[!UICONTROL Save Changes]**.
1. 在产品菜单中，单击 **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]**。
1. 在页 [!DNL Dictionaries Menu] 面上，在表的 **[!UICONTROL Actions]** 列下，单击以查找要设置为词干词典的 **[!UICONTROL Configure]** 关联词典。
1. 在对 **[!UICONTROL Configure Dictionary]** 话框的下拉列 **[!UICONTROL Advanced Stemming Mode]** 表中，选择 **[!UICONTROL Yes]**。
1. 单击 **[!UICONTROL Save Configuration]**.
1. 单击 **[!UICONTROL regenerate your staged site index]** 以重新构建分阶段的网站索引。

   请参 [阅运行实时或分阶段网站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   请参 [阅运行实时或分阶段网站的增量索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. （可选）在产品菜单上，单击 **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]**，然后执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 跨字典搜索 {#task_8D2BACC6F9B4487FA82367CBEDEE306F}

您可以在添加到站点搜索／销售的所有词典中搜索地名和同义词。

<!-- 

t_searching_across_dictionaries.xml

 -->

此功能非常有用，因为您希望编辑或删除可能存在于多个词典中的特定术语。 每个具有匹配结果的字典都显示有其匹配的字集。 如果查询返回的集数超过1000个，则只显示前1000个集合或树。

请参 [阅编辑词典](../c-about-linguistics-menu/c-about-dictionaries.md#task_7B349B2D385048D7A06E754FAB75316A)。

**要在字典中搜索**

1. 在产品菜单中，单击 **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]**。
1. 在页 [!DNL Dictionary Menu] 面的文本字 **[!UICONTROL Find]** 段中，键入要在所有词典中查找的术语，然后单击 **[!UICONTROL Find]**。
1. 在页 [!DNL Find in Dictionaries] 面中，使用随附的下拉列表设置所需的任何细化选项。

   请参 [阅编辑词典](../c-about-linguistics-menu/c-about-dictionaries.md#task_7B349B2D385048D7A06E754FAB75316A)。
1. （可选）使 **[!UICONTROL Show]** 用下拉列表指定每页要显示的最大结果数。

## 删除词典 {#task_DBAAEE624BC14D2590444B0B7869ECCA}

您可以删除不再需要或使用的词典。

<!-- 

t_deleting_a_dictionary.xml

 -->

如果删除的是实时词典，则该词典将暂存为删除。 如果删除已暂存的词典，则该词典将立即删除。

请务必删除您知道更需要的词典；没有可用于还原删除的历史记录功能。

**删除词典**

1. 在产品菜单中，单击 **[!UICONTROL Linguistics]** > **[!UICONTROL Dictionaries]**。
1. 在页 [!DNL Dictionary Menu] 面上，在表的 **[!UICONTROL Actions]** 列下，单击要删 **[!UICONTROL Delete]** 除的关联词典。
1. 中。 **[!UICONTROL Delete Dictionary]** click **[!UICONTROL Yes]** to confirm the deletion.
1. （可选）如果删除了活动词典，请执行下列操作之一：

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

