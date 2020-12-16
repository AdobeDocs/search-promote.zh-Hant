---
description: 'null'
seo-description: 'null'
seo-title: Search&amp;Promote 8.13.0發行說明(04/16/2014)
solution: Target
title: Search&amp;Promote 8.13.0發行說明(04/16/2014)
topic: Release Notes,Site search and merchandising
uuid: b3524992-ff00-4a7c-a404-078242456734
translation-type: tm+mt
source-git-commit: 9d5ac055d665b39d09b28063179d74a389d7f830
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 57%

---


# Search&amp;Promote 8.13.0發行說明(04/16/2014){#search-promote-release-notes}

| 新功能和增強功能 | 說明 |
|----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 「動態面」含完整表格比對支援 | 有些客戶有許多「SKU層級」屬性，他們想要透過動態Facet來選擇和顯示。 根據這種方式，您可選擇在靜態帳戶設定中，為每一個動態面欄位與最多一個表格建立關聯。您就能在搜尋時，為搜尋涉及的任何動態面欄位套用這些表格。請參閱[關於動態數值](../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899)。 |

**修正**

* 已將資料檢視說明欄位變更為使用`<search-display-field>`標籤，而非`<search-description>`。
* 將功能新增至「索引連接器」使「主索引鍵」成為兩個或更多欄位的串連。
* 將 AttributeLoader-Regen-Enabled 指令檔 `attributeloader-regen.pl` 變更為非 HTML 編碼的值。
* 讓用於「範圍搜尋」查詢的索引時與搜尋時空白字元處理方式相符。
* 新增業務規則有時會導致在啟用「動態面」時發生錯誤。

   請參閱[關於業務規則](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD)。

* Javascript錯誤導致無法在&#x200B;**Settings** > **SPIN** > **IndexConnector**&#x200B;中新增或編輯定義。
* 保存業務規則後，在建立業務規則期間選擇該時間時，它將預設為GMT時區。 在儲存規則後，就會顯示帳戶的時區並且生效。

   請參閱[關於業務規則](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD)。

* 測試階段中的業務規則排序無法正常運作。

   請參閱[關於業務規則](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD)。

* 搜尋績效報表是一項可讓您能夠排程以電子郵件傳送報表的增強功能。
* 業務規則修正的排程自動變更為「日光節約時間」。

   請參閱[關於業務規則](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD)。

* 如果定義了大量動態Facet欄位，使用者會經歷緩慢的核心搜尋回應時間。
* 發生偽範圍索引錯誤。
* 非北美洲資料中心的Dynamic Media Classic存取中斷。
* SPIN XPath 驗證功能傳回誤判錯誤。

* 在 SPIN 啟用/停用作業之後，系統將使用者重導至成員中心登入畫面。

