---
description: 您可以定义在您的网站上使用的常见短语，这样客户在输入搜索查询时，就无需在您定义的任何短语周围输入引号。
seo-description: 您可以定义在您的网站上使用的常见短语，这样客户在输入搜索查询时，就无需在您定义的任何短语周围输入引号。
seo-title: 关于常用短语
solution: Target
title: 关于常用短语
topic: Linguistics,Site search and merchandising
uuid: 0f980a22-d826-4476-97de-0e9c14549bc8
translation-type: tm+mt
source-git-commit: 8efa90ac2927b263b7d48ccbf25d4b0e917dac79
workflow-type: tm+mt
source-wordcount: '1216'
ht-degree: 1%

---


# 关于常用短语{#about-common-phrases}

您可以定义在您的网站上使用的常见短语，这样客户在输入搜索查询时，就无需在您定义的任何短语周围输入引号。

## 使用常用短语{#concept_4946E53586DF492EAEB1B7F757FD440F}

>[!NOTE]
>
>“通用短语”功能不显示在用户界面中，因为默认情况下未启用它。 请与技术支持联系以激活此功能供您使用。

常见短语是在客户搜索过程中识别的多词短语的集合。 它将短语视为一组词而不是单个词。 当客户在您的网站上进入搜索查询时，他们可以通过用多次引号将词引起来来识别短语，如“太平洋”。 但是，当您添加常用短语组时，将自动为客户执行报价步骤，因为客户在搜索查询中找到匹配的短语。

例如，假定网站的客户输入以下搜索查询:

`hotels near the pacific ocean`

如果不在`pacific ocean`周围添加引号，客户的搜索结果将返回位于世界任何海洋附近的酒店，而这并非客户的期望。

但是，当您添加常用短语“太平洋”时，其搜索查询会自动转换为以下内容：

`hotels near the "pacific ocean"`

使用常见短语并不妨碍客户在单词短语周围使用引号，相反，当在其搜索查询中找到定义的短语时，它只会添加引号。

此搜索查询扩展适用于后端搜索CGI参数`sp_q`和`sp_q_#`,

请参见[后端搜索CGI参数](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)中的表行25、26和32。

## 添加公用短语组{#task_35C84FABCD9042C5B48C5C788B752871}

您可以添加“常用短语组”，以确保搜索查询准确返回具有客户键入的所有单词的网页（确切顺序和接近度）。

添加“常用短语组”时，可以使用“常用短语组”主页上的“查找”功能。 通过“查找”功能，您可以搜索现有短语并找出它所在的组。

