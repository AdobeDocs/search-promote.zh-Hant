---
description: 「資料檢視」會顯示含有中繼欄位的搜尋結果。 每一欄都是中繼欄位，而每一列都是搜尋查詢的結果。 選擇並重新排列欄，以自訂資料檢視。 資料檢視也可以有自訂標題和說明。
seo-description: 「資料檢視」會顯示含有中繼欄位的搜尋結果。 每一欄都是中繼欄位，而每一列都是搜尋查詢的結果。 選擇並重新排列欄，以自訂資料檢視。 資料檢視也可以有自訂標題和說明。
seo-title: 關於資料視圖
solution: Target
title: 關於資料視圖
topic: Reports,Site search and merchandising
uuid: 18930551-960d-40c2-b5b7-0807a2e11134
translation-type: tm+mt
source-git-commit: 7af85dd37f06fe506e5f57e28a25385ca7ab3db5

---


# 關於資料視圖{#about-data-views}

「資料檢視」會顯示含有中繼欄位的搜尋結果。 每一欄都是中繼欄位，而每一列都是搜尋查詢的結果。 選擇並重新排列欄，以自訂資料檢視。 資料檢視也可以有自訂標題和說明。

## 使用資料檢視 {#concept_DCA897D074464BC1861AA47B40CC86C3}

每個帳戶都可方便建立多個資料檢視。 使用「資料檢視」頁面可建立和編輯這些資料檢視。

新增資料檢視後，您必須加以編輯，才能設定及自訂檢視。

