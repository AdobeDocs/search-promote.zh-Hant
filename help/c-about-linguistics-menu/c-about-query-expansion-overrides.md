---
description: 您可以覆蓋搜索查詢結果的擴展。
seo-description: 您可以覆蓋搜索查詢結果的擴展。
seo-title: 關於查詢擴展覆蓋
solution: Target
title: 關於查詢擴展覆蓋
topic: Linguistics,Site search and merchandising
uuid: dfe18004-b8fd-4889-b01c-72a3b0c82b9c
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 0%

---


# 關於查詢擴展覆蓋{#about-query-expansion-overrides}

您可以覆蓋搜索查詢結果的擴展。

## 使用查詢擴展覆蓋{#concept_6895B469B0E044299E93361BFA06B554}

當您設定查詢擴增覆寫時，會建立一組「規則」。 每個規則基本上都說，「在搜尋時不要將`<this>`展開為`<that>`」，其中`<this>`是簡單的文字字詞或片語，而`<that>`是文字字詞或片語，或是分類。

>[!NOTE]
>
>依預設，Search&amp;Promote未啟用此功能。 請聯絡技術支援以啟用您使用的功能。 啟用「查詢擴展覆蓋」功能後，您必須在用戶介面中「開啟」它。

**查詢擴展覆蓋的工作方式**

當在「查詢展開覆寫新增」頁面中指定「文字」和「詞語」值時，程式碼會針對特定配對運作。 當分類類型指定為詞語（例如字典或替代字詞表單）時，「不展開」值不會轉換為指定分類所建立的任何表單。

例如，假設您有下列定義：

`Do Not Expand = "dog"`

`Type = Text`

`Term = "dogs"`

搜索「dog」時，「dog」的搜索查詢將不包括「dogs」。

但是，如果定義如下：

`Do Not Expand = "dog"`

`Type = Alternate Word Forms`

查詢不包含&quot;dog&#39;s&quot;或&quot;dogs&quot;（「dog」的替代字詞表格）。

您可以指定多個詞語、多個分類或兩者。 不過，如果您選取「全部」作為「類型」，則任何多詞清單都會收合為單一「全部」項目。

如果文字和分類項目在任何規則中混合，它們會在使用者介面中重新組織，以先顯示文字值。 但是，這並不暗示或影響搜索時的評估順序。

文字詞語經過驗證以移除無意義的參照。 也就是說，它會比較詞語與「不展開」值，並在有相符項目時移除詞語。 此外，也會移除重複的「詞語」值（文字或分類）。

如果您新增具有複製舊定義之「不展開」值的新規則，新定義的「詞語」會新增至原始定義。

## 配置查詢擴展覆蓋{#task_A087354A509D4997BA275186C224160E}

在Search&amp;Promote中定義和新增查詢擴增覆蓋。

<!-- 

t_configuring_query_expansion_overrides.xml

 -->

>[!NOTE]
依預設，Search&amp;Promote未啟用此功能。 請聯絡技術支援以啟用您使用的功能。 啟用「查詢擴展覆蓋」功能後，您必須在用戶介面中「開啟」它。 以下的前幾個步驟概述了如何做到這一點。

**要配置查詢擴展覆蓋，請執行以下操作：**

1. 在Search&amp;Promote中，按一下「設定&#x200B;**** > **使用者** > **檢視角色**」。
1. 在「查看角色」頁的表的「操作」列中，按一下要授予其「語言學」菜單上查詢擴展覆蓋訪問權限的角色右側的&#x200B;**編輯**。
1. 在「編輯角色」頁面上，展開「語言學」樹。
1. 選中&#x200B;**查詢擴展覆蓋** ，然後按一下&#x200B;**保存更改**。
1. 按一下「**語言學** > **查詢擴展覆蓋**」。
1. 按一下&#x200B;**添加查詢擴展覆蓋**。
1. 在「查詢擴展覆蓋添加」頁中，設定所需的選項。

   <!-- 
   
   r_query_expansion_override_definitions.xml
   
   -->

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>選項 </p> </th> 
      <th colname="col2" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>不展開 </p> </td> 
      <td colname="col2"> <p>指定您不想展開的字詞或片語。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>類型 </p> </td> 
      <td colname="col2"> <p>選擇<b>Text</b>以指定特定的字詞或片語配對。 或者，選取分類以指定「不展開」字詞或片語不會透過選取的分類轉換。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>術語 </p> </td> 
      <td colname="col2"> <p>僅當選擇<b>Text</b>作為「類型」時才可用。 指定要從搜索展開中排除的字或片語。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Action </p> </td> 
      <td colname="col2"> <p> 按一下<b>+</b>或<b>-</b>，分別新增或刪除「詞語」至定義。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 完成後，按一下&#x200B;**添加**。

   在「查詢擴展覆蓋定義」頁中，您可以編輯或刪除已添加的定義。
1. 若要預覽新增結果，請按一下藍色方塊中的&#x200B;**重新產生分段網站索引**，以快速重建分段網站索引。
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**Live**。

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)

   * 按一下「推送即時」。****

      請參閱[即時推送階段設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)

