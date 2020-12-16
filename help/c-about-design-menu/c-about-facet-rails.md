---
description: 使用Facet边栏可重新排序网页上的facet组。
seo-description: 使用Facet边栏可重新排序网页上的facet组。
seo-title: 关于Facet边栏
solution: Target
subtopic: Navigation
title: 关于Facet边栏
topic: Design,Site search and merchandising
uuid: 6da2bd67-8c20-4955-9836-bc8ba88546c5
translation-type: tm+mt
source-git-commit: 6b3aa733b0dfaace956f0ffc25f433fefd21e15f
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 1%

---


# 关于Facet边栏{#about-facet-rail}

使用Facet边栏可重新排序网页上的facet组。

## 使用Facet边栏{#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB}

facet是属性或特征，它是对搜索结果进行一般分类的方法。 例如，制造商、价格和颜色可以视为一组彩块化。 每个彩块化可以有多个约束或值。 例如，如果颜色作为彩块，则“彩块值”可以是红色、橙色、黄色、绿色、蓝色、靛蓝和紫色。

请参阅[关于Facet](../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5)。

您可以使用彩块化边栏在网页上对这些彩块化组重新排序。 例如，假定网页左侧有一个搜索结果部分。 列出的部分，从上到下、类别facet、品牌facet、价格facet和最受欢迎的facet。 例如，使用facet边栏，您可以让“最受欢迎”facet显示在类别facet的上方或下方。

要一起重新排序的facet组属于facet边栏标记。 一个facet只能属于一个facet边栏。 facet边栏是“表示”模板标签，并包含facet的单个表示。 属于此边栏的所有彩块化共享该单个彩块化表示。

请参阅[演示文稿模板标记](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)中的[关于模板](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5)和Facet。

## 配置facet边栏{#task_561A8FF1CAD1402B9DD33E276BBC6A0E}

您可以添加彩块化边栏以自定义您的表示层。 Facet Rails为您的客户提供了“向导式搜索”，允许他们根据网页上facet的顺序深入到搜索结果中。

<!-- 

t_configuring_facet_rail.xml

-->

您对facet滑轨所做的任何更改都可以使用历史记录功能进行还原。

**配置facet边栏**

1. 在配置facet边栏之前，请确保已添加facet，并作为该任务的一部分指定了facet边栏名称。

   请参阅[添加新facet](../c-about-design-menu/c-about-facets.md#task_FC07BFFA62CA4B718D6CBF4F2855C89B)。
1. 在产品菜单上，单击&#x200B;**[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Facet Rail.]**
1. 在[!DNL Facet Rail]页面上，选择要包含在facet边栏中的facet，然后从下拉列表中设置&#x200B;**[!UICONTROL Sort Facets Method]**&#x200B;选项。

   <!-- 
   r_facet_rail_options.xml
   -->

   | 功能／选项 | 描述 |
   |--- |--- |
   | Facet Rail 名称 | 标识facet边栏的名称。  在添加facet时创建facet边栏的名称。  请参阅[添加新facet](../c-about-design-menu/c-about-facets.md#task_FC07BFFA62CA4B718D6CBF4F2855C89B) |
   | 包含的彩块化 | 可以选择的可能彩块化的列表，以添加到彩块化边栏。  如果您选择使用`Custom`对彩块化进行排序，您在此处选择彩块化的顺序将决定彩块化在`Custom Facet Order`文本框中的显示顺序。 |
   | 排序彩块化方法 | 在下拉列表中，从以下三个选项中选择一个：<ul><li>`Alpha` 彩块化按字母顺序排序，其名称包括标点字符。</li><li>`Alpha (not case sensitive)` 彩块化按字母顺序排序，忽略字母字符的大小写，包括标点字符。 </li><li>`Alpha (alphanumeric only)` 彩块化会按字母顺序对名称进行排序，忽略标点字符。 </li><li>`Alpha (not case sensitive, alphanumeric only)` 彩块化按字母顺序排序，忽略字母字符的大小写，忽略标点字符。 </li><li>`Count` 彩块化会根据计数进行排序。 </li><li>`Custom` 打开文 `Custom Facet Order` 本框，您可以通过输入每个facet的确切名称来定义facet的顺序。从`Custom Facet Order`列表删除所有未删除的facet标签。</li></ul> |
   | 自定义彩块化顺序 | 仅当您从`Sort Facets Method`下拉列表中选择`Custom`时，此选项才可用。  允许您列表facet名称（每行一个，或全部以一行和逗号分隔）。 如果定义了facet标签，则它们显示在`Facets Included`列表中，括在括号中。  不要在`Custom Facet Order`文本框中包含facet标签。  当您在`Facets Included`列表中选择或取消选择彩块化时，`Custom Facet Order`文本框会自动更新。 |

1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）在[!DNL Facet Rail]页面上，执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;以还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

1. 通过执行以下操作编辑演示文稿模板：

   * 在演示文稿模板上创建“facet模板”。
   * 用`<guided-facet-rail>`标记环绕“facet template”。

      请参阅[演示文稿模板标记](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)中的彩块化。

      示例：

      ```
      <guided-facet-rail>
        <guided-facet>
          <guided-facet-display-name/>
          ...
          </guided-facet>
        </guided-facet-rail>
      ```

      这些标记会划出演示文稿模板的一部分，以成为facet边栏中每个facet的可重复模式。 属于facet边栏的每个facet都使用此刻出的部分来评估其输出。 最终演示文稿模板上只能显示一个`<guided-facet-rail>`标记。

      以下标记不需要`<guided-facet-rail>`内的`gsname`属性，因为该值在搜索时动态确定并正确替换：

      `<guided-facet>`
      `<guided-facet-display-name>`
      `<guided-facet-total-count>`
      `<guided-facet-undo-link>`
      `<guided-facet-undo-path>`
      `<guided-facet-behavior>`

   * 保存演示文稿模板并将其实时推送。

      请参阅[编辑演示文稿或传输模板](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3)。
