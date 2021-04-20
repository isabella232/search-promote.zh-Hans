---
description: 您可以使用增量索引为实时网站或分阶段网站（如频繁更改的页面集合）的“片段”编制索引。
solution: Target
subtopic: Incremental Index
title: 关于增量索引
topic: Index,Site search and merchandising
uuid: b1ee9b08-dcbe-4ffe-b0b4-d379daaac9b5
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1357'
ht-degree: 1%

---


# 关于增量索引{#about-incremental-index}

您可以使用增量索引为实时网站或分阶段网站（如频繁更改的页面集合）的“片段”编制索引。

## 使用增量索引{#concept_A7770F0552D14C47B3DDB65DB78FFFEE}

增量索引只需几秒钟即可执行，对于需要数小时才能完全索引的大容量网站非常有用。

生成增量索引时，将显示状态信息，如开始时间、已用时间和索引过程中的错误。 还将显示有关上一个索引状态的信息。

您可以随时停止或重新启动增量索引过程。

新增索引构建于您的实时网站时，客户可以继续使用您上次的增量索引搜索您的网站。

## 配置分阶段网站{#task_46A367B0786C4C90BFFA5D3F95FD86C0}的增量索引

您可以通过指定网站URL和URL蒙版来配置要包含在增量索引中的网站页面。

