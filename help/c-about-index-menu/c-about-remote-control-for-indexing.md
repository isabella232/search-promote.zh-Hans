---
description: 只要您的网站发生更改，您就可以运行脚本或项目，请求搜索自动机使用远程控制运行索引。
solution: Target
title: 关于用于索引的远程控制
topic-legacy: Index,Site search and merchandising
uuid: 20e230c6-5c1a-4bf4-bff3-b8236d14ab21
exl-id: 1a7689f9-1e3f-48c8-a5f1-abe0efdb7768
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '1037'
ht-degree: 1%

---

# 关于索引{#about-remote-control-for-indexing}的远程控制

只要您的网站发生更改，您就可以运行脚本或项目，请求搜索自动机使用远程控制运行索引。

## 使用远程控件对{#concept_C79B322190E84106A434E5C6D4A4118F}进行索引

远程控制索引请求通常来自位于您服务器上的脚本或项目。

该机器人执行的索引步骤与从[!DNL Index]菜单手动启动的步骤相同。 要提交远程控制请求，请配置必要的密码和响应字符串。

## 如何发出远程控制请求{#section_42FAB2BAB25A4E24BEA69566C6D1C70F}

要发出远程控制请求，请根据数据中心位置使用以下格式示例：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>数据中心位置 </p> </th> 
   <th colname="col2" class="entry"> <p>示例 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>伦敦 </p> </td> 
   <td colname="col2"> <p> <code> https://center.lon5.atomz.com/search/cgiindex.tk? <b>sp_a=sp99999999&amp;sp_password=xxxxxx&amp;sp_operation=op</b> </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>北美洲 </p> </td> 
   <td colname="col2"> <p> <code> https://center.atomz.com/search/cgiindex.tk? <b>sp_a=sp99999999&amp;sp_password=xxxxxx&amp;sp_operation=op</b> </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>新加坡 </p> </td> 
   <td colname="col2"> <p> <code> https://center.sin2.atomz.com/search/cgiindex.tk? <b>sp_a=sp99999999&amp;sp_password=xxxxxx&amp;sp_operation=op</b> </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

