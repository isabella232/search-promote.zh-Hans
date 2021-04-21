---
description: 使用脚本索引，您无需登录即可编写、更新和维护增量索引选项。 搜索自动机从您服务器上托管的文本文件中读取说明。
solution: Target
subtopic: Scripted Index
title: 关于脚本索引
topic-legacy: Index,Site search and merchandising
uuid: 51e726ad-414b-4cbd-8a68-fefc3cf9b565
exl-id: e1d14cd5-4885-4e3a-bc5f-fe0b6a4df15e
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '1725'
ht-degree: 1%

---

# 关于脚本索引{#about-scripted-index}

使用脚本索引，您无需登录即可编写、更新和维护增量索引选项。 搜索自动机从您服务器上托管的文本文件中读取说明。

## 使用脚本索引{#concept_34F58D551BC04BFB8ADC294B9DA9199D}

## 关于配置脚本增量索引{#section_161D254065E143F3A39F3FC09C400090}

要使用“脚本索引”，请使用“脚本增量索引配置”页指定位于您服务器上的脚本文件（纯文本文件）的URL。 例如，`https://www.mysite.com/indexlist.txt`。当您的站点发生更改时，您可以手动或自动向文本文件添加命令块（通过新闻源、股票报价机或其他更改文件中的信息到来触发脚本）。

当脚本的增量索引开始时，搜索自动机读取文本文件并运行在该文件中找到的新命令。 默认情况下，搜索自动机仅处理由文件日期确定的新命令。 除非在配置“脚本索引”时选中&#x200B;**[!UICONTROL Clear Date]**，否则搜索自动机将“记住”最近处理的块的日期说明符。

## 关于脚本文件{#section_B312E40539F44C6583B4F9637D428E19}

您在URL中指定的脚本文件是位于您服务器上的纯文本文件。 您可以对行尾序列使用回车符、换行符或两者。 空行包含零个或多个空格字符，后跟行尾序列。 所有命令均不区分大小写。

文本文件由块组织，块描述搜索机器人在执行脚本增量索引时使用的信息。

块按日期排序，最旧的块位于文本文件的顶部，最近的块位于底部。 每个块以单行date-command和date-specifier命令开始，并以空行分隔符结束，如以下块示例中所示（介于两个命令之间）：

