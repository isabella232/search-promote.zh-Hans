---
description: 痕迹导航是可添加到网站的导航控件。 痕迹导航可为客户提供有关其在搜索结果集中所处位置的反馈。 它还有助于他们快速返回上一步。
seo-description: 痕迹导航是可添加到网站的导航控件。 痕迹导航可为客户提供有关其在搜索结果集中所处位置的反馈。 它还有助于他们快速返回上一步。
seo-title: 关于痕迹导航
solution: Target
subtopic: Navigation
title: 关于痕迹导航
topic: Design,Site search and merchandising
uuid: 3e630a72-a631-4f4f-8aa5-adf2882cdf1c
translation-type: tm+mt
source-git-commit: 7f1b5d94e8002992d62ec1e3dce11f9c5605fde8
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 1%

---


# 关于痕迹导航{#about-breadcrumbs}

痕迹导航是可添加到网站的导航控件。 痕迹导航可为客户提供有关其在搜索结果集中所处位置的反馈。 它还有助于他们快速返回上一步。

## 使用痕迹导航{#concept_FB8A943C594A4A1593B118141DA61F03}

痕迹导航会跟踪搜索的词以及选择的用于缩小结果集的后续彩块化。

使用痕迹导航设置可自定义搜索演示层的痕迹导航控制。 如果您的表示层有多组搜索结果，痕迹导航控件将用于页面上的主搜索。

您可以编辑痕迹导航以更改默认行为、最大值宽度和值扩展，并选择是否包含查询项。

## 添加新的痕迹导航{#task_2FFA94F82AE74F10BDDE7367CDCEAE8B}

您可以添加痕迹导航栏，以便客户能够跟踪他们在您网站上的位置。

<!-- 

t_adding_a_new_breadcrumb.xml

 -->

>[!NOTE]
>
>请确保在演示文稿模板中引用痕迹导航，以使痕迹导航在网站上可见。

**添加新痕迹导航**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**。
1. 在[!DNL Breadcrumbs]页面上，单击&#x200B;**[!UICONTROL Add Breadcrumb]**。
1. 在[!DNL Add Breadcrumb]页面上，设置所需的选项。

   这些设置影响痕迹导航的行为和默认演示文稿。 您可以通过演示文稿模板的设置覆盖其中的一些设置。

   <!-- 
   
   r_breadcrumb_options.xml
    
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
      <td colname="col1"> <p>痕迹导航名称 </p> </td> 
      <td colname="col2"> <p>痕迹导航的名称。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>行为 </p> </td> 
      <td colname="col2"> <p>设置以下三种痕迹导航行为之一： </p> <p> 
      <ul id="ul_7E66ACC1DA494B20BEC3B0B2CCAB103A"> 
        <li id="li_D81876660A8B48AFB70D3317063FBF6F"> <span class="uicontrol"> Goto  </span> <p>跳转将删除单击后的所有痕迹导航，并在该点开始新搜索。 </p> </li> 
        <li id="li_63AE06B544B64DCAA8C55031B3DFFFF7"> <span class="uicontrol"> 删除 </span> <p>从客户单击的痕迹导航路径中删除删除，然后开始新搜索。 当您希望让客户撤消在搜索中向下钻取的步骤时，此行为很有用。 </p> </li> 
        <li id="li_EEC810D420FF41498ECE49EBAAB33BE5"> <span class="uicontrol"> 删除  </span> <p>“删除”会删除所有痕迹导航。 </p> </li> 
      </ul> </p> <p> 例如，假设您的痕迹导航为1 &gt; 2 &gt; 3 &gt; 4。 当客户单击“2”时，根据您选择的行为，它会得到以下结果： </p> <p> 
      <ul id="ul_96FCD8E4C3704B45B59BC18A7A1AC52A"> 
        <li id="li_B880037088DF426F880788EAA3072180">转到- 1 &gt; 2 </li> 
        <li id="li_D0F07A15DCD043EFA4563632ED33A9E2">删除- 1 &gt; 3 &gt; 4 </li> 
        <li id="li_D848ED44B4E44538AA92010F9F186224"> 删除——删除整个痕迹导航，使客户在开始向下钻取之前回到点。 </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最大值宽度 </p> </td> 
      <td colname="col2"> <p>指定痕迹导航跟踪中每个值的长度。 将设置指定为多个字符。 </p> <p>例如，设置为6表示痕迹导航跟踪长度最长可达6个字符，包括空格。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>值扩展 </p> </td> 
      <td colname="col2"> <p>指定在痕迹导航被截断时要使用的椭圆。 </p> <p>默认情况下为“...” （椭圆）。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>包含查询期限 </p> </td> 
      <td colname="col2"> <p>控制痕迹导航中存在查询项。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>启用用户定义的路径 </p> </td> 
      <td colname="col2"> <p>检查以允许您使用URL中的<span class="codeph"> uX=[name]&amp;[name]=[value] </span>参数在痕迹导航中使用用户定义的项。 您可以使用处理规则按您需要的方式处理此参数。 </p> <p>例如，如果启用此功能，并且您有URL<code> https://search.host.com/?1=category&amp;q1=Clothes&amp;u2= 
          type&amp;type=Men&amp;x3=kind&amp;q3=Sweater </code>(如果您有facet <span class="codeph"> <span class="varname">类别</span> </span>和<span class="codeph"><span class="varname">类型</span> </span>)，则您的痕迹导航将看起来像<span class="codeph">服装&gt;男士&gt;</span>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>用户定义的Crumb名称 </p> </td> 
      <td colname="col2"> <p>以逗号分隔的列表符，包含用户定义的痕迹导航项的所有可能名称。 </p> <p>仅当选中<span class="uicontrol">启用用户定义的路径</span>时，此选项才可用。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Add]**.
1. （可选）在[!DNL Breadcrumbs]页面上，执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;以还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 编辑痕迹导航{#task_583481D9A23E4E0F97AEB18E72CBE13F}

您可以编辑已添加的任何痕迹导航的设置。

<!-- 

t_editing_a_breadcrumb.xml

 -->

>[!NOTE]
>
>请确保在演示文稿模板中引用痕迹导航，以使痕迹导航在网站上可见。

**编辑痕迹导航**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**。
1. 在[!DNL Breadcrumbs]页面上，单击痕迹导航名称最右侧的&#x200B;**[!UICONTROL Edit]**。
1. 在[!DNL Edit Breadcrumb]页面上，设置所需的选项。

   请参阅[添加新痕迹导航](../c-about-design-menu/c-about-breadcrumbs.md#task_2FFA94F82AE74F10BDDE7367CDCEAE8B)下的选项表。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）在&#x200B;**[!UICONTROL Breadcrumb]**&#x200B;页面上，执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;以还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 删除痕迹导航{#task_401C6E481A744284906E15A29E04F757}

您可以删除已添加的任何痕迹导航。

<!-- 

t_deleting_a_breadcrumb.xml

 -->

**删除痕迹导航**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**。
1. 在[!DNL Breadcrumbs]页面上，单击痕迹导航名称最右侧的&#x200B;**[!UICONTROL Delete]**。
1. 在[!DNL Confirmation]对话框中，单击&#x200B;**[!UICONTROL OK]**。
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;以还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

