---
description: 使用查询清理规则分析和修改传入查询。
solution: Target
title: 关于查询清理规则
topic-legacy: Rules,Site search and merchandising
uuid: 683af81f-f7c0-45f8-9212-e5e7cb82ccca
exl-id: 22ebca58-7687-4c8c-9ac1-bacb321065f3
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '1596'
ht-degree: 1%

---

# 关于查询清理规则{#about-query-cleaning-rules}

使用查询清理规则分析和修改传入查询。

## 使用查询清理规则{#concept_17F3CDDC3C8A4128AF092A82B777B86C}

当您想要修改网站搜索/促销行为时，通常会使用此功能。 例如，您可以将空白搜索更改为popular关键字，而不是“*”搜索，从而提升受欢迎的产品。 您还可以使用查询清理规则执行直接点击，您可以在该点击中重定向到URL。 当您检测到某人正在搜索产品SKU，并且您希望跳过搜索并重定向到该产品的页面时，这可能特别有用。 查询清理还可以挖掘查询并设置可在后续处理流程步骤中使用的自定义变量。 查询清理规则是按顺序执行的，每个查询。 要更改规则的顺序，可使用拖放操作。 在保存之前，实际订单不会更改。

检查查询清理模块中的查询清理规则，以确定是否必须修改任何查询参数或是否必须设置任何自定义变量。 每个查询清理规则由两个主要元素组成：规则的操作和可选条件。 可以指定不限数量的规则和条件。 这些规则的顺序很重要，因为网站搜索/销售循环逐条循环访问规则集规则。 当规则的条件匹配时，将执行所有关联的操作。

在查询清理完成后，将继续使用生成的CGI参数。 已设置的任何自定义变量可在处理流程的稍后阶段使用。 默认情况下，系统会自动从查询词中删除前导和尾随空白。

## 关于查询清理条件{#section_BF6F25F94FED4DDEA8600D921EA43A66}

条件是可选的。 如果您决定为每个查询指定操作，则始终执行这些操作。 条件可以基于任何CGI查询参数、现有Cookie或先前规则设置的自定义变量。 它被认为是“最佳实践”，即第一个查询清理规则将针对每个查询运行，在该规则中它定义和初始化您计划使用的所有自定义变量。

## 关于查询清理操作{#section_78F74A9B48DE484191CDA95F5B4E7154}

具有匹配条件的查询清理规则内的所有操作都将执行。 操作通常由操作、要执行操作的数据以及要使用的值组成。