使用HTTP 1.1样式时，低于10的所有序号日期都需要前导零。 例如，11月6日是11月06日，而不是11月6日。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Command（命令） </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>date-command </p> </td> 
   <td colname="col2"> <p>每个块开始的第一行包含两个日期命令之一： </p> <p> 
     <ul id="ul_9C1B229B7F1846C490B853FC34989E77"> 
      <li id="li_31FEF1A7163842BDBB0ABE779D07045A"> <span class="codeph"> 日期  </span> <p>使用“date”命令可指示日期说明符将由日期、日期、时间和时区组成。 </p> </li> 
      <li id="li_0918D5B090014C1A852CB80BB7C2867C"> <span class="codeph"> 秒数 </span> <p>使用<span class="codeph">秒</span>指示日期说明符将包含一个时间（以大纪元秒为单位）(例如，784111777)。 使用<span class="codeph">秒</span>时，请确保块之间的秒数增加。 </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>date-specifier </p> </td> 
   <td colname="col2"> <p><span class="codeph"> date-specifier </span>命令通常记录块信息添加到文件的顺序日期和时间（date命令）或时间(以纪元秒数（秒命令）表示。 例如： </p> <p> <code> date&nbsp;Sun,&nbsp;06&nbsp;Nov&nbsp;1994&nbsp;08:49:37&nbsp;GMT&nbsp;(HTTP&nbsp;1.1&nbsp;style) 
      date&nbsp;Sunday,&nbsp;06-Nov-94&nbsp;08:49:37&nbsp;GMT&nbsp;(HTTP&nbsp;1.0&nbsp;style) 
      date&nbsp;Sun&nbsp;Nov&nbsp;6&nbsp;08:49:37&nbsp;1994&nbsp;(Unix&nbsp;asctime()&nbsp;date&nbsp;style) 
      seconds&nbsp;784111777&nbsp;(Unix&nbsp;epoch-seconds&nbsp;style) </code> </p> <p>使用HTTP 1.1样式时，低于10的所有序号日期都需要前导零。 例如，11月6日是11月06日，而不是11月6日。 </p> <p>搜索自动机“记住”最近处理的块的日期说明符，并仅索引其认为“较新”的信息。 (实时对搜索机器人不重要。 相反，与其他先前处理的时间相比，时间才是关键。) </p> <p>例如，在搜索机器人读取日期说明符为晚上10:00的块后，它不读取任何在晚上10:00之前记录时间的块，而不管索引操作何时运行。 在最坏情况下，您可能会错误地在日期说明符中输入年份“2040”而不是“2004”。 在这种情况下，搜索机器人在下一个索引操作期间对2040块进行索引，然后拒绝读取任何其他信息块（除非有一个后日期2040）。 如果发生这种情况，请从文本文件中删除所有以前处理的块，单击<span class="uicontrol">清除日期</span>，然后将其实时推送。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>注释行 </p> </td> 
   <td colname="col2"> <p>以“#”字符开始注释行。 </p> <p>每个注释行必须是自己的行；不能键入行尾注释。 </p> <p>注释行不被视为空行。 它也可以显示在块中的任意位置，甚至在日期或秒命令之前，如以下示例所示： </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;#Added&nbsp;by&nbsp;Cathy&nbsp;Read&nbsp;after&nbsp;the&nbsp;Y2K&nbsp;seminar 
      &nbsp;&nbsp;&nbsp;&nbsp;date&nbsp;Mon,&nbsp;29&nbsp;Dec&nbsp;1999&nbsp;09:32:20&nbsp;GMT&nbsp; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>action-command </p> </td> 
   <td colname="col2"> <p>每个文本块可以包含任意所需数量的操作命令。 以下操作命令选项与标准增量索引的选项相对应： </p> <p> 
     <ul id="ul_8E1435350A0F416BB8F7826CD3886E74"> 
      <li id="li_22181666628C48A28A6A0BA1F7CA8E77"> 
       <code>
         add 
       </code> <p>与URL一起使用。 搜索自动机仅对自上次索引操作以来更改的指定URL进行索引。 此外，搜索自动机会遵循包含在指定文档中的链接，并仅对已更改的文档进行索引。 </p> <p>您可以在URL后 
        <code>
          nofollow 
        </code>或 
        <code>
          noindex 
        </code>关键字，如下例所示： </p> <p> <code> add&amp;nbsp;https://www.mydomain.com/&amp;nbsp;noindex </code> </p> </li> 
      <li id="li_8E47BF07DB24417083883F5BF40D6B9E"> 
       <code>
         update 
       </code> <p>与URL掩码一起使用。 搜索自动机会查找并更新与指定URL蒙版匹配的所有文档。 </p> <p>您可以在URL后 
        <code>
          nofollow 
        </code>或 
        <code>
          noindex 
        </code>关键字，如下例所示： </p> <p> <code> update&amp;nbsp;https://www.mydomain.com/products/ </code> </p> </li> 
      <li id="li_B3EC8B1670D54F66A1D8411A694EF7E4"> 
       <code>
         include 
       </code> 或 
       <code>
         exclude 
       </code> <p>与URL掩码一起使用。 搜索自动机根据指定的蒙版类型查找和索引("include")或忽略("exclude")文档。 </p> <p>例如： </p> <p> <code> include&amp;nbsp;https://www.mydomain.com/products/household/lightbulbs*.html </code> </p> <p>或 </p> <p> <code> exclude&amp;nbsp;https://www.mydomain.com/archive/ </code> </p> </li> 
      <li id="li_050B54B735F0475E93806455FA6DC6A5"> 
       <code>
         include-date 
       </code> 或 
       <code>
         exclude-date 
       </code> <p>与URL掩码一起使用。 搜索自动机根据URL和文档日期查找和索引(“include”)或忽略(“exclude”)文档。 有以下类型的蒙版可用： </p> <p> 
        <ul id="ul_23A15CB492214B86BE84D8E6EA1820AE"> 
         <li id="li_0C7051AC3B5A4C57A3E477F7B6246611"> 
          <code>
            include-days NNN 
          </code> <p>搜索自动机将所有与指定的URL蒙版匹配且NNN天或更旧的文档编入索引。 </p> <p>您可以使用关键字跟随URL掩码 
           <code>
             nofollow 
           </code>, 
           <code>
             noindex 
           </code>和/或 
           <code>
             server-date 
           </code>。 </p> </li> 
         <li id="li_983A10E2ED5D434EA9031F32143F4EF4"> 
          <code>
            include-date YYYY-MM-DD 
          </code> <p> 搜索自动机对与指定的URL掩码匹配且旧或早于日期YYYY-MM-DD的所有文档进行索引，其中“YYYY”是4位年份，“MM”是1位或2位月份(1-12)，“DD”是1位或2位日(1-31)。 </p> <p>您可以使用关键字跟随URL掩码 
           <code>
             nofollow 
           </code>, 
           <code>
             noindex 
           </code>和/或 
           <code>
             server-date 
           </code>。 </p> </li> 
         <li id="li_733CE1B748024CECA7FBE00D7BC7B88A"> 
          <code>
            exclude-days NNN 
          </code> <p> 禁用与指定的URL掩码匹配且NN天或更旧的所有文档的索引。 </p> <p>您可以在URL掩码后使用关键字 
           <code>
             server-date 
           </code>。 </p> </li> 
         <li id="li_90056A0B96CC4DA3854711860A15CE89"> 
          <code>
            exclude-date YYYY-MM-DD 
          </code> <p>禁用与指定的URL掩码匹配且旧或旧于日期YYYY-MM-DD的所有文档的索引。 </p> <p>您可以在URL掩码后使用关键字 
           <code>
             server-date 
           </code>。 </p> </li> 
        </ul> </p> </li> 
      <li id="li_AA78F22B60FE4535BE73BA87A8992C08"> 
       <code>
         delete 
       </code> <p>指定URL。 搜索自动机会从URL标识的索引中删除文档。 </p> </li> 
      <li id="li_9C63061568AA4D57A4FEBCF6DB9194EC"> 
       <code>
         deletemask 
       </code> <p>搜索自动机将从与指定URL蒙版匹配的索引中删除文档。 </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

另请参阅[关于URL蒙版](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164)。

## 脚本文件示例{#section_9F580F20E7214751B157A28B392BD64E}

在下面的脚本文件示例中，如果日期说明符在日期之后是最近处理的块的日期说明符，则搜索自动机处理这些块。 如果是，则执行以下索引操作：

* 从索引中删除`y2k-problems.html`。
* 将`no-y2k-problems.html`添加到搜索索引中，并且不跟踪`no-y2k-problems.html`的任何链接。

* 搜索时，从搜索索引中排除与`housewares.htm`和`lightfixtures.htm`l匹配的URL。

* 在`www.mydomain.com`下包含所有其他目录和文档。
* 更新`products`和`information`目录中的所有文档，搜索并索引自上次索引操作以来更改的所有子链接。

* 搜索时，如果URL的日期在1999年1月1日或之前，请排除网站`archive`部分的URL。
* 从搜索索引中排除与`housewares.html`和`lightfixtures.html`匹配的URL。

* 在`help`目录中为文件编制索引，但不要从这些文件爬网或索引任何链接。
* 爬网并索引为`www.mydomain.com`遇到的任何其他文件。

```
# Start of file. 
# Added by John Smith 
date Sat, 01 Jan 2004 16:05:53 PST 
exclude https://www.mydomain.com/housewares.html 
exclude https://www.mydomain.com/lightfixtures.html 
include https://www.mydomain.com/ 
delete https://www.mydomain.com/y2k-problems.html 
add https://www.mydomain.com/no-y2k-problems.html nofollow 
 
date Sun, 02 Jan 2004 20:19:08 PST 
# Added by the wire service updater 
exclude-date 1999-01-01 https://www.mydomain.com/archive server-date 
exclude https://www.mydomain.com/housewares.html 
exclude https://www.mydomain.com/lightfixtures.html 
include https://www.mydomain.com/help/ nofollow 
include https://www.mydomain.com/ 
# no add files, just update existing files 
# update all files in the "products" directory 
update https://www.mydomain.com/products/ 
# update all files in the "information" directory 
update regexp ^https://www\.mydomain\.com/information/.*$ 
# End of file.
```

## 配置脚本增量索引{#task_05AE040FE75E40FFAA5E10B6B6D4D255}

您可以指定已创建的脚本，该脚本可以写入、更新和维护增量索引，而无需登录。 搜索自动机从您服务器上托管的文本文件中读取指令以执行增量索引。

**配置脚本的增量索引**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Configuration]**。
1. 在&#x200B;**[!UICONTROL Scripted Incremental Index Configuration]**&#x200B;页面的&#x200B;**[!UICONTROL Script File URL]**&#x200B;中，输入位于您服务器上的文本文件脚本的URL。

   请参阅[关于脚本索引](../c-about-index-menu/c-about-scripted-index.md#concept_34F58D551BC04BFB8ADC294B9DA9199D)。
1. （可选）如果不希望搜索自动机“记住”最近处理的块的日期说明符，请检查&#x200B;**[!UICONTROL Clear Date]**。

   默认情况下，搜索自动机只处理文本文件中找到的新命令块（由文件的日期确定）。 如果不需要默认值，请选中&#x200B;**[!UICONTROL Clear Date]**。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 为实时网站{#task_B3A87AC4AC784507859C23B9062BA11C}设置脚本的增量索引计划

您可以计划脚本式增量索引，以在一天中定期进行。

您选择的基本时间是根据在“帐户设置”中配置的时区本地的。

请参阅[配置帐户设置](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

Web服务器通常安排在半夜停机进行维护。 如果服务器在计划的索引时间内关闭，则索引创建过程将失败。 请确保您选择了Web服务器可用的一天中的某个时间。

索引计划仅适用于实时索引；无法计划已暂存的增量索引。

**为实时网站设置脚本的增量索引计划**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Live Schedule]**。
1. 在&#x200B;**[!UICONTROL Scripted Incremental Index Schedule]**&#x200B;页面的&#x200B;**[!UICONTROL Read the Scripted Incrementally Indexing File]**&#x200B;下拉列表中，选择希望脚本增量索引文本文件运行的频率（以小时或分钟为单位）。
1. 在&#x200B;**[!UICONTROL Base Time]**&#x200B;下拉列表中，选择要重新生成新脚本增量索引的开始时间。
1. 单击 **[!UICONTROL Save Changes]**.

## 运行实时或分阶段网站{#task_6E6FC76EE1E84A5FADB3B67AD7B1DACB}的脚本增量索引

您可以使用脚本增量索引为实时或分阶段网站（如频繁更改的页面集合）的“片段”编制索引，而无需登录。

要使用此功能，请确保已配置脚本的增量索引文本文件。

请参阅[配置脚本的增量索引](../c-about-index-menu/c-about-scripted-index.md#task_05AE040FE75E40FFAA5E10B6B6D4D255)。

**运行实时网站或分阶段网站的脚本增量索引**

1. 在“产品”菜单中，执行下列操作之一：

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Live Index]**.
   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Staged Index]**.

