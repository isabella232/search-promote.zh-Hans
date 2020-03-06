---
description: 您可以使用增量索引为实时网站或分阶段网站的“片段”（如频繁更改的页面的集合）编制索引。
seo-description: 您可以使用增量索引为实时网站或分阶段网站的“片段”（如频繁更改的页面的集合）编制索引。
seo-title: 关于增量索引
solution: Target
subtopic: Incremental Index
title: 关于增量索引
topic: Index,Site search and merchandising
uuid: b1ee9b08-dcbe-4ffe-b0b4-d379daaac9b5
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a

---


# 关于增量索引{#about-incremental-index}

您可以使用增量索引为实时网站或分阶段网站的“片段”（如频繁更改的页面的集合）编制索引。

## 使用增量索引 {#concept_A7770F0552D14C47B3DDB65DB78FFFEE}

增量索引只需几秒即可执行，对于需要数小时才能完全索引的大容量网站非常有用。

生成增量索引时，会显示状态信息，如开始时间、已用时间和索引过程中的错误。 还会显示有关上一个索引状态的信息。

您可以随时停止或重新启动增量索引创建过程。

当新增索引为实时网站构建时，客户可以使用您的上次增量索引继续搜索您的网站。

## 配置分阶段网站的增量索引 {#task_46A367B0786C4C90BFFA5D3F95FD86C0}

您可以通过指定网站URL和URL蒙版来配置要包含在增量索引中的网站页面。

**配置分阶段网站的增量索引**

