---
description: 您可以使用Facet來自訂您的表現層，並為您的使用者提供引導式搜尋功能，讓他們深入探究其搜尋結果。
solution: Target
subtopic: Navigation
title: 關於Facet
topic: Design,Site search and merchandising
uuid: 28bc4d4d-a84c-4a77-befb-b0fb3bbdb966
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '3832'
ht-degree: 1%

---


# 關於Facet{#about-facets}

您可以使用Facet來自訂您的表現層，並為您的使用者提供引導式搜尋功能，讓他們深入探究其搜尋結果。

## 使用Facets {#concept_FA912B3B41EE493DB2F492D188457FF5}

例如，假設訪客造訪了銷售工具的網站，則會搜尋扳手。 該公司可以從兩個方面：一個是指定所有找到的扳手品牌，另一個是指定所有扳手尺寸。 客戶可以按一下適當面內的任何品牌或尺寸，縮小結果範圍並快速找到所需的正確扳手。

您可以根據任何現有的中繼資料定義建立Facet。 如果Facet在中繼資料中定義為「日期」類型，則會顯示為日期範圍Facet。

[!DNL Staged Facets]頁面上的表格顯示組成每個新增Facet之設定的一般概述。 您可以新增刻面，並編輯或刪除現有刻面。 您可以使用頁面右上角的&#x200B;**[!UICONTROL History]**，回復您對Facet所做的任何變更。

Facet設定預設會儲存，讓您在即時推播變更之前先測試這些變更。

