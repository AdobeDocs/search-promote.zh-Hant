---
description: 您可以使用「搜尋後規則」來檢查搜尋結果，並判斷搜尋對顯示內容有何影響。
seo-description: 您可以使用「搜尋後規則」來檢查搜尋結果，並判斷搜尋對顯示內容有何影響。
seo-title: 關於搜尋後規則
solution: Target
title: 關於搜尋後規則
topic: Rules,Site search and merchandising
uuid: 312d1e4a-f5b6-4629-8645-17e6f6c09fc4
translation-type: tm+mt
source-git-commit: d07cdc2c88f93eed4cecb0ee8818f7fdea06ee9d

---


# 關於搜尋後規則{#about-post-search-rules}

您可以使用「搜尋後規則」來檢查搜尋結果，並判斷搜尋對顯示內容有何影響。

## 使用搜尋後規則 {#concept_AF6ADFCC0ADF4A788003964939917FDE}

如果搜尋沒有結果，「搜尋後規則」可以執行類似項目的搜尋。 或者，它可顯示網頁，向搜尋找不到項目的客戶建議其他項目。

每個搜尋後規則都包含兩個主要元素：規則的動作及其可選條件。 您可以指定不限數目的規則和條件。 這些規則的順序很重要，因為規則集是循環規則。 當規則的條件符合時，會執行所有相關的動作。

您最多可以調整搜尋結果集，進行三輪搜尋。 在此之後，會使用目前可用的項目。 此限制可防止無限回圈，並確保客戶收到有效的回應。 重做搜尋的次數越多，傳回搜尋結果所花的時間就越長。 如果匹配規則未更改當前使用的演示模板的搜索或切換模板，則搜索結果集將被視為已完成並退出搜索後。

搜尋後處理建立在較早的處理模組查詢清除和搜尋前處理之上。 因此，這些模組中的任何自訂變數集都可用於搜尋後處理規則。 同樣，預搜索處理已實例化所有模板，其中與演示模板關聯的每個命名搜索都有其自己的CGI參數本地副本。 反過來，您可以個別自訂每個搜尋。

請參 [閱關於查詢清除規則](../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C)。

See [About Pre-Search Rules](../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F).

## 關於搜尋後規則條件 {#section_C43EB77CC0AC43B8B9D38569264BF1B5}

條件是可選的。 如果您指定每個查詢都指定了動作，則一律會執行這些動作。 您可以根據先前規則所設定的任何CGI查詢參數、Cookie、搜尋結果或自訂變數來設定條件。 或者，您也可以根據系統條件（例如目前選取的範本是什麼或是最後一次搜尋）來進行搜尋。 在搜索或CGI參數的結果上建立條件時，可指定模板和搜索名稱。

## 關於搜尋後規則動作 {#section_0E15FE683A894ECAAA386267EEC7F7C5}

「搜尋後規則」中具有相符條件的所有動作都會執行。 操作通常包括操作、要執行操作的資料以及要使用的值。 最簡單的動作是根據搜尋後規則的條件來切換要使用的簡報範本。 您可以使用更多進階動作來變更搜尋參數，以重新執行搜尋。 對模板的搜索參數執行操作時，請指定「演示」模板並進行搜索。

## 一般規則 {#section_AEE923988CC748FF9DEF2233FBF333B5}

對模板的搜索參數執行操作時，存在兩個特殊值，分別是「演示」模板的*targeted和*primary，以及命名搜索。 使用這些值可根據目前定位範本的主要搜尋來建立規則。 這些結構可讓您建立一般規則，而不需擔心目前的目標範本或主要搜尋被叫用的項目。 如果此傳遞是搜尋後處理的第一個傳遞，則目標範本是任何搜尋前處理設定的範本。

## 重新導向 {#section_E5669A2F13C240F2968E31C75591CD6A}

「查詢清除」中的直接點擊和重新導向可讓您根據傳入的搜尋詞重新導向至URL。 搜尋後規則中的重新導向延伸了這個概念，但可讓您檢查搜尋傳回了多少結果，然後決定是否要進行重新導向。 使用「搜尋後規則」，您可以重新導向至URL，以取代自訂變數或查詢參數。 或者，您可以重新導向至第一個結果中的欄位。 當您重新導向至結果欄位時，您會在「傳輸」範本中定義欄位，且欄位必須包含有效、明確的URL，否則會略過重新導向。

當您在「搜尋後規則」中使用重新導向機制時，可以偵測搜尋何時傳回單一結果。 您不必傳回此類結果，而是可以重新導向至與結果關聯的網頁。

如需將重新導向與「搜尋後規則」搭配使用的範例，請參閱下列重新導向範例。

## 上一個規則 {#section_FC1E0050C9324278B171038E98F6C335}

當符合設定選項之規則的條件時，後 **[!UICONTROL Last Rule]** 期搜尋處理模組不會在符合規則的動作後執行任何其他規則。 當您已設定動作，讓稍後的規則符合但您希望處理停止時，此情況會很有用。 而且，在後續的搜尋後，該規則可能會符合。

