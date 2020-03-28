---
description: 'null'
seo-description: 'null'
seo-title: Search&amp;Promote 8.14.0发行说明(05/22/2014)
solution: Target
title: Search&amp;Promote 8.14.0发行说明(05/22/2014)
topic: Release Notes,Site search and merchandising
uuid: 308d84a9-ec38-4fec-b146-e8a353e65be4
translation-type: tm+mt
source-git-commit: ffdec2cfcb30e733c664a7d1ca23868b7a9a9aa5

---


# Search&amp;Promote 8.14.0 Release Notes (05/22/2014){#search-promote-release-notes}

**修复**

* 如果 [!DNL sqlite_open] 失败，则早期的 sqlite 数据库文件将被移除，并从头创建一个新的文件。
* 在重复进行相同的搜索时，核心的搜索结果不一致。
* 改进了在每个搜索结果对应有多个输出字段时的模板处理性能。
* 在中添加了注 **[!UICONTROL Business Rule History]**&#x200B;释。
* 在执行索引操作的过程中，基于结果的触发器和操作预览索引重新生成阶段的性能会一直稳步下降。
* Changed **[!UICONTROL Reset SPIN cache]** option from boolean no/next-run to a tri-state: no/always/next-run.

