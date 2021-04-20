---
description: 使用“帐户选项”菜单可更新帐户设置、设置促销首选项或删除您自己的Search&amp;Promote帐户。
solution: Target
subtopic: Account Options
title: 关于“帐户选项”菜单
topic: Settings,Site search and merchandising
uuid: 0f830033-de9e-4197-8d76-906c818662eb
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1662'
ht-degree: 2%

---


# 关于“帐户选项”菜单{#about-the-account-options-menu}

使用“帐户选项”菜单可更新帐户设置、设置促销首选项或删除您自己的Search&amp;Promote帐户。

## 配置帐户设置{#task_80A38D0C8E4F453395BD67B81E4B45D9}

管理帐户设置，如网站名称和地址、时区等。 或者，视图您的帐号。

**配置帐户设置**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Account Settings]**。
1. 在[!DNL Account Settings]页面上，设置所需的选项。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>网站名称 </p> </td> 
      <td colname="col2"> <p>必需。 </p> <p>用于描述您的网站/帐户的简称。 如果您有多个网站，则此选项很有用。 </p> <p> <p>注意： 您必须与技术支持部门联系以选择要使用的一个或多个名称。 </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>网站地址 </p> </td> 
      <td colname="col2"> <p>必需。 </p> <p>您网站的URL地址。 此处指定的地址用作主网站入口点。 </p> <p>另请参阅<a href="../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45" type="task" format="dita" scope="local">添加要索引的多个URL入口点</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>时区（用于报告和计划） </p> </td> 
      <td colname="col2"> <p>用于报告和发布操作的时区。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>在保存时验证模板标签属性 </p> </td> 
      <td colname="col2"> <p>在分阶段模板编辑器中保存模板时，验证<span class="codeph"> &lt;guided-*&gt; </span>和<span class="codeph"> &lt;search-*&gt; </span>中的所有属性。 </p> <p>请参阅<a href="../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3" type="task" format="dita" scope="local">编辑演示文稿或传输模板</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>在保存时验证对GS对象的模板引用 </p> </td> 
      <td colname="col2"> <p> 检查“向导搜索”对象（如菜单、彩块化、痕迹导航、自定义变量和模板）是否存在，这些对象在<span class="codeph"> &lt;向导 — *&gt; </span>标签中均有引用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>实施严格的模板语法检查 </p> </td> 
      <td colname="col2"> <p>使模板验证程序更加严格，并允许检查不平衡引号和&lt;&gt;符号等内容。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>帐号 </p> </td> 
      <td colname="col2"> <p>您无法编辑帐号。 它仅用于显示目的。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Save Changes]**.

## 配置与Adobe CQ5 {#task_EA2FC2C24960498DAE01A1AB769D2F14}的集成

您可以配置网站搜索/促销与Adobe CQ5的集成。

**配置与Adobe CQ5的集成**

1. 通过执行以下操作，获取您的会员ID和帐户ID:

   * 登录您的网站搜索/促销帐户。
   * 在URL路径中，复制成员ID和帐户ID。

      例如，如果您帐户的URL路径为`https://searchandpromote.mycompany.com/px/home/?sp_id=00123a4b-sp1234a5b6`，则成员ID将为`00123a4b`，而帐户ID将为`sp1234a5b6`。

1. 在Adobe CQ5中，使用“Cloud Services”选项卡可创建网站搜索/促销配置。

   将复制的成员ID和帐户ID用于相应的设置。

## 配置促销首选项{#task_7AC7B9F5D9F44E10AB5BC0B8CB31C37A}

管理促销首选项，如默认规则生成器和默认搜索词。

