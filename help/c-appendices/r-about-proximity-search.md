---
description: “邻近性搜索”允许您将唯一位置与网站上的任何页面相关联，然后按距离给定位置的接近度（距离）搜索结果并对其排序。
seo-description: “邻近性搜索”允许您将唯一位置与网站上的任何页面相关联，然后按距离给定位置的接近度（距离）搜索结果并对其排序。
seo-title: 关于邻近搜索
solution: Target
title: 关于邻近搜索
topic: Appendices,Site search and merchandising
uuid: 24fc9265-3400-46a7-b6e0-4de5b049a39a
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# 关于邻近搜索{#about-proximity-search}

“邻近性搜索”允许您将唯一位置与网站上的任何页面相关联，然后按距离给定位置的接近度（距离）搜索结果并对其排序。

例如，假定您已使用美国邮政编码元数据在您的网站上填充了页面，如：

```
<meta name="zipcode" content="84057">
```

然后，您将帐户配置为索引您的ZIP代码元数据。 在 **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]** >中，在 **[!UICONTROL Add New Field]**[!DNL Add Field] 页面上设置以下选项：

* 字段名称: `zip`
* 元标记名称： `zipcode`
* 数据类型: **[!UICONTROL Location]**
* 排序: **[!UICONTROL Ascending]**
* 默认单位： **[!UICONTROL Miles]**

在为站点编制索引后，您需要执行以下搜索：

```
...&sp_q_location_1=84057&sp_x_1=zip&sp_q_max_1=100&sp_s=zip_proximity
```

结果集包含位于邮政编码84057100英里范围内的所有文档，这些文档按距离此邮政编码的升序排序。

您还可以为美国地点使用电话区号。 或者，您可以使用经纬度对指定站点元数据和搜索条件中的位置。 根据所提供数据的形式自动确定位置类型。

三位数的位置值（“DDD”，其中每个“D”代表0-9的十进制数字）被视为美国电话区号。

5或5-dash-4位数字位置值（“DDDDD”或“DDDDD-DDDD”）被视为美国邮政编码。

将“±DDD.DDDD.DDDDD.DDDDD”精确形式的位置值视为经纬度对。 第一个签名的数字值指定纬度，第二个签名的数字值表示经度。

**重要说明**:如果指定正纬度值或正经度值，或两者都指定，则URL中的“+”字符必须编码为 `%2b`。 否则，“+”被解释为空格，并且该值不被识别为有效位置。 例如，假设您的纬度值为+49.2394，经度值为-123.1892。URL的位置部分（已编码“+”）如下所示：

```
...&sp_q_location_1=%2b49.2394-123.1892...
```

* 正纬度值表示赤道以北的度数。
* 负纬度值表示赤道以南的度数。
* 正经度值表示“Prime Meridian”的“East”度。
* 负经度值表示“Prime Meridian”的“West”度。

例如，值“+48.8577+002.2950”表示赤道以北48.8577度，Prime Meridian以东2.295度，即法国巴黎埃菲尔铁塔的确切位置。 数字符号和每个数字是必填的，即使前导零和尾随零也是如此。 例如，三个值“48.8577+2.2950”、“+48.8577+2.2950”和“+48.8577+02.295”不是位置。 第一个值缺少纬度上的前导符号。 第二个值缺少经度上的两个前导零。 第三个值缺少经度上的尾随零。 请务必仔细检查索引日志中是否存在与位置相关的问题。

按邻近度搜索时，会为该搜索创建一个特殊的“邻近输出字段”。 该字段填充有在搜索条件中指定的位置和与每个搜索结果相关联的位置之间的相对距离。 此特殊字段是为在搜索条件中使用的位置类型字段命名的，该搜索条件在结尾处添加了“_proximity”。

在上面的示例搜索中，结果按“zip_proximity”的升序排序。 即指定的ZIP代码(84057)与每个结果的“zip”字段位置之间的距离。 您还可以使用此特殊的“近似输出字段”来使用“搜索模板”标签显示每个搜索结果的相对距离（以公里或英里为单位）。 `<Search-Display-Field>`

请参阅 [搜索模板标记](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

您也可以不使用sp_s选项进行搜索。 在这种情况下，结果按得分排序（sp_s=0，这是默认值）。得分受每个结果与通过sp_q_location[] _#参数指定的邻近搜索位置的相对距离的影响。 添加了一个新的cgi参数sp_q_max_relevent_distance[#] ，以可选地控制应用于邻近搜索的相关计算。

以下是邻近相关性搜索示例：

```
...&sp_q_location_1=84057&sp_x_1=zip&sp_q_max_1=100&sp_q_2=shirt&sp_x_2=title&sp_q_max_relevant_distance_2=50
```

结果集包含位于邮政编码84057100英里内的任何文档，并在标题字段中包含单词“shirt”，该单词按受邻近相关性评分影响的评分排序。 邻近组件的完美相关得分表示距离为0。 接近度组件的最低相关性得分表示50英里以上的距离。

您可以通过查看、、、、、、、和“搜索CGI参 `sp_location`数”参考主题，了解 `sp_location_#``sp_q_min``sp_q_min_#``sp_q_max``sp_q_max_#``sp_s` 有关接近性搜索的更多信息。

请参 [阅搜索CGI参数](../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890)。

请参 [阅添加新的元标记字段](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。
