---
description: Search&amp;Promote 8.13.0发行说明。
solution: Target
title: Search&amp;Promote 8.13.0发行说明(04/16/2014)
topic-legacy: Release Notes,Site search and merchandising
uuid: b3524992-ff00-4a7c-a404-078242456734
exl-id: cba582ad-d388-4317-af06-b8b12b300f02
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 57%

---

# Search&amp;Promote 8.13.0发行说明(04/16/2014){#search-promote-release-notes}

| 新增功能和增强功能 | 描述 |
|----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 带有完整的表格匹配支持的动态 Facet | 某些客户有许多“SKU级别”属性，他们希望通过动态彩块化进行选择和显示。 正因为如此，您现在可以有选择地将每个动态 Facet 字段最多与静态帐户配置中的一个表格名称关联。在搜索时，如果搜索中涉及任何动态 Facet 字段，则可以应用这些表格关系。请参阅[关于动态数值](../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899)。 |

**修复**

* 更改了数据视图描述字段，使其使用标签`<search-display-field>`而不是`<search-description>`。
* 在索引连接器中添加了一项功能，使得主关键字可以连接两个或多个字段。
* 将 AttributeLoader-Regen-Enabled 脚本 `attributeloader-regen.pl` 更改为非 HTML 编码的值。
* 匹配“范围搜索”查询的索引时间和搜索时间空白处理。
* 当启用动态 Facet 时，添加业务规则有时会导致出现错误。

   请参阅[关于Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD)。

* Javascript错误导致无法在&#x200B;**Settings** > **SPIN** > **IndexConnector**&#x200B;中添加或编辑定义。
* 保存业务规则后，在创建业务规则时选择该时间时，该时间默认为GMT时区。 保存之后，它会显示帐户的时区，然后生效。

   请参阅[关于Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD)。

* 不能在阶段中正确排序业务规则。

   请参阅[关于Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD)。

* 通过允许您安排用于电子邮件传输的报表，搜索绩效报告功能得以增强。
* 业务规则固定的时间安排会变为夏令时。

   请参阅[关于Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD)。

* 如果定义了大量动态facet字段，则用户会经历缓慢的核心搜索响应时间。
* 出现了误报的范围索引错误。
* Dynamic Media在非北美数据中心的经典访问被中断。
* SPIN XPath 验证功能会返回一个误报错误。

* 当执行了启用/禁用 SPIN 的操作后，用户会被重定向到成员中心登录页面。