1. 单击 **[!UICONTROL Scripted Index Now]**.
1. （可选）如果出现索引错误，请单击&#x200B;**[!UICONTROL View Errors]**&#x200B;以视图关联的日志。

## 查看实时或分阶段网站{#task_CBFCE9B9A87B4DF7A2A35A6E83DE93D7}的脚本增量索引日志

当实时完整脚本索引或分阶段完整脚本索引完成时，您可以视图其关联日志以排除发生的任何错误。

您无法导出日志，也无法保存它们。 但是，在新索引出现之前，日志仍可供查看。

**要视图实时网站或分阶段网站的增量索引日志，请执行以下操作**

1. 在“产品”菜单中，执行下列操作之一：

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Live Log]**.

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Staged Log]**.

1. 在日志页面顶部或底部，执行下列任一操作：

   * 使用导航选项&#x200B;**[!UICONTROL First]**、**[!UICONTROL Prev]**、**[!UICONTROL Next]**、**[!UICONTROL Last]**&#x200B;或&#x200B;**[!UICONTROL Go to line]**&#x200B;在日志中移动。

   * 使用显示选项&#x200B;**[!UICONTROL Errors only]**、**[!UICONTROL Wrap line]**&#x200B;或&#x200B;**[!UICONTROL Show]**&#x200B;细化您所看到的内容。
