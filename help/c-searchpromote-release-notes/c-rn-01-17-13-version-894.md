---
description: 'null'
seo-description: 'null'
seo-title: Search&amp;Promote 8.9.4發行說明(01/17/2013)
solution: Target
title: Search&amp;Promote 8.9.4發行說明(01/17/2013)
topic: Release Notes,Site search and merchandising
uuid: a9d550f6-0a23-4c71-b123-c31b997e7384
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Search&amp;Promote 8.9.4 Release Notes (01/17/2013){#search-promote-release-notes}

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
   <td colname="col2"> <p> 新加入在建立「查詢清除規則」、「搜尋前規則」及「搜尋後規則」時可以建立內嵌附註的功能。附註欄位可以記錄及說明規則。 </p> <p>請參 <a href="../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C" format="dita" scope="local"> 閱關於查詢清除規則</a>。 </p> <p>See <a href="../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F" format="dita" scope="local"> About Pre-Search Rules</a>. </p> <p>See <a href="../c-about-rules-menu/c-about-post-search-rules.md#concept_AF6ADFCC0ADF4A788003964939917FDE" format="dita" scope="local"> About Post-Search Rules</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>搜尋指南 </p> </td> 
   <td colname="col2"> <p> 新增「搜尋指南」標籤，以指出搜尋所花費的總時間。 </p> <p> <span class="codeph"> &lt;guided-search-time&gt;</span> —— 識別搜尋所花費的時間。 返回的搜索時間值以毫秒指定。 </p> <p> <span class="codeph"> &lt;guided-fall-through-searches&gt;</span> —— 傳回用於建立搜尋結果頁面的核心搜尋計數。 </p> <p> <span class="codeph"> &lt;guided-if-fall-through-search&gt;</span> —— 測試核心搜尋的計數是否大於1。 </p> <p>另請參閱簡報範本標 <a href="../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64" format="dita" scope="local"> 記中的其他語言</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**修正**

* 「詞語報表」現在會忽略星號。

   請參 [閱檢視詞語報表或空搜尋詞報表……](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A).

* 開啟「報表 > 空搜尋詞語報表」，選取時段，然後檢視報表。按一下報表中的一個字可開啟搜尋，然後再按一下「檢視報表」。您按下關鍵字時搜尋計數會增加兩次。現在這個問題已經修正。

   請參 [閱檢視詞語報表或空搜尋詞報表……](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A).

* 即時推進「業務規則」時，會進行效能最佳化。

   See [About Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* 導覽列中的移除功能有時會失常。

   請參 [閱Breadcrumbs](../c-about-design-menu/c-about-breadcrumbs.md#concept_FB8A943C594A4A1593B118141DA61F03)。

* 除非您使用「重新產生」，否則「重新排名」功能不允許任何變更的「排名規則」在搜尋結果中生效。

   請參閱[關於排名規則](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397)。

   請參 [閱關於重新排名索引](../c-about-index-menu/c-about-re-rank-index.md#concept_147B0A9FCD51451787DA898E06F7C692)。