请参阅[添加查询清理规则](../c-about-rules-menu/c-about-query-cleaning-rules.md#task_47F43988D3D9485F8AE1DFDA7E00BF54)中的选项表。

## 关于重定向{#section_597481E6194440C0A7B9E6FC901A81C0}

“直接点击”界面允许您根据传入的查询项定义一组重定向。 “查询清理”中的重定向扩展了这一理念。 但是，重定向通过指定条件为您提供了更精细的重定向时间粒度，并允许您重定向到动态URL，而不是静态URL。 当您选择重定向操作时，行将更新为包含一个文本框，您可以在其中指定要重定向到的URL。 在URL中，您可以通过将变量或参数括在多次大括号中来指定要替换的变量或参数。 在替换中，自定义变量的优先级高于CGI参数。

## 示例 {#section_DB5047CC38FB4A57B15CAAF9848073E3}

假设您有一家服装零售商店并有网站。 如果用户在没有搜索词的情况下单击“搜索”，则您希望返回针对牛仔裤的搜索，因为这正是您在国际上的知名度。 您还要分析查询词的性别，以便您以后能够根据对每个性别使用不同演示模板的自定义变量创建预搜索规则。

```
On condition: 
  query q equal 
Perform the following actions: 
  Set query parameter q to value jeans 
 
On condition: 
  Query q matches regular expression wom[e|a]n[s]|girl[s] 
Perform the following actions: 
  Add custom variable gender 
  Set custom variable gender to value female 
 
On condition: 
  Query q matches regular expression men[s]|boy[s] 
Perform the following actions: 
  Add custom variable gender 
  Set custom variable gender to value male
```

MegaElectronic是一家大型电子商店。 通过分析搜索数据，MegaElectronic注意到，许多精明的客户经常使用产品的SKU搜索产品，而不是返回单个产品的搜索结果，MegaElectronic希望重定向到与该SKU关联的网页。

```
On condition: 
  query q matches regular expression ^\D\D\D-\d\d\d\d$ 
Perform the following actions: 
  redirect to https://www.megaelectronic.com/?sku={{q}}
```

## 添加查询清理规则{#task_47F43988D3D9485F8AE1DFDA7E00BF54}

您可以定义清理或编辑客户传入搜索查询的规则。

您只能选择当前存在的模板。 如果您没有任何模板，则必须首先定义它们。

请参阅[关于模板](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5)。

**添加查询清除规则**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]**。
1. 在[!DNL Query Cleaning Rules]页面上，单击&#x200B;**[!UICONTROL Add New Rule]**。
1. 在[!DNL Name]字段中，键入新查询清除规则的名称。
1. 在[!DNL Add Query Cleaning Rule]页面上，使用下拉列表和文本字段构建您的查询。

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
      <td colname="col2"> <p>HTTP Cookie。 您可以根据与域关联的Cookie定义条件。 或者，您也可以设置使用传出搜索结果编写的Cookie。 Cookie名称和值必须编码为统一资源标识符。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>自定义变量 </p> </td> 
      <td colname="col2"> <p>用户定义的变量。 添加、删除或设置不限数量的用户定义的变量。 您可以在“预搜索规则”和“后搜索规则”中在此引用任何用户定义的变量。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>系统变量 </p> </td> 
      <td colname="col2"> <p>由您可以检查的内部系统设置的只读变量。 支持以下系统变量： </p> <p> 
        <ul id="ul_BC17F1637F27424CA4E8F530C28A3245"> 
          <li id="li_C7DF96EFD7AA4A449D00F7EACCAA0EB1"> <span class="uicontrol"> 主机名  </span> <p>服务器主机的名称。 </p> </li> 
          <li id="li_F85AB1D2B9374A859657D12B8ED6674B"> <span class="uicontrol"> uri  </span> <p>请求的URI(不含查询字符串)。 </p> </li> 
          <li id="li_440149C9EC6E4805B77BBC97BE41542A"> <span class="uicontrol"> args  </span> <p>整个查询字符串。 </p> </li> 
          <li id="li_F583FC4B0E404858BB3522B33A6F7A0A"> <span class="uicontrol"> environment（环境） </span> <p>“阶段”或“实时”，具体取决于传入的查询是发送到您的分阶段环境还是实时。 </p> </li> 
          <li id="li_15902AA49B144D42A5E95D7E8B0FB1E1"> <span class="uicontrol"> referrer </span> <p>客户所来自的URL。 </p> </li> 
          <li id="li_6FEE352DB7A842FCB2EBE1398AD03666"> <span class="uicontrol"> 用户代理  </span> <p>客户浏览器的“用户 — 代理”字符串。 </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>查询参数 </p> </td> 
      <td colname="col2"> <p>传递给查询的CGI参数。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>后端参数 </p> </td> 
      <td colname="col2"> <p>传入的查询参数最终转换为用于执行搜索的后端参数。 </p> <p>请参阅<a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local">后端搜索CGI参数</a>。 </p> <p>后端参数不显示在导航元素上。 因此，您可以隐藏任何要应用于搜索的其他参数，而不是客户。 对后端参数的操作是延迟绑定的；即，在发送搜索之前应用这些属性。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>彩块化 </p> </td> 
      <td colname="col2"> <p>与给定facet关联的特殊CGI参数。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>排名 </p> </td> 
      <td colname="col2"> <p>允许您指定要在搜索中使用的排名规则。 此选项仅在定义了某些排名字段和排名规则时才显示。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>商店 </p> </td> 
      <td colname="col2"> <p>搜索引擎根据主机名或<span class="codeph"> gs_store </span>查询参数自动检测用户所在的存储，后者具有优先级。 您可以为商店创建条件。 仅在查询清理中，您还可以使用动作过载当前商店。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最后一条规则 </p> </td> 
      <td colname="col2"> <p>当满足具有最后规则集的规则的条件时，查询清理处理模块在匹配规则的操作之后不执行任何附加规则。 当您设置了将导致以后的规则匹配但不希望以后的规则触发的操作时，此功能非常有用。 请注意，如果规则的操作是执行重定向，则重定向会立即进行，因此它实际上就像设置了最后一个规则一样。 </p> </td> 
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

## 编辑查询清除规则{#task_FA2FF1A7E2634350AD703485CBC27CB3}

您可以编辑已添加到“查询清理规则”页面的现有查询清理规则。

**编辑查询清除规则**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]**。
1. 在[!DNL Query Cleaning Rules]页面的表的&#x200B;**[!UICONTROL Actions]**&#x200B;列下，单击&#x200B;**[!UICONTROL Edit]**&#x200B;以获取要编辑的关联规则。
1. 在[!DNL Edit Query Cleaning Rule]页面上，使用下拉列表和文本字段构建您的查询。

   请参阅[添加查询清理规则](../c-about-rules-menu/c-about-query-cleaning-rules.md#task_47F43988D3D9485F8AE1DFDA7E00BF54)下的选项表。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 删除查询清理规则{#task_C52D17226B824590B087CAB6970CBB01}

您可以删除不再需要或使用的查询清理规则。

删除规则时，将自动调整其余规则运行的顺序以考虑删除。

**删除查询清除规则**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]**。
1. 在[!DNL Query Cleaning Rules]页面的表的&#x200B;**[!UICONTROL Actions]**&#x200B;列下，单击&#x200B;**[!UICONTROL Delete]**&#x200B;以获取要删除的关联规则。
1. 在[!DNL Confirmation]对话框中，单击&#x200B;**[!UICONTROL OK]**。
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 更改查询清理规则运行{#task_C24012C45A4445468A7FD998017388CA}的顺序

您可以对查询清除规则重新排序，以更改它们在演示文稿模板上运行的顺序。

查询清理规则按定义顺序运行。 规则的订单编号越高，其执行时间越晚，超越了之前的规则。 通过在[!DNL Query Cleaning Rules]页面的表的“顺序”列中输入新编号来重新排序规则。 您还可以对规则使用拖放来更改其运行顺序。

**更改查询清理规则运行的顺序**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]**。
1. 在[!DNL Query Cleaning Rules]页面上，执行以下操作之一：

   * 单击[!DNL Order]列标题以按升序或降序对规则排序。
   * 在[!DNL Order]列中，在查询清除规则名称左侧的文本字段中，键入希望规则运行的顺序编号。
   * 将表行拖放到希望规则运行的位置。 所有订单编号都会更新，以反映规则运行的新订单。

1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。
