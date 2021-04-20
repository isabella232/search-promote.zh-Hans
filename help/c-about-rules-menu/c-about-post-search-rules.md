---
description: 您可以使用“搜索后规则”来检查搜索结果并确定搜索对显示内容的影响。
solution: Target
title: 关于搜索后规则
topic: Rules,Site search and merchandising
uuid: 312d1e4a-f5b6-4629-8645-17e6f6c09fc4
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '2102'
ht-degree: 0%

---


# 关于搜索后规则{#about-post-search-rules}

您可以使用“搜索后规则”来检查搜索结果并确定搜索对显示内容的影响。

## 使用搜索后规则{#concept_AF6ADFCC0ADF4A788003964939917FDE}

如果搜索没有结果，则“搜索后规则”可以对类似项目执行搜索。 或者，它可显示一个网页，向搜索未找到的项目的客户推荐其他项目。

每个搜索后规则都包含两个主要元素：规则的操作及其可选条件。 您可以指定不限数量的规则和条件。 这些规则的顺序很重要，因为规则集是通过逐个规则循环的。 当规则的条件匹配时，将执行所有关联的操作。

您最多可以优化搜索结果集，进行三轮搜索。 之后，将使用当前可用的任何内容。 此限制可防止无限循环并确保客户获得有效响应。 重做搜索的次数越多，返回搜索结果所花的时间就越长。 如果任何匹配规则都不改变当前使用的演示模板的搜索之一或切换模板，则搜索结果集被视为已完成，且搜索后退出。

搜索后处理构建于早期的处理模块查询清理和搜索前处理之上。 因此，在这些模块中设置的任何自定义变量都可用于搜索后处理规则。 同样，预搜索处理已实例化所有模板，其中与演示模板关联的每个命名搜索都有其自己的CGI参数本地副本。 反过来，您可以单独自定义每个搜索。

请参阅[关于查询清理规则](../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C)。

请参阅[关于预搜索规则](../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F)。

## 关于搜索后规则条件{#section_C43EB77CC0AC43B8B9D38569264BF1B5}

条件是可选的。 如果指定为每个查询指定操作，则始终执行这些操作。 您可以基于任何CGI查询参数、Cookie、搜索结果或先前规则设置的自定义变量。 或者，您可以根据系统条件（如当前选定的模板是什么或是最后一次搜索）来进行搜索。 在搜索结果或CGI参数上构建条件时，需指定模板和搜索名称。

## 关于搜索后规则操作{#section_0E15FE683A894ECAAA386267EEC7F7C5}

具有匹配条件的“搜索后规则”中的所有操作都将被执行。 操作通常由操作、要执行操作的数据以及要使用的值组成。 最简单的操作是根据搜索后规则的条件切换要使用的演示模板。 您可以使用更高级的操作来更改搜索的参数，这些参数会导致重新完成搜索。 对模板的搜索参数执行操作时，请指定演示文稿模板并进行搜索。

## 一般规则{#section_AEE923988CC748FF9DEF2233FBF333B5}

对模板的搜索参数执行操作时，存在两个特殊值，分别为演示文稿模板和命名搜索的*targeted和*primary。 使用这些值可根据当前目标模板的主要搜索构建规则。 通过这些构造，您可以构建通用规则，无需担心当前目标模板或主搜索被调用的内容。 如果此传递是搜索后处理的第一次传递，则目标模板是搜索前处理将其设置为的任何模板。

## 重定向{#section_E5669A2F13C240F2968E31C75591CD6A}

“查询清理”中的“直接点击”和“重定向”允许您根据传入的搜索词重定向到URL。 搜索后规则中的重定向扩展了这一理念，只是它允许您检查搜索返回的结果数，然后决定是否要进行重定向。 通过“搜索后规则”，您可以重定向到URL，在该URL中可以替换自定义变量或查询参数。 或者，您可以重定向到第一个结果中的字段。 当您重定向到结果字段时，您在传输模板中定义了该字段，它必须包含有效的显式URL，否则将跳过重定向。

在“搜索后规则”中使用重定向机制时，可以检测搜索何时返回单个结果。 您不必返回此结果，而是可以重定向到与结果关联的网页。

有关将重定向与“搜索后规则”结合使用的示例，请参阅以下重定向示例。

## 上一个规则{#section_FC1E0050C9324278B171038E98F6C335}

当满足设置了选项&#x200B;**[!UICONTROL Last Rule]**&#x200B;的规则的条件时，在匹配规则的操作之后，后搜索处理模块不执行任何附加规则。 当您设置了导致以后的规则匹配但希望处理停止的操作时，此情况很有用。 而且，在下一轮搜索之后，这条规则可能会匹配。

