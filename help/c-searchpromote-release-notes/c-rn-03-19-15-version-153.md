---
description: 'null'
seo-description: 'null'
seo-title: Search&amp;Promote 15.3.1發行說明(03/24/2015)
solution: Target
title: Search&amp;Promote 15.3.1發行說明(03/24/2015)
topic: Release Notes,Site search and merchandising
uuid: f02da5a4-2207-4603-aa05-5cff7be16dd5
translation-type: tm+mt
source-git-commit: ffdec2cfcb30e733c664a7d1ca23868b7a9a9aa5

---


# Search&amp;Promote 15.3.1 Release Notes (03/24/2015){#search-promote-release-notes}

## 新功能和增強功能 {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* 搜尋產品模型編號——新增「語言學」設定，可讓您選擇在字母——數值轉換時分割代號。 此功能可讓部分或產品樣式Token的自由文字比對更有彈性。

   請參 **[!UICONTROL Partial Alphanumeric Matching]** 閱 [設定搜尋詞與您網頁內容的匹配方式……](../c-about-linguistics-menu/c-about-words-and-language.md#task_351A9144A51F4B41923BDBACDEF3B616).

* 新增匯出資料檢視結果的功能。

   請參 [閱資料檢視](../c-about-reports-menu/c-about-data-views.md#concept_DCA897D074464BC1861AA47B40CC86C3)。

* 動態產生範圍屬性的範圍自動Facet值分組功能。

   Adobe Systems目前要求您提供識別範圍值的內容，以執行此動作。 例如，若價格為10，請產生範圍字串&quot;介於$10和$20&quot;)。 或者，Adobe Systems要求您使用原稿篩選。 新增屬性至中繼資料欄位定義，僅適用於 `Type=Number` 欄位。 新選項將數字欄位與欄位關聯， `Type=Text` 並指定說明如何構建範圍說明的配置資訊。

   請參 [閱新增中繼標籤欄位](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。

## 修正 {#section_22D1AFC99F394D569898828A0D3C419D}

* Facet邊欄編輯對話方塊應包含分段的Facet。
* 「內嵌」搜尋模式的核心搜尋結果空白，包含日文字元的搜尋結果空白。
* Word .docx檔案的Tika轉換現在會填入屬 `title` 性。
* 已更正管理員中錯誤的「重複橫幅」 **[!UICONTROL Banner]** 訊息。
* [!DNL Dynamic Media Classic] 橫幅現在不受通訊協定限制。
* 在「 **[!UICONTROL Table Name]** 中繼資料」使用者介面中編輯使用者定義的欄位時，欄位屬性有時會隱藏，即使 **[!UICONTROL Dynamic Facets]** 已啟用帳戶亦然。
* **[!UICONTROL Recent Searches]** 不再對非ASCII字元進行乘法編碼。
* MDI欄位無需使用指令碼過濾即可填入。
* 建議中的編碼錯誤。
* 「其他選取的Facet」觸發程式現在可正確處理複雜的業務規則。