**配置促销首选项**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Merchandising Preferences]**。
1. 在[!DNL Merchandising Preferences]页面上，设置所需的选项。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>触发组主阈值 </p> </td> 
      <td colname="col2"> <p> 要应用于指定“使用帐户默认值”的基于结果的“组主导”触发器的阈值百分比。 </p> <p>更改此设置会立即影响实时搜索，因此请谨慎使用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>组定义 </p> </td> 
      <td colname="col2"> <p>促销控制台的组中的结果数。 最大为50,000。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> “销售文档ID”(MDI)字段 </p> </td> 
      <td colname="col2"> <p> 您指定的字段必须通过基于结果的“单一结果”触发器和操作来“统一”要处理的搜索结果。 </p> <p>在某些情况下，使用预定义的URL字段是有效的，但不建议这样做。 与使用URL字段相比，每个页面（如SKU或product_id）都具有唯一ID的用户定义元字段将更加高效。 指定“无”将禁用规则管理器中基于结果的“单个结果”触发器和操作。 更改此选项仅适用于将来保存的规则；现有规则继续使用最初保存它们的计量吸入器。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>默认VRB（可视规则生成器）搜索词 </p> </td> 
      <td colname="col2"> <p> 允许您自定义在可视规则生成器中使用的初始搜索词。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>VRB默认搜索 </p> </td> 
      <td colname="col2"> <p>通过此设置，可设置在可视规则生成器中最初选择的默认搜索。 </p> <p> 此设置仅与具有多个搜索的实施相关。 VRB允许您选择定义的组所应用的触发器或操作的搜索内容。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>VRB/模拟器超时 </p> </td> 
      <td colname="col2"> <p>VRB和模拟器通过比生产搜索更慢的代理服务器发送搜索。 在某些情况下（如缓慢加载资产），VRB或模拟器可能会超时。 您可以增加或减少用户界面在停止前必须等待的秒数。 您很少需要将此设置从默认值60增加。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Save Changes]**.

## 配置对您的Adobe Dynamic Media Classic帐户{#task_CEFF88C2033D41D0B2FE86C435EDAC6D}的访问

将您的网站搜索/促销帐户关联到Adobe Dynamic Media Classic，以便您能够使用从Adobe Scene7上传的数字资产轻松将横幅广告添加到您的网站。

