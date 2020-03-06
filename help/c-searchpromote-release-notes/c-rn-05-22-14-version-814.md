---
description: 'null'
seo-description: 'null'
seo-title: Search&amp;Promote 8.14.0發行說明(05/22/2014)
solution: Target
title: Search&amp;Promote 8.14.0發行說明(05/22/2014)
topic: Release Notes,Site search and merchandising
uuid: 308d84a9-ec38-4fec-b146-e8a353e65be4
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Search&amp;Promote 8.14.0 Release Notes (05/22/2014){#search-promote-release-notes}

**修正**

* 如果 [!DNL sqlite_open] 失敗，舊 SQLite 資料庫檔案便會退位，並重新產生新的資料庫檔案。
* 若重覆執行相同的搜尋，核心搜尋結果會不一致。
* 在每個搜尋結果輸出許多欄位的情況下，範本處理的績效已改良。
* 已將附註加入業務規則歷史記錄。
* 編列索引期間，結果型引動因素以及動作預覽式索引重新產生階段的績效會隨時間的推移而逐漸下降。
* **重設 SPIN 快取** 選項從布林 (無/下次執行) 變成三態: 無/永遠/下次執行。

