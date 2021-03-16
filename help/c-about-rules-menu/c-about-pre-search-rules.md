---
description: 使用搜尋前規則來分析傳入的查詢，並決定要使用的簡報範本。 「搜尋前規則」會依序執行每個查詢。 若要變更規則的順序，您可以使用拖放。 實際訂單在您儲存之前不會變更。
solution: Target
title: 關於搜索前規則
topic: 規則、網站搜尋與銷售
uuid: e75f9d9e-e8ca-4184-bf79-b1fdadb5c0fe
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1666'
ht-degree: 1%

---


# 關於預搜索規則{#about-pre-search-rules}

使用搜尋前規則來分析傳入的查詢，並決定要使用的簡報範本。 「搜尋前規則」會依序執行每個查詢。 若要變更規則的順序，您可以使用拖放。 實際訂單在您儲存之前不會變更。

## 使用預搜索規則{#concept_5BF84BB6FACB4645BA9CB7496A01CD1F}

「搜尋前規則」通常用於選取根據傳入查詢顯示結果的簡報範本。 更進階的功能可用來變更用於對簡報範本執行搜尋的查詢。 您可以視需要新增、刪除或變更查詢參數的值。 對於每個傳入查詢，預搜索處理模組檢查預搜索規則以確定查詢是否被修改以及使用什麼演示模板。 每個預先搜尋規則都包含兩個主要元素：規則的動作和可選條件。 您可以指定不限數目的規則和條件。 這些規則的順序很重要，因為規則集會依規則循環。 當規則的條件相符時，會執行所有相關的動作。

在「預搜索處理」模組中，將實例化所有已定義模板及其相關的命名搜索，其中每個搜索都獲得cgi參數的本地副本。 因此，您可以通過添加、刪除或更改搜索使用的cgi參數來自定義搜索，而不更改模板使用的任何其他命名搜索或影響其他模板的任何命名搜索。 因此，如果您有一個顯示多個結果集的演示模板，則可以分別自定義每個搜索。 如果要在全局CGI參數被複製到每個模板的每個搜索之前對其執行更改，請使用查詢清除模組。

## 搜索前規則條件{#section_B5568ADEB28546A280720309498B045D}

條件是可選的。 如果您選擇為每個查詢指定操作，則始終執行這些操作。 您的第一個規則會針對每個查詢執行，並在其中選取預設簡報範本時，會被視為最佳實務。 這樣，您就可以確保，無論傳入的查詢是什麼，您都選擇了要使用的最壞情況方案演示模板。 條件可以基於先前規則已設定或系統變數的任何CGI查詢參數、Cookie或自訂變數。

## 搜索前規則操作{#section_3B8E19D287554C1C969F5B8D81226981}

所有具有匹配條件的搜尋前規則內的動作都會執行。 操作通常包括操作、要執行操作的資料以及要使用的值。 最簡單的動作是指定當查詢符合搜尋前規則的條件時要使用的簡報範本。 然後，將目標範本設定為簡報範本的名稱。 更複雜的動作可用來變更指定範本的搜尋，方法是對範本的搜尋參數執行操作。 對模板的搜索參數執行操作時，可以指定演示模板並進行搜索。

## 一般規則{#section_885ECB9DBF0C4D539C14F82BCAA35B4E}

對模板的搜索參數執行操作時，存在兩個特殊值：*分別針對簡報範本和指名搜尋的定位和*primary。 使用這些值，您可以根據目前定位範本的主要搜尋來建立規則。 這些結構可讓您建立一般規則，而您不必擔心目前的目標範本或主要搜尋被呼叫的項目。 顯然，先前的「搜尋前規則」會定義目前定位的範本。 否則，會為您選取初始簡報範本，產生不想要的結果。

## 範例 {#section_EA153A151987454EA44A4A6862466DF6}

將預設範本設為guided.tmpl，當使用者在名為lang的cgi參數中傳遞時，若設為已知語言，請使用該語言的範本。

```
    On condition: 
      Every Query 
    Perform the following actions: 
      Set targeted template to guided 
 
    On condition: 
      Query lang matches regular expression fr 
    Perform the following actions: 
      Set targeted template to guided_french 
 
    On condition: 
      Query lang matches regular expression de 
    Perform the following actions: 
      Set targeted template to guided_german
```

## 最佳實務 {#section_31EBAE5E54174DEE8986CBB636746A98}

* 第一個規則為每個查詢選擇一個預設模板。
* 查詢的資料挖掘是在查詢清除規則內完成的。 您可以在搜尋前處理中參照這些項目。
* 將您在搜尋前規則中引入的任何新自訂變數新增至每個查詢的搜尋前規則，該規則會在其他搜尋前規則參考前執行。

## 新增搜尋前規則{#task_182B95918462490D8BDA7F16A81CAC11}

您可以使用[!DNL Pre-Search Rules]來選擇根據傳入查詢使用哪個演示模板來顯示搜索結果。

**若要新增搜尋前規則**

