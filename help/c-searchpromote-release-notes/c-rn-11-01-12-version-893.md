---
description: Search&amp;Promote 8.9.3發行說明。
solution: Target
title: Search&amp;Promote 8.9.3發行說明(11/01/2012)
topic: Release Notes,Site search and merchandising
uuid: 7bc7bcb6-f47f-4e05-94e5-a22a13a187b7
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 79%

---


# Search&amp;Promote8.9.3發行說明(11/01/2012){#search-promote-release-notes}

## Search&amp;Promote8.9.3發行說明(11/01/2012){#concept_85F5B4B4C40C43FEA3AD63E6EA5593CF}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>新功能和增強功能 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Facet 軌 </p> </td> 
   <td colname="col2"> <p> 
     <!--3309390-->新增<span class="uicontrol">「Facet 軌」</span>選項，協助控制 Facet 系列和 Facet 名稱的排序 (依據計數、字母順序)。 </p> <p>請參閱<a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local">關於 Facet 軌</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 巢狀 Facet </p> </td> 
   <td colname="col2"> <p> 新增支援巢狀 Facet 的其他排序方法。 </p> <p>請參閱<a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local">關於 Facet 軌</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>排名規則中的附註欄位 </p> </td> 
   <td colname="col2"> <p> 
     <!--3063772-->新增多行<span class="wintitle">「附註」</span>欄位至<span class="wintitle">「新增排名量度」</span>對話方塊及<span class="wintitle">「編輯排名量度」</span>對話方塊，用於排名規則和規則群組定義。 </p> <p>排名規則附註會顯示在<span class="wintitle">「定義排名規則」</span>頁面上。規則群組附註則在編輯定義時顯示。 </p> <p>請參閱<a href="../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397" format="dita" scope="local">關於排名規則</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>業務規則 </p> </td> 
   <td colname="col2"> <p> 
     <!--3331637-->改進著陸頁面支援，使用新的<span class="uicontrol">「移除所有結果」</span>選項，移除業務規則中的免費結果。 </p> <p>將此新選項搭配其他業務規則動作使用，可建立「罐裝著陸頁面」。也就是說，您想要以獨家業務規則動作建立頁面內容，且需要捨棄搜尋的「免費」結果。 </p> <p>請參閱<a href="../c-about-rules-menu/c-about-business-rules.md#task_BD3B31ED48BB4B1B8F1DCD3BFA2528E7" format="dita" scope="local">新增業務規則</a>或<a href="../c-about-rules-menu/c-about-business-rules.md#task_375CFA75D1D94D9E92A35DE1228E5087" format="dita" scope="local">編輯業務規則</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>橫幅廣告和業務規則 </p> </td> 
   <td colname="col2"> <p> 新增支援選項，可讓您在參考橫幅廣告的業務規則是即時推送時，有條件退出即時推送該橫幅廣告。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**修正**

* 當有[!DNL Stage]索引時，業務規則的運作不一致。
* 自動排名規則現在套用至罐裝著陸頁面。

   請參閱[新增排名規則](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A)中的選項表。

* [!DNL promosearch.cgi] 不是退回促銷。

   請參閱[關於搜尋](../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8)。

* 推送參考許多橫幅廣告的規則有時候會失敗。

   請參閱[關於橫幅廣告](../c-about-design-menu/c-about-banners.md#concept_5BBE01FEC6134393B43CC917C8CC64DA)。

* **[!UICONTROL Did You Mean]** 搜尋查詢快取現在已停用。

   請參閱[關於您的意思是](../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E)。