请参阅[查找包含短语](../c-about-linguistics-menu/c-about-common-phrases.md#task_20714969274740A7BB4DC71E705EA15E)中特定词的组。

**添加常用短语组**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**。
1. 在[!DNL Common Phrases Groups]页面上，单击&#x200B;**添加短语组**。
1. 在[!DNL Add Common Phrase Group]页面上，设置所需的选项，并添加组成该组的所有短语。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>群组名称 </p> </td> 
      <td colname="col2"> <p>必需。 </p> <p>公用短语组的唯一名称。 </p> <p>如果您稍后编辑公用短语组，请注意，您无法更改组名称。 要更改组名称，请使用<span class="uicontrol">重命名</span>功能。 </p> <p>请参阅<a href="../c-about-linguistics-menu/c-about-common-phrases.md#task_168E07C59C0F40989D43E7010EFF22EB" format="dita" scope="local">重命名公用短语组</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>注释 </p> </td> 
      <td colname="col2"> <p>可选. </p> <p>添加与通用短语组相关的信息。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>短语 </p> </td> 
      <td colname="col2"> <p>必需。 </p> <p>允许您指定最多五个单词的短语。 要调整最大字数设置，请与技术支持联系。 </p> <p>您输入的每个短语在任何通用短语组中必须是唯一的。 </p> <p>使用“操作”列中的加号(+)和减号(-)图标可添加输入的短语或删除短语。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击&#x200B;**添加**。
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;以还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 测试常用短语{#task_A0C344E051CA45A9A0588242F9DA675D}

如果您选择了要与短语组关联的元数据字段，则可以测试特定短语的扩展。

在测试短语的扩展时，您会根据与短语组关联的元数据字段搜索精确的短语。 词组会被搜索，好像周围有引号。 所有其他元数据字段只搜索短语中的词，不带引号。 例如，假定您测试了短语`audi TT`。 返回的结果可能如下：

`title|body|field3:"Audi TT" url|desc|keys|target|alt:Audi TT`

**测试常用短语**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**。
1. 在[!DNL Common Phrases Groups]页面的&#x200B;**包含**&#x200B;文本字段的测试短语中，输入要测试其元数据扩展的短语。
1. 单击 **[!UICONTROL Test]**.

   展开结果显示在文本框中。
1. （可选）拖动文本框的右下角以展开显示区域。

## 在短语{#task_20714969274740A7BB4DC71E705EA15E}中查找包含特定单词的组

您可以使用[!DNL Find]在已添加的所有现有组中搜索短语中的特定单词。

当您使用“查找”时，它会定位以下内容：

* 在所有组中都找到完全相同的短语。
* 短语中的任何单词在所有组中，不管短语中的单词顺序和接近度如何。

另请参阅[编辑常用短语组](../c-about-linguistics-menu/c-about-common-phrases.md#task_5CAC3A133C5342EEAFE55A7EABCBCD61)。

**查找包含短语中特定词的组**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**。
1. 在[!DNL Common Phrases Groups]页面的&#x200B;**[!UICONTROL Find groups with phrases that contain]**&#x200B;文本字段中，输入短语。
1. 单击 **[!UICONTROL Find]**.

   结果将显示在文本框中。
1. （可选）执行下列操作之一或多项：

   * 拖动文本框的右下角以展开显示区域。
   * 在结果窗口中，单击超链接的短语以打开关联组的“编辑公用短语组”页。

## 编辑常用短语组{#task_5CAC3A133C5342EEAFE55A7EABCBCD61}

您可以编辑已添加的常用短语组的现有字段、备注和短语。 但是，要编辑组名称，必须使用[!DNL Rename]功能。

另请参阅[重命名公用短语组](../c-about-linguistics-menu/c-about-common-phrases.md#task_168E07C59C0F40989D43E7010EFF22EB)。

**编辑常用短语组**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**。
1. 在[!DNL Common Phrases Groups]页面上，单击组名称最右侧的&#x200B;**[!UICONTROL Edit]**。
1. 在[!DNL Edit Common Phrase Group]页面上，设置所需的选项。

   请参见[添加公用短语组](../c-about-linguistics-menu/c-about-common-phrases.md#task_35C84FABCD9042C5B48C5C788B752871)下的选项表。
1. 单击&#x200B;**保存更改**。
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;以还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 重命名公用短语组{#task_168E07C59C0F40989D43E7010EFF22EB}

您可以更改现有公用短语组的名称。 但是，如果要更改公用短语组的现有字段、备注和短语，则必须使用[!DNL Edit]功能。

请参阅[编辑常用短语组](../c-about-linguistics-menu/c-about-common-phrases.md#task_5CAC3A133C5342EEAFE55A7EABCBCD61)。

**重命名公用短语组**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**。
1. 在[!DNL Common Phrases Groups]页面上，单击组名称最右侧的&#x200B;**[!UICONTROL Rename]**。
1. 在[!DNL Rename Common Phrase Group]页面的&#x200B;**[!UICONTROL Group Name]**&#x200B;文本字段中，输入组的新名称。
1. 单击&#x200B;**重命名**。
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;以还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 删除公用短语组{#task_4106D282A2ED4A27B09EE5A8CAAEDA36}

您可以删除已添加的任何常见短语组。 如果误删除组，可使用[!DNL History]恢复组。

请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

**删除公用短语组**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**。
1. 在[!DNL Common Phrases Groups]页面上，单击组名称最右侧的&#x200B;**[!UICONTROL Delete]**。
1. 在[!DNL Delete Common Phrase Group]页面上，单击&#x200B;**[!UICONTROL Delete]**。
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;以还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