## 示例 {#section_DDB98383690941F9B44AD00FBA55BB56}

在以下示例中，假定您有两个演示文稿模板。 一个模板用于显示许多搜索结果，另一个模板用于显示单个结果以及对与主搜索相关的附件的额外搜索。 您希望检测何时有一个结果并切换到其他演示文稿模板。 要完成此任务，可以使用以下规则：

```
On condition: 
  targeted template is default 
  targeted template primary results equal 1 
  not last search 
Perform the following actions: 
  Set targeted template to product_spotlight
```

MegaElectronic是一家大型电子商店。 在分析其搜索数据后，MegaElectronic注意到其许多客户使用产品的部件号执行产品搜索。 在这种情况下，如果客户直接搜索产品并且只找到一个产品，MegaElectronic会重定向到与产品关联的网页。

要实现此效果，您可以使用具有三个条件的单个规则。 第一个条件检查返回的搜索是否只有一个结果。 第二个条件确保查询项与MegaElectronic的部件号格式匹配，以便生成要导致重定向的结果。 第三个条件确保客户没有使用任何彩块化来向下钻取到一个结果，因为部件号可能是一个部分部件号并返回多个结果。 操作会重定向到结果中的字段。

```
On condition: 
  targeted template's primary results equal 1 
  query q matches regular expression ^\D\D\D-\d+ 
  no facet selected ^\D\D\D-\d+ 
Perform the following actions: 
  redirect to result field "loc" in template *targeted for search *primary
```

## 最佳实践 {#section_1BF7DE1BD5664B3BAEC26AA829FDB0BA}

* 触发新一轮搜索的任何规则集都应始终包含一个条件子句，以检查这不是模块的最后一次传递。 如果您已执行了最大数目的搜索，则无法重做任何搜索。
* 如果您是最后一个通过模块的程序，并且结果仍然很差，则可以切换到“无结果”模板。
* 您应该根据可能具有其他参数的搜索结果更改演示文稿模板。 如果要选择仅基于传入查询的模板，则预搜索规则更有效。
* 查询的数据挖掘是在查询清理模块中完成的。 您可以在搜索后处理中引用自定义变量。
* 当您进行重定向时，请始终检查客户是否未选择任何方面。 原因在于，当客户钻入某个方面，突然从搜索结果中拿走时，这会带来不便。 当客户看到单个结果不想要查找时，可能想取消选择facet。

## 添加新的搜索后规则{#task_52F6F9AAD65B45B5ACA1FF245DFFADD9}

可以使用[!DNL Post-Search Rules]选择用于根据传入查询显示搜索结果的演示文稿模板。