1. 在产品菜单中，单击 **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Configuration]**。
1. 在页 **[!UICONTROL Incremental Index Configuration]** 面上，使用各种字段指定要索引的页面。

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
      <td colname="col2"> <p>指定URL。 </p> <p>搜索自动机仅对自您上次编制索引以来已更改的指定文档进行索引。 </p> <p>此外，搜索机器人会遵循包含在指定文档中的链接，并仅对那些已更改的文档进行索引。 </p> <p>此字段必须仅包含文档URL，而不能包含蒙版，如下例所示： </p> <p> 
        <userinput>
          https://www.mydomain.com/products/new.html 
        </userinput> </p> <p>您可以将以下关键字与URL一起使用： </p> <p> 
        <ul id="ul_62D1082ACBD547D092B10D72C56A3A1E"> 
          <li id="li_32C2B21DE75C4459908384CC44822F7D"> 
          <userinput>
            noindex 
          </userinput> <p>如果不想为页面上与指定URL匹配的文本编制索引，但想要跟踪页面链接，请添加 
            <userinput>
              noindex 
            </userinput> 在URL之后，如下例所示： </p> <p> 
            <userinput>
              https://www.mydomain.com/products/new.html索引 
            </userinput> </p> <p>请务必将 
            <userinput>
              noindex 
            </userinput> 从含空格的URL;逗号不是有效的分隔符。 </p> </li> 
          <li id="li_33AB62B669084BF7B976F4308715E435"> 
          <userinput>
            nofollow 
          </userinput> <p>如果要为页面上与指定URL匹配的文本编制索引，但不想跟随页面链接，请添加 
            <userinput>
              nofollow 
            </userinput> 在URL之后，如下例所示： </p> <p> 
            <userinput>
              https://www.mydomain.com/products/new.html了解详情 
            </userinput> </p> <p> 请务必将 
            <userinput>
              nofollow 
            </userinput> 从含空格的URL;逗号不是有效的分隔符。 </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>查找和更新URL蒙版 </p> </td> 
      <td colname="col2"> <p>指定简单的URL蒙版——完整路径、部分路径或使用通配符或正则表达式的路径。 </p> <p>搜索自动机仅查找自您上次编制索引以来已更改的所有匹配文档和索引。 </p> <p>此外，搜索自动机遵循包含在匹配文档中的链接，并仅对那些已更改的页面进行索引。 例如： </p> <p> 
      <userinput>
        https://www.mydomain.com/products/household/*.html 
      </userinput> </p> <p>您还可以使用正则表达式，如以下示例所示： </p> <p> 
      <userinput>
        regexp^https://www\.mydomain\.com/products/houseld/.*\.html$ 
      </userinput> </p> <p>请参阅 <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> 正则表达式</a>。 </p> <p>您还可以使用关键字 
      <userinput>
        nofollow 
      </userinput> 和 
      <userinput>
        noindex 
      </userinput> 如以上“添 <span class="uicontrol"> 加或更新URL”中 </span> 所述。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>包括和排除URL蒙版 </p> </td> 
      <td colname="col2"> <p>指定简单的包含或排除URL蒙版——完整路径、部分路径或使用通配符或正则表达式的路径。 </p> <p>搜索自动机根据指定的蒙版类型查找和索引(“include”)文档或忽略(“exclude”)文档。 </p> <p> 在为站点编制索引时，将按照外观的顺序按方向进行操作。 例如，以下蒙版列表： </p> <p> 
      <userinput>
        包括https://www.mydomain.com/products/household/lightbulbs*.html 
      </userinput> </p> <p> 
      <userinput>
        排除https://www.mydomain.com/products/ 
      </userinput> </p> <p>索引页面 
      <userinput>
        lightbegles1.html 
      </userinput> 和 
      <userinput>
        lightbegles2.html 
      </userinput>。但是，它不会为products目录下列出的任何其他页面编制索引。 </p> <p>首先显示的URL蒙版始终优先于稍后在列表中显示的URL蒙版。 此外，如果搜索机器人遇到与包含蒙版和排除蒙版两者匹配的文档，则首先列出的蒙版优先。 </p> <p>您还可以使用关键字 
      <userinput>
        nofollow 
      </userinput> 和 
      <userinput>
        noindex 
      </userinput> 如以上“添 <span class="uicontrol"> 加或更新URL”中 </span> 所述。 </p> <p>请参阅 <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164" type="concept" format="dita" scope="local"> 关于URL蒙版</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>包括和排除日期蒙版 </p> </td> 
      <td colname="col2"> <p>指定简单的包含或排除日期蒙版——完整路径、部分路径或使用通配符或正则表达式的路径。 </p> <p>搜索自动机根据URL和文档的日期查找和索引(“include”)文档或忽略(“exclude”)文档。 </p> <p>您可以使用以下类型的日期蒙版： </p> <p> 
      <ul id="ul_8958ED54C8EF405AA259236595ED3ABA"> 
      <li id="li_0A7841767E004F088CA6FA42E99B9F32"> 
      <userinput>
        include-days NNN 
      </userinput> <p>搜索自动机为与指定的URL蒙版匹配且版本为NNN（天数）或更久的所有文档建立索引。 </p> <p>您可以使用以下一个或多个关键字在URL蒙版后跟踪： 
        <ul id="ul_22A38D5F38B344ABB02B16EB1865813B"> 
        <li id="li_B89CC37DC2A1428185E86FFCB9DDB193">nofollow </li> 
        <li id="li_C2579B3A338D4AF987C3F518806734B0">noindex </li> 
        <li id="li_0527BF7103F34B83AC3E684069B899F7">server-date </li> 
        </ul> </p> <p>例如，以下蒙版包括/archive/support文件夹中0天或更早的所有文档： </p> <p> 
        <userinput>
          include-days 0 https://www.mydomain.com/archive/support/ 
        </userinput> </p> </li> 
      <li id="li_7663ABED40DD4E159F746E4F92BB6407"> 
      <userinput>
        include-date YYYY-MM-DD 
      </userinput> <p>搜索自动机为与指定URL蒙版匹配且旧或旧于YYYY-MM-DD日期的所有文档编制索引。 </p> <p>您可以使用以下一个或多个关键字在URL蒙版后跟踪： </p> <p> 
        <ul id="ul_57BF37A413BB4A4D962863DACE56F395"> 
        <li id="li_88CAB9AB583B4754A5C53478BD1108FF">nofollow </li> 
        <li id="li_999E1CD34FDE4A1B9C332B4AA8C2887D">noindex </li> 
        <li id="li_05646FACF3524D2A9E201A23770E357F"> server-date </li> 
        </ul> </p> <p>以下蒙版示例包括/archive/文件夹中日期为2011年7月25日或之前的所有文档： </p> <p> 
        <userinput>
          include-date 2011-07-25 https://www.mydomain.com/archive/ 
        </userinput> </p> </li> 
      <li id="li_172692DEDA8744B3AA492701D24C2D80"> 
      <userinput>
        exclude-days NNN 
      </userinput> <p>禁用所有与指定的URL蒙版匹配且版本为NNN天或更早的文档的索引。 </p> <p>或者，您也可以选择按关键字使用URL蒙版 
        <userinput>
          server-date 
        </userinput>. </p> <p>以下蒙版示例从索引中排除所有90天或更早的PDF文件： </p> <p> 
        <userinput>
          exclude-days 90 *.pdf 
        </userinput> </p> </li> 
      <li id="li_26078517744D4AECBE1351008926CBAE"> 
      <userinput>
        exclude-date YYYY-MM-DD 
      </userinput> <p>禁用所有与指定的URL蒙版匹配且旧或早于日期YYYY-MM-DD的文档的索引。 </p> <p>或者，您也可以选择按关键字使用URL蒙版 
        <userinput>
          server-date 
        </userinput>. </p> <p>以下蒙版示例不包括2004年4月23日或之前/archive/文件夹中的所有文档： </p> <p> 
        <userinput>
          exclude-date 2004-04-23 https://www.mydomain.com/archive/ 
        </userinput> </p> </li> 
      </ul> </p> <p>请参阅 <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_F4F1F58A646F4A86B8650EC46FDCEF66" type="concept" format="dita" scope="local"> 关于日期蒙版</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>删除URL </p> </td> 
      <td colname="col2"> <p>指定URL。 </p> <p>搜索自动机会从搜索索引中查找并删除指定的文档。 如果指定的页面已在您的搜索索引中，则自动机会在添加或更新任何其他页面之前将其删除。 </p> <p>此字段只能包含文档URL，而不能包含蒙版。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>查找和删除URL蒙版 </p> </td> 
      <td colname="col2"> <p>指定简单的URL蒙版——完整路径、部分路径或使用通配符或正则表达式的URL蒙版。 </p> <p>如果指定的URL蒙版与搜索索引中的页面匹配，则搜索自动机会在添加或更新任何其他页面之前删除这些页面。 例如： </p> <p> 
      <userinput>
        https://www.mydomain.com/products/1998/household/* 
      </userinput> </p> <p>您还可以使用正则表达式，如以下示例所示： </p> <p> 
      <userinput>
        regexp^https://www\.mydomain\.com/products/199[567]/。*$ 
      </userinput> </p> <p>请参阅 <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> 正则表达式</a>。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 为实时网站设置增量索引计划 {#task_2A46BA189ECC4317A9D5C6E99A336F33}

您可以选择增量索引频率和用于抓取和更新增量索引的基本时间。

您选择的时间是根据帐户设置中配置的时区所在的本地时间。

请参 [阅配置帐户设置](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

Web服务器通常安排在半夜停工进行维护。 如果服务器在计划的索引时间内关闭，则索引构建过程将失败。 请确保选择一天中Web服务器可用的时间。

索引计划仅适用于您的实时索引；无法计划分阶段的索引。

**为实时网站设置增量索引计划**

1. 在产品菜单中，单击 **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Live Schedule]**。
1. 在页面中 **[!UICONTROL Incremental Index Schedule]** 的下拉列 **[!UICONTROL Incrementally Index]** 表中，选择索引频率（以小时或分钟为单位）。
1. 在下 **[!UICONTROL Base Time]** 拉列表中，选择要重新生成新增量索引的开始时间。
1. 单击 **[!UICONTROL Save Changes]**.

## 运行实时或分阶段网站的增量索引 {#task_9BFB6157F3884B2FAECB7E0E9CA318CB}

您可以使用增量索引为实时网站或分阶段网站的“片段”（如频繁更改的页面的集合）编制索引。

**运行实时网站或分阶段网站的增量索引**

1. 在产品菜单中，执行下列操作之一：

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Live Index]**.

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Staged Index]**.

1. 单击 **[!UICONTROL Incremental Index Now]**.
1. （可选）如果出现索引错误，请单 **[!UICONTROL View Errors]** 击以查看关联的日志。

## 查看实时网站或分阶段网站的增量索引日志 {#task_E668E1F1240C476DAA1CA783DC728232}

当实时增量索引或分阶段增量索引完成时，您可以查看其关联日志以排除发生的任何错误。


您无法导出日志，也无法保存它们。 新索引出现之前，日志一直可供查看。

**查看实时网站或分阶段网站的增量索引日志**

1. 在产品菜单中，执行下列操作之一：

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Live Log]**.

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Staged Log]**.

1. 在日志页面顶部或底部，执行下列任一操作：

   * 使用导航选 **[!UICONTROL First]**&#x200B;项、 **[!UICONTROL Prev]**、 **[!UICONTROL Next]**、 **[!UICONTROL Last]**&#x200B;或 **[!UICONTROL Go to line]** 在日志中移动。

   * 使用显示选 **[!UICONTROL Errors only]**&#x200B;项 **[!UICONTROL Wrap line]**&#x200B;或 **[!UICONTROL Show]** 优化您看到的内容。
