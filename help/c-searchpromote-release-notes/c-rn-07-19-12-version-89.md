---
description: 'null'
seo-description: 'null'
seo-title: Search&amp;Promote 8.9发行说明(07/19/2012)
solution: Target
title: Search&amp;Promote 8.9发行说明(07/19/2012)
topic: Release Notes,Site search and merchandising
uuid: 3853c75d-19ed-4e36-9e81-dcbffe5f5b0c
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 59%

---


# Search&amp;Promote8.9发行说明(07/19/2012){#search-promote-release-notes}

**新增功能**

* 元数据管理改进——客户源中的动态元数据定义

   根据客户提供的元数据定义创建动态重新配置 Search&amp;Promote 帐户的方案。
* 索引性能改进——索引加载器

   索引加载器是一种将 XML 内容直接导入 Search&amp;Promote 索引的新方法。它是现有索引连接器功能的一部分，设计用于快速导入我们的标准 XML 馈送文件。

**修复和增强功能**

* 添加了按业务规则更改排序选项的支持。
* 在帮助系统`<search-description>`标签中，当描述的meta标签包含空内容时，显示正文。
* 添加了跟踪相应表格点击量的功能（适用于通过基于结果的操作添加的结果）。
* 增加了通过查询提交POST参数的支持
* 进行爬网时，在某些情况下可跳过最终的 mirror_account 操作。
* Adobe AnalyticsURL不包括CGI参数和进行Adobe Analytics查找所需的Search&amp;Promote代码，以便从URL密钥中以类似方式删除CGI参数。
* 实时推送重写规则之后，重写规则将间歇性地从用户界面消失。
* 设置为由于结果不佳而提出建议的Search&amp;Promote帐户可能会间歇性地产生结果。
* 重写规则测试输出没有换行符。
* 搜索 URL 规则页面和爬网列表存储 URL 规则页面指向错误的历史记录页面。
* 在某些横幅上单击编辑无法显示编辑页面。
* 重新排名更新代码有时非常慢。
* Facet 名称中混用大小写字母时无法删除或推送 Facet 项目。