請參 [閱編輯資料檢視](../c-about-reports-menu/c-about-data-views.md#task_258A367896C24DD498C755925EA8F516)。

您可以複製現有資料檢視，作為建立新資料檢視的基礎。

請參 [閱複製資料檢視](../c-about-reports-menu/c-about-data-views.md#task_78D4C2799BC84677843ED4CA1CD205AF)。

## 新增資料檢視 {#task_A20FEB2E1CA1444D816D2F5F4B6E5B2D}

您可以新增資料檢視至頁 [!DNL Data Views] 面，以顯示每個含搜尋查詢之中繼欄位的值。

新增資料檢視後，您必須加以編輯，才能設定及自訂檢視。

請參 [閱編輯資料檢視](../c-about-reports-menu/c-about-data-views.md#task_258A367896C24DD498C755925EA8F516)。

**若要新增資料檢視**

1. 在產品功能表上，按一下 **[!UICONTROL Reports]** > **[!UICONTROL Data Views]**。
1. 在頁面上 [!DNL Data Views] ，按一下 **[!UICONTROL Add New Data View]**。
1. 在對 [!DNL Add New Data View] 話方塊的欄位中， [!DNL Title] 輸入您要建立的資料檢視名稱。
1. 按一下 **[!UICONTROL Add]**.

## 編輯資料檢視 {#task_258A367896C24DD498C755925EA8F516}

將資料視圖添加到頁面時， [!DNL Data Views] 使用「編輯」更改資料視圖的名稱和說明，或移動、顯示或隱藏每個元欄位的顯示。

您也可以鎖定或解除鎖定所選資料視圖。

請參 [閱新增資料檢視](../c-about-reports-menu/c-about-data-views.md#task_A20FEB2E1CA1444D816D2F5F4B6E5B2D)。

**若要編輯資料檢視**

1. 在產品功能表上，按一下 **[!UICONTROL Reports]** > **[!UICONTROL Data Views]**。
1. 在頁 [!DNL Data Views] 面上，在表格 [!DNL Actions] 的欄中，按一下 **[!UICONTROL Edit]** 您要變更的資料檢視列中的。
1. 在頁面上 [!DNL Data Views Editor] ，設定您想要的選項。

   「資料檢視編輯器」具有「資料檢視」頁面上隱藏、顯示和移動欄位欄位的所有控制項。

   當您檢視資料檢視時，產生的表格也會顯示下列不可編輯的其他欄位：排名、相關性和分數（整體）。 這三個特殊欄位代表每個結果的相關性分數、排名分數和總分。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>選項 </p> </th> 
      <th colname="col2" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>標題 </p> </td> 
      <td colname="col2"> <p>資料檢視的名稱。 當您檢視資料檢視時，名稱會顯示在右上方。 </p> <p>請參 <a href="../c-about-reports-menu/c-about-data-views.md#task_FD0D2CE53DF84CBD9220AD7CA920011F" type="task" format="dita" scope="local"> 閱查看資料視圖</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>說明 </p> </td> 
      <td colname="col2"> <p>（可選）包含資料檢視的說明。 說明會顯示在資料檢視的標題名稱與「新搜尋」文 <span class="wintitle"> 字欄位之間</span> 。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>搜尋參數 </p> </td> 
      <td colname="col2"> <p>可讓您指定預設搜尋參數。 首次顯示資料視圖時，會自動附加這些CGI參數。 </p> <p>請勿變更或刪除 <span class="codeph"> sp_cs</span><span class="codeph"> 或sp_f</span>。 這些參數對於「資料檢視」而言是必要的，不論帳戶偏好的字元集為何。 </p> <p>請參閱 <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> 後端搜尋CGI參數</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>鎖定狀態 </p> </td> 
      <td colname="col2"> <p>可讓您鎖定或解除鎖定資料檢視。 </p> <p>您只能使用密碼和用戶名查看鎖定的資料視圖。 使用者必須是帳戶的目前成員。 </p> <p>不使用密碼或用戶帳戶即可訪問解鎖資料視圖。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>訂購 </p> </td> 
      <td colname="col2"> <p> 可讓您編輯「順序」文字方塊中的數字，以變更 <span class="wintitle"> 欄順序</span> 。 您也可以拖放列來變更欄順序。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>包含 </p> </td> 
      <td colname="col2"> <p> 可讓您開啟或關閉欄的顯示。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>將URL顯示為影像 </p> </td> 
      <td colname="col2"> <p>如果此欄的搜尋結果傳回URL，則顯示此欄的縮圖和影像。 </p> <p>URL會先移除其配置名稱或通訊協定，再變成影像標籤的 <span class="codeph"> src</span> 屬性值。 </p> <p>如果傳回的搜尋結果看起來不像影像的URL，則會顯示。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>欄位長度 </p> </td> 
      <td colname="col2"> <p>設定在資料檢視中顯示為結果的字元數。 </p> <p>預設值為100個字元。 </p> <p>有些欄位（例如排名分數和日期欄位）沒有可調整的欄位長度。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）執行下列任一項作業：

   * 按一 **[!UICONTROL History]** 下以回復您所做的任何變更。

      請參 [閱使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。

## 複製資料檢視 {#task_78D4C2799BC84677843ED4CA1CD205AF}

您可以複製頁面上的現有資 [!DNL Data Views] 料檢視，作為建立新資料檢視的基礎。

複製資料檢視後，您可以編輯檢視，進一步自訂資料檢視。

請參 [閱編輯資料檢視](../c-about-reports-menu/c-about-data-views.md#task_258A367896C24DD498C755925EA8F516)。

**要複製資料視圖**

1. 在產品功能表上，按一下 **[!UICONTROL Reports]** > **[!UICONTROL Data Views]**。
1. 在頁 [!DNL Data Views] 面上，在表格 [!DNL Actions] 的欄中，按一 **[!UICONTROL Copy]** 下您要複製的資料檢視列中的。
1. 在頁 [!DNL Copy Data View] 面的文字欄 [!DNL New Title] 位中，輸入您要指派資料檢視的新名稱。
1. 按一下 **[!UICONTROL Copy]**.
1. （可選）執行下列任一項作業：

   * 按一 **[!UICONTROL History]** 下以回復您所做的任何變更。

      請參 [閱使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。

## 刪除資料視圖 {#task_61C32F8F00A549A5A3E7EDDA6F537098}

您可以刪除不再需要或使 [!DNL Data Views] 用之頁面上的資料檢視。

**刪除資料視圖**

1. 在產品功能表上，按一下 **[!UICONTROL Reports]** > **[!UICONTROL Data Views]**。
1. 在頁 [!DNL Data Views] 面上，在表格 [!DNL Actions] 的欄中，按一 **[!UICONTROL Delete]** 下您要移除的資料檢視列中的。
1. 在頁面 [!DNL Delete Data View] 上，按一下「 **刪除」**。
1. （可選）執行下列任一項作業：

   * 按一 **[!UICONTROL History]** 下以回復您所做的任何變更。

      請參 [閱使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。

## 檢視資料檢視 {#task_FD0D2CE53DF84CBD9220AD7CA920011F}

您可以在頁 [!DNL View] 面上使 [!DNL Data Views] 用以顯示選取的資料檢視。

您選擇的資料檢視會在個別的瀏覽器視窗中開啟。

**若要檢視資料檢視**

1. 在產品功能表上，按一下 **[!UICONTROL Reports]** > **[!UICONTROL Data Views]**。
1. 執行下列任一項作業：

   * 在頁 [!DNL Data Views] 面上，在表格 [!DNL Title] 的列中，按一下您要開啟的資料檢視名稱。

   * 在頁 [!DNL Data Views] 面上，在表格 [!DNL Actions] 的欄中，按一下 **[!UICONTROL View]** 您要開啟的資料檢視列中的。

