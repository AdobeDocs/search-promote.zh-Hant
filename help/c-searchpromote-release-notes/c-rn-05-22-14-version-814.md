---
description: Search&amp;Promote 8.14.0發行說明。
solution: Target
title: Search&amp;Promote 8.14.0發行說明(05/22/2014)
topic: 發行說明、網站搜尋與銷售
uuid: 308d84a9-ec38-4fec-b146-e8a353e65be4
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 63%

---


# Search&amp;Promote8.14.0發行說明(05/22/2014){#search-promote-release-notes}

**修正**

* 如果 [!DNL sqlite_open] 失敗，舊 SQLite 資料庫檔案便會退位，並重新產生新的資料庫檔案。
* 若重覆執行相同的搜尋，核心搜尋結果會不一致。
* 在每個搜尋結果輸出許多欄位的情況下，範本處理的績效已改良。
* 新增附註至&#x200B;**[!UICONTROL Business Rule History]**。
* 編列索引期間，結果型引動因素以及動作預覽式索引重新產生階段的績效會隨時間的推移而逐漸下降。
* 將&#x200B;**[!UICONTROL Reset SPIN cache]**&#x200B;選項從布林值no/next-run變更為三態：no/always/next-run。

