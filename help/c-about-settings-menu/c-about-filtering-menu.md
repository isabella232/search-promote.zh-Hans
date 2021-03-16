---
description: 使用“筛选”菜单可使用在索引Web文档之前更改其内容的脚本。
solution: Target
subtopic: Filtering
title: 关于筛选菜单
topic: 设置、网站搜索和销售
uuid: ebb08fa8-4e17-417d-868b-11fc2af9f284
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '4008'
ht-degree: 1%

---


# 关于筛选菜单{#about-the-filtering-menu}

使用“筛选”菜单可使用在索引Web文档之前更改其内容的脚本。

## 关于筛选脚本{#concept_E56B73D625854AB2A899EF2D56CFCB47}

可以使用[!DNL Filtering Script]更改Web文档的内容，然后再对其进行索引。

您可以插入HTML标记，删除不相关的内容，甚至可以根据文档的URL、MIME类型和现有内容创建新的HTML元数据。 过滤脚本是Perl脚本，它提供强大的字符串处理和常规表达式匹配的灵活性。 将过滤脚本与初始化脚本、终止脚本、URL掩码脚本和测试URL一起使用。

每次从您的网站读取文档时，都会运行筛选脚本。 脚本作为标准过滤器运行。换句话说，从STDIN读取数据，以某种方式转换该数据，并将结果写入STDOUT。 您可以使用过滤脚本将状态消息从过滤脚本打印到索引日志。 您可以将消息打印到STDERR，或通过`_search_debug_log()`子例程打印。

在“分阶段过滤脚本”页的&#x200B;**[!UICONTROL Expert (diff)]**&#x200B;模式下，可以使用的某些GNU差异选项包括：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>GNU差异选项 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -b </span> </p> </td> 
   <td colname="col2"> <p> 忽略空白量的更改。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -B </span> </p> </td> 
   <td colname="col2"> <p> 忽略插入或删除空行的更改。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -c </span> </p> </td> 
   <td colname="col2"> <p> 使用上下文输出格式，显示三行上下文。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -C行  </span> </p> </td> 
   <td colname="col2"> <p> 使用上下文输出格式，显示上下文行（整数），如果未指定行，则显示三行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -i </span> </p> </td> 
   <td colname="col2"> <p> 忽略大小写中的更改；考虑等效的大写和小写字母。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -f  </span> </p> </td> 
   <td colname="col2"> <p> 使输出看起来与编辑脚本相似，但更改了它们在文件中的显示顺序。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -n </span> </p> </td> 
   <td colname="col2"> <p> 输出RCS格式扩散；与<span class="codeph"> -f </span>类似，不同之处在于每个命令指定受影响的行数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>-u </p> </td> 
   <td colname="col2"> <p> 使用统一的输出格式，显示三行上下文。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -U行  </span> </p> </td> 
   <td colname="col2"> <p> 使用统一的输出格式，显示上下文的行（整数），如果未指定行，则使用3。 </p> </td> 
  </tr> 
 </tbody> 
</table>

您可以在这些脚本中使用局部变量、全局变量或同时使用这两个变量。 所有全局变量前面都有命名空间“main:：”。 启动筛选脚本时，其环境包含以下标准文件句柄：

* STDIN — 无内容（读取时立即返回EOF）
* STDOUT — 替换HTML(如果数据打印到STDOUT，则使用它代替原始文档)
* STDERR — 打印到STDERR的数据作为错误打印到索引日志

此外，您还可以使用`_search_debug_log()`子例程将自定义消息写入索引日志，如下例所示：

```
# Log information to the Index Log 
_search_debug_log("Done processing document: " . $main::search_url);
```

这些消息以`DEBUG`字样作为前言显示，不作为错误记录。

以下是一个筛选示例。 网页`<title>`字段通常以公司名称开头。 尽管此信息对于网站导航有用，但在搜索时并不相关。 如果所有MegaCorp网页的标题都开始有一个通用字符串，例如：

```
<title>MegaCorp -- meaningful title 
here</title>
```

您应从每个文档标题的开头删除“ `MegaCorp --`”，并计算使用过滤脚本处理的每个文档。 为此，可使用以下脚本：