1. 在產品功能表上，按一下「**[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]**」。
1. 在[!DNL Pre-Search Rules]頁面上，按一下&#x200B;**[!UICONTROL Add New Rule]**。
1. 在[!DNL Name]欄位中，輸入新查詢清除規則的名稱。
1. 在[!DNL Add Pre-Search Rule]頁面上，使用下拉式清單和文字欄位來建立查詢。

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
      <td colname="col2"> <p>HTTP Cookie。 Cookie名稱和值必須編碼為統一資源識別碼。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>自訂變數 </p> </td> 
      <td colname="col2"> <p>使用者定義的變數。 新增、刪除或設定不限數量的使用者定義變數。 </p> <p>您可以參考在「預搜索規則」中「查詢清除」模組中定義的任何變數。 </p> </td> 
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
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Facet </p> </td> 
      <td colname="col2"> <p>全域集合中與特定Facet關聯的特殊CGI參數。 所有CGI參數都會在查詢清除後複製到模板內的每個命名搜索。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>查詢參數 </p> </td> 
      <td colname="col2"> <p>全域集合中的CGI參數。 這些參數會在「查詢清除」後複製到範本內的每個已命名搜尋。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>範本的搜尋參數 </p> </td> 
      <td colname="col2"> <p>CGI參數，它位於與演示模板關聯的命名搜索的本地。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>範本的後端參數 </p> </td> 
      <td colname="col2"> <p>傳入的查詢參數最終會轉換為用於執行搜尋的後端參數。 </p> <p>請參閱<a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local">後端搜尋CGI參數</a>。 </p> <p>後端參數不會顯示在導覽元素上。 因此，您可以隱藏客戶想要套用至搜尋的任何其他參數。 此參數是簡報範本內特定搜尋的本機參數。 後端參數的動作會延遲系結；也就是說，在傳送搜尋之前就會套用搜尋。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>目標範本 </p> </td> 
      <td colname="col2"> <p>無法刪除的系統定義自訂變數的特殊例項。 此變數包含目前定位的簡報範本。 您可以指定自訂變數"targeted_template"來讀取或設定此變數。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>排名 </p> </td> 
      <td colname="col2"> <p>可讓您指定要在搜尋中使用的排名規則。 只有在您已定義排名欄位和排名規則時，才會顯示此選項。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>商店 </p> </td> 
      <td colname="col2"> <p>搜尋引擎會根據主機名稱或<span class="codeph"> gs_store </span>查詢參數自動偵測客戶所在的商店，而後者具有優先順序。 您可以建立商店的條件。 僅在查詢清除中，您也可以使用動作來過載目前商店。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>上一個規則 </p> </td> 
      <td colname="col2"> <p>勾選後，搜尋前處理模組不會在符合規則的動作之後執行任何其他規則。 當您設定了導致稍後規則符合但您不希望稍後規則執行的動作時，此動作會很有用。 </p> </td> 
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

## 編輯預搜索規則{#task_25F77050C5DA42B29DFD1C9718FB8C64}

您可以編輯已新增至[!DNL Pre-Search Rules]頁面的現有搜尋前規則。

**若要編輯搜尋前規則**

1. 在產品功能表上，按一下「**[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]**」。
1. 在[!DNL Pre-Search Rules]頁面的表格&#x200B;**[!UICONTROL Actions]**&#x200B;欄下，按一下&#x200B;**[!UICONTROL Edit]**&#x200B;以取得您要編輯的相關規則。
1. 在[!DNL Edit Pre-Search Rule]頁面上，使用下拉式清單和文字欄位來建立查詢。

   請參閱[新增搜尋前規則](../c-about-rules-menu/c-about-pre-search-rules.md#task_182B95918462490D8BDA7F16A81CAC11)下的選項表。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 刪除搜索前規則{#task_128B6A79CA6C451C991AEDAD58F51743}

您可以刪除不再需要或使用的搜尋前規則。

刪除規則時，系統會自動調整剩餘規則的執行順序，以計入刪除。

**刪除搜索前規則**

1. 在產品功能表上，按一下「**[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]**」。
1. 在[!DNL Pre-Search Rules]頁面的表格&#x200B;**[!UICONTROL Actions]**&#x200B;欄下，按一下&#x200B;**[!UICONTROL Delete]**&#x200B;以取得您要刪除的相關規則。
1. 在[!DNL Confirmation]對話框中，按一下&#x200B;**[!UICONTROL OK]**。
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 變更搜尋前規則執行{#task_C18817276A3C459089C97448076365D1}的順序

您可以重新排序搜尋前規則，以變更它們在簡報範本上執行的順序。

搜尋前規則會依其定義順序執行。 規則的訂單編號越高，在流程中執行的時間越晚，比較早的規則。 通過在[!DNL Pre-Search Rules]頁面的表的「順序」列中輸入新編號，可以重新排序規則。 您也可以對規則使用拖放功能來變更其執行順序。

**若要變更搜尋前規則的執行順序**

1. 在產品功能表上，按一下「**[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]**」。
1. 在[!DNL Pre-Search Rules]頁面上，執行下列其中一項作業：

   * 按一下&#x200B;**[!UICONTROL Order]**&#x200B;欄標題，以遞增或遞減順序排序規則。
   * 在&#x200B;**[!UICONTROL Order]**&#x200B;欄中，在搜尋前規則名稱左側的文字欄位中，輸入您要執行規則的順序編號。
   * 將表格列拖放至您要執行規則的位置。 所有訂單編號都會更新，以反映規則執行的新順序。

1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

