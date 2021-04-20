---
description: Search&amp;Promote 8.9發行說明。
solution: Target
title: Search&amp;Promote 8.9發行說明(07/19/2012)
topic: Release Notes,Site search and merchandising
uuid: 3853c75d-19ed-4e36-9e81-dcbffe5f5b0c
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 57%

---


# Search&amp;Promote8.9發行說明(07/19/2012){#search-promote-release-notes}

**新功能**

* 中繼資料管理改進——來自客戶饋送的動態中繼資料定義

   建立配置，可根據客戶提供的中繼資料定義，動態重新設定您的 Search&amp;Promote 帳戶。
* 索引效能改進——索引載入器

   「索引載入器」是將 XML 內容直接匯入至 Search&amp;Promote 索引的新方法。這是現有「索引連接器」功能的子集，專門設計來快速匯入標準 XML 饋送檔案。

**修正和增強功能**

* 已新增支援依據業務規則而變更排序選項。
* 在「說明」系統`<search-description>`標籤中，當描述的meta標籤包含空內容時，會改為顯示內文。
* 已新增功能，可以針對結果，追蹤經由基於結果之動作而新增的適用表格點擊。
* 新增支援透過POST提交查詢參數
* 在編目時，有時候可以略過最終 mirror_account 操作。
* Adobe AnalyticsURL不包含CGI引數和Adobe Analytics查找所需的Search&amp;Promote代碼，以便從URL鍵中類似地刪除CGI引數。
* 重寫規則推送至現時後，在使用者介面中會間斷消失。
* 具有「您是指」設定的Search&amp;Promote帳戶若因結果低而設定為建議，可能會產生間歇性結果。
* 重寫規則測試輸出沒有分行符號。
* 「搜尋 URL 規則」頁面和「編目清單儲存 URL 規則」頁面指向錯誤的歷史頁面。
* 點按某些橫幅廣告上的「編輯」不會顯示「編輯」頁面。
* 重新排名更新程式碼有時候會異常緩慢。
* 如果 facet 名稱使用大小寫混合，移除或推送 facet 項目無法運作。

