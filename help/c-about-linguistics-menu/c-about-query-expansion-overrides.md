---
description: 您可以覆盖搜索查询结果的扩展。
seo-description: 您可以覆盖搜索查询结果的扩展。
seo-title: 关于查询扩展覆盖
solution: Target
title: 关于查询扩展覆盖
topic: Linguistics,Site search and merchandising
uuid: dfe18004-b8fd-4889-b01c-72a3b0c82b9c
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# 关于查询扩展覆盖{#about-query-expansion-overrides}

您可以覆盖搜索查询结果的扩展。

## 使用查询扩展覆盖 {#concept_6895B469B0E044299E93361BFA06B554}

在配置查询扩展覆盖时，可创建一组“规则”。 每条规则本质上都说，“不要在搜索时 `<this>` 扩展到”，其中是简单的文本词或短语， `<that>``<this>``<that>` 是文本词或短语或分类。

>[!NOTE]
>
>默认情况下，Search&amp;Promote中未启用此功能。 请联系技术支持以激活该功能供您使用。 启用“查询扩展覆盖”功能后，您必须在用户界面中“打开它”。

**查询扩展覆盖的工作方式**

当在“查询扩展覆盖添加”页中指定了“文本”和“术语”值时，代码将对特定配对起作用。 当将分类类型指定为术语（如字典或替代单词表单）时，“不展开”值不会转换为由指示的分类创建的任何表单。

例如，假定您有以下定义：

`Do Not Expand = "dog"`

`Type = Text`

`Term = "dogs"`

搜索“dog”的查询将不包括“dog”，该查询通过替代单词表单扩展为“dog&#39;s”和“dogs”。

但是，如果定义如下：

`Do Not Expand = "dog"`

`Type = Alternate Word Forms`

查询不包括“dog&#39;s”或“dogs”（“dog”的替代单词表单）。

您可以指定多个术语、多个分类或同时指定两者。 但是，如果选择“全部”作为“类型”，则任何多词列表都将折叠为单个“全部”条目。

如果文本和分类条目在任何规则中混合，则它们会在用户界面中重新组织以首先显示文本值。 但是，这并不暗示或影响搜索时的评估顺序。

文本术语将被验证以删除无意义的引用。 即，将术语与“不展开”值进行比较，如果存在匹配项，则删除该术语。 此外，还会删除重复的术语值（文本或分类）。

如果您在复制先前定义时添加了“不扩展”值的新规则，则新定义的“条款”将添加到原始定义中。

## 配置查询扩展覆盖 {#task_A087354A509D4997BA275186C224160E}

在Search&amp;Promote中定义和添加查询扩展改写。

<!-- 

t_configuring_query_expansion_overrides.xml

 -->

>[!NOTE]
默认情况下，Search&amp;Promote中未启用此功能。 请联系技术支持以激活该功能供您使用。 启用“查询扩展覆盖”功能后，您必须在用户界面中“打开它”。 下面的前几步概述了如何实现这一点。

**配置查询扩展覆盖**

1. 在Search&amp;Promote中，单击“设 **置** ”>“用 **户** ” **>“**&#x200B;查看角色”。
1. 在“查看角色”页面的表的“操作”列中，单击“语言学”菜单中要授予其访问“查询扩展重写”权限的角色右侧的“编辑”。 ****
1. 在“编辑角色”页面上，展开“语言学”树。
1. 选中“ **查询扩展覆盖**”，然后单击“ **保存更改”**。
1. 单击“语 **言学** ”>“查 **询扩展重写”**。
1. 单击“ **添加查询扩展覆盖”**。
1. 在“查询扩展覆盖添加”页中，设置所需的选项。

   <!-- 
   
   r_query_expansion_override_definitions.xml
   
   -->

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>选项 </p> </th> 
      <th colname="col2" class="entry"> <p>描述 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>不扩展 </p> </td> 
      <td colname="col2"> <p>指定您不想展开的单词或短语。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>类型 </p> </td> 
      <td colname="col2"> <p>选择 <b>“文本</b> ”以指定特定单词或短语配对。 或者，选择一个分类以指定“不展开”字词或短语不会通过选定的分类进行转换。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>术语 </p> </td> 
      <td colname="col2"> <p>仅当您选择“文本 <b></b> ”作为“类型”时可用。 指定要从搜索扩展中排除的单词或短语。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>操作 </p> </td> 
      <td colname="col2"> <p> 单 <b>击+</b><b>或-</b> ，分别向定义中添加或删除条款。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 完成后，单击“添 **加”**。

   在“查询扩展覆盖定义”页中，可以编辑或删除已添加的定义。
1. 要预览添加的结果，请在蓝色框 **中单击重新生成分阶段站点索引** ，以快速重建分阶段网站索引。
1. （可选）执行下列操作之一：

   * 单击“ **实时**”。

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)

   * 单击“ **实时推送**”。

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)