## 範例 {#section_DDB98383690941F9B44AD00FBA55BB56}

在以下範例中，假設您有兩個簡報範本。 一個模板用於顯示許多搜索結果，另一個模板用於顯示單個結果以及對與主搜索相關的附件的額外搜索。 您想要偵測到單一結果，並切換至其他簡報範本。 要完成此任務，可以使用以下規則：

```
On condition: 
  targeted template is default 
  targeted template primary results equal 1 
  not last search 
Perform the following actions: 
  Set targeted template to product_spotlight
```

MegaElectronic是大型電子商店。 在分析其搜尋資料後，MegaElectronic注意到許多客戶使用產品的零件號來執行產品搜尋。 在這種情況下，如果客戶直接搜尋產品，而且只找到單一產品，MegaElectronic會想要重新導向至與產品相關聯的網頁。

若要達成此結果，您可以使用包含3個條件的單一規則。 第一個條件會檢查傳回的搜尋是否只有單一結果。 第二個條件會確保查詢詞語符合MegaElectronic的零件編號格式，以取得他們要造成重新導向的結果。 第三個條件可確保客戶不會使用任何刻面來深入探究一個結果，因為部件號可能是部分部件號並返回多個結果。 動作會重新導向至結果中的欄位。

```
On condition: 
  targeted template's primary results equal 1 
  query q matches regular expression ^\D\D\D-\d+ 
  no facet selected ^\D\D\D-\d+ 
Perform the following actions: 
  redirect to result field "loc" in template *targeted for search *primary
```

## 最佳實務 {#section_1BF7DE1BD5664B3BAEC26AA829FDB0BA}

* 任何觸發新一輪搜尋的規則集一律應包含條件子句，以檢查這是否不是模組的最後一次傳遞。 如果已執行了最大搜索數，則無法重做任何搜索。
* 如果您是上次通過模組時，結果仍然較差，則可以切換到「無結果」模板。
* 您應根據可能具有其他參數的搜尋結果來變更簡報範本。 如果您只想選取僅以傳入查詢為基礎的範本，則搜尋前規則會更有效率。
* 在查詢清理模組中對查詢進行資料挖掘。 您可以在搜尋後處理中參考自訂變數。
* 當您進行重新導向時，請務必檢查客戶是否未選取任何面。 原因是當客戶鑽研至Facet，突然從搜尋結果中移除時，不方便。 當客戶發現單一結果不想要尋找時，可能會想要取消選取Facet。

## 新增搜尋後規則 {#task_52F6F9AAD65B45B5ACA1FF245DFFADD9}

您可以使 [!DNL Post-Search Rules] 用來選擇用於根據傳入查詢顯示搜索結果的演示模板。

**若要新增搜尋後規則**

1. 在產品功能表上，按一下 **[!UICONTROL Rules]** > **[!UICONTROL Post-Search Rules]**。
1. 在頁面上 [!DNL Post-Search Rules] ，按一下 **[!UICONTROL Add New Rule]**。
1. 在欄位 [!DNL Name] 中，鍵入新查詢清除規則的名稱。
1. 在頁面 [!DNL Add Post-Search Rule] 上，使用下拉式清單和文字欄位來建立查詢。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>選項 </p> </th> 
      <th colname="col2" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Cookie </p> </td> 
      <td colname="col2"> <p>HTTP Cookie。 Cookie名稱和值必須經過統一資源識別碼編碼。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>自訂變數 </p> </td> 
      <td colname="col2"> <p>使用者定義的變數。 您可以新增、刪除或設定不限數量的自訂變數。 </p> <p>您可以參考您在「查詢清除」和「搜尋前規則」模組中，在「搜尋後規則」中定義的任何自訂變數。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>系統變數 </p> </td> 
      <td colname="col2"> <p>可檢查的內部系統所設定的唯讀變數。 支援下列系統變數： </p> <p> 
        <ul id="ul_BC17F1637F27424CA4E8F530C28A3245"> 
          <li id="li_C7DF96EFD7AA4A449D00F7EACCAA0EB1"> <span class="uicontrol"> 主機名 </span> <p>伺服器主機的名稱。 </p> </li> 
          <li id="li_F85AB1D2B9374A859657D12B8ED6674B"> <span class="uicontrol"> uri </span> <p>沒有查詢字串的請求的統一資源標識符。 </p> </li> 
          <li id="li_440149C9EC6E4805B77BBC97BE41542A"> <span class="uicontrol"> args </span> <p>整個查詢字串。 </p> </li> 
          <li id="li_F583FC4B0E404858BB3522B33A6F7A0A"> <span class="uicontrol"> 環境 </span> <p>「階段」或「即時」，視傳入查詢是傳送至您的分段環境還是即時環境而定。 </p> </li> 
          <li id="li_15902AA49B144D42A5E95D7E8B0FB1E1"> <span class="uicontrol"> referrer </span> <p>客戶來自的統一資源貨位。 </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>系統變數 </p> </td> 
      <td colname="col2"> <p>可用於條件中以決定目前狀態的唯讀變數。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>範本的搜尋Facet </p> </td> 
      <td colname="col2"> <p>與簡報範本相關聯之命名搜尋的本機Facet。 Facet實質上是特殊的CGI參數，用於指示客戶在Facet中選擇了哪個值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>範本的搜尋參數 </p> </td> 
      <td colname="col2"> <p>CGI參數，它位於與演示模板關聯的命名搜索的本地。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>範本的後端參數 </p> </td> 
      <td colname="col2"> <p>傳入的查詢參數最終會轉換為用於執行搜尋的後端參數。 </p> <p>請參閱 <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> 後端搜尋CGI參數 </a>。 </p> <p>後端參數不會顯示在導覽元素上。 因此，您可以隱藏客戶想要套用至搜尋的任何其他參數。 </p> <p>此參數是簡報範本內特定搜尋的本機參數。 後端參數的動作會延遲系結；也就是說，在傳送搜尋之前就會套用搜尋。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>目標範本 </p> </td> 
      <td colname="col2"> <p>無法刪除的系統定義自訂變數的特殊例項。 此變數包含目前定位的簡報範本。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>排名 </p> </td> 
      <td colname="col2"> <p>可讓您指定要在搜尋中使用的排名規則。 只有在您已定義排名欄位和排名規則時，才會顯示此選項。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>上一個規則 </p> </td> 
      <td colname="col2"> <p>勾選後，搜尋後處理模組不會在符合規則的動作後執行任何其他規則。 當您設定了導致稍後規則符合但您不希望稍後規則執行的動作時，此動作會很有用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>暫停 </p> </td> 
      <td colname="col2"> <p>關閉規則的執行，但不刪除規則。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 按一下 **[!UICONTROL Add]**.
