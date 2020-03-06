---
description: 使用“预搜索规则”分析传入的查询并确定要使用的演示文稿模板。 预搜索规则是按顺序执行的，用于每个查询。 要更改规则的顺序，您可以使用拖放操作。 在保存之前，实际订单不会更改。
seo-description: 使用“预搜索规则”分析传入的查询并确定要使用的演示文稿模板。 预搜索规则是按顺序执行的，用于每个查询。 要更改规则的顺序，您可以使用拖放操作。 在保存之前，实际订单不会更改。
seo-title: 关于预搜索规则
solution: Target
title: 关于预搜索规则
topic: Rules,Site search and merchandising
uuid: e75f9d9e-e8ca-4184-bf79-b1fdadb5c0fe
translation-type: tm+mt
source-git-commit: d07cdc2c88f93eed4cecb0ee8818f7fdea06ee9d

---


# 关于预搜索规则{#about-pre-search-rules}

使用“预搜索规则”分析传入的查询并确定要使用的演示文稿模板。 预搜索规则是按顺序执行的，用于每个查询。 要更改规则的顺序，您可以使用拖放操作。 在保存之前，实际订单不会更改。

## 使用预搜索规则 {#concept_5BF84BB6FACB4645BA9CB7496A01CD1F}

“预搜索规则”通常用于选择哪个演示文稿模板根据传入的查询显示结果。 更高级的功能可用于更改用于为演示文稿模板进行搜索的查询。 您可以根据需要添加、删除或更改查询参数的值。 对于每个传入的查询，预搜索处理模块检查预搜索规则以确定查询是否被修改以及使用什么表示模板。 每个预搜索规则由两个主要元素组成：规则的操作和可选条件。 您可以指定不限数量的规则和条件。 这些规则的顺序很重要，因为规则集是逐个规则循环的。 当规则的条件匹配时，将执行所有关联的操作。

在“预搜索处理”模块中，所有定义的模板及其关联的命名搜索被实例化，其中每个搜索都被赋予cgi参数的本地副本。 因此，您可以通过添加、删除或更改搜索使用的cgi参数之一来自定义搜索，而不更改模板使用或影响任何其他模板的任何其他命名搜索。 因此，如果您有一个显示多个结果集的演示文稿模板，则可以单独自定义每个搜索。 如果要在将全局CGI参数复制到每个模板的每个搜索之前对其执行更改，请使用查询清理模块。

## 搜索前规则条件 {#section_B5568ADEB28546A280720309498B045D}

条件是可选的。 如果选择为每个查询指定操作，则始终会执行这些操作。 对于每个查询（在其中选择默认的演示文稿模板），您的第一个规则会被视为运行的最佳实践。 这样，您可以确保，无论传入的查询是什么，您都已选择了要使用的最坏情况方案演示模板。 条件可以基于任何CGI查询参数、cookie或先前规则已设置的自定义变量或系统变量。

## 搜索前规则操作 {#section_3B8E19D287554C1C969F5B8D81226981}

具有匹配条件的预搜索规则内的所有操作都将被执行。 操作通常由操作、要执行操作的数据和要使用的值组成。 最简单的操作是指定当查询与“预搜索规则”的条件匹配时要使用的表示模板。 然后，将目标模板设置为演示文稿模板的名称。 通过对模板的搜索参数执行操作，可以使用更复杂的操作来更改为给定模板使用的搜索。 对模板的搜索参数执行操作时，需要指定演示文稿模板并进行搜索。

## 通用规则 {#section_885ECB9DBF0C4D539C14F82BCAA35B4E}

对模板的搜索参数执行操作时，存在两个特殊值：*目标和*主要用于演示文稿模板和命名搜索。 使用这些值，您可以基于当前目标模板的主要搜索构建规则。 这些构造允许构建通用规则，您不必担心当前目标模板或主搜索被调用的内容。 显然，以前的预搜索规则定义了当前目标模板的内容。 否则，会为您选择初始演示文稿模板，这会产生不期望的结果。

