---
description: 您可以使用业务规则来推销您的搜索。
seo-description: 您可以使用业务规则来推销您的搜索。
seo-title: 关于业务规则
solution: Target
title: 关于业务规则
topic: Rules,Site search and merchandising
uuid: f2186f54-7a39-4f46-bb29-5115d5a17f07
translation-type: tm+mt
source-git-commit: 2dd205d3034e8397d88007a1618a121f0b6087a8

---


# 关于业务规则{#about-business-rules}

您可以使用业务规则来推销您的搜索。

## 使用业务规则 {#concept_2A93D76216754D3D8412CDEA00BD26BD}

例如，您可以配置横幅的显示时间、显示结果的时间和顺序。 您还可以配置facet中项目的位置以及用于给定搜索的模板。 这些规则按照定义的顺序运行；规则的编号越高，越晚在该过程中运行，比之前的规则要大。 您可以拖放规则以更改其顺序，也可以通过在规则顺序文本框中输入新编号对它们重新排序。

每个业务规则由触发器和操作组成。

触发器定义规则何时运行。 例如，当查询词是“mens”或结果大多是帽子时。 触发器由多个条件组成，这些条件必须全部满足，或者其中任何一个条件必须满足才能使整个触发器成真。 可以通过更改触发器运算符来指定优先级。

该操作定义满足触发条件时发生的情况。 例如，将横幅设置为显示或将给定结果移到位置1。 规则表显示有关规则的摘要信息。 您可以单击规则名称以将其打开，并查看其他信息。

规则表显示了所有业务规则的列表。 默认情况下，表格以降序显示添加的最后十个规则。 您可以单击表中的列标题以按升序或降序对规则进行排序。

业务规则可以具有以下三种状态之一：批准、暂停或WIP（在制品）

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>业务规则状态 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>已批准 </p> </td> 
   <td colname="col2"> <p>在您的实时环境和分阶段环境中运行获准的业务规则。 您可以在高级规则生成器中批准业务规则。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>挂起 </p> </td> 
   <td colname="col2"> <p>暂停的业务规则永远不会在分阶段环境或实时环境中运行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>WIP </p> </td> 
   <td colname="col2"> <p>WIP（在制品）是既未批准也未暂停的业务规则。 即，您可能仍在处理它们，或者您可能希望在批准它们之前先对其进行测试。 处于WIP状态的业务规则仅在暂存环境中运行。 </p> </td> 
  </tr> 
 </tbody> 
</table>

您批准业务规则并将其实时推送，以便它们在您的实时环境中运行。 目前，您只能将所有规 *则* 实时推送。 但是，您可以更改规则的状态，以控制在您的实时环境中运行和不运行的规则。

默认情况下，只要满足相关触发器，规则就会运行。 但是，您可以选择计划一个规则以在特定日期和时间范围内运行。

此外，默认情况下，规则在满足所有商店的关联触发器时都会运行。 如果希望该规则仅适用于某些商店，则可以使用“商店”面板选择一个或多个应用该规则的商店。

## 添加新业务规则 {#task_BD3B31ED48BB4B1B8F1DCD3BFA2528E7}

您可以使用 [!DNL Visual Rule Builder] 或添 [!DNL Advanced Rule Builder] 加可定制客户搜索体验的业务规则。

**添加新业务规则**

以下步骤假定您使用可视规则生成器。

1. 执行以下操作之一：

   * 在产品菜单中，单击 **[!UICONTROL Rules]** > **[!UICONTROL Business Rules]**。 在页面 [!DNL Business Rules] 上，单击 **[!UICONTROL Add New Rule]**。

   * 在产品菜单中，单击 **[!UICONTROL Simulator]**。 在页 **[!UICONTROL Simulator for Today]** 面上，单 **[!UICONTROL Add New Rule]** 击下拉菜单右 **[!UICONTROL Options]** 侧的。

      如果 **[!UICONTROL Add New Rule]** 该选项在页面上不可见，请在下拉菜 **[!UICONTROL Options]** 单中单击 **[!UICONTROL Simulate Staged]**。

      ![](assets/Simulator.png)

