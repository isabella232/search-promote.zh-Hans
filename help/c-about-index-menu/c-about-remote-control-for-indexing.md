---
description: 只要网站发生更改，您就可以运行脚本或程序，请求搜索机器人使用远程控制运行索引。
seo-description: 只要网站发生更改，您就可以运行脚本或程序，请求搜索机器人使用远程控制运行索引。
seo-title: 关于索引的远程控制
solution: Target
title: 关于索引的远程控制
topic: Index,Site search and merchandising
uuid: 20e230c6-5c1a-4bf4-bff3-b8236d14ab21
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a

---


# 关于索引的远程控制{#about-remote-control-for-indexing}

只要网站发生更改，您就可以运行脚本或程序，请求搜索机器人使用远程控制运行索引。

## 使用远程控制进行索引 {#concept_C79B322190E84106A434E5C6D4A4118F}

远程控制索引请求通常来自位于服务器上的脚本或程序。

该机器人执行的索引步骤与从菜单手动启动的步骤相 [!DNL Index] 同。 要提交远程控制请求，请配置必要的口令和响应字符串。

## 如何发出远程控制请求 {#section_42FAB2BAB25A4E24BEA69566C6D1C70F}

要发出远程控制请求，请根据数据中心的位置使用以下格式示例：

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
   <td colname="col1"> <p> <span class="codeph"> sp_a= sp9999999 </span> </p> </td> 
   <td colname="col2"> <p> 您的帐号。 </p> <p>您可以在“帐户设置” <span class="uicontrol"> &gt;“帐户设 <b>置”</b></span> &gt;“帐户设 <span class="uicontrol"> 置”&gt;“帐户设 <b>置”&gt;“帐户设置”下找</b></span><span class="uicontrol"><b></b></span>到帐户编号。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_lines= N </span> </p> </td> 
   <td colname="col2"> <p>用于检查正在运行的索引爬行状态。 </p> <p> <span class="codeph">  N </span> 是正整数或全 <span class="codeph"> 部 </span>。 如果这是数值，则相应的索引日志 <span class="codeph"> 文 </span> 件的最后N行将包含在JSON响应中。 </p> <p>如果该值为 <span class="codeph"> all </span>，则返回整个文件。 </p> <p>如果值为 <span class="codeph"> 0 </span>，则不返回日志信息。 此值是运行索引状态查询的默认值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_operation= op </span> </p> </td> 
   <td colname="col2"> <p>允许您指定要运行的以下索引操作之一： </p> <p> 
     <ul id="ul_6CA190AC41694BC293FC7C6BABA629FE"> 
      <li id="li_EFC76E31D47E473F9A56B2EBA8A97CA1"> <span class="codeph"> full_index </span> <p>搜索机器人会运行您网站的完整索引。 </p> </li> 
      <li id="li_A9ACE21718804A21B3DA7B84AB6729D3"> <span class="codeph"> incremental_index </span> <p>该搜索机器人使用在“ <span class="uicontrol"> Incremental <b>Index</b></span> &gt; Incremental Index <span class="uicontrol"> &gt; <b>Index</b></span><span class="uicontrol"><b></b></span>&gt; Configuration”（增量索引&gt; Incremental Index）下设置的配置运行增量索引。 </p> </li> 
      <li id="li_722FE409AE454AD48ACE95C4CDC7A00B"> <span class="codeph"> vertical_index </span> <p>搜索机器人使用在“ <span class="uicontrol"> Index <b>&gt; Vertical Update</b> </span> &gt; Previtical Update”（垂直更新） <span class="uicontrol"> &gt;“Previtical Update”（垂直更新）配置下设置的配置运 <b></b></span><span class="uicontrol"><b></b></span>行垂直更新。 </p> <p>请参阅 <a href="../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> 关于垂直更新</a>。 </p> </li> 
      <li id="li_A40B513CE17043A4925CE3D4DE0B48A4"> <span class="codeph"> script_index </span> <p>搜索机器人使用在“索引 <span class="uicontrol"> &gt;脚本索引 <b>&gt;</b> Scripted Index </span><span class="uicontrol"><b></b></span><span class="uicontrol"><b></b></span>&gt; Configuration”（脚本索引&gt; Scripted IndexConfiguration）下指定的文本文件运行增量索引。 </p> </li> 
      <li id="li_A0BC7F1373B14393997BAB7690FD3EF7"> <span class="codeph"> full_staged_index </span> <p>搜索自动机运行网站的完整分阶段索引。 </p> </li> 
      <li id="li_47753E358457443A95B384A278FACA83"> <span class="codeph"> incremental_staged_index </span> <p>搜索机器人使用在“索引 <span class="uicontrol"> &gt;增量索引 <b>&gt;</b> Incremental Index </span> &gt;Incremental Index <span class="uicontrol"><b></b></span><span class="uicontrol"><b></b></span>Configuration”（增量索引&gt;增量索引）下设置的增量分级索引运行增量分级索引。 </p> </li> 
      <li id="li_C8B5F8F1208E438ABEFDF9129A6B14A3"> <span class="codeph"> vertical_staged_index </span> <p>搜索机器人使用在“索引 <span class="uicontrol"> &gt;垂直更新” <b>&gt;“垂直更新”配置下设置的“垂直分级更新”</b> ，运行垂 </span><span class="uicontrol"><b></b></span><span class="uicontrol"><b></b></span>直分级更新。 </p> </li> 
     </ul> </p> <p>注意： 要使用垂直更新，您可能需要由Adobe客户代表或Adobe支持在您的帐户中启用它。 </p> <p>请参 <a href="../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> 阅关于垂直更 </a>新。 </p> <p>您可以将 <span class="codeph"> _saved附加到 </span> 上述任何sp_operation值，以使搜索自动机 <span class="codeph"></span> 尝试使用保存的内容。 例如，您可以指定以下内容： </p> <p> <code class="syntax html"> sp_operation=full_index_saved </code> </p> <p>或 </p> <p> <code class="syntax html"> sp_operation=full_staged_index_saved </code> </p> <p>或者，您可以将 <span class="codeph"> _status附加到以上任何 </span> sp_operation值，以请求当前或最近 <span class="codeph"></span> 操作的状态报告。 例如，您可以指定以下内容： </p> <p> <code class="syntax html"> sp_operation=full_index_status </code> </p> <p>或 </p> <p> <code class="syntax html"> sp_operation=full_staged_index_status </code> </p> <p>并且结果将作为JSON对象返回。 包 <span class="codeph"> 括sp_lines=N以 </span> 包括N行关联的日志文件。 如果N为负，则包括最后N行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_operation= pushlive </span> </p> </td> 
   <td colname="col2"> <p> 允许您远程推送实时索引。 </p> <p>忽略将 <span class="codeph"> _saved追加 </span> 到推送实时操作的任何尝试。 </p> <p>运行pushlive操 <span class="codeph"> 作时， </span> 将向服务器返回“确定”、“优先级”或“错误”响应文本字符串。 您可以在“远程控制”页面上指定 <span class="wintitle"> 这些响应 </span> 字符串。 </p> <p>请参 <a href="../c-about-index-menu/c-about-remote-control-for-indexing.md#task_57C296258404448DA7A5ADC9B7232391" format="dita" scope="local"> 阅配置远程控制以建立索引</a>。 </p> <p>如果在没有分阶段索引时实时推送，则不会发生任何情况，并返回“确定”响应字符串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_password=xxxxxx </span> </p> </td> 
   <td colname="col2"> <p>遥控密码。 </p> </td> 
  </tr> 
 </tbody> 