```
# Make sure this is an HTML document. 
if ($main::ws_content_type =~ /^text\/html/) { 
    # Read the entire document into a local scalar variable. 
    my @docarray = <>; 
    my $doc = join("", @docarray); 
 
    # Remove "MegaCorp -- " from the title. 
    $doc =~ s/(<TITLE>)MegaCorp -- /$1/gis; 
 
    # Print the resulting document. 
    print $doc; 
 
    # Count that we've filtered one more document. 
    $main::doc_count++; 
}
```

## 全局变量 {#global-variables}

您可以在任何筛选脚本中使用以下变量：

| 变量 | 描述 |
|--- |--- |
| `$main::search_crawl_type` | 值`$main::search_crawl_type`表示正在进行的索引操作的类型。  已弃用表单：`$main::ws_crawl_type`索引操作和相关值包括： <ul><li>完整索引：手动 — `manual`</li><li>完整索引：计划 — `auto`</li><li>完整索引：远程控制 — `CGI`</li><li>增量索引：手动 — `manual-incremental`</li><li>增量索引：计划 — `auto-incremental` </li><li>增量索引：远程控制 — `CGI-incremental`</li><li>脚本索引：手动 — `manual-indexlist.txt` </li><li>脚本索引：计划 — `auto-indexlist.txt`</li><li>脚本索引：远程控制 — `CGI-indexlist.txt`</li><li>重新生成 — `manual-upgrade`</li></ul> |
| `$main::search_clear_cache` | 该值指示是否为当前索引操作请求了“清除索引缓存”索引选项。 如果请求了&quot;清除索引缓存&quot;，则`$main::search_clear_cache`的值为&quot; `1`&quot;。  弃用版本：`$main::ws_clear_cache` |
| `$main::search_fields` | 该值包含在帐户中定义的元数据字段的制表符分隔列表。 默认情况下，值为：   `url title desc keys target body alt date charset language`已弃用的表单：`$main::ws_fields` |
| `$main::search_collections` | 该值包含帐户中定义的收藏集的制表符分隔列表。  弃用版本：`$main::ws_collections` |
| `$main::search_url` | 该值是文档的完全限定URL。  弃用版本：`$main::ws_url` |
| `$main::search_content_type` | 该值是从http-equiv meta标签中获取的文档的内容类型。 典型值是“text/html;charset=iso-8859-1&quot;。  弃用版本：`$main::ws_content_type` |
| `$main::search_content_class` | 该值是文档的内容类，派生自content-type字段。  弃用版本：`$main::ws_content_class` |
| `$main::search_syntax_check` | 该值反映了“检查语法”按钮的使用。 如果单击，则值为1(1);否则，其值为0（零）。  弃用版本：`$main::ws_syntax_check` |
| `$main::search_last_mod_date` | 如果Web服务器提供，则此值包含文档上次修改日期的Epoch表示形式（自1970年1月1日起的秒）。  可以使用Perl localtime()库调用设置此值的格式。 |

### 快速提示{#section_89A5C16911744AF98E232DF608C6A1F5}

* 所有全局变量前面都有命名空间“main:：”：`$main::doc_count = 0;`
* 所有局部变量都使用“my”声明：`my $i = 0;`
* 子例程在初始化脚本中定义。 他们不需要明确的“main:：”命名空间:`sub my_sub {` `...`

   `}`

* 在对文件进行更改之前，请测试`$main::search_content_type`。 测试可以帮助您避免对二进制文件（如SWF文件或PDF文件）做出粗心更改：

   `if ($main::search_content_type =~ /^text\/html/) { ...`

* `$main::search_content_type`是服务器提供的完整Content-Type头。 它有时可包含简单的MIME类型，如“text/html”。 或者，它可以包含MIME类型，后跟其他信息，如文档的字符集编码，如“text/html;charset=iso-8859-1&quot;。
* 对于每种类型的非HTML文档,`$main::search_content_type`可以采用各种值。 测试脚本中的每个值变得麻烦。 例如，某些Word文档的内容类型值为“application/msword”、“application/vnd.ms-word”或“application/x-msword”。 在这种情况下，`$main::search_content_class`可采用以下值：

   * html
   * pdf
   * 词
   * excel
   * powerpoint
   * mp3
   * text