1. 在文本 **[!UICONTROL Name]** 字段中，键入业务规则的新名称。

   请勿单击 **[!UICONTROL Save Rule]** 鼠标。
1. （可选）如果您管理大量业务规则，则可以使用特定标签标记业务规则。 在字段 **[!UICONTROL Tags]** 中，输入一个或多个标记标签，使用逗号、制表符或输入作为分隔符。

   在页面 [!DNL Business Rules] 上，使用该功 **[!UICONTROL Filter by tag]** 能筛选与给定标签匹配的规则。 1.在页 [!DNL Business Rule Builder] 面中，设置要使用的触发器和操作。

       **触发器选项**
     
    “触发器”是运行业务规则必须满足的条件。 当业务规则有多个触发器时，您可以使用以下三种方法之一配置触发器的响应方式：
   
   * 一个响应，其中所有触发器都必须为true（默认设置），如下例所示：

      `if a AND b AND c then ...`

   * 任何触发器都必须为true的响应，如下例所示：

      `if a OR b OR c then ...`

   * 指定自定义触发器组合的响应。 即，将单个触发器或“条件”与运算符和运 `AND` 算符组合 `OR` 在一起。

      您还可以通过添加左括号和右括号组合来更改评估的优先级，如下例所示：

      `if (a OR b) AND c then ...`

      >[!NOTE]
      >
      >如果在自定 `AND` 义业务规 `OR` 则集中将操作符与操作符结合，请确保正确地指定括号，以确保按正确的顺序评估触发器。

      默认情况下，不能自定义触发器组合这一特殊功能。 请联系技术支持以激活此功能供您使用。
   <table> 
      <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>触发器选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>关键字匹配 </p> </td> 
      <td colname="col2"> <p>当搜索词与给定区分大小写的关键字匹配时，触发器为true。 触发器对于关键字及其所有同义词均为true，如语言学词典中所定义。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> 查询匹配 </p> </td> 
      <td colname="col2"> <p> 当所有搜索参数匹配时，触发器为true。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Result Group是Dominant </p> </td> 
      <td colname="col2"> <p> 当给定搜索定义的一组结果主导结果集时，触发器为true。 </p> <p>默认情况下，支配地位设定在50%。 此设置是您可以设置的促销首选项。 </p> <p> 
        <!--See <xref href="t_Configuring_Merchandising_preferences.xml#task_7AC7B9F5D9F44E10AB5BC0B8CB31C37A" type="task" format="dita" scope="local">Configuring Merchandising preferences</xref>. --> </p> <p>整个组必须位于结果集中，此触发器才为true。 结果组是动态的。 根据与原始搜索条件匹配的结果，索引操作之后可以更改。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>结果组存在 </p> </td> 
      <td colname="col2"> <p> 当由给定搜索定义的结果组存在于结果集中时，触发器为true。 要满足此触发器，必须在结果集中包含整个组（结果可显示在任何页面上）。 结果组是动态的，并且在索引操作之后可能会根据与原始搜索条件匹配的结果而改变。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> 结果演示 </p> </td> 
      <td colname="col2"> <p> 当在结果集中找到单个结果时，触发器为true。 结果可以位于结果集中的任意位置，它不必位于用户当前查看的页面上。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

   **操作选项**

   当满足业务规则的触发器时，将执行与该规则关联的操作。 在可视规则生成器中，您可以创建以下操作，但可以使用高级规则生成器创建其他类型的操作。

   下表中的“删除彩块化项”(Remove Facet Item)、“显示彩块化项”(Reveal Facet Item)、“删除彩块化”(Remove Facet)、“推送彩块化项”(Push Facet Item)操作需要彩块化。 选择facet的界面取决于帐户的配置方式。 例如，普通帐户使用下拉列表来选择facet。 但是，如果您的帐户有带槽的facet，则会出现一个自动完成文本框，您可以在其中输入任何facet的名称。 在您键入facet的名称时，自动完成会在下拉列表中建议facet。 建议包括当前定义的彩块化。 如果您的帐户有插槽图，则还建议使用插槽彩块化。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>动作选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>推送组 </p> </td> 
      <td colname="col2"> <p> 将由指定搜索条件定义的搜索结果组推送到特定位置。 </p> <p>推送搜索结果组不会隐式添加该组。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>添加组 </p> </td> 
      <td colname="col2"> <p> 根据指定的搜索条件定义添加搜索结果组。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>删除组 </p> </td> 
      <td colname="col2"> <p> 删除由指定搜索条件定义的搜索结果组。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>单次推送 </p> </td> 
      <td colname="col2"> <p> 将单个搜索结果推送到选定位置。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>添加单个 </p> </td> 
      <td colname="col2"> <p> 将单个搜索结果添加到选定位置。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>删除单个 </p> </td> 
      <td colname="col2"> <p> 从搜索结果集中删除单个搜索结果。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>删除所有结果 </p> </td> 
      <td colname="col2"> <p>从搜索结果集中删除所有结果。 </p> <p> 
        <!-- Bug #3331637 The option is meant to be used in conjunction with other rule actions in order to create "canned landing pages" where we want to create a page's content solely by rule actions, and need to completely discard the "natural" results of the search. Given that the other options don't have any kind of "here's how/why you might use this", I don't see much point in breaking that precedent here.--> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>选择其他横幅 </p> </td> 
      <td colname="col2"> <p> 更改选定横幅区域中的横幅。 </p> <p>在网页查看区域中右键单击横幅时，此选项可用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>添加横幅命令 </p> </td> 
      <td colname="col2"> <p>仅适用于Adobe Dynamic Media Classic模板。 </p> <p>允许您更改在横幅模板中使用的默认参数。 </p> <p>请参阅使用Adobe Dynamic Media Classic <a scope="local" href="../c-about-design-menu/c-about-banners.md#task_AD1E0C00A9E04B1FA819EB93288786B3" type="reference" format="dita"> 添加横幅中的选项表 </a>。 </p> <p>另请参 <a href="../c-about-design-menu/c-about-banners.md#task_C3E782477FBF428ABEA220751781ACA9" type="task" format="dita" scope="local"> 阅使用Adobe Dynamic Media Classic编辑横幅 </a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>删除横幅 </p> </td> 
      <td colname="col2"> <p> 从选定的横幅区域删除横幅；除非设置横幅的其他规则覆盖此规则，否则不会显示横幅。 </p> <p>在网页查看区域中右键单击横幅时，此选项可用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>推送彩块化项 </p> </td> 
      <td colname="col2"> <p> 将彩块化内的项目推送到选定位置。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>删除区域 </p> </td> 
      <td colname="col2"> <p> 从搜索结果页面中删除区域。 </p> <p>另请参阅下面的删除彩块化操作。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>显示区域 </p> </td> 
      <td colname="col2"> <p> 在搜索结果页面中显示一个区域。 </p> <p>另请参阅下面的“显示彩块化”动作。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>删除彩块化项 </p> </td> 
      <td colname="col2"> <p> 从彩块化中删除彩块化项。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>“显示 Facet 项目” </p> </td> 
      <td colname="col2"> <p> 显示特定的facet项。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>显示彩块化 </p> </td> 
      <td colname="col2"> <p> 显示特定的facet。 此操作比“显示区域”操作更为首选。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>删除彩块化 </p> </td> 
      <td colname="col2"> <p> 删除特定facet。 此操作比“删除区域”操作更为首选。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

   根据处于活动状态（已展开）的规则构建器面板，您还可以执行以下操作来设置触发器和操作。

   * 展开面 **[!UICONTROL Triggers]** 板时——在“业务规则生成器”页面的演示文稿模板区域，右键单击任何搜索结果或搜索facet，然后单击 **[!UICONTROL Add "result present" trigger]**。

      在“触发器”面板中，单击触发器左侧的“X”，将其从触发器列表中删除。

   * 展开面 **[!UICONTROL Actions]** 板时——在“业务规则生成器”页面的演示文稿模板区域，右键单击搜索结果。 单 **[!UICONTROL Add Result]**&#x200B;击、 **[!UICONTROL Remove Result]**、 **[!UICONTROL Push to bottom]**&#x200B;或(其中 **[!UICONTROL Push to #`<n>`]**`<n>` 是数字)。