</table>

搜索以正确的HTTP响应形式返回数据。 完整响应由HTTP状态、HTTP响应头、空行和响应字符串组成。

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

或者，假定您执行以下远程控制状态请求：

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

要获取与此索引操作关联的日志列表的前十行及其状态，请使用以下查询：

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

Note the `offset` value. 此值标识日志文件中读取结束时的文件偏移位置。 要阅读文 *件中的* 10行，您应在本例中将请求包含在发送到 `&sp_offset=672` 服务器的请求中。

使 `sp_offset`用，您可以有效地翻阅日志文件。

要获取日 *志的最后* 10行以及状态，请将计数指定为负数。 例如，指定 `sp_lines=` 的值为， `-10` 如下所示：

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

请注意，此处不 `offset` 返回任何值，因为此操作在文件末尾完成，并且不再有可读取的行。

## 配置远程控制以进行索引 {#task_57C296258404448DA7A5ADC9B7232391}

只要您的网站发生更改，您就可以使用远程控制从您的服务器运行脚本或程序，请求搜索机器人运行索引。

**配置远程控制以建立索引**

1. 在产品菜单中，单击 **[!UICONTROL Index]** > **[!UICONTROL Remote Control]**。
1. 在页面 [!DNL Remote Control] 上，设置每个配置字段选项，以便能够自动提交来自服务器的索引请求以索引您的网站。

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
    <td colname="col2"> <p>指定远程控制口令。 </p> <p> 密码区分大小写，长度至少为6个字符，并且必须至少包含一个字母。 建议您还至少包含一个数字。 </p> <p>请勿使用网站搜索／销售登录密码。 </p> <p>每个远程控制请求都使用您的口令。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>确定响应字符串 </p> </td> 
    <td colname="col2"> <p>允许您在请求的索引操作成功开始时指定“确定”响应文本字符串。 在这种情况下，搜索自动机会将您的OK响应字符串返回给服务器。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>优先级响应字符串 </p> </td> 
    <td colname="col2"> <p>如果在发出远程请求时正在进行另一个索引操作，则搜索机器人无法执行所请求的索引。 在这种情况下，您的优先级响应文本字符串将返回到服务器。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>错误响应字符串 </p> </td> 
    <td colname="col2"> <p>允许您指定“错误”响应文本字符串。 在这种情况下，搜索自动机会将您的“错误”响应字符串返回给服务器。 </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. 单击 **[!UICONTROL Save Changes]**.
