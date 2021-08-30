---
description: 了解Search&amp;Promote中的搜尋表單
solution: Target
title: 搜尋表單
topic-legacy: Appendices,Site search and merchandising
uuid: 91153e3a-c437-47f3-8c2a-d9ac02965b8c
exl-id: 9771a19d-86a8-41db-9c80-d734fbd10ab7
source-git-commit: 95bf92df17d7832df72e8d883a22f9063e53a18d
workflow-type: tm+mt
source-wordcount: '2899'
ht-degree: 0%

---

# 搜尋表單{#search-forms}

## 在搜尋表單中使用集合 {#reference_5A079AEEEFB84457892EF0870D0605C3}

集合可讓客戶搜尋您網站的特定區域。 視您實作的下拉式清單或核取方塊清單而定，您可以讓客戶搜尋單一系列或多個系列。

另請參閱[關於集合](../c-about-settings-menu/c-about-searching-menu.md#concept_62E42ACE53D54EEE9273433B86259127)。

下列範例顯示四個不同的系列名稱及其所涵蓋的網站的相關區域：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>集合名稱 </p> </th> 
   <th colname="col2" class="entry"> <p> </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>產品 </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_7AE70789C0914EBFBCCC7695C6F53B9E"> 
      <li id="li_72525BAA34E2442D86152F2FD8CA83D5"> https://www.mycompany.com/products.htm </li> 
      <li id="li_5CA4152239124BDBB251E6C94B15D45B"> https://www.mycompany.com/publish/ </li> 
      <li id="li_6E266736B3494696A3AFD841C4AFEC57"> https://www.mycompany.com/search/ </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>客戶 </p> </td> 
   <td colname="col2"> <p>https://www.mycompany.com/customers/ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>新聞 </p> </td> 
   <td colname="col2"> <p>https://www.mycompany.com/news/ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>關於Adobe </p> </td> 
   <td colname="col2"> <p>https://www.mycompany.com/company/ </p> </td> 
  </tr> 
 </tbody> 
</table>

下拉式搜尋表單介面可讓使用者選取一個系列，如下所示：

![](assets/DropdownsearchformUI.png)

下拉式搜尋表單會以下列HTML程式碼產生：

```
<select name="sp_k"> 
<option value="">All of Adobe</option> 
<option value="Products">Products</option> 
<option value="Customers">Customers</option> 
<option value="News">News</option> 
<option value="About Adobe">About Adobe</option> 
</select>
```

或者，您也可以在搜尋表單中使用一組核取方塊，讓訪客可以選取多個集合：

![](assets/checkboxes.png)

核取方塊搜尋表單會以下列HTML程式碼產生：

```
<input type="checkbox" name="sp_k" value="">All of Adobe<br> 
<input type="checkbox" name="sp_k" value="Products">Products<br> 
<input type="checkbox" name="sp_k" value="Customers">Customers<br> 
<input type="checkbox" name="sp_k" value="News">News<br> 
<input type="checkbox" name="sp_k" value="About Adobe">About Adobe<br>
```

## 搜尋結果 {#section_BBDD5B44E2B349BC88D937F44583D350}

搜索模板標籤`<search-input-collections>`在搜索結果中生成集合清單框HTML，並自動選擇搜索中指定的集合。 如果要生成複選框，請使用`<search-input>`標籤，而不是`<input>`標籤，如下所示：

```
<search-input type="checkbox" name="sp_k" value="">All of Adobe<br> 
<search-input type="checkbox" name="sp_k" value="Products">Products<br> 
<search-input type="checkbox" name="sp_k" value="Customers">Customers<br> 
<search-input type="checkbox" name="sp_k" value="News">News<br> 
<search-input type="checkbox" name="sp_k" value="About Adobe">About Adobe<br>
```

如果在搜尋中指定集合，`<search-input>`標籤會輸出`<input>`標籤，並包含`checked`屬性。

## 使用框架和表單 {#reference_82CDDDA1E37042E4849EBF7EA05407C5}

您可以設定您的框架集以搭配網站搜尋/銷售運作。

<!-- 404 DEAD LINK To learn more about HTML frames and the HTML frameset element, see the following URL:

[https://www.w3schools.com/html/html_frames.asp](https://www.w3schools.com/html/html_frames.asp) -->

如果您的網站使用框架，則可以為搜索結果連結指定目標框架。 預設目標為_self，可在當前框架或瀏覽器窗口中開啟連結。 您可以改為指定網站特定或瀏覽器保留的目標：

* _top（保留瀏覽器）結果在當前瀏覽器窗口中開啟並替換所有當前幀。
* _blank（瀏覽器保留）結果在新的瀏覽器窗口中開啟(_B)。
* _parent（瀏覽器保留）結果在當前幀的父幀中開啟。
* frame2（特定網站）結果會在名為「frame2」的框架中開啟。 您可以將任何框架的名稱指定為值（例如主要或內容）。

如果您的網站不使用框架，則您很可能不想變更預設目標名稱。

如果您為網站建立自訂搜尋結果範本，則可使用`<search-link>`標籤的`target`屬性來覆寫指定的設定。

配置框架集的過程如下：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>處理步驟 </p> </th> 
   <th colname="col02" class="entry"> <p>程式說明 </p> </th> 
   <th colname="col2" class="entry"> <p>連結 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col02"> <p>將表單新增至網頁中的所需框架。 </p> </td> 
   <td colname="col2"> <p> <a href="#section_BAA8A502BB2243F8B5FF9783CDF2BFFD" type="section" format="dita" scope="local"> 正在將搜索表單代碼添加到您的框架中……  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col02"> <p>為搜索結果頁設定目標框架。 </p> </td> 
   <td colname="col2"> <p> <a scope="local" href="#section_532CACB90888467093D95EACB64FDFA1" type="section" format="dita"> 為搜索結果頁設定目標框架  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col02"> <p>為從搜尋結果頁面建立的連結設定目標。 </p> </td> 
   <td colname="col2"> <p> <a scope="local" href="#section_523248C5AC424D878321C21A23A5CD66" type="section" format="dita"> 正在設定從搜索結果建立的連結的目標……  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col02"> <p>編輯導航框架頁以防止對它們編製索引。 </p> </td> 
   <td colname="col2"> <p> <a scope="local" href="#section_C62E5F0EE1294D5EBD97E123E54433FC" type="section" format="dita"> 正在編輯導航框架頁以防止它們……  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col02"> <p>測試搜尋表單。 </p> </td> 
   <td colname="col2"> <p> <a scope="local" href="#section_43D8D4A7BF524DC480DFE5442F6A2E3C" type="section" format="dita"> 測試搜尋表單  </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 將搜索表單代碼添加到網頁中的框架 {#section_BAA8A502BB2243F8B5FF9783CDF2BFFD}

1. 在產品功能表中，按一下「**[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**」。

   HTML搜尋表單程式碼看起來類似下列：

   ```
   <!-- Adobe Target HTML for [your customer name] --> 
   <form method="get" action="https://search.atomz.com/search/"> 
   <input size=15 name="sp_q"><br> 
   <input type=submit value="Search"> 
   <input type=hidden name="sp_a" value="[your account number]"> 
   </form>
   ```

1. 在[!DNL Standard Form Source]頁面上，選取並複製文字欄位中顯示的HTML搜尋表單程式碼。
1. 將搜尋表單程式碼貼入您要在架構集中的架構中。

   在以下示例中，搜索表單代碼會貼上到導航框架中 — 螢幕左側的窄垂直框架。

   ![](assets/frames1.gif)

## 為搜索結果頁設定目標框架 {#section_532CACB90888467093D95EACB64FDFA1}

如果您將搜索表單代碼放入垂直導航框架中，則可以在較大的主框架中顯示搜索結果。 在此範例中，您呼叫主框架&quot;body&quot;，並將其設為目標框架。

![](assets/frames2.gif)

1. 要為結果頁指定目標框架，請將搜索表單代碼中的以下行從以下行更改為表單添加目標和值：

   `<form method="get" action="https://search.atomz.com/search/">`

   變更為：

   `<form target="body" method="get" action="https://search.atomz.com/search/">`

   請務必在表單目標值周圍加上引號。

當客戶執行網站搜尋時，搜尋結果會顯示在網頁的「內文」框架中。

## 設定從搜尋結果頁面建立之連結的目標 {#section_523248C5AC424D878321C21A23A5CD66}

您可以直接編輯範本來設定目標框架。

如果您的搜尋結果出現在「body」框架中，您可能也希望連結在「body」框架中開啟。 因為這是同一幀，預設設定為目標值`"_self"` ，因此您無需進行任何更改。

您也可以為結果連結設定目標框架。 以下是您可以執行的幾個範例：

* 為搜索結果及其連結指定不同的幀，使搜索結果在各自的幀中保持活動狀態，而每次按一下的結果在單獨的幀中開啟。
* 指定搜索結果將開啟到新的空白窗口中，以便舊窗口在其原始內容中保持活動狀態，同時保留搜索結果。

目標名稱可以是在HTML中指定的框架的名稱，也可以是以下幾個HTML預設值之一：

* `target="_blank"` 在新的空白未命名視窗中開啟連結。

* `target="_self"` 預設值. 在搜尋結果所在的相同視窗中開啟連結。 在這種情況下，將顯示原始搜索結果窗口。 使用此選項可覆蓋全局分配的基本目標。

* `target="_parent"` 在連結頁面的上層架構集中開啟連結。如果文檔沒有父級，則預設情況下，此函式類似於`"_self"`。

* `target="_top"` 在完整視窗中開啟連結。如果文檔已位於頂部，則預設情況下此函式類似於`"_self"`。 使用此選項可突出任意深度的框架嵌套。

例如，要設定`_blank`目標目標幀，可以按以下方式編輯模板：

1. 在產品功能表中，按一下「**[!UICONTROL Design]** > **[!UICONTROL Templates]**」。

1. 在[!DNL Staged Templates]頁面的表格中，按一下目標目標框架的範本名稱。
1. 找到`<search-link>`標籤。 您的預設`<search-link>`標籤看起來應類似下列：

   `<search-link><search-title length=100></search-link>`

1. 將幀目標添加到`<search-link>`標籤。 在上例中，輸入`target="_blank"`。 請務必在目標值周圍加上底線和引號。

   `<search-link>`標籤現在的顯示方式如下：

   `<search-link target="_blank"><search-title length=100></search-link>`

當網站訪客選擇搜尋結果連結時，連結的頁面現在會開啟一個新的空白視窗。

## 編輯導航框架頁以防止對它們編製索引 {#section_C62E5F0EE1294D5EBD97E123E54433FC}

通常，您希望排除導航幀，使其不與搜索結果建立索引。 若要完成此功能，您可以將`noindex`中繼標籤新增至這些頁面。

1. 開啟導航框架的HTML頁面源。
1. 在HTML的`<head>`區段內新增下列中繼標籤：

   `<meta name="robots" content="noindex">`

   例如：

   ```
   <html> 
   <head> 
   <title>This page is a frameset that I do not want indexed</title> 
   <meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1"> 
   <meta name="robots" content="noindex"> 
   </head>
   ```

## 測試搜尋表單 {#section_43D8D4A7BF524DC480DFE5442F6A2E3C}

1. 前往您的網站並導覽至表單。
1. 在搜尋欄位中輸入幾個搜尋詞，然後按一下&#x200B;**[!UICONTROL Search]**。

   以下是true:

   * 搜索結果頁將顯示在指定的目標框架中。
   * 搜索結果中的連結位於指定的目標框架中。
   * 導航框結果不顯示。

   如果您在測試搜尋表單後遇到框架問題，請聯絡客戶支援。

## 進階搜尋表單範例 {#reference_82E1051918744EBA88A01E9E6AE42C4A}

您可以編輯進階表單程式碼以符合您的設計和內容需求，或新增或移除其他搜尋參數。

您的首頁是插入高級搜索表單的好地方，因為許多客戶希望在那裡找到搜索功能。 您也可以建立HTML頁面，其中包含搜尋表單和其他實用資訊，然後在您的整個網站中連結至該頁面。

如果您正在為安全內容編製索引，則可以從安全的搜索Web伺服器提供搜索結果。 將搜尋表單動作屬性中的URL變更為：action=&quot;https://search.atomz.com/search/&quot;來執行此操作。

>[!NOTE]
>
>有些HTML編輯器無法從其他應用程式貼上HTML程式碼。 如果HTML代碼以文本形式顯示在網頁上，請將搜索代碼複製並貼上到簡單的文本編輯器中（如Windows上的記事本或Mac上的簡單文本），然後從簡單文本編輯器再次複製並貼上到HTML編輯器中。

搜尋參數用於進階搜尋表單程式碼，以建立選項按鈕、核取方塊和清單方塊，供客戶用來自訂個別搜尋。 例如，客戶可以指定顯示的搜索結果數，或日期範圍，或是通過高級搜索表單上顯示的選項，指定摘要是否與搜索結果一起顯示。

使用下列範例進階搜尋表單，本主題的其餘部分會示範如何使用搜尋參數建立表單上的每個選項。

![](assets/advancedsearchform.png)

您可以檢視上述範例的整個進階搜尋表單HTML程式碼。

請參閱[進階搜尋表單HTML程式碼](#reference_9AAD4A46B68D4D48865508982CB86DB9)。

請參閱[設定自動完成CSS](../c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96)。

請參閱[將搜索表單的HTML代碼複製到……](../c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7)。

<table> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> <p>表單上的位置 </p> </th> 
   <th colname="col1" class="entry"> <p>參數 </p> </th> 
   <th colname="col3" class="entry"> <p>HTML程式碼 </p> </th> 
   <th colname="col4" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p>啟用高級搜索表單選項（隱藏欄位） </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_advanced  </span> </p> </td> 
   <td colname="col3"> <p> <span class="syntax html codeph"> &lt;input type="hidden" name="sp_advanced" value="1"&gt; </span> </p> </td> 
   <td colname="col4"> <p>啟用或禁用高級搜索選項。 例如，您可以將標準搜尋表單放在首頁上，其中含有第二頁（包含進階表單）的連結。 在此情況下，您會將標準表單的副本放入<span class="codeph"> &lt;search-if-not-advanced&gt;...&lt;/search-if-not-advanced&gt; </span>範本標籤。 </p> <p>從標準表單執行搜尋的客戶在顯示搜尋結果時，會看到標準搜尋表單。 在高級搜索表單螢幕上，您將<span class="codeph"> &lt;input type=hidden name="sp_advanced" value=1&gt; </span>標籤與其他高級表單選項一起包含。 </p> <p>您也可以在&lt;search-if-advanced&gt;... &lt;/search-if-advanced&gt;範本標籤中包含進階搜尋表單的副本。 從您的高級搜索表單執行搜索的客戶在顯示搜索結果時看到高級搜索表單。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> 匹配任何、全部或片語 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_p  </span> </p> <p> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--&nbsp;Allow&nbsp;"any,"&nbsp;"all,"&nbsp;or&nbsp;"phrase"&nbsp;--&gt; 
      &lt;input&nbsp;type=radio&nbsp;name="sp_p"&nbsp;value="any"&gt;Any&nbsp;word 
      &lt;input&nbsp;type=radio&nbsp;name="sp_p"&nbsp;value="all"&nbsp;checked&gt;All&nbsp;words 
      &lt;input&nbsp;type=radio&nbsp;name="sp_p"&nbsp;value="phrase"&gt;Exact&nbsp;phrase </code> </p> </td> 
   <td colname="col4"> <p>允許客戶指定「任何字詞」、「所有字詞」或「確切的片語」必須存在，檔案才能相符。 指定<span class="codeph"> sp_p </span>參數時，客戶無需在搜尋查詢中使用「+」、「 — 」或兩者。 </p> <p> 如果省略了<span class="codeph"> sp_p </span>參數，或將其設定為""或"any"，則客戶仍可以使用"+"和"-"說明符。 如果<span class="codeph"> sp_p </span>參數設為"all"或"phrase"，則指定的"+"和"-"將被忽略。 </p> <p>您可以進一步了解在搜尋中使用「+」和「 — 」。 </p> <p>請參閱<a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local">關於搜尋</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> 相似音符 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_w  </span> </p> <p>和 </p> <p> <span class="codeph"> sp_w_control  </span> </p> <p> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--&nbsp;Checkbox&nbsp;enables&nbsp;sound-alike&nbsp;matching&nbsp;--&gt; 
      &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value=1&gt; 
      &lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="alike"&gt;&nbsp;Sound-alike&nbsp;matching </code> </p> </td> 
   <td colname="col4"> <p>讓客戶啟用或停用相似音效比對。 相似匹配允許拼寫錯誤的搜索查詢匹配文檔中「相似」的單詞。 </p> <p>當<span class="codeph"> sp_w_control </span>參數設為1且<span class="codeph"> sp_w </span>參數設為「alike」時，將選中生成的複選框，預設情況下啟用相似音匹配。 </p> <p>如果<span class="codeph"> sp_w </span>參數設定為""，則不會選中複選框。 </p> <p>如果您在最近的索引操作中未啟用相似音效匹配，則無法進行相似音效匹配，並忽略<span class="codeph"> sp_w </span>參數。 要啟用相似音匹配，請在產品菜單上按一下「語言學</span> &gt; <span class="uicontrol">單詞和語言</span> &gt; <span class="uicontrol">相似音匹配</span>」。<span class="uicontrol"> </span></p> <p>您也可以以下列方式指派參數<span class="codeph"> sp_w </span>和<span class="codeph"> sp_w_control </span>: </p> <p> <code class="syntax html"> &lt;!--&nbsp;Checkbox&nbsp;disables&nbsp;sound-alike&nbsp;matching&nbsp;--&gt; 
      &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value=0&gt; 
      &lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="exact"&gt; 
      No&nbsp;sound-alike&nbsp;matching </code> </p> <p>在此情況下，當<span class="codeph"> sp_w_control </span>參數設為0且<span class="codeph"> sp_w </span>參數設為「exact」時，預設會停用相似音效比對。 如果<span class="codeph"> sp_w </span>參數設定為「」，則啟用相似音符匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>日期範圍比對 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_d  </span> </p> <p> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--Specifies&nbsp;type&nbsp;of&nbsp;date&nbsp;range&nbsp;searching&nbsp;to&nbsp;perform.--&gt; 
      &lt;input&nbsp;type=radio&nbsp;name="sp_d"&nbsp;value="custom"&nbsp;checked&gt; 
      &lt;input&nbsp;type=radio&nbsp;name="sp_d"&nbsp;value="specific"&gt; </code> </p> </td> 
   <td colname="col4"> <p><span class="codeph"> sp_d </span>參數指定要執行的自訂資料範圍比對，或指定要執行的特定日期範圍比對。 </p> <p>在預設的進階搜尋表單中，此選項會以選項按鈕群組呈現，其中下拉式清單為「自訂」日期範圍，如同<span class="codeph"> sp_date_range </span>參數所產生。 它還包括一組「特定」的開始日期和結束日期，這些日期是以<span class="codeph"> sp_start_day </span>、<span class="codeph"> sp_start_month </span>、<span class="codeph"> sp_start_year </span>、<span class="codeph"> sp_end_day </span>、<span class="codeph"> sp_end_month </span>和<span class="codeph"> sp_end_year </span>參數產生。 </p> <p>「自訂」日期範圍是要搜尋的已命名日期範圍。 例如「隨時」、「今天」、「去年內」等。 </p> <p>「特定」日期範圍包含開始日期和結束日期。 例如，從「2009年9月8日」到2011年10月18日」。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>日期範圍比對：自訂日期範圍 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_date_range  </span> </p> <p> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--Selection&nbsp;list&nbsp;for&nbsp;custom&nbsp;date&nbsp;range.--&gt; 
      &lt;select&nbsp;name="sp_date_range"&nbsp;size=1&gt; 
      &lt;option&nbsp;value=-1&nbsp;selected&gt;Anytime&lt;/option&gt; 
      &lt;option&nbsp;value=7&gt;Within&nbsp;the&nbsp;last&nbsp;week&lt;/option&gt; 
      &lt;option&nbsp;value=14&gt;Within&nbsp;the&nbsp;last&nbsp;2&nbsp;weeks&lt;/option&gt; 
      &lt;option&nbsp;value=30&gt;Within&nbsp;the&nbsp;last&nbsp;30&nbsp;days&lt;/option&gt; 
      &lt;option&nbsp;value=60&gt;Within&nbsp;the&nbsp;last&nbsp;60&nbsp;days&lt;/option&gt; 
      &lt;option&nbsp;value=90&gt;Within&nbsp;the&nbsp;last&nbsp;90&nbsp;days&lt;/option&gt; 
      &lt;option&nbsp;value=180&gt;Within&nbsp;the&nbsp;last&nbsp;180&nbsp;days&lt;/option&gt; 
      &lt;option&nbsp;value=365&gt;Within&nbsp;the&nbsp;last&nbsp;year&lt;/option&gt; 
      &lt;option&nbsp;value=730&gt;Within&nbsp;the&nbsp;last&nbsp;two&nbsp;years&lt;/option&gt; 
      &lt;/select&gt; </code> </p> </td> 
   <td colname="col4"> <p><span class="codeph"> sp_date_range </span>參數用於建立「自訂」日期範圍。 例如「隨時」、「今天」、「去年內」等。 </p> <p>大於或等於零的值指定今天之前要搜尋的天數。 例如，值0指定「今天」，值1指定「今天和昨天」，值30指定「過去30天內」，以此類推。 小於零的值指定自訂範圍，如下所示： </p> <p> 
     <ul id="ul_E65DDE33883F441F9730F315E485AD98"> 
      <li id="li_83E9466AB9D7438A8544001F6B007186"> <p>-1 = "隨時"，與指定日期範圍相同。 </p> </li> 
      <li id="li_38AB8D97179A47F9B860A96EA09119BB"> <p>-2 = "本週"，在當周的星期日到星期六之間搜尋。 </p> </li> 
      <li id="li_F4C3A8658428418A8A06FBAAB4733C68"> <p>-3 = "Last week"，在當周前一週的星期日到星期六之間搜索。 </p> </li> 
      <li id="li_DF2D0B043A4E4DE9BE8D82E69A76E793"> <p>-4 = "本月"，搜尋當月日期。 </p> </li> 
      <li id="li_76BC4C2CED574E2A81448158828BFF1B"> <p>-5 = "上個月"，其搜尋日期在當月前的某月內。 </p> </li> 
      <li id="li_17FF849384FB46D58AF6FF1D3BC408C8"> <p>-6 =「今年」，其搜尋日期為當年。 </p> </li> 
      <li id="li_E2B8B4DFF3914BBDB86D0EB77F52B305"> <p>-7 = "Last year"，其搜尋日期在目前年份之前的一年內。 </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>日期範圍比對：開始日期 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_start_day, sp_start_month, sp_start_year  </span> </p> <p> </p> </td> 
   <td colname="col3"> </td> 
   <td colname="col4"> <p>這三份數值會指定要搜尋的特定日期範圍的開始日期。 請務必指定全部三個值，因為會忽略部分指定的日期。 </p> <p>只指定開始日期、結束日期或開始日期和結束日期都是合法的。 如果僅指定了開始日期，則搜索將包括日期為開始日期或之後的匹配文檔。 如果僅指定了結束日期，則搜索將包括結束日期或結束日期之前的匹配文檔。 如果同時指定了開始日期和結束日期，則搜索將包括從開始日期到結束日期的匹配文檔。 </p> <p>所有日期都會依據格林威治標準時間進行搜尋。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> 日期範圍比對：結束日期 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_end_day, sp_end_month, sp_end_year  </span> </p> <p> </p> </td> 
   <td colname="col3"> </td> 
   <td colname="col4"> <p>這三份數值會指定要搜尋的特定日期範圍的結束日期。 請務必指定全部三個值，因為會忽略部分指定的日期。 </p> <p>只指定開始日期、結束日期或開始日期和結束日期是合法的。 如果僅指定了開始日期，則搜索將包括日期為開始日期或之後的匹配文檔。 如果僅指定了結束日期，則搜索將包括結束日期或結束日期之前的匹配文檔。 如果同時指定了開始日期和結束日期，則搜索將包括從開始日期到結束日期的匹配文檔。 </p> <p>所有日期都會依據格林威治標準時間進行搜尋。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>在搜尋欄位內 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_x  </span> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--&nbsp;List&nbsp;box&nbsp;selects&nbsp;the&nbsp;search&nbsp;field&nbsp;--&gt; 
      Within&nbsp;&lt;select&nbsp;name="sp_x"&nbsp;size=1&gt; 
      &lt;option&nbsp;value="any"&nbsp;selected&gt;Anywhere&lt;/option&gt; 
      &lt;option&nbsp;value="title"&gt;Title&lt;/option&gt; 
      &lt;option&nbsp;value="desc"&gt;Description&lt;/option&gt; 
      &lt;option&nbsp;value="keys"&gt;Keywords&lt;/option&gt; 
      &lt;option&nbsp;value="body"&gt;Body&lt;/option&gt; 
      &lt;option&nbsp;value="alt"&gt;Alternate&nbsp;text&lt;/option&gt; 
      &lt;option&nbsp;value="url"&gt;URL&lt;/option&gt; 
      &lt;option&nbsp;value="target"&gt;Target&lt;/option&gt; 
      &lt;option&nbsp;value="date"&gt;Date&lt;/option&gt;* 
      &lt;/select&gt; </code> </p> </td> 
   <td colname="col4"> <p><span class="codeph"> sp_x </span>清單方塊可讓您的客戶指定要在其中搜尋查詢字串的欄位。 </p> <p>客戶可以選擇所有欄位、標題、文檔說明、文檔關鍵字、正文、替代文本、文檔的URL、日期或目標關鍵字。 </p> <p>使用<span class="codeph"> sp_x </span>參數時，客戶不需要在搜尋查詢字串中指定「title：」、「desc：」、「keys：」、「body：」、「alt：」、「url：」和「target：」。 </p> <p>如果省略了<span class="codeph"> sp_x </span>參數，或將其設定為""或"any"，則客戶仍可使用欄位說明符字串。 如果將<span class="codeph"> sp_x </span>參數設定為特定欄位，則會忽略所有其他欄位說明符字串。 </p> <p>請參閱<a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local">關於搜尋</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>顯示結果計數 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_c  </span> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--&nbsp;List&nbsp;box&nbsp;selects&nbsp;number&nbsp;of&nbsp;results&nbsp;to&nbsp;show&nbsp;per&nbsp;page&nbsp;--&gt; 
      Show&nbsp;&lt;select&nbsp;name="sp_c"&nbsp;size=1&gt; 
      &lt;option&nbsp;value=5&gt;5&lt;/option&gt; 
      &lt;option&nbsp;value=10&nbsp;selected&gt;10&lt;/option&gt; 
      &lt;option&nbsp;value=25&gt;25&lt;/option&gt; 
      &lt;option&nbsp;value=50&gt;50&lt;/option&gt; 
      &lt;option&nbsp;value=100&gt;100&lt;/option&gt; 
      &lt;/select&gt;&nbsp;results </code> </p> </td> 
   <td colname="col4"> <p>可讓客戶選擇在每個搜尋結果頁面上顯示的搜尋結果數目。 </p> <p>表單中可以有任意數目或任意數目的選項。 確認「value=」值符合顯示的值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>顯示或隱藏摘要 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_m  </span> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--&nbsp;Show&nbsp;or&nbsp;hide&nbsp;summaries&nbsp;in&nbsp;search&nbsp;results&nbsp;--&gt; 
      &lt;select&nbsp;name="sp_m"&nbsp;size=1&gt; 
      &lt;option&nbsp;value=1&nbsp;selected&gt;with&lt;/option&gt; 
      &lt;option&nbsp;value=0&gt;without&lt;/option&gt; 
      &lt;/select&gt;&nbsp;summaries&nbsp; </code> </p> </td> 
   <td colname="col4"> <p>讓客戶選擇是否顯示每個相符項目的摘要文字。 </p> <p>如果要顯示摘要，請將值設為1。 如果要隱藏摘要，請將值設定為0。 您也可以搭配一組選項按鈕使用參數，如下列範例所示： </p> <p> <code class="syntax html"> &lt;!--&nbsp;Show&nbsp;or&nbsp;hide&nbsp;summaries&nbsp;in&nbsp;search&nbsp;results&nbsp;--&gt; 
      &lt;input&nbsp;type=radio&nbsp;name="sp_m"&nbsp;value=1&nbsp;selected&gt;Show&nbsp;summaries 
      &lt;input&nbsp;type=radio&nbsp;name="sp_m"&nbsp;value=0&gt;Hide&nbsp;summaries </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>按結果排序 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> sp_s  </span> </p> </td> 
   <td colname="col3"> <p> <code class="syntax html"> &lt;!--&nbsp;Sort&nbsp;results&nbsp;by&nbsp;relevance&nbsp;or&nbsp;by&nbsp;date&nbsp;--&gt; 
      Sort&nbsp;by&nbsp;&lt;select&nbsp;name="sp_s"&nbsp;size=1&gt; 
      &lt;option&nbsp;value=0&nbsp;selected&gt;relevance&lt;/option&gt; 
      &lt;option&nbsp;value=1&gt;date&lt;/option&gt; 
      &lt;/select&gt; </code> </p> </td> 
   <td colname="col4"> <p>可讓客戶根據關聯性或日期選擇列出結果。 </p> <p>將值設定為1時，結果將從最近更改的文檔列為最近更改的文檔。 當值設為0時，結果會從最相關和最不相關的中列出。 您也可以搭配選項按鈕使用此參數，如下列範例所示： </p> <p> <code class="syntax html"> &lt;!--&nbsp;Sort&nbsp;results&nbsp;by&nbsp;relevance&nbsp;or&nbsp;by&nbsp;date&nbsp;--&gt; 
      &lt;input&nbsp;type=radio&nbsp;name="sp_s"&nbsp;value=0&nbsp;selected&gt;Sort&nbsp;by&nbsp;relevance 
      &lt;input&nbsp;type=radio&nbsp;name="sp_s"&nbsp;value=1&gt;Sort&nbsp;by&nbsp;date </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 進階搜尋表單HTML程式碼 {#reference_9AAD4A46B68D4D48865508982CB86DB9}

用於產生進階搜尋表單的HTML表單程式碼，會顯示在「範例進階搜尋表單」主題頂端。

請參閱[範例進階搜尋表單](#reference_82E1051918744EBA88A01E9E6AE42C4A)。

如果您使用此代碼，請記得將`sp99999999`的`sp_a`值替換為實際帳號。

若要尋找您的帳戶號碼，請在產品功能表上按一下「**[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Account Settings]**」。

```
<form method="get" action="https://search.atomz.com/search/"> 
<table cellspacing=0 cellpadding=0 border=0> 
<tr><td colspan=4> 
<b>Search For:</b><br> 
<input size=35 name="sp_q"> 
<!-- The "Search" button --> 
<input type=submit value="Search"> 
<input type=hidden name="sp_a" value="sp99999999"> 
<input type=hidden name="sp_f" value="ISO-8859-1"> 
</td></tr> 
<input type=hidden name="sp_advanced" value=1> 
<!-- Allow "any," "all," or "phrase" --> 
<tr><td valign=top> 
<b>Match: </b> 
</td><td colspan=4> 
<input type=radio name="sp_p" value="any">Any word 
<input type=radio name="sp_p" value="all" checked>All words 
<input type=radio name="sp_p" value="phrase">Exact phrase<br> 
<!-- Checkbox enables sound-alike matching --> 
<input type=hidden name="sp_w_control" value=1> 
<input type=checkbox name="sp_w" value="alike" checked> 
Sound-alike matching 
</td></tr> 
<!-- Date range criteria --> 
<tr><td><b>Dated:</b></td><td colspan=4> 
<input type=radio name="sp_d" value="custom" checked> 
<select name="sp_date_range" size=1> 
<option value=-1 selected>Anytime</option> 
<option value=7>Within the last week</option> 
<option value=14>Within the last 2 weeks</option> 
<option value=30>Within the last 30 days</option> 
<option value=60>Within the last 60 days</option> 
<option value=90>Within the last 90 days</option> 
<option value=180>Within the last 180 days</option> 
<option value=365>Within the last year</option> 
<option value=730>Within the last two years</option> 
</select> 
</td></tr> 
<tr><td></td><td rowspan=2> 
<input type=radio name="sp_d" value=specific> 
</td><td align=right>From:</td><td> 
<select name="sp_start_month" size=1> 
<option value=0 selected></option> 
<option value=1>January</option> 
<option value=2>February</option> 
<option value=3>March</option> 
<option value=4>April</option> 
<option value=5>May</option> 
<option value=6>June</option> 
<option value=7>July</option> 
<option value=8>August</option> 
<option value=9>September</option> 
<option value=10>October</option> 
<option value=11>November</option> 
<option value=12>December</option> 
</select> 
<select name="sp_start_day" size=1> 
<option value=0 selected></option> 
<option value=1>1</option> 
<option value=2>2</option> 
<option value=3>3</option> 
<option value=4>4</option> 
<option value=5>5</option> 
<option value=6>6</option> 
<option value=7>7</option> 
<option value=8>8</option> 
<option value=9>9</option> 
<option value=10>10</option> 
<option value=11>11</option> 
<option value=12>12</option> 
<option value=13>13</option> 
<option value=14>14</option> 
<option value=15>15</option> 
<option value=16>16</option> 
<option value=17>17</option> 
<option value=18>18</option> 
<option value=19>19</option> 
<option value=20>20</option> 
<option value=21>21</option> 
<option value=22>22</option> 
<option value=23>23</option> 
<option value=24>24</option> 
<option value=25>25</option> 
<option value=26>26</option> 
<option value=27>27</option> 
<option value=28>28</option> 
<option value=29>29</option> 
<option value=30>30</option> 
<option value=31>31</option> 
</select> 
<!--comma-->, 
<input size=4 name="sp_start_year"> 
</td></tr> 
<tr><td></td> 
<td align=right>To:</td><td> 
<select name="sp_end_month" size=1> 
<option value=0 selected></option> 
<option value=1>January</option> 
<option value=2>February</option> 
<option value=3>March</option> 
<option value=4>April</option> 
<option value=5>May</option> 
<option value=6>June</option> 
<option value=7>July</option> 
<option value=8>August</option> 
<option value=9>September</option> 
<option value=10>October</option> 
<option value=11>November</option> 
<option value=12>December</option> 
</select> 
<select name="sp_end_day" size=1> 
<option value=0 selected></option> 
<option value=1>1</option> 
<option value=2>2</option> 
<option value=3>3</option> 
<option value=4>4</option> 
<option value=5>5</option> 
<option value=6>6</option> 
<option value=7>7</option> 
<option value=8>8</option> 
<option value=9>9</option> 
<option value=10>10</option> 
<option value=11>11</option> 
<option value=12>12</option> 
<option value=13>13</option> 
<option value=14>14</option> 
<option value=15>15</option> 
<option value=16>16</option> 
<option value=17>17</option> 
<option value=18>18</option> 
<option value=19>19</option> 
<option value=20>20</option> 
<option value=21>21</option> 
<option value=22>22</option> 
<option value=23>23</option> 
<option value=24>24</option> 
<option value=25>25</option> 
<option value=26>26</option> 
<option value=27>27</option> 
<option value=28>28</option> 
<option value=29>29</option> 
<option value=30>30</option> 
<option value=31>31</option> 
</select> 
<!--comma-->, 
<input size=4 name="sp_end_year"> 
</td></tr> 
<!-- List box selects the search field --> 
<tr><td valign=top> 
<b>Within: </b> 
</td><td colspan=4><select name="sp_x" size=1> 
<option value="any" selected>Anywhere</option> 
<option value="title">Title</option> 
<option value="desc">Description</option> 
<option value="keys">Keywords</option> 
<option value="body">Body</option> 
<option value="alt">Alternate text</option> 
<option value="url">URL</option> 
<option value="target">Target</option> 
</select> 
</td></tr> 
<!-- List box selects number of results to show per page --> 
<tr><td valign=top> 
<b>Show: </b> 
</td><td colspan=4><select name="sp_c" size=1> 
<option value=5>5</option> 
<option value=10 selected>10</option> 
<option value=25>25</option> 
<option value=50>50</option> 
<option value=100>100</option> 
</select> results  
<!-- Show or hide summaries in search results --> 
<select name="sp_m" size=1> 
<option value=1 selected>with</option> 
<option value=0>without</option> 
</select> summaries<br> 
</td></tr> 
<!-- Sort results by relevance or by date --> 
<tr><td valign=top> 
<b>Sort by: </b> 
</td><td colspan=4><select name="sp_s" size=1> 
<option value=0 selected>relevance</option> 
<option value=1>date</option> 
</select> 
</td></tr> 
</table> 
</form>
```

## 高級搜索表單模板代碼 {#reference_D762C22E754E462DBEECD88D2C3FA579}

您可以將進階搜尋表單HTML程式碼新增至範本，讓任何參數的預設選項與先前的搜尋相同。

換言之，如果客戶按一下&#x200B;**[!UICONTROL Exact phrase]**&#x200B;選項按鈕，您可以確保在顯示搜索結果時預設選擇了單選按鈕。

若要完成此功能，請從標準HTML標籤中移除所有「已勾選」或「已選取」說明符，然後取代下列HTML標籤：

* `<input>`
* `<select>`
* `<option>`
* `</option>`
* `</select>`

以及下列對應的範本標籤：

* `<search-input>`
* `<search-select>`
* `<search-option>`
* `</search-option>`
* `</search-select>`

要執行此操作，請使用下列程式碼作為搜尋範本上的`<form>`標籤。

```
<!-- Adobe Target results section.--> 
 
<!-- Show heading and logo graphic. --> 
<SEARCH-IF-RESULTS> 
<b>SEARCH RESULTS <SEARCH-LOWER> - <SEARCH-UPPER></b> 
of <SEARCH-TOTAL> total results for <b><SEARCH-QUERY></b><br> 
</SEARCH-IF-RESULTS> 
<SEARCH-IF-NOT-RESULTS> 
<b>SEARCH RESULTS</b> for <b><SEARCH-QUERY></b><br> 
</SEARCH-IF-NOT-RESULTS> 
<SEARCH-LOGO><br> 
 
<!-- Display Results. --> 
<SEARCH-RESULTS LENGTH=160> 
<p><b><SEARCH-LINK><SEARCH-TITLE LENGTH=160></SEARCH-LINK></b><br> 
<SEARCH-IF-SHOW-SUMMARIES> 
<SEARCH-IF-CONTEXT LENGTH=240><SEARCH-CONTEXT><br></SEARCH-IF-CONTEXT> 
<font size="-1"><SEARCH-URL LENGTH=60></font><br> 
</SEARCH-IF-SHOW-SUMMARIES> 
</SEARCH-RESULTS> 
 
<!-- If no results, show a message. --> 
<SEARCH-IF-NOT-RESULTS><p> 
Sorry, no matches were found containing <b><SEARCH-QUERY>.</b> 
</SEARCH-IF-NOT-RESULTS> 
<!-- Show By Relevance, By Date links, Show/Hide Summaries links. --> 
<SEARCH-IF-RESULTS><p> 
<SEARCH-IF-SORT-BY-DATE> 
<b><SEARCH-SORT-BY-SCORE COUNT=10>Sort By Relevance</SEARCH-SORT-BY-SCORE></b> 
</SEARCH-IF-SORT-BY-DATE> 
<SEARCH-IF-SORT-BY-SCORE> 
<b><SEARCH-SORT-BY-DATE COUNT=10>Sort By Date</SEARCH-SORT-BY-DATE></b> 
</SEARCH-IF-SORT-BY-SCORE> 
| <b> 
<SEARCH-IF-SHOW-SUMMARIES> 
<SEARCH-HIDE-SUMMARIES COUNT=20>Hide Summaries</SEARCH-HIDE-SUMMARIES> 
</SEARCH-IF-SHOW-SUMMARIES> 
<SEARCH-IF-HIDE-SUMMARIES> 
<SEARCH-SHOW-SUMMARIES COUNT=10>Show Summaries</SEARCH-SHOW-SUMMARIES> 
</SEARCH-IF-HIDE-SUMMARIES> 
</b><br> 
</SEARCH-IF-RESULTS> 
 
<!-- Display Prev & Next links. --> 
<SEARCH-IF-RESULTS> 
<SEARCH-IF-PREV-COUNT> 
<b><SEARCH-PREV>Prev <SEARCH-PREV-COUNT></SEARCH-PREV></b> 
<SEARCH-IF-NEXT-COUNT> | </SEARCH-IF-NEXT-COUNT> 
</SEARCH-IF-PREV-COUNT> 
<SEARCH-IF-NEXT-COUNT> 
<b><SEARCH-NEXT>Next <SEARCH-NEXT-COUNT></SEARCH-NEXT></b><br> 
</SEARCH-IF-NEXT-COUNT><p> 
</SEARCH-IF-RESULTS> 
 
<!-- Put up the next form. --> 
<form method="get" action="https://search.atomz.com/search/"> 
<SEARCH-IF-NOT-ADVANCED> 
<SEARCH-INPUT-ACCOUNT> 
<SEARCH-INPUT-GALLERY> 
<SEARCH-INPUT-QUERY SIZE=25> 
<SEARCH-INPUT type=hidden name=sp_p> 
<input type=submit value="New Search"> 
<SEARCH-IF-INPUT-COLLECTIONS> 
<br><SEARCH-INPUT-COLLECTIONS> 
</SEARCH-IF-INPUT-COLLECTIONS> 
</SEARCH-IF-NOT-ADVANCED> 
<SEARCH-IF-ADVANCED> 
<table cellspacing=0 cellpadding=0 border=0> 
<tr><td colspan=4> 
<b>Search For:</b><br> 
<SEARCH-INPUT-QUERY SIZE=35> 
 
<!-- The "Search" button --> 
<input type=submit value="New Search"> 
<SEARCH-INPUT-ACCOUNT> 
<SEARCH-INPUT-GALLERY> 
</td></tr> 
<SEARCH-IF-INPUT-COLLECTIONS> 
<!-- Collections --> 
<tr><td> 
<b>In: </b> 
</td><td colspan=4> 
<SEARCH-INPUT-COLLECTIONS> 
</td></tr> 
</SEARCH-IF-INPUT-COLLECTIONS> 
<input type=hidden name="sp_advanced" value=1> 
 
<!-- Allow "any," "all," or "phrase" --> 
<tr><td valign=top> 
<b>Match: </b> 
</td><td colspan=4> 
<SEARCH-INPUT type=radio name="sp_p" value="any">Any word 
<SEARCH-INPUT type=radio name="sp_p" value="all">All words 
<SEARCH-INPUT type=radio name="sp_p" value="phrase">Exact phrase<br> 
<!-- Checkbox enables sound-alike matching --> 
<input type=hidden name="sp_w_control" value=1> 
<SEARCH-INPUT type=checkbox name="sp_w" value="alike">Sound-alike matching 
</td></tr> 
 
<!-- Date range section --> 
<tr> 
<td><b>Dated:</b></td> 
<td colspan=3> 
<SEARCH-INPUT type=radio name="sp_d" value="custom"> 
<SEARCH-SELECT name="sp_date_range" size=1> 
<SEARCH-OPTION value=-1>Anytime</SEARCH-OPTION> 
<SEARCH-OPTION value=7>Within the last week</SEARCH-OPTION> 
<SEARCH-OPTION value=14>Within the last 2 weeks</SEARCH-OPTION> 
<SEARCH-OPTION value=30>Within the last 30 days</SEARCH-OPTION> 
<SEARCH-OPTION value=60>Within the last 60 days</SEARCH-OPTION> 
<SEARCH-OPTION value=90>Within the last 90 days</SEARCH-OPTION> 
<SEARCH-OPTION value=180>Within the last 180 days</SEARCH-OPTION> 
<SEARCH-OPTION value=365>Within the last year</SEARCH-OPTION> 
<SEARCH-OPTION value=730>Within the last two years</SEARCH-OPTION> 
</SEARCH-SELECT> 
</td></tr> 
<tr><td></td><td rowspan=2> 
<SEARCH-INPUT type=radio name="sp_d" value=specific></td> 
<td align=right>From:</td><td> 
<SEARCH-SELECT name="sp_start_month" size=1> 
<SEARCH-OPTION value=0></SEARCH-OPTION> 
<SEARCH-OPTION value=1>January</SEARCH-OPTION> 
<SEARCH-OPTION value=2>February</SEARCH-OPTION> 
<SEARCH-OPTION value=3>March</SEARCH-OPTION> 
<SEARCH-OPTION value=4>April</SEARCH-OPTION> 
<SEARCH-OPTION value=5>May</SEARCH-OPTION> 
<SEARCH-OPTION value=6>June</SEARCH-OPTION> 
<SEARCH-OPTION value=7>July</SEARCH-OPTION> 
<SEARCH-OPTION value=8>August</SEARCH-OPTION> 
<SEARCH-OPTION value=9>September</SEARCH-OPTION> 
<SEARCH-OPTION value=10>October</SEARCH-OPTION> 
<SEARCH-OPTION value=11>November</SEARCH-OPTION> 
<SEARCH-OPTION value=12>December</SEARCH-OPTION> 
</SEARCH-SELECT> 
<SEARCH-SELECT name="sp_start_day" size=1> 
<SEARCH-OPTION value=0></SEARCH-OPTION> 
<SEARCH-OPTION value=1>1</SEARCH-OPTION> 
<SEARCH-OPTION value=2>2</SEARCH-OPTION> 
<SEARCH-OPTION value=3>3</SEARCH-OPTION> 
<SEARCH-OPTION value=4>4</SEARCH-OPTION> 
<SEARCH-OPTION value=5>5</SEARCH-OPTION> 
<SEARCH-OPTION value=6>6</SEARCH-OPTION> 
<SEARCH-OPTION value=7>7</SEARCH-OPTION> 
<SEARCH-OPTION value=8>8</SEARCH-OPTION> 
<SEARCH-OPTION value=9>9</SEARCH-OPTION> 
<SEARCH-OPTION value=10>10</SEARCH-OPTION> 
<SEARCH-OPTION value=11>11</SEARCH-OPTION> 
<SEARCH-OPTION value=12>12</SEARCH-OPTION> 
<SEARCH-OPTION value=13>13</SEARCH-OPTION> 
<SEARCH-OPTION value=14>14</SEARCH-OPTION> 
<SEARCH-OPTION value=15>15</SEARCH-OPTION> 
<SEARCH-OPTION value=16>16</SEARCH-OPTION> 
<SEARCH-OPTION value=17>17</SEARCH-OPTION> 
<SEARCH-OPTION value=18>18</SEARCH-OPTION> 
<SEARCH-OPTION value=19>19</SEARCH-OPTION> 
<SEARCH-OPTION value=20>20</SEARCH-OPTION> 
<SEARCH-OPTION value=21>21</SEARCH-OPTION> 
<SEARCH-OPTION value=22>22</SEARCH-OPTION> 
<SEARCH-OPTION value=23>23</SEARCH-OPTION> 
<SEARCH-OPTION value=24>24</SEARCH-OPTION> 
<SEARCH-OPTION value=25>25</SEARCH-OPTION> 
<SEARCH-OPTION value=26>26</SEARCH-OPTION> 
<SEARCH-OPTION value=27>27</SEARCH-OPTION> 
<SEARCH-OPTION value=28>28</SEARCH-OPTION> 
<SEARCH-OPTION value=29>29</SEARCH-OPTION> 
<SEARCH-OPTION value=30>30</SEARCH-OPTION> 
<SEARCH-OPTION value=31>31</SEARCH-OPTION> 
</SEARCH-SELECT><!--comma-->, 
<SEARCH-INPUT size=4 name="sp_start_year"> 
</td></tr> 
<tr><td></td> 
<td align=right>To:</td><td> 
<SEARCH-SELECT name="sp_end_month" size=1> 
<SEARCH-OPTION value=0></SEARCH-OPTION> 
<SEARCH-OPTION value=1>January</SEARCH-OPTION> 
<SEARCH-OPTION value=2>February</SEARCH-OPTION> 
<SEARCH-OPTION value=3>March</SEARCH-OPTION> 
<SEARCH-OPTION value=4>April</SEARCH-OPTION> 
<SEARCH-OPTION value=5>May</SEARCH-OPTION> 
<SEARCH-OPTION value=6>June</SEARCH-OPTION> 
<SEARCH-OPTION value=7>July</SEARCH-OPTION> 
<SEARCH-OPTION value=8>August</SEARCH-OPTION> 
<SEARCH-OPTION value=9>September</SEARCH-OPTION> 
<SEARCH-OPTION value=10>October</SEARCH-OPTION> 
<SEARCH-OPTION value=11>November</SEARCH-OPTION> 
<SEARCH-OPTION value=12>December</SEARCH-OPTION> 
</SEARCH-SELECT> 
<SEARCH-SELECT name="sp_end_day" size=1> 
<SEARCH-OPTION value=0></SEARCH-OPTION> 
<SEARCH-OPTION value=1>1</SEARCH-OPTION> 
<SEARCH-OPTION value=2>2</SEARCH-OPTION> 
<SEARCH-OPTION value=3>3</SEARCH-OPTION> 
<SEARCH-OPTION value=4>4</SEARCH-OPTION> 
<SEARCH-OPTION value=5>5</SEARCH-OPTION> 
<SEARCH-OPTION value=6>6</SEARCH-OPTION> 
<SEARCH-OPTION value=7>7</SEARCH-OPTION> 
<SEARCH-OPTION value=8>8</SEARCH-OPTION> 
<SEARCH-OPTION value=9>9</SEARCH-OPTION> 
<SEARCH-OPTION value=10>10</SEARCH-OPTION> 
<SEARCH-OPTION value=11>11</SEARCH-OPTION> 
<SEARCH-OPTION value=12>12</SEARCH-OPTION> 
<SEARCH-OPTION value=13>13</SEARCH-OPTION> 
<SEARCH-OPTION value=14>14</SEARCH-OPTION> 
<SEARCH-OPTION value=15>15</SEARCH-OPTION> 
<SEARCH-OPTION value=16>16</SEARCH-OPTION> 
<SEARCH-OPTION value=17>17</SEARCH-OPTION> 
<SEARCH-OPTION value=18>18</SEARCH-OPTION> 
<SEARCH-OPTION value=19>19</SEARCH-OPTION> 
<SEARCH-OPTION value=20>20</SEARCH-OPTION> 
<SEARCH-OPTION value=21>21</SEARCH-OPTION> 
<SEARCH-OPTION value=22>22</SEARCH-OPTION> 
<SEARCH-OPTION value=23>23</SEARCH-OPTION> 
<SEARCH-OPTION value=24>24</SEARCH-OPTION> 
<SEARCH-OPTION value=25>25</SEARCH-OPTION> 
<SEARCH-OPTION value=26>26</SEARCH-OPTION> 
<SEARCH-OPTION value=27>27</SEARCH-OPTION> 
<SEARCH-OPTION value=28>28</SEARCH-OPTION> 
<SEARCH-OPTION value=29>29</SEARCH-OPTION> 
<SEARCH-OPTION value=30>30</SEARCH-OPTION> 
<SEARCH-OPTION value=31>31</SEARCH-OPTION> 
</SEARCH-SELECT><!--comma-->, 
<SEARCH-INPUT size=4 name="sp_end_year"> 
</td></tr> 
<!-- List box selects the search field --> 
<tr><td valign=top> 
<b>Within: </b> 
</td><td colspan=4><SEARCH-SELECT name="sp_x" size=1> 
<SEARCH-OPTION value="any">Anywhere</SEARCH-OPTION> 
<SEARCH-OPTION value="title">Title</SEARCH-OPTION> 
<SEARCH-OPTION value="desc">Description</SEARCH-OPTION> 
<SEARCH-OPTION value="keys">Keywords</SEARCH-OPTION> 
<SEARCH-OPTION value="body">Body</SEARCH-OPTION> 
<SEARCH-OPTION value="alt">Alternate text</SEARCH-OPTION> 
<SEARCH-OPTION value="url">URL</SEARCH-OPTION> 
<SEARCH-OPTION value="target">Target</SEARCH-OPTION> 
</SEARCH-SELECT></td></tr> 
<!-- List box selects number of results to show per page --> 
<tr><td valign=top> 
<b>Show:</b> 
</td><td colspan=4><SEARCH-SELECT name="sp_c" size=1> 
<SEARCH-OPTION value=5>5</SEARCH-OPTION> 
<SEARCH-OPTION value=10>10</SEARCH-OPTION> 
<SEARCH-OPTION value=25>25</SEARCH-OPTION> 
<SEARCH-OPTION value=50>50</SEARCH-OPTION> 
<SEARCH-OPTION value=100>100</SEARCH-OPTION> 
</SEARCH-SELECT> results  
<!-- Show or hide summaries in search results --> 
<SEARCH-SELECT name="sp_m" size=1> 
<SEARCH-OPTION value=1>with</SEARCH-OPTION> 
<SEARCH-OPTION value=0>without</SEARCH-OPTION> 
</SEARCH-SELECT> summaries<br></td></tr> 
<!-- Sort results by relevance or by date --> 
<tr><td valign=top> 
<b>Sort by: </b> 
</td><td colspan=4><SEARCH-SELECT name="sp_s" size=1> 
<SEARCH-OPTION value=0>relevance</SEARCH-OPTION> 
<SEARCH-OPTION value=1>date</SEARCH-OPTION> 
</SEARCH-SELECT></td></tr> 
</table> 
</SEARCH-IF-ADVANCED> 
</form>
```