* 在该示例中，测试`$main::search_content_class`的“word”将匹配三个可能的content-type值中的任意一个。
* 如果从筛选脚本中没有将任何内容打印到STDOUT，则文档会完全按下载方式使用。 即，如果您不需要更改文档中的任何内容，则无需将该文档的STDIN复制到STDOUT。
* 如果要从文档中删除所有文本，请打印有效的文件STDOUT。 例如，要从HTML文档中完全删除所有文本，请执行以下操作：`print "<html></html>";`

## 添加筛选脚本{#task_0AB84FD1133F47F9AA069A79BEA13A22}

过滤脚本是一个Perl脚本，它针对从您的网站下载的每个文档运行。

将过滤脚本与初始化脚本、终止脚本和URL掩码脚本结合使用。

请确保重新构建站点索引，以便您的客户能够看到过滤脚本的结果。

请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**添加筛选脚本**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Filtering Script]**。
1. （可选）在[!DNL Filtering Script]页面的[!DNL Test URL]字段中，输入网站上文档的URL。

   单击测试选项可查看对原始HTML文本的更改。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>测试URL字段 </p> </td> 
      <td colname="col2"> <p>允许您在网站上输入文档的URL。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>测试 </p> </td> 
      <td colname="col2"> <p>根据筛选脚本和URL蒙版测试URL。 </p> <p>将下载测试URL文档，然后将其用作过滤脚本的STDIN输入。 然后运行初始化、过滤和终止脚本。 如果筛选脚本中有任何STDOUT输出，则该输出将显示在新的浏览器窗口中。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>仅测试 </p> </td> 
      <td colname="col2"> <p>仅测试脚本的操作。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>预览 </p> </td> 
      <td colname="col2"> <p>允许您视图页面。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>全视 </p> </td> 
      <td colname="col2"> <p>生成文档的完整前后表视图。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>短视 </p> </td> 
      <td colname="col2"> <p>仅显示前后视图之间的差异。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>专家（差异） </p> </td> 
      <td colname="col2"> <p>使用提供的命令行选项显示用于比较文件的GNU diff命令的原始输出。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>筛选脚本 </p> </td> 
      <td colname="col2"> <p>允许您在提供的字段中粘贴过滤脚本。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>保存更改 </p> </td> 
      <td colname="col2"> <p>保存筛选脚本。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>检查语法 </p> </td> 
      <td colname="col2"> <p>允许您通过运行初始化、筛选和终止脚本对脚本执行快速语法检查。 它不会更新并保存您的脚本。 </p> <p>将打印所有Perl编译器错误和警告以及所有STDERR输出。 </p> <p>在客户看到脚本的效果之前，您必须重新构建站点索引。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

   **GNU diff命令行选项**

   在“分阶段过滤脚本”页的&#x200B;**[!UICONTROL Expert (diff)]**&#x200B;模式下，可以使用的某些GNU差异选项包括：

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>GNU diff命令行选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -b  </span> </p> </td> 
      <td colname="col2"> <p> 忽略空白量的更改。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -B  </span> </p> </td> 
      <td colname="col2"> <p> 忽略插入或删除空行的更改。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -c  </span> </p> </td> 
      <td colname="col2"> <p> 使用上下文输出格式，显示三行上下文。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -C行  </span> </p> </td> 
      <td colname="col2"> <p> 使用上下文输出格式，显示上下文行（整数），如果未指定行，则显示三行。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -i  </span> </p> </td> 
      <td colname="col2"> <p> 忽略大小写中的更改；考虑等效的大写和小写字母。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -f  </span> </p> </td> 
      <td colname="col2"> <p> 使输出看起来与编辑脚本相似，但更改了它们在文件中的显示顺序。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -n  </span> </p> </td> 
      <td colname="col2"> <p> 输出RCS格式扩散；与<span class="codeph"> -f </span>类似，不同之处在于每个命令指定受影响的行数。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>-u </p> </td> 
      <td colname="col2"> <p> 使用统一的输出格式，显示三行上下文。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -U行  </span> </p> </td> 
      <td colname="col2"> <p> 使用统一的输出格式，显示上下文的行（整数），如果未指定行，则使用3。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击&#x200B;**[!UICONTROL Test]**&#x200B;以针对筛选脚本和URL掩码进行测试。

   单击&#x200B;**[!UICONTROL Test]**&#x200B;不会更新并保存您的筛选脚本。
