---
description: 使用“重写规则”菜单设置爬网和搜索URL和标题规则。
solution: Target
subtopic: Rewrite Rules
title: 关于“重写规则”菜单
topic-legacy: Settings,Site search and merchandising
uuid: 77ee84dd-fdba-4d34-ae8e-2fe786599800
exl-id: cff17ead-6997-4ff6-a995-7ca020b06d50
translation-type: tm+mt
source-git-commit: aa095add9eb656913792b3f14001dda66cdd7d67
workflow-type: tm+mt
source-wordcount: '10178'
ht-degree: 0%

---

# 关于“重写规则”菜单{#about-the-rewrite-rules-menu}

使用“重写规则”菜单设置爬网和搜索URL和标题规则。

## 关于爬网列表存储URL规则{#concept_B71CF4C8030A4A74A22C3BFE4DE3B865}

“爬网URL规则”指定如何重写它在Web内容中遇到的URL。 您可以指定不限数量的规则和条件，并可以处理所遇到的URL的任何部分。

<!-- 

c_about_crawl_list_store_url_rules.xml

 -->

爬网规则对于重写URL的动态部分（如会话标识符）最有用，该标识符对于访问您网站的每个客户都是唯一的。 您还可以使用重写规则来隐藏搜索自动机中的URL部分(如查询参数)。 默认情况下，不指定任何规则，也不执行URL重写。

当网站被爬网时，嵌入的内容URL存储在要爬网的其他网页的临时列表中。 在将URL添加到此列表之前，将应用商店重写规则。 通常，存储重写规则用于从URL中删除会话ID或强制执行特定会话ID以进行搜索。 当搜索自动机从列表检索URL时，检索重写规则用于再次操作该URL的部分。 通常，检索规则用于将时间敏感数据插入URL中。 实际从您的网站中检索页面的是最终的URL。