请参阅[关于横幅](../c-about-design-menu/c-about-banners.md#concept_5BBE01FEC6134393B43CC917C8CC64DA)。

请参阅[使用Adobe Dynamic Media Classic](../c-about-design-menu/c-about-banners.md#task_AD1E0C00A9E04B1FA819EB93288786B3)添加横幅。

**配置对您的Adobe Dynamic Media Classic帐户的访问权限**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Scene7 Configuration]**。
1. 在[!DNL Scene7 Configuration]页面上，设置所需的选项。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>区域 </p> </td> 
      <td colname="col2"> <p>必需。标识您的Dynamic Media Classic帐户访问各种Dynamic Media Classic服务器的世界区域。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>默认公司 </p> </td> 
      <td colname="col2"> <p>标识与您的Dynamic Media Classic帐户关联的公司的名称。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> 电子邮件 </p> </td> 
      <td colname="col2"> <p>必需。标识用于Dynamic Media Classic登录和通信的电子邮件地址。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>密码 </p> </td> 
      <td colname="col2"> <p>必需。您的Dynamic Media Classic登录密码。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>启用 </p> </td> 
      <td colname="col2"> <p>启用网站搜索/促销中的所有Dynamic Media Classic控件。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>测试 </p> </td> 
      <td colname="col2"> <p>验证您的Dynamic Media经典区域名称、电子邮件地址和密码详细信息是否正确。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. （可选）单击&#x200B;**[!UICONTROL Test]**&#x200B;验证您的Dynamic Media经典区域名称、电子邮件地址和密码详细信息是否正确。
1. 单击 **[!UICONTROL Save Changes]**.

## 配置Adobe Analytics重定向器{#task_2C9DE333FD7246E4A460FC0F55204160}

如果使用[!DNL Adobe Analytics]跟踪网站访客，则可在网站搜索/促销中使用[!DNL Adobe Analytics Redirector]跟踪[!DNL Adobe Analytics]的所有HTTP重定向。

**配置Adobe Analytics重定向器**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Adobe Analytics Redirector]**。
1. 在[!DNL Adobe Analytics Redirector]页面上，设置所需的选项。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>启用Adobe Analytics重定向器功能 </p> </td> 
      <td colname="col2"> <p>使用Adobe Analytics打开跟踪HTTP重定向。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>跟踪服务器 </p> </td> 
      <td colname="col2"> <p> 标识您的Adobe Analytics跟踪服务器名。 </p> <p>要查找跟踪服务器名称， </p> <p> 
      <ol id="ol_D17B77E81F8D40D0948415CD60839BE3"> 
      <li id="li_BE58DBA104D44F0DB6C64AD3F12CEA97"> 在Adobe Analytics中，单击<span class="uicontrol">管理</span> &gt; <span class="uicontrol">Admin Console</span> &gt; <span class="uicontrol">代码管理器</span>。 </li> 
      <li id="li_67A93D17C3A14874928C6DC4FF2D4784"> 在<span class="wintitle">选项</span>组框中，从相应的下拉列表中选择一个报表包。 </li> 
      <li id="li_5AAB004AC58441DBB0F813BDE30EFFD4"> 单击<span class="uicontrol">生成代码</span>。 </li> 
      <li id="li_E80368993F4D4DD69E37509FF4348B36"> 在<span class="wintitle">代码管理器</span>页面上，单击<span class="uicontrol">核心Javascript文件选项卡</span>。 </li> 
      <li id="li_991BDCDDA41A445F85CEEAAE9A46A304"> 在<span class="wintitle">配置部分</span>中，找到如下所示的行： <p> <code> s.trackingServer="yourcompany.122.2o7.net" </code> </p> <p>在本例中，跟踪服务器名称为<span class="codeph"> "yourcompany.122.2o7.net" </span> </p> </li> 
      </ol> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>报表包 ID </p> </td> 
      <td colname="col2"> <p> 标识您的报表包ID。 </p> <p>要了解您的报表包ID， </p> <p> 
      <ol id="ol_4FD7B2459358486DBDB130426131D16A"> 
      <li id="li_9AF624CEB128453C808892EEE385D5D1"> 在Adobe Analytics中，单击<span class="uicontrol">管理</span> &gt; <span class="uicontrol">Admin Console</span> &gt; <span class="uicontrol">报表包</span>。 </li> 
      <li id="li_AAC47EAA04144A67BDCB5C7B8D8098E9"> 查看表中的<span class="wintitle">报表包ID </span>列以查找ID。 </li> 
      </ol> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>自定义参数 </p> </td> 
      <td colname="col2"> <p>允许您向Adobe Analytics重定向URL添加自定义参数。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>将所有自定义值的大小写设置为 </p> </td> 
      <td colname="col2"> <p>允许您对用于您在上面指定的任何自定义参数值的大小写进行标准化。 Adobe Analytics区分大小写，因此有理由统一值。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）如果要预览结果，请重新构建分阶段站点索引。

   请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在[!DNL Adobe Analytics Redirector]页面上，执行下列任一操作：

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 配置根文件{#task_5F175C8743FB49A2A003813CBF7C56BF}

管理网站根文件夹中的根文件。

**配置根文件**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Root Files]**。
1. 在[!DNL Root Files]页面上，浏览到要上载的根文件。

   <table> 
    <thead> 
    <tr> 
      <th colname="col1" class="entry"> <p>根文件 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
      <td colname="col1"> <p>favicon.ico </p> </td> 
      <td colname="col2"> <p> 站点的图标。 通常，它显示在客户浏览器的地址栏中。 </p> </td> 
    </tr> 
    <tr> 
      <td colname="col1"> <p>robots.txt </p> </td> 
      <td colname="col2"> <p>允许或禁止机器人访问网站的某些部分。 </p> </td> 
    </tr> 
    <tr> 
      <td colname="col1"> <p>sitemap.xml </p> </td> 
      <td colname="col2"> <p>包含网站上所有页面列表的XML文件。 </p> </td> 
    </tr> 
    <tr> 
      <td colname="col1"> <p>crossdomain.xml </p> </td> 
      <td colname="col2"> <p>允许或禁止Flash Player跨域访问文件。 </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）如果要预览结果，请重新构建分阶段站点索引。

   请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在[!DNL Root Files]页面上，执行下列任一操作：

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 将帐户所有权转移给其他帐户用户{#task_47E3C66CC6374274830DA10171E0CF17}

作为帐户所有者，如果要取消登录，您必须首先将所有权转移给其他有效帐户用户。 可以使用[!DNL Transfer Ownership]完成此任务。

您可以将所有权转移给任何现有网站搜索/促销帐户用户。

当所有权转让完成时，新帐户所有者会收到一封电子邮件通知，而该职位的前所有者将被免除该职位的限制和责任。

每个帐户只能有一个所有者。 如果您将您的所有权转让给其他用户，则您不再具有所有权权限。

请参阅[取消登录](../c-about-settings-menu/c-about-my-profile-menu.md#task_D57701BB726243B08CEA14EEC86C3087)。

请参阅[删除帐户](../c-about-settings-menu/c-about-account-options-menu.md#task_975178D5B9444BF8B52D72B897A49C32)。

请参阅[从帐户](../c-about-settings-menu/c-about-account-options-menu.md#task_C56F5AB87B664BAAAC2FD2F15003E73F)中删除您自己。

**要将帐户所有权转移到其他帐户**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Transfer Ownership]**。
1. 在[!DNL Transfer Ownership]页面上，单击要对您的帐户拥有所有权的用户。
1. 单击 **[!UICONTROL Transfer]**.

## 删除帐户{#task_975178D5B9444BF8B52D72B897A49C32}

您可以从网站搜索/促销中完全删除帐户。 在您这样做时，您和帐户的任何其他用户都不再有权访问它。

删除帐户后，将不再能用于为活动站点编制索引或搜索活动站点。 此外，

要允许其他用户继续使用此帐户，您可以将所有权转移给其他用户，然后以帐户用户身份删除您自己。

请参阅[将帐户所有权转移给其他帐户用户](../c-about-settings-menu/c-about-account-options-menu.md#task_47E3C66CC6374274830DA10171E0CF17)。

如果您有其他帐户，则在删除当前帐户后，您将转到登录中列出的第一个帐户。

请参阅[从帐户](../c-about-settings-menu/c-about-account-options-menu.md#task_C56F5AB87B664BAAAC2FD2F15003E73F)中删除您自己。

请参阅[取消登录](../c-about-settings-menu/c-about-my-profile-menu.md#task_D57701BB726243B08CEA14EEC86C3087)。

**删除帐户**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Remove Account]**。
1. （可选）在[!DNL Reason for Removal]字段中，输入帐户删除的原因。
1. 单击 **[!UICONTROL Remove Account]**.

## 从帐户{#task_C56F5AB87B664BAAAC2FD2F15003E73F}中删除您自己

您可以从网站搜索/促销帐户中删除您自己。

从帐户中删除您自己后，将无法再访问该帐户，也无法编辑帐户设置或使用帐户设置为网站编制索引。

要重新获得对帐户的访问权限，请要求当前帐户用户恢复您的身份。

请参阅[取消登录](../c-about-settings-menu/c-about-my-profile-menu.md#task_D57701BB726243B08CEA14EEC86C3087)。

请参阅[删除帐户](../c-about-settings-menu/c-about-account-options-menu.md#task_975178D5B9444BF8B52D72B897A49C32)。

请参阅[将帐户所有权转移给其他帐户用户](../c-about-settings-menu/c-about-account-options-menu.md#task_47E3C66CC6374274830DA10171E0CF17)。

**从帐户中删除您自己**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Remove Yourself]**。
1. 单击 **[!UICONTROL Remove Yourself]**.