1. 在[!DNL Filtering Script]字段中，粘贴您的脚本。
1. （可选）单击&#x200B;**[!UICONTROL Check Syntax]**，通过运行筛选、初始化和终止脚本对脚本执行快速语法检查。

   **[!UICONTROL Check Syntax]** 不更新和保存脚本。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）如果要预览结果，请重新构建分阶段站点索引。

   请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在[!DNL Filtering Script]页面上，执行下列任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于初始化脚本{#concept_048B4C8BC9F74BE8BB6162C490C201A3}

可以使用[!DNL Initialization Script]更改Web文档的内容，然后再对其进行索引。

您可以插入HTML标记，删除不相关的内容，甚至可以根据文档的URL、MIME类型和现有内容创建新的HTML元数据。 初始化脚本是Perl脚本，它提供强大的字符串处理和常规表达式匹配的灵活性。 将初始化脚本与过滤脚本、终止脚本、URL掩码脚本和测试URL一起使用。

初始化脚本在开始索引之前运行一次。 使用此脚本可初始化过滤脚本使用的所有全局变量和子例程。 您可以使用初始化脚本将状态消息从筛选脚本打印到索引日志。 您可以将消息打印到STDERR，或通过`_search_debug_log()`子例程打印。

在“分阶段初始化脚本”页的&#x200B;**[!UICONTROL Expert (diff)]**&#x200B;模式下，可以使用的某些GNU差异选项包括：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>GNU差异选项 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -b  </span> </p> </td> 
   <td colname="col2"> <p> 忽略空白量的更改。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -B  </span> </p> </td> 
   <td colname="col2"> <p> 忽略插入或删除空行的更改。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -c  </span> </p> </td> 
   <td colname="col2"> <p> 使用上下文输出格式，显示三行上下文。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -C行  </span> </p> </td> 
   <td colname="col2"> <p> 使用上下文输出格式，显示上下文行（整数），如果未指定行，则显示三行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -i  </span> </p> </td> 
   <td colname="col2"> <p> 忽略大小写中的更改；考虑等效的大写和小写字母。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -f  </span> </p> </td> 
   <td colname="col2"> <p> 使输出看起来与编辑脚本相似，但更改了它们在文件中的显示顺序。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -n  </span> </p> </td> 
   <td colname="col2"> <p> 输出RCS格式扩散；与<span class="codeph"> -f </span>类似，不同之处在于每个命令指定受影响的行数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>-u </p> </td> 
   <td colname="col2"> <p> 使用统一的输出格式，显示三行上下文。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -U行  </span> </p> </td> 
   <td colname="col2"> <p> 使用统一的输出格式，显示上下文的行（整数），如果未指定行，则使用3。 </p> </td> 
  </tr> 
 </tbody> 
</table>

您可以在这些脚本中使用局部变量、全局变量或同时使用这两个变量。 所有全局变量前面都有命名空间“main:：”。 启动初始化脚本时，其环境包含以下标准文件句柄：

* STDIN — 无内容（读取时立即返回EOF）
* STDOUT — 无内容（如果数据打印到STDOUT，则会丢弃它）
* STDERR — 打印到STDERR的数据作为错误打印到索引日志

此外，您还可以使用`_search_debug_log()`子例程将自定义消息写入索引日志，如下例所示：

```
# Log information to the Index Log 
_search_debug_log("Done processing document: " . $main::search_url);
```

这些消息以`DEBUG`字样作为前言显示，不作为错误记录。

初始化脚本的示例如下：

```
# My subroutine to do something. 
sub my_sub_for_the_filtering_script { 
    my ($param1, $param2) = @_; 
    ... 
} 
 
# Initialize the document counter. 
$main::doc_count = 0;
```

请参阅[全局变量](#global-variables)

### 快速提示{#section_A2CC0302CAF14135BF8EF6171FB184F1}

* 所有全局变量前面都有命名空间“main:：”：`$main::doc_count = 0;`
* 所有局部变量都使用“my”声明：`my $i = 0;`
* 子例程在初始化脚本中定义。 他们不需要明确的“main:：”命名空间:`sub my_sub {` `...`

   `}`

* 在对文件进行更改之前，请测试`$main::search_content_type`。 测试可以帮助您避免对二进制文件（如SWF文件或PDF文件）做出粗心更改：

   `if ($main::search_content_type =~ /^text\/html/) { ...`

* `$main::search_content_type`是服务器提供的完整Content-Type头。 它有时可包含简单的MIME类型，如“text/html”。 或者，它可以包含MIME类型，后跟其他信息，如文档的字符集编码，如“text/html;charset=iso-8859-1&quot;。
* 对于每种类型的非HTML文档,`$main::search_content_type`可以采用各种值。 测试脚本中的每个值变得麻烦。 例如，某些Word文档的内容类型值为“application/msword”、“application/vnd.ms-word”或“application/x-msword”。 在这种情况下，`$main::search_content_class`可采用以下值：

   * html
   * pdf
   * 词
   * excel
   * powerpoint
   * mp3
   * 文本

* 在该示例中，测试`$main::search_content_class`的“word”将匹配三个可能的content-type值中的任意一个。
* 如果从筛选脚本中没有将任何内容打印到STDOUT，则文档会完全按下载方式使用。 即，如果您不需要更改文档中的任何内容，则无需将该文档的STDIN复制到STDOUT。
* 如果要从文档中删除所有文本，请打印有效的文件STDOUT。 例如，要从HTML文档中完全删除所有文本，请执行以下操作：`print "<html></html>";`

## 添加初始化脚本{#task_5A03B8D0C46E4674B7CE88203515803B}

初始化脚本是Perl脚本，在编制任何文档索引之前运行一次。

将初始化脚本与过滤脚本、终止脚本和URL掩码脚本结合使用。

请确保重新构建站点索引，以便您的客户能够看到初始化脚本的结果。

请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**添加初始化脚本**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Initialization Script]**。
1. （可选）在[!DNL Initialization Script]页面的[!DNL Test URL]字段中，输入网站上文档的URL。

   单击测试选项可查看对原始HTML文本的更改。

   请参阅&#x200B;**添加筛选脚本**&#x200B;下的筛选选项表。

   单击&#x200B;**[!UICONTROL Test]**&#x200B;以针对筛选脚本和URL掩码进行测试。

   单击&#x200B;**[!UICONTROL Test]**&#x200B;不会更新并保存您的初始化脚本。
1. 在[!DNL Initialization Script]字段中，粘贴您的脚本。
1. （可选）单击&#x200B;**[!UICONTROL Check Syntax]**，通过运行筛选、初始化和终止脚本对脚本执行快速语法检查。

   **[!UICONTROL Check Syntax]** 不更新和保存脚本。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）如果要预览结果，请重新构建分阶段站点索引。

   请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在[!DNL Initialization Script]页面上，执行下列任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于终止脚本{#concept_AAD6B3B0E7124874AD0947096FC42F47}

可以使用[!DNL Termination Script]更改Web文档的内容，然后再对其进行索引。

您可以插入HTML标记，删除不相关的内容，甚至可以根据文档的URL、MIME类型和现有内容创建新的HTML元数据。 初始化脚本是Perl脚本，它提供强大的字符串处理和常规表达式匹配的灵活性。 将终止脚本与初始化脚本、筛选脚本、终止脚本、URL掩码脚本和测试URL一起使用。

在所有文档编入索引后，终止脚本运行一次。 您可以使用终止脚本将状态消息从过滤脚本打印到索引日志。 您可以将消息打印到STDERR，或通过`_search_debug_log()`子例程打印。

在“分阶段终止脚本”页的&#x200B;**[!UICONTROL Expert (diff)]**&#x200B;模式下，可以使用的某些GNU diff命令行选项包括：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>GNU diff命令行选项 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -b  </span> </p> </td> 
   <td colname="col2"> <p> 忽略空白量的更改。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -B  </span> </p> </td> 
   <td colname="col2"> <p> 忽略插入或删除空行的更改。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -c  </span> </p> </td> 
   <td colname="col2"> <p> 使用上下文输出格式，显示三行上下文。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -C行  </span> </p> </td> 
   <td colname="col2"> <p> 使用上下文输出格式，显示上下文行（整数），如果未指定行，则显示三行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -i  </span> </p> </td> 
   <td colname="col2"> <p> 忽略大小写中的更改；考虑等效的大写和小写字母。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -f  </span> </p> </td> 
   <td colname="col2"> <p> 使输出看起来与编辑脚本相似，但更改了它们在文件中的显示顺序。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -n  </span> </p> </td> 
   <td colname="col2"> <p> 输出RCS格式扩散；与<span class="codeph"> -f </span>类似，不同之处在于每个命令指定受影响的行数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>-u </p> </td> 
   <td colname="col2"> <p> 使用统一的输出格式，显示三行上下文。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -U行  </span> </p> </td> 
   <td colname="col2"> <p> 使用统一的输出格式，显示上下文的行（整数），如果未指定行，则使用3。 </p> </td> 
  </tr> 
 </tbody> 
</table>

您可以在这些脚本中使用局部变量、全局变量或同时使用这两个变量。 所有全局变量前面都有命名空间“main:：”。 启动终止脚本时，其环境包含以下标准文件句柄：

* STDIN — 无内容（读取时立即返回EOF）
* STDOUT — 无内容（如果数据打印到STDOUT，则会丢弃它）
* STDERR — 打印到STDERR的数据作为错误打印到索引日志

此外，您还可以使用`_search_debug_log()`子例程将自定义消息写入索引日志，如下例所示：

```
# Log information to the Index Log 
_search_debug_log("Done processing document: " . $main::search_url);
```

这些消息以`DEBUG`字样作为前言显示，不作为错误记录。

要将筛选脚本处理的文档数作为索引日志中的错误行显示，可以使用以下终止脚本：

```
# Print the value of the document counter. 
print STDERR "Total docs: $main::doc_count\n"; 
# Or, using the log subroutine: 
_search_debug_log("Total docs: " . $main::doc_count);
```

请参阅[全局变量](#global-variables)

### 快速提示{#section_5790EA7ACAC046CBA01F759F88E2460F}

* 所有全局变量前面都有命名空间“main:：”：`$main::doc_count = 0;`
* 所有局部变量都使用“my”声明：`my $i = 0;`
* 子例程在初始化脚本中定义。 他们不需要明确的“main:：”命名空间:`sub my_sub {` `...`

   `}`

* 在对文件进行更改之前，请测试`$main::search_content_type`。 测试可以帮助您避免对二进制文件（如SWF文件或PDF文件）做出粗心更改：

   `if ($main::search_content_type =~ /^text\/html/) { ...`

* `$main::search_content_type`是服务器提供的完整Content-Type头。 它有时可包含简单的MIME类型，如“text/html”。 或者，它可以包含MIME类型，后跟其他信息，如文档的字符集编码，如“text/html;charset=iso-8859-1&quot;。
* 对于每种类型的非HTML文档,`$main::search_content_type`可以采用各种值。 测试脚本中的每个值变得麻烦。 例如，某些Word文档的内容类型值为“application/msword”、“application/vnd.ms-word”或“application/x-msword”。 在这种情况下，`$main::search_content_class`可采用以下值：

   * html
   * pdf
   * 词
   * excel
   * powerpoint
   * mp3
   * 文本

* 在该示例中，测试`$main::search_content_class`的“word”将匹配三个可能的content-type值中的任意一个。
* 如果从筛选脚本中没有将任何内容打印到STDOUT，则文档会完全按下载方式使用。 即，如果您不需要更改文档中的任何内容，则无需将该文档的STDIN复制到STDOUT。
* 如果要从文档中删除所有文本，请打印有效的文件STDOUT。 例如，要从HTML文档中完全删除所有文本，请执行以下操作：`print "<html></html>";`

## 添加终止脚本{#task_F0CFB412871642CFBC88132889C5B6F9}

终止脚本是一个Perl脚本，在所有文档编入索引后运行一次。

将终止脚本与过滤脚本、终止脚本和URL掩码脚本结合使用。

请确保重新构建站点索引，以便您的客户能够看到初始化脚本的结果。

请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**添加终止脚本**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Termination Script]**。
1. （可选）在[!DNL Termination Script]页面的[!DNL Test URL]字段中，输入网站上文档的URL。

   单击测试选项可查看对原始HTML文本的更改。

   请参见&#x200B;**添加筛选脚本**&#x200B;下的筛选选项表。

   单击&#x200B;**[!UICONTROL Test]**&#x200B;以针对筛选脚本和URL掩码进行测试。

   单击&#x200B;**[!UICONTROL Test]**&#x200B;不会更新并保存您的终止脚本。
1. 在[!DNL Termination Script]字段中，粘贴您的脚本。
1. （可选）单击&#x200B;**[!UICONTROL Check Syntax]**，通过运行初始化、筛选和终止脚本来对脚本执行快速语法检查。

   **[!UICONTROL Check Syntax]** 不更新和保存脚本。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）如果要预览结果，请重新构建分阶段站点索引。

   请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在[!DNL Termination Script]页面上，执行下列任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于URL掩码脚本{#concept_384F32EA18F84853A7BA99A04009330B}

通过筛选，您可以在对Web文档的内容编制索引之前对其进行更改。 您可以插入HTML标记，删除不相关的内容，甚至可以根据文档的URL、MIME类型和现有内容创建新的HTML元数据。 URL掩码脚本是Perl脚本，它提供强大的字符串处理和常规表达式匹配的灵活性。

要更改仅存在于网站特定部分中的文档的内容，可以指定包括URL蒙版、排除URL蒙版或同时指定两者，以定义相应的页面。

如果只想更改`"https://www.mysite.com/faqs/"`下的文档，可以使用以下蒙版集：

```
include https://www.mysite.com/faqs/ 
exclude *
```

您还可以在URL掩码脚本中使用常规表达式，如下例所示：

```
include regexp ^https://www\.mysite\.com.*/faqs/.*$ 
exclude *
```

请参阅[常规表达式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

脚本URL蒙版将按照您在[!DNL URL Masks]字段中输入它们的顺序进行考虑。 当文档URL与蒙版匹配时，将根据蒙版类型包含或排除该文档。 如果文档的URL与任何URL掩码不匹配，则仅当其MIME类型为“text/html”时，才包含该文档。 所有其他MIME类型均被排除。

## 添加URL掩码脚本{#task_D18F2A496C1C45C997B5DA650AAF5D59}

指定URL包括蒙版和排除蒙版，以更改仅存在于网站特定部分中的文档内容。

在“URL蒙版”设置的效果对访客可见之前，请重新构建您的站点索引。

**添加URL掩码脚本**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL URL Masks]**。
1. （可选）在[!DNL URL Masks]页面的[!DNL Test URL]字段中，输入网站上某个文档的URL，然后单击&#x200B;**[!UICONTROL Test]**&#x200B;以根据筛选脚本和蒙版测试该URL。

   将下载测试URL文档，它用作过滤脚本的STDIN输入。 然后运行筛选、初始化和终止脚本。 如果筛选脚本中有任何STDOUT输出，则输出将显示在新的浏览器窗口中。

   单击&#x200B;**[!UICONTROL Test]**&#x200B;不会更新并保存脚本。
1. 在[!DNL URL Masks]字段中，每行输入一个URL掩码。
1. （可选）单击&#x200B;**[!UICONTROL Check Syntax]**，通过运行筛选、初始化和终止脚本，对URL掩码执行快速语法检查。

   **[!UICONTROL Check Syntax]** 不更新和保存脚本。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）如果要预览结果，请重新构建分阶段站点索引。

   请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在[!DNL URL Masks]页面上，执行下列任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 关于筛选{#concept_E3EFF4A148EA4D21AFD0A5453A00427E}中的内容类型

允许您选择要为此帐户筛选的内容类型。

在所选内容类型内找到的文本将转换为HTML，然后使用在筛选脚本中指定的脚本进行处理。

请参阅[关于筛选脚本](../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47)。

您可以从中选择的内容类型包括：

* PDF文档
* 文本文档
* AdobeFlash电影
* Microsoft Word文件
* Microsoft Office文件(OpenXML)
* Microsoft Excel文件
* Microsoft Powerpoint文件
* MP3音乐文件中的文本

在“内容类型”设置的效果或对设置所做的更改对客户可见之前，必须重新构建您的站点索引。

## 选择筛选的{#task_C46081FA425A43EC8FDE6EA4A52A170A}内容类型

选择要传递给在筛选脚本中指定的脚本的内容类型。

请参阅[关于筛选脚本](../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47)。

**要选择筛选的内容类型，请执行以下操作**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Content Types]**。
1. 在[!DNL Content Types]页面上，检查要传递到筛选器脚本的内容类型。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）如果要预览结果，请重新构建分阶段站点索引。

   请参阅[配置分阶段网站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可选）在[!DNL Content Types]页面上，执行下列任一操作：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;可还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。