**添加新的搜索后规则**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Rules]** > **[!UICONTROL Post-Search Rules]**。
1. 在[!DNL Post-Search Rules]页面上，单击&#x200B;**[!UICONTROL Add New Rule]**。
1. 在[!DNL Name]字段中，键入新查询清除规则的名称。
1. 在[!DNL Add Post-Search Rule]页面上，使用下拉列表和文本字段构建您的查询。

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
      <td colname="col2"> <p>HTTP Cookie。 Cookie名称和值必须进行统一资源标识符编码。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>自定义变量 </p> </td> 
      <td colname="col2"> <p>用户定义的变量。 您可以添加、删除或设置不限数量的自定义变量。 </p> <p>您可以引用在“查询清理”和“预搜索规则”模块中在“后搜索规则”中定义的任何自定义变量。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>系统变量 </p> </td> 
      <td colname="col2"> <p>由您可以检查的内部系统设置的只读变量。 支持以下系统变量： </p> <p> 
        <ul id="ul_BC17F1637F27424CA4E8F530C28A3245"> 
          <li id="li_C7DF96EFD7AA4A449D00F7EACCAA0EB1"> <span class="uicontrol"> 主机名  </span> <p>服务器主机的名称。 </p> </li> 
          <li id="li_F85AB1D2B9374A859657D12B8ED6674B"> <span class="uicontrol"> uri  </span> <p>请求的统一资源标识符(不含查询字符串)。 </p> </li> 
          <li id="li_440149C9EC6E4805B77BBC97BE41542A"> <span class="uicontrol"> args  </span> <p>整个查询字符串。 </p> </li> 
          <li id="li_F583FC4B0E404858BB3522B33A6F7A0A"> <span class="uicontrol"> environment（环境） </span> <p>“阶段”或“实时”，具体取决于传入的查询是发送到您的分阶段环境还是实时环境。 </p> </li> 
          <li id="li_15902AA49B144D42A5E95D7E8B0FB1E1"> <span class="uicontrol"> referrer </span> <p>客户所来的统一资源定位器。 </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>系统变量 </p> </td> 
      <td colname="col2"> <p>可在条件中使用以确定当前状态的只读变量。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>模板的搜索彩块化 </p> </td> 
      <td colname="col2"> <p>与演示文稿模板关联的命名搜索的本地方面。 facet本质上是特殊的CGI参数，用于指示客户在facet中选择了哪个值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>模板的搜索参数 </p> </td> 
      <td colname="col2"> <p>CGI参数，它本地指向与演示模板关联的命名搜索。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>模板的后端参数 </p> </td> 
      <td colname="col2"> <p>传入的查询参数最终转换为用于执行搜索的后端参数。 </p> <p>请参阅<a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local">后端搜索CGI参数</a>。 </p> <p>后端参数不显示在导航元素上。 因此，您可以隐藏任何要应用于搜索的其他参数，而不是客户。 </p> <p>该参数是演示文稿模板中特定搜索的本地参数。 对后端参数的操作是延迟绑定的；即，在发送搜索之前应用这些属性。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>目标模板 </p> </td> 
      <td colname="col2"> <p>无法删除的系统定义自定义变量的特殊实例。 此变量包含当前目标演示文稿模板。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>排名 </p> </td> 
      <td colname="col2"> <p>允许您指定要在搜索中使用的排名规则。 此选项仅在定义了排名字段和排名规则时才显示。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最后一条规则 </p> </td> 
      <td colname="col2"> <p>选中后，搜索后处理模块在匹配规则的操作之后不执行任何附加规则。 此操作对于您设置了导致以后的规则匹配但不希望以后规则运行的动作时很有用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>暂停 </p> </td> 
      <td colname="col2"> <p>关闭规则的运行，但不删除规则。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Add]**.
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 编辑后搜索规则{#task_ECB00334C0A74C87AF857DB3EB372119}

您可以编辑已添加到[!DNL Post-Search Rules]页面的现有搜索后规则。

**编辑搜索后规则**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]**。
1. 在[!DNL Post-Search Rules]页面的表的&#x200B;**[!UICONTROL Actions]**&#x200B;列下，单击&#x200B;**[!UICONTROL Edit]**&#x200B;以获取要编辑的关联规则。
1. 在[!DNL Edit Post-Search Rule]页面上，使用下拉列表和文本字段构建您的查询。

   请参阅[添加新的搜索后规则](../c-about-rules-menu/c-about-post-search-rules.md#task_52F6F9AAD65B45B5ACA1FF245DFFADD9)下的选项表。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 删除搜索后规则{#task_0F4653AB20D54B769A4FA8D1491AB4CF}

您可以删除不再需要或使用的搜索后规则。

删除规则时，将自动调整其余规则运行的顺序以考虑删除。

**删除搜索后规则**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Rules]** > **[!UICONTROL Post-Search Rules]**。
1. 在[!DNL Post-Search Rules]页面的表的&#x200B;**[!UICONTROL Actions]**&#x200B;列下，单击&#x200B;**[!UICONTROL Delete]**&#x200B;以获取要删除的关联规则。
1. 在[!DNL Confirmation]对话框中，单击&#x200B;**[!UICONTROL OK]**。
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 更改搜索后规则运行{#task_40542FCD32234BBF881A81BF5477F78F}的顺序

您可以对搜索后规则重新排序，以更改它们在演示文稿模板上运行的顺序。

搜索后规则按定义顺序运行。 规则的订单编号越高，其执行时间越晚，超越了之前的规则。 通过在[!DNL Post-Search Rules]页面的表的“顺序”列中输入新编号来重新排序规则。 您还可以对规则使用拖放来更改其运行顺序。

**更改搜索后规则运行的顺序**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Rules]** > **[!UICONTROL Post-Search Rules]**。
1. 在[!DNL Post-Search Rules]页面上，执行以下操作之一：

   * 单击&#x200B;**[!UICONTROL Order]**&#x200B;列标题以按升序或降序对规则排序。
   * 在[!DNL Order]列中，在预搜索规则名称左侧的文本字段中，键入希望规则运行的顺序编号。
   * 将表行拖放到希望规则运行的位置。 所有订单编号都会更新，以反映规则运行的新订单。

1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。
