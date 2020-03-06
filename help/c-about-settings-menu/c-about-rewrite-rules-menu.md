---
description: 使用“重写规则”菜单设置爬行和搜索URL和标题规则。
seo-description: 使用“重写规则”菜单设置爬行和搜索URL和标题规则。
seo-title: 关于“重写规则”菜单
solution: Target
subtopic: Rewrite Rules
title: 关于“重写规则”菜单
topic: Settings,Site search and merchandising
uuid: 77ee84dd-fdba-4d34-ae8e-2fe786599800
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a

---


# 关于“重写规则”菜单 {#about-the-rewrite-rules-menu}

使用“重写规则”菜单设置爬行和搜索URL和标题规则。

## 关于爬行列表存储URL规则 {#concept_B71CF4C8030A4A74A22C3BFE4DE3B865}

爬网URL规则指定如何重写它在Web内容中遇到的URL。 您可以指定不限数量的规则和条件，并可以处理所遇到的URL的任何部分。

<!-- 

c_about_crawl_list_store_url_rules.xml

 -->

爬行规则对重写URL的动态部分最有用，例如会话标识符对于访问您网站的每个客户都是唯一的。 您还可以使用重写规则从搜索自动机中隐藏URL的某些部分，如查询参数。 默认情况下，不指定规则，也不执行URL重写。

当网站被爬网时，嵌入的内容URL存储在要爬网的其他网页的临时列表中。 在将URL添加到此列表之前，会将商店重写规则应用到该列表。 通常，商店重写规则用于从URL中删除会话ID或强制执行特定会话ID以进行搜索。 当搜索自动机从列表中检索URL时，检索重写规则将用于再次操作该URL的部分。 通常，检索规则用于将时间敏感数据插入URL中。 这是最终的URL，用于从您的网站中实际检索页面。