**配置分阶段网站的增量索引**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Configuration]**。
1. 在&#x200B;**[!UICONTROL Incremental Index Configuration]**&#x200B;页面上，使用各种字段指定要索引的页面。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>字段 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>添加或更新URL </p> </td> 
      <td colname="col2"> <p>指定URL。 </p> <p>搜索自动机仅对自您上次编制索引以来已更改的指定文档进行索引。 </p> <p>此外，搜索自动机会遵循包含在指定文档中的链接，并仅对已更改的文档进行索引。 </p> <p>此字段必须仅包含文档URL，而不包含蒙版，如以下示例中所示： </p> <p> 
        <code>
          https://www.mydomain.com/products/new.html 
        </code> </p> <p>您可以在URL中使用以下关键字： </p> <p> 
        <ul id="ul_62D1082ACBD547D092B10D72C56A3A1E"> 
          <li id="li_32C2B21DE75C4459908384CC44822F7D"> 
          <code>
            noindex 
          </code> <p>如果不想为页面上与指定URL匹配的文本编制索引，但想要跟踪页面链接，请添加 
            <code>
              noindex 
            </code>在URL之后，如下例所示： </p> <p> 
            <code>
              https://www.mydomain.com/products/new.html noindex 
            </code> </p> <p>确保您 
            <code>
              noindex 
            </code>，来自带空格的URL;逗号不是有效的分隔符。 </p> </li> 
          <li id="li_33AB62B669084BF7B976F4308715E435"> 
          <code>
            nofollow 
          </code> <p>如果要为页面上与指定URL匹配的文本编制索引，但不希望跟踪页面链接，请添加 
            <code>
              nofollow 
            </code>在URL之后，如下例所示： </p> <p> 
            <code>
              https://www.mydomain.com/products/new.html nofollow 
            </code> </p> <p> 确保您 
            <code>
              nofollow 
            </code>，来自带空格的URL;逗号不是有效的分隔符。 </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>查找和更新URL蒙版 </p> </td> 
      <td colname="col2"> <p>指定简单的URL蒙版 — 完整路径、部分路径或使用通配符或常规表达式的路径。 </p> <p>搜索自动机只查找自您上次编制索引以来已更改的所有匹配文档和索引。 </p> <p>此外，搜索自动机会跟踪包含在匹配文档中的链接，并仅对那些已更改的页面进行索引。 例如： </p> <p> 
      <code>
        https://www.mydomain.com/products/household/*.html 
      </code> </p> <p>您还可以使用常规表达式，如下例所示： </p> <p> 
      <code>
        regexp ^https://www\.mydomain\.com/products/household/.*\.html$ 
      </code> </p> <p>请参阅<a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local">常规表达式</a>。 </p> <p>您还可以使用关键字 
      <code>
        nofollow 
      </code>和 
      <code>
        noindex 
      </code>，如上面的<span class="uicontrol">添加或更新URL </span>中所述。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>包含和排除URL蒙版 </p> </td> 
      <td colname="col2"> <p>指定简单包括或排除URL蒙版 — 完整路径、部分路径或使用通配符或常规表达式的路径。 </p> <p>搜索自动机根据指定的蒙版类型查找和索引("include")或忽略("exclude")文档。 </p> <p> 在为站点编制索引时，将按照外观的顺序进行指示。 例如，蒙版的以下列表: </p> <p> 
      <code>
        include https://www.mydomain.com/products/household/lightbulbs*.html 
      </code> </p> <p> 
      <code>
        exclude https://www.mydomain.com/products/ 
      </code> </p> <p>索引页面 
      <code>
        lightbulbs1.html 
      </code>和 
      <code>
        lightbulbs2.html 
      </code>。 但是，它不会为产品目录下列出的任何其他页面编制索引。 </p> <p>首先显示的URL蒙版始终优先于稍后在列表中显示的URL蒙版。 此外，如果搜索自动机遇到与包含蒙版和排除蒙版匹配的文档，则首先列出的蒙版优先。 </p> <p>您还可以使用关键字 
      <code>
        nofollow 
      </code>和 
      <code>
        noindex 
      </code>，如上面的<span class="uicontrol">添加或更新URL </span>中所述。 </p> <p>请参阅<a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164" type="concept" format="dita" scope="local">关于URL蒙版</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>包含和排除日期蒙版 </p> </td> 
      <td colname="col2"> <p>指定简单包含或排除日期蒙版 — 完整路径、部分路径或使用通配符或常规表达式的路径。 </p> <p>搜索自动机根据URL和文档日期查找和索引(“include”)或忽略(“exclude”)文档。 </p> <p>您可以使用以下类型的日期蒙版： </p> <p> 
      <ul id="ul_8958ED54C8EF405AA259236595ED3ABA"> 
      <li id="li_0A7841767E004F088CA6FA42E99B9F32"> 
      <code>
        include-days NNN 
      </code> <p>搜索自动机将所有与指定的URL蒙版匹配且NNN天或更旧的文档编入索引。 </p> <p>您可以使用以下一个或多个关键字跟随URL掩码： 
        <ul id="ul_22A38D5F38B344ABB02B16EB1865813B"> 
        <li id="li_B89CC37DC2A1428185E86FFCB9DDB193">nofollow </li> 
        <li id="li_C2579B3A338D4AF987C3F518806734B0">noindex </li> 
        <li id="li_0527BF7103F34B83AC3E684069B899F7">server-date </li> 
        </ul> </p> <p>例如，以下掩码包括/archive/support文件夹中0天或更早的所有文档: </p> <p> 
        <code>
          include-days 0 https://www.mydomain.com/archive/support/ 
        </code> </p> </li> 
      <li id="li_7663ABED40DD4E159F746E4F92BB6407"> 
      <code>
        include-date YYYY-MM-DD 
      </code> <p>搜索自动机可对与指定URL蒙版匹配且旧或早于YYYY-MM-DD日期的所有文档进行索引。 </p> <p>您可以使用以下一个或多个关键字跟随URL掩码： </p> <p> 
        <ul id="ul_57BF37A413BB4A4D962863DACE56F395"> 
        <li id="li_88CAB9AB583B4754A5C53478BD1108FF">nofollow </li> 
        <li id="li_999E1CD34FDE4A1B9C332B4AA8C2887D">noindex </li> 
        <li id="li_05646FACF3524D2A9E201A23770E357F"> server-date </li> 
        </ul> </p> <p>以下蒙版示例包括2011年7月25日或之前/archive/文件夹中的所有文档: </p> <p> 
        <code>
          include-date 2011-07-25 https://www.mydomain.com/archive/ 
        </code> </p> </li> 
      <li id="li_172692DEDA8744B3AA492701D24C2D80"> 
      <code>
        exclude-days NNN 
      </code> <p>禁用所有与指定的URL掩码匹配且NN天或更旧的文档的索引。 </p> <p>（可选）您可以按关键字遵循URL掩码 
        <code>
          server-date 
        </code>。 </p> <p>下面的蒙版示例从索引中排除所有90天或更旧的PDF文件： </p> <p> 
        <code>
          exclude-days 90 *.pdf 
        </code> </p> </li> 
      <li id="li_26078517744D4AECBE1351008926CBAE"> 
      <code>
        exclude-date YYYY-MM-DD 
      </code> <p>禁用与指定的URL掩码匹配且旧或早于日期YYYY-MM-DD的所有文档的索引。 </p> <p>（可选）您可以按关键字遵循URL掩码 
        <code>
          server-date 
        </code>。 </p> <p>以下蒙版示例不包括2004年4月23日或之前/archive/文件夹中的所有文档: </p> <p> 
        <code>
          exclude-date 2004-04-23 https://www.mydomain.com/archive/ 
        </code> </p> </li> 
      </ul> </p> <p>请参阅<a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_F4F1F58A646F4A86B8650EC46FDCEF66" type="concept" format="dita" scope="local">关于日期蒙版</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>删除URL </p> </td> 
      <td colname="col2"> <p>指定URL。 </p> <p>搜索自动机会查找并删除搜索索引中的指定文档。 如果指定的页面已在您的搜索索引中，则自动机会在添加或更新任何其他页面之前将其删除。 </p> <p>此字段必须仅包含文档URL，而不包含蒙版。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>查找和删除URL蒙版 </p> </td> 
      <td colname="col2"> <p>指定简单的URL蒙版 — 完整路径、部分路径或使用通配符或常规表达式的蒙版。 </p> <p>如果指定的URL掩码与搜索索引中的页面匹配，则搜索自动机会在添加或更新任何其他页面之前删除这些页面。 例如： </p> <p> 
      <code>
        https://www.mydomain.com/products/1998/household/* 
      </code> </p> <p>您还可以使用常规表达式，如下例所示： </p> <p> 
      <code>
        regexp ^https://www\.mydomain\.com/products/199[567]/.*$ 
      </code> </p> <p>请参阅<a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local">常规表达式</a>。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 设置实时网站{#task_2A46BA189ECC4317A9D5C6E99A336F33}的增量索引计划