請參閱[關於測試](../c-about-staging.md#concept_08B8F3CA1F4241108F14BA7FC7806CA7)。

您可以使用&#x200B;**[!UICONTROL View Live Settings]**&#x200B;來比較您的分段設定與目前的即時設定。 使用&#x200B;**[!UICONTROL View Staged Settings]**&#x200B;返回測試區。 對於已分段的項目，設定的即時版本為唯讀。 因此，您可透過即時推送階段設定來控制它。 當您對已對分段Facet所做的任何變更感到滿意後，請按一下&#x200B;**[!UICONTROL Push Live]**&#x200B;即時推送。

## 日期範圍Facet {#section_FEFFF6B5B6534456913189FEF559BA58}

在中繼資料中定義為「日期」類型的刻面會與其他刻面處理不同。 這些值不會被視為一組值，而會被視為日期範圍、開始日期、結束日期或兩者。

日期範圍Facet的值為開始日期，後面接著&quot;BTW&quot;（對於&quot;between&quot;），後面接著結束日期。 日期採用下列兩種格式：

mm-dd-yyyy

yyyy/mm/dd

需要4位數的年數。 至少必須有一個開始日期或結束日期，但兩者皆非必要。 例如，「12/1/2007BTW1/4/2009」系指2007年12月1日至2009年1月4日之間的所有日期。 但是，「1-1-2005BTW」系指自2005年1月1日起的所有日期。

您可以使用簡報範本標籤`<guided-facet-value/>`來取得日期範圍Facet的值，例如一般Facet。 目前，需要JavaScript才能讓使用者輸入要搜尋的日期範圍。 例如，您可以從兩個參加項目欄位輸入開始日期和結束日期。 然後，您可以驗證輸入，並將新Facet的值（從兩個輸入欄位建立）和Facet名稱附加至現有的URL。

請參閱[簡報範本標籤](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)。

以下程式碼範例是如何在頁面上呈現日期範圍的範例。 如果已選取，則會顯示現有的日期範圍；否則，它會呈現簡單的輸入表單。 提交表單時，會執行簡單驗證。 然後，它會將瀏覽器傳送至包含兩個新參數的新URL:

* `q#` -代表從兩個輸入欄位組合的所選日期範圍。
* `x#` -命名Facet。在此範例中，日期範圍Facet的名稱為「已修改」。

由於安全原因，Apache不允許URL路徑中的`%2F`部分，因此需要代碼中的`replace(/%2F/ig, '~2F')`部分；使用SEO URL時，查詢位於URL路徑中。 因此，`/`會編碼為`~2F`，而非`%2F`，因為它通常位於URL中。

```
<div class="date_range"> 
 <p>Date Range</p> 
 <guided-if-facet-selected gsname="modified"> 
  <guided-facet-values gsname="modified"> 
   <script> 
   var modified_daterange= '<guided-facet-value />'.split(/BTW/) ; 
   if (modified_daterange[0]=='') modified_daterange[0]= '--/--/----' ; 
   if (modified_daterange[1]=='') modified_daterange[1]= '--/--/----' ; 
   document.write('From: ' + modified_daterange[0]) ; 
   document.write('<br>To: ' + modified_daterange[1]) ; 
   </script> 
  </guided-facet-values> 
 
 <guided-else-facet-selected> 
  <form action="#"> 
   From: <input name="dateFrom" size=10> 
   <br>To: <input name="dateTo" size=10> 
   <br><input type="button" value="Go" onclick="goClick(this.form)"> 
  </form> 
  <script> 
  function goClick(f) { 
   if (f.dateFrom.value=='' && f.dateTo.value=='') { 
    alert('You must enter either a From: date or a To: date.') ; 
    return ; 
   } 
   if ( f.dateFrom.value!='' && !f.dateFrom.value.match(/^\d+[\/\-]\d+[\/\-]\d\d\d\d$/) ) { 
    alert('From: date must be in "mm/dd/yyyy" or "mm-dd-yyyy" format.') ; 
    return ; 
   } 
   if ( f.dateTo.value!='' && !f.dateTo.value.match(/^\d+[\/\-]\d+[\/\-]\d\d\d\d$/) ) { 
    alert('To: date must be in "mm/dd/yyyy" or "mm-dd-yyyy" format.') ; 
    return ; 
   } 
   // Note that "/" is encoded as "~2F" instead of "%2F" to avoid Apache 404 error. 
   var new_url= '<guided-current-path />&<guided-query-param-name gsname="q#" offset="0" />=' 
    + encodeURIComponent(f.dateFrom.value).replace(/%2F/ig, '~2F') + 'BTW' 
    + encodeURIComponent(f.dateTo  .value).replace(/%2F/ig, '~2F') 
    + '&<guided-query-param-name gsname="x#" offset="0" />=modified' ; 
   location.href= new_url ; 
  } 
  </script> 
 </guided-if-facet-selected> 
</div>
```

## 關於巢狀Facet {#section_6BC77F38DE9F43D5B6911F8CECB15DFC}

巢狀Facet是顯示多層類別的Facet，如下所示：

![](assets/nestedfacets.png)

「女性」和「男性」類別位於頂端或父項面。 子類別(例如「附件」(Accessories)和「鞋類」(Sooters))位於下層或下層。

目前支援的巢狀Facet深度為2，但可位於下鑽清單的任何位置。

以下是各種類型巢狀刻面的行為：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>巢狀Facet類型的行為 </p> </th> 
   <th colname="col2" class="entry"> <p>行為 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>一般 </p> </td> 
   <td colname="col2"> <p>一般巢狀Facet的行為是，如果其他Facet縮小搜索範圍，則會縮小。 </p> <p>如果選取巢狀Facet，則會縮小為選取範圍。 如果選取了父Facet，則只有該父Facet會與其餘所有子Facet一起顯示。 如果選取了子Facet，則Facet只會顯示所選的父Facet和所選的子Facet。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自黏 </p> </td> 
   <td colname="col2"> <p>黏著巢狀Facet的行為是會嘗試根據其他Facet的狀態或搜尋准則，盡量讓Facet保持開啟。 如果選取子刻面，則會計入自黏深度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>多選 </p> </td> 
   <td colname="col2"> <p>多選Facet的行為是讓Facet保持開啟。 任何新選取項都會嘗試清除所有其他Facet選取項目，除非Facet是巢狀Facet類別的「父項」。 在本例中，「父項」是指類別Facet，而非巢狀Facet的頂層類別。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>類別多選 </p> </td> 
   <td colname="col2"> <p>「按贊多選」巢狀Facet類型，但有下列例外： </p> 
    <ul id="ul_D5AB6AF3169A483E8F3FC6D2A2EA3A28"> 
     <li id="li_9308156EF2FF43CE9DFB933F13786C58">如果首次選取此刻面，則先前選取的任何其他刻面都會取消選取。 </li> 
     <li id="li_DD96D6802A9C479283212A0FD68C6F85">如果客戶直接向下切入子刻面而未按一下父刻面或不同父刻面的同級，則先前選擇的其他刻面也會取消選取。 </li> 
     <li id="li_8BF58F10969B4743986D5D0E0086AD6C">他們可以有父母，因為類別小麵包有父母。 請勿將此行為與所有巢狀刻面的父子關係混淆。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

另請參閱[關於Facet邊欄](../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB)。

## 新增Facet {#task_FC07BFFA62CA4B718D6CBF4F2855C89B}

您可以新增刻面來自訂您的表現層，並為客戶提供引導式搜尋功能，讓他們深入探究其搜尋結果。

<!-- 

t_adding_a_new_facet.xml

 -->

[!DNL Facets]頁面上的Facet表格顯示組成單一Facet的設定摘錄。 您可以新增刻面，並編輯或刪除現有刻面。 您對刻面所做的任何變更都可以使用「步驟記錄」功能來還原。

>[!NOTE]
>
>請確定您參考簡報範本中的Facet，以便在網站上顯示。

另請參閱[關於Facet邊欄](../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB)。

**若要新增Facet**

1. 在新增Facet之前，請先確定您已執行下列動作，再繼續下一步：

   * 已定義一些meta標籤欄位。

      請參閱[新增中繼標籤欄位](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。
   * 將中繼資料插入索引中。
請參閱[添加欄位插入定義](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Facets.]**」
1. 在[!DNL Facets]頁面上，按一下&#x200B;**[!UICONTROL Add New Facet]**。
1. 在[!DNL Add Facet]頁面上，設定您想要的選項。

   這些設定會同時影響Facet的行為和預設呈現方式。 您可以透過簡報範本的設定，覆寫其中一些設定。

   如果Facet在中繼資料中定義為「日期」類型，則會顯示為日期範圍。

   請參閱[日期範圍Facet](../c-about-design-menu/c-about-facets.md#section_FEFFF6B5B6534456913189FEF559BA58)。

   視您選取的Facet選項而定，並非所有選項都可用。

   <!-- 
   r_add_facet_options.xml
   -->

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>選項 </p> </th> 
      <th colname="col2" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Facet名稱 </p> </td> 
      <td colname="col2"> <p>識別指定Facet的名稱。 </p> <p> <p>注意： 您只能以現有使用者定義的中繼資料為基礎來建立Facet。 如果下拉式清單中沒有可用的刻面，則您必須先定義一些中繼資料。 </p> </p> <p>請參閱<a href="../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5" type="task" format="dita" scope="local">新增中繼標籤欄位</a>。 </p> <p>若要根據欄位表格建立Facet，請使用自訂Facet名稱並指定欄位表格名稱。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>顯示標籤 </p> </td> 
      <td colname="col2"> <p>設定Facet的標籤，以便用於導覽路徑標示中，而非中繼資料欄位名稱（使用<span class="codeph"> &lt;guided-breadcrumb-label&gt; </span>標籤）或獨立值（使用<span class="codeph"> &lt;guided-facet-display-name&gt; </span>標籤）。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>行為 </p> </td> 
      <td colname="col2"> <p>設定三個Facet行為之一。 </p> <p> 
      <ul id="ul_67C19E1C16224B9990F04A0D05BD3D05"> 
      <li id="li_6B232C11A61840B68CA59E1F593405A0"> <span class="uicontrol"> 一般 </span> <p>當客戶點按行為設為<span class="uicontrol">一般</span>的Facet時，會深入到該項目的搜尋結果中。 從那裡，客戶可以進一步細化和縮小搜索結果的數量。 </p> </li> 
      <li id="li_7D7C43A7F7AB4B84A9B0FEF34627605A"> <span class="uicontrol"> 類別 </span> <p>類別Facet的作用類似導覽元素。 這些刻面是頂層刻面，客戶通常在透過屬性選項揭露刻面之前，先進行深入探討。 當選取其他刻面並保持開啟時，類別刻面不會縮小。 按一下類別Facet中的不同值，會取消選取頁面上除該類別Facet的父項以外的所有其他Facet。 </p> </li> 
      <li id="li_01255993D71F40DBA8870AA3FEA7D304"> <span class="uicontrol"> 類別多選  </span> <p>Facet是類別Facet，可支援從項目一起「或」的Facet選取多個項目。 </p> </li> 
      </ul> 
      <ul id="ul_683F6D3FC8524E65AF303453ADDB6001"> 
        <li id="li_81F504D1D1294666BBBC5EA43B34B712"> <span class="uicontrol"> 自黏 </span> <p>當客戶點按行為設為「嚴格<span class="uicontrol"></span>」的Facet時，具有選取選項的Facet會在向下切入期間保持開啟狀態。 當您想要讓客戶變更先前的選擇時，這個選項很實用。 </p> </li> 
      </ul> 
      <ul id="ul_8E871D63B09445268C600C8ABC20F6A4"> 
        <li id="li_F88AC5528B0C4751BC4CFE7FA9525857"> <span class="uicontrol"> 多選  </span> <p>允許從Facet選取多個項目，其中Facet內的項目是「ORed」一起選取。 此選項對於可能顯示顏色等次要屬性的Facet很有用，而您希望讓客戶能夠建立查詢，讓他們「顯示我大小的紅色或黑色鞋」。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>一律顯示 </p> </td> 
      <td colname="col2"> <p>對於一般或嚴格Facet，請將Facet設定為隨時讓客戶可看見。 </p> <p>只有在從<span class="uicontrol">「行為</span>」下拉式清單中選擇「<span class="uicontrol">一般</span>」、「<span class="uicontrol">類別</span>」或「<span class="uicontrol">嚴格</span>」時，此選項才可用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Facet的父項 </p> </td> 
      <td colname="col2"> <p>只有在從<span class="uicontrol">行為</span>下拉清單中選擇<span class="uicontrol">類別</span>或<span class="uicontrol">類別多選</span>時，此選項才可用。 </p> <p>指出類別Facet的父項。 類別父Facet中選取的項目可用來縮小目前類別Facet中可用的選項。 當客戶與類別Facet互動時，不會取消選取父Facet。 您可以指定多個逗號分隔的父項。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>黏著深度 </p> </td> 
      <td colname="col2"> <p>只有在從<span class="uicontrol">行為</span>下拉式清單中選取「嚴格<span class="uicontrol"></span>」時，此選項才可用。 </p> <p>設定在向下鑽取期間要保持開啟的選項數。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>長度閾值 </p> </td> 
      <td colname="col2"> <p>設定在項目數中定義的小平面的垂直長度(1-9999)。 </p> <p>如果您的簡報範本已正確設定，您可以使用此設定來提供「顯示更多……」 連結，或決定何時將Facet拖曳至可捲動div，依此類推。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>截斷長度閾值 </p> </td> 
      <td colname="col2"> <p>在指定臨界值後截斷Facet中的項目數。 </p> <p>有些實作有Facet，其中包含數千個項目。 傳送所有資料在網路上可能非常昂貴。 您可使用此設定將Facet修剪至可管理的層級。 排序後，Facet會被截斷。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最大值寬度 </p> </td> 
      <td colname="col2"> <p>指定Facet值字串長度的限制(1-999)。 </p> <p>當您想要將Facet置於固定寬度的版面並避免字串纏繞時，這個選項很實用。 根據預設，字串會設為比臨界值短3個字元，以便新增省略號。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>值延伸功能 </p> </td> 
      <td colname="col2"> <p>指定您要用來指示Facet值被截斷的字串。 預設情況下，字串"。.." 的下界。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>分隔字元 </p> </td> 
      <td colname="col2"> <p>指定分隔字元，用於套用至Facet的任何分隔值清單。 </p> <p>使用的分隔字元與在Facet所依據的中繼資料中定義的分隔字元相同。 預設分隔字元是逗號。 不過，您可以使用任何XML相容的值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>排序 </p> </td> 
      <td colname="col2"> <p>指定您要如何在網站上排序刻面。 您可依下列方式來排序Facet。 視需要，最多可以合併5種排序方式。 </p> 
      <ul id="ul_12987F4DC7B34C63ABC906B59688A174"> 
      <li id="li_3206C96013DF431D90119F594D93D85D"> <span class="uicontrol"> alpha  </span> <p>依字母順序(0-9, A-Z)排序值，包括標點符號字元。 </p> </li> 
      <li id="li_304E4A518FBE48D18D9E9EA7339A3481"> <span class="uicontrol"> alpha（僅限英數字元）  </span> <p>依字母順序(0-9, A-Z)排序值，忽略標點符號字元。 </p> </li> 
      <li id="li_CADB888CC514455F9CA379C8EEE490AA"> <span class="uicontrol"> alpha（不區分大小寫）  </span> <p>按字母順序(0-9, A-Z)對值進行排序，忽略字母字元的大小寫，並包括標點符號字元。 </p> </li> 
      <li id="li_F61122E79AB5413792DA31F8AB1414BD"> <span class="uicontrol"> alpha（不區分大小寫，僅限英數字元）  </span> <p>按字母順序(0-9, A-Z)對值進行排序，忽略字母字元的大小寫，忽略標點符號字元。 </p> </li> 
      <li id="li_F50CC298ABF046D0A39D5AE5B1261823"> <span class="uicontrol"> 計數  </span> <p>依與每個Facet值相符的結果數目排序，從最大到最小。 </p> </li> 
      <li id="li_32B6AF39E9534762B39B15181DC5AD01"> <span class="uicontrol"> 數值  </span> <p>以數字方式對值排序。 在排序數字時，此選項優於Alpha排序，因為如果您使用Alpha排序，2之前會顯示10。 </p> </li> 
      <li id="li_CF8E76A7B1184E0C8DCC11B53E31A1DC"> <span class="uicontrol"> split </span> <p>依計數臨界值，將清單分為兩個不同的清單。 高於臨界值的Facet值會移至頂端。 計數低於臨界值的Facet值會移至底部。 當您想要強制特定範圍的值一律位於頂端時，需要分割臨界值。 </p> </li> 
      <li id="li_4AB8276577384B1099CBA895898205AD"> <span class="uicontrol"> break  </span> <p>強制將某些值置於清單的頂端或底部。 例如，您可能總是希望詞語"Other"出現在清單的底部。 當您使用分隔排序來識別應位於排序頂端或底部的明確值時，需要頂部值或底部值。 </p> </li> 
      <li id="li_227E96CFED2044FCA2F10B6913B03CFB"> <span class="uicontrol"> 訂購  </span> <p>Facet值應一律以固定順序（在<span class="uicontrol">順序</span>選項中定義的分隔字元分隔值清單，如下所述）。 </p> </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Facet的別名 </p> </td> 
      <td colname="col2"> <p>若要支援您在野外可能擁有的現有搜尋URL，您可以使用Facet別名，將舊有參數名稱對應至已修改的Facet，或僅建立具有不同名稱的Facet。 別名僅套用至傳入的請求，不用來建立Facet連結。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Facet邊欄名稱 </p> </td> 
      <td colname="col2"> <p>如果您決定依字母順序、依計數或依自訂方法排序Facet邊欄的名稱。 </p> <p>請參閱<a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local">關於 Facet 軌</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>訂購 </p> </td> 
      <td colname="col2"> <p>只有在從<span class="uicontrol">排序</span>下拉清單中選擇了<span class="uicontrol">排序</span>時，此選項才可用。 </p> <p>可讓您定義分隔值清單，以指定使用順序。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>附加額外內容 </p> </td> 
      <td colname="col2"> <p>只有在從<span class="uicontrol">排序</span>下拉清單中選擇了<span class="uicontrol">排序</span>時，此選項才可用。 </p> <p>如果值不在有序清單中，則值會附加到結尾。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>《鬼魂秀》 </p> </td> 
      <td colname="col2"> <p>只有在從<span class="uicontrol">排序</span>下拉清單中選擇了<span class="uicontrol">排序</span>時，此選項才可用。 </p> <p>如果排序清單所指定的值遺失，此選項會將Facet中每個遺失的項目標示為「Ghost」，讓項目顯示不同。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>巢狀Facet </p> </td> 
      <td colname="col2"> <p>巢狀Facet會顯示其類別及其子系的類別。 它只能顯示兩個類別的深度，但可以位於向下鑽取的任意位置。 </p> <p>此Facet的資料必須遵循一項慣例，才能說明兩個類別層級。 例如，Facet值可以是'shoes:boots'，其中父類別為'shoes'，子類別為'boots'。 ':'是用作分隔字元。 </p> <p>如需變更分隔字元的詳細資訊，請參閱下方的巢狀分隔字元。 </p> <p>若要以此格式產生資料，您可以使用篩選指令碼來結合兩個現有類別。 您可以將「一般」、「類別」和「嚴格」行為與巢狀Facet結合。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>巢狀父代名稱 </p> </td> 
      <td colname="col2"> <p>此下拉式清單僅在您選取「<span class="uicontrol">巢狀Facet </span>」時可用。 </p> <p>可讓您選擇代表父類別的欄位。 此欄位在搜尋期間用於匹配父類別。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>巢狀子代名稱 </p> </td> 
      <td colname="col2"> <p>此下拉式清單僅在您選取「<span class="uicontrol">巢狀Facet </span>」時可用。 </p> <p>可讓您選擇代表子類別的欄位。 此欄位在搜尋期間用於匹配子類別。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>巢狀Facet分隔字元 </p> </td> 
      <td colname="col2"> <p>只有在您選擇了<span class="uicontrol">巢狀Facet </span>時，此選項才可用。 </p> <p>在此處輸入的字元用於從其資料中分析父類別和子類別。 </p> <p>例如，如果':'用作分隔字元，而父代是'shoes'，而子代是'boots'，則會預期資料格式會是'shoes:boots'。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>分割閾值 </p> </td> 
      <td colname="col2"> <p>只有在從<span class="uicontrol">排序</span>下拉清單中選擇了<span class="uicontrol">拆分</span>時，此選項才可用。 </p> <p>使用「分割」排序時，分割臨界值會定義將Facet分割為兩個單獨清單的計數。 計數大於或等於閾值的值保留在頂部，而低於閾值的值移到底部。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最高值 </p> </td> 
      <td colname="col2"> <p>只有在從<span class="uicontrol">排序</span>下拉清單中選擇<span class="uicontrol">分隔</span>時，此選項才可用。 </p> <p>使用分隔排序時，此值的分隔清單一律會放在清單的頂端。 允許使用規則運算式，但它們應使用大括弧或大括弧，例如：{^新增。*?},{^非常新。*} </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最低值 </p> </td> 
      <td colname="col2"> <p>只有在從<span class="uicontrol">排序</span>下拉清單中選擇<span class="uicontrol">分隔</span>時，此選項才可用。 </p> <p>使用分隔排序時，此值的分隔清單一律會放在清單底部。 允許使用規則運算式，但它們應使用大括弧或大括弧，如下列範例所示：{^舊。*?},{^非常舊。*} </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 按一下 **[!UICONTROL Add]**.
1. （可選）在[!DNL Facets]頁面上，執行下列其中一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 新增巢狀Facet {#task_A132FA7EB7494A6B88E443F2C3FABBBA}

您可以新增巢狀Facet來顯示多個類別層級。

<!-- 

t_adding_a_nested_facet.xml

 -->

建立巢狀Facet時，請記住下列事項：

* 每個巢狀Facet都需要一個使用者定義的中繼標籤欄位。
* 巢狀Facet由父Facet和子Facet兩個其它Facet組成。 它們可以是單值刻面或多值刻面。 不允許混合單值刻面和多值刻面。
* 您需要確定此Facet是否將用於搜尋欄位表格中。 欄位表格需要巢狀Facet本身及其構圖Facet。
* 考慮使用JSON來實作巢狀刻面；這更簡單。

* [任務1 —— 添加meta標籤](../c-about-design-menu/c-about-facets.md#task_6944558325204E749C725DCFEF17EF3D)
* [任務2 —— 添加過濾指令碼以生成預格式化資料](../c-about-design-menu/c-about-facets.md#task_2DFED8BCB87B4067A6CE280945D7CAF4)
* [任務3 —— 添加新Facet](../c-about-design-menu/c-about-facets.md#task_3C11A4159FC44B9494D48594941AF8CF)
* [任務4 —— 編輯引導搜索](../c-about-design-menu/c-about-facets.md#task_E50EFD7BBD0F45729C15759EA4F548D8)
* [任務5 —— 建立傳輸模板](../c-about-design-menu/c-about-facets.md#task_C1FEDEF11D2549DEB1A9C09BFBA64381)
* [任務6 —— 建立演示模板](../c-about-design-menu/c-about-facets.md#task_4B2ABB37B9CD4F3F8AF8E6874227A995)
* [任務7 —— 編輯Breadcrumb](../c-about-design-menu/c-about-facets.md#task_5E22409528EC4DA284821F82FDCE3438)

>[!NOTE]
>
>本主題將巢狀Facet引用為Facet n1。

## 任務1 —— 添加meta標籤{#task_6944558325204E749C725DCFEF17EF3D}

新增中繼標籤欄位，專用於為巢狀Facet保留日期。 它可以是多值欄位或單一值欄位。

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**」。
1. 在[!DNL Definitions]頁面上，按一下&#x200B;**[!UICONTROL Add New Field]**。
1. 在[!DNL Add Field]頁面上，設定您想要的選項。

   請參閱[新增中繼標籤欄位](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。
1. 按一下 **[!UICONTROL Add]**.
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參閱[設定分段網站的遞增索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

   其餘任務將此meta標籤欄位稱為&#x200B;**n1**。

## 任務2 —— 添加過濾指令碼以生成預格式化資料{#task_2DFED8BCB87B4067A6CE280945D7CAF4}

1. 新增篩選指令碼，將原始Facet組合為下列格式：`<parent_value><nested_delimiter><child_value>`。

   請參閱[新增篩選指令碼](../c-about-settings-menu/c-about-filtering-menu.md#task_0AB84FD1133F47F9AA069A79BEA13A22)。

   以下是使用上述格式的meta標籤欄位n1的值範例

   `Womens:Handbags`

   `Womens:Dresses`

   `Mens:Accessories`

   `Mens:Footwear`
1. 建立或編輯篩選指令碼後，請測試該指令碼。 如果看起來正確，請視需要重新索引您的帳戶。 您可以使用[!DNL Index Overview]檢查索引。

   下列範例假設您有一些標準諮詢程式庫隨附於篩選指令碼初始化。 請記住，每個帳戶都不同，因此您的篩選指令碼應反映您自己帳戶的必要需求。

   **多值篩選指令碼範例**

   ```
   my $doc; 
   { 
   # Slurp all the data into $doc 
   local $/; 
   undef $/; 
   $doc = <>; 
   } 
    # Create n1 field 
    if ( $doc =~ m{<meta\s+name="t1"\s+content="([^\"]*)"}is ) 
    { 
     my @t1arr = split(/\|/, $1); 
     if (scalar @t1arr > 0) 
     { 
      if ( $doc =~ m{<meta\s+name="t2"\s+content="([^\"]*)"}is ) 
      { 
       my @t2arr = split(/\|/, $1); 
   
       if ( scalar @t2arr > 0 ) 
       { 
        my $max = ((scalar @t1arr) < (scalar @t2arr)) ? (scalar @t1arr) : (scalar @t2arr); 
        for (my $i = 0; $i < $max; $i++) 
        { 
         $t1arr[$i] .= ":" . $t2arr[$i]; 
        } 
       } 
      } 
      my $output = join( '|', @t1arr ); 
      $doc =~ s{</head>}{<meta name="n1" content="$output" />\b</head>}is; 
     } 
    } 
    # END: n1 field
   ```

   **單一值篩選指令碼範例**

   ```
   # This is a complete example. 
   # This script is designed for index connector where each record 
   # in the XML file is converted into a fake HTML page filled with 
   # meta data tags.  
   my $doc; 
   { 
   # Slurp all the data 
   local $/; 
   undef $/; 
   $doc = <>; 
   } 
   # All legitimate index connector data has key in its URL. 
   # Process the page if and only if it is coming from index connector and 
   # it is not the first entry point page.  Entry point pages don't have key 
   # in the URL. 
   if ($main::search_url =~ /\?key=/) { 
    my $meta = {}; 
    # Mine and scrape the meta fields from the page 
    my @lines = split(/\n/,$doc); 
    foreach my $line (@lines) 
    { 
     if ($line =~ m{<meta name="(.*?)" content="(.*?)" />}) 
     { 
      $meta->{lc($1)} = $2; 
     } 
    } 
    # Combined t1,t2 and t2,t3, and t3,t4 together. 
    # Assign them respectively to n1, n2, and n3. 
    my ($t1, $t2, $t3, $t4); 
    my %meta2; 
    $t1 = $meta->{'t1'}; 
    $t2 = $meta->{'t2'}; 
    $t3 = $meta->{'t3'}; 
    $t4 = $meta->{'t4'}; 
    if (defined $t1 && $t1) { 
     $meta2{'n1'} = $t1; 
     if (defined $t2 && $t2) { 
      $meta2{'n1'} .= ":" . $t2; 
      $meta2{'n2'} = $t2; 
      if (defined $t3 && $t3) { 
      $meta2{'n2'} .= ":" . $t3; 
       $meta2{'n3'} = $t3; 
       if (defined $t4 && $t4) { 
        $meta2{'n3'} .= ":" . $t4; 
       } 
      } 
     } 
    } 
    foreach my $stuff ( keys %meta2 ) 
    { 
     my $v = $meta2{$stuff}; 
     $doc =~ s{</head>}{<meta name="$stuff" content="$v" />\n</head>}; 
    } 
   } 
   
   # Do some ranking stuff here 
   ws_insert_static_rank_meta_tag(\$doc, "RANK"); 
   
   # Prints the entire page back out. 
   print $doc;
   ```

## 任務3 —— 添加新的Facet {#task_3C11A4159FC44B9494D48594941AF8CF}

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Facets]**」。
1. 在[!DNL Facets]頁面上，按一下&#x200B;**[!UICONTROL Add New Facet]**。
1. 在[!DNL Add Facet]頁面上，設定下列選項：

   * 在[!DNL Facet Name]下拉式清單中，選取您在Task 1中定義的meta標籤欄位。 如果您使用搜尋欄位表格，請在下拉式清單中選取&#x200B;**[!UICONTROL custom]**，然後輸入Facet的自訂名稱。

   * 勾選&#x200B;**[!UICONTROL Nested Facet]**&#x200B;以「開啟」巢狀刻面。
   * 在[!DNL Nested Parent Name]和[!DNL Nested Child Name]下拉式清單中，選擇您可以使用的meta標籤欄位。 如果您使用搜尋欄位表格，請選取&#x200B;**[!UICONTROL custom]**&#x200B;並輸入Facet的自訂名稱。

   * 在[!DNL Nested Facet Delimiter]欄位中，指定您要使用的分隔字元，例如&quot;:&quot;（冒號）。 請勿將此與多值分隔字元混淆。 兩個分隔字元應不同。
   * 如果您設定Facet的行為&#x200B;**[!UICONTROL Category]**，您可以指定Facet的父項（請勿混淆父項與巢狀Facet父項）。 一般而言，切勿使用其他巢狀Facet的名稱做為「類別」父項。 請改用組成巢狀Facet的個別Facet。
   * 設定您想要的任何其他Facet選項。

   請參閱[新增Facet](../c-about-design-menu/c-about-facets.md#task_FC07BFFA62CA4B718D6CBF4F2855C89B)。
1. 按一下 **[!UICONTROL Add]**.

## 任務4 —— 編輯引導搜索{#task_E50EFD7BBD0F45729C15759EA4F548D8}

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Searches]**」。
1. 在[!DNL Searches]頁面上，按一下您要更新之搜尋類型名稱上的&#x200B;**[!UICONTROL Edit]**。
1. `sp_field_table`需要欄位n1、t1和t2。

   如果使用欄位表，則應編輯`sp_field_table`參數。 或者，您也可以使用查詢清除規則或搜尋前規則，在其他地方完成此作業。

   請參閱[添加查詢清除規則](../c-about-rules-menu/c-about-query-cleaning-rules.md#task_47F43988D3D9485F8AE1DFDA7E00BF54)。

   請參閱[新增搜尋前規則](../c-about-rules-menu/c-about-pre-search-rules.md#task_182B95918462490D8BDA7F16A81CAC11)。
1. 按一下 **[!UICONTROL Save Changes]**.

## 任務5 —— 建立傳輸模板{#task_C1FEDEF11D2549DEB1A9C09BFBA64381}

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Templates]**」。
1. 在[!DNL Templates]頁面上，按一下&#x200B;**[!UICONTROL Add New Template]**。
1. 在[!DNL Add Template]對話框中，指定傳輸模板檔案的名稱。
1. 在[!DNL New Template Type]下拉式清單中，選取&#x200B;**[!UICONTROL Transport]**。
1. 按一下 **[!UICONTROL Add]**.
1. 在[!DNL Templates]頁面上，按一下剛添加的傳輸模板檔案名。
1. 在傳輸範本的[!DNL Template Editor]頁面上，包含來自欄位n1的資料。 請參閱下列範例。

   **傳回巢狀Facet資料的XML范** 例XML範例需要指定使用哪個字元作為Facet值之間的分隔字元。在本例中，它是垂直號(|)。

   ```
   <facet name="n1"> 
     <values delimiter="|"><search-field-value-list name="n1" quotes="no" separator="|" sortby="values" data="values" /></values> 
     <counts><search-field-value-list name="n1" quotes="no" sortby="values" data="results" /></counts> 
   </facet>
   ```

   **傳回巢狀Facet資料的JSON範例**

   ```
   { 
      "name" : "n1", 
      "values" : [ <search-field-value-list name="n1" quotes="yes" sortby="values" data="values" encoding="json"/>], 
      "counts" : [<search-field-value-list name="n1" quotes="no" sortby="values" data="results" />] 
   },
   ```

## 任務6 —— 建立演示模板{#task_4B2ABB37B9CD4F3F8AF8E6874227A995}

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Templates]**」。
1. 在[!DNL Templates]頁面上，按一下&#x200B;**[!UICONTROL Add New Template]**。
1. 在[!DNL Add Template]對話方塊中，指定簡報範本檔案的名稱。
1. 在[!DNL New Template Type]下拉式清單中，選取&#x200B;**[!UICONTROL Presentation]**。
1. 按一下 **[!UICONTROL Add]**.
1. 在[!DNL Templates]頁面上，按一下您剛新增的簡報範本檔案名稱。
1. 在簡報範本的[!DNL Template Editor]頁面上，新增與預期輸出整合的HTML標籤。

   您可以使用下列標籤來顯示子標籤：

* **如果子項存在標籤** `<guided-if-facet-value-has-children><guided-else-facet-value-selected></guided-if-facet-value-has-children>`

* **子值標籤** `<guided-facet-value-children></guided-facet-value-children>`

   「子值」標籤的行為不像一般的guided-facet-value標籤。 wrapper標籤會強制所有包含`<guided-facet-value>`標籤重複執行子Facet值，而非父Facet值。 同樣地，其他引導Facet標籤（例如還原標籤）也會遵循相同的步驟。 它們最適合用於`<guided-if-facet-value-has-children>`標籤。

   以下是具有HTML標籤的簡報範本範例。

   ```
   <guided-facet gsname="n1"> 
   <guided-if-facet-selected> 
    <guided-facet-values> 
    <guided-if-facet-value-selected> 
     <li><span class="selected"><guided-facet-value /></span><guided-facet-value-undo-link gsname="n1">X</guided-facet-value-undo-link></li> 
     <guided-if-facet-value-has-children> 
      <ul> 
      <guided-facet-value-children> 
      <guided-if-facet-value-selected> 
       <li><span class="selected"><guided-facet-value /></span><guided-facet-value-undo-link gsname="n1">X</guided-facet-value-undo-link></li> 
      <guided-else-facet-value-selected> 
       <li><guided-facet-link title='<guided-facet-value />'><guided-facet-value /> (<guided-facet-count />)</guided-facet-link> </li> 
      </guided-if-facet-value-selected> 
      </guided-facet-value-children> 
      </ul> 
     </guided-if-facet-value-has-children> 
    <guided-else-facet-value-selected> 
     <li><guided-facet-link title='<guided-facet-value />'><guided-facet-value /> (<guided-facet-count />)</guided-facet-link> </li> 
     <guided-if-facet-value-has-children> 
      <ul> 
      <guided-facet-value-children> 
       <li><guided-facet-link title='<guided-facet-value />'><guided-facet-value /> (<guided-facet-count />)</guided-facet-link> </li> 
      </guided-facet-value-children> 
      </ul> 
     </guided-if-facet-value-has-children> 
    </guided-if-facet-value-selected> 
    </guided-facet-values> 
   <guided-else-facet-selected>  
    <guided-facet-values> 
    <guided-if-facet-value-selected> 
     <li><span class="selected"><guided-facet-value /></span><guided-facet-value-undo-link gsname="n1">X</guided-facet-value-undo-link></li> 
     <guided-if-facet-value-has-children> 
      <ul> 
      <guided-facet-value-children> 
       <li><guided-facet-link title='<guided-facet-value />'><guided-facet-value /> (<guided-facet-count />)</guided-facet-link> </li> 
      </guided-facet-value-children> 
      </ul> 
     </guided-if-facet-value-has-children> 
    <guided-else-facet-value-selected> 
     <li><guided-facet-link title='<guided-facet-value />'><guided-facet-value /> (<guided-facet-count />)</guided-facet-link> </li> 
     <guided-if-facet-value-has-children> 
      <ul> 
      <guided-facet-value-children> 
       <li><guided-facet-link title='<guided-facet-value />'><guided-facet-value /> (<guided-facet-count />)</guided-facet-link> </li> 
      </guided-facet-value-children> 
      </ul> 
     </guided-if-facet-value-has-children> 
    </guided-if-facet-value-selected> 
    </guided-facet-values> 
   </guided-if-facet-selected> 
   </guided-facet>
   ```

## 任務7 —— 編輯Breadcrumb {#task_5E22409528EC4DA284821F82FDCE3438}

如果您在搜尋中使用網站導覽路徑標示，您必須將行為設定為&#x200B;**前往**。

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**」。
1. 在[!DNL Breadcrumbs]頁面上，按一下您要更新其行為的階層連結名稱上的&#x200B;**[!UICONTROL Edit]**。
1. 在[!DNL Edit Breadcrumb]頁面的[!DNL Behavior]下拉式清單中，選擇&#x200B;**前往**。
1. 按一下 **[!UICONTROL Save Changes]**.

## 編輯Facet {#task_457EDC49983F4F7781873703AF574DA5}

您可以編輯已新增之任何Facet的設定。

<!-- 

t_editing_a_facet.xml

 -->

>[!NOTE]
>
>請確定您參考簡報範本中的Facet，以便在網站上顯示。

**若要編輯Facet**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Facets.]**」
1. 在[!DNL Facets]頁面上，按一下Facet名稱最右側的&#x200B;**[!UICONTROL Edit]**。
1. 在[!DNL Edit Facet]頁面上，設定您想要的選項。

   請參閱[新增facet](../c-about-design-menu/c-about-facets.md#task_FC07BFFA62CA4B718D6CBF4F2855C89B)下的選項表。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （選用）在[!DNL Facets]頁面上，

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 刪除Facet {#task_17756FD66BCC49629325B2217F821BDD}

您可以刪除已新增的任何Facet。

<!-- 

t_deleting_a_facet.xml

 -->

**刪除Facet**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Facets]**」。
1. 在[!DNL Facets]頁面上，按一下Facet名稱最右側的&#x200B;**[!UICONTROL Delete]**。
1. 在[!DNL Confirmation]對話框中，按一下&#x200B;**[!UICONTROL OK]**。
1. 進行以下一項操作: 

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