## 示例 {#section_EA153A151987454EA44A4A6862466DF6}

将默认模板设置为guided.tmpl，当用户传入名为lang的cgi参数时，将其设置为已知语言，请使用该语言的模板。

```
    On condition: 
      Every Query 
    Perform the following actions: 
      Set targeted template to guided 
 
    On condition: 
      Query lang matches regular expression fr 
    Perform the following actions: 
      Set targeted template to guided_french 
 
    On condition: 
      Query lang matches regular expression de 
    Perform the following actions: 
      Set targeted template to guided_german
```

## 最佳实践 {#section_31EBAE5E54174DEE8986CBB636746A98}

* 第一个规则为每个查询选择一个默认模板。
* 查询的数据挖掘是在查询清理规则内完成的。 您可以在搜索前处理中引用它们。
* 将您在预搜索规则中引入的任何新自定义变量添加到预搜索规则中，该规则在任何其他预搜索规则引用前针对每个查询运行。

## 添加新的搜索前规则 {#task_182B95918462490D8BDA7F16A81CAC11}

您可以使 [!DNL Pre-Search Rules] 用选择用于根据传入的查询显示搜索结果的演示文稿模板。

**添加新的搜索前规则**

1. 在产品菜单中，单击 **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]**。
1. 在页面 [!DNL Pre-Search Rules] 上，单击 **[!UICONTROL Add New Rule]**。
1. 在字 [!DNL Name] 段中，键入新查询清除规则的名称。
1. 在页 [!DNL Add Pre-Search Rule] 面上，使用下拉列表和文本字段构建查询。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Cookie </p> </td> 
      <td colname="col2"> <p>HTTP cookie。 Cookies名称和值必须采用统一资源标识符编码。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>自定义变量 </p> </td> 
      <td colname="col2"> <p>用户定义的变量。 添加、删除或设置不限数量的用户定义变量。 </p> <p>您可以引用在“预搜索规则”的“查询清理”模块中定义的任何变量。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>系统变量 </p> </td> 
      <td colname="col2"> <p>可检查的内部系统设置的只读变量。 支持以下系统变量： </p> <p> 
        <ul id="ul_BC17F1637F27424CA4E8F530C28A3245"> 
          <li id="li_C7DF96EFD7AA4A449D00F7EACCAA0EB1"> <span class="uicontrol"> 主机名 </span> <p>服务器主机的名称。 </p> </li> 
          <li id="li_F85AB1D2B9374A859657D12B8ED6674B"> <span class="uicontrol"> uri </span> <p>请求的uri（不带查询字符串）。 </p> </li> 
          <li id="li_440149C9EC6E4805B77BBC97BE41542A"> <span class="uicontrol"> args </span> <p>整个查询字符串。 </p> </li> 
          <li id="li_F583FC4B0E404858BB3522B33A6F7A0A"> <span class="uicontrol"> environment（环境） </span> <p>“阶段”或“实时”，具体取决于传入的查询是发送到您的阶段还是实时环境。 </p> </li> 
          <li id="li_15902AA49B144D42A5E95D7E8B0FB1E1"> <span class="uicontrol"> referrer </span> <p>客户所来自的URL。 </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>彩块化 </p> </td> 
      <td colname="col2"> <p>全局集合中与特定facet关联的特殊CGI参数。 在查询清理之后，所有CGI参数都被复制到模板中每个命名的搜索中。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>查询参数 </p> </td> 
      <td colname="col2"> <p>全局集合中的CGI参数。 这些参数将复制到查询清除后模板内的每个命名搜索。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>模板的搜索参数 </p> </td> 
      <td colname="col2"> <p>CGI参数，它本地指向与演示模板关联的已命名搜索。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>模板的后端参数 </p> </td> 
      <td colname="col2"> <p>传入的查询参数最终转换为用于执行搜索的后端参数。 </p> <p>请参 <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> 阅后端搜索CGI参 </a>数。 </p> <p>后端参数不显示在导航元素上。 因此，您可以隐藏客户要应用于搜索的任何其他参数。 该参数是演示文稿模板中特定搜索的本地参数。 对后端参数的操作是滞后绑定的；即，在发送搜索之前应用它们。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>目标模板 </p> </td> 
      <td colname="col2"> <p>无法删除的系统定义自定义变量的特殊实例。 此变量包含当前目标演示文稿模板。 您可以通过指定自定义变量“targeted_template”来读取或设置此变量。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>排名 </p> </td> 
      <td colname="col2"> <p>允许您指定要在搜索中使用的排名规则。 此选项仅在定义了排名字段和排名规则时显示。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>商店 </p> </td> 
      <td colname="col2"> <p>搜索引擎根据主机名或 <span class="codeph"> gs_store查询参数自动检测客户所在的商店，而 </span> gs_store查询参数具有优先级。 您可以在商店中创建条件。 仅在查询清除中，您还可以使用动作覆盖当前商店。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最后一条规则 </p> </td> 
      <td colname="col2"> <p>当选中时，搜索前处理模块在匹配规则的操作之后不执行任何附加规则。 当您设置了导致以后的规则匹配但不希望以后的规则运行的操作时，此操作非常有用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>暂停 </p> </td> 
      <td colname="col2"> <p>关闭规则的运行，但不删除规则。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Add]**.
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## Editing a pre-search rule {#task_25F77050C5DA42B29DFD1C9718FB8C64}

