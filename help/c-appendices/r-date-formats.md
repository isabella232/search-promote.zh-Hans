---
description: 您可以定义在分析任何数据类型为“日期”字段并为其编制索引时使用的日期格式。
seo-description: 您可以定义在分析任何数据类型为“日期”字段并为其编制索引时使用的日期格式。
seo-title: 日期格式
solution: Target
title: 日期格式
topic: Appendices,Site search and merchandising
uuid: 148914b5-33ef-41db-8404-67c03f6f0832
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# 日期格式{#date-formats}

您可以定义在分析任何数据类型为“日期”字段并为其编制索引时使用的日期格式。

日期和时间的格式使用格式字符串指定。 格式字符串由零个或多个转换规范（转换规范由百分号和其他字符组成）和普通字符组成。 提供了每个日期字段的日期格式字符串的默认列表。

您可以完全控制此列表，并可以添加或修改该列表以满足站点的需要。 顶级格式字符串优先，并且仅当解析给定元数据标签的内容产生错误时才使用后续格式字符串。

例如，假定您指定了以下日期格式：

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%B %d,%Y %T %Z </p> <p>%b %d,%Y %T %Z </p> <p>%A %B %d,%Y %T %Z </p> <p>%A %b %d,%Y %T %Z </p> <p>%a %B %d,%Y %T %Z </p> <p>%a %b %d,%Y %T %Z </p> <p>%d %b %Y %T %Z </p> </td> 
  </tr> 
 </tbody> 
</table>

第一种格式为&quot;%B %d,%Y %T %Z&quot;，与类似于以下&quot;2014年9月20日13:12:00 PDT&quot;的日期匹配。 如果无法使用此格式字符串分析元数据标记内容，则尝试使用下一个可用格式&quot;%b %d,%Y %T %Z&quot;。 此格式与以下日期相匹配：“2014年9月20日太平洋夏令时3:12:00”。 如果无法使用此格式字符串分析元数据标记内容，则站点搜索／销售会在格式字符串列表中下移，直到找到有效的格式字符串。

下表描述了可用的日期格式字符串：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>数据格式 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%同类群组 </p> </td> 
   <td colname="col2"> <p>匹配完整工作日名称的国家代表，例如“星期一”。 国家代表性由"单词和语言"选项的"语言"设置决定 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a </p> </td> 
   <td colname="col2"> <p> 匹配缩写工作日名称的国家代表，其中缩写是前三个字符，例如“亲爱的。” 国家代表性由"单词和语言"选项的"语言"设置决定 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%B </p> </td> 
   <td colname="col2"> <p> 匹配全月名称的国家代表，例如“6月。” 国家代表性由"单词和语言"选项的"语言"设置决定 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%b </p> </td> 
   <td colname="col2"> <p> 匹配缩写月份名称的国家代表，其中缩写是前三个字符，例如“6月。” 国家代表性由"单词和语言"选项的"语言"设置决定 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%D </p> </td> 
   <td colname="col2"> <p> 等效于"%m/%d/%y"，例如"06/06/01" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%d </p> </td> 
   <td colname="col2"> <p> 将月份的某天作为小数(01-31) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%e </p> </td> 
   <td colname="col2"> <p> 将月份的某天作为小数(1-31);单位数字前面有空白 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%H </p> </td> 
   <td colname="col2"> <p> 将小时（24小时制）与小数(00-23)匹配 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%h </p> </td> 
   <td colname="col2"> <p> 匹配缩写月份名称的国家代表，其中缩写是前三个字符，例如“Jun”（与%b相同） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%I </p> </td> 
   <td colname="col2"> <p> 将小时（12小时制）与小数(01-12)匹配 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%j </p> </td> 
   <td colname="col2"> <p> 将一年中的某天作为小数(001-366) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%k </p> </td> 
   <td colname="col2"> <p> 将小时（24小时时钟）与小数(0-23)相匹配；单位数字前面有空白 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%l </p> </td> 
   <td colname="col2"> <p> 将小时（12小时钟）作为小数(1-12);单位数字前面有空白 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%M </p> </td> 
   <td colname="col2"> <p> 将分钟数与小数(00-59)相匹配 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%m </p> </td> 
   <td colname="col2"> <p> 将月份与小数(01-12)匹配 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%p </p> </td> 
   <td colname="col2"> <p> 与“ante meridiem”或“post meridiem”的国家代表(如“下午。” 国家代表性由"单词和语言"选项的"语言"设置决定 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%R </p> </td> 
   <td colname="col2"> <p> 等效于“%H:%M”，例如《13:23》 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%r </p> </td> 
   <td colname="col2"> <p> 等效于"%I:%M:%S %p"，例如"下午01:23:45" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%S </p> </td> 
   <td colname="col2"> <p> 将第二个数字与十进制数字相匹配(00-60) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%T </p> </td> 
   <td colname="col2"> <p> 等效于"%H:%M:%S"，例如《13:26:47》 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%U </p> </td> 
   <td colname="col2"> <p> 将年份的周数（星期日作为周的第一天）与小数(00-53)匹配 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%v </p> </td> 
   <td colname="col2"> <p> 等效于"%e-%b-%Y"，例如《2001年6月6日》 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Y </p> </td> 
   <td colname="col2"> <p> 将年份与世纪作为十进制数，例如《2001年》 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%y </p> </td> 
   <td colname="col2"> <p> 将没有世纪的年份作为小数(00-99)匹配 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Z </p> </td> 
   <td colname="col2"> <p> 与时区名称匹配 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%% </p> </td> 
   <td colname="col2"> <p> matches "%" </p> </td> 
  </tr> 
 </tbody> 
</table>

**默认格式字符串**

模板使用以下默认格式字符串。 您可以添加到此列表，或根据需要编辑它。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>默认格式字符串 </p> </th> 
   <th colname="col2" class="entry"> <p>结果示例 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%B %d,%Y %T %Z </p> </td> 
   <td colname="col2"> <p> 1999年9月5日太平洋夏令时13时12分0秒 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%b %d,%Y %T %Z </p> </td> 
   <td colname="col2"> <p> 1999年9月5日太平洋夏令时13:12:00 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%A %B %d,%Y %T %Z </p> </td> 
   <td colname="col2"> <p> 星期日1999年9月5日太平洋夏令时13时12分00秒 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%A %b %d,%Y %T %Z </p> </td> 
   <td colname="col2"> <p> 1999年9月5日星期日太平洋夏令时13时12分00秒 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a %B %d,%Y %T %Z </p> </td> 
   <td colname="col2"> <p> 1999年9月5日太平洋夏令时13时12分 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a %b %d,%Y %T %Z </p> </td> 
   <td colname="col2"> <p> 1999年9月5日太平洋夏令时13:12:00 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%d %b %Y %T %Z </p> </td> 
   <td colname="col2"> <p> 1999年9月5日太平洋夏令时13:12:00 </p> </td> 
  </tr> 
 </tbody> 
</table>
