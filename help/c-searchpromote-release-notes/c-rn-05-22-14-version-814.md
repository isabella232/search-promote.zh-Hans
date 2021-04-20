---
description: Search&amp;Promote 8.14.0发行说明。
solution: Target
title: Search&amp;Promote 8.14.0发行说明(05/22/2014)
topic: Release Notes,Site search and merchandising
uuid: 308d84a9-ec38-4fec-b146-e8a353e65be4
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 63%

---


# Search&amp;Promote 8.14.0发行说明(05/22/2014){#search-promote-release-notes}

**修复**

* 如果 [!DNL sqlite_open] 失败，则早期的 sqlite 数据库文件将被移除，并从头创建一个新的文件。
* 在重复进行相同的搜索时，核心的搜索结果不一致。
* 改进了在每个搜索结果对应有多个输出字段时的模板处理性能。
* 在&#x200B;**[!UICONTROL Business Rule History]**&#x200B;中添加了注释。
* 在执行索引操作的过程中，基于结果的触发器和操作预览索引重新生成阶段的性能会一直稳步下降。
* 将&#x200B;**[!UICONTROL Reset SPIN cache]**&#x200B;选项从布尔值no/next-run更改为三状态：no/always/next-run。