请参 [阅关于爬行列表检索URL规则](../c-about-settings-menu/c-about-rewrite-rules-menu.md#concept_EC8E2E48B99A458D8567B526C9827CBA)。

通常，您只使用商店URL规则。 仅当URL包含动态数据（如会话ID），并且该动态数据随时间变化而保持有效时，才需要检索URL规则。 在这种情况下，您使用“商店URL规则”从遇到的URL获取数据的最新状态。 然后，当搜索自动机尝试检索页面时，您可以使用“检索URL规则”将该数据添加到每个URL。

每个规则都使用重写规则(RewriteRule)指令和一个或多个可选的重写条件(RewriteCond)来指定。 规则的顺序很重要。 规则集按规则循环。 当规则匹配时，它循环访问任何相应的重写条件。 按以下方式指定了游动URL规则：

```
RewriteCond TestString CondPattern [Flags] 
RewriteRule Pattern Substitution [Flags]
```

当遇到嵌入的URL时，搜索自动机会尝试将URL与每个爬行规则的模式匹配。 如果模式匹配，重写引擎将查找相应的RewriteCond指令。 如果不存在条件，则URL将替换为从替代字符串构建的新值，并继续执行规则集中的下一个规则。 如果存在条件，则按其列出的顺序处理这些条件。 重写引擎尝试将条件模式(CondPattern)与测试字符串(TestString)匹配。 如果两个匹配项匹配，则会处理下一个条件，直到没有其他条件可用。 如果所有条件都匹配，则URL将替换为规则中指定的替代。 如果条件不满足，则完整的条件集和相应的规则将失败。

## 关于RewriteRule指令 {#section_162122340BB34F12BB9A36DC9349092B}

RewriteRule指令具有以下形式：

```
           
<i>RewriteRule Pattern Substitution [Flags]</i> 
        
```

`Pattern` 可以是POSIX正则表达式，它应用于当前URL。 “当前URL”可能与原始请求的URL不同，因为之前的规则可能已匹配和更改了URL。

请参阅 [正则表达式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

不能使用“not”字符(&#39;!&#39;)在模式前添加前缀。 “not”字符允许您取消模式，即仅当当前URL与此模式不匹配时才为true。 当最好匹配负模式时，可以使用“not”字符，或者作为最终的默认规则。

>[!NOTE]
>
>不能在模式中使用“not”字符和分组通配符。 此外，当替换字符串包含$N时，您不能使用否定的模式。

可以使用括号在图案中创建背向参照，该背向参照可由Substitution和CondPattern引用。

**替换** URL由替换字符串替换，该字符串包含以下内容：

纯文本：传递的文本未更改。

Backreferences提供对“图案”或“条纹”的分组部分（内括号）的访问。 以下是两种类型的回溯引用：

* **RewriteRule Backreferences** These match backreferences in the expored RewriteRule Pattern, the form $N(0 &lt;= N &lt;= 9)。 例如，`RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2.`

* **RewriteCond Backreferences** Thes the satched RewriteCondPattern中的这些反向引用与上一个匹配的RewriteCond CondPattern中的反向引用相匹配，其格式为%N(0 &lt;= N &lt;= 9)。

变量：这些是%{NAME_OF_VARIABLE}形式的变量，其中NAME_OF_VARIABLE是定义变量名称的字符串。 有关设置环 `*[E]*` 境变量的更多信息，请参阅标记。

函数：这些函数的形式为${NAME_OF_FUNCTION:key} ，其中NAME_OF_FUNCTION如下所示：

* tolower使所有字符均以小 *写* 。
* toupper使所有字符均以大 *写形式* 。
* escape URL对密钥中的所有字符进行 *编码*。
* 字符“a”。z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;...&#39;9&#39;、&#39;*&#39;、&#39;-&#39;、&#39;.&#39;、&#39;/&#39;、&#39;@&#39;和&#39;_&#39;保持不变；空格将转换为“+”，所有其他字符将转换为其%xx URL编码的等效字符。
* unescape将“+”转换回空格，所有%xx URL编码的字符都转换回单个字符。

>[!NOTE]
>
>有一个特殊的替换字符串：这 `'-'` 意味着&quot;不能替代&quot; 该字 `'-'` 符串通常与C(chain)标志一起使用，这样您就可以在发生替换之前将URL与多个模式匹配。

**旗**

（可选）将标记括在括号中 `[]`。 多个标志以逗号分隔。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>旗标 </p> </th> 
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
   <td colname="col2"> <p>下一轮。 </p> <p> 使用来自上一重写规则（而非原始URL）的URL重新运行重写过程（从第一重写规则开始）。 小心不要造成死循环！ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>用下一条规则链接。 </p> <p>将当前规则链接到下一个规则（也可以将其链接到下一个规则，依此类推）。 如果规则匹配，则替换过程将照常继续。 如果规则不匹配，则跳过所有后续的链式规则。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>没案子。 </p> <p> 使图案不区分大小写（即，当图案与当前URL匹配时，“A-Z”和“a-z”之间没有区别）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>跳过下一个规则。 </p> <p> 如果当前规则匹配，则此标志将强制重写引擎跳过规则集中的下一个num规则。 使用此标志可生成伪if-then-else构造。 then-子句的最后一条规则变为skip=N，其中N是else-子句中的规则数。 </p> <p> <p>注意： 此标志与“chain|C”标志不同！) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>设置环境变量。 </p> <p>创建设置为值VAL的环境变量“VAR”，其中VAL可以包含扩展的正则表达式返回引用$N和%N。 您可以多次使用此标志设置多个变量。 以后可以通过%{VAR}在以下RewriteCond模式中取消引用变量。 </p> <p>使用此标记可删除和记住URL中的信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>存储重写规则和检索重写规则共享变量值。 由于这种行为，当遇到并存储嵌入式URL时，您可以将变量设置为时间敏感的sessionid值。 当从临时存储列表检索到下一个URL时，可在检索该页面之前向其添加最新的sessionid值。

**具有函数的RewriteRule的示例**

假定您有一台区分大小写的服务器，它处理字符串并且 `"www.mydomain.com"` 不同 `"www.MyDomain.com"` 。 为了使服务器能正常工作，请确保域始终处于正常状态，即使某些文档包含引用此操作的链接 `"www.mydomain.com"``"www.MyDomain.com."` ，您也可以使用以下规则：

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2
```

此重写规则使用函 `tolower` 数重写URL的域部分，以确保它始终为小写，如下所示：

1. “模式” `(^https://([^/]*)(.*)$)` 包含一个反向引 `([^/]*)` 用，它匹配URL中与第一个 `https://` 字符之间 `/` 的所有字符。 该模式还包含与URL中所有其 `(.*)` 余字符相匹配的第二个反向引用。

1. 替代 `(https://${tolower:$1}$2)` 通过使用第一个反向引用上的函数来告知搜索引擎重写URL, `tolower` 而 `(https:// ${tolower:$1}$2)` 保留URL的其余部分不变 `(https://${tolower:$1} $2)`。

因此，表单的URL被重 `https://www.MyDomain.com/INTRO/index.Html` 写为 `https://www.mydomain.com/INTRO/index.Html`。

## 关于RewriteCond指令 {#section_CD5A19B2D3204F73B645411931FC34A1}

RewriteCond指令定义规则条件。 当RewriteCond在RewriteRule之前时，只有在规则的模式与当前标题匹配且附加条件适用时，才使用该规则。 重写条件采用以下形式：

```
           
<i>RewriteCond TestString CondPattern [Flags]</i> 
        
```

`TestString` 是一个字符串，它可以包含以下构造：

纯文本：传递的文本未更改。

Backreferences提供对“图案”或“条纹”的分组部分（内括号）的访问。 以下是两种类型的回溯引用：

* **RewriteRule Backreferences** These match backreferences in the expored RewriteRule Pattern, and the form $N(0 &lt;= N &lt;= 9)。 例如，`RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2`。

* **RewriteCond Backreferences** 这些匹配的RewriteCondPattern中的返回引用，其形式为%N(0&lt;= N &lt;= 9)。

变量：这些是%{NAME_OF_VARIABLE}形式的变量，其中NAME_OF_VARIABLE可以是定义变量名称的字符串。 有关设置变量 *`[E]`* 的详细信息，请参阅RewriteRule标志。

函数：这些函数的形式为${NAME_OF_FUNCTION:key} ，其中NAME_OF_FUNCTION如下所示：

* tolower使所有字符均以小 *写* 。
* toupper使所有字符均以大 *写形式* 。
* escape URL对键中的所有字符进行编码。 字符“a”。z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;...&#39;9&#39;、&#39;*&#39;、&#39;-&#39;、&#39;.&#39;、&#39;/&#39;、&#39;@&#39;和&#39;_&#39;保持不变，空格将转换为&#39;+&#39;，所有其他字符将转换为其 `%xx` URL编码的等效字符。
* unescape将“+”转换回空格，所有 `%xx` URL编码字符都转换回单个字符。

**CondPattern是带有一些附加项的标准扩展正则表达式。** 图案字符串可以前缀有字符( `!` 感叹号)以指定非匹配图案。 您可以使用下列特殊变体之一，而不是实数正则表达式字符串：

>[!NOTE]
>
>您还可以在所有这些测试的前缀上加感叹号(&#39;!&#39;)否定他们的意义。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern字符串 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>词法上更少。 </p> <p> 将CondPattern视为纯字符串，并将其与TestString进行语法比较。 如果TestString词性小于CondPattern，则为true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>词法上更大。 </p> <p> 将CondPattern视为纯字符串，并将其与TestString进行语法比较。 如果TestString词性大于CondPattern，则为true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>词法上相等。 </p> <p> 将CondPattern视为纯字符串，并将其与TestString进行语法比较。 如果TestString在词法上等于CondPattern，即两个字符串完全相等（逐个字符），则为true。 如果CondPattern只是“”（两个引号），则将TestString与空字符串进行比较。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**标记**（可选）将标记括在括号中 `[]`。 多个标志以逗号分隔。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>旗标 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> 没案子。 </p> <p>此标志使测试不区分大小写，即，在扩展的TestString和CondPattern中，“A-Z”和“a-z”之间没有区别。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p>或者下一个条件。 </p> <p>使用此标志将规则条件与本地OR（而不是隐式AND）组合在一起。 如果没有此标志，您必须多次写入第二个／规则。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**示例**

某些网页在访客首次到达站点时分配一个“sessionid” CGI变量。 此变量用于标识访客，并且当访客浏览网站时，该变量会一直传递。 由于搜索自动机看起来就像您网站的访客，因此会为它分配一个“sessionid”编号。 搜索自动机会保留这个“sessionid”值，即使第二个站点页面尝试指定新值也是如此。 要确保这一点，您需要两个重写规则。

第一条规则用于标识和存储sessionid变量：

```
RewriteCond  %{sessionid}  !.+ 
RewriteRule  ^.+sessionid= 
<b>([^&#]+)</b>.*$  -   
<i>[E=sessionid:$1]</i>
```

RewriteRule使用E标志将 `([E=sessionid:$1])` sessionid CGI参数的当前值指定给变量 `sessionid`。 该 `$1` 引用第一反向引用，它包含在RewriteRule的模式中的第一组括号之间 `([^&#]+)`。

正则表达式 `^&#]+` 匹配单词与下一个字符之间的URL `sessionid` 部分的 `**&**or**#**` 内容。 由于此RewriteRule仅用于为sessionid变量创建初始值，因此不会重写。 请注意，规则的“替换”字段设置为 `-` 指示不需要重写。

RewriteCond检查变 `sessionid` 量( `%{sessionid}`)。 如果它连一个字符都没有(!.+)，则匹配RewriteRule。

使用此规则，URL将读取为， `https://www.domain.com/home/?sessionid=1234&function=start` 并为变量 `1234` 赋值 `sessionid`。

第二条规则用于重写所有与以下RewriteRule模式匹配的URL:

```
RewriteRule   
<b>^(.+)</b>sessionid=[^&#]+ 
<i>(.*)$</i>  $1sessionid=%{sessionid}$2
```

RewriteRule模式包含两个反向引用： `(.+)` 和 `(.*)`。 第一个反向引用匹配之前的所有字符 `sessionid`。 第二个反向引用匹配终止或之后的所 `&` 有字符 `#`。

替代模式使用第一个反向引用重写URL，后跟字符串“sessionid=”，后跟由第一个规则定义的会话ID变量的值 `%{sessionid}`，后跟第二个反向引用。 `($1sessionid=%{sessionid} $2)`

请注意，此RewriteRule不包含RewriteCond。 因此，它会导致对与RewriteRule模式匹配的所有URL进行 *重写*。 因此，如果sessionid变量( `%{sessionid}`)的值 `1234`为，则表单的URL将重写 `https://www.domain.com/products/?sessionid=5678&function=buy` 为 `https://www.domain.com/products/?sessionid=1234&function=buy`

## 确认 {#section_B17088EF38244496BC1DDD4ECF75EB5B}

重写引擎软件最初由Apache Group开发，用于Apache HTTP服务器项目(https://www.apache.org/)。

## 添加游动列表存储URL规则 {#task_22DD40DF95584B12BE8E6ECFBF579BCD}

可以添加游动列表存储URL规则，以指定如何重写Web内容中遇到的URL。 您可以指定不限数量的规则和条件，并可以处理所遇到的URL的任何部分。

<!-- 

t_adding_a_crawl_list_store_url_rule.xml

 -->

**添加游动列表存储URL规则**

1. 在产品菜单中，单击 **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Store URL Rules]**。
1. 在字 [!DNL Crawl List Store URL Rules] 段中，输入所需的规则。

   允许以“#”（哈希）字符开头的空行和注释行。
1. （可选）在页 [!DNL Crawl List Store URL Rules] 面的字段中，输 [!DNL Test Crawl List Store URL Rules] 入要测试其游动规则的测试URL，然后单击“测 **试”**。
1. 单击&#x200B;**保存更改**。
1. （可选）如果要预览结果，请重新构建分阶段站点索引。

   请参 [阅配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在页 [!DNL Crawl List Store URL Rules] 面上，执行下列任一操作：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于爬行列表检索URL规则 {#concept_EC8E2E48B99A458D8567B526C9827CBA}

爬网URL规则指定如何重写Web内容中遇到的URL。 您可以指定不限数量的规则和条件，并可以处理所遇到的URL的任何部分。

<!-- 

c_about_crawl_list_retrieve_url_rules.xml

 -->

在客户看到规则的效果之前，请确保重新构建站点索引。

爬行规则对重写URL的动态部分最有用，例如会话标识符对于访问您网站的每个客户都是唯一的。 您还可以使用重写规则从搜索自动机中隐藏URL的某些部分，如查询参数。 默认情况下，不指定规则，也不执行URL重写。

当网站被爬网时，嵌入的内容URL存储在要爬网的其他网页的临时列表中。 当搜索自动机从列表中检索URL时，“检索重写规则”用于操作该URL的部分。 通常，检索规则用于将时间敏感型数据插入URL。 这是最终的URL，用于从您的网站中实际检索页面。

仅当URL包含动态数据（如会话ID）并且该动态数据随时间变化而保持有效时，才需要检索重写规则。 在这种情况下，您使用“商店重写规则”从遇到的URL获取数据的最新状态。 然后，当搜索机器人检索页面时，您可以使用“检索重写规则”将该数据添加到每个URL。

每个规则都使用重写规则(RewriteRule)指令和一个或多个可选的重写条件(RewriteCond)来指定。 规则的顺序很重要。 规则集按规则循环。 当规则匹配时，它循环访问任何相应的重写条件。 按以下方式指定了游动URL规则：

```
RewriteCond TestString CondPattern [Flags] 
RewriteRule Pattern Substitution [Flags]
```

当遇到嵌入的URL时，搜索自动机会尝试将URL与每个爬行规则的模式匹配。 如果模式匹配，重写引擎将查找相应的RewriteCond指令。 如果不存在条件，则URL将替换为从替代字符串构建的新值，并继续执行规则集中的下一个规则。 如果存在条件，则按其列出的顺序处理这些条件。 重写引擎尝试将条件模式(CondPattern)与测试字符串(TestString)匹配。 如果两个匹配项匹配，则会处理下一个条件，直到没有其他条件可用。 如果所有条件都匹配，则URL将替换为规则中指定的替代。 如果条件不满足，则完整的条件集和相应的规则将失败。

## 关于RewriteRule指令 {#section_32B24B29627946398AFBC5F869A610CB}

RewriteRule指令具有以下形式：

```
           
<i>RewriteRule Pattern Substitution [Flags]</i> 
        
```

`Pattern` 可以是POSIX正则表达式，它应用于当前URL。 “当前URL”可能与原始请求的URL不同，因为之前的规则可能已匹配和更改了URL。

请参阅 [正则表达式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

不能使用“not”字符(&#39;!&#39;)在模式前添加前缀。 “not”字符允许您取消模式，即仅当当前URL与此模式不匹配时才为true。 当最好匹配负模式时，可以使用“not”字符，或者作为最终的默认规则。

>[!NOTE]
>
>不能在模式中使用“not”字符和分组通配符。 此外，当替换字符串包含$N时，您不能使用否定的模式。

可以使用括号在图案中创建背向参照，该背向参照可由Substitution和CondPattern引用。

**替换** URL由替换字符串替换，该字符串包含以下内容：

纯文本：传递的文本未更改。

Backreferences提供对“图案”或“条纹”的分组部分（内括号）的访问。 以下是两种类型的回溯引用：

* **RewriteRule Backreferences** These match backreferences in the expored RewriteRule Pattern, the form $N(0 &lt;= N &lt;= 9)。 例如，`RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2.`

* ** RewriteCond Backreferences**这些反向引用与上次匹配的RewriteCondPattern中的反向引用相匹配，并采用%N(0 &lt;= N &lt;= 9)形式。

变量：这些是%{NAME_OF_VARIABLE}形式的变量，其中NAME_OF_VARIABLE是定义变量名称的字符串。 有关设置环 *[境变量的详细信息]* ，请参阅E标志。

函数：这些函数的形式为${NAME_OF_FUNCTION:key} ，其中NAME_OF_FUNCTION如下所示：

* tolower使所有字符均以小 *写* 。
* toupper使所有字符均以大 *写形式* 。
* escape URL对密钥中的所有字符进行 *编码*。
* 字符“a”。z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;...&#39;9&#39;、&#39;*&#39;、&#39;-&#39;、&#39;.&#39;、&#39;/&#39;、&#39;@&#39;和&#39;_&#39;保持不变；空格将转换为“+”，所有其他字符将转换为其%xx URL编码的等效字符。
* unescape将“+”转换回空格，所有%xx URL编码的字符都转换回单个字符。

>[!NOTE]
>
>有一个特殊的替换字符串：&#39;-&#39;表示“不替换”。 “-”字符串通常与C（链）标志一起使用，这样您就可以在发生替换之前将URL与多个模式匹配。

**旗**

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>旗标 </p> </th> 
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
   <td colname="col2"> <p>下一轮。 </p> <p> 使用来自上一重写规则（而非原始URL）的URL重新运行重写过程（从第一重写规则开始）。 注意不要造成死循环。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>用下一条规则链接。 </p> <p>将当前规则链接到下一个规则（也可以将其链接到下一个规则，依此类推）。 如果规则匹配，则替换过程将照常继续。 如果规则不匹配，则跳过所有后续的链式规则。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>没案子。 </p> <p> 使图案不区分大小写（即，当图案与当前URL匹配时，“A-Z”和“a-z”之间没有区别）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>跳过下一个规则。 </p> <p> 如果当前规则匹配，则此标志将强制重写引擎跳过规则集中的下一个num规则。 使用此标志可生成伪if-then-else构造。 then-子句的最后一条规则变为skip=N，其中N是else-子句中的规则数。 </p> <p> <p>注意： 此标志与“chain|C”标志不同！) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>设置环境变量。 </p> <p>创建设置为值VAL的环境变量“VAR”，其中VAL可以包含扩展的正则表达式返回引用$N和%N。 您可以多次使用此标志设置多个变量。 以后可以通过%{VAR}在以下RewriteCond模式中取消引用变量。 </p> <p>使用此标记可删除和记住URL中的信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>存储重写规则和检索重写规则共享变量值。 由于这种行为，当遇到并存储嵌入式URL时，您可以将变量设置为时间敏感的sessionid值。 当从临时存储列表检索到下一个URL时，可在检索该页面之前向其添加最新的sessionid值。

**具有函数的RewriteRule的示例**

假定您有一台区分大小写的服务器，它以不同方式处理字符串“www.mydomain.com”和“www.MyDomain.com”。 为了使服务器能正常工作，请确保域始终为“www.mydomain.com”，即使某些文档包含引用“www.MyDomain.com”的链接也是如此。 为此，您可以使用以下规则：

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2
```

此重写规则使用函 `tolower` 数重写URL的域部分，以确保它始终为小写，如下所示：

1. “模式” `(^https://([^/]*)(.*)$)` 包含一个反向引用** `([^/]*)`**，它匹配URL中介于和第 `https://` 一个之间的所 `/` 有字符。 该模式还包含与URL中所有其 `(.*)` 余字符相匹配的第二个反向引用。
1. 替代 `(https://${tolower:$1}$2)` 通过使用第一个反向引用上的函数来告知搜索引擎重写URL, `tolower` 而 `(https:// ${tolower:$1}$2)` 保留URL的其余部分不变 `(https://${tolower:$1} $2)`。

因此，表单的URL被重 `https://www.MyDomain.com/INTRO/index.Html` 写为 `https://www.mydomain.com/INTRO/index.Html`。

## 关于RewriteCond指令 {#section_ADD642A24B68452CB98294A0BD687EC3}

RewriteCond指令定义规则条件。 当RewriteCond在RewriteRule之前时，只有在规则的模式与当前标题匹配且附加条件适用时，才使用该规则。 重写条件采用以下形式：

```
           
<i>RewriteCond TestString CondPattern [Flags]</i> 
        
```

`TestString` 是一个字符串，它可以包含以下构造：

纯文本：传递的文本未更改。

Backreferences提供对“图案”或“条纹”的分组部分（内括号）的访问。 以下是两种类型的回溯引用：

* **RewriteRule Backreferences** These match backreferences in the expored RewriteRule Pattern, the form $N(0 &lt;= N &lt;= 9)。 例如，`RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2`。

* **RewriteCond Backreferences** 这些匹配的RewriteCondPattern中的返回引用，其形式为%N(0&lt;= N &lt;= 9)。

变量：这些是%{NAME_OF_VARIABLE}形式的变量，其中NAME_OF_VARIABLE可以是定义变量名称的字符串。 有关设置变量 *`[E]`* 的详细信息，请参阅RewriteRule标志。

函数：这些函数的形式为${NAME_OF_FUNCTION:key} ，其中NAME_OF_FUNCTION如下所示：

* tolower使所有字符均以小 *写* 。
* toupper使所有字符均以大 *写形式* 。
* escape URL对键中的所有字符进行编码。 字符“a”。z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;...&#39;9&#39;、&#39;*&#39;、&#39;-&#39;、&#39;.&#39;、&#39;/&#39;、&#39;@&#39;和&#39;_&#39;保持不变，空格将转换为&#39;+&#39;，所有其他字符将转换为其%xx URL编码的等效字符。
* unescape将“+”转换回空格，所有%xx URL编码字符都转换回单个字符。

**CondPattern是带有一些附加项的标准扩展正则表达式。** 模式字符串可以在前缀为“!” 字符（感叹号）指定非匹配模式。 您可以使用以下某个特殊变体，而不是真正的正则表达式字符串：

>[!NOTE]
>
>您还可以在所有这些测试的前缀上加感叹号(&#39;!&#39;)否定他们的意义。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern字符串 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>词法上更少。 </p> <p> 将CondPattern视为纯字符串，并将其与TestString进行语法比较。 如果TestString词性小于CondPattern，则为true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>词法上更大。 </p> <p> 将CondPattern视为纯字符串，并将其与TestString进行语法比较。 如果TestString词性大于CondPattern，则为true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>词法上相等。 </p> <p> 将CondPattern视为纯字符串，并将其与TestString进行语法比较。 如果TestString在词法上等于CondPattern，即两个字符串完全相等（逐个字符），则为true。 如果CondPattern只是“”（两个引号），则将TestString与空字符串进行比较。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**标记**（可选）将标记括在括号中 `[]`。 多个标志以逗号分隔。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>旗标 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> 没案子。 </p> <p>此标志使测试不区分大小写，即，在扩展的TestString和CondPattern中，“A-Z”和“a-z”之间没有区别。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p>或者下一个条件。 </p> <p>使用此标志将规则条件与本地OR（而不是隐式AND）组合在一起。 如果没有此标志，您必须多次写入第二个／规则。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**示例**

某些网页在访客首次到达站点时分配一个“sessionid” CGI变量。 此变量用于标识访客，并且当访客浏览网站时，该变量会一直传递。 由于搜索自动机看起来就像您网站的访客，因此会为它分配一个“sessionid”编号。 搜索自动机会保留这个“sessionid”值，即使第二个站点页面尝试指定新值也是如此。 要确保这一点，您需要两个重写规则。

第一条规则用于标识和存储sessionid变量：

```
RewriteCond  %{sessionid}  !.+ 
RewriteRule  ^.+sessionid= 
<b>([^&#]+)</b>.*$  -   
<i>[E=sessionid:$1]</i>
```

RewriteRule使用E标志将 `([E=sessionid:$1])` sessionid CGI参数的当前值指定给变量 `sessionid`。 该 `$1` 引用第一反向引用，它包含在RewriteRule的模式中的第一组括号之间 `([^&#]+)`。

正则表达式 `^&#]+` 将匹配单词与下一个**&amp; `sessionid` or ****#**字符之间的URL部分。 由于此RewriteRule仅用于为sessionid变量创建初始值，因此不会重写。 请注意，规则的“替换”字段设置为 `-` 指示不需要重写。

RewriteCond检查变 `sessionid` 量( `%{sessionid}`)。 如果它连一个字符都没有(!.+)，则匹配RewriteRule。

使用此规则，URL将读取为， `https://www.domain.com/home/?sessionid=1234&function=start` 并为变量 `1234` 赋值 `sessionid`。

第二条规则用于重写所有与以下RewriteRule模式匹配的URL:

```
RewriteRule   
<b>^(.+)</b>sessionid=[^&#]+ 
<i>(.*)$</i>  $1sessionid=%{sessionid}$2
```

RewriteRule模式包含两个反向引用： `(.+)` 和 `(.*)`。 第一个反向引用匹配之前的所有字符 `sessionid`。 第二个反向引用匹配终止或之后的所 `&` 有字符 `#`。

替代模式使用第一个反向引用重写URL，后跟字符串“sessionid=”，后跟由第一个规则定义的会话ID变量的值 `%{sessionid}`，后跟第二个反向引用。 `($1sessionid=%{sessionid} $2)`

请注意，此RewriteRule不包含RewriteCond。 因此，它会导致对与RewriteRule模式匹配的所有URL进行 *重写*。 因此，如果sessionid变量( `%{sessionid}`)的值 `1234`为，则表单的URL将重写 `https://www.domain.com/products/?sessionid=5678&function=buy` 为 `https://www.domain.com/products/?sessionid=1234&function=buy`

## 确认 {#section_EC3A1DAEB5A54C93A265CB119DF91E9F}

重写引擎软件最初由Apache Group开发，用于Apache HTTP服务器项目(https://www.apache.org/)。

## 添加游动列表检索URL规则 {#task_94A28ED7DC404BFF9767DBB5ADEE6B7A}

可以添加游动列表检索URL规则，以指定如何重写Web内容中遇到的URL。 仅当URL包含动态数据（如会话ID）并且该动态数据随时间变化而保持有效时，才需要检索重写规则。

<!-- 

t_adding_crawl_list_retrieve_url_rules.xml

 -->

**添加游动列表检索URL规则**

1. 在产品菜单中，单击 **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Retrieve URL Rules]**。
1. 在字 [!DNL Crawl List Retrieve URL Rules] 段中，输入所需的规则。

   允许以“#”（哈希）字符开头的空行和注释行。
1. （可选）在页 [!DNL Crawl List Retrieve URL Rules] 面的字段中，输 [!DNL Test Crawl List Retrieve URL Rules] 入要测试其游动规则的测试URL，然后单击“测 **试”**。
1. 单击&#x200B;**保存更改**。
1. （可选）如果要预览结果，请重新构建分阶段站点索引。

   请参 [阅配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在页 [!DNL Crawl List Retrieve URL Rules] 面上，执行下列任一操作：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于爬行标题规则 {#concept_BD3A576987DA4D93A998B0B9CDDC3C79}

爬行标题规则指定在Web内容中遇到的标题存储在搜索索引中之前如何重写它们。

<!-- 

c_about_crawl_title_rules.xml

 -->

例如，您可以使用重写规则删除部分标题，如组织名称。 当网站被爬网时，遇到的标题被存储在临时缓冲区中。 但是，在将标题添加到此缓冲区之前，将对其应用标题规则。 默认情况下，网站搜索／销售没有游动标题规则，并且不会修改标题。

在客户看到规则的效果之前，请重新构建站点索引。

您可以使用“历史记录”功能快速还原对“爬行标题规则”所做的任何更改。

规则可以由两个主要元素组成：rewriteRule和可选的RewriteCond。 您可以指定不限数量的规则和条件。 这些规则的顺序很重要，因为规则集是逐个规则循环的。 当规则匹配时，它循环访问任何（可选）相应的重写条件。 按照以下方式指定游动URL规则：

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

当遇到标题时，搜索自动机会尝试将标题与每个爬行规则的“模式”匹配。 如果模式匹配，重写引擎将查找相应的RewriteCond指令。 如果不存在条件，则URL将替换为从替代字符串构建的新值，并继续执行规则集中的下一个规则。 如果存在条件，则按其列出的顺序处理这些条件。 重写引擎尝试将条件模式(CondPattern)与测试字符串(TestString)匹配。 如果两个匹配项匹配，则会处理下一个条件，直到没有其他条件可用。 如果所有条件都匹配，则URL将替换为规则中指定的替代。 如果条件不满足，则完整的条件集和相应的规则将失败。

在文本框中输入游动URL规则，然后单击保存更改。 允许以“#”（哈希）字符开头的空行和注释行。 要测试搜索规则，可在“测试重写规则”文本框中输入测试URL，然后单击“测试”。

## RewriteRule指令 {#section_669445C505754E838E14029D6583D9B6}

每个RewriteRule指令定义一个重写规则。 规则按其列出的顺序应用。 重写规则采用以下形式：

```
RewriteRule Pattern Substitution [Flags]
```

**模式** 可以是POSIX正则表达式，它应用于当前标题。 “当前标题”与原始标题不同，因为之前的规则已经匹配和更改了它。

请参阅 [正则表达式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

您可以使用“not”字符(&#39;!&#39;)在模式前添加前缀。 “not”字符允许您取消模式，即仅当当前标题与模式不匹配时才为true。 当最好匹配负模式时，可以使用“not”字符，或者作为最终的默认规则。 注意：不能在模式中使用“not”字符和分组通配符。 此外，当替换字符串包含$N时，您不能使用否定的模式。

可使用括号创建背向引用，后向引用可由Substitution和CondPattern引用。

**替换** 标题由替换字符串替换。 该字符串可以包含以下内容：

纯文本——传递的文本未更改。

Backreferences提供对“图案”或“条纹”的分组部分（内括号）的访问。 以下是两种类型的回溯引用：

* RewriteRule Backreferences

   这些匹配相应RewriteRule模式中的反向引用，并采用$N(0 &lt;= N &lt;= 9)形式。 例如，`RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`
* RewriteCond Backreferences

   这些匹配的RewriteCondCondPattern中的反向引用采用%N(0 &lt;= N &lt;= 9)形式。

变量这些是%{NAME_OF_VARIABLE}形式的变量，其中NAME_OF_VARIABLE可以是定义变量名称的字符串。 有关设置环 `[E]` 境变量的更多信息，请参阅标记。

函数这些函数是${NAME_OF_FUNCTION格式的函数：key}，其中NAME_OF_FUNCTION为：

* tolower使所有字符均以小 *写* 。
* toupper使所有字符均以大 *写形式* 。

>[!NOTE]
>
>有一个特殊的替换字符串：&#39;-&#39;表示“不替换”。 “-”字符串通常与C（链）标志一起使用，这允许您在发生替换之前将标题与多个模式匹配。

**标记** （可选）

标记括在括号中， `[]`多个标记以逗号分隔：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>旗标 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>最后一条规则。 </p> <p> 停止重写进程，并且不应用任何其他重写规则。 使用此标志可防止对当前标题进行任何进一步处理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>下一轮。 </p> <p> 使用来自最后重写规则的标题（而不是原始标题）重新运行重写过程（从第一重写规则再次开始）。 小心不要造成死循环。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>用下一条规则链接。 </p> <p>将当前规则链接到下一个规则（也可以将其链接到下一个规则，依此类推）。 如果规则匹配，则替换过程将照常继续。 如果规则不匹配，则跳过所有后续的链式规则。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>没案子。 </p> <p>使图案不区分大小写（即，当图案与当前标题匹配时，“A-Z”和“a-z”之间没有差异）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>跳过下一个规则或规则。 </p> <p> 如果当前规则匹配，则此标志将强制重写引擎跳过规则集中的下一个num规则。 使用它制作伪if-then-else构造。 then-子句的最后一条规则变为skip=N，其中N是else-子句中的规则数。 (注：这与“chain|C”标志不同！) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>设置环境变量。 </p> <p> 创建设置为值VAL的环境变量“VAR”，其中VAL可以包含正则表达式回引，$N和%N，该变量已展开。 您可以多次使用此标志设置多个变量。 以后可以通过%{VAR}在以下RewriteCond模式中引用变量。 使用此标记可删除和记住标题中的信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## RewriteCond指令（可选） {#section_D664B71DE3884E0790531804C49A3222}

RewriteCond指令定义规则条件。 当RewriteCond在RewriteRule之前时，只有在规则的模式与当前标题匹配且附加条件适用时，才使用该规则。

重写条件指令采用以下形式：

```
RewriteCond TestString CondPattern [Flags] 
```

**TestString是一个字符串** ，它可以包含以下构造：

纯文本——传递的文本未更改。

Backreferences提供对“图案”或“条纹”的分组部分（内括号）的访问。 有两种类型的回溯：

* RewriteRule Backreferences这些匹配RewriteRule模式中的反向引用，其形式为$N(0 &lt;= N &lt;= 9)。 例如，`RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`
* RewriteCond Backreferences这些反向引用与上次匹配的RewriteCondPattern中的反向引用相匹配，并采用%N(0 &lt;= N &lt;= 9)形式。

变量这些是%{NAME_OF_VARIABLE}形式的变量，其中NAME_OF_VARIABLE可以是定义变量名称的字符串。 有关设置 `[E]` 环境变量的更多信息，请参阅标记。

函数这些函数是${NAME_OF_FUNCTION:key}形式的函数，其中NAME_OF_FUNCTION为：

* tolower使所有字符均以小 *写* 。
* toupper使所有字符均以大 *写形式* 。
* escape URL对键中的所有字符进行编码。
* 字符“a”。z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;...&#39;9&#39;、&#39;*&#39;、&#39;-&#39;、&#39;.&#39;、&#39;/&#39;、&#39;@&#39;和&#39;_&#39;保持不变，空格将转换为&#39;+&#39;，所有其他字符将转换为其%xx URL编码的等效字符。
* unescape将“+”转换回空格，所有%xx URL编码的字符都转换回单个字符。

**CondPattern是带有一些附加项的标准扩展正则表达式。** 模式字符串可以在前缀为“!” 字符（感叹号）指定非匹配模式。 您可以使用以下某个特殊变体，而不是真正的正则表达式字符串。

>[!NOTE]
>
>您可以在所有这些测试前加感叹号(&#39;!&#39;)否定他们的意义。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern字符串 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>词法上更少。 </p> <p>将 <i>CondPattern</i> 视为纯字符串，并将其与 <i>TestString进行语法比较</i>。 如果 <i>TestString</i> 词法小于 <i>CondPattern，则为true</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>词法上更大。 </p> <p>将 <i>CondPattern</i> 视为纯字符串，并将其与 <i>TestString进行语法比较</i>。 如果 <i>TestString</i> 词性大于 <i>CondPattern</i>，则为true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p> 词法上相等。 </p> <p>将 <i>CondPattern</i> 视为纯字符串，并将其与 <i>TestString进行语法比较</i>。 如果 <i>TestString</i> 在词法上等于 <i>CondPattern</i>，即两个字符串完全相等（逐个字符），则为true。 如 <i>果CondPattern</i> 只是“”（两个引号），则将 <i>TestString</i> 与空字符串进行比较。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**标记** （可选）

标记括在括号中， `[]`多个标记以逗号分隔：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>旗标 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>没案子。 </p> <p> 使测试不敏感。 即，在扩展的 <i>TestString和</i> CondPattern中，“A-Z”和“a-z”之间没有差 <i>异。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p> 或者下一个条件。 </p> <p>使用此标志将规则条件与本地OR（而不是隐式AND）组合在一起。 如果没有此标志，您必须多次写入第二个／规则。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**示例**

假定您拥有一个标准标题格式的公司网站：“My Company”（我的公司）后跟连字符，然后是页面特定的描述（例如，“My Company - Welcome”或“My Company - News”）。 您希望从标题中去除“我的公司-”，并在为站点编制索引时将整个标题转换为大写字母。

以下重写规则使用函数编写器将标题的描述性部分仅重写为大写：

```
RewriteRule  ^My[[:blank:]]Company[[:blank:]]-[[:blank:]] 
<b>(.*)</b>$  ${toupper: 
<b>$1</b>}
```

规则的“模式”包 `(^My[[:blank:]]Company[[:blank:]]-[[:blank:]] (.*))` 含与“我 `(.*)` 的公司-”后面的标题内容相匹配的反向引用。 请记住，带有圆括号()的图案的一部分周围会创建可由替换引用的反向引用。 在此示例中，替换(${topper:**$1**})使用toupper函数重写该回溯引用(**$1**)。

因此，“My Company - Welcome”表单的标题被改写为“WELCOME”。

**确认**

重写引擎软件最初由Apache Group开发，用于Apache HTTP服务器项目(https://www.apache.org/)。

## 添加游动标题规则 {#task_272BB4C603BA4C9ABDBEEB398798B101}

可以添加爬行标题规则，以指定在将Web内容中遇到的标题存储在搜索索引中之前如何重写这些标题。

<!-- 

t_adding_crawl_title_rules.xml

 -->

**添加游动标题规则**

1. 在产品菜单中，单击 **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl Title Rules]**。
1. 在字 [!DNL Crawl Title Rules] 段中，输入所需的规则。

   允许以“#”（哈希）字符开头的空行和注释行。
1. （可选）在页 [!DNL Crawl Title Rules] 面的字段中，输 [!DNL Test Crawl Title Rules] 入要测试其搜索规则的测试URL，然后单击“测 **试”**。
1. 单击&#x200B;**保存更改**。
1. （可选）如果要预览结果，请重新构建分阶段站点索引。

   请参 [阅配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在页 [!DNL Crawl Title Rules] 面上，执行下列任一操作：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于搜索URL规则 {#concept_017EC95E68844B6C8CC9F874F0EC8D3C}

搜索URL规则指定网站搜索结果中URL的显示方式。 这些规则在完整URL上运行。 URL的任何部分都可以处理，包括通常保留会话ID信息的查询参数。

<!-- 

c_about_search_url_rules.xml

 -->

通常，搜索URL规则用于将会话ID插入URL。 但是，您也可以使用搜索URL规则更改随结果一起显示的域名。 默认情况下，不指定规则，也不执行URL修改。

搜索URL规则可以由两个主要元素组成：rewriteRule和可选的RewriteCond。 当URL作为搜索结果的一部分包含在内时，将使用规则对其进行操作。 您可以指定不限数量的搜索URL规则和条件。 这些规则的顺序很重要，因为规则集是按规则循环的。 当规则匹配时，软件会循环访问任何（可选）相应的重写条件。 按照以下方式指定游动URL规则：

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

在处理URL时，站点搜索／销售会尝试将其与每个搜索规则的模式匹配。 如果匹配失败，重写引擎将立即停止处理规则并继续集合中的下一个规则。 如果模式匹配，重写引擎将查找相应的RewriteCond指令。 如果不存在条件，则URL将替换为新值。 该值由替换字符串构造，并与规则集中的下一个规则一起继续。 如果存在条件，则其列出的顺序是处理这些条件的方式。 重写引擎尝试将条件模式(CondPattern)与测试字符串(TestString)匹配。 如果两个匹配项匹配，则会处理下一个条件，直到没有其他条件可用。 如果所有条件都匹配，则URL将替换为规则中指定的替代。 如果条件不满足，则完整的条件集和相应的规则将失败。

## 关于RewriteRule指令 {#section_A3473B5B90B74DA1970213113A90591E}

重写规则采用以下形式：

```
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

**模式** 可以是POSIX正则表达式，它应用于当前URL。 “当前URL”可能与原始URL不同，因为之前的规则可能已经匹配和更改了它。

请参阅 [正则表达式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

您可以使用“not”字符(&#39;!&#39;)在模式前添加前缀。 使用“not”字符可以否定某个模式。 换句话说，仅当当前URL与模式不匹配时，此值才为true。 当最好匹配负模式时，您可以使用“not”字符，或者作为最终的默认规则。 请注意，您不能在模式中同时使用“not”字符和分组通配符。 此外，当替换字符串包含$N时，您不能使用否定的模式。

可使用括号创建背向引用，后向引用可由Substitution和CondPattern引用。

**替换** URL被替换字符串完全替换，该字符串可以包含以下内容：

纯文本——传递的文本未更改。

反向引用提供对“图案”或“条纹”的分组部分（内括号）的访问。 有两种类型的回溯：

RewriteRule Backreferences这些匹配RewriteRule模式中的反向引用，其形式为$N(0 &lt;= N &lt;= 9)。 例如，`RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

RewriteCond Backreferences-这些反向引用与上次匹配的RewriteCondPattern中的反向引用相匹配，并采用%N(0 &lt;= N &lt;= 9)形式。

函数：这些函数的形式为${NAME_OF_FUNCTION:key} ，其中NAME_OF_FUNCTION是：

* tolower使所有字符均以小 *写* 。
* toupper使所有字符均以大 *写形式* 。
* escape URL对密钥中的所有字符进行 *编码*。
* 字符“a”。z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;...&#39;9&#39;、&#39;*&#39;、&#39;-&#39;、&#39;.&#39;、&#39;/&#39;、&#39;@&#39;和&#39;_&#39;保持不变；空格转换为&#39;+&#39;;所有其他字符将转换为其%xx URL编码的等效字符。
* unescape将“+”转换回空格，所有%xx URL编码的字符都转换回单个字符。

>[!NOTE]
>
>有一个特殊的替换字符串：&#39;-&#39;表示“不替换”。 “-”字符串通常与C（链）标志一起使用。 它允许您在进行替换之前将URL与多个模式匹配。

**标记** （可选）

标记括在括号中， `[]`多个标记以逗号分隔：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>旗标 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>最后一条规则。 </p> <p> 停止重写过程，不应用任何附加的重写规则。 使用此标志可阻止对当前URL进行任何进一步处理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p> 下一轮。 </p> <p>使用来自上一重写规则（而非原始URL）的URL，重新运行重写过程（从第一重写规则开始）。 小心不要造成死循环！ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p> 用下一条规则链接。 </p> <p>此标志将当前规则链接到下一个规则，该规则也可以链接到其以下规则，依此类推。 如果规则匹配，则替换过程将照常继续。 如果规则不匹配，则跳过所有后续的链式规则。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>没案子。 </p> <p>此标志使“图案”不区分大小写。 换句话说，当模式与当前URL匹配时，“A-Z”和“a-z”之间没有差异。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>跳过下一个规则或规则。 </p> <p> 如果当前规则匹配，则此标志将强制重写引擎跳过规则集中的下一个num规则。 使用它制作伪if-then-else构造。 then-子句的最后一条规则变为skip=N，其中N是else-子句中的规则数。 (注：这与“chain|C”标志不同！) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>设置环境变量。 </p> <p> 此标志创建设置为值VAL的环境变量“VAR”。 VAL可以包含正则表达式反向引用，$N和%N，它们已展开。 您可以多次使用此标志设置多个变量。 以后可以通过%{VAR}在以下RewriteCond模式中取消引用变量。 使用此标记可删除和记住URL中的信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

请注意，“存储重写规则”和“检索重写规则”共享变量值。 因此，在遇到并存储嵌入式URL时，可以将变量设置为时间敏感的sessionid值。 当从临时存储列表检索到下一个URL时，可在检索该页面之前向其添加最新的sessionid值。

**示例**

假定您有区分大小写的服务器。 它以不同方式处理字符串“www.mydomain.com”和“www.MyDomain.com”。 要使服务器正常工作，您必须确保域始终为“www.mydomain.com”，即使某些文档包含引用“www.MyDomain.com”的链接也是如此。 为此，您可以使用以下规则：

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2 
```

此重写规则使用函数“tolower”重写URL的域部分，以确保它始终为小写：

1. “模式” `(^https://([^/]*)(.*)$)` 包含一个反向引 **`([^/]*)`** 用，它匹配URL中“https://”和第一个“/”之间的所有字符。 该模式还包含第二个反向引 **用(.*)** ，它匹配URL中所有剩余字符。

1. 替代 `(https://${tolower:$1}$2)` 通过使用第一个反向引用上的tolower **(tolower** )函数告知搜索引擎重写URL，而 `(https://**${tolower:$1**}$2)` 不更改URL的其余部分 `(https://${tolower:$1}*$2*)`。

因此，表单的URL将重 `https://www.MyDomain.com/INTRO/index.Html` 写为 `https://www.mydomain.com/INTRO/index.Html`

**RewriteCond指令** （可选）

RewriteCond指令定义规则条件。 当RewriteCond在RewriteRule之前时，只有在规则的模式与当前标题匹配且附加条件适用时，才使用该规则。

重写条件指令采用以下形式：

```
RewriteCond  
<i>TestString CondPattern [Flags]</i>
```

*TestString是一个字符串* ，它可以包含以下构造：

纯文本：传递的文本未更改。

Backreferences提供对“图案”或“条纹”的分组部分（内括号）的访问。 有两种类型的回溯：

* ** RewriteRule Backreferences**这些反向引用在相应的RewriteRule模式中匹配，形式为$N(0 &lt;= N &lt;= 9)。 例如，`RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* **RewriteCond Backreferences** Thes the satched RewriteCondPattern中的这些反向引用与上一个匹配的RewriteCond CondPattern中的反向引用相匹配，其格式为%N(0 &lt;= N &lt;= 9)。

变量这些是%{NAME_OF_VARIABLE}形式的变量，其中NAME_OF_VARIABLE可以是定义变量名称的字符串。 有关设置变量 *`[E]`* 的详细信息，请参阅RewriteRule标志。

>[!NOTE]
>
>重写规则通常使用变量。 来自当前URL的所有CGI参数都会自动变为变量。 例如，搜索URL将自 `"https://search.atomz.com/search/?sp_a=sp00000000&sp_q="Product"&session=1234&id=5678"` 动提供四个变量，这些变量可在重写规则中引用。 在此示例中，一个变量称为“session”，其值为“1234”，而另一个变量称为“id”，其值为“5678”。 (另外两个变量是 `sp_a` 和 `sp_q`。)您应将网页上搜索表单中的所有必需变量作为隐藏字段进行传递。 在此示例中，您应传递“session”和“id”值，它们标识执行搜索的Web站点用户。 要在搜索表单上传递隐藏字段，请使用类似的标记 `<input type=hidden name="session" value="1234">`。

函数这些函数是${NAME_OF_FUNCTION:key}形式的函数，其中NAME_OF_FUNCTION为：

* tolower使所有字符均以小 *写* 。
* toupper使所有字符均以大 *写形式* 。
* escape URL对密钥中的所有字符进行 *编码*。 字符“a”。z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;...&#39;9&#39;、&#39;*&#39;、&#39;-&#39;、&#39;.&#39;、&#39;/&#39;、&#39;@&#39;和&#39;_&#39;保持不变，空格将转换为&#39;+&#39;，所有其他字符将转换为其%xx URL编码的等效字符。
* unescape将“+”转换回空格，所有%xx URL编码字符都转换回单个字符。

**CondPattern是带有一些附加项的标准扩展正则表达式。** 模式字符串可以在前缀为“!” 字符（感叹号）指定非匹配模式。 您可以使用以下某个特殊变体，而不是真正的正则表达式字符串。

您可以使用感叹号(&#39;!&#39;)在所有这些测试前加上前缀否定他们的意义。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern字符串 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>词法上更少。 </p> <p> 将 <i>CondPattern</i> 视为纯字符串，并将其与 <i>TestString进行语法比较</i>。 如果 <i>TestString</i> 词法小于 <i>CondPattern，则为true</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>词法上更大。 </p> <p> 将 <i>CondPattern</i> 视为纯字符串，并将其与 <i>TestString进行语法比较</i>。 如果 <i>TestString</i> 词性大于 <i>CondPattern</i>，则为true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>词法上相等。 </p> <p> 将 <i>CondPattern</i> 视为纯字符串，并将其与 <i>TestString进行语法比较</i>。 如果 <i>TestString</i> 在词法上等于 <i>CondPattern，则为true</i>。 即，两个字符串完全相等（逐个字符）。 如 <i>果CondPattern</i> 只是“”（两个引号），则将 <i>TestString</i> 与空字符串进行比较。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**标记** （可选）

标记括在括号中， `[]`多个标记以逗号分隔：

&#39;nocase|NC&#39;(no case):这使测试不区分大小写。 换句话说，在扩展的 *TestString中和在* CondPattern中，“A-Z”和“a-z”之间没有差 *异*。

&#39;ornext|OR&#39;（或下一个条件）:使用它将规则条件与局部OR（而不是隐式AND）组合在一起。 如果没有此标志，您必须多次写入第二个／规则。

**示例**

某些网页在客户第一次到达站点时分配一个“sessionid” CGI变量。 此变量用于标识客户，并且当客户浏览站点时，该变量会一直传递。 由于搜索机器人看起来就像是您网站的客户，因此会为它分配一个“sessionid”编号。 搜索自动机会保留这个“sessionid”值，即使第二个站点页面尝试指定新值也是如此。 为确保此，您需要以下重写规则：

```
RewriteCond  %{sessionid}  .+ 
RewriteRule  ^ 
<b>(.+)</b>sessionid=[^&#]+ 
<i>(.*)</i>$   
<b>$1</b>sessionid=%{sessionid} 
<i>$2</i>
```

RewriteRule模式包含两个反向引用：(.+) 和 (.*)。第一个反向引用匹配“sessionid=”之前的所有字符。 第二个反向引用匹配会话ID终止“&amp;”或“#”后的所有字符。

替代模式使用第一个反向引用，后跟字符串“sessionid=”，再跟会话ID变量的值（在URL中作为CGI参数传递，后跟第二个反向引用）重写URL。 `($1sessionid=%{sessionid}$2)`.

RewriteCond **检查变量** sessionid `(%{sessionid})`。 如果它至少包含一个字符(.+)，则匹配RewriteRule。

因此，如果搜索查询为 `"https://search.atomz.com/search/?sp_a=sp99999999&sp_q=word&sessionid=5678"`，则将重写所有搜索结果URL，使“sessionid”值为“5678”，而不是搜索机器人在搜索您的站点并保存链接时遇到的“sessionid”值。

**确认**

重写引擎软件最初由Apache Group开发，用于Apache HTTP服务器项目(https://www.apache.org/)。

## 添加搜索URL规则 {#task_50C77D1B53804AEEB20896F74265BD6F}

您可以添加搜索URL规则以指定网站搜索结果中URL的显示方式。 这些规则在完整URL上运行。 您可以操作URL的任何部分，包括经常保留会话ID信息的查询参数。

<!-- 

t_adding_search_url_rules.xml

 -->

**添加搜索URL规则**

1. 在产品菜单中，单击 **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Search URL Rules]**。
1. 在字 [!DNL Search URL Rules] 段中，输入所需的规则。

   允许以“#”（哈希）字符开头的空行和注释行。
1. （可选）在页 [!DNL Search URL Rules] 面的字段中，输 [!DNL Test Search URL Rules] 入要测试其游动规则的测试URL，然后单击“测 **试”**。
1. 单击&#x200B;**保存更改**。
1. （可选）如果要预览结果，请重新构建分阶段站点索引。

   请参 [阅配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在页 [!DNL Search URL Rules] 面上，执行下列任一操作：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于搜索标题规则 {#concept_C72D20F8DFF64EDE809AF4B72797E858}

“搜索标题规则”指定网站搜索结果中标题的显示方式。 标题的任何部分都可以操作。

<!-- 

c_about_search_title_rules.xml

 -->

重写规则可能用于删除标题的一部分，例如组织名称。 默认情况下，网站搜索／销售没有标题规则，也不会修改标题。

标题规则可以由两个主要元素组成：rewriteRule和可选的RewriteCond。 可以指定不限数量的规则和条件。 这些规则的顺序很重要，因为规则集是逐个规则循环的。 当规则匹配时，软件会循环访问任何（可选）相应的重写条件。 搜索标题规则按以下方式指定：

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

遇到标题时，站点搜索／销售会尝试将其与每个爬行规则的“模式”匹配。 如果模式匹配，重写引擎将查找相应的RewriteCond指令。 如果不存在条件，则标题将替换为由替换字符串构建的新值，并继续使用规则集中的下一个规则。 如果存在条件，则按其列出的顺序处理这些条件。 重写引擎尝试将条件模式(CondPattern)与测试字符串(TestString)匹配。 如果两个匹配项匹配，则会处理下一个条件，直到没有其他条件可用。 如果所有条件都匹配，则URL将替换为规则中指定的替代。 如果条件不满足，则完整的条件集和相应的规则将失败。

## RewriteRule指令 {#section_3BF2B0FF89F74A26AE79D68FA3184B9B}

每个RewriteRule指令定义一个重写规则。 规则按其列出的顺序应用。 重写规则采用以下形式：

```
RewriteRule Pattern Substitution [Flags]
```

**模式** A POSIX正则表达式，它应用于当前标题。 “当前标题”可能与原始标题不同，因为之前的规则可能已经匹配和更改了它。

请参阅 [正则表达式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

您可以使用“not”字符(&#39;!&#39;)在模式前添加前缀。 使用“not”字符可以否定某个模式。 即，仅当当前标题与模式不匹配时才为true。 当最好匹配负模式时，可以使用“not”字符，或者作为最终的默认规则。 注意：不能在模式中使用“not”字符和分组通配符。 此外，当替换字符串包含$N时，您不能使用否定的模式。

可以使用括号创建回参照，该回参照可以由Substitution和CondPattern引用。

**替换** “标题”由替换字符串完全替换，该字符串可以包含以下内容：

纯文本——传递的文本未更改。

**反向引用** -提供对“图案”或“条件”(CondPattern)的分组部分（内括号）的访问。 以下是两种类型的回溯引用：

* **RewriteRule Backreferences** These match backreferences in the expored RewriteRule Pattern, the form $N(0 &lt;= N &lt;= 9)。 例如，`RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* ** RewriteCond Backreferences**这些反向引用与上次匹配的RewriteCondPattern中的反向引用相匹配，并采用%N(0 &lt;= N &lt;= 9)形式。

**变量** :%{NAME_OF_VARIABLE}形式的变量，其中NAME_OF_VARIABLE可以是定义变量名称的字符串。 有关设置环 [境变量的详细信息] ，请参阅E标志。 变量也可以在生成搜索结果的搜索表单中定义。

**函数** ，这些函数的形式为${NAME_OF_FUNCTION:key}，其中NAME_OF_FUNCTION为：

* tolower使所有字符均以小 *写* 。
* toupper使所有字符均以大 *写形式* 。

有一个特殊的替换字符串：&#39;-&#39;表示“不替换”。 “-”字符串通常与C（链）标志结合使用，允许您在发生替换之前将标题与多个模式匹配。

**标记** （可选）

标记括在括号中 `[]`，多个标记以逗号分隔：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>旗标 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p> 最后一条规则。 </p> <p> 停止重写过程，不应用任何附加的重写规则。 使用此标志可防止对当前标题进行任何进一步处理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>下一轮。 </p> <p> 使用来自最后重写规则的标题（而非原始标题！）重新运行重写过程（从第一重写规则再次开始）。 小心不要造成死循环。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>用下一条规则链接。 </p> <p> 此标志将当前规则链接到下一个规则（也可以将其链接到其以下规则，等等）。 如果规则匹配，则替换过程将照常继续。 如果规则不匹配，则跳过所有后续的链式规则。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> 没案子。 </p> <p> 此标志使“图案”不区分大小写。 即，当图案与当前标题匹配时，“A-Z”和“a-z”之间没有差异。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p> 跳过下一个规则或规则。 </p> <p> 如果当前规则匹配，则此标志将强制重写引擎跳过规则集中的下一个num规则。 使用它制作伪if-then-else构造。 then-子句的最后一条规则变为skip=N，其中N是else-子句中的规则数。 （这与“chain|C”标志不同！） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>设置环境变量。 </p> <p> 此标志创建一个设置为值VAL的环境变量“VAR”，其中VAL可以包含正则表达式返回引用$N和%N，这将展开。 您可以多次使用此标志设置多个变量。 以后可以通过%{VAR}在以下RewriteCond模式中引用变量。 使用此标记可删除和记住标题中的信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## RewriteCond指令（可选） {#section_9D72B2AB454849A7B681BC39C506AAA3}

RewriteCond指令定义规则条件。 当RewriteCond在RewriteRule之前时，只有在规则的模式与当前标题匹配且附加条件适用时，才使用该规则。

重写条件指令采用以下形式：

```
RewriteCond TestString CondPattern [Flags]
```

**TestString是一个字符串** ，它可以包含以下构造：

纯文本——传递的文本未更改。

Backreferences提供对“图案”或“条纹”的分组部分（内括号）的访问。 有两种类型的回溯：

* **RewriteRule Backreferences** These match backreferences in the expored RewriteRule Pattern, the form $N(0 &lt;= N &lt;= 9)。 例如，`RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* **RewriteCond Backreferences** Thes the satched RewriteCondPattern中的这些反向引用与上一个匹配的RewriteCond CondPattern中的反向引用相匹配，其格式为%N(0 &lt;= N &lt;= 9)。

**变量** :%{NAME_OF_VARIABLE}形式的变量，其中NAME_OF_VARIABLE可以是定义变量名称的字符串。 有关设置环 `[E]` 境变量的更多信息，请参阅标记。 变量也可以在生成搜索结果的搜索表单中定义。

**函数** ，这些函数的形式为${NAME_OF_FUNCTION:key}，其中NAME_OF_FUNCTION为：

* tolower使所有字符均以小 *写* 。
* toupper使所有字符均以大 *写形式* 。
* escape URL对密钥中的所有字符进行 *编码*。
* 字符“a”。z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;...&#39;9&#39;、&#39;*&#39;、&#39;-&#39;、&#39;.&#39;、&#39;/&#39;、&#39;@&#39;和&#39;_&#39;保持不变，空格将转换为&#39;+&#39;，所有其他字符将转换为其%xx URL编码的等效字符。
* unescape将“+”转换回空格，所有%xx URL编码的字符都转换回单个字符。

有一个特殊的替换字符串：&#39;-&#39;表示“不替换”。 “-”字符串通常与C（链）标志结合使用，允许您在发生替换之前将URL与多个模式匹配。

**CondPattern** A standard Extended Regular Expression with some additions. 模式字符串可以在前缀为“!” 字符（感叹号）指定非匹配模式。 您可以使用以下某个特殊变体，而不是真正的正则表达式字符串。

所有这些测试都可以用感叹号(&#39;!&#39;)作为前缀否定他们的意义。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern字符串 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>词法上更少。 </p> <p> 将 <i>CondPattern</i> 视为纯字符串，并将其与 <i>TestString进行语法比较</i>。 如果 <i>TestString</i> 词法小于 <i>CondPattern，则为true</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p> 词法上更大。 </p> <p> 将 <i>CondPattern</i> 视为纯字符串，并将其与 <i>TestString进行语法比较</i>。 如果 <i>TestString</i> 词性大于 <i>CondPattern</i>，则为true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>词法上相等。 </p> <p> 将 <i>CondPattern</i> 视为纯字符串，并将其与 <i>TestString进行语法比较</i>。 如果 <i>TestString</i> 在词法上等于 <i>CondPattern，则为true</i>。 即，两个字符串完全相等（逐个字符）。 如 <i>果CondPattern</i> 只是“”（两个引号），则将 <i>TestString</i> 与空字符串进行比较。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**标记** （可选）

标记括在括号中`[]`，多个标记以逗号分隔：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>旗标 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC'(no case) </p> </td> 
   <td colname="col2"> <p>使测试不敏感。 即，在扩展的 <i>TestString和</i> CondPattern中，“A-Z”和“a-z”之间没有差 <i>异</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR'（或下一个条件） </p> </td> 
   <td colname="col2"> <p> 使用它将规则条件与局部OR（而不是隐式AND）组合在一起。 如果没有此标志，您必须多次写入第二个／规则。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 示例 {#section_E7454FFE169E459AABD9D033651939CB}

假定您拥有一个标准标题格式的公司网站：“My Company”（我的公司）后跟连字符，然后是页面特定的描述（例如，“My Company - Welcome”或“My Company - News”）。 您希望从标题中删除“我的公司-”，并在为站点编制索引时将整个标题转换为大写字母。

以下重写规则使用函数编写器将标题的描述性部分仅重写为大写：

```
RewriteRule  ^My[[:blank:]]Company[[:blank:]]-[[:blank:]] 
<b>(.*)</b>$  ${toupper: 
<b>$1</b>} 
```

规则的“模式”包 `(^My[[:blank:]]Company[[:blank:]]-[[:blank:]] (.*))` 含与“我 **`(.*)`** 的公司-”后面的标题内容相匹配的反向引用。 请记住，带有圆括号()的图案的一部分周围会创建可由替换引用的反向引用。 在此示例中，替换(${topper:**$1**})使用toupper函数重写该回溯引用(**$1**)。

因此，“My Company - Welcome”表单的标题被改写为“WELCOME”。

**确认**

重写引擎软件最初由Apache Group开发，用于Apache HTTP服务器项目(https://www.apache.org/)。

## 添加搜索标题规则 {#task_155CECB74BE3444384EDBBD04F41515E}

您可以添加搜索标题规则以指定如何显示网站搜索结果中的标题。 您可以操作标题的任何部分。

<!-- 

t_adding_search_title_rules.xml

 -->

**添加搜索标题规则**

1. 在产品菜单中，单击 **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Search Title Rules]**。
1. 在字 [!DNL Search Title Rules] 段中，输入所需的规则。

   允许以“#”（哈希）字符开头的空行和注释行。
1. （可选）在页 [!DNL Search Title Rules] 面的字段中，输 [!DNL Test Search Title Rules] 入测试标题，然后单击“测 **试”**。
1. 单击&#x200B;**保存更改**。
1. （可选）如果要预览结果，请重新构建分阶段站点索引。

   请参 [阅配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在页 [!DNL Search Title Rules] 面上，执行下列任一操作：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

