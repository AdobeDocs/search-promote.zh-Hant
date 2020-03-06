---
description: 'null'
seo-description: 'null'
seo-title: Search&amp;Promote 8.16.0發行說明(9/18/2014)
solution: Target
title: Search&amp;Promote 8.16.0發行說明(9/18/2014)
topic: Release Notes,Site search and merchandising
uuid: 0a59858b-213b-40d6-aea1-d085c4d6d2fa
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Search&amp;Promote 8.16.0 Release Notes (9/18/2014){#search-promote-release-notes}

## Search&amp;Promote 8.16.0 Release Notes (9/18/2014) {#topic_5BECD3F66C684987828F6AE65E62DA29}

## New features {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* 在引導式搜尋3(GS3)中快取搜尋結果——若要為您設定此自訂功能，以便您在帳戶中使用，請連絡您的Adobe技術帳戶管理員。
* 經常變更欄位的垂直更新——您現在可以快速更新一組中繼資料欄位的所有值，而不需要完全重新索引內容。

   請參閱「新增新中繼標籤欄位」和「關於 [垂直更新」中表格中的「垂直更新](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)[欄位」選項](../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899)。

   This feature can only be used on [!DNL Adobe Search&Promote] accounts that use Index Connector. 若要設定此自訂功能將其用於帳戶中，請連絡您的 Adobe Technical 帳戶管理員。

## Fixes and enhancements {#section_22D1AFC99F394D569898828A0D3C419D}

* Corrected the Index Connector parsing of XML feeds that contained `?>` string.
* 已修正強制實施最低文件計數時的「索引連接器 SFPT」傳送。
* 匯出報表至 Microsoft Excel 的功能現在支援 UTF8。
* 引導式搜尋: 面向編譯緩慢。
* 屬性載入程式: 彙總資料具有重複金鑰。
* 已修正推送個別執行中規則時的錯誤業務規則執行順序。
* 引導式搜尋會產生錯誤的面向「復原」連結。
* 新增的遠端控制作業 (`sp_lines=N`) 可讓您檢查目前執行之索引編目的進度與狀態。

   請參 [閱關於遠程控制索引](../c-about-index-menu/c-about-remote-control-for-indexing.md#concept_C79B322190E84106A434E5C6D4A4118F)。

* 在「索引連接器」增加期間提取刪除資訊時，需要傳送授權資訊。
* The [!DNL Change Log] report now identifies the user who initiates a manual index operation.

   See [Viewing the Change Log](../c-about-reports-menu/c-about-reports-menu.md#task_166F1156719F4B3D834BEA8E249C8057).

* When you export a [!DNL Terms Report], you are no longer limited to 500 or less items in the report.

   請參 [閱檢視詞語報表或空搜尋詞報表……](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A).

* 索引連接器 **[!UICONTROL Strip HTML]** 設定一律顯示為已勾選。
* Inconsistent search results were experienced with the **[!UICONTROL Common Phrases]** feature.
* 「規則清單」摘要在顯示屬性名稱時會將名稱截斷。
* 推送個別執行中的「業務規則」時，會推送所有執行中的「業務規則」。

