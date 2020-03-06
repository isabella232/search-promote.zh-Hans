---
description: 有关构造正则表达式的语法和规则的复习。
seo-description: 有关构造正则表达式的语法和规则的复习。
seo-title: 正则表达式
solution: Target
title: 正则表达式
topic: Appendices,Site search and merchandising
uuid: 369b54f6-372a-41de-bb5d-3ae0bd640199
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# 正则表达式{#regular-expressions}

有关构造正则表达式的语法和规则的复习。

另请参 [阅配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**正则表达式的语法**

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
   <td colname="col1"> <p> <b>数量表示符</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> ? </p> </td> 
   <td colname="col3"> <p> 0或1个以上文本 </p> </td> 
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
   <td colname="col3"> <p> 文本分组，设置替代项的边框，或返回引用，其中N组用于RewriteRule的RHS，且$N) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>锚点</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> ^ </p> </td> 
   <td colname="col3"> <p> 行的开头锚点。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> $ </p> </td> 
   <td colname="col3"> <p> 行锚点结束。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>逃生</b> </p> </td> 
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

**正则表达式规则**

* 普通字符（不是下面描述的特殊字符之一）是与自身匹配的单字符正则表达式。
* 反斜杠(\)后跟任何特殊字符是与特殊字符本身匹配的单字符正则表达式。 特殊字符包括：

   * `.` （句点）、 `*` （星号）、 `?` （问号）、 `+` （加号）、 `[` （左方括号）、 `|` （垂直管道）和 `\` （反斜杠）始终是特殊字符，但方括号内显示的字符除外。
   * `^` （尖角或外括号）在正则表达式的开头特殊，或者当它紧跟在一对方括号的左侧时。
   * `$` （美元符号）在正则表达式的结尾处是特殊的。
   * `.` （句点）是与任何字符匹配的单字符正则表达式，包括新行除外的补充代码集字符。
   * 包含在（左方括号和右方括号）中的非空字符串是一个单字符正则表达式，它匹配该字符串中的一个字符，包括补充代码集字符。 `[ ]`

      但是，如果字符串的第一个字符是 `^` (condflex)，则单字符正则表达式将匹配任何字符，包括补充代码集字符，但新行和字符串中的其余字符除外。

      仅当 `^` 字符串中的第一个出现时，才具有此特殊含义。 您可以使 `-` 用（减号）来指示一系列连续字符，包括补充代码集字符。 例如， [0-9] 等于 [0123456789]。

      指定范围的字符必须来自同一个代码集。 当字符来自不同的代码集时，将匹配指定范围的字符之一。 如果 `-` 它是在字符串中出现的第一个(在初始值之后，如 `^`果有)或最后一个，则会丢失此特殊含义。 如果 `]` 字符串是其中第一个字符，则（右方括号）不终止该字符串（如果有），但是它是初始字符 `^`后的第一个字符。 例如， []a-f]匹配 `]` （右方括号）或ASCII字母a至f（含）之一。 上面作为特殊字符列出的四个字符代表在这样的字符串中。

**用单字符正则表达式构造正则表达式的规则**

您可以使用以下规则从单字符正则表达式构建正则表达式：

* 单字符正则表达式是与单字符正则表达式匹配的任意正则表达式。
* 单字符正则表达式后跟 `*` （星号）是与单字符正则表达式的零个或多个出现匹配的正则表达式，该正则表达式可以是补充代码集字符。 如果有任何选择，则选择允许匹配的最左边的最长字符串。
* 单字符正则表达式后跟 `?` （问号）是与单字符正则表达式的零或一个匹配的正则表达式，该正则表达式可以是补充代码集字符。 如果有任何选择，则选择允许匹配的最左边的最长字符串。
* 单字符正则表达式后跟 `+` （加号）是与单字符正则表达式的一个或多个实例相匹配的正则表达式，该单字符正则表达式可以是补充代码集字符。 如果有任何选择，则选择允许匹配的最左边的最长字符串。
* 单字符正则表达式后跟 `{m}`、 `{m,}`或 `{m,n}` 是与单字符正则表达式的出现范围相匹配的正则表达式。 m和n的值必须为小于256的非负整数；匹 `{m}` 配m个匹配项；匹 `{m,}` 配至少m次；匹 `{m,n}` 配m和n（含m和n）之间的任意次数。 只要存在选择，正则表达式就匹配尽可能多的实例。
* 正则表达式的连接是一个正则表达式，它与正则表达式的每个组件所匹配的字符串的连接相匹配。
* 包含在字符序列（和）之间的正则表达式是与无点的正则表达式匹配的任何正则表达式。
* 正则表达式后跟 `|` （垂直管道）和正则表达式是与第一正则表达式（垂直管道之前）或第二正则表达式（垂直管道之后）匹配的正则表达式。

您还可以限制正则表达式仅匹配行的初始段或最终段，或两者。

* 正 `^` 则表达式开头的(condiflex)限制该正则表达式与行的初始段匹配。
* 整 `$` 个正则表达式末尾的（美元符号）限制该正则表达式匹配行的最终段。
* 构造“正则表达式$”限制正则表达式匹配整行。

有一些预定义的字符类名称，可用来代替复杂的带括号的正则表达式。 例如，数字可以由单字符正则表达式 [0-9] ，或由字符类单字符正则表达式[[:digit:]]表示。

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
   <td colname="col1"> <p> [[:graph:]] </p> </td> 
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
   <td colname="col1"> <p> [[:punct:]] </p> </td> 
   <td colname="col2"> <p> 标点。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:空格:]] </p> </td> 
   <td colname="col2"> <p> 空白，如空格、制表符或行尾。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:upper:]] </p> </td> 
   <td colname="col2"> <p> 大写字母字符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:xdigit:]] </p> </td> 
   <td colname="col2"> <p> 十六进制数字，大写或小写。 </p> </td> 
  </tr> 
 </tbody> 
</table>

两个特殊字符类名称与单词开头和结尾处的空格相匹配。 换句话说，它们与实际字符不匹配。 单词被视为字母字符、数字或下划线(_)的任意序列。

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
   <td colname="col2"> <p> 一个字的开头 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:&gt;:]] </p> </td> 
   <td colname="col2"> <p>一个字结尾 </p> </td> 
  </tr> 
 </tbody> 
</table>

