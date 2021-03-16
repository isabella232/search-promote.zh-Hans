---
description: 有关构造常规表达式的语法和规则的复习。
solution: Target
title: 正则表达式
topic: 附录、网站搜索和销售
uuid: 369b54f6-372a-41de-bb5d-3ae0bd640199
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 1%

---


# 正则表达式{#regular-expressions}

有关构造常规表达式的语法和规则的复习。

另请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**常规表达式的语法**

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>文本</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>任意单个字符 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> [字符] </p> </td> 
   <td colname="col3"> <p> 字符类：字符之一 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> [^chars] </p> </td> 
   <td colname="col3"> <p>字符类：无字符 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> text1|text2 </p> </td> 
   <td colname="col3"> <p> 备选方案：text1或text2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>量词</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> ? </p> </td> 
   <td colname="col3"> <p> 前文的0或1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> * </p> </td> 
   <td colname="col3"> <p> 0或N(N &gt; 1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> + </p> </td> 
   <td colname="col3"> <p>1或N(N &gt; 1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>分组</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> (text) </p> </td> 
   <td colname="col3"> <p> 文本分组，设置替代项的边框，或返回引用，其中N组用在$N的RewriteRule的RHS上) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>锚点</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> ^ </p> </td> 
   <td colname="col3"> <p> 开始行锚点。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> $ </p> </td> 
   <td colname="col3"> <p> 行锚点结尾。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>逃跑</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> </p> </td> 
   <td colname="col2"> <p>\char </p> </td> 
   <td colname="col3"> <p>避开特定的字符。 例如，指定字符“”。[]()"等。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**常规表达式**

* 普通字符（不是下面描述的特殊字符之一）是与自身匹配的单字符常规表达式。
* 反斜杠(\)后跟任何特殊字符是与特殊字符本身匹配的单字符常规表达式。 特殊字符包括：

   * `.` （句点）、 `*` （星号）、 `?` （问号）、 `+` （加号）、 `[` （左方括号）、 `|` （垂直管道）和(反斜 `\` 线)始终是特殊字符，但方括号内显示的字符除外。
   * `^` （尖号或扬抑符）在常规表达式的开头或紧靠两个方括号左侧时特别。
   * `$` （美元符号）在常规表达式的末尾特别。
   * `.` (period)是与任何字符匹配的单字符常规表达式，包括除新行外的补充代码集字符。
   * 包含在`[ ]`（左方括号和右方括号）中的非空字符串是一个字符的常规表达式，它与该字符串中的一个字符（包括补充代码集字符）匹配。

      但是，如果字符串的第一个字符是`^`（扬抑符），则单字符常规表达式符匹配任何字符，包括补充代码集字符，但新行和字符串中的其余字符除外。

      `^`仅在字符串中出现时具有此特殊含义。 可以使用`-`（减号）来指示一系列连续字符，包括补充代码集字符。 例如，[0-9]等效于[0123456789]。

      指定范围的字符必须来自同一代码集。 当字符来自不同的代码集时，将匹配指定范围的字符之一。 如果`-`是在字符串中出现的，则它将失去此特殊含义（在初始`^`之后，如果有）或最后一个。 如果字符串是字符串中的第一个字符，则`]`（右方括号）不终止该字符串（如果有）。 `^`例如，`[]a-f]`与`]`（右方括号）或ASCII字母a至f（含a）匹配。 上面作为特殊字符列出的四个字符代表在这样的字符串中。

**从单字符规则表达式构造规则表达式**

您可以使用以下规则从单字符常规表达式构建常规表达式:

* 单字符常规表达式是与单字符常规表达式匹配的常规表达式。
* 单字符常规表达式后跟`*`（星号）是与单字符常规表达式的零个或多个匹配的常规表达式，该字符可以是补充代码集字符。 如果有任何选择，则选择允许匹配的最左边最长的字符串。
* 单字符常规表达式后跟`?`（问号）是与单字符常规表达式的零个或一个匹配的常规表达式，该字符可以是补充代码集字符。 如果有任何选择，则选择允许匹配的最左边最长的字符串。
* 单字符常规表达式后跟`+`（加号）是与单字符常规表达式的一个或多个匹配的常规表达式，该字符可以是补充代码集字符。 如果有任何选择，则选择允许匹配的最左边最长的字符串。
* 单字符常规表达式，后跟`{m}`、`{m,}`或`{m,n}`是与单字符常规表达式的出现范围相匹配的常规表达式。 m和n的值必须是小于256的非负整数；`{m}`与m个匹配；`{m,}`至少匹配m次；`{m,n}`匹配m和n（含m和n）之间的任意次数。 只要存在选择，常规表达式将匹配尽可能多的匹配项。
* 正则表达式的串联是与正则表达式的每个组件所匹配的字符串的串联相匹配的常规表达式。
* 在字符序列（和）之间包含的常规表达式是与任何未修饰的常规表达式匹配的常规表达式。
* 常规表达式后跟`|`（垂直管道）和常规表达式是与第一常规表达式（垂直管道之前）或第二常规表达式（垂直管道之后）匹配的常规表达式。

您还可以限制常规表达式，使其仅匹配行的初始段或最终段，或同时匹配两者。

* 常规表达式开头的`^`（扬抑符）限制该常规表达式与行的初始段匹配。
* 整个常规表达式末尾的`$`（美元符号）限制该常规表达式与行的最终段匹配。
* 构造^常规表达式$将限制常规表达式以匹配整行。

您可以使用一些预定义的字符类名称来代替复杂括号内的常规表达式。 例如，数字可以由单字符常规表达式[0-9]或由字符类单字符常规表达式[[:digit:]]表示。

预定义的字符类及其含义如下：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>字符类 </p> </th> 
   <th colname="col2" class="entry"> <p>含义 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> [[:alnum:]] </p> </td> 
   <td colname="col2"> <p> 字母字符或数字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:alpha:]] </p> </td> 
   <td colname="col2"> <p>字母字符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:空:]] </p> </td> 
   <td colname="col2"> <p>空格或制表符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:cntrl:]] </p> </td> 
   <td colname="col2"> <p> 控制代码；非打印字符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:dig:]] </p> </td> 
   <td colname="col2"> <p>数字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[：图表：]] </p> </td> 
   <td colname="col2"> <p> 除空格外的任何打印字符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:小写:]] </p> </td> 
   <td colname="col2"> <p>小写字母字符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[：打印：]] </p> </td> 
   <td colname="col2"> <p> 任何打印字符，包括空格。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[：分]] </p> </td> 
   <td colname="col2"> <p> 标点。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:空格:]] </p> </td> 
   <td colname="col2"> <p> 空格，如空格、制表符或行尾。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[：上：]] </p> </td> 
   <td colname="col2"> <p> 大写字母字符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:xdig:]] </p> </td> 
   <td colname="col2"> <p> 十六进制数字，大写或小写。 </p> </td> 
  </tr> 
 </tbody> 
</table>

两个特殊字符类名称匹配单词开始和结尾处的空格。 换句话说，它们与实际字符不匹配。 单词被视为字母字符、数字或下划线(_)的任意序列。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>字符类 </p> </th> 
   <th colname="col2" class="entry"> <p>含义 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> [[:&lt;:]] </p> </td> 
   <td colname="col2"> <p> 开始 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:&gt;:]] </p> </td> 
   <td colname="col2"> <p>词尾 </p> </td> 
  </tr> 
 </tbody> 
</table>

