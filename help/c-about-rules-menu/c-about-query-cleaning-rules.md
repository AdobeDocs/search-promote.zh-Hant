---
description: 使用查詢清除規則來分析和修改傳入查詢。
solution: Target
title: 關於查詢清除規則
topic: 規則、網站搜尋與銷售
uuid: 683af81f-f7c0-45f8-9212-e5e7cb82ccca
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1601'
ht-degree: 1%

---


# 關於查詢清除規則{#about-query-cleaning-rules}

使用查詢清除規則來分析和修改傳入查詢。

## 使用查詢清除規則{#concept_17F3CDDC3C8A4128AF092A82B777B86C}

當您想要修改網站搜尋／銷售行為時，通常會使用此功能。 例如，您可將空白搜尋變更為熱門關鍵字，而非「*」搜尋，以推廣熱門產品。 您也可以使用查詢清除規則來執行直接點擊，您可在其中重新導向至URL。 當您偵測到有人正在搜尋產品SKU，而您想要略過搜尋並重新導向至該產品頁面時，這特別有用。 「查詢清除」也可以挖掘查詢，並設定可用於後續處理流程步驟的自訂變數。 查詢清除規則會依序執行每個查詢。 若要變更規則的順序，您可以使用拖放。 實際訂單在您儲存之前不會變更。

檢查查詢清除模組中的查詢清除規則，以確定是否必須修改任何查詢參數或是否必須設定任何自定義變數。 每個查詢清除規則都包含兩個主要元素：規則的動作和可選條件。 可以指定不限數目的規則和條件。 這些規則的順序很重要，因為網站搜尋／銷售會循環循規則集。 當規則的條件符合時，會執行所有相關的動作。

查詢清除完成後，將繼續使用生成的CGI參數。 任何已設定的自訂變數都可供處理流程的後續階段使用。 依預設，系統會自動從查詢詞語中移除前導和尾隨空白字元。

## 關於查詢清除條件{#section_BF6F25F94FED4DDEA8600D921EA43A66}

條件是可選的。 如果您決定為每個查詢指定操作，則始終執行這些操作。 條件可以以任何CGI查詢參數、現有Cookie或先前規則已設定的自訂變數為基礎。 對於每個查詢，第一個要運行的查詢清除規則被視為「最佳做法」，它定義並初始化您計畫使用的所有自定義變數。

## 關於查詢清除操作{#section_78F74A9B48DE484191CDA95F5B4E7154}

查詢清除規則中具有匹配條件的所有操作都會被執行。 操作通常由操作、要執行操作的資料以及要使用的值組成。

