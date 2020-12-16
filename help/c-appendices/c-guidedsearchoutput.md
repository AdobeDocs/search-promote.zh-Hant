---
description: 您可以自訂任何文字格式的輸出，包括XML或JSON。
seo-description: 您可以自訂任何文字格式的輸出，包括XML或JSON。
seo-title: 引導式搜尋輸出
solution: Target
title: 引導式搜尋輸出
topic: Appendices,Site search and merchandising
uuid: 234fd563-f249-42b0-88ca-c89b44f8df77
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a
workflow-type: tm+mt
source-wordcount: '6298'
ht-degree: 2%

---


# 引導式搜尋輸出{#guided-search-output}

您可以自訂任何文字格式的輸出，包括XML或JSON。

## 使用引導搜索輸出{#concept_2A1BA3AD413848A1AC2A3ABC4FFE481F}

可自訂輸出格式，以支援設計程式中所做的Faceting、排序和其他實作特定決策。 如有需要，您可以自行調整格式，以簡化客戶前端的開發。

整個輸出包含在`<result>`標籤中，而大部分的動態資料都包含在`<![CDATA[ ]]>`標籤中。 此類組織可讓結果包含HTML和其他非XML實體。

當提供其他頁面的連結時，會以相對URL的形式呈現。 此結果也包含傳遞以產生所需結果的查詢字串參數。

## 瞭解引導式搜尋實作{#section_95483980930C4325BAB50A40BD47245A}

當您開始進行引導式搜尋實作時，請記住[!DNL Adobe Search&Promote]負責業務層。 也就是說，在任何特定時間，客戶都可看到哪些結果和刻面，這個邏輯是圍繞著這些邏輯的。

當您實作分析結果並以HTML格式顯示結果的Web應用程式前端時，請將功能限制為僅顯示。 換言之，您用來建立表現層的任何伺服器端邏輯，除非有必要，否則不會決定要向客戶展示什麼。 如果前端指令碼正在變更搜尋結果，業務規則將無法如預期般運作。

[!DNL Adobe Search&Promote] 透過URL參數，維護所選搜尋調整選項的使用者狀態。所有`<link>`節點都包含客戶選擇的相關參數。 這些參數可包括階層連結、分頁、排序和Facet選擇。 如果適用，會傳回`<undolink>`節點，讓客戶「退出」選擇。 刻面和階層連結提供這些類型的連結。

## 使用搜索伺服器{#section_8DBEACDECD714E59BDED6315E6041B8D}

您可使用類似REST的API來執行搜尋並接收結果。 最常用於結果的格式為XML或JSON。

基本URI與特定帳戶和分段或即時環境相關聯。 您可以向帳戶管理員請求基本URI的多個別名。 例如，一家名為Megacorp的虛構公司有下列兩個與其帳戶關聯的基本URL:

* `https://search.megacorp.com `
* `https://stage.megacorp.com`

前者URI會針對其活動索引執行搜尋，後者則針對其分段索引執行搜尋。

搜索請求由基本URI和一組CGI參數或鍵值對組成，這些參數或鍵值對指示對與基本URI關聯的帳戶進行所需搜索。

支援三種格式的CGI參數。 預設情況下，您的帳戶配置為使用分號(`;`)分隔CGI參數，如下例所示：

* `https://search.megacorp.com?q=shoes ;page=2`

如果您願意，您可以讓帳戶管理員設定您的帳戶，使用&amp;符號(`&`)來分隔CGI參數，如下列範例所示：

* `https://search.megacorp.com?q=shoes &page=2`

另外也支援另一種稱為SEO格式的格式，其中使用正斜線(`/`)來取代分隔符號，並使用等號來產生&quot;clean&quot;連結，如下列範例所示：

* `https://search.megacorp.com/q/shoes/page/2`

只要使用SEO格式傳送請求，所有輸出連結都會以相同格式傳回。

## 搜索查詢參數{#section_7ADA5E130E3040C9BE85D0D68EDD3223}

下表說明您可使用的標準「現成」搜尋查詢參數。 處理規則和業務規則可以根據使用者定義的查詢參數建立，以實作與您公司相關的自訂商業邏輯。 您可與諮詢團隊合作，以取得這些參數的相關檔案。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>搜尋查詢參數 </p> </th> 
   <th colname="col2" class="entry"> <p>範例 </p> </th> 
   <th colname="col3" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> q </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> q=字串  </span> </p> </td> 
   <td colname="col3"> <p> 指定搜索的查詢字串。 此參數映射至<span class="codeph"> sp_q </span>後端搜尋參數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> q# </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> q#=字串  </span> </p> </td> 
   <td colname="col3"> <p>編號<span class="codeph"> q </span>和<span class="codeph"> x </span>參數可完成臉部設定，或在指定欄位內搜尋。 </p> <p><span class="codeph"> q </span>參數將您在Facet中搜索的術語定義為相應編號的<span class="codeph"> x </span>參數。 例如，如果您有兩個刻面，其名稱為size和color，則可能有類似下列的項目： </p> <p> <span class="codeph"> q1=small;x1=size;q2=red;x2=color  </span> </p> <p>此參數會映射至<span class="codeph"> sp_q_exact_# </span>後端搜尋參數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> x# </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> x#=字串  </span> </p> </td> 
   <td colname="col3"> <p> 編號<span class="codeph"> q </span>和<span class="codeph"> x </span>參數可完成臉部設定，或在指定欄位內搜尋。 </p> <p><span class="codeph"> q </span>參數將您在Facet中搜索的術語定義為相應編號的<span class="codeph"> x </span>參數。 例如，如果您有兩個刻面，其名稱為size和color，則可能有類似下列的項目： </p> <p> <span class="codeph"> q1=small;x1=size;q2=red;x2=color  </span> </p> <p>此參數映射至<span class="codeph"> sp_x_# </span>後端搜尋參數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> 集合 </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> collection=字串  </span> </p> </td> 
   <td colname="col3"> <p> 指定要用於搜尋的系列。 此參數映射至<span class="codeph"> sp_k </span>後端搜尋參數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> 計數  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> count=數字  </span> </p> </td> 
   <td colname="col3"> <p> 指定顯示的結果總計。 預設定義於<span class="uicontrol">設定</span> &gt; <span class="uicontrol">搜索</span> &gt; <span class="uicontrol">搜索</span>。 此參數映射至<span class="codeph"> sp_c </span>後端搜尋參數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> page </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> 頁=數字  </span> </p> </td> 
   <td colname="col3"> <p> 指定返回的結果頁。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> 排名  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> 排名=欄位  </span> </p> </td> 
   <td colname="col3"> <p> 指定用於靜態排名的排名欄位。 欄位必須是關聯性大於0的「排名」類型欄位。 此參數映射至<span class="codeph"> sp_sr </span>後端參數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> gs_store  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> gs_store=字串  </span> </p> </td> 
   <td colname="col3"> <p> 指定要搜索的儲存。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> 排序  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> 排序=數字  </span> </p> </td> 
   <td colname="col3"> <p> 指定排序順序。 「0」是預設值，並依關聯分數排序；「1」按日期排序；"-1"不排序。 </p> <p>用戶可以為<span class="codeph"> sp_s </span>參數的值指定欄位名。 例如，<span class="codeph"> sp_s=title </span>會根據標題欄位中包含的值對結果排序。 當欄位名稱用於<span class="codeph"> sp_s </span>參數的值時，結果將按該欄位排序，然後按相關性進行子排序。 </p> <p>若要啟用此功能，請執行下列動作： </p> 
    <ol id="ol_3894F81EA7BF4827A84DE8662111ABEF"> 
     <li id="li_C040C0B88F174A4885E1A8E721FD032A">在產品功能表上，按一下「設定<span class="uicontrol"> </span> &gt; <span class="uicontrol">中繼資料</span> &gt; <span class="uicontrol">定義</span>」。 </li> 
     <li id="li_2E83C3A46D1B4BF991EABAD9D3E52B7D">在<span class="wintitle"> 「分段定義</span>」頁面上，執行下列任一操作： 
      <ul id="ul_8018FEE10E0A4C96A74F84A897080580"> 
       <li id="li_E9A7CE43E2734F4D9522A1283CA111FB">按一下「<span class="uicontrol">添加新欄位</span>」。 </li> 
       <li id="li_9D2434A321924FBD874569CA9AD2EEF7">按一下<span class="uicontrol">編輯</span>以查看特定欄位名。 </li> 
      </ul> </li> 
     <li id="li_90D5E3F4AC0A4A6189934A5589F69903">在<span class="wintitle">排序</span>下拉式清單中，按一下「遞增<span class="uicontrol">」或「遞減</span>」。<span class="uicontrol"></span> </span><p>此參數映射至<span class="codeph"> sp_s </span>後端搜尋參數。 </p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

## 與系統{#section_91261B19A44A4E579B3FC9FAB9AD3665}整合

以下是與系統整合的建議。

* 與搜尋伺服器通訊。

   您可以使用http GET請求與[!DNL Adobe Search&Promote]網頁伺服器通訊。 您的伺服器會產生這些要求，或在用戶端執行Ajax要求。
* 儲存搜尋歷史記錄。

[!DNL Adobe Search&Promote] 是無狀態，其中整個狀態在http請求中傳遞。
* 剖析傳回的結果。

   建議您使用以SAX為基礎的XML剖析器來剖析XML回應。 如果您要產生Ajax請求，請設定[!DNL Adobe Search&Promote]以傳回這些請求的JSON回應，讓解析回應變得更輕鬆。

## 引導式搜尋JSON輸出{#reference_EB8182A564DE4374BB84158F2AABEF74}

說明標準JSON回應輸出的表格。