1. （可選）執行下列任一項作業：

   * 按一 **[!UICONTROL History]** 下以回復您所做的任何變更。

      請參 [閱使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。

## 編輯搜尋後規則 {#task_ECB00334C0A74C87AF857DB3EB372119}

您可以編輯已新增至頁面的現有搜尋後規 [!DNL Post-Search Rules] 則。

**若要編輯搜尋後規則**

1. 在產品功能表上，按一下 **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]**。
1. 在頁 [!DNL Post-Search Rules] 面上，在表格的 **[!UICONTROL Actions]** 欄下，按一下您要 **[!UICONTROL Edit]** 編輯的關聯規則。
1. 在頁面 [!DNL Edit Post-Search Rule] 上，使用下拉式清單和文字欄位來建立查詢。

   請參閱新增搜尋後 [規則下的選項表](../c-about-rules-menu/c-about-post-search-rules.md#task_52F6F9AAD65B45B5ACA1FF245DFFADD9)。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）執行下列任一項作業：

   * 按一 **[!UICONTROL History]** 下以回復您所做的任何變更。

      請參 [閱使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。

## 刪除搜尋後規則 {#task_0F4653AB20D54B769A4FA8D1491AB4CF}

您可以刪除不再需要或使用的搜尋後規則。

刪除規則時，系統會自動調整剩餘規則的執行順序，以計入刪除。

**刪除搜尋後規則**

1. 在產品功能表上，按一下 **[!UICONTROL Rules]** > **[!UICONTROL Post-Search Rules]**。
1. 在頁 [!DNL Post-Search Rules] 面上，在表格的 **[!UICONTROL Actions]** 欄下，按一下您要 **[!UICONTROL Delete]** 刪除的關聯規則。
1. 在對話 [!DNL Confirmation] 方塊中，按一下 **[!UICONTROL OK]**。
1. （可選）執行下列任一項作業：

   * 按一 **[!UICONTROL History]** 下以回復您所做的任何變更。

      請參 [閱使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。

## 變更搜尋後規則的執行順序 {#task_40542FCD32234BBF881A81BF5477F78F}

您可以重新排序搜尋後規則，以變更規則在簡報範本上執行的順序。

搜尋後規則依其定義順序執行。 規則的訂單編號越高，在流程中執行的時間越晚，比較早的規則。 您可以在頁面上表格的「順序」欄中輸入新編號，以重新排序 [!DNL Post-Search Rules] 規則。 您也可以對規則使用拖放功能來變更其執行順序。

**若要變更搜尋後規則的執行順序**

1. 在產品功能表上，按一下 **[!UICONTROL Rules]** > **[!UICONTROL Post-Search Rules]**。
1. 在頁面 [!DNL Post-Search Rules] 上，執行下列其中一項作業：

   * 按一下 **[!UICONTROL Order]** 欄標題，以遞增或遞減順序排序規則。
   * 在欄 [!DNL Order] 中，在搜尋前規則名稱左側的文字欄位中，輸入您要執行規則的訂單編號。
   * 將表格列拖放至您要執行規則的位置。 所有訂單編號都會更新，以反映規則執行的新順序。

1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）執行下列任一項作業：

   * 按一 **[!UICONTROL History]** 下以回復您所做的任何變更。

      請參 [閱使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。