您可以编辑已添加到页面的现有预搜索规 [!DNL Pre-Search Rules] 则。

**编辑预搜索规则**

1. 在产品菜单中，单击 **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]**。
1. 在页 [!DNL Pre-Search Rules] 面上，在表的 **[!UICONTROL Actions]** 列下，单击 **[!UICONTROL Edit]** 要编辑的关联规则。
1. 在页 [!DNL Edit Pre-Search Rule] 面上，使用下拉列表和文本字段构建查询。

   请参阅添加新的预 [搜索规则下的选项表](../c-about-rules-menu/c-about-pre-search-rules.md#task_182B95918462490D8BDA7F16A81CAC11)。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 删除预搜索规则 {#task_128B6A79CA6C451C991AEDAD58F51743}

您可以删除不再需要或使用的搜索前规则。

删除规则时，将自动调整其余规则的运行顺序以考虑删除。

**删除预搜索规则**

1. 在产品菜单中，单击 **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]**。
1. 在页 [!DNL Pre-Search Rules] 面上，在表的 **[!UICONTROL Actions]** 列下，单击 **[!UICONTROL Delete]** 要删除的关联规则。
1. 在对话 [!DNL Confirmation] 框中，单击 **[!UICONTROL OK]**。
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 更改预搜索规则运行的顺序 {#task_C18817276A3C459089C97448076365D1}

您可以对预搜索规则重新排序，以更改它们在演示文稿模板上运行的顺序。

预搜索规则按定义顺序运行。 规则的订单编号越高，越晚在该过程中运行，超越了之前的规则。 可通过在页面上表的“顺序”列中输入新编号来重新排序规 [!DNL Pre-Search Rules] 则。 您还可以对规则使用拖放来更改其运行顺序。

**更改预搜索规则运行的顺序**

1. 在产品菜单中，单击 **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]**。
1. 在页 [!DNL Pre-Search Rules] 面上，执行下列操作之一：

   * 单击列 **[!UICONTROL Order]** 标题以按升序或降序对规则进行排序。
   * 在列 **[!UICONTROL Order]** 中，在预搜索规则名称左侧的文本字段中，键入要运行规则的顺序编号。
   * 将表行拖放到希望规则运行的位置。 所有订单编号都会更新以反映规则运行的新顺序。

1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

