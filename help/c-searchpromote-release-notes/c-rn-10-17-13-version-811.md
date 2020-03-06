---
description: 'null'
seo-description: 'null'
seo-title: Search&amp;Promote 8.11.0發行說明(10/29/2013)
solution: Target
title: Search&amp;Promote 8.11.0發行說明(10/29/2013)
topic: Release Notes,Site search and merchandising
uuid: 973f9608-a5c7-4571-ae2b-6f1fa05bc862
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Search&amp;Promote 8.11.0 Release Notes (10/29/2013){#search-promote-release-notes}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>新功能 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 丹麥文分解器 </p> </td> 
   <td colname="col2"> <p> A mechanism is now provided to allow <span class="keyword"> Adobe Search&amp;Promote</span> to access the language (Danish) detection, decompounding, stemming and segmentor services provided by Adobe. </p> </td> 
  </tr> 
 </tbody> 
</table>

**改良和修正**

* Enhancements made to the existing [!DNL Search&Promote] table matching capabilities. 此次改良對 SKU 和產品資料間日益複雜的關係相關的客戶需求，提供更好的支援。

   >[!NOTE]
   >
   >此功能預設未啟用。 若想在 Search&amp;Promote 中啟用此功能，請聯絡 Adobe 客戶服務。

* 新增搜尋指南可根據帳戶的語言設定來排序刻面的選項。

   >[!NOTE]
   此功能預設未啟用。 若想在 Search&amp;Promote 中啟用此功能，請聯絡 Adobe 客戶服務。

* 新增可增加刻面值的數目，以供使用者為多選刻面指定的選項。

   >[!NOTE]
   此功能預設未啟用。 若想在 Search&amp;Promote 中啟用此功能，請聯絡 Adobe 客戶服務。

* 已將核取方塊選 **[!UICONTROL Only allow searches that use HTTPS]** 項新 **[!UICONTROL Settings]** 增至 **[!UICONTROL Searching]** > **[!UICONTROL Restrictions]**。

   請參閱 [關於限制](../c-about-settings-menu/c-about-searching-menu.md#concept_B5B527E04EBF4E9AB5956EEF881DDBF1)。

* 新增選項至 **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]** > **[!UICONTROL Create Feed]** >以保留精靈面 **[!UICONTROL Generic Feed]**[!DNL File Submission] 板中的標籤字元。

   請參閱 [建立動態消息](../c-about-settings-menu/c-about-searching-menu.md#task_63179C1FC359497483CD6CE13FD1C250)。

* 將新刻面定義的每個上方和下方欄位中，所接受的資料大小從 80 個字元增加到 1000 個字元。

   請參閱 [關於刻面](../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5)。

* 引導式搜尋除錯參數現在可正確報告業務規則編號。
* 業務規則現在可套用至即時環境。
* 對於設定「語言 = 丹麥文 (丹麥)」的帳戶，依據緯度/經度搜尋時，鄰近地區搜尋現在可以運作。
* 現在可以觸發未指派計劃的結果型觸發器。
* 現在，使用>中的選項時，會 **[!UICONTROL Ignore Apostrophes]** 報告一致 **[!UICONTROL Linguistics]** 的結果 **[!UICONTROL Words & Language]**。

   請參 [閱關於字詞和語言](../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79)。

* 自動完成文字清單使用者介面現在適用於大量刻面。

