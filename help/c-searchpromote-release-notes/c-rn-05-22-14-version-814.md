---
description: 'null'
seo-description: 'null'
seo-title: Search&amp;Promote 8.14.0發行說明(05/22/2014)
solution: Target
title: Search&amp;Promote 8.14.0發行說明(05/22/2014)
topic: Release Notes,Site search and merchandising
uuid: 308d84a9-ec38-4fec-b146-e8a353e65be4
translation-type: tm+mt
source-git-commit: ffdec2cfcb30e733c664a7d1ca23868b7a9a9aa5

---


# Search&amp;Promote 8.14.0 Release Notes (05/22/2014){#search-promote-release-notes}

**修正**

* 如果 [!DNL sqlite_open] 失敗，舊 SQLite 資料庫檔案便會退位，並重新產生新的資料庫檔案。
* 若重覆執行相同的搜尋，核心搜尋結果會不一致。
* 在每個搜尋結果輸出許多欄位的情況下，範本處理的績效已改良。
* 新增附註至 **[!UICONTROL Business Rule History]**。
* 編列索引期間，結果型引動因素以及動作預覽式索引重新產生階段的績效會隨時間的推移而逐漸下降。
* Changed **[!UICONTROL Reset SPIN cache]** option from boolean no/next-run to a tri-state: no/always/next-run.