或

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>字符串和值 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_a=sp99999999  </span> </p> </td> 
   <td colname="col2"> <p> 您的帐号。 </p> <p>您可以在<span class="uicontrol"> <b>Settings</b> </span> &gt; <span class="uicontrol"> <b>Account Options</b> </span> &gt; <span class="uicontrol"> <b>Account Settings</b> </span>下找到您的帐户号。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_lines= N  </span> </p> </td> 
   <td colname="col2"> <p>允许您检查正在运行的索引爬网的状态。 </p> <p> <span class="codeph">  N </span> 是正整数或全 <span class="codeph"> 部 </span>。如果这是数值，则JSON响应中将包括相应索引日志文件的最后一行<span class="codeph"> N </span>行。 </p> <p>如果值为<span class="codeph">所有</span>，则返回整个文件。 </p> <p>如果值为<span class="codeph"> 0 </span>，则不返回日志信息。 此值是运行索引状态查询的默认值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_operation= op  </span> </p> </td> 
   <td colname="col2"> <p>允许您指定要运行的以下索引操作之一： </p> <p> 
     <ul id="ul_6CA190AC41694BC293FC7C6BABA629FE"> 
      <li id="li_EFC76E31D47E473F9A56B2EBA8A97CA1"> <span class="codeph"> full_index  </span> <p>搜索机器人会运行您网站的完整索引。 </p> </li> 
      <li id="li_A9ACE21718804A21B3DA7B84AB6729D3"> <span class="codeph"> incremental_index  </span> <p>搜索机器人使用在<span class="uicontrol"><b>Index</b> </span> &gt; <span class="uicontrol"> <b></b> </span> &gt; <span class="uicontrol"> <b>Configuration</b></span>下设置的配置运行增量索引。 </p> </li> 
      <li id="li_722FE409AE454AD48ACE95C4CDC7A00B"> <span class="codeph"> vertical_index  </span> <p>该搜索机器人使用在<span class="uicontrol"><b>Index</b> </span> &gt; <span class="uicontrol"> <b></b> </span> &gt; <span class="uicontrol"> <b>Configuration</b></span>下设置的配置运行垂直更新。 </p> <p>请参阅<a href="../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local">关于垂直更新</a>。 </p> </li> 
      <li id="li_A40B513CE17043A4925CE3D4DE0B48A4"> <span class="codeph"> script_index  </span> <p>该搜索机器人使用在<span class="uicontrol"><b>Index</b> </span> &gt; <span class="uicontrol"> <b>脚本索引</b> </span> &gt; <span class="uicontrol"> <b>Configuration</b></span>下指定的文本文件运行增量索引。 </p> </li> 
      <li id="li_A0BC7F1373B14393997BAB7690FD3EF7"> <span class="codeph"> full_staged_index  </span> <p>搜索自动机运行网站的完整分阶段索引。 </p> </li> 
      <li id="li_47753E358457443A95B384A278FACA83"> <span class="codeph"> incremental_staged_index  </span> <p>该搜索机器人使用在<span class="uicontrol"><b>Index</b> </span> &gt; <span class="uicontrol"> <b>Incremental Index</b> </span> &gt; <span class="uicontrol"> <b>Configuration</b></span>下设置的配置来运行增量分级索引。 </p> </li> 
      <li id="li_C8B5F8F1208E438ABEFDF9129A6B14A3"> <span class="codeph"> vertical_staged_index  </span> <p>该搜索机器人使用在<span class="uicontrol"><b>Index</b> </span> &gt; <span class="uicontrol"> <b> Vertical Update</b> </span> &gt; <span class="uicontrol"> <b>Configuration</b></span>下设置的配置来运行垂直分级更新。 </p> </li> 
     </ul> </p> <p>注意： 要使用垂直更新，您可能需要由Adobe帐户代表或Adobe支持在您的帐户中启用它。 </p> <p>请参阅<a href="../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local">关于垂直更新</a>。 </p> <p>您可以将<span class="codeph">_saved </span>附加到以上任何<span class="codeph"> sp_operation </span>值，以让搜索自动机尝试使用已保存的内容。 例如，您可以指定以下内容： </p> <p> <code class="syntax html"> sp_operation=full_index_saved </code> </p> <p>或 </p> <p> <code class="syntax html"> sp_operation=full_staged_index_saved </code> </p> <p>或者，可以将<span class="codeph"> _status </span>附加到以上任何<span class="codeph"> sp_operation </span>值，以请求当前或最近操作的状态报告。 例如，您可以指定以下内容： </p> <p> <code class="syntax html"> sp_operation=full_index_status </code> </p> <p>或 </p> <p> <code class="syntax html"> sp_operation=full_staged_index_status </code> </p> <p>结果将作为JSON对象返回。 包括<span class="codeph"> sp_lines=N </span>以包括关联日志文件的N行。 如果N为负，则包括最后N行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_operation= pushlive  </span> </p> </td> 
   <td colname="col2"> <p> 允许您远程推送分阶段索引。 </p> <p>忽略将<span class="codeph">_saved </span>追加到推送实时操作的任何尝试。 </p> <p>运行<span class="codeph"> pushlive </span>操作时，OK、Priority或Error响应文本字符串将返回到服务器。 在<span class="wintitle">远程控制</span>页面上指定这些响应字符串。 </p> <p>请参阅<a href="../c-about-index-menu/c-about-remote-control-for-indexing.md#task_57C296258404448DA7A5ADC9B7232391" format="dita" scope="local">配置远程控制以建立索引</a>。 </p> <p>如果在没有分阶索引时实时推送，则不会发生任何情况，并返回“确定”响应字符串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_password= xxxxxx  </span> </p> </td> 
   <td colname="col2"> <p>遥控密码。 </p> </td> 
  </tr> 
 </tbody> 
</table>

搜索以适当的HTTP响应形式返回数据。 完整响应由HTTP状态、HTTP响应头、空行和响应字符串组成。

例如，假定您执行以下远程控制请求：

```
https://center.atomz.com/search/cgiindex.tk?sp_a=sp99999999&sp_password=my-password&sp_operation=full_index
```

以下是服务器的响应：

```
Status: 200 OK 
Content-type: text/plain 
OK
```

或者，假设您执行以下远程控制状态请求：

```
https://center.atomz.com/search/cgiindex.tk?sp_a=sp99999999&sp_password=my-password&sp_operation=full_index_status
```

来自服务器的响应可能如下所示：

```
Status: 200 OK 
Content-type: application/json; charset=utf-8 
{ 
    "current_time": "2017-08-27T10:58:58-0700", 
    "start_time": "2017-07-25T16:40:07-0800", 
    "end_time": "2017-07-25T16:40:20-0800", 
    "elapsed_seconds": 13, 
    "elapsed_seconds_fmt": "13s", 
    "state": "finished", 
    "docs_indexed": 3, 
    "depth": 0, 
    "errors": 0, 
    "status": 1, 
    "message": "ok" 
}
```

要获取与此索引操作关联的日志列表的前十行及其状态，使用以下查询:

```
https://center.atomz.com/search/cgiindex.tk?sp_a=sp99999999&sp_password=my-password&sp_operation=full_index_status&sp_lines=10
```

来自服务器的响应：

