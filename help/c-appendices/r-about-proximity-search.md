---
description: “邻近性搜索”允许您将唯一位置与网站上的任何页面关联，然后按距离给定位置的邻近性（距离）搜索结果并对其排序。
solution: Target
title: 关于邻近搜索
topic: Appendices,Site search and merchandising
uuid: 24fc9265-3400-46a7-b6e0-4de5b049a39a
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 0%

---


# 关于接近搜索{#about-proximity-search}

“邻近性搜索”允许您将唯一位置与网站上的任何页面关联，然后按距离给定位置的邻近性（距离）搜索结果并对其排序。

例如，假定您已在您的网站上填充了美国邮政邮政编码元数据，例如：

```
<meta name="zipcode" content="84057">
```

然后，您将配置帐户以索引您的邮政编码元数据。 在&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]** > **[!UICONTROL Add New Field]**&#x200B;中，在[!DNL Add Field]页面上设置以下选项：

* 字段名称: `zip`
* 元标记名称：`zipcode`
* 数据类型: **[!UICONTROL Location]**
* 排序: **[!UICONTROL Ascending]**
* 默认单位：**[!UICONTROL Miles]**

在为站点编制索引后，您执行以下搜索：

```
...&sp_q_location_1=84057&sp_x_1=zip&sp_q_max_1=100&sp_s=zip_proximity
```

结果集包含位于100英里以内的任何文档，按距此邮政编码的升序排序。

您还可以为美国地点使用电话区号。 或者，您可以使用纬度/经度对指定站点元数据和搜索条件中的位置。 根据所提供的数据的形式自动确定位置类型。

三位数的位置值（&quot;DDD&quot;，其中每个&quot;D&quot;表示0-9之间的十进制数字）被视为美国电话区号。

5或5 — 短划4位数的位置值（&quot;DDDDD&quot;或&quot;DDDDD-DDDD&quot;）被视为美国邮政编码。

以“±DD.DDDD.DDDD.DDDDD”精确形式的位置值被视为经纬度对。 第一个签名数值指定纬度，第二个签名数值表示经度。

**重要说明**:如果指定正纬度值或正经度值，或同时指定两者，则URL中的“+”字符必须编码为 `%2b`。否则，&quot;+&quot;将解释为空格，并且该值不被识别为有效位置。 例如，假设您的纬度值为+49.2394，经度值为–123.1892。URL的位置部分（已编码“+”）如下所示：

```
...&sp_q_location_1=%2b49.2394-123.1892...
```

* 正纬度值表示赤道以北的度数。
* 负纬度值表示赤道以南的度数。
* 正经度值表示“主子午线”的“东侧”度。
* 负经度值表示主子午线的西度。

例如，值“+48.8577+002.2950”表示赤道以北48.8577度，主子午线以东2.295度，即埃菲尔铁塔在法国巴黎的确切位置。 数字符号和每个数字是必填项，甚至前导零和尾随零也是如此。 例如，三个值“48.8577+2.2950”、“+48.8577+2.2950”和“+48.8577+02.295”不是位置。 第一个值缺少纬度上的行距符号。 第二个值缺少经度上的两个前导零。 第三个值缺少经度上的尾随零。 请务必仔细检查索引日志中是否存在任何与位置相关的问题。

当您按proximity搜索时，会为该搜索创建一个特殊的“proximity输出字段”。 该字段填充了在搜索条件中指定的位置和与每个搜索结果关联的位置之间的相对距离。 此特殊字段是为在搜索条件中使用的位置类型字段命名的，该搜索条件在末尾添加了“_proximity”。

在上面的示例搜索中，结果按“zip_proximity”的升序排序。 即指定的ZIP代码(84057)与每个结果的“zip”字段位置之间的距离。 您还可以使用此特殊的“proximity output field”来显示每个搜索结果的相对距离（以公里或英里为单位），使用`<Search-Display-Field>`搜索模板标记。

请参阅[搜索模板标记](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

您也可以不使用sp_s选项进行搜索。 在这种情况下，结果按得分排序（sp_s=0，这是默认值）。得分受每个结果与通过sp_q_location[_#]参数指定的邻近搜索位置的相对距离的影响。 添加新的cgi参数sp_q_max_relevent_distance[#]，以任选地控制应用于邻近搜索的相关计算。

下面是一个邻近相关搜索示例：

```
...&sp_q_location_1=84057&sp_x_1=zip&sp_q_max_1=100&sp_q_2=shirt&sp_x_2=title&sp_q_max_relevant_distance_2=50
```

结果集包含任何位于100英里以内的文档，并在标题字段中包含单词“shirt”，该单词按受邻近相关评分影响的评分排序。 接近度分量的完美相关得分表示距离为0。 邻近部分的最低相关分数代表距离仅略超过50英里。

您可以通过查看搜索CGI参数参考主题中的`sp_location`、`sp_location_#`、`sp_q_min`、`sp_q_min_#`、`sp_q_max`、`sp_q_max_#`和`sp_s`来了解有关接近性搜索的更多信息。

请参阅[搜索CGI参数](../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890)。

请参阅[添加新的meta标签字段](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。
