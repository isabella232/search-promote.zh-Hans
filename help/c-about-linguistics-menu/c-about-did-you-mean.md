---
description: 您可以配置“是否是您的意思”，以便客户在尝试失败的搜索时，会收到有关有效搜索词的建议。 通过查找拼写并键入导致有效搜索的搜索词的更正来形成建议。
seo-description: 您可以配置“是否是您的意思”，以便客户在尝试失败的搜索时，会收到有关有效搜索词的建议。 通过查找拼写并键入导致有效搜索的搜索词的更正来形成建议。
seo-title: 你是说
solution: Target
title: 你是说
topic: Linguistics,Site search and merchandising
uuid: c5973541-3d6b-4fc9-bad4-66d4d3559fe8
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 2%

---


# 关于你是说{#about-did-you-mean}

您可以配置“是否是您的意思”，以便客户在尝试失败的搜索时，会收到有关有效搜索词的建议。 通过查找拼写并键入导致有效搜索的搜索词的更正来形成建议。

## 配置是指{#task_B539D6A0043547EFB1CA19B67E762371}

当客户的查询返回不返回或最少的搜索结果时，您可以定制[!DNL site search/merchandising]如何提供搜索建议。

<!-- 

t_configuring_did_you_mean.xml

 -->

**配置是指**

1. 在产品菜单中，单击&#x200B;**[!UICONTROL Linguistics]** > **[!UICONTROL Did You Mean]**。
1. 在[!DNL Did You Mean]页面的&#x200B;**从建议中删除这些单词文本字段中，输入空格或行分隔的单词以筛选不需要的建议。**

   这些是搜索索引中不显示为推荐的替代搜索词的词。 可以通过使用常规表达式排除与模式匹配的任何单词。 否则，仅删除确切的单词。

1. 设置您需要的&#x200B;**Did You Mean**&#x200B;选项。

   <!-- 
   
   r_did_you_mean_options.xml
   
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
      <td colname="col1"> <p>建议算法 </p> </td> 
      <td colname="col2"> <p>调整软件查找建议的距离。 如果用户犯了一个单字母错误，所有算法都会提出相同的建议。 其原因在于，只需进行一次编辑即可得出有效的建议，所有算法都会找到与原文相近的词。 但是，当原始搜索词与索引中的现有词不相似时，<b>Deep</b>和<b>错误拼写符</b>建议算法会继续搜索可能的建议。 如果客户尝试了难以键入的正确名称，并发出声音，则此方案很有用。 但是，如果只希望显示类似的建议，可以选择<b>Quick</b>算法。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>要显示的建议的默认计数 </p> </td> 
      <td colname="col2"> <p>指定客户的搜索未返回结果时要显示的“Did You Mean”术语建议(0-20)数。 默认值为 3。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最小建议字长 </p> </td> 
      <td colname="col2"> <p>Prunes Did You Mean术语，指定建议单词的最小字母数。 </p> <p>例如，如果将值设置为4，则软件不建议长度为1、2或3个字符的单词。 如果指定值0，则不会从术语建议中删除任何短词。 如果指定的值较高，则通常不会生成术语建议。 默认值为 3。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最小索引频率 </p> </td> 
      <td colname="col2"> <p> 指定词在包含在“Did You Mean”词典之前必须出现在索引中的最小次数。 </p> <p>不能在字段中指定负数。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>如果没有结果，搜索建议词 </p> </td> 
      <td colname="col2"> <p>当客户的搜索未产生任何结果并且至少存在一个“您是中意的”术语建议时，自动重新搜索第一个建议的术语。 </p> <p>您可以在演示文稿模板中使用以下标记来指示网站搜索／销售正在自动搜索其他术语： </p> <p> <code>&nbsp;&lt;guided-if-suggestion-autosearch&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Search&nbsp;for&nbsp;&lt;guided-param&nbsp;gsname="q"&nbsp;/&gt;&nbsp;instead&nbsp;of&nbsp;guided-suggestion-original-query&nbsp;/&gt;&nbsp;&lt;/guided-if-suggestion-autosearch&gt;</code> </p> <p>您还可以在此处显示其他建议。 </p> <p> <code>&nbsp;&lt;guided-if-suggestion-autosearch&gt;&nbsp;&nbsp;There&nbsp;was&nbsp;0&nbsp;matches&nbsp;for&nbsp;&lt;guided-suggestion-original-query&nbsp;/&gt;&nbsp;&nbsp;&nbsp;Did&nbsp;You&nbsp;Mean&nbsp;&lt;guided-param&nbsp;gsname="q"&gt;?&nbsp;Here&nbsp;are&nbsp;the&nbsp;results&nbsp;for&nbsp;that&nbsp;search.&nbsp;&nbsp;&nbsp;Or&nbsp;Did&nbsp;You&nbsp;Mean&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestions&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestion-link&gt;&lt;guided-suggestion&nbsp;/&gt;&lt;/guided-suggestion-link&gt;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-suggestions&gt;&nbsp;&lt;/guided-if-suggestion-autosearch&gt;</code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>由于结果不佳而提出建议 </p> </td> 
      <td colname="col2"> <p>如果客户搜索的搜索结果少于10个的词，搜索引擎会检查该词是否有可产生100个以上结果的建议。 如果确实如此，您可以使用以下标记向用户表明，当用户获得结果时，他们可能希望搜索其他内容： </p> <p> <code>&nbsp;&lt;guided-if-suggestion-low-results&gt; &nbsp;&nbsp;You&nbsp;have&nbsp;a&nbsp;low&nbsp;result&nbsp;count&nbsp;for&nbsp;&lt;Search&nbsp;for&nbsp;guided-param&nbsp;gsname="q"&gt;.&nbsp;&nbsp;Did&nbsp;you&nbsp;mean:&nbsp;&lt;guided-suggestion&gt;&lt;guided-suggestion-link&gt;&lt;guided-suggestion&nbsp;/&gt;&lt;/guided-suggestion-link&gt;&lt;guided-if-not-last&gt;,&nbsp;&lt;/guided-if-not-last&gt;&lt;/guided-suggestions&gt;&nbsp;&lt;/guided-if-suggestion-low-results&gt;</code> </p> <p> 在以上方案中，建议数量由<span class="uicontrol">默认建议计数中指定的值控制，以显示</span>。 低阈值和高阈值可由以下选项配置。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>在初始结果少于时提出建议 </p> </td> 
      <td colname="col2"> <p>控制系统开始优惠建议时的结果数。 </p> <p>仅当选中<span class="uicontrol">由于结果低而建议</span>时，才会显示此选项。 </p> <p>默认值为 10。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>建议必须至少生成这么多结果 </p> </td> 
      <td colname="col2"> <p>过滤器由于主搜索结果较低而按结果计数提出的建议。 </p> <p>仅当选中<span class="uicontrol">由于结果低而建议</span>时，才会显示此选项。 </p> <p>默认值为 100。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 单击&#x200B;**保存更改**。
1. （可选）执行下列操作之一：

   * 单击&#x200B;**[!UICONTROL History]**&#x200B;以还原您所做的任何更改。

      请参阅[使用历史记录选项](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 单击 **[!UICONTROL Live]**.

      请参阅[查看实时设置](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 单击 **[!UICONTROL Push Live]**.

      请参阅[实时推送舞台设置](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