您可以选择增量索引频率以及用于爬网和更新增量索引的基本时间。

您选择的时间是根据在“帐户设置”中配置的时区本地的。

请参阅[配置帐户设置](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

Web服务器通常安排在半夜停机进行维护。 如果服务器在计划的索引时间内关闭，则索引创建过程将失败。 请确保您选择了Web服务器可用的一天中的某个时间。

索引计划仅适用于实时索引；无法计划分阶段索引。

**为实时网站设置增量索引计划**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Live Schedule]**。
1. 在&#x200B;**[!UICONTROL Incremental Index Schedule]**&#x200B;页面的&#x200B;**[!UICONTROL Incrementally Index]**&#x200B;下拉列表中，选择以小时或分钟为单位的索引频率。
1. 在&#x200B;**[!UICONTROL Base Time]**&#x200B;下拉列表中，选择要重新生成新增量索引的开始时间。
1. 单击 **[!UICONTROL Save Changes]**.

## 运行实时或分阶段网站{#task_9BFB6157F3884B2FAECB7E0E9CA318CB}的增量索引

您可以使用增量索引为实时网站或分阶段网站（如频繁更改的页面集合）的“片段”编制索引。

**要运行实时或分阶段网站的增量索引，请执行以下操作**

1. 在“产品”菜单中，执行下列操作之一：

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Live Index]**.

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Staged Index]**.

1. 单击 **[!UICONTROL Incremental Index Now]**.
1. （可选）如果出现索引错误，请单击&#x200B;**[!UICONTROL View Errors]**&#x200B;以视图关联的日志。

## 查看实时或分阶段网站{#task_E668E1F1240C476DAA1CA783DC728232}的增量索引日志

当实时增量索引或分阶段增量索引完成时，您可以视图其关联日志以排除发生的任何错误。


您无法导出日志，也无法保存它们。 在新索引出现之前，日志仍可供查看。

**要视图实时网站或分阶段网站的增量索引日志，请执行以下操作**

1. 在“产品”菜单中，执行下列操作之一：

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Live Log]**.

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Staged Log]**.

1. 在日志页面顶部或底部，执行下列任一操作：

   * 使用导航选项&#x200B;**[!UICONTROL First]**、**[!UICONTROL Prev]**、**[!UICONTROL Next]**、**[!UICONTROL Last]**&#x200B;或&#x200B;**[!UICONTROL Go to line]**&#x200B;在日志中移动。

   * 使用显示选项&#x200B;**[!UICONTROL Errors only]**、**[!UICONTROL Wrap line]**&#x200B;或&#x200B;**[!UICONTROL Show]**&#x200B;细化您所看到的内容。

