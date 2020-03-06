---
description: 直接点击允许您在客户搜索匹配词时将客户重定向到指定的URL。 这种功能使您能够改进网站搜索的导航。
seo-description: 直接点击允许您在客户搜索匹配词时将客户重定向到指定的URL。 这种功能使您能够改进网站搜索的导航。
seo-title: 关于直接点击
solution: Target
title: 关于直接点击
topic: Rules,Site search and merchandising
uuid: 374d63c8-2b82-4165-b543-05b587757baa
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# 关于直接点击{#about-direct-hits}

直接点击允许您在客户搜索匹配词时将客户重定向到指定的URL。 这种功能使您能够改进网站搜索的导航。

## 使用直接点击 {#concept_C5EE074A19FD4D5B8DD21DB575E35565}

直接点击由两个主要元素组成：网站的URL以及一个或多个以逗号分隔的搜索词。 直接点击按如下方式指定：

```
    website_URL: term
    website_URL: term, term, term
```

例如，假设您有一个公司网站，其中有一个页面指定了您的所有条款和条件。 当客户搜索您的条款和条件而不是显示结果时，您可以将客户重定向到您的条款和条件页面。

```
    https://www.mycompany.com/policies.asp?article=terms: terms and conditions, terms, conditions, security
    https://www.mycompany.com/press/news.asp: press releases, press
```

如果查询词与任何直接点击不匹配，则搜索结果会按通常方式返回。

## 配置直接点击 {#task_64DFB8C554874C699FCC0C2F26C3669F}

您可以指定将Web浏览器重定向到URI的搜索词，而不是返回搜索结果。

<!-- 

t_configuring_direct_hits.xml

 -->

允许以“#”（哈希）字符开头的空行和注释行。

**配置直接点击**

1. 在产品菜单中，单击 **[!UICONTROL Rules]** > **[!UICONTROL Direct Hits]**。
1. 在字 [!DNL Direct Hits] 段中，输入网站的URL以及一个或多个以逗号分隔的搜索词。
1. 单击 **[!UICONTROL Save Changes]**.
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 测试直接点击 {#task_1E2EA833BF90423AA0DD8C5BBFE77445}

在实时推送直接点击规则之前，您可以通过输入术语来测试直接点击。

<!-- 

t_testing_direct_hits.xml

 -->

如果测试的术语未被直接点击规则涵盖，则会显示一条消息，通知您。 在这种情况下，如果直接点击规则在您的网站上实时显示，则搜索结果将一如既往地返回。 如果测试了直接点击规则涵盖的术语，将显示一条消息，告知您已经重定向到指定的URL。

**测试直接点击**

1. 在产品菜单中，单击 **[!UICONTROL Rules]** > **[!UICONTROL Direct Hits]**。
1. 在字段 [!DNL Test Direct Hits] 中，输入搜索词，然后单击 **[!UICONTROL Test]**。
1. （可选）执行下列操作之一：

   * 单击 **[!UICONTROL History]** 可还原您所做的任何更改。

      请参 [阅使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅 [查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参 [阅实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

