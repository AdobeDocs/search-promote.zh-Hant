---
description: Search&amp;Promote 15.1.1發行說明。
solution: Target
title: Search&amp;Promote 15.1.1發行說明(01/15/2015)
topic-legacy: Release Notes,Site search and merchandising
uuid: 070f9c46-426f-4ca1-80c7-8ca53d40a402
exl-id: 6176ce1e-aafe-4a46-a564-57c3ac4632ef
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 17%

---

# Search&amp;Promote15.1.1發行說明(01/15/2015){#search-promote-release-notes}

## 新功能 {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* 以前，導引搜尋規則的關鍵字一律套用相關字詞、同義字等語言學功能。現在您可以停用此擴充功能，照原樣使用關鍵字。

   當您要將觸發條件套用至業務規則時，在[!DNL Advanced Rule Builder]中&#x200B;**[!UICONTROL If any/all of the following conditions are met]**&#x200B;後面的第一個下拉式清單中，選取&#x200B;**[!UICONTROL keyword]**，然後在第二個下拉式清單中選取新的運算子&#x200B;**[!UICONTROL equal exact]**。

   請參閱[關於業務規則](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD)。

## 修正與增強功能{#section_22D1AFC99F394D569898828A0D3C419D}

* [!DNL Visual Rule Builder] 和 [!DNL Advanced Rule Builder] 不再截斷MDI（銷售檔案ID）欄位值。
* 已修正 RBTA 相關的索引失敗。
* 編輯狀態為「已批准」的現有業務規則，現在會廢止「已核准」狀態。 您必須使用[!DNL Advanced Rule Builder]來重新勾選選項&#x200B;**[!UICONTROL Approved]**，然後依常態儲存規則。 如果您未重新批准編輯的規則，則在[!DNL Business Rules]頁面上，規則的狀態會自動設定為WIP(Work In Progress)。
* [!DNL Business Rules]頁面現在提供新的&#x200B;**[!UICONTROL Advanced Search]**&#x200B;選項，以改善規則篩選。
* 在[!DNL Query Cleaning]、[!DNL Pre-Search Rules]、[!DNL Post Search Rules]和[!DNL Business Rules]中新增&#x200B;**[!UICONTROL contains word]**&#x200B;條件至規則觸發器，讓您輕鬆指定斷字。
* 對業務規則附註所做的改進，例如當您檢視規則時，現在可擷取該規則的附註歷史記錄。 此外，註解現在會記錄在&#x200B;**[!UICONTROL Reports]** > **[!UICONTROL Change Log]**&#x200B;中。
* 具有非零`sp_i`值的查詢不再通過[!DNL Adobe Analytics]重定向器運行。

   請參閱[後端搜尋CGI參數](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)表格中的第15行。
