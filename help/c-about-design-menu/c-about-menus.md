---
description: 您可以使用菜单自定义您的表示层。
solution: Target
subtopic: Navigation
title: 关于菜单
topic: 设计、网站搜索和销售
uuid: 011050cd-21b6-4150-9503-18fa3f771626
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 1%

---


# 关于菜单{#about-menus}

您可以使用菜单自定义您的表示层。

## 使用菜单{#concept_68123CE5CF4447B59217B5D721424E32}

添加映射到搜索中设置的菜单。 菜单中的每个项指定菜单设置的值。 您还可以自定义菜单标签。

在演示文稿模板中，您可以引用定义的菜单。 然后，您可以将它们放入所需的任何HTML组件中，如选择控件。 此组合使用户能够自定义其搜索结果。 支持三种菜单类型：排序、计数和导航。

## 添加新菜单{#task_EE171532D3AE477FAFE8C2F4077A6D73}

您可以添加映射到搜索结果中设置的菜单。

<!-- 

t_adding_a_new_menu.xml

 -->

>[!NOTE]
>
>请确保引用演示文稿模板中的菜单，以便该菜单在网站上可见。

**添加新菜单**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Menus]**。
1. 在[!DNL Menus]页面上，单击&#x200B;**[!UICONTROL Add New Menu]**。
1. 在[!DNL Add Menu]页面上，设置所需的选项。

   这些设置影响痕迹导航的行为和默认演示。 您可以通过演示文稿模板的设置覆盖其中的一些设置。

   请参阅[关于菜单](../c-about-design-menu/c-about-menus.md#concept_68123CE5CF4447B59217B5D721424E32)。

   <!-- 
   r_add_menu_options.xml
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
      <td colname="col1"> <p>菜单名称 </p> </td> 
      <td colname="col2"> <p>菜单的名称。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>菜单类型 </p> </td> 
      <td colname="col2"> <p>设置以下三种菜单类型之一： </p> <p> 
      <ul id="ul_7E66ACC1DA494B20BEC3B0B2CCAB103A"> 
      <li id="li_D81876660A8B48AFB70D3317063FBF6F"> <span class="uicontrol"> 排序 </span> <p>按任何定义的元数据类型组织您的搜索。 </p> <p>例如，您可以定义具有以下元数据类型的排序菜单：三项相关性；自定义元数据字段，如可用性代码；和价格。 这三个项目可分别标有“按相关性排序”、“按可用性排序”和“按价格排序”。 在您的演示文稿模板中包含此控件时，客户可以使用此控件对其搜索结果进行排序。 </p> </li> 
      <li id="li_63AE06B544B64DCAA8C55031B3DFFFF7"> <span class="uicontrol"> 计数 </span> <p>定义要显示的搜索结果数。 此菜单类型映射到cgi参数<span class="varname"> sp_c </span>。 </p> <p>请参阅<a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" format="dita" scope="local">后端搜索CGI参数</a>。 </p> </li> 
      <li id="li_EEC810D420FF41498ECE49EBAAB33BE5"> <span class="uicontrol"> 导航 </span> <p>指定与菜单项关联的一组静态URL。 通常，导航菜单用于在搜索结果页面上创建顶级导航栏。 </p> <p>例如，您可以创建一个菜单，其中包含女性、男性、男孩和女孩，菜单项类似于： 
      <code>
        /?q1=womens;x1=gender 
      </code>, 
      <code>
        /?q1=mens;x1=gender 
      </code> </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>促销 </p> 
        <!--DONT' KNOW WHAT THIS DOES--> </td> 
      <td colname="col2"> <p>此选项仅在选择菜单类型<span class="uicontrol">排序时才可用。</span> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>菜单中的项数 </p> </td> 
      <td colname="col2"> <p>指定菜单中的项数。 更改此设置将添加或删除表单中的字段。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>默认项 </p> </td> 
      <td colname="col2"> <p>允许您选择默认显示的菜单项。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>项目值 </p> </td> 
      <td colname="col2"> <p>项目值取决于您设置的菜单类型。 </p> 
        <ul id="ul_2F14E6AA673640578A2D5161FD9D13EF"> 
        <li id="li_5017EC6E4ACB4B8E99E0AA61CBAAFFAE"> 排序菜单类型 <p>标识菜单中选定项的排序依据。 所选项目将填充可排序的元数据字段。 </p> <p>对于单个项目，可以按三个元数据字段排序。 排序按指定的顺序进行。 </p> </li> 
        <li id="li_CC6BAFBF969C4367A71B55F08E0758D1"> 计数菜单类型 <p>允许您指定客户选择此菜单项时要返回的结果数。 </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>项目标签 </p> </td> 
      <td colname="col2"> <p>项目标签取决于您设置的菜单类型。 </p> 
        <ul id="ul_957BF01235F84748B5EB7062D6AEAC41"> 
        <li id="li_03FB2E2C96134A2B8E08154F87F0CD55"> 排序菜单类型 <p>标识您希望客户在菜单中视图此项目时看到的自定义标签。 </p> </li> 
        <li id="li_C9FE2BC46D9443FB85FEB837C7CA45E1"> 计数菜单类型 <p>标识要为此菜单项显示的自定义标签。 </p> </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Add]**.
1. （可选）在[!DNL Menus]页面上，执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 编辑菜单{#task_0770DBFD0C7046169097FB6F771B9114}

您可以编辑已添加的任何菜单的设置。

<!-- 

t_editing_a_menu.xml

 -->

>[!NOTE]
>
>请确保引用演示文稿模板中的菜单，以便该菜单在网站上可见。

**编辑菜单**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Menus]**。
1. 在[!DNL Menus]页面上，单击菜单名称最右侧的&#x200B;**[!UICONTROL Edit]**。
1. 在[!DNL Edit Menu]页面上，设置所需的选项。

   请参见[添加新菜单](../c-about-design-menu/c-about-menus.md#task_EE171532D3AE477FAFE8C2F4077A6D73)下的选项表。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）在[!DNL Menus]页面上，执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 删除菜单{#task_645E212311A045CD8D9D906878165F47}

可以删除已添加的任何菜单。

<!-- 

t_deleting_a_menu.xml

 -->

**删除菜单**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Menus]**
1. 在[!DNL Menus]页面上，单击菜单名称最右侧的&#x200B;**[!UICONTROL Delete]**。
1. 在[!DNL Confirmation]对话框中，单击&#x200B;**[!UICONTROL OK]**。
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

