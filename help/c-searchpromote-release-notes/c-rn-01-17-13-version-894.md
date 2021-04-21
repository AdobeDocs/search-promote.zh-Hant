---
description: Search&amp;Promote 8.9.4發行說明。
solution: Target
title: Search&amp;Promote 8.9.4發行說明(01/17/2013)
topic-legacy: Release Notes,Site search and merchandising
uuid: a9d550f6-0a23-4c71-b123-c31b997e7384
exl-id: cb5d93d9-54ac-4b41-96ad-66f18ee1e934
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 30%

---

# Search&amp;Promote8.9.4發行說明(01/17/2013){#search-promote-release-notes}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>新功能和增強功能 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>規則 </p> </td> 
   <td colname="col2"> <p> 新加入在建立「查詢清除規則」、「搜尋前規則」及「搜尋後規則」時可以建立內嵌附註的功能。附註欄位可以記錄及說明規則。 </p> <p>請參閱<a href="../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C" format="dita" scope="local">關於查詢清除規則</a>。 </p> <p>請參閱<a href="../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F" format="dita" scope="local">關於預搜索規則</a>。 </p> <p>請參閱<a href="../c-about-rules-menu/c-about-post-search-rules.md#concept_AF6ADFCC0ADF4A788003964939917FDE" format="dita" scope="local">關於搜尋後規則</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>搜尋指南 </p> </td> 
   <td colname="col2"> <p> 新增「搜尋指南」標籤，以指出搜尋所花費的總時間。 </p> <p> <span class="codeph"> &lt;guided-search-time&gt;</span> -標識搜索所花費的時間。返回的搜索時間值以毫秒指定。 </p> <p> <span class="codeph"> &lt;guided-fall-through-searches&gt;</span> -返回用於生成搜索結果頁的內核搜索計數。 </p> <p> <span class="codeph"> &lt;guided-if-fall-through-search&gt;</span> -測試核心搜尋的計數是否大於1。 </p> <p>另請參閱<a href="../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64" format="dita" scope="local">演示模板標籤</a>中的其他語言。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**修正**

* 「詞語報表」現在會忽略星號。

   請參閱[檢視詞語報表或Null搜尋詞報表……](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A)。

* 開啟&#x200B;**[!UICONTROL Reports > Null Search Terms Report]**，選取時段，然後檢視報表。 按一下報表中的一個字可開啟搜尋，然後再按一下「檢視報表」。您按下關鍵字時搜尋計數會增加兩次。現在這個問題已經修正。

   請參閱[檢視詞語報表或Null搜尋詞報表……](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A)。

* 當您推播業務規則時，已進行效能最佳化。

   請參閱[關於業務規則](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD)。

* 在[!DNL Breadcrumbs]中移除的功能不會一直運作。

   請參閱[關於Breadcrumbs](../c-about-design-menu/c-about-breadcrumbs.md#concept_FB8A943C594A4A1593B118141DA61F03)。

* 除非您使用重新產生，否則重新排名功能不允許任何變更的排名規則在搜尋結果中生效。

   請參閱[關於排名規則](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397)。

   請參閱[關於重新排名索引](../c-about-index-menu/c-about-re-rank-index.md#concept_147B0A9FCD51451787DA898E06F7C692)。