请参阅[关于爬网列表检索URL规则](../c-about-settings-menu/c-about-rewrite-rules-menu.md#concept_EC8E2E48B99A458D8567B526C9827CBA)。

通常，您只使用“商店URL规则”。 仅当URL包含动态数据（如会话ID）且动态数据随时间变化而保持有效时，才需要检索URL规则。 在这种情况下，您使用“存储URL规则”从遇到的URL获取数据的最新状态。 然后，当搜索自动机尝试检索页面时，您可以使用“检索URL规则”将该数据添加到每个URL。

每个规则都用重写规则(RewriteRule)指令和一个或多个可选重写条件(RewriteCond)指定。 规则的顺序很重要。 规则集按规则循环。 当规则匹配时，它循环访问任何相应的重写条件。 按以下方式指定爬网URL规则：

```
RewriteCond TestString CondPattern [Flags] 
RewriteRule Pattern Substitution [Flags]
```

遇到嵌入的URL时，搜索自动机会尝试将URL与每个爬网规则的模式匹配。 如果模式匹配，重写引擎将查找相应的RewriteCond指令。 如果不存在任何条件，则URL将替换为从替代字符串构建的新值，并继续使用规则集中的下一个规则。 如果存在条件，则按其列出顺序处理它们。 重写引擎尝试将条件模式(CondPattern)与测试字符串(TestString)匹配。 如果两者匹配，则处理下一个条件，直到不再有可用的条件。 如果所有条件都匹配，则URL将替换为规则中指定的替代。 如果条件不满足，则完整的条件集和相应的规则将失败。

## 关于RewriteRule指令{#section_162122340BB34F12BB9A36DC9349092B}

RewriteRule指令具有以下形式：

```
           
<i>RewriteRule Pattern Substitution [Flags]</i> 
        
```

`Pattern` 可以是应用于当前URL的POSIX常规表达式。“当前URL”可能与原始请求的URL不同，因为之前的规则可能已经匹配和更改了URL。

请参阅[常规表达式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

不能使用“not”字符(“！”) 以在模式前添加前缀。 “not”字符允许您取消模式，即仅当当前URL与此模式不匹配时才为true。 当更好匹配负模式时，或者作为最终的默认规则时，可以使用“not”字符。

>[!NOTE]
>
>不能在模式中同时使用&quot;not&quot;字符和分组通配符。 此外，当替换字符串包含$N时，您不能使用否定的模式。

可以使用括号在图案中创建背参照，该背参照可以由“替代”(Substitution)和“CondPattern”(CondPattern)引用。

**替** 换URL由包含以下内容的替换字符串替换：

纯文本：未更改传递的文本。

“反向引用”提供对“图案”或“第二图案”的编组部分（内括号）的访问。 以下是两种类型的反向引用：

* **RewriteRule** Backreferences这些匹配RewriteRule模式中的反向引用，其格式为$N(0)  &lt;>例如，`RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2.`

* **RewriteCond Backreferences这** 些匹配的RewriteCond CondPattern中的反向引用，形式为%N(0)  &lt;>

变量：这些是%{NAME_OF_VARIABLE}形式的变量，其中NAME_OF_VARIABLE是定义变量名称的字符串。 有关设置环境变量的详细信息，请参阅`*[E]*`标志。

函数：这些函数的形式为${NAME_OF_FUNCTION:key} ，其中NAME_OF_FUNCTION如下所示：

* tolower使&#x200B;*key*&#x200B;中的所有字符都小写。
* toupper使&#x200B;*key*&#x200B;中的所有字符都为大写。
* 转义URL — 编码&#x200B;*key*&#x200B;中的所有字符。
* 字符“a”……z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;“9”、“*”、“ — ”、“。”、“/”、“@”和“_”保持不变；空格将转换为“+”，所有其他字符将转换为其%xx URL编码的等效字符。
* unescape将“+”转换回空格，所有%xx URL编码的字符都转换回单个字符。

>[!NOTE]
>
>有一个特殊的替换字符串：`'-'`表示“NO替换”。 `'-'`字符串通常与C（链）标志一起使用，这样您就可以在发生替换之前将URL与多个模式匹配。

**标志**

（可选）将标记括在括号`[]`中。 多个标志以逗号分隔。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>标志 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>最后一条规则。 </p> <p>停止重写过程，并且不应用任何附加的重写规则。 使用此标志可阻止对当前URL进行任何进一步处理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>下一轮。 </p> <p> 使用来自上次重写规则（而非原始URL）的URL重新运行重写过程（从第一个重写规则开始）。 小心不要造成死循环！ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>用下一条规则链接。 </p> <p>将当前规则链接到下一个规则（也可以将其链接到下一个规则，依此类推）。 如果规则匹配，则替代过程将照常继续。 如果规则不匹配，则跳过所有后续的链式规则。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>没有。 </p> <p> 使图案不区分大小写（即，当图案与当前URL匹配时，“A-Z”和“a-z”之间没有差异）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>跳过下一个规则。 </p> <p> 如果当前规则匹配，则此标志将强制重写引擎跳过规则集中的下一个num规则。 使用此标志可生成伪if-then-else构造。 then-clause的最后一个规则变为skip=N ，其中N是else-clause中的规则数。 </p> <p> <p>注意： 此标志与“chain|C”标志不同！) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>设置环境变量。 </p> <p>创建设置为值VAL的环境变量"VAR"，其中VAL可以包含扩展的常规表达式反向引用$N和%N。 您可以多次使用此标志设置多个变量。 以后可以通过%{VAR}在以下RewriteCond模式中取消引用变量。 </p> <p>使用此标志可删除和记住URL中的信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>存储重写规则和检索重写规则共享变量值。 由于这种行为，当遇到并存储嵌入的URL时，您可以将变量设置为时间敏感的sessionid值。 当从临时存储列表检索下一个URL时，可以在检索该页面之前将最新的sessionid值添加到该URL。

**具有函数的RewriteRule的示例**

假设您有一个区分大小写的服务器，它以不同方式处理字符串`"www.mydomain.com"`和`"www.MyDomain.com"`。 为了使服务器正常工作，请确保域始终`"www.mydomain.com"`，即使某些文档包含引用`"www.MyDomain.com."`的链接。要执行此操作，您可以使用以下规则：

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2
```

此重写规则使用函数`tolower`重写URL的域部分，以确保它始终为小写，如下所示：

1. 模式`(^https://([^/]*)(.*)$)`包含一个反向引用`([^/]*)`，它匹配URL中`https://`和第一个`/`之间的所有字符。 该模式还包含第二个反向引用`(.*)`，该反向引用与URL中所有剩余字符相匹配。

1. 替代`(https://${tolower:$1}$2)`指示搜索引擎使用第一个反向引用`(https:// ${tolower:$1}$2)`上的`tolower`函数重写URL，而URL的其余部分保持不变`(https://${tolower:$1} $2)`。

因此，表单`https://www.MyDomain.com/INTRO/index.Html`的URL被重写为`https://www.mydomain.com/INTRO/index.Html`。

## 关于RewriteCond指令{#section_CD5A19B2D3204F73B645411931FC34A1}

RewriteCond指令定义规则条件。 当RewriteCond在RewriteRule之前时，只有当规则的模式与当前标题匹配且附加条件适用时，才使用该规则。 重写条件采用以下形式：

```
           
<i>RewriteCond TestString CondPattern [Flags]</i> 
        
```

`TestString` 是一个字符串，可以包含以下构造：

纯文本：未更改传递的文本。

“反向引用”提供对“图案”或“第二图案”的编组部分（内括号）的访问。 以下是两种类型的反向引用：

* **RewriteRule** Backreferences这些匹配RewriteRule模式中的反向引用，其格式为$N(0)  &lt;>例如，`RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2`。

* **RewriteCond Backreferences这** 些匹配的RewriteCond CondPattern中的反向引用，形式为%N(0)&lt;>

变量：这些是%{NAME_OF_VARIABLE}形式的变量，其中NAME_OF_VARIABLE可以是定义变量名称的字符串。 有关设置变量的详细信息，请参阅RewriteRule *`[E]`*&#x200B;标志。

函数：这些函数的形式为${NAME_OF_FUNCTION:key} ，其中NAME_OF_FUNCTION如下所示：

* tolower使&#x200B;*key*&#x200B;中的所有字符都小写。
* toupper使&#x200B;*key*&#x200B;中的所有字符都为大写。
* 转义URL对键中的所有字符进行编码。 字符“a”……z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;“9”、“*”、“ — ”、“。”、“/”、“@”和“_”保持不变，空格将转换为“+”，所有其他字符将转换为其`%xx` URL编码的等效字符。
* unescape将“+”转换回空格，所有`%xx` URL编码字符都重新编码为单个字符。

**CondPattern是** 带有一些附加内容的标准扩展常规表达式。模式字符串可以前缀为`!`字符（感叹号），以指定非匹配模式。 您可以使用下列特殊变体之一，而不是实际的常规表达式字符串：

>[!NOTE]
>
>您还可以在所有这些测试前加感叹号(&#39;!&#39;) 否定他们的意义。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern字符串 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> “&lt;CondPattern” </p> </td> 
   <td colname="col2"> <p>词法上更少。 </p> <p> 将CondPattern视为纯字符串，并以词法方式将其与TestString进行比较。 如果TestString词法上小于CondPattern，则为true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>词法上更大。 </p> <p> 将CondPattern视为纯字符串，并以词法方式将其与TestString进行比较。 如果TestString词性大于CondPattern，则为true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>词法上相等。 </p> <p> 将CondPattern视为纯字符串，并以词法方式将其与TestString进行比较。 如果TestString在词法上等于CondPattern，则为true，即两个字符串完全相等（逐个字符）。 如果CondPattern仅为""（两个引号），则会将TestString与空字符串进行比较。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**标记**
（可选）将标记括在括号中 `[]`。多个标志以逗号分隔。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>标志 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> 没有。 </p> <p>此标志使测试不区分大小写，即，扩展的TestString和CondPattern中的“A-Z”和“a-z”之间没有差异。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p>或者下一个条件。 </p> <p>使用此标志将规则条件与本地OR而不是隐式AND组合。 如果没有此标志，您必须多次写入第二个/规则。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**示例**

某些网页在访客第一次到达站点时分配“sessionid” CGI变量。 此变量用于标识访客，当访客浏览站点时，变量会随之传递。 由于搜索自动机看起来像是站点的访客，因此会为它分配一个“sessionid”编号。 搜索自动机会保留此单个“sessionid”值，即使第二个站点页面尝试指定新值也是如此。 为了确保这一点，您需要两个重写规则。

第一条规则用于标识和存储会话id变量：

```
RewriteCond  %{sessionid}  !.+ 
RewriteRule  ^.+sessionid= 
<b>([^&#]+)</b>.*$  -   
<i>[E=sessionid:$1]</i>
```

RewriteRule使用E标志`([E=sessionid:$1])`将会话CGI参数的当前值指定给变量`sessionid`。 `$1`引用第一个反向引用，它包含在RewriteRule的Pattern `([^&#]+)`中的第一组括号之间。

常规表达式`^&#]+`匹配单词`sessionid`和下一个`**&**or**#**`字符之间的URL部分。 由于此RewriteRule仅用于为sessionid变量创建初始值，因此不会重写。 请注意，规则的“替代”字段设置为`-`以指示不需要重写。

RewriteCond检查变量`sessionid`(`%{sessionid}`)。 如果它连一个字符(!.+)，则匹配RewriteRule。

使用此规则，URL将读作`https://www.domain.com/home/?sessionid=1234&function=start`，并将值`1234`赋给变量`sessionid`。

第二条规则用于重写所有与以下RewriteRule模式匹配的URL:

```
RewriteRule   
<b>^(.+)</b>sessionid=[^&#]+ 
<i>(.*)$</i>  $1sessionid=%{sessionid}$2
```

RewriteRule模式包含两个反向引用：`(.+)`和`(.*)`。 第一个反向引用与`sessionid`之前的所有字符匹配。 第二个反向引用匹配终止`&`或`#`后的所有字符。

替代模式使用第一个反向引用，后跟字符串&quot;sessionid=&quot;，后跟由第一条规则`%{sessionid}`定义的会话ID变量值，后跟第二个反向引用来重写URL。`($1sessionid=%{sessionid} $2)`

请注意，此RewriteRule不包含RewriteCond。 因此，它会对与RewriteRule *Pattern*&#x200B;匹配的所有URL进行重写。 因此，如果sessionid变量(`%{sessionid}`)的值为`1234`，则表单`https://www.domain.com/products/?sessionid=5678&function=buy`的URL被重写为`https://www.domain.com/products/?sessionid=1234&function=buy`

## 确认{#section_B17088EF38244496BC1DDD4ECF75EB5B}

重写引擎软件最初由Apache Group开发，用于Apache HTTP服务器项目(https://www.apache.org/)。

## 添加爬网列表存储URL规则{#task_22DD40DF95584B12BE8E6ECFBF579BCD}

可以添加爬网列表存储URL规则，以指定如何重写Web内容中遇到的URL。 您可以指定不限数量的规则和条件，并可以处理所遇到的URL的任何部分。

<!-- 

t_adding_a_crawl_list_store_url_rule.xml

 -->

**要添加爬网列表存储URL规则：**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Store URL Rules]**。
1. 在[!DNL Crawl List Store URL Rules]字段中，输入所需的规则。

   允许以“#”（哈希）字符开头的空行和注释行。
1. （可选）在[!DNL Crawl List Store URL Rules]页面的[!DNL Test Crawl List Store URL Rules]字段中，输入要测试其爬网规则的测试URL，然后单击&#x200B;**[!UICONTROL Test]**。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）如果要预览结果，请重新构建分阶段站点索引。

   请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在[!DNL Crawl List Store URL Rules]页面上，执行下列任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于爬网列表检索URL规则{#concept_EC8E2E48B99A458D8567B526C9827CBA}

爬网URL规则指定如何重写Web内容中遇到的URL。 您可以指定不限数量的规则和条件，并可以处理所遇到的URL的任何部分。

<!-- 

c_about_crawl_list_retrieve_url_rules.xml

 -->

在客户看到规则的效果之前，请确保重新构建站点索引。

爬网规则对于重写URL的动态部分（如会话标识符）最有用，该标识符对于访问您网站的每个客户都是唯一的。 您还可以使用重写规则来隐藏搜索自动机中的URL部分(如查询参数)。 默认情况下，不指定任何规则，也不执行URL重写。

当网站被爬网时，嵌入的内容URL存储在要爬网的其他网页的临时列表中。 当搜索自动机从列表检索URL时，“检索重写规则”用于操作该URL的部分。 通常，检索规则用于将时间敏感数据插入URL中。 实际从您的网站中检索页面的是最终的URL。

仅当URL包含动态数据（如会话ID）且动态数据随时间变化而保持有效时，才需要检索重写规则。 在这种情况下，您使用“商店重写规则”从遇到的URL获取数据的最新状态。 然后，当搜索机器人检索页面时，您可以使用“检索重写规则”将该数据添加到每个URL。

每个规则都用重写规则(RewriteRule)指令和一个或多个可选重写条件(RewriteCond)指定。 规则的顺序很重要。 规则集按规则循环。 当规则匹配时，它循环访问任何相应的重写条件。 按以下方式指定爬网URL规则：

```
RewriteCond TestString CondPattern [Flags] 
RewriteRule Pattern Substitution [Flags]
```

遇到嵌入的URL时，搜索自动机会尝试将URL与每个爬网规则的模式匹配。 如果模式匹配，重写引擎将查找相应的RewriteCond指令。 如果不存在任何条件，则URL将替换为从替代字符串构建的新值，并继续使用规则集中的下一个规则。 如果存在条件，则按其列出顺序处理它们。 重写引擎尝试将条件模式(CondPattern)与测试字符串(TestString)匹配。 如果两者匹配，则处理下一个条件，直到不再有可用的条件。 如果所有条件都匹配，则URL将替换为规则中指定的替代。 如果条件不满足，则完整的条件集和相应的规则将失败。

## 关于RewriteRule指令{#section_32B24B29627946398AFBC5F869A610CB}

RewriteRule指令具有以下形式：

```
           
<i>RewriteRule Pattern Substitution [Flags]</i> 
        
```

`Pattern` 可以是应用于当前URL的POSIX常规表达式。“当前URL”可能与原始请求的URL不同，因为之前的规则可能已经匹配和更改了URL。

请参阅[常规表达式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

不能使用“not”字符(“！”) 以在模式前添加前缀。 “not”字符允许您取消模式，即仅当当前URL与此模式不匹配时才为true。 当更好匹配负模式时，或者作为最终的默认规则时，可以使用“not”字符。

>[!NOTE]
>
>不能在模式中同时使用&quot;not&quot;字符和分组通配符。 此外，当替换字符串包含$N时，您不能使用否定的模式。

可以使用括号在图案中创建背参照，该背参照可以由“替代”(Substitution)和“CondPattern”(CondPattern)引用。

**替** 换URL由包含以下内容的替换字符串替换：

纯文本：未更改传递的文本。

“反向引用”提供对“图案”或“第二图案”的编组部分（内括号）的访问。 以下是两种类型的反向引用：

* **RewriteRule** Backreferences这些匹配RewriteRule模式中的反向引用，其格式为$N(0)  &lt;>例如，`RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2.`

* ** RewriteCond Backreferences**这些匹配的RewriteCond CondPattern中的反向引用采用%N(0 &lt;= N &lt;= 9)形式。

变量：这些是%{NAME_OF_VARIABLE}形式的变量，其中NAME_OF_VARIABLE是定义变量名称的字符串。 有关设置环境变量的详细信息，请参阅&#x200B;*[E]*&#x200B;标志。

函数：这些函数的形式为${NAME_OF_FUNCTION:key} ，其中NAME_OF_FUNCTION如下所示：

* tolower使&#x200B;*key*&#x200B;中的所有字符都小写。
* toupper使&#x200B;*key*&#x200B;中的所有字符都为大写。
* 转义URL — 编码&#x200B;*key*&#x200B;中的所有字符。
* 字符“a”……z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;“9”、“*”、“ — ”、“。”、“/”、“@”和“_”保持不变；空格将转换为“+”，所有其他字符将转换为其%xx URL编码的等效字符。
* unescape将“+”转换回空格，所有%xx URL编码的字符都转换回单个字符。

>[!NOTE]
>
>有一个特殊的替换字符串：“ — ”表示“NO替换”。 “ — ”字符串通常与C（链）标志一起使用，这样您就可以在发生替换之前将URL与多个模式匹配。

**标志**

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>标志 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>最后一条规则。 </p> <p>停止重写过程，并且不应用任何附加的重写规则。 使用此标志可阻止对当前URL进行任何进一步处理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>下一轮。 </p> <p> 使用来自上次重写规则（而非原始URL）的URL重新运行重写过程（从第一个重写规则开始）。 小心不要造成死循环。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>用下一条规则链接。 </p> <p>将当前规则链接到下一个规则（也可以将其链接到下一个规则，依此类推）。 如果规则匹配，则替代过程将照常继续。 如果规则不匹配，则跳过所有后续的链式规则。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>没有。 </p> <p> 使图案不区分大小写（即，当图案与当前URL匹配时，“A-Z”和“a-z”之间没有差异）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>跳过下一个规则。 </p> <p> 如果当前规则匹配，则此标志将强制重写引擎跳过规则集中的下一个num规则。 使用此标志可生成伪if-then-else构造。 then-clause的最后一个规则变为skip=N ，其中N是else-clause中的规则数。 </p> <p> <p>注意： 此标志与“chain|C”标志不同！) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>设置环境变量。 </p> <p>创建设置为值VAL的环境变量"VAR"，其中VAL可以包含扩展的常规表达式反向引用$N和%N。 您可以多次使用此标志设置多个变量。 以后可以通过%{VAR}在以下RewriteCond模式中取消引用变量。 </p> <p>使用此标志可删除和记住URL中的信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>存储重写规则和检索重写规则共享变量值。 由于这种行为，当遇到并存储嵌入的URL时，您可以将变量设置为时间敏感的sessionid值。 当从临时存储列表检索下一个URL时，可以在检索该页面之前将最新的sessionid值添加到该URL。

**具有函数的RewriteRule的示例**

假设您有一个区分大小写的服务器，它以不同方式处理字符串“www.mydomain.com”和“www.MyDomain.com”。 为了使服务器正常工作，请确保域始终为“www.mydomain.com”，即使某些文档包含引用“www.MyDomain.com”的链接也是如此。 为此，可以使用以下规则：

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2
```

此重写规则使用函数`tolower`重写URL的域部分，以确保它始终为小写，如下所示：

1. 模式`(^https://([^/]*)(.*)$)`包含一个反向引用** `([^/]*)`**，它匹配URL中`https://`和第一个`/`之间的所有字符。 该模式还包含第二个反向引用`(.*)`，该反向引用与URL中所有剩余字符相匹配。
1. 替代`(https://${tolower:$1}$2)`指示搜索引擎使用第一个反向引用`(https:// ${tolower:$1}$2)`上的`tolower`函数重写URL，而URL的其余部分保持不变`(https://${tolower:$1} $2)`。

因此，表单`https://www.MyDomain.com/INTRO/index.Html`的URL被重写为`https://www.mydomain.com/INTRO/index.Html`。

## 关于RewriteCond指令{#section_ADD642A24B68452CB98294A0BD687EC3}

RewriteCond指令定义规则条件。 当RewriteCond在RewriteRule之前时，只有当规则的模式与当前标题匹配且附加条件适用时，才使用该规则。 重写条件采用以下形式：

```
           
<i>RewriteCond TestString CondPattern [Flags]</i> 
        
```

`TestString` 是一个字符串，可以包含以下构造：

纯文本：未更改传递的文本。

“反向引用”提供对“图案”或“第二图案”的编组部分（内括号）的访问。 以下是两种类型的反向引用：

* **RewriteRule** Backreferences这些匹配RewriteRule模式中的反向引用，其格式为$N(0)  &lt;>例如，`RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2`。

* **RewriteCond Backreferences这** 些匹配的RewriteCond CondPattern中的反向引用，形式为%N(0)&lt;>

变量：这些是%{NAME_OF_VARIABLE}形式的变量，其中NAME_OF_VARIABLE可以是定义变量名称的字符串。 有关设置变量的详细信息，请参阅RewriteRule *`[E]`*&#x200B;标志。

函数：这些函数的形式为${NAME_OF_FUNCTION:key} ，其中NAME_OF_FUNCTION如下所示：

* tolower使&#x200B;*key*&#x200B;中的所有字符都小写。
* toupper使&#x200B;*key*&#x200B;中的所有字符都为大写。
* 转义URL对键中的所有字符进行编码。 字符“a”……z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;“9”、“*”、“ — ”、“。”、“/”、“@”和“_”保持不变，空格将转换为“+”，所有其他字符将转换为其%xx URL编码的等效字符。
* unescape将“+”转换回空格，所有%xx URL编码字符都转换回单个字符。

**CondPattern是** 带有一些附加内容的标准扩展常规表达式。模式字符串可以前缀为“！” 字符（感叹号）指定非匹配模式。 您可以使用下列特殊变体之一，而不是实际的常规表达式字符串：

>[!NOTE]
>
>您还可以在所有这些测试前加感叹号(&#39;!&#39;) 否定他们的意义。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern字符串 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> “&lt;CondPattern” </p> </td> 
   <td colname="col2"> <p>词法上更少。 </p> <p> 将CondPattern视为纯字符串，并以词法方式将其与TestString进行比较。 如果TestString词法上小于CondPattern，则为true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>词法上更大。 </p> <p> 将CondPattern视为纯字符串，并以词法方式将其与TestString进行比较。 如果TestString词性大于CondPattern，则为true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>词法上相等。 </p> <p> 将CondPattern视为纯字符串，并以词法方式将其与TestString进行比较。 如果TestString在词法上等于CondPattern，则为true，即两个字符串完全相等（逐个字符）。 如果CondPattern仅为""（两个引号），则会将TestString与空字符串进行比较。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**标记**
（可选）将标记括在括号中 `[]`。多个标志以逗号分隔。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>标志 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> 没有。 </p> <p>此标志使测试不区分大小写，即，扩展的TestString和CondPattern中的“A-Z”和“a-z”之间没有差异。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p>或者下一个条件。 </p> <p>使用此标志将规则条件与本地OR而不是隐式AND组合。 如果没有此标志，您必须多次写入第二个/规则。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**示例**

某些网页在访客第一次到达站点时分配“sessionid” CGI变量。 此变量用于标识访客，当访客浏览站点时，变量会随之传递。 由于搜索自动机看起来像是站点的访客，因此会为它分配一个“sessionid”编号。 搜索自动机会保留此单个“sessionid”值，即使第二个站点页面尝试指定新值也是如此。 为了确保这一点，您需要两个重写规则。

第一条规则用于标识和存储会话id变量：

```
RewriteCond  %{sessionid}  !.+ 
RewriteRule  ^.+sessionid= 
<b>([^&#]+)</b>.*$  -   
<i>[E=sessionid:$1]</i>
```

RewriteRule使用E标志`([E=sessionid:$1])`将会话CGI参数的当前值指定给变量`sessionid`。 `$1`引用第一个反向引用，它包含在RewriteRule的Pattern `([^&#]+)`中的第一组括号之间。

常规表达式`^&#]+`匹配单词`sessionid`和下一个**&amp;**或**#**字符之间的URL部分。 由于此RewriteRule仅用于为sessionid变量创建初始值，因此不会重写。 请注意，规则的“替代”字段设置为`-`以指示不需要重写。

RewriteCond检查变量`sessionid`(`%{sessionid}`)。 如果它连一个字符(!.+)，则匹配RewriteRule。

使用此规则，URL将读作`https://www.domain.com/home/?sessionid=1234&function=start`，并将值`1234`赋给变量`sessionid`。

第二条规则用于重写所有与以下RewriteRule模式匹配的URL:

```
RewriteRule   
<b>^(.+)</b>sessionid=[^&#]+ 
<i>(.*)$</i>  $1sessionid=%{sessionid}$2
```

RewriteRule模式包含两个反向引用：`(.+)`和`(.*)`。 第一个反向引用与`sessionid`之前的所有字符匹配。 第二个反向引用匹配终止`&`或`#`后的所有字符。

替代模式使用第一个反向引用，后跟字符串&quot;sessionid=&quot;，后跟由第一条规则`%{sessionid}`定义的会话ID变量值，后跟第二个反向引用来重写URL。`($1sessionid=%{sessionid} $2)`

请注意，此RewriteRule不包含RewriteCond。 因此，它会对与RewriteRule *Pattern*&#x200B;匹配的所有URL进行重写。 因此，如果sessionid变量(`%{sessionid}`)的值为`1234`，则表单`https://www.domain.com/products/?sessionid=5678&function=buy`的URL被重写为`https://www.domain.com/products/?sessionid=1234&function=buy`

## 确认{#section_EC3A1DAEB5A54C93A265CB119DF91E9F}

重写引擎软件最初由Apache Group开发，用于Apache HTTP服务器项目(https://www.apache.org/)。

## 添加爬网列表检索URL规则{#task_94A28ED7DC404BFF9767DBB5ADEE6B7A}

可以添加爬网列表检索URL规则，以指定如何重写Web内容中遇到的URL。 仅当URL包含动态数据（如会话ID）且动态数据随时间变化而保持有效时，才需要检索重写规则。

<!-- 

t_adding_crawl_list_retrieve_url_rules.xml

 -->

**要添加爬网列表检索URL规则：**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Retrieve URL Rules]**。
1. 在[!DNL Crawl List Retrieve URL Rules]字段中，输入所需的规则。

   允许以“#”（哈希）字符开头的空行和注释行。
1. （可选）在[!DNL Crawl List Retrieve URL Rules]页面的[!DNL Test Crawl List Retrieve URL Rules]字段中，输入要测试其爬网规则的测试URL，然后单击&#x200B;**[!UICONTROL Test]**。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）如果要预览结果，请重新构建分阶段站点索引。

   请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在[!DNL Crawl List Retrieve URL Rules]页面上，执行下列任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于爬网标题规则{#concept_BD3A576987DA4D93A998B0B9CDDC3C79}

爬网标题规则指定在Web内容中遇到的标题存储在搜索索引中之前如何重写这些标题。

<!-- 

c_about_crawl_title_rules.xml

 -->

例如，您可以使用重写规则删除部分标题，如组织名称。 当网站被爬网时，遇到的标题存储在临时缓冲区中。 但是，在将标题添加到此缓冲区之前，将应用标题规则。 默认情况下，网站搜索/促销没有爬网标题规则，并且不会修改标题。

在客户看到规则的效果之前，请重新构建您的站点索引。

您可以使用历史记录功能快速还原对爬网标题规则所做的任何更改。

规则可以由两个主要元素组成：重写规则和可选的重写条件。 您可以指定不限数量的规则和条件。 这些规则的顺序很重要，因为规则集是按规则循环的。 当规则匹配时，它循环访问任何（可选）相应的重写条件。 按以下方式指定爬网URL规则：

```
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i> 
 
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

当遇到标题时，搜索自动机会尝试将标题与每个爬网规则的模式匹配。 如果模式匹配，重写引擎将查找相应的RewriteCond指令。 如果不存在任何条件，则URL将替换为从替代字符串构建的新值，并继续使用规则集中的下一个规则。 如果存在条件，则按其列出顺序处理它们。 重写引擎尝试将条件模式(CondPattern)与测试字符串(TestString)匹配。 如果两者匹配，则处理下一个条件，直到不再有可用的条件。 如果所有条件都匹配，则URL将替换为规则中指定的替代。 如果条件不满足，则完整的条件集和相应的规则将失败。

在文本框中输入爬网URL规则，然后单击保存更改。 允许以“#”（哈希）字符开头的空行和注释行。 要测试搜索规则，可在“测试重写规则”文本框中输入测试URL，然后单击“测试”。

## RewriteRule指令{#section_669445C505754E838E14029D6583D9B6}

每个RewriteRule指令定义一个重写规则。 规则按其列出顺序应用。 重写规则采用以下形式：

```
RewriteRule Pattern Substitution [Flags]
```

**图** 案可以是应用于当前标题的POSIX常规表达式。“当前标题”与原始标题不同，因为之前的规则已经匹配和更改了它。

请参阅[常规表达式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

可以使用“not”字符(“！”) 以在模式前添加前缀。 “not”字符允许您取消模式，即仅当当前标题与模式不匹配时才为true。 当更好匹配负模式时，或者作为最终的默认规则时，可以使用“not”字符。 注意：不能在模式中同时使用&quot;not&quot;字符和分组通配符。 此外，当替换字符串包含`$N`时，您不能使用否定的模式。

可以使用括号创建背参照，可以由Substitution和CondPattern引用。

替换 — 标题将替换为替换字符串。 该字符串可以包含以下内容：

纯文本 — 未更改传递的文本。

“反向引用”提供对“图案”或“第二图案”的编组部分（内括号）的访问。 以下是两种类型的反向引用：

* RewriteRule Backreferences — 这些匹配RewriteRule模式中的反向引用，其格式为$N(0 &lt;= N &lt;= 9)。

   例如，`RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* RewriteCond Backreferences — 这些匹配的RewriteCond CondPattern中的反向引用采用%N(0 &lt;= N &lt;= 9)形式。

变量这些是%{NAME_OF_VARIABLE}形式的变量，其中NAME_OF_VARIABLE可以是定义变量名称的字符串。 有关设置环境变量的详细信息，请参阅`[E]`标志。

函数以下是${NAME_OF_FUNCTION格式的函数：key} ，其中NAME_OF_FUNCTION为：

* tolower使&#x200B;*key*&#x200B;中的所有字符都小写。
* toupper使&#x200B;*key*&#x200B;中的所有字符都为大写。

>[!NOTE]
>
>有一个特殊的替换字符串：“ — ”表示“NO替换”。 “ — ”字符串通常对C（链）标志有用，它允许您在发生替换之前将标题与多个模式匹配。

**标志** （可选）

标记括在括号`[]`中，多个标记以逗号分隔：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>标志 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>最后一条规则。 </p> <p> 停止重写过程，不应用任何附加的重写规则。 使用此标志可防止对当前标题进行任何进一步处理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>下一轮。 </p> <p> 使用来自最后重写规则的标题（而非原始标题）重新运行重写过程（从第一个重写规则重新开始）。 小心不要造成死循环。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>用下一条规则链接。 </p> <p>将当前规则链接到下一个规则（也可以将其链接到下一个规则，依此类推）。 如果规则匹配，则替代过程将照常继续。 如果规则不匹配，则跳过所有后续的链式规则。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>没有。 </p> <p>使图案不区分大小写（即，当图案与当前标题匹配时，“A-Z”和“a-z”之间没有差异）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>跳过下一条规则。 </p> <p> 如果当前规则匹配，则此标志将强制重写引擎跳过规则集中的下一个num规则。 使用它生成伪if-then-else构造。 then-clause的最后一个规则变为skip=N ，其中N是else-clause中的规则数。 (注：这与“chain|C”标志不同！) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>设置环境变量。 </p> <p> 创建设置为值VAL的环境变量"VAR"，其中VAL可以包含正则表达式反向引用，$N和%N，这是展开的。 您可以多次使用此标志设置多个变量。 以后可以通过%{VAR}在以下RewriteCond模式中引用变量。 使用此标记删除和记住标题中的信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## RewriteCond指令（可选）{#section_D664B71DE3884E0790531804C49A3222}

RewriteCond指令定义规则条件。 当RewriteCond在RewriteRule之前时，只有当规则的模式与当前标题匹配且附加条件适用时，才使用该规则。

重写条件指令采用以下形式：

```
RewriteCond TestString CondPattern [Flags] 
```

**TestString** 是一个字符串，可以包含以下构造：

纯文本 — 未更改传递的文本。

“反向引用”提供对“图案”或“第二图案”的编组部分（内括号）的访问。 有两种类型的反向引用：

* RewriteRule Backreferences — 这些匹配RewriteRule模式中的反向引用，其格式为$N(0 &lt;= N &lt;= 9)。

   例如，`RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* RewriteCond Backreferences — 这些匹配的RewriteCond CondPattern中的反向引用采用%N(0 &lt;= N &lt;= 9)形式。

变量这些是%{NAME_OF_VARIABLE}形式的变量，其中NAME_OF_VARIABLE可以是定义变量名称的字符串。 有关设置环境变量的详细信息，请参阅`[E]`标志。

函数这些函数是${NAME_OF_FUNCTION:key}形式的函数，其中NAME_OF_FUNCTION为：

* tolower使&#x200B;*key*&#x200B;中的所有字符都小写。
* toupper使&#x200B;*key*&#x200B;中的所有字符都为大写。
* 转义URL对键中的所有字符进行编码。
* 字符“a”……z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;“9”、“*”、“ — ”、“。”、“/”、“@”和“_”保持不变，空格将转换为“+”，所有其他字符将转换为其%xx URL编码的等效字符。
* unescape将“+”转换回空格，所有%xx URL编码的字符都转换回单个字符。

**CondPattern是** 带有一些附加内容的标准扩展常规表达式。模式字符串可以前缀为“！” 字符（感叹号）指定非匹配模式。 您可以使用以下某个特殊变体，而不是真正的常规表达式字符串。

>[!NOTE]
>
>可以在所有这些测试前加感叹号(“！”) 否定他们的意义。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern字符串 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> “&lt;CondPattern” </p> </td> 
   <td colname="col2"> <p>词法上更少。 </p> <p>将<i>CondPattern</i>视为普通字符串，并将其与<i>TestString</i>进行词性比较。 如果<i>TestString</i>词法上小于<i>CondPattern</i>，则为true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>词法上更大。 </p> <p>将<i>CondPattern</i>视为普通字符串，并将其与<i>TestString</i>进行词性比较。 如果<i>TestString</i>词法上大于<i>CondPattern</i>，则为true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p> 在词法上相等。 </p> <p>将<i>CondPattern</i>视为普通字符串，并将其与<i>TestString</i>进行词性比较。 如果<i>TestString</i>在词法上等于<i>CondPattern</i>，则为true，即这两个字符串完全相等（逐个字符）。 如果<i>CondPattern</i>仅为""（两个引号），则将<i>TestString</i>与空字符串进行比较。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**标志** （可选）

标记括在括号`[]`中，多个标记以逗号分隔：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>标志 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>没有。 </p> <p> 使测试不敏感。 也就是说，在扩展的<i>TestString</i>和<i>CondPattern中，“A-Z”和“a-z”之间没有差异。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p> 或者下一个条件。 </p> <p>使用此标志将规则条件与本地OR而不是隐式AND组合。 如果没有此标志，您必须多次写入第二个/规则。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**示例**

假定您拥有一个标有标题格式的企业网站：“我的公司”后跟连字符，然后是页面特定的描述(例如，“我的公司 — 欢迎”或“我的公司 — 新闻”)。 您希望从标题中去除“我的公司 — ”，并在对站点进行索引时将整个标题转换为大写字母。

以下重写规则使用函数拖页将标题的描述性部分仅重写为大写：

```
RewriteRule  ^My[[:blank:]]Company[[:blank:]]-[[:blank:]] 
<b>(.*)</b>$  ${toupper: 
<b>$1</b>}
```

规则的模式

`(^My[[:blank:]]Company[[:blank:]]-[[:blank:]] (.*))`

包含与“我的公司 — ”后面的标题内容相匹配的反向引用`(.*)`。 请记住，带括号()的图案的一部分周围会创建可由替代引用的反向引用。 在此示例中，替代

`(${toupper:**$1**})`

使用toupper函数重写该backreference(`**$1**`)。

因此，&quot;我的公司 — 欢迎&quot;形式的标题被改写为&quot;欢迎&quot;。

**确认**

重写引擎软件最初由Apache Group开发，用于Apache HTTP服务器项目(https://www.apache.org/)。

## 添加爬网标题规则{#task_272BB4C603BA4C9ABDBEEB398798B101}

可以添加爬网标题规则，以指定在Web内容中遇到的标题存储在搜索索引中之前如何重写这些标题。

<!-- 

t_adding_crawl_title_rules.xml

 -->

**要添加爬网标题规则：**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl Title Rules]**。
1. 在[!DNL Crawl Title Rules]字段中，输入所需的规则。

   允许以“#”（哈希）字符开头的空行和注释行。
1. （可选）在[!DNL Crawl Title Rules]页面的[!DNL Test Crawl Title Rules]字段中，输入要测试其搜索规则的测试URL，然后单击&#x200B;**[!UICONTROL Test]**。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）如果要预览结果，请重新构建分阶段站点索引。

   请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在[!DNL Crawl Title Rules]页面上，执行下列任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于搜索URL规则{#concept_017EC95E68844B6C8CC9F874F0EC8D3C}

搜索URL规则指定网站搜索结果中URL的显示方式。 规则在完整URL上运行。 URL的任何部分都可以处理，包括经常保留会话ID信息的查询参数。

<!-- 

c_about_search_url_rules.xml

 -->

通常，搜索URL规则用于将会话ID插入URL。 但是，您也可以使用搜索URL规则来更改随结果一起显示的域名。 默认情况下，未指定规则，也不执行URL修改。

搜索URL规则可以包含两个主要元素：重写规则和可选的重写条件。 当将URL作为搜索结果的一部分包含在内时，将使用规则对其进行操作。 可以指定不限数量的搜索URL规则和条件。 这些规则的顺序很重要，因为规则集是通过逐个规则循环的。 当规则匹配时，软件循环访问任何（可选）相应的重写条件。 按以下方式指定爬网URL规则：

```
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i> 
 
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

处理URL时，网站搜索/促销会尝试将其与每个搜索规则的模式匹配。 如果匹配失败，重写引擎将立即停止处理该规则并继续执行集合中的下一个规则。 如果模式匹配，重写引擎将查找相应的RewriteCond指令。 如果不存在条件，则URL将替换为新值。 此值由替代字符串构造，并与规则集中的下一个规则一起继续。 如果存在条件，则列出这些条件的顺序是处理这些条件的方式。 重写引擎尝试将条件模式(CondPattern)与测试字符串(TestString)匹配。 如果两者匹配，则处理下一个条件，直到不再有可用的条件。 如果所有条件都匹配，则URL将替换为规则中指定的替代。 如果条件不满足，则完整的条件集和相应的规则将失败。

## 关于RewriteRule指令{#section_A3473B5B90B74DA1970213113A90591E}

重写规则采用以下形式：

```
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

**** 模式可以是POSIX常规表达式，可应用到当前URL。“当前URL”可能与原始URL不同，因为之前的规则可能已经匹配和更改了它。

请参阅[常规表达式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

可以使用“not”字符(“！”) 以在模式前添加前缀。 “not”字符允许您取消模式。 换句话说，仅当当前URL与模式不匹配时，才为true。 当与负模式匹配较好时，您可以使用“not”字符，或者作为最终的默认规则。 请注意，您不能在模式中同时使用“not”字符和分组通配符。 此外，当替换字符串包含$N时，您不能使用否定的模式。

可以使用括号创建背参照，可以由Substitution和CondPattern引用。

**替** 换URL被替换字符串完全替换，该字符串可以包含以下内容：

纯文本 — 未更改传递的文本。

反向引用提供对“图案”或“条纹”的编组部分（内括号）的访问。 有两种类型的反向引用：

RewriteRule反向引用这些匹配反向引用在相应的RewriteRule模式中，其格式为$N(0 &lt;= N &lt;= 9)。 例如，`RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

RewriteCond Backreferences — 这些匹配的RewriteCond CondPattern中的反向引用采用%N(0 &lt;= N &lt;= 9)形式。

函数：这些函数的形式为${NAME_OF_FUNCTION:key} ，其中NAME_OF_FUNCTION为：

* tolower使&#x200B;*key*&#x200B;中的所有字符都小写。
* toupper使&#x200B;*key*&#x200B;中的所有字符都为大写。
* 转义URL — 编码&#x200B;*key*&#x200B;中的所有字符。
* 字符“a”……z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;“9”、“*”、“ — ”、“。”、“/”、“@”和“_”保持不变；空格将转换为“+”；所有其他字符都将转换为其%xx URL编码的等效字符。
* unescape将“+”转换回空格，所有%xx URL编码的字符都转换回单个字符。

>[!NOTE]
>
>有一个特殊的替换字符串：“ — ”表示“NO替换”。 “ — ”字符串通常与C（链）标志结合使用。 它允许您在发生替换之前将URL与多个模式匹配。

**标志** （可选）

标记括在括号`[]`中，多个标记以逗号分隔：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>标志 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>最后一条规则。 </p> <p> 停止重写过程，不要应用任何附加的重写规则。 使用此标志可阻止对当前URL进行任何进一步处理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p> 下一轮。 </p> <p>使用来自上次重写规则（而非原始URL）的URL重新运行重写过程（从第一个重写规则开始）。 小心不要造成死循环！ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p> 用下一条规则链接。 </p> <p>此标志将当前规则链接到下一个规则，也可以将其链接到下一个规则，依此类推。 如果规则匹配，则替代过程将照常继续。 如果规则不匹配，则跳过所有后续的链式规则。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>没有。 </p> <p>此标志使“图案”不区分大小写。 换句话说，当模式与当前URL匹配时，“A-Z”和“a-z”之间没有差异。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>跳过下一条规则。 </p> <p> 如果当前规则匹配，则此标志将强制重写引擎跳过规则集中的下一个num规则。 使用它生成伪if-then-else构造。 then-clause的最后一个规则变为skip=N ，其中N是else-clause中的规则数。 (注：这与“chain|C”标志不同！) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>设置环境变量。 </p> <p> 此标志创建一个设置为值VAL的环境变量“VAR”。 VAL可以包含正则表达式回溯引用，$N和%N，这些引用已展开。 您可以多次使用此标志设置多个变量。 以后可以通过%{VAR}在以下RewriteCond模式中取消引用变量。 使用此标志可删除和记住URL中的信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

请注意，存储重写规则和检索重写规则共享变量值。 因此，在遇到并存储嵌入的URL时，可以将变量设置为时间敏感的会话id值。 当从临时存储列表检索下一个URL时，可以在检索该页面之前将最新的sessionid值添加到该URL。

**示例**

假设您有一个区分大小写的服务器。 它以不同方式处理字符串&quot;www.mydomain.com&quot;和&quot;www.MyDomain.com&quot;。 要使服务器正常工作，您必须确保域始终为“www.mydomain.com”，即使某些文档包含引用“www.MyDomain.com”的链接。 为此，可以使用以下规则：

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2 
```

此重写规则使用函数&quot;tolower&quot;重写URL的域部分，以确保它始终为小写：

1. 模式`(^https://([^/]*)(.*)$)`包含一个反向引用&#x200B;**`([^/]*)`**，它匹配URL中&quot;https://&quot;和第一个&quot;/&quot;之间的所有字符。 该模式还包含第二个反向引用&#x200B;**(.*)**，它匹配URL中所有剩余字符。

1. 替换`(https://${tolower:$1}$2)`命令搜索引擎使用第一个反向引用`(https://**${tolower:$1**}$2)`上的&#x200B;**tolower**&#x200B;函数来重写URL，而保留URL的其余部分未更改`(https://${tolower:$1}*$2*)`。

因此，表单`https://www.MyDomain.com/INTRO/index.Html`的URL被重写为`https://www.mydomain.com/INTRO/index.Html`

**RewriteCond指令** （可选）

RewriteCond指令定义规则条件。 当RewriteCond在RewriteRule之前时，只有当规则的模式与当前标题匹配且附加条件适用时，才使用该规则。

重写条件指令采用以下形式：

```
RewriteCond  
<i>TestString CondPattern [Flags]</i>
```

*TestString* 是一个字符串，可以包含以下构造：

纯文本：未更改传递的文本。

“反向引用”提供对“图案”或“第二图案”的编组部分（内括号）的访问。 有两种类型的反向引用：

* RewriteRule Backreferences — 这些匹配RewriteRule模式中的反向引用，其格式为$N(0 &lt;= N &lt;= 9)。

   例如，`RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* RewriteCond Backreferences — 这些匹配的RewriteCond CondPattern中的反向引用采用%N(0 &lt;= N &lt;= 9)形式。

变量这些是%{NAME_OF_VARIABLE}形式的变量，其中NAME_OF_VARIABLE可以是定义变量名称的字符串。 有关设置变量的详细信息，请参阅RewriteRule *`[E]`*&#x200B;标志。

>[!NOTE]
>
>重写规则通常利用变量。 来自当前URL的所有CGI参数都会自动变量。 例如，搜索URL `"https://search.atomz.com/search/?sp_a=sp00000000&sp_q="Product"&session=1234&id=5678"`会自动提供四个变量，这些变量可在重写规则中引用。 在此示例中，一个变量称为“session”，其值为“1234”，而另一个变量称为“id”，其值为“5678”。 （另外两个变量是`sp_a`和`sp_q`。） 您应将网页上搜索表单中所有必需的变量作为隐藏字段进行传递。 在此示例中，您应传递“session”和“id”值，它们标识执行搜索的网站用户。 要在搜索表单上传递隐藏字段，请使用`<input type=hidden name="session" value="1234">`等标签。

函数这些函数是${NAME_OF_FUNCTION:key}形式的函数，其中NAME_OF_FUNCTION为：

* tolower使&#x200B;*key*&#x200B;中的所有字符都小写。
* toupper使&#x200B;*key*&#x200B;中的所有字符都为大写。
* 转义URL — 编码&#x200B;*key*&#x200B;中的所有字符。 字符“a”……z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;“9”、“*”、“ — ”、“。”、“/”、“@”和“_”保持不变，空格将转换为“+”，所有其他字符将转换为其%xx URL编码的等效字符。
* unescape将“+”转换回空格，所有%xx URL编码字符都转换回单个字符。

**CondPattern是** 带有一些附加内容的标准扩展常规表达式。模式字符串可以前缀为“！” 字符（感叹号）指定非匹配模式。 您可以使用以下某个特殊变体，而不是真正的常规表达式字符串。

可以使用感叹号(“！”)在所有这些测试前添加前缀 否定他们的意义。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern字符串 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> “&lt;CondPattern” </p> </td> 
   <td colname="col2"> <p>词法上更少。 </p> <p> 将<i>CondPattern</i>视为普通字符串，并将其与<i>TestString</i>进行词性比较。 如果<i>TestString</i>词法上小于<i>CondPattern</i>，则为true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>词法上更大。 </p> <p> 将<i>CondPattern</i>视为普通字符串，并将其与<i>TestString</i>进行词性比较。 如果<i>TestString</i>词法上大于<i>CondPattern</i>，则为true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>在词法上相等。 </p> <p> 将<i>CondPattern</i>视为普通字符串，并将其与<i>TestString</i>进行词性比较。 如果<i>TestString</i>在词法上等于<i>CondPattern</i>，则为true。 即，两个字符串完全相等（逐个字符）。 如果<i>CondPattern</i>仅为""（两个引号），则将<i>TestString</i>与空字符串进行比较。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**标志** （可选）

标记括在括号`[]`中，多个标记以逗号分隔：

“nocase|NC”（无大小写）：这使测试不区分大小写。 换句话说，在展开的&#x200B;*TestString*&#x200B;和&#x200B;*CondPattern*&#x200B;中，“A-Z”和“a-z”之间没有差异。

“ornext|OR”（或下一个条件）：使用它将规则条件与局部OR（而不是隐式AND）组合。 如果没有此标志，您必须多次写入第二个/规则。

**示例**

某些网页在客户第一次到达网站时分配“sessionid” CGI变量。 此变量用于标识客户，并且当客户浏览网站时，变量会随之传递。 由于搜索自动机看起来就像您网站的客户，因此会为它分配一个“sessionid”编号。 搜索自动机会保留此单个“sessionid”值，即使第二个站点页面尝试指定新值也是如此。 为确保此，您需要以下重写规则：

```
RewriteCond  %{sessionid}  .+ 
RewriteRule  ^ 
<b>(.+)</b>sessionid=[^&#]+ 
<i>(.*)</i>$   
<b>$1</b>sessionid=%{sessionid} 
<i>$2</i>
```

RewriteRule模式包含两个反向引用：(.+) 和 (.*)。第一个反向引用匹配&quot;sessionid=&quot;之前的所有字符。 第二个反向引用匹配会话id终止“&amp;”或“#”后的所有字符。

替代模式使用第一个反向引用，后跟字符串&quot;sessionid=&quot;，再跟会话ID变量的值（在URL中作为CGI参数传递，后跟第二个反向引用）重写URL。`($1sessionid=%{sessionid}$2)`。

**RewriteCond**&#x200B;检查变量sessionid `(%{sessionid})`。 如果它至少包含一个字符(.+)，则匹配RewriteRule。

因此，如果搜索查询为`"https://search.atomz.com/search/?sp_a=sp99999999&sp_q=word&sessionid=5678"`，则将重写所有搜索结果URL，以使“sessionid”值为“5678”，而不是搜索机器人在搜索您的站点并保存链接时遇到的“sessionid”值。

**确认**

重写引擎软件最初由Apache Group开发，用于Apache HTTP服务器项目(https://www.apache.org/)。

## 添加搜索URL规则{#task_50C77D1B53804AEEB20896F74265BD6F}

您可以添加搜索URL规则，以指定网站搜索结果中URL的显示方式。 规则在完整URL上运行。 您可以操作URL的任何部分，包括经常保留会话ID信息的查询参数。

<!-- 

t_adding_search_url_rules.xml

 -->

**要添加搜索URL规则：**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Search URL Rules]**。
1. 在[!DNL Search URL Rules]字段中，输入所需的规则。

   允许以“#”（哈希）字符开头的空行和注释行。

1. （可选）在[!DNL Search URL Rules]页面的[!DNL Test Search URL Rules]字段中，输入要测试其爬网规则的测试URL，然后单击&#x200B;**[!UICONTROL Test]**。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）如果要预览结果，请重新构建分阶段站点索引。

   请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在[!DNL Search URL Rules]页面上，执行下列任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于搜索标题规则{#concept_C72D20F8DFF64EDE809AF4B72797E858}

搜索标题规则指定网站搜索结果中标题的显示方式。 标题的任何部分都可进行操作。

<!-- 

c_about_search_title_rules.xml

 -->

例如，可能使用重写规则来删除标题的一部分，如组织名称。 默认情况下，网站搜索/促销没有标题规则，也不会修改标题。

标题规则可以包含两个主要元素：RewriteRule和可选RewriteCond。 可以指定不限数量的规则和条件。 这些规则的顺序很重要，因为规则集是逐个规则循环的。 当规则匹配时，软件循环访问任何（可选）相应的重写条件。 搜索标题规则按以下方式指定：

```
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i> 
 
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

遇到标题时，网站搜索/促销会尝试将其与每个爬网规则的模式匹配。 如果模式匹配，重写引擎将查找相应的RewriteCond指令。 如果不存在任何条件，则标题将替换为从替代字符串构建的新值，并继续使用规则集中的下一个规则。 如果存在条件，则按其列出顺序处理它们。 重写引擎尝试将条件模式(CondPattern)与测试字符串(TestString)匹配。 如果两者匹配，则处理下一个条件，直到不再有可用的条件。 如果所有条件都匹配，则URL将替换为规则中指定的替代。 如果条件不满足，则完整的条件集和相应的规则将失败。

## RewriteRule指令{#section_3BF2B0FF89F74A26AE79D68FA3184B9B}

每个RewriteRule指令定义一个重写规则。 规则按其列出顺序应用。 重写规则采用以下形式：

```
RewriteRule Pattern Substitution [Flags]
```

**Pattern** A POSIX常规表达式，它应用于当前标题。“当前标题”可能与原始标题不同，因为早期规则可能已匹配并更改了它。

请参阅[常规表达式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

您可以使用“not”字符(“！”) 以在模式前添加前缀。 “not”字符允许您取消模式。 即，仅当当前标题与模式不匹配时才为true。 当更好匹配负模式时，或者作为最终的默认规则时，可以使用“not”字符。 注意：不能在模式中同时使用&quot;not&quot;字符和分组通配符。 此外，当替换字符串包含$N时，您不能使用否定的模式。

可以使用括号创建反向引用，后向引用可由“替代”和“条纹”引用。

**替** 换标题由替换字符串完全替换，它可以包含以下内容：

纯文本 — 未更改传递的文本。

* 反向引用 — 提供对“图案”或“条纹”的编组部分（内括号）的访问。 以下是两种类型的反向引用：

* RewriteRule Backreferences — 这些匹配RewriteRule模式中的反向引用，其格式为$N(0 &lt;= N &lt;= 9)。

   例如，`RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* ** RewriteCond Backreferences**这些匹配的RewriteCond CondPattern中的反向引用采用%N(0 &lt;= N &lt;= 9)形式。

**变** 量这些是%{NAME_OF_VARIABLE}形式的变量，其中NAME_OF_VARIABLE可以是定义变量名称的字符串。有关设置环境变量的详细信息，请参阅[E]标志。 变量也可以在生成搜索结果的搜索表单中定义。

**函** 数以下是${NAME_OF_FUNCTION格式的函数：key} ，其中NAME_OF_FUNCTION为：

* tolower使&#x200B;*key*&#x200B;中的所有字符都小写。
* toupper使&#x200B;*key*&#x200B;中的所有字符都为大写。

有一个特殊的替换字符串：“ — ”表示“NO替换”。 “ — ”字符串通常与C（链）标志结合使用，允许您在发生替换之前将标题与多个模式匹配。

**标志** （可选）

标记括在括号`[]`中，多个标记以逗号分隔：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>标志 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p> 最后一条规则。 </p> <p> 停止重写过程，不要应用任何附加的重写规则。 使用此标志可防止对当前标题进行任何进一步处理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>下一轮。 </p> <p> 使用来自最后重写规则（而非原始标题！）的标题重新运行重写过程（从第一个重写规则重新开始）。 小心不要造成死循环。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>用下一条规则链接。 </p> <p> 此标志将当前规则链接到下一个规则（也可以将其链接到下一个规则，依此类推）。 如果规则匹配，则替代过程将照常继续。 如果规则不匹配，则跳过所有后续的链式规则。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> 没有。 </p> <p> 此标志使“图案”不区分大小写。 也就是说，当图案与当前标题匹配时，“A-Z”和“a-z”之间没有差异。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p> 跳过下一条规则。 </p> <p> 如果当前规则匹配，则此标志将强制重写引擎跳过规则集中的下一个num规则。 使用它生成伪if-then-else构造。 then-clause的最后一个规则变为skip=N ，其中N是else-clause中的规则数。 （这与“chain|C”标志不同！） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>设置环境变量。 </p> <p> 此标志创建一个设置为值VAL的环境变量"VAR"，其中VAL可以包含常规表达式反向引用，$N和%N，将展开。 您可以多次使用此标志设置多个变量。 以后可以通过%{VAR}在以下RewriteCond模式中引用变量。 使用此标记删除和记住标题中的信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## RewriteCond指令（可选）{#section_9D72B2AB454849A7B681BC39C506AAA3}

RewriteCond指令定义规则条件。 当RewriteCond在RewriteRule之前时，只有当规则的模式与当前标题匹配且附加条件适用时，才使用该规则。

重写条件指令采用以下形式：

```
RewriteCond TestString CondPattern [Flags]
```

**TestString** 是一个字符串，可以包含以下构造：

纯文本 — 未更改传递的文本。

“反向引用”提供对“图案”或“第二图案”的编组部分（内括号）的访问。 有两种类型的反向引用：

* RewriteRule Backreferences — 这些匹配RewriteRule模式中的反向引用，其格式为$N(0 &lt;= N &lt;= 9)。

   例如，`RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* RewriteCond Backreferences — 这些匹配的RewriteCond CondPattern中的反向引用采用%N(0 &lt;= N &lt;= 9)形式。

**变** 量这些是%{NAME_OF_VARIABLE}形式的变量，其中NAME_OF_VARIABLE可以是定义变量名称的字符串。有关设置环境变量的详细信息，请参阅`[E]`标志。 变量也可以在生成搜索结果的搜索表单中定义。

**函** 数这些函数的形式为${NAME_OF_FUNCTION:key} ，其中NAME_OF_FUNCTION为：

* tolower使&#x200B;*key*&#x200B;中的所有字符都小写。
* toupper使&#x200B;*key*&#x200B;中的所有字符都为大写。
* 转义URL — 编码&#x200B;*key*&#x200B;中的所有字符。
* 字符“a”……z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;“9”、“*”、“ — ”、“。”、“/”、“@”和“_”保持不变，空格将转换为“+”，所有其他字符将转换为其%xx URL编码的等效字符。
* unescape将“+”转换回空格，所有%xx URL编码的字符都转换回单个字符。

有一个特殊的替换字符串：“ — ”表示“NO替换”。 “ — ”字符串通常与C（链）标志结合使用，允许您在发生替换之前将URL与多个模式匹配。

**CondPattern** 带一些附加的标准扩展常规表达式。模式字符串可以前缀为“！” 字符（感叹号）指定非匹配模式。 您可以使用以下某个特殊变体，而不是真正的常规表达式字符串。

所有这些测试还可以用感叹号(&#39;!&#39;)作为前缀 否定他们的意义。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern字符串 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> “&lt;CondPattern” </p> </td> 
   <td colname="col2"> <p>词法上更少。 </p> <p> 将<i>CondPattern</i>视为普通字符串，并将其与<i>TestString</i>进行词性比较。 如果<i>TestString</i>词法上小于<i>CondPattern</i>，则为true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p> 词法上更大。 </p> <p> 将<i>CondPattern</i>视为普通字符串，并将其与<i>TestString</i>进行词性比较。 如果<i>TestString</i>词法上大于<i>CondPattern</i>，则为true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>在词法上相等。 </p> <p> 将<i>CondPattern</i>视为普通字符串，并将其与<i>TestString</i>进行词性比较。 如果<i>TestString</i>在词法上等于<i>CondPattern</i>，则为true。 即，两个字符串完全相等（逐个字符）。 如果<i>CondPattern</i>仅为""（两个引号），则将<i>TestString</i>与空字符串进行比较。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**标志** （可选）

标记括在方括号`[]`中，多个标记以逗号分隔：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>标志 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> “nocase|NC”（无大小写） </p> </td> 
   <td colname="col2"> <p>使测试不敏感。 也就是说，在展开的<i>TestString</i>和<i>CondPattern</i>中，“A-Z”和“a-z”之间没有差异。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> “ornext|OR”（或下一个条件） </p> </td> 
   <td colname="col2"> <p> 使用它将规则条件与局部OR（而不是隐式AND）组合。 如果没有此标志，您必须多次写入第二个/规则。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 示例 {#section_E7454FFE169E459AABD9D033651939CB}

假定您拥有一个标有标题格式的企业网站：“我的公司”后跟连字符，然后是页面特定的描述(例如，“我的公司 — 欢迎”或“我的公司 — 新闻”)。 您希望从标题中去除“我的公司 — ”，并在对站点进行索引时将整个标题转换为大写字母。

以下重写规则使用函数拖页将标题的描述性部分仅重写为大写：

```
RewriteRule  ^My[[:blank:]]Company[[:blank:]]-[[:blank:]] 
<b>(.*)</b>$  ${toupper: 
<b>$1</b>} 
```

规则的模式`(^My[[:blank:]]Company[[:blank:]]-[[:blank:]] (.*))`包含与“我的公司 — ”后面的标题内容匹配的反向引用&#x200B;**`(.*)`**。 请记住，带括号()的图案的一部分周围会创建可由替代引用的反向引用。 在此示例中，替代

`(${toupper:**$1**})`

使用toupper函数重写该backreference(**$1**)。

因此，&quot;我的公司 — 欢迎&quot;形式的标题被改写为&quot;欢迎&quot;。

**确认**

重写引擎软件最初由Apache Group开发，用于Apache HTTP服务器项目(https://www.apache.org/)。

## 添加搜索标题规则{#task_155CECB74BE3444384EDBBD04F41515E}

您可以添加搜索标题规则以指定网站搜索结果中标题的显示方式。 您可以操作标题的任何部分。

<!-- 

t_adding_search_title_rules.xml

 -->

**要添加搜索标题规则，请执行以下操作：**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Search Title Rules]**。
1. 在[!DNL Search Title Rules]字段中，输入所需的规则。

   允许以“#”（哈希）字符开头的空行和注释行。
1. （可选）在[!DNL Search Title Rules]页面的[!DNL Test Search Title Rules]字段中，输入测试标题，然后单击&#x200B;**[!UICONTROL Test]**。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）如果要预览结果，请重新构建分阶段站点索引。

   请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在[!DNL Search Title Rules]页面上，执行下列任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。