請參閱[添加查詢清除規則](../c-about-rules-menu/c-about-query-cleaning-rules.md#task_47F43988D3D9485F8AE1DFDA7E00BF54)中的選項表。

## 關於重新導向{#section_597481E6194440C0A7B9E6FC901A81C0}

「直接點擊」介面可讓您根據傳入的查詢詞語定義一組重新導向。 「查詢清除」中的重新導向延伸了此理念。 不過，重新導向會透過指定條件提供您更精細的重新導向時間，並讓您重新導向至動態URL，而非靜態URL。 當您選取重新導向動作時，會更新該列，使其具有文字方塊，您可在其中指定要重新導向至的URL。 在URL中，您可以指定要取代的變數或參數，方法是將變數或參數加上雙大括弧。 自訂變數的優先順序高於替代中的CGI參數。

## 範例 {#section_DB5047CC38FB4A57B15CAAF9848073E3}

假設您有一家服裝零售商店，並有網站。 如果使用者在沒有搜尋詞的情況下按一下「搜尋」，您會想要傳回對牛仔褲的搜尋，因為這是您國際知名的搜尋詞。 您也想要剖析性別的查詢詞語，以便您稍後能夠根據針對每個性別使用不同表現範本的自訂變數，建立搜尋前規則。

```
On condition: 
  query q equal 
Perform the following actions: 
  Set query parameter q to value jeans 
 
On condition: 
  Query q matches regular expression wom[e|a]n[s]|girl[s] 
Perform the following actions: 
  Add custom variable gender 
  Set custom variable gender to value female 
 
On condition: 
  Query q matches regular expression men[s]|boy[s] 
Perform the following actions: 
  Add custom variable gender 
  Set custom variable gender to value male
```

MegaElectronic是大型電子商店。 從分析其搜尋資料，MegaElectronic注意到，許多精明的客戶通常會使用產品的SKU來搜尋產品，而不是傳回單一產品的搜尋結果，因此MegaElectronic會想要重新導向至與該SKU相關的網頁。

```
On condition: 
  query q matches regular expression ^\D\D\D-\d\d\d\d$ 
Perform the following actions: 
  redirect to https://www.megaelectronic.com/?sku={{q}}
```

## 添加查詢清除規則{#task_47F43988D3D9485F8AE1DFDA7E00BF54}

您可以定義清除或編輯客戶傳入搜尋查詢的規則。

您只能選取目前存在的範本。 如果您沒有任何範本，您必須先定義範本。

請參閱[關於模板](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5)。

**要添加查詢清除規則**

1. 在產品功能表上，按一下「**[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]**」。
1. 在[!DNL Query Cleaning Rules]頁面上，按一下&#x200B;**[!UICONTROL Add New Rule]**。
1. 在[!DNL Name]欄位中，輸入新查詢清除規則的名稱。
1. 在[!DNL Add Query Cleaning Rule]頁面上，使用下拉式清單和文字欄位來建立查詢。

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
      <td colname="col2"> <p>HTTP Cookie。 您可以根據與您網域關聯的Cookie來定義條件。 或者，您可以設定使用傳出搜尋結果寫入的Cookie。 Cookie名稱和值必須編碼為統一資源識別碼。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>自訂變數 </p> </td> 
      <td colname="col2"> <p>使用者定義的變數。 新增、刪除或設定不限數量的使用者定義變數。 您可以在此處參考「搜尋前規則」和「搜尋後規則」中的任何使用者定義變數。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>系統變數 </p> </td> 
      <td colname="col2"> <p>可檢查的內部系統所設定的唯讀變數。 支援下列系統變數： </p> <p> 
        <ul id="ul_BC17F1637F27424CA4E8F530C28A3245"> 
          <li id="li_C7DF96EFD7AA4A449D00F7EACCAA0EB1"> <span class="uicontrol"> 主機名  </span> <p>伺服器主機的名稱。 </p> </li> 
          <li id="li_F85AB1D2B9374A859657D12B8ED6674B"> <span class="uicontrol"> uri  </span> <p>沒有查詢字串的請求URI。 </p> </li> 
          <li id="li_440149C9EC6E4805B77BBC97BE41542A"> <span class="uicontrol"> args  </span> <p>整個查詢字串。 </p> </li> 
          <li id="li_F583FC4B0E404858BB3522B33A6F7A0A"> <span class="uicontrol"> 環境 </span> <p>「階段」或「即時」，視傳入查詢是傳送至您的分段或即時環境而定。 </p> </li> 
          <li id="li_15902AA49B144D42A5E95D7E8B0FB1E1"> <span class="uicontrol"> referrer </span> <p>客戶來自的URL。 </p> </li> 
          <li id="li_6FEE352DB7A842FCB2EBE1398AD03666"> <span class="uicontrol"> 用戶代理  </span> <p>客戶瀏覽器的「使用者代理」字串。 </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>查詢參數 </p> </td> 
      <td colname="col2"> <p>傳遞給查詢的CGI參數。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>後端參數 </p> </td> 
      <td colname="col2"> <p>傳入的查詢參數最終會轉換為用於執行搜尋的後端參數。 </p> <p>請參閱<a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local">後端搜尋CGI參數</a>。 </p> <p>後端參數不會顯示在導覽元素上。 因此，您可以隱藏客戶想要套用至搜尋的任何其他參數。 後端參數的動作會延遲系結；也就是說，在傳送搜尋之前就會套用搜尋。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Facet </p> </td> 
      <td colname="col2"> <p>與特定Facet相關的特殊CGI參數。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>排名 </p> </td> 
      <td colname="col2"> <p>可讓您指定要在搜尋中使用的排名規則。 只有在定義了一些排名欄位和排名規則時，才會顯示此選項。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>商店 </p> </td> 
      <td colname="col2"> <p>搜索引擎根據主機名或<span class="codeph"> gs_store </span>查詢參數自動檢測用戶所在的儲存，後者具有優先順序。 您可以建立商店的條件。 僅在查詢清除中，您也可以使用動作來過載目前商店。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>上一個規則 </p> </td> 
      <td colname="col2"> <p>當符合具有最後一個規則集的規則的條件時，查詢清除處理模組不會在匹配規則的動作之後執行任何其他規則。 當您設定的動作會使稍後的規則符合，但您不希望觸發後續規則時，這個功能會很有用。 請注意，如果規則的動作是執行重新導向，則重新導向會立即進行，因此實際上會如同設定了最後一個規則。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>暫停 </p> </td> 
      <td colname="col2"> <p>關閉規則的執行，但不刪除規則。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 按一下 **[!UICONTROL Add]**.
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 編輯查詢清除規則{#task_FA2FF1A7E2634350AD703485CBC27CB3}

您可以編輯已添加到「查詢清除規則」頁的現有查詢清除規則。

**要編輯查詢清除規則**

1. 在產品功能表上，按一下「**[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]**」。
1. 在[!DNL Query Cleaning Rules]頁面的表格&#x200B;**[!UICONTROL Actions]**&#x200B;欄下，按一下&#x200B;**[!UICONTROL Edit]**&#x200B;以取得您要編輯的相關規則。
1. 在[!DNL Edit Query Cleaning Rule]頁面上，使用下拉式清單和文字欄位來建立查詢。

   請參閱[添加查詢清除規則](../c-about-rules-menu/c-about-query-cleaning-rules.md#task_47F43988D3D9485F8AE1DFDA7E00BF54)下的選項表。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 刪除查詢清除規則{#task_C52D17226B824590B087CAB6970CBB01}

您可以刪除不再需要或使用的查詢清除規則。

刪除規則時，系統會自動調整剩餘規則的執行順序，以計入刪除。

**刪除查詢清除規則**

1. 在產品功能表上，按一下「**[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]**」。
1. 在[!DNL Query Cleaning Rules]頁面的表格&#x200B;**[!UICONTROL Actions]**&#x200B;欄下，按一下&#x200B;**[!UICONTROL Delete]**&#x200B;以取得您要刪除的相關規則。
1. 在[!DNL Confirmation]對話框中，按一下&#x200B;**[!UICONTROL OK]**。
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 更改查詢清除規則運行{#task_C24012C45A4445468A7FD998017388CA}的順序

您可以重新排序查詢清除規則，以變更它們在簡報範本上執行的順序。

查詢清除規則按定義順序運行。 規則的訂單編號越高，在流程中執行的時間越晚，比較早的規則。 通過在[!DNL Query Cleaning Rules]頁面的表的「順序」列中輸入新編號，可以重新排序規則。 您也可以對規則使用拖放功能來變更其執行順序。

**要更改查詢清除規則運行的順序，請執行以下操作：**

1. 在產品功能表上，按一下「**[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]**」。
1. 在[!DNL Query Cleaning Rules]頁面上，執行下列其中一項作業：

   * 按一下[!DNL Order]欄標題，以遞增或遞減順序排序規則。
   * 在[!DNL Order]欄中，在查詢清除規則名稱左側的文字欄位中，輸入您要執行規則的訂單編號。
   * 將表格列拖放至您要執行規則的位置。 所有訂單編號都會更新，以反映規則執行的新順序。

1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