另請參閱[引導式搜尋JSON輸出](../c-appendices/c-guidedsearchoutput.md#reference_EB8182A564DE4374BB84158F2AABEF74)。

您可以檢閱JSON回應，以取得下列項目：

* [橫幅廣告](../c-appendices/c-guidedsearchoutput.md#section_88519CAAD25F4BD49D5E517077745B0E)
* [階層連結](../c-appendices/c-guidedsearchoutput.md#section_A7DB0F1DA9ED4CBCAE18395122F3E01E)
* [刻面](../c-appendices/c-guidedsearchoutput.md#section_65932C95931743A1BFAF1DF16D7E6D92)
* [頁首和查詢](../c-appendices/c-guidedsearchoutput.md#section_1D57062259CA46E0B4F598FA4EB37065)
* [編頁](../c-appendices/c-guidedsearchoutput.md#section_504E7AB570BD49AF9839530DC438EE96)
* [最近搜尋](../c-appendices/c-guidedsearchoutput.md#section_525816A0355C48F8970D89B8FC3F1FFF)
* [結果](../c-appendices/c-guidedsearchoutput.md#section_41AC56BB0A084BF59379B06C8BEF2157)
* [搜尋表單](../c-appendices/c-guidedsearchoutput.md#section_434DA13EA295474C99FFE9F14801CD0E)
* [排序](../c-appendices/c-guidedsearchoutput.md#section_558853CD376F4D71BACF211D53085D55)
* [建議](../c-appendices/c-guidedsearchoutput.md#section_6EC104E1DDD94AC799B65E6E61A2FB3C)
* [區域](../c-appendices/c-guidedsearchoutput.md#section_AE53A498B440465EAF2286F2AE87D548)

## 橫幅廣告 {#section_88519CAAD25F4BD49D5E517077745B0E}

範例:  

```xml
<banners> 
 <banner> 
  <area><![CDATA[top-left]]></area> 
  <content><![CDATA[<img src="https://www.megacorp.com/discount.gif"/>]]></content> 
 </banner> 
</banners>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>橫幅中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;banner&gt; </span> </p> </td> 
   <td colname="col2"> <p> 個別橫幅節點。 您可以有多個橫幅節點。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;area&gt; </span> </p> </td> 
   <td colname="col2"> <p> 顯示橫幅的網頁區域。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;content&gt; </span> </p> </td> 
   <td colname="col2"> <p> 橫幅區域的HTML內容。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 階層連結{#section_A7DB0F1DA9ED4CBCAE18395122F3E01E}

在下列範例中，每次客戶透過Facet進一步縮小範圍時，選取範圍就會新增至階層連結。 每個項目都表示為`<breadcrumb-item>`。

範例:  

```xml
 <breadcrumb> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year]]></link> 
   <value><![CDATA[new year]]></value> 
  </breadcrumb-item> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year;q1=Articles;x1=content-type]]></link> 
   <value><![CDATA[Articles]]></value> 
  </breadcrumb-item> 
 </breadcrumb> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>網站導覽路徑標示中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> 顯示所需檢視之搜尋結果的相對連結。 按一下網站導覽路徑標示連結，會將客戶帶往檢視，其中會移除所有後續的調整。 其他選項也可供使用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> 階層連結項目的客戶對應文字。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Facets {#section_65932C95931743A1BFAF1DF16D7E6D92}

刻面是細化選項，可讓客戶篩選結果。 Facet通常用於分類、價格範圍、顏色選擇和其他屬性調整。 索引中的中繼資料是推動Facet的因素。

當客戶在分類中向下移動時，通常會隱藏或顯示分類Facet。 最高級別的分類（類別）稱為第1層。 當客戶按一下第1層選項時，會出現第2層（子類別）調整選項，而第1層選項會消失。 當客戶按一下第2層選項時，會出現第3層（子子類別）調整選項，而第2層選項會消失。 如上所述，這些選項會隱藏並顯示——您的Web應用程式不會受到這些選項的影響。

每個Facet都包含在`<facet-item>`標籤中。 在下列範例中，它顯示一個Facet，可讓客戶依「holiday」調整搜尋結果。

範例:  

```xml
 <facets> 
  <facet-item> 
   <facet-title><![CDATA[Holidays]]></facet-title> 
   <facet-value> 
    <label><![CDATA[New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[11]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Christmas]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Christmas;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Chinese New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Chinese+New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Thanksgiving]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Thanksgiving;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[4th of July]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=4th+of+July;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Father&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Father's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Hanukkah]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Hanukkah;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Mother&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Mother's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Valentine&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Valentine's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
  </facet-item> 
  <facet-item> 
   <facet-title><![CDATA[Seasons]]></facet-title> 
   <facet-value> 
    <label><![CDATA[Winter]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Winter;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[20]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Summer]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Summer;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Autumn]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Autumn;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[4]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Spring]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Spring;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
  </facet-item> 
 </facets> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Facet中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> Facet的客戶對應標題。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> Facet選項的客戶對應標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> 與結果的相對連結，讓選項進一步調整。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;count&gt; </span> </p> </td> 
   <td colname="col2"> <p> 該精化結果集中的結果數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;undolink&gt; </span> </p> </td> 
   <td colname="col2"> <p> 選取Facet值時，節點會傳回「還原連結」，讓客戶退出結果。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 標題和查詢{#section_1D57062259CA46E0B4F598FA4EB37065}

範例:  

```xml
<result> 
 <query> 
  <user-query><![CDATA[new year]]></user-query> 
  <lower-results><![CDATA[1]]></lower-results> 
  <upper-results><![CDATA[16]]></upper-results> 
  <total-results><![CDATA[621]]></total-results> 
 </query> 
```

搭配使用這些標籤時，會顯示如下訊息：「在621年的1-16項中，顯示『新年』的結果。」

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>標題和查詢中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;user-query&gt; </span> </p> </td> 
   <td colname="col2"> <p> 隨請求提交的關鍵字查詢。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;lower-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> 此頁面上第一個結果的項目編號。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;upper-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> 此頁面上最後一個結果的項目編號。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> 符合使用者查詢的結果總數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;custom-field&gt; </span> </p> </td> 
   <td colname="col2"> <p> 全域套用至搜尋結果的可選欄位。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 編頁{#section_504E7AB570BD49AF9839530DC438EE96}

範例:  

```xml
<pagination> 
 <total-pages><39></total-pages> 
 <pages> 
   <page position="first"></page> 
   <page position="last">?i=1;page=39;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="previous"></page> 
   <page position="next">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="1" selected="true">?i=1;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="2">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="3">?i=1;page=3;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="4">?i=1;page=4;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="5">?i=1;page=5;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="6">?i=1;page=6;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="7">?i=1;page=7;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="8">?i=1;page=8;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="9">?i=1;page=9;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="10">?i=1;page=10;q=new+year;q1=Articles;x1=content-type]]></page> 
 </pages> 
</pagination> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>分頁中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-pages&gt; </span> </p> </td> 
   <td colname="col2"> <p> 結果的頁數總計，以結果數除以每頁結果數為基準。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="first"&gt; </span> </p> </td> 
   <td colname="col2"> <p> 包含結果集中第一頁的相對連結，除非客戶已檢視第1頁。 在這種情況下，它是空的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="last"&gt; </span> </p> </td> 
   <td colname="col2"> <p> 包含結果集中最後一頁的相對連結，除非客戶正在查看最後一頁。 在這種情況下，它是空的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="previous"&gt; </span> </p> </td> 
   <td colname="col2"> <p> 包含結果集上一頁的相對連結，除非客戶正在檢視第1頁；在這種情況下，它是空的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="next"&gt; </span> </p> </td> 
   <td colname="col2"> <p> 包含結果集中最後一頁的相對連結，除非客戶正在查看最後一頁。 在這種情況下，它是空的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="x"&gt;</span> </p> </td> 
   <td colname="col2"> <p> 包含特定頁碼的相對連結。 顯示十個連續的頁碼。 在第1頁，是第1-10頁。 在結果集結尾（在本例中為39）時，會是第30-39頁。 例如，在結果集的中心（第15頁），它應該是第11-20頁。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> selected="true"&gt;  </span> </p> </td> 
   <td colname="col2"> <p> 套用為屬性至目前選取的頁面。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最近搜索{#section_525816A0355C48F8970D89B8FC3F1FFF}

「最近搜尋」是以Cookie為基礎的功能，只有在您將Cookie資訊中繼至伺服器時才能運作。

範例:  

```xml
<recent-searches> 
 <recent-search> 
  <search-term><![CDATA[shoes]]></search-term> 
  <link><![CDATA[?q=shoes]]></link> 
 </recent-search> 
</recent-searches> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>最近搜尋中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;recent-search&gt; </span> </p> </td> 
   <td colname="col2"> <p> 個別的最近搜尋節點。 您可以有多個最近搜尋的節點。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-term&gt; </span> </p> </td> 
   <td colname="col2"> <p> 客戶先前搜尋的詞。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> 前一個搜尋的連結。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 結果 {#section_41AC56BB0A084BF59379B06C8BEF2157}

「結果」集是JSON回應的可自訂區域。 每個索引在中繼資料的欄位命名機制中都是唯一的。 每個結果都會傳回常見欄位，例如標題、說明和URL。 但是，為索引中的頁面定義的任何中繼資料都可以用於每個結果節點。 分類、價格、顏色和縮圖只是您可套用至結果的一些選項，以產生更吸引人的搜尋結果。

「結果」格式會根據您實作的特定中繼資料自訂。 結果中顯示的任何結果資料（包括縮圖影像URL）都包含在此處。

此外，您也可以在頁面中設定多個結果區域，例如「精選結果」，或個別「產品」和「內容」結果區域。 在這些情況下，HTML中會提供多個結果區域，但Facet僅與主要結果集關聯。

範例:  

```xml
 <results> 
  <result> 
    <index><![CDATA[1]]></index> 
    <result-title><![CDATA[New Year's Eve Slumber Party]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/new-years-eve-slumber-party-705199/]]></url> 
    <meta-description><![CDATA[Fun New Year's celebration ideas for your kids]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/new-years-eve-

slumber-party-parties-photo-80-FF1200SLEEPA18.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/new-years-eve- 
slumber-party-parties-photo-160-FF1200SLEEPA18.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Nancy Mades]]></byline> 
    <blurb><![CDATA[Fun New Year's celebration ideas for your kids]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[2]]></index> 
    <result-title><![CDATA[10 Holiday Traditions to Start This Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/10-holiday-traditions-to-start-this-year-704781/]]></url> 
    <meta-description><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/10-holiday- 
traditions-to-start-this-year-parties-photo-80-FF1107HOLIA01.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/10-holiday- 
traditions-to-start-this-year-parties-photo-160-FF1107HOLIA01.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Julie Taylor]]></byline> 
    <blurb><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[3]]></index> 
    <result-title><![CDATA[A Perfect New Year's Eve]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/a-perfect-new-years-eve-705258/]]></url> 
    <meta-description><![CDATA[You can turn New Year's into a celebration for the whole family.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Teri Keough]]></byline> 
    <blurb><![CDATA[You can turn New Year's into a celebration for the whole family.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[4]]></index> 
    <result-title><![CDATA[New Year's Fun and Games]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/new-years-fun-and-games-705220/]]></url> 
    <meta-description><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Charlotte Meryman]]></byline> 
    <blurb><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[5]]></index> 
    <result-title><![CDATA[11 Great Ways to Start the New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/11-great-ways-to-start-the-new-year-705552/]]></url> 
    <meta-description><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Emily Block]]></byline> 
    <blurb><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[6]]></index> 
    <result-title><![CDATA[Celebrating Chinese New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/celebrating-chinese-new-year-705260/]]></url> 
    <meta-description><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[7]]></index> 
    <result-title><![CDATA[New Year's Eve, Family Style]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/new-years-eve-family-style-701283/]]></url> 
    <meta-description><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[8]]></index> 
    <result-title><![CDATA[Chinese New Year Activities]]></result-title> 
    <url><![CDATA[https://mysite.com/crafts/chinese-new-year-activities-710345/]]></url> 
    <meta-description><![CDATA[Activities for celebrating Chinese New Year.]]></meta-description> 
    <category><![CDATA[crafts]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Activities for celebrating Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[9]]></index> 
    <result-title><![CDATA[More Organized in the New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/more-organized-in-the-new-year-701284/]]></url> 
    <meta-description><![CDATA[Tips for getting your household more organized--and getting the kids to help.]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Tips for getting your household more organized--and getting your kids to help out.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[10]]></index> 
    <result-title><![CDATA[Checklists: Year-End Safety Checklist]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/checklists-year-end-safety-checklist-701352/]]></url> 
    <meta-description><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></blurb> 
  </result>   
 </results> 
</customer-result> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>結果中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;index&gt; </span> </p> </td> 
   <td colname="col2"> <p> 此結果集中結果的序列號。 在此範例中，每頁顯示10個結果，在結果第2頁，第一個項目的索引為11。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> 此頁面的客戶對應標題。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;url&gt; </span> </p> </td> 
   <td colname="col2"> <p> 此頁面的URL。 它可用來建立超連結，讓客戶點選結果。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 搜尋表單{#section_434DA13EA295474C99FFE9F14801CD0E}

範例:  

```xml
<search-form> 
 <include-tnt-mbox>1 </included-tnt-mbox> 
 <autocomplete> 
  <css><![CDATA[<!--link rel="stylesheet" type="te 
        xt/css"href="//content.atomz.com/sp000000a8/publish/autoc 
        omplete_styles.css?sp_css_cache_ver=2" /-->]]> 
  </css> 
  <form-content><![CDATA[<div id="autocomplete"></div>]]> 
  </form-content> 
  <js><![CDATA[<script type="text/javascript" 
   src="//content.atomz.com/sp100491de/publish/autoc 
   omplete_data.js?sp_js_cache_ver=3"></script>]]> 
  </js> 
 </autcomplete> 
 <hidden-parameters> 
  <parameter> 
   <name><![CDATA[store]]></name> 
   <value><![CDATA[mens]]></value> 
  </parameter> 
 </hidden-parameters> 
</search-form>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>搜尋表單中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;include-tnt-mbox&gt; </span> </p> </td> 
   <td colname="col2"> <p> 可選. 當JSON中顯示值1時，它表示您的帳戶已連結至<span class="keyword"> Test&amp;Target </span>，且至少有一個業務規則位於A:B測試中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;autocomplete&gt; </span> </p> </td> 
   <td colname="col2"> <p> 可選. 使用自動完成時，此節點會顯示在頁面上，指出CSS和JavaScript與表單中的內容一起存在。 這些欄位通常不會變更，除非有人變更自動完成設定。 在這種情況下，xxx_cache_ver欄位會遞增，以強制客戶瀏覽器上快取內容失效。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;css&gt; </span> </p> </td> 
   <td colname="col2"> <p> 與自動完成相關聯的CSS。 建議您將此標籤置於頁面高處，以改善頁面演算。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;form-content&gt; </span> </p> </td> 
   <td colname="col2"> <p> 自動完成實用程式搜索到正確控制項所需的內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;js&gt; </span> </p> </td> 
   <td colname="col2"> <p> 自動完成所需的自訂JavaScript。 建議您將此標籤放置在頁面中低處，以改善頁面演算。 自動完成作業也需要UI JavaScript。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;hidden-parameters&gt; </span> </p> </td> 
   <td colname="col2"> <p> 包含要包含在搜索表單中的所有隱藏參數（名稱和值）。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 排序{#section_558853CD376F4D71BACF211D53085D55}

下列範例顯示三選項排序功能表的資料。 功能表可讓客戶依相關性、標題或評分來排序。 目前選取的項目包含屬性&quot;selected=true&quot;。 」。 始終提供關聯選項，允許客戶返回原始顯示的預設搜索結果。

範例:  

```xml
 <sort> 
  <sort-item selected="true"> 
   <label><![CDATA[Relevance]]></label> 
   <value><![CDATA[relevance]]></value> 
   <link><![CDATA[]]></link> 
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Title]]></label> 
   <value><![CDATA[title]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=title;x1=content-type]]></link>     
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Rating]]></label> 
   <value><![CDATA[user-rating]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=user-rating;x1=content-type]]></link>     
  </sort-item> 
 </sort>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>排序選單中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> 選項的客戶對應文字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> 表示此選項的"sort"查詢字串參數值。 如果使用<span class="codeph"> &lt;link&gt; </span>值，則不需要此標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> 對於未選定的選項，<span class="codeph"> &lt;link&gt; </span>參數包含返回相同結果集的相對連結，按新排序參數排序。 此欄位對於當前選擇的排序選項為空。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 建議 {#section_6EC104E1DDD94AC799B65E6E61A2FB3C}

只有少數結果或沒有結果時，就會傳回建議。 此節點包含的詞語可產生成功的查詢，並可顯示在「無結果」頁面上。 連結也會傳回，讓客戶可以跳至新查詢。

範例:  

```xml
 <suggestions> 
  <suggestion-item> 
   <link><![CDATA[?q=video]]></link> 
   <word><![CDATA[video]]> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>建議中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p>用來建立建議詞語搜尋結果超連結的相對連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;word&gt; </span> </p> </td> 
   <td colname="col2"> <p>建議的詞。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 區域{#section_AE53A498B440465EAF2286F2AE87D548}

範例:  

```xml
<zones> 
 <zone> 
  <name><![CDATA[best-sellers]]></name> 
  <display><![CDATA[1]]></display> 
 </zone> 
</zones> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>區域中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;zone&gt; </span> </p> </td> 
   <td colname="col2"> <p> 單個區域節點。 您可以有多個區域節點。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;名稱&gt; </span> </p> </td> 
   <td colname="col2"> <p> 區域的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;display&gt; </span> </p> </td> 
   <td colname="col2"> <p> 1或0表示區域是否顯示。 實際區域內容可以是網頁或搜尋結果中的靜態區域，例如最暢銷商品或相關產品。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 引導式搜尋XML輸出{#reference_D93E859A277643068B10AE7A61C973EA}

描述標準XML回應輸出的表格。

您可以檢視下列項目的XML回應：

* [橫幅廣告](../c-appendices/c-guidedsearchoutput.md#section_6A19EC26DD3B494194AAA788151B78B5)
* [階層連結](../c-appendices/c-guidedsearchoutput.md#section_E48A71B0EBDB4EDDA7587009AD865488)
* [刻面](../c-appendices/c-guidedsearchoutput.md#section_5CEB1F966C004FFEA3CF675638966E25)
* [頁首和查詢](../c-appendices/c-guidedsearchoutput.md#section_802835E19BCB48239C6770A1B72DFFF8)
* [編頁](../c-appendices/c-guidedsearchoutput.md#section_72DB86DDE1284B1EA295CFFBC16A3150)
* [最近搜尋](../c-appendices/c-guidedsearchoutput.md#section_BCA2DDD17F264CF6BA11634E1A514E28)
* [結果](../c-appendices/c-guidedsearchoutput.md#section_EC496F5CA2634158891455E2F6DF6833)
* [搜尋表單](../c-appendices/c-guidedsearchoutput.md#section_F92D8C3D37174A10A4E26CAFF3F3DF89)
* [排序](../c-appendices/c-guidedsearchoutput.md#section_32DC50A103BF491BA3665A5CADCCAADE)
* [建議](../c-appendices/c-guidedsearchoutput.md#section_D81BCE46F0AF443695DF9C4BA084B716)
* [區域](../c-appendices/c-guidedsearchoutput.md#section_15D8AA585F3246799968BA88EE2C9FC2)

## 橫幅廣告 {#section_6A19EC26DD3B494194AAA788151B78B5}

範例:  

```xml
<banners> 
 <banner> 
  <area><![CDATA[top-left]]></area> 
  <content><![CDATA[<img src="https://www.megacorp.com/discount.gif"/>]]></content> 
 </banner> 
</banners>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>橫幅中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;banner&gt; </span> </p> </td> 
   <td colname="col2"> <p> 個別橫幅節點。 您可以有多個橫幅節點。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;area&gt; </span> </p> </td> 
   <td colname="col2"> <p> 顯示橫幅的網頁區域。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;content&gt; </span> </p> </td> 
   <td colname="col2"> <p> 橫幅區域的HTML內容。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 階層連結{#section_E48A71B0EBDB4EDDA7587009AD865488}

在下列範例中，每次客戶透過Facet進一步縮小範圍時，選取範圍就會新增至階層連結。 每個項目都表示為`<breadcrumb-item>`。

範例:  

```xml
 <breadcrumb> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year]]></link> 
   <value><![CDATA[new year]]></value> 
  </breadcrumb-item> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year;q1=Articles;x1=content-type]]></link> 
   <value><![CDATA[Articles]]></value> 
  </breadcrumb-item> 
 </breadcrumb> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>網站導覽路徑標示中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> 顯示所需檢視之搜尋結果的相對連結。 按一下網站導覽路徑標示連結，會將客戶帶往檢視，其中會移除所有後續的調整。 其他選項也可供使用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> 階層連結項目的客戶對應文字。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Facets {#section_5CEB1F966C004FFEA3CF675638966E25}

刻面是細化選項，可讓客戶篩選結果。 Facet通常用於分類、價格範圍、顏色選擇和其他屬性調整。 索引中的中繼資料是推動Facet的因素。

當客戶在分類中向下移動時，通常會隱藏或顯示分類Facet。 最高級別的分類（類別）稱為第1層。 當客戶按一下第1層選項時，會出現第2層（子類別）調整選項，而第1層選項會消失。 當客戶按一下第2層選項時，會出現第3層（子子類別）調整選項，而第2層選項會消失。 如上所述，這些選項會隱藏並顯示——您的Web應用程式不會受到這些選項的影響。

每個Facet都包含在`<facet-item>`標籤中。 在下列範例中，它顯示一個Facet，可讓客戶依「holiday」調整搜尋結果。

範例:  

```xml
 <facets> 
  <facet-item> 
   <facet-title><![CDATA[Holidays]]></facet-title> 
   <facet-value> 
    <label><![CDATA[New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[11]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Christmas]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Christmas;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Chinese New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Chinese+New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Thanksgiving]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Thanksgiving;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[4th of July]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=4th+of+July;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Father&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Father's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Hanukkah]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Hanukkah;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Mother&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Mother's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Valentine&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Valentine's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
  </facet-item> 
  <facet-item> 
   <facet-title><![CDATA[Seasons]]></facet-title> 
   <facet-value> 
    <label><![CDATA[Winter]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Winter;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[20]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Summer]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Summer;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Autumn]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Autumn;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[4]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Spring]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Spring;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
  </facet-item>  
 </facets> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Facet中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> Facet的客戶對應標題。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> Facet選項的客戶對應標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> 與結果的相對連結，讓選項進一步調整。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;count&gt; </span> </p> </td> 
   <td colname="col2"> <p> 該精化結果集中的結果數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;undolink&gt; </span> </p> </td> 
   <td colname="col2"> <p> 選取Facet值時，節點會傳回「還原連結」，讓客戶退出結果。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 標題和查詢{#section_802835E19BCB48239C6770A1B72DFFF8}

範例:  

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes" ?> 
<result> 
 <query> 
  <user-query><![CDATA[new year]]></user-query> 
  <lower-results><![CDATA[1]]></lower-results> 
  <upper-results><![CDATA[16]]></upper-results> 
  <total-results><![CDATA[621]]></total-results> 
 </query> 
```

搭配使用這些標籤時，會顯示如下訊息：「在621年的1-16項中，顯示『新年』的結果。」

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>標題和查詢中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;user-query&gt; </span> </p> </td> 
   <td colname="col2"> <p> 隨請求提交的關鍵字查詢。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;lower-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> 此頁面上第一個結果的項目編號。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;upper-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> 此頁面上最後一個結果的項目編號。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> 符合使用者查詢的結果總數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;custom-field&gt; </span> </p> </td> 
   <td colname="col2"> <p> 全域套用至搜尋結果的可選欄位。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 編頁{#section_72DB86DDE1284B1EA295CFFBC16A3150}

範例:  

```xml
<pagination> 
 <total-pages><39></total-pages> 
 <pages> 
   <page position="first"></page> 
   <page position="last">?i=1;page=39;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="previous"></page> 
   <page position="next">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="1" selected="true">?i=1;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="2">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="3">?i=1;page=3;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="4">?i=1;page=4;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="5">?i=1;page=5;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="6">?i=1;page=6;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="7">?i=1;page=7;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="8">?i=1;page=8;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="9">?i=1;page=9;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="10">?i=1;page=10;q=new+year;q1=Articles;x1=content-type]]></page> 
 </pages> 
</pagination> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>分頁中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-pages&gt; </span> </p> </td> 
   <td colname="col2"> <p> 結果的頁數總計，以結果數除以每頁結果數為基準。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="first"&gt; </span> </p> </td> 
   <td colname="col2"> <p> 包含結果集中第一頁的相對連結，除非客戶已檢視第1頁。 在這種情況下，它是空的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="last"&gt; </span> </p> </td> 
   <td colname="col2"> <p> 包含結果集中最後一頁的相對連結，除非客戶正在查看最後一頁。 在這種情況下，它是空的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="previous"&gt; </span> </p> </td> 
   <td colname="col2"> <p> 包含結果集上一頁的相對連結，除非客戶正在檢視第1頁；在這種情況下，它是空的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="next"&gt; </span> </p> </td> 
   <td colname="col2"> <p> 包含結果集中最後一頁的相對連結，除非客戶正在查看最後一頁。 在這種情況下，它是空的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="x"&gt;</span> </p> </td> 
   <td colname="col2"> <p> 包含特定頁碼的相對連結。 顯示十個連續的頁碼。 在第1頁，是第1-10頁。 在結果集結尾（在本例中為39）時，會是第30-39頁。 例如，在結果集的中心（第15頁），它應該是第11-20頁。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> selected="true"&gt;  </span> </p> </td> 
   <td colname="col2"> <p> 套用為屬性至目前選取的頁面。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最近搜索{#section_BCA2DDD17F264CF6BA11634E1A514E28}

「最近搜尋」是以Cookie為基礎的功能，只有在您將Cookie資訊中繼至伺服器時才能運作。

範例:  

```xml
<recent-searches> 
 <recent-search> 
  <search-term><![CDATA[shoes]]></search-term> 
  <link><![CDATA[?q=shoes]]></link> 
 </recent-search> 
</recent-searches> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>最近搜尋中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;recent-search&gt; </span> </p> </td> 
   <td colname="col2"> <p> 個別的最近搜尋節點。 您可以有多個最近搜尋的節點。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-term&gt; </span> </p> </td> 
   <td colname="col2"> <p> 客戶先前搜尋的詞。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> 前一個搜尋的連結。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 結果 {#section_EC496F5CA2634158891455E2F6DF6833}

「結果」集是XML回應的可自訂區域。 每個索引在中繼資料的欄位命名機制中都是唯一的。 每個結果都會傳回常見欄位，例如標題、說明和URL。 但是，為索引中的頁面定義的任何中繼資料都可以用於每個結果節點。 分類、價格、顏色和縮圖只是您可套用至結果的一些選項，以產生更吸引人的搜尋結果。

「結果」格式會根據您實作的特定中繼資料自訂。 結果中顯示的任何結果資料（包括縮圖影像URL）都包含在此處。

此外，您也可以在頁面中設定多個結果區域，例如「精選結果」，或個別「產品」和「內容」結果區域。 在這些情況下，HTML中會提供多個結果區域，但Facet僅與主要結果集關聯。

範例:  

```xml
 <results> 
  <result> 
    <index><![CDATA[1]]></index> 
    <result-title><![CDATA[New Year's Eve Slumber Party]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/new-years-eve-slumber-party-705199/]]></url> 
    <meta-description><![CDATA[Fun New Year's celebration ideas for your kids]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/new-years-eve-

slumber-party-parties-photo-80-FF1200SLEEPA18.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/new-years-eve- 
slumber-party-parties-photo-160-FF1200SLEEPA18.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Nancy Mades]]></byline> 
    <blurb><![CDATA[Fun New Year's celebration ideas for your kids]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[2]]></index> 
    <result-title><![CDATA[10 Holiday Traditions to Start This Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/10-holiday-traditions-to-start-this-year-704781/]]></url> 
    <meta-description><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/10-holiday- 
traditions-to-start-this-year-parties-photo-80-FF1107HOLIA01.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/10-holiday- 
traditions-to-start-this-year-parties-photo-160-FF1107HOLIA01.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Julie Taylor]]></byline> 
    <blurb><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[3]]></index> 
    <result-title><![CDATA[A Perfect New Year's Eve]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/a-perfect-new-years-eve-705258/]]></url> 
    <meta-description><![CDATA[You can turn New Year's into a celebration for the whole family.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Teri Keough]]></byline> 
    <blurb><![CDATA[You can turn New Year's into a celebration for the whole family.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[4]]></index> 
    <result-title><![CDATA[New Year's Fun and Games]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/new-years-fun-and-games-705220/]]></url> 
    <meta-description><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Charlotte Meryman]]></byline> 
    <blurb><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[5]]></index> 
    <result-title><![CDATA[11 Great Ways to Start the New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/11-great-ways-to-start-the-new-year-705552/]]></url> 
    <meta-description><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Emily Block]]></byline> 
    <blurb><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[6]]></index> 
    <result-title><![CDATA[Celebrating Chinese New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/celebrating-chinese-new-year-705260/]]></url> 
    <meta-description><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[7]]></index> 
    <result-title><![CDATA[New Year's Eve, Family Style]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/new-years-eve-family-style-701283/]]></url> 
    <meta-description><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[8]]></index> 
    <result-title><![CDATA[Chinese New Year Activities]]></result-title> 
    <url><![CDATA[https://mysite.com/crafts/chinese-new-year-activities-710345/]]></url> 
    <meta-description><![CDATA[Activities for celebrating Chinese New Year.]]></meta-description> 
    <category><![CDATA[crafts]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Activities for celebrating Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[9]]></index> 
    <result-title><![CDATA[More Organized in the New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/more-organized-in-the-new-year-701284/]]></url> 
    <meta-description><![CDATA[Tips for getting your household more organized--and getting the kids to help.]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Tips for getting your household more organized--and getting your kids to help out.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[10]]></index> 
    <result-title><![CDATA[Checklists: Year-End Safety Checklist]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/checklists-year-end-safety-checklist-701352/]]></url> 
    <meta-description><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></blurb> 
  </result>   
 </results> 
</customer-result> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>結果中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;index&gt; </span> </p> </td> 
   <td colname="col2"> <p> 此結果集中結果的序列號。 在此範例中，每頁顯示10個結果，在結果第2頁，第一個項目的索引為11。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> 此頁面的客戶對應標題。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;url&gt; </span> </p> </td> 
   <td colname="col2"> <p> 此頁面的URL。 它可用來建立超連結，讓客戶點選結果。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 搜尋表單{#section_F92D8C3D37174A10A4E26CAFF3F3DF89}

範例:  

```xml
<search-form> 
 <include-tnt-mbox>1 </included-tnt-mbox> 
 <autocomplete> 
  <css><![CDATA[<!--link rel="stylesheet" type="te 
        xt/css"href="//content.atomz.com/sp000000a8/publish/autoc 
        omplete_styles.css?sp_css_cache_ver=2" /-->]]> 
  </css> 
  <form-content><![CDATA[<div id="autocomplete"></div>]]> 
  </form-content> 
  <js><![CDATA[<script type="text/javascript" 
   src="//content.atomz.com/sp100491de/publish/autoc 
   omplete_data.js?sp_js_cache_ver=3"></script>]]> 
  </js> 
 </autcomplete> 
 <hidden-parameters> 
  <parameter> 
   <name><![CDATA[store]]></name> 
   <value><![CDATA[mens]]></value> 
  </parameter> 
 </hidden-parameters> 
</search-form>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>搜尋表單中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;include-tnt-mbox&gt; </span> </p> </td> 
   <td colname="col2"> <p> 可選. 當XML中顯示1時，它表示您的帳戶已連結至<span class="keyword"> Test&amp;Target </span>，且至少有一個業務規則位於A:B測試中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;autocomplete&gt; </span> </p> </td> 
   <td colname="col2"> <p> 可選. 使用自動完成時，此節點會顯示在頁面上，指出CSS和JavaScript與表單中的內容一起存在。 這些欄位通常不會變更，除非有人變更自動完成設定。 在這種情況下，xxx_cache_ver欄位會遞增，以強制客戶瀏覽器上快取內容失效。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;css&gt; </span> </p> </td> 
   <td colname="col2"> <p> 與自動完成相關聯的CSS。 建議您將此標籤置於頁面高處，以改善頁面演算。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;form-content&gt; </span> </p> </td> 
   <td colname="col2"> <p> 自動完成實用程式搜索到正確控制項所需的內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;js&gt; </span> </p> </td> 
   <td colname="col2"> <p> 自動完成所需的自訂JavaScript。 建議您將此標籤放置在頁面中低處，以改善頁面演算。 自動完成作業也需要UI JavaScript。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;hidden-parameters&gt; </span> </p> </td> 
   <td colname="col2"> <p> 包含要包含在搜索表單中的所有隱藏參數（名稱和值）。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 排序{#section_32DC50A103BF491BA3665A5CADCCAADE}

下列範例顯示三選項排序功能表的資料。 功能表可讓客戶依相關性、標題或評分來排序。 目前選取的項目包含屬性&quot;selected=true&quot;。 」。 始終提供關聯選項，允許客戶返回原始顯示的預設搜索結果。

範例:  

```xml
 <sort> 
  <sort-item selected="true"> 
   <label><![CDATA[Relevance]]></label> 
   <value><![CDATA[relevance]]></value> 
   <link><![CDATA[]]></link> 
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Title]]></label> 
   <value><![CDATA[title]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=title;x1=content-type]]></link>     
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Rating]]></label> 
   <value><![CDATA[user-rating]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=user-rating;x1=content-type]]></link>     
  </sort-item> 
 </sort>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>排序選單中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> 選項的客戶對應文字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> 表示此選項的"sort"查詢字串參數值。 如果使用<span class="codeph"> &lt;link&gt; </span>值，則不需要此標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> 對於未選定的選項，<span class="codeph"> &lt;link&gt; </span>參數包含返回相同結果集的相對連結，按新排序參數排序。 此欄位對於當前選擇的排序選項為空。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 建議 {#section_D81BCE46F0AF443695DF9C4BA084B716}

只有少數結果或沒有結果時，就會傳回建議。 此節點包含的詞語可產生成功的查詢，並可顯示在「無結果」頁面上。 連結也會傳回，讓客戶可以跳至新查詢。

範例:  

```xml
 <suggestions> 
  <suggestion-item> 
   <link><![CDATA[?q=video]]></link> 
   <word><![CDATA[video]]> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>建議中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p>用來建立建議詞語搜尋結果超連結的相對連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;word&gt; </span> </p> </td> 
   <td colname="col2"> <p>建議的詞。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 區域{#section_15D8AA585F3246799968BA88EE2C9FC2}

範例:  

```xml
<zones> 
 <zone> 
  <name><![CDATA[best-sellers]]></name> 
  <display><![CDATA[1]]></display> 
 </zone> 
</zones> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>區域中的標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;zone&gt; </span> </p> </td> 
   <td colname="col2"> <p> 單個區域節點。 您可以有多個區域節點。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;名稱&gt; </span> </p> </td> 
   <td colname="col2"> <p> 區域的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;display&gt; </span> </p> </td> 
   <td colname="col2"> <p> 1或0表示區域是否顯示。 實際區域內容可以是網頁或搜尋結果中的靜態區域，例如最暢銷商品或相關產品。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Adobe Experience Manager {#reference_DBE13C606C3A4BB185DE53F88D0D3048}的引導式搜尋XML輸出

說明AEM(Adobe Experience Manager)標準XML回應輸出的表格。

另請參閱 . [引導式搜尋XML輸出](../c-appendices/c-guidedsearchoutput.md#reference_D93E859A277643068B10AE7A61C973EA)

您可以檢視下列項目的XML回應：

* [橫幅廣告](../c-appendices/c-guidedsearchoutput.md#section_B16EDC5533FA4494AC9983AA7357CBE3)
* [網站導覽路徑標示](../c-appendices/c-guidedsearchoutput.md#section_49EA7043FBE44315A79A4E738BE30114)
* [自訂欄位](../c-appendices/c-guidedsearchoutput.md#section_38DD31AFE5DD4263A63644AFF484E0F4)
* [刻面](../c-appendices/c-guidedsearchoutput.md#section_BE98990E3DD748A1BD4E0CA322314B79)
* [標題](../c-appendices/c-guidedsearchoutput.md#section_5305B1DC5774439485CA0665DB683F9C)
* [功能表與排序](../c-appendices/c-guidedsearchoutput.md#section_A34CBB645DBF4C70A12A5B7E81211295)
* [編頁](../c-appendices/c-guidedsearchoutput.md#section_E52F81C6A6EB4B8F996157B657EC540F)
* [查詢](../c-appendices/c-guidedsearchoutput.md#section_3DAA1013F09742869B80F6A361816E6C)
* [最近搜尋](../c-appendices/c-guidedsearchoutput.md#section_17F942F6EC07456DABED7A483AC08446)
* [結果](../c-appendices/c-guidedsearchoutput.md#section_155A80B8C4F641678DD9C8F257108412)
* [搜尋表單](../c-appendices/c-guidedsearchoutput.md#section_9E4B99D4FEDC49629F6C7E866F3A7493)
* [建議](../c-appendices/c-guidedsearchoutput.md#section_2899FACB9AD84F60B3687C1B4EF09E15)
* [範本](../c-appendices/c-guidedsearchoutput.md#section_1E2BB2F274B04F5491A4CCCC38F507BD)
* [區域](../c-appendices/c-guidedsearchoutput.md#section_26C4A947E7B1474A8E37D86D9579B93E)

## 橫幅廣告 {#section_B16EDC5533FA4494AC9983AA7357CBE3}

網站搜尋／銷售可管理客戶的橫幅，將橫幅插入網頁的不同部分。

範例橫幅：

以下是橫幅的範例，它位於稱為「top」的頁面區域中。

```xml
   <banners> 
       <banner> 
           <area><![CDATA[top]]></area> 
           <content><![CDATA[<div style="color:#70A100">We have custom shipping</div>]]></content> 
       </banner> 
    </banners> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>節點 </p> </th> 
   <th colname="col2" class="entry"> <p>父節點 </p> </th> 
   <th colname="col3" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>橫幅 </p> </td> 
   <td colname="col2"> <p>客戶成果 </p> </td> 
   <td colname="col3"> <p>包含0-n個橫幅節點，指示每個橫幅區域以及插入該區域的內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>橫幅 </p> </td> 
   <td colname="col2"> <p>橫幅 </p> </td> 
   <td colname="col3"> <p>個別橫幅節點。 您可以有多個橫幅節點。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>面積 </p> </td> 
   <td colname="col2"> <p>橫幅 </p> </td> 
   <td colname="col3"> <p>顯示橫幅的網頁區域。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>內容 </p> </td> 
   <td colname="col2"> <p>橫幅 </p> </td> 
   <td colname="col3"> <p>橫幅內容。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 網站導覽路徑標示 {#section_49EA7043FBE44315A79A4E738BE30114}

支援多個網站導覽路徑。 您可以在&#x200B;**[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**&#x200B;中定義瀏覽路徑標示及其對應行為。 此外，您還需要為您定義的每個階層連結指定唯一的名稱。 瀏覽路徑標示XML節點會重複您所有定義的瀏覽路徑標示。 建議您在搜尋結果中只顯示一個網站導覽路徑標示。

在下列範例中，每次客戶透過Facet進一步縮小範圍時，選取範圍就會新增至階層連結。 每個項目都表示為`<breadcrumb-item>`。

階層連結節點範例：

```xml
    <breadcrumbs> 
  <breadcrumb> 
            <name><![CDATA[default]]></name> 
     <breadcrumb-item> 
   <link><![CDATA[?i=1;q=mens;sp_cs=UTF-8;view=xml]]></link> 
   <value><![CDATA[mens]]></value> 
                <label><![CDATA[]]></label> 
      </breadcrumb-item> 
     <breadcrumb-item> 
   <link><![CDATA[?i=1;q=mens;q1=Channel;sp_cs=UTF-8;view=xml;x1=brand]]></link> 
   <value><![CDATA[Channel]]></value> 
                <label><![CDATA[brand]]></label> 
      </breadcrumb-item> 
   </breadcrumb> 
    </breadcrumbs> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>節點 </p> </th> 
   <th colname="col2" class="entry"> <p>父節點 </p> </th> 
   <th colname="col3" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>麵包屑 </p> </td> 
   <td colname="col2"> <p>客戶成果 </p> </td> 
   <td colname="col3"> <p> 包含定義每個階層連結的0-n階層連結節點。 大部分客戶只有一個階層連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>breadcrum </p> </td> 
   <td colname="col2"> <p>麵包屑 </p> </td> 
   <td colname="col3"> <p> 包含定義網站導覽路徑標示定義的子節點。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p>breadcrum </p> </td> 
   <td colname="col3"> <p> 階層連結的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>breadcrumb-item </p> </td> 
   <td colname="col2"> <p>階層連結中的個別項目。 每個項目都表示當使用者縮小結果集時，追蹤中的步驟。 </p> </td> 
   <td colname="col3"> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>breadcrumb-item </p> </td> 
   <td colname="col3"> <p> 顯示所需檢視之搜尋結果的相對連結。 按一下網站導覽路徑標示連結，會將客戶帶往檢視，其中會移除所有後續的調整。 也提供其他選項，例如拖放和移除。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>value </p> </td> 
   <td colname="col2"> <p>breadcrumb-item </p> </td> 
   <td colname="col3"> <p> 階層連結項目的客戶對應文字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>標籤 </p> </td> 
   <td colname="col2"> <p>breadcrumb-item </p> </td> 
   <td colname="col3"> <p> 標籤標籤會輸出階層連結值的標籤，其中詳述選取要產生該階層連結項目的階層連結值。 它僅用於引導式網站導覽路徑標示區塊的內容。 對於查詢詞語步驟，此為空白。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 自訂欄位{#section_38DD31AFE5DD4263A63644AFF484E0F4}

自訂欄位是具有全域內容之變數的雜項集合。 它通常用於傳遞在搜尋結果頁面中繼資料中設定的搜尋引擎最佳化變數。

自定義欄位節點示例：

```xml
    <custom-fields> 
        <custom-field name="seo-search-title"><![CDATA[Geometrixx Search Results]]></custom-field> 
        <custom-field name="seo-search-keywords"><![CDATA[]]></custom-field> 
    </custom-fields> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>節點 </p> </th> 
   <th colname="col2" class="entry"> <p>父節點 </p> </th> 
   <th colname="col3" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>自訂欄位 </p> </td> 
   <td colname="col2"> <p>客戶成果 </p> </td> 
   <td colname="col3"> <p> 可包含定義自訂欄位的0-n子節點。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>custom-field </p> </td> 
   <td colname="col2"> <p>自訂欄位 </p> </td> 
   <td colname="col3"> <p> 可選. 包含由name屬性指示的指定自訂欄位值。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Facets {#section_BE98990E3DD748A1BD4E0CA322314B79}

刻面是細化選項，可讓客戶篩選結果。 Facet通常用於分類、價格範圍、顏色選擇和其他屬性調整。 Facet建立在索引中的中繼資料之上。

當客戶在分類中向下移動時，通常會隱藏或顯示分類Facet。 最高級別的分類（類別）稱為第1層。 當客戶按一下第1層選項時，會出現第2層（子類別）調整選項，而第1層選項會消失。 當客戶按一下第2層選項時，會出現第3層（子子類別）調整選項，而第2層選項會消失。 如上所述，這些選項被隱藏和顯示；您的Web應用程式不會影響它們。

每個Facet都包含在`<facet-item>`標籤中。 在下列範例中，它顯示一個Facet，可讓客戶依「假日」調整搜尋結果。

Facet區塊範例：

```xml
<facets>          
     <facet> 
         <facet-title><![CDATA[Department]]></facet-title> 
                <behavior><![CDATA[sticky]]></behavior> 
                <selected>1</selected> 
                <undo-link><![CDATA[?i=1;lang=enus;q=*;q1=Armora+Jeans;sp_staged=1;view=xml;x1=brand]]></undo-link> 
      <facet-value> 
          <selected><![CDATA[true]]></selected> 
              <label><![CDATA[Mens]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Armora+Jeans;q2=Mens;sp_staged=1;view=xml;x1=brand;x2=leveli]]></link> 
       <count><![CDATA[3]]></count> 
                        <undolink><![CDATA[?i=1;lang=enus;q=*;q1=Armora+Jeans;sp_staged=1;view=xml;x1=brand]]></undolink> 
      </facet-value> 
      </facet> 
     <facet> 
         <facet-title><![CDATA[Sub-Category]]></facet-title> 
                <behavior><![CDATA[sticky]]></behavior> 
                <selected>0</selected> 
      <facet-value>           
              <label><![CDATA[Apparel]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans;q3=Apparel;sp_staged=1;view=xml;x1=leveli;x2=brand;x3=levelii]]></link> 
       <count><![CDATA[3]]></count>                         
      </facet-value>   
      </facet>         
     <facet> 
         <facet-title><![CDATA[Brand]]></facet-title> 
                <behavior><![CDATA[multi-select]]></behavior> 
                <selected>1</selected> 
                <undo-link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;sp_staged=1;view=xml;x1=leveli]]></undo-link> 
      <facet-value>        
              <label><![CDATA[Amoura]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Amoura;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[9]]></count>                         
      </facet-value>   
      <facet-value>         
              <label><![CDATA[Armora]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Armora;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[12]]></count>                        
      </facet-value>   
      <facet-value> 
          <selected><![CDATA[true]]></selected> 
              <label><![CDATA[Armora Jeans]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Armora+Jeans;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
 
       <count><![CDATA[3]]></count> 
                        <undolink><![CDATA[?i=1;lang=enus;q=*;q1=Mens;sp_staged=1;view=xml;x1=leveli]]></undolink> 
      </facet-value>   
      <facet-value>           
              <label><![CDATA[Art of Grooming]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Art+of+Grooming;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[4]]></count>                         
      </facet-value>   
      <facet-value>          
              <label><![CDATA[Bear Co.]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Bear+Co.;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[1]]></count> 
      </facet-value> 
      <facet-value>      
              <label><![CDATA[Citizens]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Citizens;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[4]]></count> 
      </facet-value> 
      <facet-value> 
              <label><![CDATA[D&amp;B]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|D%26B;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[17]]></count> 
      </facet-value> 
      <facet-value> 
              <label><![CDATA[David Yuri]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|David+Yuri;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[2]]></count>    
      </facet-value>   
      </facet> 
    </facets> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>節點 </p> </th> 
   <th colname="col2" class="entry"> <p>父節點 </p> </th> 
   <th colname="col3" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>刻面 </p> </td> 
   <td colname="col2"> <p>客戶成果 </p> </td> 
   <td colname="col3"> <p>容器Facet節點，其具有代表每個Facet的0-n個子節點。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>fact </p> </td> 
   <td colname="col2"> <p>刻面 </p> </td> 
   <td colname="col3"> <p> 單一Facet例項。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>facet-title </p> </td> 
   <td colname="col2"> <p>fact </p> </td> 
   <td colname="col3"> <p>Facet的客戶對應標題。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>行為 </p> </td> 
   <td colname="col2"> <p>fact </p> </td> 
   <td colname="col3"> <p>Facet的行為。 例如，一般、自黏或多選。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>已選取 </p> </td> 
   <td colname="col2"> <p>fact </p> </td> 
   <td colname="col3"> <p>1)，否則為0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>還原連結 </p> </td> 
   <td colname="col2"> <p>fact </p> </td> 
   <td colname="col3"> <p> 僅在選取Facet時顯示。 還原連結會還原整個Facet。 例如，當它是多選Facet時，它會取消選取該Facet的所有選取選項。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>facet-value </p> </td> 
   <td colname="col2"> <p>fact </p> </td> 
   <td colname="col3"> <p>包含屬於Facet的所有個別Facet項目。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>已選取 </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>如果選取了含有Facet的目前項目，則此節點會存在並設為「true」。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>標籤 </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>Facet選項的客戶對應標籤。 依預設，這應該已由HTML逸出。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p> 與結果的相對連結，讓選項進一步調整。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>計數 </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>該精化結果集中的結果數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>還原連結 </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>選取Facet值時，節點會傳回「還原連結」，讓客戶退出選取個別Facet的選項。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 檔頭 {#section_5305B1DC5774439485CA0665DB683F9C}

範例:  

```xml
xml version="1.0" encoding="utf-8" standalone="yes" 
```

## 菜單和排序{#section_A34CBB645DBF4C70A12A5B7E81211295}

支援排序結果的功能表，並變更每頁要傳回的結果數。 它也支援導覽功能表，對於使用「搜尋為導覽」非常有用。 帳戶可以定義多個相同類型的功能表，並使用其任何功能表進行簡報。

菜單節點示例：

下列範例顯示三選項排序選單和導覽選單的資料。 排序功能表可讓客戶依相關性、標題或評分來排序。 目前選取的項目包含屬性&quot;selected=true&quot;。 」。 始終提供關聯選項，允許客戶返回原始顯示的預設搜索結果。

```xml
<menus> 
        <menu> 
           <name><![CDATA[sort]]></name>         
             <item selected="true"> 
          <label><![CDATA[Relevance]]></label> 
          <value><![CDATA[relevance]]></value> 
          <link><![CDATA[ ]]></link> 
             </item> 
             <item> 
          <label><![CDATA[Lowest Price]]></label> 
          <value><![CDATA[Price]]></value> 
          <link><![CDATA[?i=1;q=mens;sort=Price;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item> 
             <item> 
          <label><![CDATA[Highest Price]]></label> 
          <value><![CDATA[Price_r]]></value> 
          <link><![CDATA[?i=1;q=mens;sort=Price_r;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item> 
             <item> 
          <label><![CDATA[Brand]]></label> 
          <value><![CDATA[brand]]></value> 
          <link><![CDATA[?i=1;q=mens;sort=brand;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item> 
        </menu> 
        <menu> 
            <name><![CDATA[ss_head_nav]]></name>   
                    <item> 
                        <label><![CDATA[WOMEN'S]]></label> 
          <value><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1;i=1;m_ss_head_nav=WOMEN'S]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[MEN'S]]></label> 
          <value><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></value> 
          <link><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[JEWELRY & ACCESSORIES]]></label> 
          <value><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1]]></value> 
          <link><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1;i=1;m_ss_head_nav=JEWELRY+%26+ACCESSORIES]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[BEAUTY & FRAGRANCE]]></label> 
          <value><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=BEAUTY+%26+FRAGRANCE]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[GIFTS & HOME]]></label> 
          <value><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=GIFTS+%26+HOME]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[CHILDREN & TOYS]]></label> 
          <value><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=CHILDREN+%26+TOYS]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[ELECTRONICS]]></label> 
          <value><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=ELECTRONICS]]></link> 
                    </item> 
        </menu> 
    </menus> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>節點 </p> </th> 
   <th colname="col2" class="entry"> <p>父節點 </p> </th> 
   <th colname="col3" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>菜單 </p> </td> 
   <td colname="col2"> <p>客戶成果 </p> </td> 
   <td colname="col3"> <p>包含定義每個菜單的0-n子節點。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>功能表 </p> </td> 
   <td colname="col2"> <p>菜單 </p> </td> 
   <td colname="col3"> <p>功能表的單一例項（與<span class="uicontrol">設計</span> &gt; <span class="uicontrol">導覽</span> &gt; <span class="uicontrol">功能表</span>中定義的功能表相對應）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>名稱 </p> </td> 
   <td colname="col2"> <p>功能表 </p> </td> 
   <td colname="col3"> <p>功能表名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>項目 </p> </td> 
   <td colname="col2"> <p>功能表 </p> </td> 
   <td colname="col3"> <p>定義功能表中的每個項目。 如果目前選取了指定的功能表項目，則選取的選用屬性會設為true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>標籤 </p> </td> 
   <td colname="col2"> <p>項目 </p> </td> 
   <td colname="col3"> <p>功能表項目的客戶對應文字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>值 </p> </td> 
   <td colname="col2"> <p>項目 </p> </td> 
   <td colname="col3"> <p>表示功能表項目的值（功能表也設定的查詢參數值）。 如果使用&lt;link&gt;值，則不需要此標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>項目 </p> </td> 
   <td colname="col3"> <p>對於未選取的選項，&lt;link&gt;參數包含傳回相同結果集但套用功能表選項的相對連結。 此欄位對於當前選擇的排序選項為空。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 編頁{#section_E52F81C6A6EB4B8F996157B657EC540F}

結果集會分割成多個頁面。 通常，客戶在單一頁面上顯示10 - 20個結果。 後續結果會顯示在下一頁。 分頁XML可讓您建立一組導覽連結，讓客戶可以逐頁瀏覽結果集。 有四個可用的導覽連結：第一、最後、下一個和上一個。 每種連結類型都可讓客戶快速瀏覽頁面，以便輕鬆地檢閱和調整所要的內容。

下列範例顯示搜尋的編頁，該搜尋位於第一頁，其編頁設定為顯示五頁的連結。

分頁範例：

```xml
    <pagination> 
        <total-pages><![CDATA[112]]></total-pages> 
        <pages> 
     <page position="first"><![CDATA[]]></page> 
     <page position="last"><![CDATA[?i=1;page=112;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
     <page position="next"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="1" selected="true"><![CDATA[?i=1;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="2"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="3"><![CDATA[?i=1;page=3;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="4"><![CDATA[?i=1;page=4;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="5"><![CDATA[?i=1;page=5;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
        </pages> 
    </pagination> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>節點 </p> </th> 
   <th colname="col2" class="entry"> <p>父節點 </p> </th> 
   <th colname="col3" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>分頁 </p> </td> 
   <td colname="col2"> <p>客戶成果 </p> </td> 
   <td colname="col3"> <p> 結果的頁數總計，以結果數除以每頁結果數為基準。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>總頁數 </p> </td> 
   <td colname="col2"> <p>分頁 </p> </td> 
   <td colname="col3"> <p>分佈搜尋結果的頁面總數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>頁面 </p> </td> 
   <td colname="col2"> <p>分頁 </p> </td> 
   <td colname="col3"> <p>包含0-n個頁面節點，可定義分頁中的每個頁面。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>頁面 </p> </td> 
   <td colname="col2"> <p>頁面 </p> </td> 
   <td colname="col3"> <p>存在四個特殊頁面節點：第一、最後、上一和下一個。 這四個頁面是可選的，只有在合理時才會顯示在結果集中。 例如，如果您位於第1頁，則沒有「上一個」連結。 所有其他頁面都表示位置。 列出的頁數取決於在分頁使用者介面中設定的「頁面連結數」。 「選取」屬性會指出客戶目前所在的頁面。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 查詢 {#section_3DAA1013F09742869B80F6A361816E6C}

查詢節點示例：

```xml
    <query> 
        <user-query><![CDATA[mens]]></user-query> 
 <lower-results><![CDATA[1]]></lower-results> 
 <upper-results><![CDATA[12]]></upper-results> 
 <total-results><![CDATA[265]]></total-results> 
    </query> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>節點 </p> </th> 
   <th colname="col2" class="entry"> <p>父節點 </p> </th> 
   <th colname="col3" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>query </p> </td> 
   <td colname="col2"> <p>客戶成果 </p> </td> 
   <td colname="col3"> <p> 提供查詢概覽的全局節點。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>user-query </p> </td> 
   <td colname="col2"> <p>查詢 </p> </td> 
   <td colname="col3"> <p> 搜尋的關鍵字。 如果「您的意思是<span class="uicontrol">」由於原始詞語未產生結果而自動搜尋建議詞語，則會反映在搜尋的新關鍵字中（請參閱建議節點以取得原始關鍵字）。</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>低結果 </p> </td> 
   <td colname="col2"> <p>查詢 </p> </td> 
   <td colname="col3"> <p> 此頁面上第一個結果的項目編號。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>上限結果 </p> </td> 
   <td colname="col2"> <p>查詢 </p> </td> 
   <td colname="col3"> <p> 此頁面上最後一個結果的項目編號。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>總結果 </p> </td> 
   <td colname="col2"> <p>查詢 </p> </td> 
   <td colname="col3"> <p> 符合使用者查詢的結果總數。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最近搜索{#section_17F942F6EC07456DABED7A483AC08446}

「最近搜尋」是以Cookie為基礎的功能，只有在您將Cookie資訊中繼至網站搜尋／銷售伺服器時才能運作。

最近搜尋的範例：

```xml
    <recent-searches> 
        <clear-link><![?q=womens&gscr=clear]]></clear-link> 
        <recent-search> 
            <link><![?q=mens]]></link> 
            <label><![CDATA[mens]]></label> 
        <recent-search> 
    </recent-searches> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>節點 </p> </th> 
   <th colname="col2" class="entry"> <p>父節點 </p> </th> 
   <th colname="col3" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>最近搜尋 </p> </td> 
   <td colname="col2"> <p>客戶成果 </p> </td> 
   <td colname="col3"> <p>僅當搜索有最近搜索時，節點才存在。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clear-link </p> </td> 
   <td colname="col2"> <p>最近搜尋 </p> </td> 
   <td colname="col3"> <p>清除客戶最近所有搜尋的相對路徑。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>最近搜索 </p> </td> 
   <td colname="col2"> <p>最近搜尋 </p> </td> 
   <td colname="col3"> <p>定義最近的搜索。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>最近搜索 </p> </td> 
   <td colname="col3"> <p>建立連結的路徑，該連結執行用戶最近執行的搜索。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>標籤 </p> </td> 
   <td colname="col2"> <p>最近搜索 </p> </td> 
   <td colname="col3"> <p>最近搜尋的客戶對應顯示標籤。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 結果 {#section_155A80B8C4F641678DD9C8F257108412}

「結果」集是XML回應的可自訂區域。 每個索引在中繼資料的欄位命名機制中都是唯一的。 每個結果都會傳回常見欄位，例如標題、說明和URL。 但是，為索引中的頁面定義的任何中繼資料都可以用於每個結果節點。 分類、價格、顏色和縮圖只是您可套用至結果的一些選項，以產生更吸引人的搜尋結果。

結果格式會根據您實施的特定中繼資料自訂。 結果中顯示的任何結果資料（包括縮圖影像URL）都包含在此處。

此外，您也可以在頁面中設定多個結果區域，例如「精選結果」，或個別「產品」和「內容」結果區域。 在這些情況下，HTML中會提供多個結果區域，但Facet僅與主要結果集關聯。

結果節點示例：

```xml
    <results> 
        <result-set> 
            <name><![CDATA[default]]></name> 
         <result> 
                    <field name="index"><![CDATA[1]]></field> 
                    <field name="sku"><![CDATA[200190]]></field> 
                    <field name="pagename"><![CDATA[Relaxed Paint Splattered]]></field> 
 
                    <field name="img_sm_url"><![CDATA[https://geometrixx.com/images/08_geometrixx_icon_men.jpg]]></field> 
      <field name="brand"><![CDATA[Armora Jeans]]></field> 
      <field name="price"><![CDATA[195]]></field> 
      <field name="foundIn"><![CDATA[Mens,  
            Apparel,  
          Denim]]></field> 
         </result>   
         <result> 
                    <field name="index"><![CDATA[2]]></field> 
                    <field name="sku"><![CDATA[200195]]></field> 
                    <field name="pagename"><![CDATA[Tumbled Jeans]]></field> 
 
                    <field name="img_sm_url"><![CDATA[https://geometrixx.com/images/08_geometrixx_icon_men.jpg]]></field> 
      <field name="brand"><![CDATA[Armora Jeans]]></field> 
      <field name="price"><![CDATA[235]]></field> 
      <field name="foundIn"><![CDATA[Mens,  
            Apparel,  
          Denim]]></field> 
         </result>    
         <result> 
                    <field name="index"><![CDATA[3]]></field> 
                    <field name="sku"><![CDATA[200196]]></field> 
                    <field name="pagename"><![CDATA[Montana Relaxed]]></field> 
 
                    <field name="img_sm_url"><![CDATA[https://geometrixx.com/images/08_geometrixx_icon_men.jpg]]></field> 
      <field name="brand"><![CDATA[Armora Jeans]]></field> 
      <field name="price"><![CDATA[220]]></field> 
      <field name="foundIn"><![CDATA[Mens,  
            Apparel,  
          Denim]]></field> 
         </result>         
        </result-set>   
    </results> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>節點 </p> </th> 
   <th colname="col2" class="entry"> <p>父節點 </p> </th> 
   <th colname="col3" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>結果 </p> </td> 
   <td colname="col2"> <p>客戶成果 </p> </td> 
   <td colname="col3"> <p>0-n個結果集的容器節點。 零結果集表示您位於特殊的無結果著陸頁面。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>結果集 </p> </td> 
   <td colname="col2"> <p>結果 </p> </td> 
   <td colname="col3"> <p>傳入的搜尋可觸發多個搜尋。 每個結果集都包含所執行的特定命名搜索的結果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>名稱 </p> </td> 
   <td colname="col2"> <p>結果集 </p> </td> 
   <td colname="col3"> <p>結果集所屬的搜索的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>項結果 </p> </td> 
   <td colname="col2"> <p>結果集 </p> </td> 
   <td colname="col3"> <p>包含與結果集的單個結果關聯的所有欄位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>欄位 </p> </td> 
   <td colname="col2"> <p>項結果 </p> </td> 
   <td colname="col3"> <p>name屬性定義所顯示索引中欄位的名稱。 該值是該欄位的實際值。 有些結果可能會遺失與個別結果無關的欄位。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 搜尋表單{#section_9E4B99D4FEDC49629F6C7E866F3A7493}

搜尋表單包含在結果集中，讓客戶動態建立其搜尋表單。 此步驟為可選步驟。 大部分客戶都有固定的搜尋表單。 不過，它確實允許客戶根據至少有一個執行A:B測試的業務規則，判斷搜尋表單是否需要Test&amp;Target mbox。 同樣地，它可讓客戶自動取用最新的自動完成CSS和JavaScript。

搜尋表單XML的範例：

```xml
    <search-form> 
        <include-tnt-mbox>1</include-tnt-mbox> 
        <autocomplete> 
            <enabled>1</enabled> 
            <css><![CDATA[<link rel="stylesheet" type="text/css" href="https://content.t1.atomz.com/sp10043554/stage/autocomplete_styles.css?sp_js_param=2" /> 
]]></css> 
 
            <form-content><![CDATA[<div id="autocomplete"></div> 
<input type="hidden" name="sp_staged" id="sp_staged" value="1" /> 
]]></form-content> 
            <javascript><![CDATA[<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/utilities/utilities.js"></script> 
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/datasource/datasource-min.js"></script> 
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/autocomplete/autocomplete-min.js"></script> 
<script type="text/javascript" src="https://content.t1.atomz.com/sp10043554/stage/autocomplete_data.js?sp_js_param=3"></script>]]></javascript> 
        </autocomplete> 
    </search-form> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>節點 </p> </th> 
   <th colname="col2" class="entry"> <p>父節點 </p> </th> 
   <th colname="col3" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>search-form </p> </td> 
   <td colname="col2"> <p>客戶成果 </p> </td> 
   <td colname="col3"> <p>包含用於驅動搜索表單的資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>include-tnt-mbox </p> </td> 
   <td colname="col2"> <p> search-form </p> </td> 
   <td colname="col3"> <p>從技術上講，只有在您至少有一個執行Test&amp;Target A:B測試的業務規則時，才需要在搜尋表單中使用mbox。 此節點指出您是否需要mbox，或不允許您減少Test&amp;Target伺服器上的點擊數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自動完成 </p> </td> 
   <td colname="col2"> <p>search-form </p> </td> 
   <td colname="col3"> <p>容納與自動完成相關的子節點。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>已啟用 </p> </td> 
   <td colname="col2"> <p>自動完成 </p> </td> 
   <td colname="col3"> <p>當搜尋帳戶使用自動完成時，設為1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>css </p> </td> 
   <td colname="col2"> <p> 自動完成 </p> </td> 
   <td colname="col3"> <p> CSS以自動完成。 將此節點盡可能放在頁面上。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> form-content </p> </td> 
   <td colname="col2"> <p>自動完成 </p> </td> 
   <td colname="col3"> <p>插入搜尋表單的內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javascript </p> </td> 
   <td colname="col2"> <p>自動完成 </p> </td> 
   <td colname="col3"> <p>JavaScript以自動完成。 將此節點盡量放在頁面上。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 建議 {#section_2899FACB9AD84F60B3687C1B4EF09E15}

客戶可以通過三種方式配置&#x200B;**[!UICONTROL Did You Mean]**&#x200B;功能：因無結果而建議、在沒有結果時自動搜尋第一個建議，或因低結果而建議（建議結果計數較高）。 所有建議都會產生結果。

此建議節點包含可產生成功查詢的詞語。 連結也會傳回，讓客戶可以跳至新查詢。

由於0個結果而建議的範例輸出：

```xml
    <suggestions> 
        <auto-searched>0</auto-searched> 
        <suggestions-low-results>0</suggestions-low-results> 
 <suggestion-item> 
     <link><![CDATA[?i=1;q=arcade;sp_cs=UTF-8;view=xml]]></link> 
     <word><![CDATA[arcade]]></word> 
 </suggestion-item>    
    </suggestions>
```

自動搜尋建議的範例輸出：

```xml
    <suggestions> 
        <auto-searched>1</auto-searched> 
        <orig-query><![CDATA[arcace]]></orig-query> 
        <suggestions-low-results>0</suggestions-low-results>         
    </suggestions> 
```

由於結果不佳而建議的範例輸出：

```xml
   <suggestions> 
        <auto-searched>0</auto-searched> 
        <suggestions-low-results>1</suggestions-low-results> 
 <suggestion-item> 
     <link><![CDATA[?i=1;q=coffee;sp_cs=UTF-8;view=xml]]></link> 
     <word><![CDATA[coffee]]></word> 
 </suggestion-item>  
    </suggestions> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>節點 </p> </th> 
   <th colname="col2" class="entry"> <p>父節點 </p> </th> 
   <th colname="col3" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>建議 </p> </td> 
   <td colname="col2"> <p>客戶成果 </p> </td> 
   <td colname="col3"> <p> 包含定義建議的子節點（如果有的話）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自動搜尋 </p> </td> 
   <td colname="col2"> <p>建議 </p> </td> 
   <td colname="col3"> <p> 如果存在，則指出網站搜尋／銷售是否因沒有結果而自動搜尋新詞。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>orig-query </p> </td> 
   <td colname="col2"> <p>建議 </p> </td> 
   <td colname="col3"> <p> 當網站搜尋／銷售自動搜尋第一個建議時，查詢節點中的使用者查詢會顯示所搜尋的關鍵字。 此節點顯示原始查詢詞。 結合兩者，讓客戶建立「搜尋街機而非賣場」等結構。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>建議——低結果 </p> </td> 
   <td colname="col2"> <p>建議 </p> </td> 
   <td colname="col3"> <p>如果存在，則指出網站搜尋／銷售是否因為目前的搜尋詞產生低結果而提出建議，而建議產生高得多的結果。 這兩個臨界值可在<span class="uicontrol"> Did You Mean </span>中設定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>建議項目 </p> </td> 
   <td colname="col2"> <p>建議 </p> </td> 
   <td colname="col3"> <p>包含0-n個節點，表示各種建議。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>建議項目 </p> </td> 
   <td colname="col3"> <p>包含建立建議詞語連結的路徑。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>詞 </p> </td> 
   <td colname="col2"> <p>建議項目 </p> </td> 
   <td colname="col3"> <p> 包含建議的字詞。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範本 {#section_1E2BB2F274B04F5491A4CCCC38F507BD}

支援根據結果切換客戶搜尋體驗的功能。 其中部分包括在不同範本之間切換搜尋結果的不同版面。 例如，您可能有一個範本，其中包含許多產品的格線檢視。 或者，當顯示具有更多詳細資料的單一結果時，您可能會有「精選」範本。 當搜尋未產生任何結果時，您也可能有「無結果」範本。 模板節點指示使用哪個模板來顯示搜索結果。

範例範本：

```xml
<template><![CDATA[grid]]></template>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>節點 </p> </th> 
   <th colname="col2" class="entry"> <p>父節點 </p> </th> 
   <th colname="col3" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>template </p> </td> 
   <td colname="col2"> <p>客戶成果 </p> </td> 
   <td colname="col3"> <p>指示用於顯示搜索結果的模板的名稱。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 區域{#section_26C4A947E7B1474A8E37D86D9579B93E}

區域是頁面中可由業務規則開啟或關閉的部分。 區域可包含任何內容，包括但不限於Facet、搜尋、階層連結、靜態內容。 客戶網頁上的區域應與網站搜尋／銷售對應至相同的區域。

區域節點示例：

```xml
    <zones> 
        <zone> 
            <name><![CDATA[brand-facet]]></name> 
            <display>1</display> 
        </zone> 
    </zones> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>節點 </p> </th> 
   <th colname="col2" class="entry"> <p>父節點 </p> </th> 
   <th colname="col3" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>區域 </p> </td> 
   <td colname="col2"> <p>客戶成果 </p> </td> 
   <td colname="col3"> <p>包含0-n個區域。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>區域 </p> </td> 
   <td colname="col2"> <p>區域 </p> </td> 
   <td colname="col3"> <p> 單個區域節點。 您可以有多個區域節點。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>名稱 </p> </td> 
   <td colname="col2"> <p>區域 </p> </td> 
   <td colname="col3"> <p>區域的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>顯示 </p> </td> 
   <td colname="col2"> <p>1或0，指示是否顯示或隱藏與區域名稱對應的區域。 </p> </td> 
   <td colname="col3"> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範例 {#reference_64B7D8D228AF4B8D90EDF4DE507B0F84}

在虛構網站（稱為Geometrixx）上*搜尋的範例輸出，以及用來產生範例輸出的範例簡報範本。

* [輸出範例](../c-appendices/c-guidedsearchoutput.md#section_515C000A18B847D59097D0A9CCC02636)
* [範例簡報範本](../c-appendices/c-guidedsearchoutput.md#section_AD42571DFB88491AA7F0FDF0929EBE97)

## 輸出示例{#section_515C000A18B847D59097D0A9CCC02636}

在虛構網站Geometrixx上*搜尋的輸出範例。

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes" ?> 
<customer-results> 
    <query> 
        <user-query><![CDATA[*]]></user-query> 
 <lower-results><![CDATA[1]]></lower-results> 
 <upper-results><![CDATA[12]]></upper-results> 
 <total-results><![CDATA[1337]]></total-results> 
    </query> 
 
    <custom-fields> 
 
        <custom-field name="seo-search-title"><![CDATA[Geometrixx Search Results]]></custom-field> 
        <custom-field name="seo-search-keywords"><![CDATA[]]></custom-field> 
    </custom-fields> 
 
    <menus> 
 
        <menu> 
           <name>sort</name>

             <item selected="true"> 
 
          <label><![CDATA[Relevance]]></label> 
          <value><![CDATA[relevance]]></value> 
          <link><![CDATA[ ]]></link> 
             </item>

             <item> 
          <label><![CDATA[Lowest Price]]></label> 
          <value><![CDATA[Price]]></value> 
          <link><![CDATA[?i=1;q=*;sort=Price;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item>

             <item> 
          <label><![CDATA[Highest Price]]></label> 
          <value><![CDATA[Price_r]]></value> 
          <link><![CDATA[?i=1;q=*;sort=Price_r;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item>

             <item> 
          <label><![CDATA[Brand]]></label> 
          <value><![CDATA[brand]]></value> 
          <link><![CDATA[?i=1;q=*;sort=brand;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item>

        </menu> 
        <menu> 
            <name><![CDATA[ss_head_nav]]></name>

                    <label><![CDATA[WOMEN'S]]></label> 
      <value><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1;i=1;m_ss_head_nav=WOMEN'S]]></link>

                    <label><![CDATA[MEN'S]]></label> 
      <value><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></value> 
      <link><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></link>

                    <label><![CDATA[JEWELRY & ACCESSORIES]]></label> 
      <value><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1]]></value> 
      <link><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1;i=1;m_ss_head_nav=JEWELRY+%26+ACCESSORIES]]></link>

                    <label><![CDATA[BEAUTY & FRAGRANCE]]></label> 
      <value><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=BEAUTY+%26+FRAGRANCE]]></link>

                    <label><![CDATA[GIFTS & HOME]]></label> 
      <value><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=GIFTS+%26+HOME]]></link>

                    <label><![CDATA[CHILDREN & TOYS]]></label> 
      <value><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=CHILDREN+%26+TOYS]]></link>

                    <label><![CDATA[ELECTRONICS]]></label> 
      <value><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=ELECTRONICS]]></link>

        </menu> 
    </menus> 
 
    <breadcrumbs> 
  <breadcrumb> 
            <name><![CDATA[default]]></name> 
       
  <breadcrumb-item> 
    <link><![CDATA[?i=1;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></link> 
    <value><![CDATA[*]]></value> 
                        <label><![CDATA[]]></label> 
   </breadcrumb-item> 
          
   </breadcrumb> 
 
    </breadcrumbs> 
 
    <suggestions> 
        <auto-searched>0</auto-searched> 
         
        <suggestions-low-results>0</suggestions-low-results> 
         
    </suggestions> 
 
    <pagination> 
        <total-pages><![CDATA[112]]></total-pages> 
 
        <pages> 
     <page position="first"><![CDATA[]]></page> 
     <page position="last"><![CDATA[?i=1;page=112;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
      
     <page position="next"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="1" selected="true"><![CDATA[?i=1;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="2"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="3"><![CDATA[?i=1;page=3;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="4"><![CDATA[?i=1;page=4;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="5"><![CDATA[?i=1;page=5;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

        </pages> 
    </pagination> 
 
    <facets>  
         
     <facet-item> 
         <facet-title><![CDATA[Department]]></facet-title> 
                <selected>0</selected>

      <facet-value> 
           
              <label><![CDATA[Womens]]></label> 
 
       <link><![CDATA[?i=1;q=*;q1=Womens;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[219]]></count> 
                         
      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Mens]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Mens;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[202]]></count> 
                         
      </facet-value> 
   
      <facet-value>

              <label><![CDATA[Beauty &amp; Fragrance]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Beauty+%26+Fragrance;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[169]]></count> 
                         
      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Children &amp; Toys]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Children+%26+Toys;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[209]]></count> 
                         
      </facet-value>

      <facet-value> 
           
              <label><![CDATA[Electronics &amp; Toys]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Electronics+%26+Toys;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[200]]></count> 
                         
      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Gifts &amp; Home]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Gifts+%26+Home;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[156]]></count>

      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Jewelry &amp; Accessories]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Jewelry+%26+Accessories;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[182]]></count> 
                         
      </facet-value> 
   
      </facet-item> 
  
    </facets> 
 
    <results> 
        <result-set> 
            <name><![CDATA[default]]></name> 
               
         <result> 
                    <field name="index"><![CDATA[1]]></field> 
      <field name="brand"><![CDATA[Citizens]]></field> 
      <field name="price"><![CDATA[149]]></field> 
      <field name="foundIn"><![CDATA[Womens,  
            Apparel,  
          Denim]]></field> 
         </result>   
        
         <result> 
 
                    <field name="index"><![CDATA[2]]></field> 
      <field name="brand"><![CDATA[One For All]]></field> 
      <field name="price"><![CDATA[145]]></field> 
      <field name="foundIn"><![CDATA[Womens,  
            Apparel,  
          Denim]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[3]]></field> 
      <field name="brand"><![CDATA[Citizens]]></field> 
      <field name="price"><![CDATA[208]]></field> 
 
      <field name="foundIn"><![CDATA[Womens,  
            Apparel,  
          Denim]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[4]]></field> 
      <field name="brand"><![CDATA[Vera Watson]]></field> 
      <field name="price"><![CDATA[850]]></field> 
      <field name="foundIn"><![CDATA[Womens,  
            Dresses,  
          Day]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[5]]></field> 
 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[195]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[6]]></field> 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[80]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[7]]></field> 
      <field name="brand"><![CDATA[Petrol]]></field> 
      <field name="price"><![CDATA[85]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[8]]></field> 
      <field name="brand"><![CDATA[Woolberry]]></field> 
 
      <field name="price"><![CDATA[280]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[9]]></field> 
      <field name="brand"><![CDATA[Petrol]]></field> 
      <field name="price"><![CDATA[149]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
 
                    <field name="index"><![CDATA[10]]></field> 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[55]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[11]]></field> 
      <field name="brand"><![CDATA[Petrol]]></field> 
      <field name="price"><![CDATA[45]]></field> 
 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[12]]></field> 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[47]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
      
        </result-set>   
    </results>

    <banners> 
         
            <banner> 
                <area><![CDATA[top]]></area> 
                <content><![CDATA[<div style="color:#70A100">We have custom shipping</div>]]></content> 
            </banner>

    </banners> 
 
    <zones> 
        <zone> 
 
            <name><![CDATA[brand-facet]]></name> 
            <display>1</display> 
        </zone> 
    </zones> 
 
    <search-form> 
        <include-tnt-mbox>1</include-tnt-mbox> 
        <autocomplete> 
 
            <enabled>1</enabled> 
            <css><![CDATA[<link rel="stylesheet" type="text/css" href="https://content.t1.atomz.com/sp10043554/stage/autocomplete_styles.css?sp_js_param=2" /> 
]]></css> 
            <form-content><![CDATA[<div id="autocomplete"></div> 
<input type="hidden" name="sp_staged" id="sp_staged" value="1" /> 
]]></form-content> 
            <javascript><![CDATA[<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/utilities/utilities.js"></script> 
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/datasource/datasource-min.js"></script> 
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/autocomplete/autocomplete-min.js"></script> 
<script type="text/javascript" src="https://content.t1.atomz.com/sp10043554/stage/autocomplete_data.js?sp_js_param=3"></script>]]></javascript> 
        </autocomplete> 
    </search-form> 
 
</customer-results> 
```

## 演示模板示例{#section_AD42571DFB88491AA7F0FDF0929EBE97}

以下是用於產生上述範例輸出的範例簡報範本。

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes" ?> 
<customer-results> 
    <query> 
        <user-query><![CDATA[<guided-query-param gsname="q" />]]></user-query> 
 <lower-results><![CDATA[<guided-results-lower>]]></lower-results> 
 <upper-results><![CDATA[<guided-results-upper>]]></upper-results> 
 <total-results><![CDATA[<guided-results-total>]]></total-results> 
    </query> 
 
    <custom-fields> 
        <custom-field name="seo-search-title"><![CDATA[Geometrixx Search Results]]></custom-field> 
        <custom-field name="seo-search-keywords"><![CDATA[<guided-general-field gsname="default" field="seo_search_keywords"/>]]></custom-field> 
    </custom-fields> 
 
    <menus> 
 
        <menu> 
           <name>sort</name> 
     <guided-menu gsname="sort"> 
         <guided-if-menu-item-selected> 
             <item selected="true"> 
          <label><![CDATA[<guided-menu-item-label />]]></label> 
          <value><![CDATA[<guided-menu-item-value />]]></value> 
          <link><![CDATA[ ]]></link> 
             </item> 
        <guided-else-menu-item-selected> 
             <item> 
          <label><![CDATA[<guided-menu-item-label />]]></label> 
          <value><![CDATA[<guided-menu-item-value />]]></value> 
          <link><![CDATA[<guided-menu-item-path />]]></link>     
             </item> 
        </guided-if-menu-item-selected> 
    </guided-menu> 
        </menu> 
        <menu> 
            <name><![CDATA[ss_head_nav]]></name> 
            <guided-menu gsname="ss_head_nav"> 
                <guided-if-menu-item-selected> 
                    <item selected="true"> 
                    <label><![CDATA[<guided-menu-item-label />]]></label> 
      <value><![CDATA[<guided-menu-item-value />]]></value> 
      <link><![CDATA[<guided-menu-item-path />]]></link> 
                <guided-else-menu-item-selected> 
                    <label><![CDATA[<guided-menu-item-label />]]></label> 
      <value><![CDATA[<guided-menu-item-value />]]></value> 
      <link><![CDATA[<guided-menu-item-path />]]></link> 
                </guided-if-menu-item-selected> 
            </guided-menu>  
        </menu> 
    </menus> 
 
    <breadcrumbs> 
  <breadcrumb> 
            <name><![CDATA[default]]></name> 
      <guided-breadcrumb gsname="default"> 
  <breadcrumb-item> 
    <link><![CDATA[<guided-breadcrumb-path gsname="goto">]]></link> 
    <value><![CDATA[<guided-breadcrumb-value />]]></value> 
                        <label><![CDATA[<guided-breadcrumb-label>]]></label> 
   </breadcrumb-item> 
         </guided-breadcrumb> 
   </breadcrumb> 
    </breadcrumbs> 
 
    <suggestions> 
        <auto-searched><guided-if-suggestion-autosearch>1<guided-else-suggestion-autosearch>0</guided-if-suggestion-autosearch></auto-searched> 
        <guided-if-suggestion-autosearch><orig-query><![CDATA[<guided-suggestion-original-query/>]]></orig-query></guided-if-suggestion-autosearch> 
        <suggestions-low-results><guided-if-suggestion-low-results>1<guided-else-suggestion-low-results>0</guided-if-suggestion-low-results></suggestions-low-results> 
        <guided-suggestions> 
     <suggestion-item> 
         <link><![CDATA[<guided-suggestion-path />]]></link> 
  <word><![CDATA[<guided-suggestion />]]></word> 
     </suggestion-item> 
 </guided-suggestions> 
    </suggestions> 
 
    <pagination> 
        <total-pages><![CDATA[<guided-page-total />]]></total-pages> 
        <pages> 
     <page position="first"><![CDATA[<guided-page-path gsname="first" />]]></page> 
     <page position="last"><![CDATA[<guided-page-path gsname="last" />]]></page> 
     <guided-if-page-prev><page position="prev"><![CDATA[<guided-page-path gsname="prev" />]]></page></guided-if-page-prev> 
     <guided-if-page-next><page position="next"><![CDATA[<guided-page-path gsname="next" />]]></page></guided-if-page-next> 
     <guided-if-page-viewall><page position="viewall"><![CDATA[<guided-page-path gsname="viewall" />]]></page></guided-if-page-viewall> 
     <guided-if-page-viewpages><page position="viewall"><![CDATA[<guided-page-path gsname="viewpages" />]]></page></guided-if-page-viewpages> 
 
     <guided-pages> 
                <guided-if-page-selected><page position="<guided-page-number />" selected="true"><![CDATA[<guided-page-path />]]></page> 
  <guided-else-page-selected><page position="<guided-page-number />"><![CDATA[<guided-page-path />]]></page> 
  </guided-if-page-selected> 
     </guided-pages> 
        </pages> 
    </pagination> 
 
    <facets>  
        <guided-facet gsname="leveli"> 
     <facet-item> 
         <facet-title><![CDATA[Department]]></facet-title> 
                <selected><guided-if-facet-selected>1<guided-else-facet-selected>0</guided-if-facet-selected></selected> 
                <guided-if-facet-selected><undo-link><![CDATA[<guided-facet-undo-path gsname="leveli">]]></undo-link></guided-if-facet-selected> 
  <guided-facet-values> 
      <facet-value> 
          <guided-if-facet-value-selected><selected><![CDATA[true]]></selected></guided-if-facet-value-selected> 
              <label><![CDATA[<guided-facet-value>]]></label> 
       <link><![CDATA[<guided-facet-value-path />]]></link> 
       <count><![CDATA[<guided-facet-count>]]></count> 
                        <guided-if-facet-value-selected><undolink><![CDATA[<guided-facet-value-undo-path />]]></undolink></guided-if-facet-value-selected> 
      </facet-value> 
  </guided-facet-values> 
      </facet-item> 
 </guided-facet> 
    </facets> 
 
    <results> 
        <result-set> 
            <name><![CDATA[default]]></name> 
            <guided-results gsname="default">   
         <result> 
                    <field name="index"><![CDATA[<guided-result-index />]]></field> 
      <field name="brand"><![CDATA[<guided-result-field gsname="brand" />]]></field> 
      <field name="price"><![CDATA[<guided-result-field gsname="price" />]]></field> 
      <field name="foundIn"><![CDATA[<guided-if-result-field gsname="leveli"><!--tmpl_var name='leveli'-->, </guided-if-result-field> 
            <guided-if-result-field gsname="levelii"><!--tmpl_var name='levelii'-->, </guided-if-result-field> 
          <guided-if-result-field gsname="leveliii"><!--tmpl_var name='leveliii'--></guided-if-result-field>]]></field> 
         </result>   
     </guided-results> 
        </result-set>   
    </results> 
 
    <guided-if-recent-searches> 
    <recent-searches> 
        <clear-link><guided-recent-searches-clear-path/></clear-link> 
        <guided-recent-searches> 
            <recent-search> 
                <link><guided-recent-searches-path></link> 
                <label><guided-recent-searches-value></label> 
            <recent-search> 
        </guided-recent-searches> 
    </recent-searches> 
    </guided-if-recent-searches> 
 
    <banners> 
        <guided-if-banner-set gsname="top"> 
            <banner> 
                <area><![CDATA[top]]></area> 
                <content><![CDATA[<guided-banner gsname="top">]]></content> 
            </banner> 
        </guided-if-banner-set> 
        <guided-if-banner-set gsname="bottom"> 
            <banner> 
                <area><![CDATA[bottom]]></area> 
                <content><![CDATA[<guided-banner gsname="bottom">]]></content> 
            </banner> 
        </guided-if-banner-set> 
    </banners> 
 
    <zones> 
        <zone> 
            <name><![CDATA[brand-facet]]></name> 
            <display><guided-if-zone gsname="brand-facet">1<guided-else-zone>0</guided-if-zone></display> 
        </zone> 
    </zones> 
 
    <search-form> 
        <include-tnt-mbox><guided-if-tnt-business-rules>1<guided-else-tnt-business-rules>0</guided-if-tnt-business-rules></include-tnt-mbox> 
        <autocomplete> 
            <enabled><guided-if-autocomplete>1<guided-else-autocomplete>0</guided-if-autocomplete></enabled> 
            <css><![CDATA[<guided-ac-css/>]]></css> 
            <form-content><![CDATA[<guided-ac-form-content/>]]></form-content> 
            <javascript><![CDATA[<guided-ac-javascript/>]]></javascript> 
        </autocomplete> 
    </search-form> 
 
</customer-results> 
```

