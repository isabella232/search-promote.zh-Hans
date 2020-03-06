---
description: 您可以使用垂直更新来快速更新索引的各个部分，而无需处理大量数据。
seo-description: 您可以使用垂直更新来快速更新索引的各个部分，而无需处理大量数据。
seo-title: 关于垂直更新
solution: Target
subtopic: Vertical Update
title: 关于垂直更新
topic: Index,Site search and merchandising
uuid: ded09e89-5a52-4e8c-a6f7-3e25b4191183
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a

---


# 关于垂直更新{#about-vertical-update}

您可以使用垂直更新来快速更新索引的各个部分，而无需处理大量数据。

## 使用垂直更新 {#concept_E65A70C9C2E04804BF24FBE1B3CAD899}

垂直索引只需几秒即可执行，对大容量电子商务网站非常有用，这些网站可能需要数小时才能完全索引或以增量方式索引。

生成垂直索引时，将显示状态信息，如开始时间、已用时间和索引过程中的错误。

您可以随时停止或重新启动垂直索引过程。

当新的垂直索引更新您的实时网站时，客户可以继续使用您当前的索引搜索您的网站。

>[!NOTE]
>
>默认情况下，此功 [!DNL Adobe Search&Promote]能未在中启用。 请联系技术支持以激活该功能供您使用。

“垂直更新”专门用于电子商务样式帐户， [!DNL Adobe Search&Promote] 这些帐户使用IndexConnector提供搜索索引的内容。 典型的用例是，索引代表可搜索的产品目录，并且需要能够快速更新频繁更改的值，如库存、可用性和／或价格。 [!DNL Adobe Search&Promote] 垂直更新与增量索引有些相似，只是它只更新每个文档的部分，而增量索引则用新版本替换整个文档。

术语“垂直更新”指的是索引可以以柱状表的形式出现，每列对应于 [!DNL Adobe Search&Promote][!DNL Adobe Search&Promote] “元数据”字段定义，每行对应于文档。 垂直更新过程将替换一个或多个列，无需更改任何其他列的内容。

当内容的主源（IndexConnector源）包含创建索引所需的所有数据元素时，垂直更新源是主源的子集，它使用相同的IndexConnector“架构”定义数据元素，但仅包含需要更新的数据项 ** 。

垂直更新源至少需要包含“主键”元素(如IndexConnector配置中的“主键 **** ”复选框所标识)和至少一个要更新的数据元素。

例如，主IndexConnector源可能如下所示（但通常包含更多数据项）:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<products>
<product>
  <id><![CDATA[123]]></id>
  <title><![CDATA[Title for product 123]]></title>
  <description><![CDATA[Description for product 123.]]></description>
  <price>3.99</price>
  <link><![CDATA[https://www.somewhere.com/products/123]]></link>
  <image><![CDATA[https://www.somewher.com/images/products/123.jpg]]></image>
  <label><![CDATA[PROD123]]></label>
  <inventory>100</inventory>
  <brand><![CDATA[brand123]]></brand>
  ...
</product>
<product>
...
</product>
</products>
```

一个要求是，必须能够快速更新 `<price>` 和值 `<inventory>` ，因为这些值在客户的站点上可以快速更改。 然后，垂直更新源可能如下所示：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<products>
<product>
  <id><![CDATA[123]]></id>
  <price>3.50</price>
  <inventory>90</inventory>
</product>
<product>
...
</product>
</products>
```

此信息通常存储在客户服务器上的单独文件中，IndexConnector的“垂直文件路径”配置设置指向此文件。 “垂直更新”过程会读取此新内容并更新现有索 [!DNL Adobe Search&Promote] 引，仅更新和的 `<price>` 值， `<inventory>`在这种情况下。 随后的搜索将返回新更新的内容。

>[!NOTE]
在此示例中，需要 `<price>` 在 `<inventory>` 选中“垂直更新字段”选项的情况下定义 **“和元数据字段** ”。

另请参 [阅关于为索引和添加](../c-about-index-menu/c-about-remote-control-for-indexing.md#concept_C79B322190E84106A434E5C6D4A4118F)[新元标记字段进行远程控制](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。

## 配置分阶段网站的垂直更新 {#task_46A367B0786C4C90BFFA5D3F95FD86C0}

您可以通过指定URL来配置要包含在垂直更新中的索引连接器源。

**配置分阶段网站的垂直更新**

1. 在产品菜单中，单击 **[!UICONTROL Index]** > **[!UICONTROL Vertical Update]** > **[!UICONTROL Configuration]**。
1. 在页 **[!UICONTROL Vertical Update Configuration]** 面的“更新URL”字段中，指定要编入索引的页面的URL。

   搜索自动机只更新在指定的索引连接器源中标识的文档。

   此字段必须仅包含索引连接器URL，如下例所示：

   `index:product_catalog`。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 查看实时网站或分阶段网站的垂直更新日志 {#task_E668E1F1240C476DAA1CA783DC728232}

当实时垂直更新或分阶段垂直更新完成时，您可以查看其关联的日志来排除可能发生的任何错误。

您无法导出垂直更新日志文件，也无法保存它们。 日志文件在出现下一个索引之前一直可供查看。

**查看实时网站或分阶段网站的垂直更新日志**

1. 在产品菜单中，执行下列操作之一：

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Vertical Update]** > **[!UICONTROL Live Log]**.

   * 单击 **[!UICONTROL Index]** > **[!UICONTROL Vertical Update]** > **[!UICONTROL Staged Log]**.

1. 在日志页面顶部或底部，执行下列任一操作：

   * 使用导航选 **[!UICONTROL First]**&#x200B;项、 **[!UICONTROL Prev]**、 **[!UICONTROL Next]**、 **[!UICONTROL Last]**&#x200B;或 **[!UICONTROL Go to line]** 在日志中移动。

   * 使用显示选 **[!UICONTROL Errors only]**&#x200B;项 **[!UICONTROL Wrap line]**&#x200B;或 **[!UICONTROL Show]** 优化您看到的内容。