```
Status: 200 OK 
Content-type: application/json; charset=utf-8 
{ 
    "current_time": "2017-08-27T10:59:30-0700", 
    "start_time": "2017-07-25T16:40:07-0800", 
    "end_time": "2017-07-25T16:40:20-0800", 
    "elapsed_seconds": 13, 
    "elapsed_seconds_fmt": "13s", 
    "state": "finished", 
    "docs_indexed": 3, 
    "depth": 0, 
    "errors": 0, 
    "offset": 672, 
    "lines": [ 
        "07/25 16:40:07 PST   ======== Starting manual crawl of account sp99999999. ========", 
        "07/25 16:40:08 PST   Loading existing data", 
        "07/25 16:40:08 PST   Downloading entrypoint https://www.atomz.com/", 
        "07/25 16:40:08 PST   Robots.txt exclude mask: https://www.atomz.com/snap", 
        "07/25 16:40:08 PST   Exclude mask: regexp ^https://www.atomz.com/$", 
        "07/25 16:40:08 PST   Include mask: https://www.atomz.com/", 
        "07/25 16:40:08 PST   Downloading https://www.atomz.com/style.css", 
        "07/25 16:40:09 PST   Ignoring https://www.atomz.com/style.css, document type 'text/css'.", 
        "07/25 16:40:09 PST   Downloading https://www.atomz.com/privacy.html", 
        "07/25 16:40:09 PST   Downloading https://www.atomz.com/terms.html" 
    ], 
    "status": 1, 
    "message": "ok" 
}
```

记下`offset`值。 此值标识日志文件中读取中断时的文件偏移位置。 要读取文件中的&#x200B;*下一行*&#x200B;十行，您应在发送到服务器的请求中包括`&sp_offset=672`。

使用`sp_offset`，您可以有效地翻阅日志文件。

要获取日志的&#x200B;*最后*&#x200B;十行以及状态，请将计数指定为负数。 例如，指定`sp_lines=`，其值为`-10`，如下所示：

```
https://center.atomz.com/search/cgiindex.tk?sp_a=sp99999999&sp_password=my-password&sp_operation=full_index_status&sp_lines=-10
```

来自服务器的响应：

```
Status: 200 OK 
Content-type: application/json; charset=utf-8 
{ 
    "current_time": "2017-08-27T11:01:14-0700", 
    "start_time": "2017-07-25T16:40:07-0800", 
    "end_time": "2017-07-25T16:40:20-0800", 
    "elapsed_seconds": 13, 
    "elapsed_seconds_fmt": "13s", 
    "state": "finished", 
    "docs_indexed": 3, 
    "depth": 0, 
    "errors": 0, 
    "lines": [ 
        "07/25 16:40:20 PST   End Time: 07/25/2017 16:40:20 PST", 
        "07/25 16:40:20 PST   Elapsed Time: 13 seconds", 
        "07/25 16:40:20 PST   Pages Crawled: 3 pages", 
        "07/25 16:40:20 PST   Pages Indexed: 3 pages", 
        "07/25 16:40:20 PST   Words/Bytes Indexed: 2373 words/ 20618 bytes", 
        "07/25 16:40:20 PST   Errors: 0", 
        "07/25 16:40:20 PST   *** Index Summary ***", 
        "07/25 16:40:20 PST   Total Pages: 3", 
        "07/25 16:40:20 PST   --------------------------------------------------------------------", 
        "07/25 16:40:20 PST   ======== Finish manual crawl of account sp99999999: Done. ========" 
    ], 
    "status": 1, 
    "message": "ok" 
}
```

请注意，此处没有返回任何`offset`值，因为此操作在文件末尾完成，并且没有其他行可供读取。

## 为索引{#task_57C296258404448DA7A5ADC9B7232391}配置远程控制

只要您的网站发生更改，您就可以使用远程控制从您的服务器运行脚本或项目，请求搜索自动机运行索引。

**为索引配置远程控制**

1. 在产品菜单上，单击&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Remote Control]**。
1. 在[!DNL Remote Control]页面上，设置每个配置字段选项，以便能够自动提交来自服务器的索引请求以索引您的网站。

   <table> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> <p>选项 </p> </th> 
    <th colname="col2" class="entry"> <p>描述 </p> </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>远程控制密码 </p> </td> 
    <td colname="col2"> <p>指定远程控制密码。 </p> <p> 密码区分大小写，长度至少为六个字符，并且必须至少包含一个字母。 建议您还至少包含一个数字。 </p> <p>请勿使用网站搜索/促销登录密码。 </p> <p>您的密码将用于每个远程控制请求。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>确定响应字符串 </p> </td> 
    <td colname="col2"> <p>允许您指定OK响应文本字符串（如果请求的索引操作成功开始）。 在这种情况下，搜索自动机会将您的OK响应字符串返回到服务器。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>优先级响应字符串 </p> </td> 
    <td colname="col2"> <p>如果在发出远程请求时正在执行另一个索引操作，则搜索机器人无法执行所请求的索引。 在这种情况下，您的优先级响应文本字符串将返回到服务器。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>错误响应字符串 </p> </td> 
    <td colname="col2"> <p>允许您指定错误响应文本字符串。如果密码不正确，或发生其他错误。 在这种情况下，搜索自动机会将您的“错误”响应字符串返回给服务器。 </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Save Changes]**.
