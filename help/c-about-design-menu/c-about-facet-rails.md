---
description: 使用Facet邊欄可重新排序網頁上的Facet群組。
seo-description: 使用Facet邊欄可重新排序網頁上的Facet群組。
seo-title: 關於Facet邊欄
solution: Target
subtopic: Navigation
title: 關於Facet邊欄
topic: Design,Site search and merchandising
uuid: 6da2bd67-8c20-4955-9836-bc8ba88546c5
translation-type: tm+mt
source-git-commit: 6b3aa733b0dfaace956f0ffc25f433fefd21e15f

---


# 關於Facet邊欄{#about-facet-rail}

使用Facet邊欄可重新排序網頁上的Facet群組。

## 使用Facet邊欄 {#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB}

Facet是屬性或特徵，它是一般分類搜尋結果的方式。 例如，製造商、價格和顏色可視為一組Facet。 每個Facet可以有多個約束或值。 例如，如果您有顏色作為刻面，「刻面值」可能是紅色、橘色、黃色、綠色、藍色、靛藍和紫色。

請參閱 [關於刻面](../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5)。

您可使用Facet Rail來重新排序網頁上的這些Facet群組。 例如，假設您的網頁左側有搜尋結果區段。 列出的區段包括從上到下、類別Facet、品牌Facet、價格Facet和最受歡迎Facet。 例如，您可以使用Facet邊欄，讓「最受歡迎」Facet顯示在「類別」Facet的上方或下方。

您想要一起重新排序的Facet群組屬於Facet邊欄標籤。 Facet只能屬於一個Facet邊欄。 Facet邊欄是「表現」範本標籤，並包含Facet的單一表示。 屬於此邊欄的所有刻面都共用該單一刻面表示。

請參 [閱關於簡報](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5) 範本範本標 [簽中的範本和Facet](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)。

## 設定Facet邊欄 {#task_561A8FF1CAD1402B9DD33E276BBC6A0E}

您可以新增Facet邊欄來自訂您的表現層。 Facet Rails可為客戶提供「引導式搜尋」，讓他們根據網頁上Facet的順序深入探究搜尋結果。

<!-- 

t_configuring_facet_rail.xml

-->

您對Facet滑軌所做的任何變更都可使用「步驟記錄」功能進行還原。

**若要設定Facet邊欄**

1. 在設定Facet邊欄之前，請確定您已新增Facet，並在該工作中指定Facet邊欄名稱。

   請參 [閱新增Facet](../c-about-design-menu/c-about-facets.md#task_FC07BFFA62CA4B718D6CBF4F2855C89B)。
1. 在產品功能表上，按一下 **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Facet Rail.]**
1. 在頁 [!DNL Facet Rail] 面上，選取您要包含在Facet邊欄中的Facet，然後從下拉式清單 **[!UICONTROL Sort Facets Method]** 中設定選項。

   <!-- 
   r_facet_rail_options.xml
   -->

   | 功能／選項 | 說明 |
   |--- |--- |
   | Facet 軌 名稱 | 識別Facet邊欄的名稱。  您在新增Facet時，會建立Facet邊欄的名稱。  請參 [閱新增Facet](../c-about-design-menu/c-about-facets.md#task_FC07BFFA62CA4B718D6CBF4F2855C89B) |
   | 包含的刻面 | 可以選取以新增至Facet邊欄的可能Facet清單。  如果您選擇使用來排 `Custom`序刻面，您在此處選取刻面的順序會決定它們在文字方塊中的 `Custom Facet Order` 顯示順序。 |
   | 排序刻面方法 | 從下拉式清單中的下列三個選項中選擇：<ul><li>`Alpha` 刻面會依字母順序排序，包括標點符號字元。</li><li>`Alpha (not case sensitive)` Facet會依字母順序依名稱排序，忽略字母字元的大小寫，並包含標點符號字元。 </li><li>`Alpha (alphanumeric only)` 刻面會依字母順序依名稱排序，忽略標點符號字元。 </li><li>`Alpha (not case sensitive, alphanumeric only)` 刻面會依字母順序依名稱排序，忽略字母字元的大小寫，並忽略標點符號字元。 </li><li>`Count` 刻面會根據計數排序。 </li><li>`Custom` 開啟文 `Custom Facet Order` 字方塊，讓您輸入每個Facet的確切名稱來定義Facet的順序。 任何遺漏的Facet標籤都會從清單中 `Custom Facet Order` 移除。</li></ul> |
   | 自訂Facet順序 | 只有從下拉式清單中選取 `Custom` 時， `Sort Facets Method` 此選項才可用。  可讓您列出Facet名稱，每行一個，或全部列在一行上，以逗號分隔。 如果定義了Facet標籤，則它們會顯示在列 `Facets Included` 表中，並括在括弧中。  請勿在文字方塊中包含 `Custom Facet Order` Facet標籤。  當您在清單中選取或取消選取Facet `Facets Included` 時，文字 `Custom Facet Order` 方塊會自動更新。 |

1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）在頁 [!DNL Facet Rail] 面上，執行下列其中一項作業：

   * 按一 **[!UICONTROL History]** 下以回復您所做的任何變更。

      請參 [閱使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。

1. 執行下列動作，編輯簡報範本：。

   * 在簡報範本上建立「Facet範本」。
   * 將「facet範本」與標籤包 `<guided-facet-rail>` 圍。

      請參閱「簡報範本 [中的刻面」標籤](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)。

      範例:  

      ```
      <guided-facet-rail>
        <guided-facet>
          <guided-facet-display-name/>
          ...
          </guided-facet>
        </guided-facet-rail>
      ```

      這些標籤會划出簡報範本的一段，以成為Facet邊欄中每個Facet的可重複模式。 屬於刻面軌的每個刻面都使用此刻出的部分來評估其輸出。 最終的簡 `<guided-facet-rail>` 報範本上只能顯示一個標籤。

      下列標籤不需要內部屬 `gsname` 性，因 `<guided-facet-rail>` 為值是在搜尋時動態決定並正確取代的：

      `<guided-facet>`
      `<guided-facet-display-name>`
      `<guided-facet-total-count>`
      `<guided-facet-undo-link>`
      `<guided-facet-undo-path>`
      `<guided-facet-behavior>`

   * 儲存簡報範本並即時推播。

      請參 [閱編輯簡報或傳輸範本](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3)。