1. （可选）在“业务规则生成器”面板( [!DNL Triggers]、 [!DNL Actions]或 [!DNL Schedule])中，执行下列操作之一：

   * 在“业务规则构建器”页面区域的演示文稿模板区域中，右键单击横幅，然后单击 **[!UICONTROL Select different banner]**。 在页面 **[!UICONTROL Pick Banner]** 上，单击横幅 **[!UICONTROL Pick this banner]** 缩略图下方，将其添加到演示文稿模板。 只有与演示文稿模板上原始横幅的大小和区域匹配的横幅才可供您选择。

      添加横幅操作将添加到面 [!DNL Actions] 板。

   * 在页面的演示文稿模板区 [!DNL Business Rule Builder] 域中，右键单击要更改其参数的Adobe Dynamic Media Classic模板横幅，然后单击 **[!UICONTROL Add banner commands]**。 在对 [!DNL Change Parameters] 话框中，设置所需的参数选项。

      请参阅使用Adobe Dynamic Media Classic [添加横幅中的选项表](../c-about-design-menu/c-about-banners.md#task_AD1E0C00A9E04B1FA819EB93288786B3)。

      单击 **[!UICONTROL Save]**.

      参数更改将添加到面 [!DNL Actions] 板。

      另请参 [阅使用Adobe Dynamic Media Classic编辑横幅](../c-about-design-menu/c-about-banners.md#task_C3E782477FBF428ABEA220751781ACA9)。

   * 在“业务规则生成器”页面的演示文稿模板区域中，右键单击要从页面中删除的横幅，然后单击 **[!UICONTROL Remove banner]**。 删除横幅操作将添加到“操作”面板。

1. （可选）在面 **[!UICONTROL Schedule]** 板中，执行下列操作之一：

   * 单击 **[!UICONTROL Run Indefinitely]** 可在满足其关联触发器时运行规则。 此选项是默认值。
   * 单 **[!UICONTROL Fixed Schedule]**&#x200B;击，然后指定开始日期和时间以及规则在满足其关联触发器时运行的结束日期和时间。

1. 单击 **[!UICONTROL Save Rule]**.
1. （可选）在页 [!DNL Business Rules] 面上，执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 编辑业务规则 {#task_375CFA75D1D94D9E92A35DE1228E5087}

您可以使用可视规则生成器或高级规则生成器来编辑已添加的业务规则。

**编辑新业务规则**

1. 在产品菜单中，单击 **[!UICONTROL Rules]** > **[!UICONTROL Business Rules]**。
1. 在页 [!DNL Business Rules] 面上，执行下列操作之一：

   * 在列 [!DNL Name] 下，单击要更改的业务规则的名称。

      业务规则将在> **[!UICONTROL Settings]** >中指定的默认界面 **[!UICONTROL My Profile]** 中打开 **[!UICONTROL My Preferences]**。

   * 在下拉列表中，单击或，然后单击要编辑的业务规则名称 **[!UICONTROL Edit in advanced mode]** 旁边 **[!UICONTROL Edit in visual mode]**。

1. 在文本 [!DNL Name] 字段中，键入业务规则的新名称。

   请勿单击 **[!UICONTROL Save Rule]** 鼠标。 1.在页 [!DNL Business Rule Builder] 面中，设置要使用的触发器和操作。

   请参阅添加新业务 [规则下的选项表](../c-about-rules-menu/c-about-business-rules.md#task_BD3B31ED48BB4B1B8F1DCD3BFA2528E7)。
1. （可选）在任 **[!UICONTROL Business Rule Builder]** 意面板( [!DNL Triggers]、 [!DNL Actions]或，执 [!DNL Schedule]行下列任一操作：

   * 在页面的演示文稿模板区 [!DNL Business Rule Builder] 域中，右键单击横幅，然后单击 **[!UICONTROL Select different banner]**。 在中， [!DNL Pick Banner page]单击横幅 **[!UICONTROL Pick this banner]** 缩略图下方，将其添加到演示文稿模板中。 只有与演示文稿模板上原始横幅的大小和区域匹配的横幅才可供您选择。

      添加横幅操作将添加到面 [!DNL Actions] 板。

   * 在页面的演示文稿模板区 [!DNL Business Rule Builder] 域中，右键单击要更改其参数的Adobe Dynamic Media Classic模板横幅，然后单击 **[!UICONTROL Add banner commands]**。 在对 [!DNL Change Parameters] 话框中，设置所需的参数选项。

      请参阅使用Adobe Dynamic Media Classic [添加横幅中的选项表](../c-about-design-menu/c-about-banners.md#task_AD1E0C00A9E04B1FA819EB93288786B3)。

      单击 **[!UICONTROL Save]**.

      参数更改将添加到面 [!DNL Actions] 板。

      另请参 [阅使用Adobe Dynamic Media Classic编辑横幅](../c-about-design-menu/c-about-banners.md#task_C3E782477FBF428ABEA220751781ACA9)。

   * 在页面的演示文稿模板区 [!DNL Business Rule Builder] 域中，右键单击要从页面中删除的横幅，然后单击 **[!UICONTROL Remove banner]**。 删除横幅操作将添加到该 [!DNL Actions] 面板。

1. （可选）在面 [!DNL Schedule] 板中，执行下列操作之一：

   * 单击 **[!UICONTROL Run Indefinitely]** 可在满足其关联触发器时运行规则。 此选项是默认值。
   * 单 **[!UICONTROL Fixed Schedule]**&#x200B;击，然后指定开始日期和时间以及规则在满足其关联触发器时运行的结束日期和时间。

1. 单击 **[!UICONTROL Save Rule]**.

   页 [!DNL Business Rule Builder] 面将关闭，您将返回到该 **[!UICONTROL Business Rule]** 页面。 您的规则显示在表中。 单击列 **[!UICONTROL Modified]** 标题可按编辑日期对规则排序。 1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 复制业务规则 {#task_89F1879C71A54EE9B7454439302C03EC}

您可以复制现有业务规则以用作要创建的新业务规则的基础。

**复制业务规则**

1. 在产品菜单中，单击 **[!UICONTROL Rules]** > **[!UICONTROL Business Rules]**。
1. 在页 **[!UICONTROL Business Rules]** 面中，在要复制的业务规则名称旁边的下拉列表中，单击 **[!UICONTROL Copy rule]**。
1. 像往常一样编辑复制的业务规则。

   See [Editing a business rule](../c-about-rules-menu/c-about-business-rules.md#task_375CFA75D1D94D9E92A35DE1228E5087).

## 批准业务规则 {#task_BD569D18BF664272B8692294C162E2C1}

您可以激活状态为“WIP（在制品）”或“暂停”的业务规则。

**批准业务规则**

1. 在产品菜单中，单击 **[!UICONTROL Rule]** > **[!UICONTROL Business Rules]**。
1. 在页 [!DNL Business Rules] 面上，使用业务规则表列中的 [!DNL Status] 状态列标题，对状态为或的规则进行排序 **[!UICONTROL WIP]****[!UICONTROL suspended]**。

   使用表左侧的复选框列标题检查页面上当前显示的所有规则，或仅检查状态为或的 **[!UICONTROL WIP]** 规则 **[!UICONTROL suspended]**。 1.在页面顶部附近的菜单栏上，单击 **[!UICONTROL Approve]**。
1. 在对话 **[!UICONTROL Confirm Action]** 框中，单击 **[!UICONTROL OK]**。
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 暂停业务规则 {#task_364E1FFB905141C08E306C8F1794A20E}

您可以暂停状态为“WIP”（在制品）或“已批准”的业务规则。

暂停某个规则后，您将在用户界面中指示该规则暂时处于非活动状态，并将其上的任何工作再推迟一段时间。 但是，您仍可以编辑暂停的规则。

**暂停业务规则**

1. 在产品菜单中，单击 **[!UICONTROL Rule]** > **[!UICONTROL Business Rules]**。
1. 在页 [!DNL Business Rules] 面上，使用业务规则表的状态列中的状态，在表的最左侧列中检查状态为或的 **[!UICONTROL WIP]**&#x200B;规则 **[!UICONTROL approved]**。
1. 在页面顶部附近的菜单栏上，单击 **[!UICONTROL Suspend]**。
1. 在对话 **[!UICONTROL Confirm Action]** 框中，单击 **[!UICONTROL OK]**。
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 恢复业务规则 {#task_E67D678C765B436EA2A3D6ADD7A49ABA}

您可以恢复业务规则以重新激活暂停的规则。 在恢复业务规则后，其状态将设置为“WIP（进行中的作品）”。

**恢复业务规则**

1. 在产品菜单中，单击 **[!UICONTROL Rule]** > **[!UICONTROL Business Rules]**。
1. 在页 [!DNL Business Rules] 面中，使用业务规则表的状态列中的状态，在表的最左侧列中检查状态为的规则 **[!UICONTROL suspended]**。
1. 在页面顶部附近的菜单栏上，单击 **[!UICONTROL Resume]**。
1. 在对话 [!DNL Confirm Action] 框中，单击 **[!UICONTROL OK]**。
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 更改业务规则的运行顺序 {#task_FE3B1C17307F49B49050C2EC5A063991}

您可以对业务规则重新排序，以更改它们在演示文稿模板上运行的顺序。

商业规则按照定义的顺序运行；规则的编号越高，越晚在该过程中运行，比之前的规则要大。 可通过在页面上表的“顺序”列中输入新编号来重新排序规 [!DNL Business Rules] 则。 您还可以对规则使用拖放来更改其运行顺序。

**更改业务规则运行的顺序**

1. 在产品菜单中，单击 **[!UICONTROL Rule]** > **[!UICONTROL Business Rules]**。
1. 在页 [!DNL Business Rules] 面的表中，执行下列任一操作：

   * 单击列 **[!UICONTROL Order]** 标题以按升序或降序对规则进行排序。
   * 在列 **[!UICONTROL Order]** 中，在业务规则名称左侧的文本字段中，键入要运行规则的订单编号。
   * 将表行拖放到希望规则运行的位置。 所有订单编号都会更新以反映规则运行的新顺序。

1. 单击 **[!UICONTROL Save Changes]**.

   您的业务规则现在将按您指定的顺序运行。 例外情况是，如果指定了重定向业务规则。 当触发或点击重定向业务规则时，业务规则处理停止以允许重定向。
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 删除业务规则 {#task_AE37B42412044541BCC6D46CF8793DFF}

您可以使用“批量操作”下拉菜单删除状态为WIP、暂停或批准的业务规则。

**删除业务规则**

1. 在产品菜单中，单击 **[!UICONTROL Rules]** > **[!UICONTROL Business Rules]**。
1. 在页 [!DNL Business Rules] 面上，执行下列操作之一：

   * 使用复选框列标题检查页面上当前显示的所有规则。
   * 根据表的“状态”列中的状态，仅检查要删除的业务规则。

1. 在下 [!DNL Bulk Actions] 拉列表中，单击 **[!UICONTROL Delete]**。
1. 在对话 [!DNL Confirm Action] 框中，单击 **[!UICONTROL OK]**。
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。
