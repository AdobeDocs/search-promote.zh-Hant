---
description: 'null'
seo-description: 'null'
seo-title: Search&amp;Promote 15.1.1發行說明(01/15/2015)
solution: Target
title: Search&amp;Promote 15.1.1發行說明(01/15/2015)
topic: Release Notes,Site search and merchandising
uuid: 070f9c46-426f-4ca1-80c7-8ca53d40a402
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Search&amp;Promote 15.1.1 Release Notes (01/15/2015){#search-promote-release-notes}

## 新功能 {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* 以前，導引搜尋規則的關鍵字一律套用相關字詞、同義字等語言學功能。現在您可以停用此擴充功能，照原樣使用關鍵字。

   When you want to apply trigger conditions to a business rule, in the [!DNL Advanced Rule Builder], following **[!UICONTROL If any/all of the following conditions are met]**, in the first drop-down list, select **[!UICONTROL keyword]**, and then select the new operator **[!UICONTROL equal exact]** in the second drop-down list.

   See [About Business Rules](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

## Fixes and enhancements {#section_22D1AFC99F394D569898828A0D3C419D}

* [!DNL Visual Rule Builder] 和 [!DNL Advanced Rule Builder] 不再截斷MDI（銷售檔案ID）欄位值。
* 已修正 RBTA 相關的索引失敗。
* 編輯狀態為「已批准」的現有業務規則，現在會廢止「已核准」狀態。 You must use [!DNL Advanced Rule Builder] to recheck the option **[!UICONTROL Approved]**, and then save the rule as usual. If you do not reapprove an edited rule, the rule&#39;s status is automatically set to WIP (Work In Progress) on the [!DNL Business Rules] page.
* A new **[!UICONTROL Advanced Search]** option is now available on the [!DNL Business Rules] page for improved filtering of rules.
* 新增 **[!UICONTROL contains word]** 條件至、、、 [!DNL Query Cleaning]和中的規則觸發 [!DNL Pre-Search Rules][!DNL Post Search Rules][!DNL Business Rules]器，讓您輕鬆指定斷字。
* 對業務規則附註所做的改進，例如當您檢視規則時，現在可擷取該規則的附註歷史記錄。 此外，註解現在會登入 **[!UICONTROL Reports]** > **[!UICONTROL Change Log]**。
* Queries with nonzero `sp_i` values are no longer run through the [!DNL Adobe Analytics] redirector.

   請參閱後端搜尋CGI參數 [表格中的第15行](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。

