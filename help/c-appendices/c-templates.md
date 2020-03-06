---
description: 'null'
seo-description: 'null'
seo-title: 範本
solution: Target
title: 範本
topic: Appendices,Site search and merchandising
uuid: 78299032-dc23-4dfe-b68f-cd57b2b6d7d8
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a

---


# 範本{#templates}

## 範本 {#concept_A5CFB6BD805D49459A96219AF1B17842}

## 簡報範本標籤 {#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64}

簡報範本的網站搜尋／銷售標籤和屬性清單。


簡報範本是HTML檔案，包含網站搜尋／銷售所定義的簡報範本標籤。 這些標籤表示客戶看到的搜索結果的格式。

請參閱 [關於範本](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5)。

您可從下列簡報標籤群組中選取：

* [聲明](../c-appendices/c-templates.md#section_82C5CA734D2941EB858FEFE3B695D2EC)
* [結果](../c-appendices/c-templates.md#section_06F249C9F6AE4B0F8C32117E19DCC905)
* [刻面](../c-appendices/c-templates.md#section_EA4C5678D5864B89BAB4D0DFE62A4624)
* [階層連結](../c-appendices/c-templates.md#section_9B39B71FA6EC49FA8D88AD8A3BA987F7)
* [功能表](../c-appendices/c-templates.md#section_1D489ADF041F4351A66E5D5742125CA8)
* [帕格納夫](../c-appendices/c-templates.md#section_2EE397635C514BBC8D668278EA314F35)
* [最近搜尋](../c-appendices/c-templates.md#section_8CD907521F584257B475595B01A5964B)
* [您的意思是](../c-appendices/c-templates.md#section_C1EB3B9D8E1242798A6E04609D1E3543)
* [自動完成](../c-appendices/c-templates.md#section_897316BEE1454E839A56B565CA4AF018)
* [商店](../c-appendices/c-templates.md#section_A33E25DB5E67404A823BD9618665B773)
* [區域](../c-appendices/c-templates.md#section_B9B3179E000C42D492E1541F2FE44CB5)
* [循環指示燈](../c-appendices/c-templates.md#section_387322CA0AA843A2ACF2795C328673E9)
* [其他語言](../c-appendices/c-templates.md#section_BFE8DC98E26F4D7BB60FEC54D9A5DC6C)

## 聲明 {#section_82C5CA734D2941EB858FEFE3B695D2EC}

聲明是特殊的引導宣告標籤，您可在頂層簡報範本的頂端加以設定。 將忽略任何後續聲明，包括包含的模板中的聲明。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-content-type-header content="content-type"&gt; </span> </p> </td> 
   <td colname="col2"> <p>依預設，簡報範本會以mime類型的text/html傳回。 您可以變更此標籤使用的內容類型。 </p> <p>在您的簡報範本中盡可能聲明此標籤。 請勿使用此標籤在同一行上新增其他文字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-xml-declare [charset="charset"&gt; </span> </p> </td> 
   <td colname="col2"> <p> 如果您要傳回XML，可使用此標籤來建立XML聲明。 將此標籤設為簡報範本中的第一行。 使用此標籤時，除非您在第一行中以 <span class="codeph"> &lt;guided-content-type-header&gt;覆寫內容類型，否則content-type會自動設 </span> 為text/xml。 如果您未指定字元集，則預設為UTF-8。 此標籤會在XML檔案中產生下列輸出： </p> <p> <span class="codeph"> &lt;?xml version="1.0" enconding="charset-name" standalone="yes" ?&gt; </span> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 結果 {#section_06F249C9F6AE4B0F8C32117E19DCC905}

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng 1/31/13--> <span class="codeph"> &lt;guided-results [gsname="searchname"]&gt;&lt;/guided-results&gt; </span> </p> </td> 
   <td colname="col2"> <p>引導結果標籤定義結果循環的邊界。 通過指定 <span class="codeph"> gsname屬性，可以訪問任何結 </span> 果集。 如果未 <span class="codeph"> 提供 </span> gsname，則會顯示預設搜尋結果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng 1/31/13--> <span class="codeph"> &lt;guided-result-link [gsname="fieldname"] [attr="value"+&gt;&lt;/guided-result-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>若要建立指定結果的連結，請使 <span class="codeph"> 用guided-result-link標 </span> 記。 定義 <span class="codeph"> gsname屬 </span> 性後，您就可以使用索引中的欄位，而非參照"search-url"的標準"loc"標籤。 任何其他屬性（例如類別和目標）也可以傳遞，這些屬性會輸出到產生的錨點標籤中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng 1/31/13--> <span class="codeph"> &lt;guided-result-img gsname="fieldname" [attr="value"+&gt; </span> </p> </td> 
   <td colname="col2"> <p>&lt;guided-result-img&gt;標 <span class="codeph"> 簽可協助建立影像標籤，而非將變數內嵌在原始 </span> img標 <span class="codeph"></span> 記中。 </p> <p>指定gsname屬性中用於影像路徑的 <span class="codeph"> 欄 </span> 位。 結果會是 <span class="codeph"> img標 </span> 簽，其中包含您定義、傳遞的任何標準HTML屬性。 所以，下面的例子是： </p> <p> <code class="syntax html"> &lt;guided-result-img&nbsp;gsname="thumbnail" 
      &nbsp;class="thumb"&nbsp;border="0"/&gt; </code> </p> <p>becomes: </p> <p> <code class="syntax html"> &lt;img&nbsp;src="prod8172.jpg"&nbsp;class="thumb" 
      &nbsp;border="0"/&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 1/31/13; search-eng version does not have [escape...] Added ijson on 8/28/2015--> <span class="codeph"> &lt;guided-result-field gsname="fieldname" [escape="html|url|js|json|json|0"/&gt; </span> </p> </td> 
   <td colname="col2"> <p> 結果中顯示的任何資訊都會顯示為 <span class="codeph"> &lt;guided-result-field&gt;標籤 </span> (使用自動產生標籤(例如 <span class="codeph"> &lt;guided-result-img&gt;標籤)除外 </span> )。 </p> <p>在 <span class="codeph"> gsname中指定「搜索索引」欄位的名 </span>稱。 傳遞的確切字串會在範本中輸出。 </p> <p>如果希望此欄位與傳輸模板中指定的欄位進行不同的逸出，則可以指定逸出選項。 </p> <p>此編碼會套用在傳輸範本中指定的任何編碼上。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <span class="codeph"> &lt;guided-if[-not]-result-field gsname="fieldname&gt;&lt;/guided-if-result-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果特定欄位中有內容要顯示，則此組條件標籤為true。 如果沒有內容，則條件為false。 您可以使用標籤來決定是否顯示周圍的HTML（如果不存在值，或顯示不同的影像），依此類推。 </p> <p> <code class="syntax html"> &lt;guided-if-result-field&nbsp;gsname="thumbnail"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-result-img&nbsp;gsname="thumbnail"&nbsp;class="thumb"&nbsp;/&gt; 
      &lt;guided-else-result-field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;img&nbsp;src="nothumb.jpg"&nbsp;class="nothumb"&nbsp;/&gt; 
      &lt;/guided-if-result-field&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <code> &lt;guided-if[-not]-result-wrap&gt; 
      &lt;guided-else-result-wrap&gt; 
      &lt;/guided-if[-not]-result-wrap&gt; </code> </p> </td> 
   <td colname="col2"> <p>在列中顯示結果時，此標籤用於標識當前結果是否標籤列的結尾。 </p> <p>當布爾條件為true時，會將HTML添加到結果的末尾，以完成行並啟動新行。 當是最後一行時，不會啟動新行。 </p> <p>請參 <span class="codeph"> 閱&lt;guided-if-not-last&gt;以 </span> 進一步瞭解該標籤。 </p> <p> <code class="syntax html"> &lt;guided-if-result-wrap&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/div&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-not-last&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;div&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-not-last&gt; 
      &nbsp;&lt;/guided-if-result-wrap&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-results-found [gsname="searchname"]/&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果後端搜尋請求傳回結果，則傳回1；如果未傳回，則傳回0。 如果未指 <span class="codeph"> 定gsname </span> ，則標籤會假定主搜索。 此標籤對於將邏輯傳遞至JavaScript常式很有用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-results-total [gsname="searchname"]/&gt; </span> </p> </td> 
   <td colname="col2"> <p>傳回指定結果集中的結果總數。 未指定 <span class="codeph"> gsname時，假 </span> 設預設搜索。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-results-lower [gsname="searchname"/&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回指定結果集的頁面上較低結果的結果編號。 未指定 <span class="codeph"> gsname時，假 </span> 設預設搜索。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-results-upper [gsname="searchname"]/&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回指定結果集頁面上上方結果的結果編號。 未指定 <span class="codeph"> gsname時，假 </span> 設預設搜索。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> 

    &amp;lt;/guided-if[-not]-results-found&amp;gt;&lt;/code> &lt;/p> &lt;/td>
<td colname="col2"> <p>在找到結果時顯示內容。 或者，找不到結果時，不顯示結果HTML。 </p> <p> <code class="syntax html"> &lt;guided-if-results-found&nbsp;gsname="products"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-results&nbsp;gsname="products"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;... 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-results&gt; 
      &lt;guided-else-results-found&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;No&nbsp;results&nbsp;were&nbsp;found. 
      &lt;/guided-if-results-found&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-title/&gt; </span> </p> </td> 
   <td colname="col2"> <p>&lt;guided-result-title&gt;標 <span class="codeph"> 簽提供使用 </span> &lt;title&gt;傳輸標籤指定的標題傳輸範本 <span class="codeph"></span> 欄位值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-description/&gt; </span> </p> </td> 
   <td colname="col2"> <p>&lt;guided-result-description&gt;標 <span class="codeph"> 簽提供使用 </span> &lt;description&gt;傳輸標籤指定的description傳輸範本欄 <span class="codeph"></span> 位值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-loc/&gt; </span> </p> </td> 
   <td colname="col2"> <p>&lt; <span class="codeph"> guided-result-loc&gt; </span> tag gives value of loc transport template field specified with <span class="codeph"> &lt;loc&gt; </span> transport tag. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;/guided-if-result-field&amp;gt;&lt;/code> &lt;/p> &lt;/td>
<td colname="col2"> <p>如果特定欄位中有要顯示的內容，則為true。 如果沒有內容，則條件為false。 使用標籤來決定是否顯示周圍的HTML（如果沒有值，或是顯示不同的影像），依此類推。 </p> <p> <code class="syntax html"> &lt;guided-if-result-field&nbsp;gsname="thumbnail"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-result-img&nbsp;gsname="thumbnail"&nbsp;class="thumb"/&gt; 
      &lt;guided-else-result-field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;img&nbsp;src="nothumb.jpg"&nbsp;class="nothumb"/&gt; 
      &lt;/guided-if-result-field&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-attribute-table gsname="tablename"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此標籤提供在傳輸模板中定義的具有 <span class="codeph"> &lt;attribute_table&gt;傳輸標籤的循環 </span> 屬性表。 有 <span class="codeph"> &lt;guided-result-attribute-table-field&gt;標籤可顯 </span> 示屬性表欄位值。 此外，您也可以在回圈內使 <span class="codeph"> 用簡單的引導結果欄 </span> 位標籤來顯示其他結果欄位。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-attribute-table-field gsname="fieldname" [escape="html|url|js|json|0"/&gt; </span> </p> </td> 
   <td colname="col2"> <p>顯示在傳輸模板中定義的屬性表欄位。 </p> <p> 

    ...
    
    &amp;lt;
    
    &amp;lt;guided-result-attribute-table&amp;nbsp;gsname=&quot;downloads&quot;&amp;gt;
    &amp;nbsp;&amp;nbsp;&amp;li&amp;
    &amp;nbsp;&amp;nbsp;&amp;am;nbsp;&lt;a&amp;nbsp;href=&quot;&amp;lt;guided-result-attribute-table-field&amp;nbsp;gsname=&quot;download_link&quot;&amp;nbsp;
    &amp;gt;&amp;nbsp;&amp;nbsp;&amp;nbsp;nbsp;bsp;&amp;nbsp;&amp;lt;guided-result-attribute-table-field&amp;nbsp;gsname=&quot;download_title&quot;&amp;nbsp;
    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;lt;&amp;am;nbsp;(&amp;mp; lt; guided-result-field&amp; nbsp; gsname=&quot;title&quot;/&amp;;gt;)
    &amp;&amp;mp; nbsp;nbsp;&amp;mp;lt;/li&amp;mp;
    
    
    
    
    ;lt;
    
    &amp;lt;/guided-results&amp;gt;&lt;/code> &lt;/p> &lt;/td>
</tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release in October 2014--> <span class="codeph"> &lt;guided-trace [gsname="searchname"]/&gt; </span> </p> </td> 
   <td colname="col2"> <p>將追蹤資料中找到的追蹤資訊，輸出給定搜尋的傳輸範本所輸出JSON資料的一般區段。 </p> <p>如果未提供搜尋名稱，則 <span class="codeph"> 會假 </span> 設為預設。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release on October 30, 2014)--> <span class="codeph"> &lt;guided-result-trace/&gt; </span> </p> </td> 
   <td colname="col2"> <p>輸出目前搜尋結果之傳輸範本所輸出之JSON資料的結果&gt;追蹤資訊中找到的JSON內容。 </p> <p>此標籤僅在&lt;guided-results&gt; <span class="codeph"> &lt;/guided-results&gt;循環中有 </span> 效。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 刻面 {#section_EA4C5678D5864B89BAB4D0DFE62A4624}

Facet是導覽元件，可讓您深入探索搜尋結果。 您可以使用Facet標籤在您的簡報範本上顯示各種Facet。 您可依名稱參照Facet。

請參閱 [關於刻面](../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5)。

請參閱[關於 Facet 軌](../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB)。

請參 [閱關於動態面](../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899)。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 02/27/2014--> <span class="codeph"> &lt;guided-dynamic-facets&gt;&lt;/guided-dynamic-facets&gt; </span> </p> </td> 
   <td colname="col2"> 
    <!--NEW 2/2/2014--> <p>特定搜尋之任何動態Facet的循環內容。 </p> <p>編輯 <span class="codeph"> &lt;guided-facet&gt; </span> presentation範本標籤，讓gsname屬性由 <span class="codeph"> &lt;guided-dynamic-facets&gt;循環內容自 </span> 動提供。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-display-name gsname=" <span class="varname"> facetname </span>"/&gt; </span> </p> </td> 
   <td colname="col2"> <p>傳回Facet的顯示標籤。 </p> <p>如果Facet在傳輸范 <span class="codeph"> 本上使用&lt;display-name&gt; </span> 標籤，則該標籤的內容會變成標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-rail&gt;&lt;/guided-facet-rail&gt; </span> </p> </td> 
   <td colname="col2"> <p> 定義表示範本的區段，該區段用作Facet邊欄中每個Facet的重複圖樣。 </p> <p> 屬於Facet邊欄的每個Facet都會使用此區段來評估其輸出。 </p> <p>以下是Facet邊欄的範例： </p> <p> <code class="syntax html"> &lt;guided-facet-rail&gt; 
      &nbsp;&nbsp;&lt;guided-facet&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-display-name/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;... 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet&gt; 
      &nbsp;&nbsp;&lt;/guided-facet-rail&gt; </code> </p> <p>請注意，當在 <span class="codeph"> &lt;guided-facet-rail&gt;標籤內時，下列標籤不需要 </span><span class="codeph"></span> gsname屬性，因為值會在搜尋時動態決定，並會正確取代： </p> 
    <ul id="ul_5B5ACAFD2B8848DDB27471AB9DA7BE6E"> 
     <li id="li_5A07E78D51FE4708879DD742C877FFFF">引導Facet </li> 
     <li id="li_B875DCACD7AB4FC890A456A6939AB657">guided-facet-display-name </li> 
     <li id="li_B70450749E864DE7BA401E3CD6EF5EB3">guided-facet-total-count </li> 
     <li id="li_DECDF5EF6FF7454F86C236D322F2BFEA">引導-facet-undo-link </li> 
     <li id="li_176949227AC14E8CA643A419E10F7B5A">引導-Facet-undo-path </li> 
     <li id="li_B32D981281744462BC680F6EFEAC0069">引導-Facet-行為 </li> 
    </ul> <p>「Facet邊欄」( <span class="wintitle"> Facet Rail)頁 </span> 面上的排序標準會決定Facet的位置。 您可以從「排序刻面方法」下拉式清單中選擇排序順序。 </p> <p> 
     <!--NEW 02/27/2014-->此標籤可選擇接受 <span class="codeph"> _dynamic_facets的gsname屬性值 </span>，此值可為此搜尋的任何動態Facet提供循環內容。 此預先定義的Facet邊欄也會在Business Rules使用者介面中公開，以便在Facet邊欄「_dynamic_facets」中 <span class="codeph"> 將動作推播Facet X以定位Y </span>」。 </p> <p>請參閱<a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local">關於 Facet 軌</a>。 </p> <p>另請參閱 <a href="../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> 動態面 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match current search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet gsname=" <span class="varname"> facetname </span>" height=" 60px <span class="varname"> " width=" </span>120px <span class="varname"></span>"&gt;&lt;/guided-facet&gt; </span> </p> </td> 
   <td colname="col2"> <p>使用引 <span class="codeph"> 導Facet標 </span> 記來定義所有Facet標籤都與特定Facet相關的區域。 此標籤也是布林標籤，如果Facet中沒有值，則會隱藏所有內容。 在這種情況下，沒有輸出刻面值的點)。 </p> <p>高度和寬度屬性是可選的，尺寸以像素(px)指定。 「視覺化規則產生器」(VRB)會使用這兩個屬性，並在Facet隱藏時，將虛線方塊顯示為互動預留位置。 </p> <p> 當顯示名稱位於Facet中且Facet已隱藏時，名稱也會隱藏。 但是，如果名稱位於Facet外，則只有區域標籤或引導-if-facet-visible標籤包住它時，才 <span class="codeph"></span><span class="codeph"></span> 能隱藏名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-if[-not]-facet-long [gsname="facetname"]&gt;&lt;/guided-if[-not]-facet-long </span> </p> </td> 
   <td colname="col2"> <p>當Facet值數量超過設定中定義的長度臨界值時，此條件標籤為true。 當清單過長時，可使用它將Facet顯示為不同的UI元素（例如截斷的清單或捲動方塊）。 </p> <p> <code class="syntax xml"> &lt;guided-facet&nbsp;name="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-long&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;select&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-option&nbsp;/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/select&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-long&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-value-link&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-long&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>您也可以在命名的 <span class="codeph"> guided-facet區塊的上下文外使用此條件，方法是直接使用 </span> gsname屬 <span class="codeph"></span> 性來參照特定facet。 </p> <p> <code class="syntax html"> &lt;guided-if-facet-long&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;The&nbsp;category&nbsp;facet&nbsp;is&nbsp;very&nbsp;long! 
      &lt;/guided-if-facet-long&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-if[-not]-facet-selected [gsname="facetname"]&gt;&lt;/guided-if[-not]-facet-selected&gt; </span> </p> </td> 
   <td colname="col2"> <p>當Facet至少被點按一次且目前已選取Facet值時，此條件標籤為true。 它會用來顯示或隱藏HTML或gs標籤，視點按Facet而定。 </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;name="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This&nbsp;facet&nbsp;has&nbsp;been&nbsp;selected.&nbsp;&nbsp;You&nbsp;can&nbsp;no&nbsp;longer&nbsp;refine&nbsp;it. 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-value-link&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-selected&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>您也可以在命名的 <span class="codeph"> guided-facet區塊的上下文外使用此條件，方法是直接使用 </span> gsname屬 <span class="codeph"></span> 性來參照特定facet。 </p> <p> <code> &lt;guided-if-facet-selected&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;The&nbsp;category&nbsp;facet&nbsp;is&nbsp;selected! 
      &lt;/guided-if-facet-selected&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-if[-not]-facet-single [gsname="facetname"]&gt;&lt;/guided-if[-not]-facet-single&gt; </span> </p> </td> 
   <td colname="col2"> <p>當只有一個Facet值時，此條件標籤為true。 當Facet無法調整結果時，使用標籤來變更其顯示。 </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;name="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-single&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Facet&nbsp;is&nbsp;not&nbsp;refinable. 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-single&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-value-link&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-single&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>您也可以在命名的 <span class="codeph"> guided-facet區塊的上下文外使用此條件，方法是直接使用 </span> gsname屬 <span class="codeph"></span> 性來參照特定facet。 </p> <p> <code class="syntax html"> &lt;guided-if-facet-single&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;There&nbsp;is&nbsp;only&nbsp;one&nbsp;value&nbsp;in&nbsp;the&nbsp;category&nbsp;facet! 
      &lt;/guided-if-facet-single&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--Added 7/15/2014--> <span class="codeph"> &lt;guided-if[-not]-facet-multiselect [gsname="facetname"]&gt;&lt;/guided-if[-not]-facet-multiselect&gt; </span> </p> </td> 
   <td colname="col2"> <p>當Facet為多選時，此條件標籤為true。 使用標籤來變更&lt;guided-facet-rail&gt;或 <span class="codeph"> &lt;guided-dynamic-facets&gt;標籤內之Facet的顯 </span><span class="codeph"></span> 示。 </p> <p> 

    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;lt;guided-if-facet-multiselect&amp;gt;
    &amp;nbsp;...
    &amp;nbsp;&amp;lt;guided-else-facet-multiselect&amp;gt;
    &amp;nbsp;...
    &amp;nbsp;&amp;lt;/guided-if-facet-multiselect&amp;gt;
    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;...
    &amp; nbsp;&amp;nbsp;&amp;nbsp;&amp; lt;/guided-facet&amp;gt;
    &amp;nbsp;&amp;nbsp;&amp;lt;/guided-facet-rail&amp;gt&lt;/code> &lt;/p> &lt;/td>
</tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-values [gsname=" <span class="varname"> facetname </span>"]&gt;&lt;/guided-facet-values&gt; </span> </p> </td> 
   <td colname="col2"> <p>這是Facet值循環迭代器標籤。 您可在命名的guided-facet區塊的內容中 <span class="codeph"> 定義它， </span> 在此情況下，您可以省略 <span class="codeph"> gsname <span class="varname"></span></span>。 或者，您可以在任何引導 <span class="codeph"> Facet區塊外定義 </span> 它，但需要 <span class="codeph"> gsname <span class="varname"> 屬性來 </span></span> 識別要顯示的Facet值集。 </p> <p>您也可以使用此標籤，在命名的guided-facet區塊的上下文外顯 <span class="codeph"> 示facet </span> 值。 您可使用gsname屬性直接參照特 <span class="codeph"> 定 <span class="varname"></span></span> 刻面。 </p> <p> <code class="syntax html"> &lt;script&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;registerFacetValues('category',&nbsp;'&lt;guided-facet-values&nbsp;gsname="category"&gt;&lt;guided-facet-value/&gt;,&lt;/guided-facet-values&gt;'); 
      &lt;/script&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-value [escape="html|url|js|json|0"/&gt; </span> </p> </td> 
   <td colname="col2"> <p>輸出目前Facet值的字串。 </p> <p>依預設，此值為HTML逸出。 您可以使用逸出選項來變更值逸出的方式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-count/&gt; </span> </p> </td> 
   <td colname="col2"> <p>輸出與目前Facet值相符的結果數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-facet-value-link [attr="value"]+&gt;&lt;/guided-facet-value-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>在Facet值字串周圍建立連結，讓網站訪客按一下。 會自動產生路徑，以依目前的Facet值縮小結果。 它支援將任何屬性直接傳遞至錨點標籤。 </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-value-link&nbsp;class="facetlink"&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-value-link&gt; 
      &lt;/guided-facet-values&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> <code> &lt;guided-if-facet-value-selected&gt; 
      &lt;guided-else-facet- 
      value-selected&gt; 
      &lt;/guided-if-facet-value-selected&gt; </code> </p> </td> 
   <td colname="col2"> <p>變更當前選取多面值時的顯示。 如果它已經被選中，在大多數情況下，它不再可連結。 </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-value-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;b&gt;&lt;guided-facet-value/&gt;&lt;/b&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-value-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt;&nbsp;&nbsp;&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-value-selected&gt; 
      &lt;/guided-facet-values&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> 

    &amp;lt;/guided-if[-not]-facet-value-ghost&amp;gt;&lt;/code> &lt;/p> &lt;/td>
<td colname="col2"> <p>變更刻面值是重影值時的顯示。 當Facet值是重影值時，它通常以斜體文字顯示，以指出該值遺失或是「重影」。 </p> <p>以下程式碼摘錄是Facet區塊的範例： </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-value-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;b&gt;&lt;guided-facet-value&nbsp;/&gt;&nbsp;(&lt;guided-facet-count&nbsp;/&gt;)&lt;/b&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-value-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-value-ghost&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;i&gt;&lt;guided-facet-value&nbsp;/&gt;&nbsp;(0)&lt;/i&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-value-ghost&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&nbsp;class="link"&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-link&gt;&nbsp;(&lt;guided-facet-count&nbsp;/&gt;) 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-value-ghost&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-value-selected&gt; 
      &lt;/guided-facet-values&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-undo-link gsname=" <span class="varname"> facetname </span>"&gt;&lt;/guided-facet-undo-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>顯示指定Facet的還原連結。 如果有多選刻面，此連結會取消選取所有指定刻面的值。 為Facet命名。 如果Facet目前未選取，則連結是目前路徑。 </p> <p>以下是此標籤用法的範例： </p> <p> <code class="syntax html"> &lt;guided-if-facet-selected&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-undo-link&nbsp;gsname="category"&gt;Undo&nbsp;Category&lt;/guided-facet-undo-link&gt; 
      &lt;/guided-if-facet-selected&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <varname></varname> </p> </td> 
   <td colname="col2"> <p>當Facet值數量超過設定中定義的長度臨界值時，此條件標籤為true。 當清單過長時，使用它可將Facet顯示為不同的使用者介面元素（例如截斷的清單或捲動方塊）。 </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-long&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;div&nbsp;class="long_facet"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/div&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-long&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;div&nbsp;class="facet"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/div&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-long&gt; 
      &nbsp;&lt;/guided-facet&gt; </code> </p> <p>您也可以在命名的引導面區塊的上下文外使用此條件，方法是直接透過使用 <span class="codeph"> gsname </span> 屬性來參照特定面 <span class="codeph"> ，以 <span class="varname"></span></span> 便使用。 </p> <p> <code class="syntax html"> &lt;guided-if-facet-long&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The&nbsp;category&nbsp;facet&nbsp;is&nbsp;very&nbsp;long! 
      &lt;/guided-if-facet-long&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-facet-selected [gsname="facetname"]&gt; 
      &lt;guided-else-facet-selected&gt;&lt;/guided-if-facet-selected&gt; </code> </p> </td> 
   <td colname="col2"> <p>當Facet至少被點按一次且目前已選取Facet值時，此條件標籤為true。 它可用來顯示或隱藏HTML或gs標籤，視點按Facet而定。 </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This&nbsp;facet&nbsp;has&nbsp;been&nbsp;selected.&nbsp;&nbsp;You&nbsp;can&nbsp;no&nbsp;longer&nbsp;refine&nbsp;it. 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-selected&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>您也可以在命名的 <span class="codeph"> guided-facet區塊的上下文外使用此條件，方法是直接使用 </span> gsname屬 <span class="codeph"></span> 性來參照特定facet。 </p> <p> <code class="syntax html"> &lt;guided-if-facet-selected&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The&nbsp;category&nbsp;facet&nbsp;is&nbsp;selected! 
      &lt;/guided-if-facet-selected&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> <varname></varname> </p> </td> 
   <td colname="col2"> <p>當只有一個Facet值時，此條件標籤為true。 當Facet無法調整結果時，它可用來變更Facet的顯示。 </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-single&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Facet&nbsp;is&nbsp;not&nbsp;refinable. 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-single&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-single&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>您也可以在命名的引導面區塊的上下文外使用此條件，方法是直接透過使用 <span class="codeph"> gsname </span> 屬性來參照特定面 <span class="codeph"> ，以 <span class="varname"></span></span> 便使用。 </p> <p> <code class="syntax html"> &lt;guided-if-facet-single&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;There&nbsp;is&nbsp;only&nbsp;one&nbsp;value&nbsp;in&nbsp;the&nbsp;category&nbsp;facet! 
      &lt;/guided-if-facet-single&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> <varname></varname> </p> </td> 
   <td colname="col2"> <p>此條件可讓您檢查指定的Facet是否有任何值。 您可使用它來顯示另一個Facet，而非空的Facet。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>20 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-total-count gsname=" <span class="varname"> facetname </span>"/&gt; </span> </p> </td> 
   <td colname="col2"> <p>輸出在指定Facet內的結果總數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>21 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value gsname=" <span class="varname"> associated custom facet value </span>" [escape="html|url|js|json|0"/&gt; </span> </p> </td> 
   <td colname="col2"> <p>輸出與Facet相關聯的值的字串。 您可以有0或多個欄位與Facet相關聯。 具有關聯欄位非常少見，因此您可以配置傳輸模板。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>22 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-facet-value gsname=" <span class="varname"> associated custom facet value </span>"/&gt;&lt;guided-else-facet-value&gt;&lt;/guided-if-facet-value&gt; </span> </p> </td> 
   <td colname="col2"> <p>測試Facet值是否具有關聯欄位值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>23 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-link [attr=" <span class="varname"> value </span>"]+&gt;&lt;/guided-facet-link </span> </p> </td> 
   <td colname="col2"> <p>在Facet值字串周圍建立連結，讓客戶按一下。 會自動產生路徑，以依目前的Facet值縮小結果。 它支援將任何屬性直接傳遞至錨點標籤。 </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&nbsp;class="facetlink"&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &lt;/guided-facet-values&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>24 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-path [escape="html|url|js|json|0"/&gt; </span> </p> </td> 
   <td colname="col2"> <p>建立您自己的Facet值連結。 </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-lt/&gt;a&nbsp;href="&lt;guided-facet-value-path/&gt;"&lt;guided-gt/&gt;&lt;guided-facet-value/&gt;&lt;/a&gt; 
      &lt;/guided-facet-values&gt; </code> </p> <p>依預設，值為URL逸出。 不過，您可以透過逸出參數指定您要使用的逸出模式，以新增另一層編碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>25 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-children&gt;&lt;/guided-facet-value-children&gt; </span> </p> </td> 
   <td colname="col2"> <p>當 <span class="codeph"> &lt;guided-facet-values&gt;逐 </span> 步遍歷每個facet值時，此標籤會迭代嵌套Facet的所有子值。 在此標籤內，使用一般的Facet標籤來建立連結、建立還原連結及顯示Facet值。 此標籤必須位於 <span class="codeph"> &lt;guided-facet-values&gt;內，因 </span> 為它會巢狀循環。 </p> <p>使用此標籤的範例如下： </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&lt;guided-facet-link&nbsp;title='&lt;guided-facet-value&nbsp;/&gt;'&gt;&lt;guided-facet-value&nbsp;/&gt;&nbsp;(&lt;guided-facet-count&nbsp;/&gt;)&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&lt;guided-if-facet-value-has-children&gt; 
      &nbsp;&nbsp;&nbsp;&lt;guided-facet-value-children&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&nbsp;title='&lt;guided-facet-value&nbsp;/&gt;'&gt;&lt;guided-facet-value&nbsp;/&gt;&nbsp;(&lt;guided-facet-count&nbsp;/&gt;)&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&lt;/guided-facet-value-children&gt; 
      &nbsp;&nbsp;&lt;/guided-if-facet-value-has-children&gt; 
      &lt;/guided-facet-values&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>26 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-facet-value-has-children&gt; 
      &lt;guided-else-facet- 
      value-has-children&gt; 
      &lt;/guided-if-facet-value-has-children&gt; </code> </p> </td> 
   <td colname="col2"> <p>測試目前Facet值是否具有子值。 建議在使用 <span class="codeph"> &lt;guided-facet-value-children&gt;標籤前使 </span> 用。 "else"子句是可選的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>27 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;guided-else[-not]-facet-value-above-length-threshold&amp;gt;
    
    &amp;lt;/guided-if[-not]-facet-value-above-length-threshold&amp;gt;&lt;/code> &lt;/p> &lt;/td>
<td colname="col2"> <p>判斷facet-values回圈中的目前facet值是否高於長度臨界值。 它通常用於只顯示長刻面上低於臨界值的值（除非使用者先前選取了顯示在刻面下方的「檢視更多」連結）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>28 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;guided-else[-not]-facet-value-equals-length-threshold&amp;gt;
    
    &amp;lt;/guided-if[-not]-facet-value-equals-length-threshold&amp;gt&lt;/code> &lt;/p> &lt;/td>
<td colname="col2"> <p>判斷facet-values回圈中的目前facet值是否等於長度臨界值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>29 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-undo-link&gt;&lt;/guided-facet-value-undo-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>顯示指定選取之Facet值的還原連結。 使用它可在選取的Facet值旁顯示還原連結。 由於此還原連結只會解除該特定選取的值，所以與 <span class="codeph"> &lt;guided-facet-undo-link&gt;不同，&lt;guided-facet-undo-link&gt; </span> 會取消選取所有選取的值。 </p> <p> <p>注意： 如果Facet沒有多選行為，則兩個還原連結有相同的行為。 也就是說，Facet只能有一個選取的值。 </p> </p> <p>如果Facet目前未選取，則連結是目前路徑。 僅在引導Facet值 <span class="codeph"> 回圈中使用此標 </span> 記。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>30 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-undo-path/&gt; </span> </p> </td> 
   <td colname="col2"> <p>建立您自己的Facet值還原連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>31 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-undo-path gsname=" <span class="varname"> facetname </span>"/&gt; </span> </p> </td> 
   <td colname="col2"> <p>建立您自己的Facet還原連結。 </p> <p> 與 <span class="codeph"> &lt;guided-facet-undo-link&gt;標籤類似， </span> 只不過它提供原始路徑來建立您自己的還原連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>32 </p> </td> 
   <td colname="col1"> <p> <varname></varname> </p> </td> 
   <td colname="col2"> <p>當指定Facet有選取或單一值「值」時，有條件地顯示HTML。 這組標籤通常用於根據在其他Facet中選取的值來顯示Facet。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>33 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-behavior gsname=" <span class="varname"> facetname </span>"/&gt; </span> </p> </td> 
   <td colname="col2"> <p>判斷Facet的行為，例如一般、自黏或多選。 對於收到XML結果並想要根據Facet的行為動態變更其顯示方式的客戶而言，這非常有用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>34 </p> </td> 
   <td colname="col1"> <p> <varname></varname>

    &amp;lt;/guided-if-facet[-not]-visible&amp;gt;&lt;/code> &lt;/p> &lt;/td>
<td colname="col2"> <p>此標籤所包住的內容會根據Facet的可見性狀態而隱藏或顯示。 如果業務規則直接隱藏或揭示Facet，則Facet內的任何內容都會隱藏或揭示。 這些標籤不必包住Facet。 </p> <p> 此標籤的常見用途是當名稱位於Facet外時隱藏顯示名稱。 將此標籤包住顯示名稱，會在Facet隱藏時使名稱消失。 </p> <p>此標籤會取代區域，而且其許多效能優點與使用區域相同。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 階層連結 {#section_9B39B71FA6EC49FA8D88AD8A3BA987F7}

請參 [閱Breadcrumbs](../c-about-design-menu/c-about-breadcrumbs.md#concept_FB8A943C594A4A1593B118141DA61F03)。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-breadcrumb [gsname=" <span class="varname"> breadcrumbname </span>"&gt;&gt;&lt;/guided-breadcrumb&gt; </span> </p> </td> 
   <td colname="col2"> <p>階層連結的循環標籤。 對於當前狀態的每個查詢編號，會迭代在開始和結束標籤之間的任何內容。 </p> <p>如果 <span class="codeph"> 省略 <span class="varname"></span></span> gsname，則會使用名為"default"的階層連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-breadcrumb-link [gsname="goto|remove|drop"] [attr="value"+&gt;&lt;/guided-breadcrumb-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>在階層連結中建立連結。 預設行為是「goto」行為。 如果連結的運作方式不同，請使用 <span class="codeph"> gsname <span class="varname"> 選用屬 </span></span> 性來指定「移除」或「拖放」。 標籤中包含的任何屬性都會傳遞至產生的錨點標籤。 </p> <p> <code class="syntax html"> &lt;guided-breadcrumb&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-link&nbsp;gsname="remove"&nbsp;class="bc_link"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-value/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-beadcrumb-value /&gt; </span> </p> </td> 
   <td colname="col2"> <p>值標籤會列出目前階層連結小版本的轉換值。 它僅用於引導式網站導覽路徑 <span class="codeph"> 標示區塊的內 </span> 容。 </p> <p> <code class="syntax html"> &lt;guided-breadcrumb&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-value/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-beadcrumb-label /&gt; </span> </p> </td> 
   <td colname="col2"> <p>標籤標籤會輸出階層連結值的標籤，其中詳述選取要產生該階層連結項目的階層連結值。 它僅用於引導式網站導 <span class="codeph"> 覽路徑標示區 </span> 塊。 </p> <p> <code class="syntax html"> &lt;guided-breadcrumb&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-label/&gt;:&nbsp;&lt;guided-breadcrumb-value/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to search-eng version, 2/1/2013--> <code> &lt;guided-if-breadcrumb-label&gt; 
      &lt;guided-else- 
      breadcrumb-label&gt; 
      &lt;guided-if-breadcrumb-label /&gt; </code> </p> </td> 
   <td colname="col2"> <p>如果目前的階層連結值有標籤，則此條件標籤會用來有條件地顯示內容。 它僅用於在標籤實際存在時顯示標籤和關聯內容。 它僅用於引導式網站導 <span class="codeph"> 覽路徑標示區 </span> 塊。 </p> <p> <code class="syntax html"> &lt;guided-breadcrumb&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-breadcrumb-label&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-label/&gt;: 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-breadcrumb-label&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-value/&gt;&lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-breadcrumb-path [gsname="goto|remove|drop"/&gt; </span> </p> </td> 
   <td colname="col2"> <p>用於建立您自己的網站導覽路徑標示連結。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 功能表 {#section_1D489ADF041F4351A66E5D5742125CA8}

請參閱 [關於功能表](../c-about-design-menu/c-about-menus.md#concept_68123CE5CF4447B59217B5D721424E32)。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu gsname="menuname"&gt;&lt;/guided-menu&gt; </span> </p> </td> 
   <td colname="col2"> <p>這是功能表值循環迭代器標籤。 使用 <span class="codeph"> gsname </span> 屬性來識別要顯示的功能表項目集。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-link [attr="value"+&gt;&lt;/guided-menu-item-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>提供URL，以調整目前功能表項目的搜尋。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-option [attr="value"]+ /&gt; </span> </p> </td> 
   <td colname="col2"> <p>通常，選單會顯示在範本的選取控制項中。 此標籤可讓建立選取控制項變得更簡單，因為它會產生HTML，以產生選取控制項的選項。 </p> <p>例如，下列程式碼區塊： </p> <p> <code class="syntax html"> &lt;select&nbsp;name="sort"&nbsp;onchange="gcGo(this);"&gt; 
      &lt;guided-menu&nbsp;gsname="sort"&gt; 
      &lt;guided-menu-item-option/&gt; 
      &lt;/guided-menu&gt; 
      &lt;/select&gt; </code> </p> <p>可產生HTML，如下所示： </p> <p> <code class="syntax html"> &lt;select&nbsp;name="sort"&nbsp;onchange="gcGo(this);"&gt; 
      &nbsp;&nbsp;&lt;option&nbsp;value="?sort=relevance;sp_sfvl_field=product-type|category|size;"&nbsp;selected="selected"&gt;Sort&nbsp;by&nbsp;Relevance&lt;/option&gt; 
      &nbsp;&nbsp;&lt;option&nbsp;value="?sort=avail-code;sp_sfvl_field=product-type|category|size;"&gt;Sort&nbsp;by&nbsp;Availability&lt;/option&gt; 
      &nbsp;&nbsp;&lt;option&nbsp;value="?sort=price;sp_sfvl_field=product-type|category|size;"&gt;Sort&nbsp;by&nbsp;Price&lt;/option&gt; 
      &lt;/select&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-value /&gt; </span> </p> </td> 
   <td colname="col2"> <p>傳回與功能表相關聯之值的字串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-label /&gt; </span> </p> </td> 
   <td colname="col2"> <p>傳回與功能表關聯的標籤字串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-path /&gt; </span> </p> </td> 
   <td colname="col2"> <p>傳迴路徑字串。 如果您想要新增參數至路徑並建立自訂連結，請使用標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if-menu-item-selected&gt; 
      &lt;guided-else-menu- 
      item-selected&gt; 
      &lt;/guided-if-menu-item-selected&gt; </code> </p> </td> 
   <td colname="col2"> <p>傳回1或0，指出是否選取目前的功能表項目。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 帕格納夫 {#section_2EE397635C514BBC8D668278EA314F35}

頁面導覽標籤可用來建立一組連結，讓使用者可以透過搜尋結果進行頁面。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-pages&gt;&lt;/guided-pages&gt; </span> </p> </td> 
   <td colname="col2"> <p>頁面導覽的循環標籤。 每個頁面都會重複開始和結束標籤之間的任何內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-link [attr="value"+&gt;&lt;/guided-page-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>在頁面導覽中建立連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-link gsname="first|prev|next|last|viewall|viewpages" [attr="value"+&gt;&lt;guided-page-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>建立第一個、上一個、下一個或最後一頁的連結。 它也可以建立連結，以檢視單一頁面上的所有頁面。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-number /&gt; </span> </p> </td> 
   <td colname="col2"> <p> 傳回具有目前頁碼的字串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if-page-selected&gt; 
      &lt;guided-else-page- 
      selected&gt; 
      &lt;/guided-if-page-selected&gt; </code> </p> </td> 
   <td colname="col2"> <p>如果選取目前重複的頁面，則此組條件標籤為true。 它通常用於在頁面導覽控制項中顯示不同的頁碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-page-prev&gt; 
      &lt;guided-else-page- 
      prev&gt; 
      &lt;/guided-if[-not]-page-prev&gt; </code> </p> </td> 
   <td colname="col2"> <p> 如果目前頁面有上一頁，則此組條件標籤為true。 它通常用於在頁面導覽中顯示先前的連結（當有意義時）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-page-next&gt; 
      &lt;guided-else-page- 
      next&gt; 
      &lt;/guided-if[-not]-page-next&gt; </code> </p> </td> 
   <td colname="col2"> <p> 如果目前頁面有下一頁，則此組條件標籤為true。 它通常用於在頁面導覽中顯示先前的連結（當有意義時）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-page-viewall&gt; 
      &lt;guided-else-page- 
      viewall&gt; 
      &lt;/guided-if[-not]-page-viewall&gt; </code> </p> </td> 
   <td colname="col2"> <p> 當搜尋傳回大型結果集時，您可能不想提供檢視所有結果的能力。 因此，您可以使用這組條件標籤來決定何時顯示「全部檢視」連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-page-viewpages&gt; 
      &lt;guided-else-page- 
      viewpages&gt; 
      &lt;/guided-if[-not]-page-viewpages&gt; </code> </p> </td> 
   <td colname="col2"> <p>您可以使用這組條件標籤來決定何時顯示「檢視頁面」連結。 它通常用於允許客戶檢視特定頁面。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 

    &amp;lt;guided-else-page-link&amp;gt;
    &amp;lt;/guided-if[-not]-page-link&amp;gt&lt;/code> &lt;/p> &lt;/td>
<td colname="col2"> <p>測試頁面導覽是否包含第一頁、上一頁、下一頁等。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-total /&gt; </span> </p> </td> 
   <td colname="col2"> <p> 傳回搜尋結果總頁數的字串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-pagination gsname= 
      "pagination_name"&gt;&lt;/guided-pagination&gt; </code> </p> </td> 
   <td colname="col2"> <p>使用引 <span class="codeph"> 導編頁標 </span> 簽可定義一個區域，在此區域中，所有編頁標籤都與特定編頁設定相關，以備您定義的「頁面導覽設定」較少時。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> 

    next|last|viewall|viewpages;/&amp;gt;&lt;/code> &lt;/p> &lt;/td>
<td colname="col2"> <p>在頁面導覽中建立您自己的連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-page-high-eq-last&gt; 
      &lt;guided-else-page- 
      high-eq-last&gt; 
      &lt;/guided-if-page-high-eq-last&gt; </code> </p> </td> 
   <td colname="col2"> <p>測試頁面導覽中的最高頁面是否等於頁面總數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-page-low-eq-first&gt; 
      &lt;guided-else-page-low-eq-first&gt; &lt;/guided-if-page-low-eq-first&gt; </code> </p> </td> 
   <td colname="col2"> <p>測試頁面導覽中最低的頁面是否等於頁面導覽。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-page-is-multipage&gt; &lt;guided-else-page-is-multipage&gt; &lt;/guided-if-page-is-multipage&gt; </span> </p> </td> 
   <td colname="col2"> <p>測試是否有單一頁結果或多頁結果。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最近搜尋 {#section_8CD907521F584257B475595B01A5964B}

您可以使用最近搜尋標籤來建立一組連結，讓使用者可快速執行先前的搜尋，如下列範例所示：

```
<guided-if-recent-searches> 
    <span>Recent Searches</span><br/> 
    <guided-recent-searches> 
        <guided-recent-searches-link><guided-recent-searches-value></guided-recent-searches-link><br/> 
    </guided-recent-searches> 
    <guided-recent-searches-clear-link>Clear Recent Searches</guided-recent-searches-clear-link> 
</guided-if-recent-searches>
```

請參 [閱設定最近搜尋](../c-about-design-menu/t-configuring-recent-searches.md#task_E9E8ACA04C90484F8AFD5262167B2562)。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches&gt;&lt;/guided-recent-searches&gt; </span> </p> </td> 
   <td colname="col2"> <p>最近搜尋的循環標籤。 每個頁面都會重複開始和結束標籤之間的任何內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-recent-searches-link [attr="value"]+&gt; 
      &lt;/guided-recent-searches-link&gt; </code> </p> </td> 
   <td colname="col2"> <p>可讓您建立最近搜尋的連結。 它支援將任何HTML屬性直接傳遞至錨點標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-path/&gt; </span> </p> </td> 
   <td colname="col2"> <p>可讓您擷取最近搜尋的相對URL路徑，位於引導 <span class="codeph"> -最近搜尋循 </span> 環中。 通常您會使 <span class="codeph"> 用引導——最近搜尋連結 </span>。 不過，如果您想要建立自己的連結，則可使用此標籤。 以下是範例： </p> <p> <code class="syntax html"> &lt;guided-lt/&gt;a&amp;nbsp;href="&lt;guided_recent_searches_path&gt;"&gt;&lt;guided-recent-searches-value&gt;&lt;/a&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-value&gt; </span> </p> </td> 
   <td colname="col2"> <p>可讓您擷取與最近搜尋相關聯的查詢詞。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-clear-link [attr="value"]+&gt;&lt;/guided-recent-searches-clear-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>可讓您讓客戶能夠清除最近儲存的搜尋。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-clear-path/&gt; </span> </p> </td> 
   <td colname="col2"> <p>傳回 <span class="codeph"> &lt;guided-recent-searches-clear-link&gt;所使用的路 </span> 徑，以便您建立自己的連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;/guided-if-recent-searches&amp;gt;&lt;/code> &lt;/p> &lt;/td>
<td colname="col2"> <p>可讓您在客戶執行最近搜尋時顯示最近的搜尋。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 您的意思是 {#section_C1EB3B9D8E1242798A6E04609D1E3543}

當搜尋未傳回任何結果且搜尋詞未在帳戶字典中時，您可以使用「您是指」標籤來建立建議的連結集。 以下是使用Did You Mean標籤的範例：

```
<guided-if-suggestions> 
    <span>Did You Mean?</span><br/> 
    <guided-suggestions> 
        <guided-suggestion-link><guided-suggestion/></guided-suggestion-link><br/> 
    </guided-suggestions> 
</guided-if-suggestions>
```

請參閱[關於您的意思是](../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E)。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matches search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-exceliations&gt;&lt;/guided-excempendations&gt; </span> </p> </td> 
   <td colname="col2"> <p>這是循環標籤，可循環顯示建議。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matches search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-seccument-link [attr="value"]+&gt;&lt;/guided-seccument-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>建立指向指定建議的連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Newly added from search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-seccument-value /&gt; </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-suggestions&gt;&lt;guided-else[-not]- 
      suggestions&gt;&lt;/guided-if[-not]-suggestions&gt; </code> </p> </td> 
   <td colname="col2"> <p>可讓您測試是否有任何建議。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-seccument-path/&gt; </span> </p> </td> 
   <td colname="col2"> <p>傳回建議的路徑字串。 您可使用它建立自己的錨點標籤。 通常會 <span class="codeph"> 改用引導建議 </span> 連結。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-seccommendation/&gt; </span> </p> </td> 
   <td colname="col2"> <p>建議。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-seccument-result-count/&gt; </span> </p> </td> 
   <td colname="col2"> <p>建議的結果計數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-suggestion-autosearch&gt; 
      &lt;guided-else[-not]-suggestion-autosearch&gt; 
      &lt;/guided-if[-not]-suggestion-autosearch&gt; </code> </p> </td> 
   <td colname="col2"> <p>可讓您測試是否已對零結果執行依建議的自動搜尋，以防此功能開啟。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-seckuping-original-query/&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果已執行自動搜索，則返回原始查詢。 </p> <p>使用範例： </p> <p> <code class="syntax html"> &lt;guided-if-suggestion-autosearch&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;Search&nbsp;for&nbsp;&lt;guided-query-param&nbsp;gsname="q"&nbsp;/&gt;&nbsp;instead&nbsp;of&nbsp;&lt;guided-suggestion-original-query&nbsp;/&gt; 
      &lt;/guided-if-suggestion-autosearch&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-suggestion-low-results&gt; 
      &lt;guided-else[-not]-suggestion-low-results&gt; 
      &lt;/guided-if[-not]-suggestion-low-results&gt; </code> </p> </td> 
   <td colname="col2"> <p>如果因為結果計數低而有建議，則此條件成立，以防此功能開啟。 </p> <p>以下是使用此標籤的範例： </p> <p> <code class="syntax html"> &lt;guided-if-suggestion-low-results&gt; 
      &nbsp;&nbsp;&nbsp;You&nbsp;have&nbsp;a&nbsp;low&nbsp;result&nbsp;count&nbsp;for&nbsp;&lt;guided-query-param&nbsp;gsname="q"&nbsp;/&gt;. 
      &nbsp;&nbsp;&nbsp;Did&nbsp;you&nbsp;mean:&nbsp;&lt;guided-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestion-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestion&nbsp;/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-suggestion-link&gt;&lt;guided-if-not-last&gt;,&nbsp;&lt;/guided-if-not-last&gt; 
      &nbsp;&nbsp;&nbsp;&lt;/guided-suggestions&gt; 
      &lt;/guided-if-suggestion-low-results&gt; </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 自動完成 {#section_897316BEE1454E839A56B565CA4AF018}

下列標籤可用來將自動完成新增至您的搜尋表單。 必須有head-content和form-content標籤，才能使自動完成功能正確。 建議您使用標籤，而非將自動完成的Javascript和CSS硬式編碼至簡報範本。 原因在於，只要您變更自動完成設定，而不需要手動更新範本，標籤就可讓範本擷取任何新的失敗快取ID。

請參 [閱關於自動完成](../c-about-auto-complete.md#concept_093A9CD754864BA79B456FE4BEB64578)。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-autocomplete&gt; &lt;guided-else-autocomplete&gt; &lt;/guided-if-autocomplete&gt; </span> </p> </td> 
   <td colname="col2"> <p>檢測是否啟用了自動完成功能。 您可以使用標籤來挑選自動完成所需的標題和表單內容。 反過來，這可讓您開啟或關閉功能，而不必變更簡報範本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-ac-css/&gt; </span> </p> </td> 
   <td colname="col2"> <p>在簡報範本的標題中使用，並由自動完成的適當CSS指令碼所取代。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-ac-form-content/&gt; </span> </p> </td> 
   <td colname="col2"> <p>用於簡報範本的搜尋表單(在 <span class="codeph"> &lt;form&gt; </span> 和 <span class="codeph"></span> &lt;/form&gt;標籤之間)，而非硬式編碼表單中的自動完成標籤。 標籤會以自動完成作業所需的適當HTML取代。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-ac-javascript/&gt; </span> </p> </td> 
   <td colname="col2"> <p>產生自動完成JavaScript的連結。 為獲得最佳效能，建議您將此標籤放置在頁面底部附近的結尾「body」標籤之前。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Store {#section_A33E25DB5E67404A823BD9618665B773}

使用下列標籤來測試和顯示使用者目前所在的商店。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-store/&gt; </span> </p> </td> 
   <td colname="col2"> <p>輸出當前儲存。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-store-defined&gt; &lt;guided-else-store-defined&gt; &lt;guided-if-store-defined&gt; </span> </p> </td> 
   <td colname="col2"> <p>檢測用戶是否在商店中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-store gsname="store"&gt; &lt;guided-else-store&gt; &lt;-guided-if-store&gt; </span> </p> </td> 
   <td colname="col2"> <p>檢測用戶是否在儲存中 <span class="codeph"> gsname參 </span> 數指定。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 區域 {#section_B9B3179E000C42D492E1541F2FE44CB5}

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-zone gsname="zone area" [search="associated search"] [facet="associated facet"] [width="xx" height="yy"&gt; </span> </p> </td> 
   <td colname="col2"> <p>您可以包覆區域標籤中的任何內容，以建立區域。 這可讓您使用業務規則來視需要顯示區域。 預設情況下，始終顯示區域。 您可以使用可選的搜尋和刻面參數來指出與區域關聯的搜尋或刻面。 這類功能可讓軟體在隱藏區域時略過搜尋或刻面，以改善搜尋時的效能。 高度和寬度屬性是可選的，用來設定移除區域時，預留位置顯示器在視覺化規則產生器中的顯示方式。 </p> <p> 使用 <span class="codeph"> guided-if-facet[-not]-visible標籤，而 </span> 非盡可能使用區域。 它可簡化簡報範本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-zone gsname="zone area"&gt; &lt;guided-else-zone&gt; &lt;guided-if-zone&gt; </span> </p> </td> 
   <td colname="col2"> <p>這組標籤可啟用當前是否顯示區域的測試。 當頁面上的其他位置有您只想在顯示區域時顯示的內容時，此功能就很實用。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 循環指示燈 {#section_387322CA0AA843A2ACF2795C328673E9}

您可以在下列任何循環塊中使用下列每個循環指示符：

* 引導結果
* guided-facet-values
* guided-breadcrumb
* guided-menu-items
* 引導式頁面

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-first&gt;&lt;guided-else[-not]-first&gt; 
      &lt;/guided-if[-not]-first&gt; </code> </p> </td> 
   <td colname="col2"> <p>當當前小版本是循環的第一個小版本時，此條件為真。 這不一定表示第一個結果或第一個頁面，但是第一個顯示的頁面。 如果網站訪客位於每頁10的結果集第2頁，則第一個小版本為結果11。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-last&gt;&lt;guided-else[-not]-last&gt; 
      &lt;/guided-if[-not]-last&gt; </code> </p> </td> 
   <td colname="col2"> <p>當當前小版本是循環的最後一個小版本時，此條件為真。 這並不一定表示最後一個結果或最後一頁，而是目前內容（頁面）中顯示的最後一個結果。 如果網站訪客位於包含200個結果但每頁僅有10個結果的結果集第1頁，則最後一個小版本會是結果10，而非結果200。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-odd&gt;&lt;guided-else[-not]-odd&gt; 
      &lt;/guided-if[-not]-odd&gt; </code> </p> </td> 
   <td colname="col2"> <p>當當前小版本是循環的奇數小版本（與偶數小版本相比）時，此條件是正確的。 這有助於顯示各種行顏色。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-even&gt;&lt;guided-else[-not]-even&gt; 
      &lt;/guided-if[-not]-even&gt; </code> </p> </td> 
   <td colname="col2"> <p>當當前小版本是環的偶數小版本（與奇數小版本相比）時，此條件是正確的。 這有助於顯示各種行顏色。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-alt&gt;&lt;guided-else[-not]-alt&gt; 
      &lt;/guided-if[-not]-alt&gt; </code> </p> </td> 
   <td colname="col2"> <p>當當前小版本是循環的偶數小版本時，此條件是正確的。 這有助於顯示各種行顏色。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-inner&gt;&lt;guided-else[-not]-inner&gt; 
      &lt;/guided-if[-not]-inner&gt; </code> </p> </td> 
   <td colname="col2"> <p>如果當前小版本不是第一個小版本或最後一個小版本，則在它們之間包含文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-outer&gt;&lt;guided-else[-not]-outer&gt; 
      &lt;/guided-if[-not]-outer&gt; </code> </p> </td> 
   <td colname="col2"> <p>如果當前小版本是第一個小版本或最後一個小版本，則在它們之間包含文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-loop-index&gt; </span> </p> </td> 
   <td colname="col2"> <p>一個整數（從0開始），其值會隨循環的每個迭代而遞增。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-loop-counter&gt; </span> </p> </td> 
   <td colname="col2"> <p>一個整數（從1開始），其值會隨循環的每個迭代而遞增。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 其他語言 {#section_BFE8DC98E26F4D7BB60FEC54D9A5DC6C}

以下標籤可讓您使用範本執行更多進階的工作，例如建立您自己的mini-facet。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng, 2/1/2013--> <span class="codeph"> &lt;guided-current-path [escape="html|url|js|json|0" /&gt; </span> </p> </td> 
   <td colname="col2"> <p>提供您目前使用的路徑。 通常，它用於建立新增參數至現有搜尋的連結。 依預設，路徑為URL逸出。 您可以指定要通過轉義參數使用的轉義模式。 </p> <p>範例:   </p> <p> <code class="syntax html"> &lt;a&nbsp;href="&lt;guided-current-path&nbsp;/&gt;&amp;lang=fr"&gt; 
      French&nbsp;Version </code> </p> <p>在此範例中，搜尋處理規則使用lang來選取法文版本。 </p> <p>目前路徑一律至少有一個查詢參數。 如果沒有其他查詢參數，則將其設 <span class="codeph"> 置為q=* </span> ，以便更輕鬆地添加更多參數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> 基本路徑 </span> </p> </td> 
   <td colname="col2"> <p> 如果您想要使用基本路徑建立連結，請在 <span class="codeph"> href </span> 開頭使用 <span class="codeph"> /並 </span> 新增參數。 </p> <p> <code class="syntax html"> &lt;a&nbsp;href="/"&gt;All&nbsp;Products&lt;/a&gt; 
      Would&nbsp;create&nbsp;a&nbsp;link&nbsp;"All&nbsp;Products"&nbsp;to&nbsp;your 
      basepath,&nbsp;for&nbsp;example&nbsp;https://search.mycompany.com/ 
       </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng, 2/1/2013--> <span class="codeph"> &lt;guided-query-param gsname="query-parameter" [escape="html|url" /&gt; </span> </p> </td> 
   <td colname="col2"> <p>可讓您擷取URL上查詢參數的現有值。 如果您的參數不存在，此標籤會傳回空字串。 如果您未指定逸出選項，傳回的字串會自動HTML逸出，您可以指定HTML或URL逸出。 </p> <p>範例:   </p> <p> 

    &amp;lt;guided-query-param&amp;nbsp;gssname=&quot;q&quot;&amp;nbsp;
    gives&amp;nbsp;you&amp;nbsp;nbsp;value&amp;nbsp;nbsp
    
    &amp;lt;guided-query-param&amp;nbsp;gsname=&quot;&amp;nbsp;&amp;bsp;gt;
    gives&amp; nbsp; you&amp; nbsp; nbsp;value&amp; nbsp;en
    
    &amp;nbsp;guided-query-param&amp;nbsp;gt;nbsp;/&amp;
    gives&amp;nbsp;you&amp;nbsp;nbsp;nbsp&amp;ampstring
    &amp;nbsp;
    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&lt;/code> &lt;/p> &lt;/td>
</tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-query-param-name gsname="param#" offset="offset-number"/&gt; </span> </p> </td> 
   <td colname="col2"> <p>引導式搜尋的概念是查詢編號，用於階層連結控制項。 <span class="codeph"> guided-query-param-name可讓您將參數定義為簡報範本中連結的一部分，其中「guided Search」會為您找出正確的查詢編號。 </span> gsname <span class="codeph"></span> 中有"x",「引導式搜尋」會以正確的數字取代。 偏移值可以是0 - 15，其中0表示使用了下一個可用的查詢編號。 1表示您要新增1到它，依此類推。 </p> <p>您可結 <span class="codeph"> 合引導——目前路徑 </span>，建立自己的迷你Facet連結，或允許額外的下鑽層級。 </p> <p>範例:   </p> <p> <code class="syntax html"> &lt;a&nbsp;href="&lt;guided-current-path 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;&amp;&lt;guided-query-param-name&nbsp;gsname="q#"&nbsp;offset="0" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=mens&amp;&lt;guided-query-param-name&nbsp;gsname="x#"&nbsp;offset="0" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=category"&nbsp;&gt;Category:Men&lt;/a&gt;&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </code> </p> <p> <code class="syntax html"> &lt;a&nbsp;href="&lt;guided-current-path 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;&amp;&lt;guided-query-param-name&nbsp;gsname="sp_q_exact_#"&nbsp;offset="0" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=mens&amp;&lt;guided-query-param-name&nbsp;gsname="sp_x_#"&nbsp;offset="0" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=category&amp;&lt;guided-query-param-name&nbsp;gsname="sp_q_exact_#"&nbsp;offset="1" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=Jeans&amp;&lt;guided-query-param-name&nbsp;gsname="sp_x_#"&nbsp;offset="1" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=product-type"&nbsp;&gt;Cat:Men&nbsp;-&nbsp;Product:Jeans&lt;/a&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-include gsfile="filename" /&gt; </span> </p> </td> 
   <td colname="col2"> <p> 可讓您包含其他範本檔案。 此功能表示您可以使用子範本做為模組來建立多個範本。 </p> <p>在下列範例中，包含 <span class="filepath"> 了階層 </span> 連結 <span class="filepath"> 和 </span> 刻面檔案： </p> <p> <code class="syntax html"> &lt;guided-include&nbsp;gsfile='breadcrumbs.tmpl'&nbsp;/&gt; 
      &lt;guided-include&nbsp;gsfile='facets.tmpl'&nbsp;/&gt; </code> </p> <p>不支援動態包含。 換言之， <span class="codeph"> gsfile不 </span> 能是變數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 1/17/2013--> <span class="codeph"> &lt;guided-search-time&gt; </span> </p> </td> 
   <td colname="col2"> <p> 識別搜尋所花的時間。 返回的搜索時間值以毫秒指定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 1/17/2013--> <span class="codeph"> &lt;guided-fall-through-searches&gt; </span> </p> </td> 
   <td colname="col2"> <p> 傳回用於建立搜尋結果頁面的核心搜尋計數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 1/17/2013--> <span class="codeph"> &lt;guided-if-fall-through-search&gt;&lt;/guided-if-fall-through-search&gt; </span> </p> </td> 
   <td colname="col2"> <p>測試核心搜尋的計數是否大於1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-even&gt;&lt;guided-else[-not]-even&gt; 
      &lt;/guided-if[-not]-even&gt; </code> </p> </td> 
   <td colname="col2"> <p>當當前小版本是環的偶數小版本（與奇數小版本相比）時，此條件是正確的。 這有助於顯示各種行顏色。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-alt&gt;&lt;guided-else[-not]-alt&gt; 
      &lt;/guided-if[-not]-alt&gt; </code> </p> </td> 
   <td colname="col2"> <p>當當前小版本是循環的偶數小版本時，此條件是正確的。 這有助於顯示各種行顏色。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-inner&gt;&lt;guided-else[-not]-inner&gt; 
      &lt;/guided-if[-not]-inner&gt; </code> </p> </td> 
   <td colname="col2"> <p>如果當前小版本不是第一個小版本或最後一個小版本，則在它們之間包含文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-outer&gt;&lt;guided-else[-not]-outer&gt; 
      &lt;/guided-if[-not]-outer&gt; </code> </p> </td> 
   <td colname="col2"> <p>如果當前小版本是第一個小版本或最後一個小版本，則在它們之間包含文本。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-first-search&gt;&lt;guided-else-first-search&gt; 
      &lt;/guided-if-first-search&gt; </code> </p> </td> 
   <td colname="col2"> <p>可讓您檢查您是否在初始搜尋中（查詢是搜尋方塊中搜尋的結果）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-search-url/&gt; </span> </p> </td> 
   <td colname="col2"> <p>您可以在範本中使用此標籤，以免硬式編碼搜尋表單的動作。 它會偵測您是在「分段」或「即時」環境中，並相應變更。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-query-param-defined gsname="query-parameter"&gt; &lt;guided-else-query-param-defined&gt; &lt;/guided-if-query-param-defined&gt; </span> </p> </td> 
   <td colname="col2"> <p>這組標籤可讓您測試在搜尋路徑中定義的CGI參數。 只有定義了參數的值，才能測試這些參數的值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-next-query-number [gsname="offset" /&gt; </span> </p> </td> 
   <td colname="col2"> <p>驅動範本的引導式搜尋引擎有浮動查詢編號的概念，引擎產生的每個新連結都會使用下一個可用的查詢編號。 此標籤可讓您擷取下一個查詢編號或位移，以便您建立可深入結果集的自訂連結。 偏移可讓您偏移至下一個查詢編號。 例如，如果您已選取一個Facet，則下一個查詢編號為2，而偏移為1時，傳回的查詢編號為3。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-custom-var gsname="custom_variable" [escape="html|url|js|json|0"/&gt; </span> </p> </td> 
   <td colname="col2"> <p>可讓您擷取處理規則所定義之自訂變數的現有值。 如果您未指定逸出選項，則傳回的字串會自動HTML逸出，您可以指定 <span class="codeph"> html、 </span>URL <span class="codeph"> 、js或 </span>0 <span class="codeph"></span><span class="codeph"></span>。 如果您使用處理規則將傳入的CGI參數複製到自訂變數，然後在範本中顯示或使用該變數，並將逸出設定為無或js，則可在搜尋中建立XSS弱點。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-custom-var-defined gsname="custom-variable"&gt; &lt;guided-else-custom-var-defined&gt; &lt;/guided-if-custom-var-defined&gt; </span> </p> </td> 
   <td colname="col2"> <p>啟用在處理規則中定義自訂變數（查詢清除、搜尋前處理和搜尋後處理）時的測試。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-general-field gsname="searchname" field="fieldname" [escape="html|url|js|json|0"/&gt; </span> </p> </td> 
   <td colname="col2"> <p>可讓您顯示傳輸範本中定義的一般欄位內容。 如果未指定轉義選項，則返回的字串將按照在該欄位的傳輸模板中指定的格式進行編碼。 指定逸出選項會套用在您要編碼欄位的任何格式上，就像在傳輸範本中一樣。 您可以指定html、js <span class="codeph"> js、 </span>url、json <span class="codeph"> html </span>或0 <span class="codeph"></span><span class="codeph"></span><span class="codeph"></span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>20 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-general-field gsname="searchname" field="fieldname"&gt; &lt;guided-else-general-field&gt; &lt;guided-if-general-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>啟用在傳輸模板中定義的常規欄位內容是否存在時進行測試。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>21 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-cookie-value gsname="cookie_name" [escape="html|url|js|json|0"/&gt; </span> </p> </td> 
   <td colname="col2"> <p>可讓您擷取Cookie的值（假設Cookie可用）。 如果您未指定逸出選項，則傳回的字串會自動HTML逸出，您可以指定html、 <span class="codeph"> url </span>js、 <span class="codeph"> js </span>、 <span class="codeph"> Json </span><span class="codeph"></span><span class="codeph"></span>0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>22 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-cookie gsname="cookie_name"&gt; &lt;guided-else-cookie&gt; &lt;/guided-if-cookie&gt; </span> </p> </td> 
   <td colname="col2"> <p>啟用Cookie存在時的測試。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>23 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-banner gsname="banner area" [escape="html|url|js|json|0"] [width="xx" height="yy"/&gt; </span> </p> </td> 
   <td colname="col2"> <p>輸出指定區域的橫幅。 視覺規則產生器會使用可選的寬度和高度屬性，讓顯示有意義的位置保持器，讓使用者選取橫幅。 依預設，橫幅不會逸出。 而是要將HTML插入簡報範本。 不過，如果您要建立JSON範本，請考慮使用js逸出選項。 </p> <p>範例:   </p> <p> <code class="syntax html"> &lt;guided-banner&nbsp;gsname="top"&nbsp;width="400px" 
      &nbsp;height="50px"/&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>24 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-banner-set gsname="banner area"&gt; &lt;guided-else-banner-set&gt; &lt;guid-if-banner-set&gt; </span> </p> </td> 
   <td colname="col2"> <p>啟用在設定橫幅區域時進行測試。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>25 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-simulator-mode&gt; &lt;guided-else-simulator-mode&gt; &lt;guided-if-simulator-mode&gt; </span> </p> </td> 
   <td colname="col2"> <p>可讓您偵測在模擬器或視覺規則產生器中檢視搜尋的時間。 它通常用於顯示您的額外除錯資訊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>26 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-tnt-business-rules&gt; &lt;guided-else-tnt-business-rules&gt; &lt;guided-if-tnt-business-rules&gt; </span> </p> </td> 
   <td colname="col2"> <p>可讓您偵測是否有任何參考 <span class="keyword"> Adobe Target促銷活動的業 </span> 務規則。 它通常用作與 <span class="keyword"> Adobe Target整合的一部分， </span> 以防止在不需要時點擊 <span class="keyword"> Target </span> 伺服器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>27 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-redirect/&gt; </span> </p> </td> 
   <td colname="col2"> <p>預設會自動執行重新導向。 不過，如果您已設定網站搜尋／銷售以傳回XML或JSON回應至您的Web應用程式，您可以選擇解析Web應用程式中的302/301回應，或是將重新導向傳送至您，作為結果集的一部分。 如果您是將重新導向傳入為結果集的一部分，則此標籤可用於範本中，以輸出重新導向位置。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>28 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-redirect&gt; &lt;guided-else-redirect&gt; &lt;/guided-if-redirect&gt; </span> </p> </td> 
   <td colname="col2"> <p>當您已設定網站搜尋／銷售以在結果集中傳回重新導向時，這組標籤可用來判斷是否有重新導向至輸出。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>29 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-lt/&gt; &lt;guided-gt/&gt; </span> </p> </td> 
   <td colname="col2"> <p>這組標籤可讓您在HTML屬性中內嵌引導範本標籤。 </p> <p>範例:   </p> <p> <code class="syntax html"> &lt;guided-lt/&gt;div&nbsp;&lt;guided-if-facet-long&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;style="height:&nbsp;125px;&nbsp;overflow: 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;auto;"&lt;/guided-if-facet-long&gt;&lt;guided-gt/&gt; </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 傳輸範本標籤 {#reference_227D199F5A7248049BE1D405C0584751}

傳輸範本是XML範本，可將資料從後端搜尋傳遞至引導式搜尋表現層。

<!-- 

r_transport_template_tags.xml

 -->

在您的表現層中，您可以有單一的表現範本，來呈現多個搜尋的結果。 每個搜尋都可以使用相同的傳輸範本或自訂傳輸範本，將資料傳遞至表現層。

由於傳輸範本僅用於將資料傳遞至表現層，因此它沒有任何與顯示搜尋結果相關的HTML。 傳輸範本使用傳輸範本XML標籤來傳遞用於填入引導式搜尋元件（例如刻面、階層連結和功能表）的搜尋結果。 在這些標籤內，標準搜尋範本標籤可用來顯示實際值。

請參 [閱編輯簡報或傳輸範本](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3)。

請參閱 [搜尋範本標籤](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>傳輸範本標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-xml&gt;&lt;/guided-xml&gt; </span> </p> </td> 
   <td colname="col2"> <p>表現層用來檢測從傳輸模板中解析的內容的根XML標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;general&gt;&lt;/general&gt; </span> </p> </td> 
   <td colname="col2"> <p>標籤圍繞根據結果集提供摘要資料的搜索模板標籤。 通常，這些標籤包含搜尋標籤，用於搜尋總結果數、較低結果和最高結果。 您可以使用一般欄位標籤定義任意數量的其 <span class="codeph"> 他全域欄 </span> 位，如下列範例所示： </p> <p> <code class="syntax html"> &lt;general&gt; 
      &nbsp;&nbsp;&lt;total&gt;&lt;search-total&nbsp;/&gt;&lt;/total&gt; 
      &nbsp;&nbsp;&lt;lower&gt;&lt;search-lower&nbsp;/&gt;&lt;/lower&gt; 
      &nbsp;&nbsp;&lt;upper&gt;&lt;search-upper&nbsp;/&gt;&lt;/upper&gt; 
      &nbsp;&nbsp;&lt;general-field&nbsp;name="my_custom_field"&gt;Some&nbsp;global&nbsp;content&lt;/general-field&gt; 
      &lt;/general&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;results&gt;&lt;/results&gt; </span> </p> </td> 
   <td colname="col2"> <p>標籤會包住搜尋結果，讓「搜尋指南」知道在何處尋找。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result&gt;&lt;/result&gt; </span> </p> </td> 
   <td colname="col2"> <p>標籤會包住每個搜尋結果，讓「搜尋指南」識別單一搜尋結果的內容開始和結束的位置，如下列範例所示： </p> <code class="syntax html"> &lt;results&gt; 
     &nbsp;&nbsp;&lt;search-results&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;result&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;index&gt;&lt;search-index&nbsp;/&gt;&lt;/index&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;loc&gt;&lt;search-cdata&gt;&lt;search-url&nbsp;length="500"&nbsp;/&gt;&lt;/search-cdata&gt;&lt;/loc&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;/result&gt; 
     &nbsp;&nbsp;&lt;/search-results&gt; 
     &lt;/results&gt; </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;attribute-table name="tablename"&gt; </span> </p> </td> 
   <td colname="col2"> <p>可讓您重複檢視多值清單中的每個項目，以產生單一結果。 僅在結果中使用此標籤。 其目的是讓您重複屬於結果欄位的屬性，如下列範例所示： </p> <code class="syntax html"> &lt;results&gt; 
     &nbsp;&nbsp;&lt;search-results&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;result&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;index&gt;&lt;search-index&nbsp;/&gt;&lt;/index&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;loc&gt;&lt;search-url&nbsp;/&gt;&lt;/loc&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;title&gt;&lt;search-title&nbsp;/&gt;&lt;/title&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;attribute-table&nbsp;name="downloads"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;field&nbsp;name="download_title"&gt;&lt;search-display-field&nbsp;name="download_title"&nbsp;/&gt;&lt;/field&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;field&nbsp;name="download_link"&nbsp;delimiter="|"&gt;&lt;search-display-field&nbsp;name="download_link"&nbsp;/&gt;&lt;/field&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/attribute-table&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;/result&gt; 
     &nbsp;&nbsp;&lt;/search-results&gt; 
     &lt;/results&gt; </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facets&gt;&lt;/facets&gt; </span> </p> </td> 
   <td colname="col2"> <p>傳遞填入Facet的結果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <!--NEW 2/27/2014--> <span class="codeph"> &lt;dynamic-facet&gt;&lt;/dynamic-facet&gt; </span> </p> </td> 
   <td colname="col2"> <p> 可將小平面指定為動態小平面和小平面邊欄的成員。 不過，其處理方式與相關的簡報範本標籤無關。 </p> <p>換言之，不允許在動態Facet循環內容中巢狀內嵌Facet邊欄循環內容，反之亦然。 </p> <p>對於動態和欄位化的刻面，只有為特定搜尋傳回的動態刻面，才會顯示在刻面軌道循環內容中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet name="name"&gt;&lt;facet&gt; </span> </p> </td> 
   <td colname="col2"> <p> 每個Facet都有其專屬的Facet標籤，其中name參數與Facet名稱相符。 搜尋標籤會在Facet標籤中用於Facet值，如下列範例所示： </p> <code class="syntax html"> &lt;facets&gt; 
     &nbsp;&nbsp;&lt;facet&nbsp;name="brand"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
     &nbsp;&nbsp;&lt;/facet&gt; 
     &nbsp;&nbsp;&lt;facet&nbsp;name="category"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
     &nbsp;&nbsp;&lt;/facet&gt; 
     &lt;/facets&gt; </code> <p> 使用槽刻面的帳戶可以使用動態標籤和顯示名稱標籤。 這兩個標籤都有助於在建立業務規則時，在槽刻刻面和實際刻面之間建立對應。 </p> <code class="syntax html"> &lt;facets&gt; 
     &nbsp;&nbsp;&lt;facet&nbsp;name="facet_values01"&gt; 
     &nbsp;&lt;dynamic&gt;1&lt;/dynamic&gt; 
     &nbsp;&lt;display-names&gt;&lt;search-field-value-list&nbsp;name="facet_names01"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/display-names&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="facet_values01"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="facet_values01"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
     &nbsp;&nbsp;&lt;/facet&gt; </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field separator=","&gt; </span> </p> </td> 
   <td colname="col2"> <p>分隔 <span class="codeph"> 符屬 </span> 性可讓您變更在輸出清單的搜尋顯示欄位資料時使用的分隔符。 預設值為逗號。 </p> <p>一般而言，您使用的分隔字元應該是無法立即顯示在欄位內容中的分隔字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;建議&gt;&lt;/建議&gt; </span> </p> </td> 
   <td colname="col2"> <p> 使用標籤來包住您的「您的意思」建議，讓「搜尋指南」識別哪些XML節點包含建議。 </p> <p>請參閱<a href="../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E" type="concept" format="dita" scope="local">關於您的意思是</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;建議&gt;&lt;/建議&gt; </span> </p> </td> 
   <td colname="col2"> <p>以標籤包住每個Did You Mean建議，如下列範例所示： </p> <code class="syntax html"> &lt;search-if-suggestions&gt; 
     &nbsp;&nbsp;&lt;suggestions&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;search-suggestions&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;suggestion&gt;&lt;search-suggestion-text&nbsp;/&gt;&lt;/suggestion&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-suggestions&gt; 
     &nbsp;&nbsp;&lt;/suggestions&gt; 
     &lt;/search-if-suggestions&gt; </code> <p>請參閱<a href="../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E" type="concept" format="dita" scope="local">關於您的意思是</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 搜尋範本標籤 {#reference_F7AA3FF602314E42842BBC740D2CA1A4}

搜尋範本是HTML檔案，包含網站搜尋／銷售所定義的範本標籤。 這些標籤表示搜索結果的格式。 以下參考包含每個搜索模板標籤及其屬性的簡要說明。

<!-- 

r_search_template_tags.xml

 -->

>[!NOTE]
>
>僅在傳輸範本檔案(.tpl)中使用搜尋範本標籤。

您可以從下列搜尋範本標籤群組和參考資料中選取。

僅在結果回圈內有效的標籤包括：

* [關於結果循環標籤](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629)
* [結果回圈字串標籤](../c-appendices/c-templates.md#section_80D68334E8D04A33937A6E58ABAAA320)
* [結果循環條件標籤](../c-appendices/c-templates.md#section_35C367969E384A06A9865E388F1F9360)
* [結果循環錨點連結標籤](../c-appendices/c-templates.md#section_C5FAEF520E9E42ADAD1F90651922AA02)
* [循環位置條件標籤](../c-appendices/c-templates.md#section_E0C29DDA09E043C9A396F36334F05EBB)

在整個範本中有效的標籤包括：

* [欄位值清單標籤](../c-appendices/c-templates.md#section_D3298B5F976447DBA0032B883DCC91B1)
* [欄位值清單循環標籤](../c-appendices/c-templates.md#section_0717FA09F0FC449CB916883B0500A60E)
* [建議標籤](../c-appendices/c-templates.md#section_C28EB8B4F7DC4E278A0F143BCFEEB1AC)
* [範本字串標籤](../c-appendices/c-templates.md#section_67E3D529661F4F03A1FF469D9D658CAF)
* [範本錨點連結標籤](../c-appendices/c-templates.md#section_3A51D27616C541E2B818CC52B2B856BA)
* [範本條件標籤](../c-appendices/c-templates.md#section_18D9BC66DE484881932FD2F7EA9D170D)
* [範本表單控制標籤](../c-appendices/c-templates.md#section_45AFC414ACA74825B72FEAA8456F8DD2)

搜尋範本參考主題

* [日期格式字串](../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4)
* [語言識別碼](../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911)
* [指定內容類型HTTP標題](../c-appendices/c-templates.md#section_AEED823E9938448A9EDB2F286D9CFD90)
* [在HTML範本中指定字元集](../c-appendices/c-templates.md#section_E0D1816ABB5846BEBE9C26D5980CCBE6)
* [在XML模板中指定字元集](../c-appendices/c-templates.md#section_17DC31CDCC104F5F8081466B41A96E9D)
* [在其他範本中包含搜尋範本](../c-appendices/c-templates.md#section_7D1FCD3D9E2340C291E354C9720E8BC0)

## 關於結果循環標籤 {#section_D4DC7B4560144663972E8DBC3369C629}

結果loop標籤是模板系統的主要功能。 在搜尋期間遇到標籤時，會重複HTML，而開始和結束結果循環標籤之間會有其他標籤，以您的搜尋結果取代任何其他標籤。

`<search-results> ... </search-results>`

結果循環標籤環繞顯示搜尋結果的HTML。 標籤之間的HTML會針對每個結果重複，並顯示在頁面上。

下列標籤僅在結果循環中有效：

* [結果回圈字串標籤](../c-appendices/c-templates.md#section_80D68334E8D04A33937A6E58ABAAA320)
* [結果循環條件標籤](../c-appendices/c-templates.md#section_35C367969E384A06A9865E388F1F9360)
* [結果循環錨點連結標籤](../c-appendices/c-templates.md#section_C5FAEF520E9E42ADAD1F90651922AA02)
* [循環位置條件標籤](../c-appendices/c-templates.md#section_E0C29DDA09E043C9A396F36334F05EBB)

## 結果回圈字串標籤 {#section_80D68334E8D04A33937A6E58ABAAA320}

下列標籤會傳回字串。

請參 [閱關於結果循環標籤](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629)。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-index&gt; </span> </p> </td> 
   <td colname="col2"> <p>返回當前結果的數值索引。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-title length="XX"&gt; </span> </p> </td> 
   <td colname="col2"> <p>傳回目前結果的頁面標題。 選用的length屬性可用來限制顯示的字串長度，預設值為80個字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-bodytext length="XX" encoding="html/javascript/json/perl/url/none" &gt; </span> </p> </td> 
   <td colname="col2"> <p>傳回從頁面頂端開始的內文文字。 相關詞語以粗體顯示。 選用的length屬性可用來限制顯示的字串長度，預設值為80個字元。 編碼屬性是選用的，可以使用HTML編碼（預設值）、Javascript編碼、Perl編碼或無來編碼輸出字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-description length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p> 返回當前結果的說明。 如果元描述標籤存在且內容屬性不為空，則會顯示該文本。 否則，將顯示頁面的正文文本的開頭。 選用的length屬性可用來限制顯示的字串長度，預設值為80個字元。 </p> <p>可選的 <span class="codeph"> 編 </span> 碼屬性控制輸出是否為HTML編碼、JavaScript編碼、Perl編碼、URL編碼或未編碼，以便在結果頁面上輸出。 編碼的預設 <span class="codeph"> 值 </span> 為 <span class="codeph"> html </span>。 通常，您不需要指定編碼屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-score rank="dynamic/static/dynamic-raw/static-raw/final-raw" precision="XX"&gt; </span> </p> </td> 
   <td colname="col2"> <p>傳回目前結果的分數，即數字0 - 100。 如果您已在「選項」&gt;「 <span class="uicontrol"> 中繼資料 </span> 」&gt;「定義」下定義排名欄位，則可將排名屬性設為動態( <span class="uicontrol"></span><span class="uicontrol"></span><span class="codeph"></span>&lt;search-score rank="dynamic"&gt;)，以顯示動態頁面排名。 您可將排名屬性設為靜態( <span class="codeph"> &lt;search-score rank="static"&gt; </span>)，以顯示靜態頁面排名。 您可以使用可選的precision屬性來指定要顯示的小數位數。 預設值為0，顯示整數分數)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-date length="XX" none="text" date-format="date-format-string" gmt="yes/no" language="0/2/language-id"&gt; </span> </p> </td> 
   <td colname="col2"> <p>傳回目前結果的日期。 如果沒有與當前結果關聯的日期，則顯示可選的「無」文本值。 如果未提供可選的「無」值，則如果沒有與當前結果關聯的日期，則顯示「無日期」文本。 </p> <p>「date-format」屬性採用UNIX樣式的日期格式字串，如「%A, %B %d, %Y」（對於「2016年7月25日星期一」）。 "gmt"預設為"yes"，並控制日期字串的時間部分應以GMT("yes")或帳戶的時區("no")輸出。 </p> <p>「語言」屬性控制輸出日期字串的語言和地區設定慣例。 "0"（預設值）表示「使用帳戶語言」。 「2」意指「使用檔案語言」。 「語言」值「1」保留供日後使用。 任何其他「語言」值都會解讀為特定語言識別碼，例如，「en_US」意指「英文（美國）」。 </p> <p>選用的length屬性可用來限制顯示的字串長度，預設值為80個字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-size&gt; </span> </p> </td> 
   <td colname="col2"> <p>傳回目前結果的大小（以位元組為單位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-url length="XX" encoding="html/javascript/json/perl/url/none" &gt; </span> </p> </td> 
   <td colname="col2"> <p>傳回目前結果的URL。 </p> <p>使用可選 <span class="codeph"> 長度屬 </span> 性來限制顯示的字串長度，預設值為不限個字元。 </p> <p>編碼 <span class="codeph"> 屬 </span> 性是選用的，可以使用HTML編碼、Javascript編碼、Perl編碼或無來編碼輸出字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-url-path-query length="XX"&gt; </span> </p> </td> 
   <td colname="col2"> <p>傳回包含目前結果URL問號的路徑和查詢部分。 </p> <p>使用可選 <span class="codeph"> 長度屬 </span> 性來限制顯示的字串長度，預設值為不限個字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-context length="XX" encoding="html/javascript/json/perl/url/none" &gt; </span> </p> </td> 
   <td colname="col2"> <p>傳回搜尋詞的下一行內容。 相關詞語以粗體顯示。 重複呼叫此標籤，以顯示目前結果的多個上下文行。 </p> <p>使用可選 <span class="codeph"> 長度 </span> 屬性來限制顯示的字串長度，預設值為80個字元。 如果 <span class="codeph"> 此標籤 </span> 由包含長度屬性的 <span class="codeph"> &lt;search-if-context&gt;或 </span> &lt;search-if-any-context&gt;標籤集包圍，則會忽略 <span class="codeph"></span> length屬性。 </p> <p>編碼 <span class="codeph"> 屬 </span> 性是選用的，它可以使用HTML編碼（預設值）、Javascript編碼、Perl編碼或無來編碼輸出字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field name="field-name" length="XX" length="text" date-format="date-format-string" gmt="yes/no" language="0/2/language-id" encoding="html/javascript/json/perl/url/none"引號="yes/no" unies=" mules=" miles/mes/mes/kies/kies/kies/kies/kies=" ses/kires/kres=" ses/" separes=" </span> </p> </td> 
   <td colname="col2"> <p>此進階標籤會顯示目前結果的中繼資料欄位(url、標題、desc、keys、target、body、alt、date、charset，以及名稱屬性中指定之「選項 <span class="uicontrol"> &gt; </span> Metadata <span class="uicontrol"> &gt;定義」下定義的語言或欄位) </span><span class="codeph"></span> 內容。 例如: </p> <p> <span class="codeph"> &lt;search-display-field name="title" length="70" none="no title"&gt; </span> </p> <p>輸出搜尋結果的頁面標題。 如果指定 <span class="codeph"> 了 </span> 可選的none屬性，則僅當沒有與欄位關聯的內容時，其值才會顯示在結果頁上。 </p> <p>只有 <span class="codeph"> 指定欄位的內容類型為date-format時，日 </span>期、 <span class="codeph"> gmt和語言屬性才 </span><span class="codeph"></span><span class="codeph"></span>相關。 </p> <p>日期 <span class="codeph"> 格式屬 </span> 性採用UNIX樣式的日期格式字串，如 <span class="codeph"> %A、%B %d、%Y </span> （2016年7月25日星期一）。 <span class="codeph"> gmt </span> 預設 <span class="codeph"> 為 </span> yes，並控制日期字串的時間部分是以GMT( <span class="codeph"> yes </span>)或帳戶的時區( <span class="codeph"> no </span>)輸出。 </p> <p>請參閱 <a href="../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4" type="section" format="dita" scope="local"> 日期格式字串</a>。 </p> <p>語言 <span class="codeph"> 屬 </span> 性控制輸出日期字串的語言和地區設定慣例。 <span class="codeph"> 0 </span> （預設值）表示「使用帳戶語言」。 <span class="codeph"> 2 </span> 意指「使用檔案語言」。 語 <span class="codeph"> 言 </span> 值 <span class="codeph"> 1保留 </span> 供將來使用)。 任何其 <span class="codeph"> 他語 </span> 言值都會解讀為特定語言識別碼，例如 <span class="codeph"> en_US </span> 代表「英文（美國）」。 </p> <p>請參閱 <a href="../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911" type="section" format="dita" scope="local"> 語言識別碼</a>。 </p> <p>選用的 <span class="codeph"> length屬 </span> 性可用來限制顯示的字串長度，預設值為80個字元。 </p> <p>可選的 <span class="codeph"> 編 </span> 碼屬性控制輸出是否為HTML編碼、JavaScript編碼、Perl編碼、URL編碼或未編碼，以便在結果頁面上輸出。 編碼的預設 <span class="codeph"> 值 </span> 為 <span class="codeph"> html </span>。 通常，您不需要指定編碼屬性。 </p> <p>可選的 <span class="codeph"> 引號屬 </span> 性控制單個項輸出是否用雙引號(或單引號，如果 <span class="codeph"> encoding=perl </span>)。 引號的預 <span class="codeph"> 設值 </span> 為 <span class="codeph"> no </span>。 </p> <p>選用的逗 <span class="codeph"> 號屬 </span> 性會控制個別輸出的項目是否以逗號分隔。 逗號的預 <span class="codeph"> 設值 </span> 為 <span class="codeph"> yes </span>。 非清 <span class="codeph"> 單類 </span> 型欄位會忽略逗號屬性。 </p> <p>可選單 <span class="codeph"> 位屬 </span> 性控制應用於鄰近搜索輸出欄位的距離單位。 單位的預設值 <span class="codeph"> 由與 </span> 給定鄰近搜索輸出欄位相關聯的位置類型欄位的「預設單位」設定確定。 </p> <p>請參 <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> 閱關於鄰近搜尋</a>。 </p> <p>可選的 <span class="codeph"> 分隔符 </span> 屬性定義在清單類型欄位的輸出值之間插入的單字元或分隔符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-values name="field-name"&gt;...&lt;search-display-field-values&gt; </span> </p> </td> 
   <td colname="col2"> <p>此標籤會建立一個循環，用於枚舉目前結果的中繼資料欄位值(url、title、desc、keys、target、body、alt、date、charset和語言或欄位，這些欄位定義在「選項」 <span class="uicontrol"> &gt; </span> 「中繼資料 <span class="uicontrol"> &gt; </span><span class="uicontrol"></span>定義」下。 請勿將此標籤巢狀內嵌在另 <span class="codeph"> 一個&lt;search-display-field-values&gt;標籤 </span> 中。 name屬 <span class="codeph"> 性 </span> 指定包含要枚舉的值的欄位的名稱。 此標籤對於已勾選「允許清單」屬性的欄位最有用(在「選項」&gt;「中繼資料」 <span class="uicontrol"></span><span class="uicontrol"></span><span class="uicontrol"></span><span class="uicontrol"></span>&gt;「定義」下)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-value date-format="date-format-string" gmt="yes/no" language="0/language-id" encoding="html/javascript/json/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此標籤會輸出目前 <span class="uicontrol"> &lt;search-display-field-values&gt;循環迭代的中繼資料欄位值(url、title、desc、keys、target、body、alt、date、charset和語言或欄位，這些欄位定義在「選項」( </span> Options)&gt; <span class="uicontrol"> 「中繼資料 </span> &gt; <span class="uicontrol"> 定義」(Metadata </span><span class="codeph"></span> &gt; Definitions)下。 此標籤僅在 <span class="codeph"> &lt;search-display-field-values&gt;回圈內有 </span> 效。 僅當 <span class="codeph"> &lt;search-display- </span>language&gt;附加的&lt;search-field-values&gt;標籤中指定的欄位名的內容類型為日期- <span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span>display-language時，日期格式、格林尼治屬性和格林尼治屬性才相關。 日期 <span class="codeph"> 屬性採 </span> 用UNIX樣式日期格式字串，如 <span class="codeph"> "%A, </span>%B <span class="codeph"></span><span class="codeph"></span><span class="codeph"></span>%d Format "（2016年7月25日星期一）。 預設 <span class="codeph"> 為「是」 </span> 屬性，並控制日期字串的時間部分是以GMT（是）輸出，還是以帳戶的時區( <span class="codeph"> 無)輸出 </span><span class="codeph"></span><span class="codeph"></span>。 </p> <p>語言 <span class="codeph"> 屬 </span> 性控制輸出日期字串的語言和地區設定慣例。 <span class="codeph"> 0 </span> （預設值）表示「使用帳戶語言」。 任何其 <span class="codeph"> 他語 </span> 言值都會解讀為特定語言識別碼，例如 <span class="codeph"> en_US </span> 代表「英文（美國）」。 </p> <p>可選的 <span class="codeph"> 編 </span> 碼屬性控制輸出是否為HTML編碼、JavaScript編碼、Perl編碼、URL編碼或未編碼，以便在結果頁面上輸出。 編碼的預設 <span class="codeph"> 值 </span> 為 <span class="codeph"> html </span>。 通常，您不需要指定編碼屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-value-count name="field-name"&gt; </span> </p> </td> 
   <td colname="col2"> <p>輸出在使用name屬性指定之中繼資料欄位(url、title、desc、keys、target、body、alt、date、charset和語言或欄位，以及在 <span class="uicontrol"> Options </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"></span>Definitions下定義的值總數。 此標籤可顯示在結果循環中的任何位置。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-value-counter&gt; </span> </p> </td> 
   <td colname="col2"> <p>輸出當前&lt;search-display-field-values&gt;循環迭代的序數計數器（1、2、3等） <span class="codeph"></span> 。 此標籤僅在 <span class="codeph"> &lt;search-display-field-values&gt;回圈內有 </span> 效。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-dynamic-facet-fields&gt; </span> </p> </td> 
   <td colname="col2"> <p>開始此搜尋所傳回之任何動態Facet欄位的循環內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-dynamic-facet-field-name&gt; </span> </p> </td> 
   <td colname="col2"> <p>輸出此循環迭代的當前動態Facet-field的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release on October 30 2014--> <span class="codeph"> &lt;search-result-trace encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>輸出與當前結果的放置有關的資訊，例如影響結果位置的任何基於結果的操作。 </p> <p>此標籤的輸出格式為JSON，如下列範例所示： </p> <p> <code> { 
      &nbsp;&nbsp;"sliceID":&nbsp;5, 
      &nbsp;&nbsp;"indexID":&nbsp;5894, 
      &nbsp;&nbsp;"finalScore":&nbsp;98.5, 
      &nbsp;&nbsp;"dynamicScore":&nbsp;15.3, 
      &nbsp;&nbsp;"staticScore":&nbsp;55.456, 
      &nbsp;&nbsp;"position":&nbsp;1, 
      &nbsp;&nbsp;"rbtaActionListID":&nbsp;117, 
      &nbsp;&nbsp;"rbtaActionID":&nbsp;57 
      } </code> </p> 
    <!--<p> Results added to the results set by way of <codeph>rbta</codeph> have a "naturalPosition" value of -1. </p>--> <p>編碼 <span class="codeph"> 屬 </span> 性是可選的；預設值為 <span class="codeph"> html </span>。 </p> <p> <p>注意： 僅當使用核心搜索查詢參 <span class="codeph"> 數指定sp_trace=1 </span> 時，此標籤才具有輸出。 </p> </p> <p>請參閱後端搜尋CGI參數中 <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" format="dita" scope="local"> 的表格第48行</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 結果循環條件標籤 {#section_35C367969E384A06A9865E388F1F9360}

下列標籤有條件地包含它們之間的HTML。

請參 [閱關於結果循環標籤](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629)。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-title&gt;...&lt;/search-if-title&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-title&gt;...&lt;/search-if-not-title&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果下次呼叫 <span class="codeph"> &lt;search-title&gt;時，從檔案標題傳回（或未傳回）文字， </span> 則這些標籤會包含它們之間的HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-description length="XX"&gt; .../search-if-description&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-description&gt;...&lt;/search-if-not-description&gt; </span> </p> </td> 
   <td colname="col2"> <p> 如果下次對 <span class="codeph"> &lt;search-description&gt;的呼叫從檔案說明傳回（或未傳回）文字，這些標籤會包含 </span> 它們之間的HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-bodytext&gt;...&lt;/search-if-bodytext&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-bodytext&gt;...&lt;/search-if-not-bodytext&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果下次呼叫 <span class="codeph"> &lt;search-bodytext&gt;時，從檔案內文傳回（或未傳回）文字， </span> 則這些標籤會包含它們之間的HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-context length="XX"&gt; ...&lt;/search-if-context&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-context&gt;...&lt;/search-if-not-context&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果下次呼叫 <span class="codeph"> &lt;search-context&gt;傳回（或未傳回）非空白的上下文字串，則這些標籤 </span> 會包含它們之間的HTML。 length屬性會覆寫任何內含的 <span class="codeph"> &lt;search-context&gt;標籤上的length屬 </span> 性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-any-context length="XX"&gt; .../search-if-any-context&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-any-context&gt;...&lt;/search-if-not-any-context&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果有（或不有）與結果相關聯的上下文字串，這些標籤會包含它們之間的HTML。 length屬性會覆寫任何內含的 <span class="codeph"> &lt;search-context&gt;標籤上的length屬 </span> 性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-score lower="XX" upper="yy" rank="dynamic/static/dynamic-raw/static-raw/final-raw"&gt; ...&lt;/search-if-score&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-score lower=XX upper=yy rank="dynamic/static"&gt; ...&lt;/search-if-not-score&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果目前結果的分數介於XX和YY之間（或不在），這些標籤會包含它們之間的HTML。 對於新增項目符號或圖形，以顯示結果的相關性非常有用。 如果您已在「選項」 <span class="uicontrol"> &gt; </span> 「中繼資料 <span class="uicontrol"> &gt; </span> Y」下定義排名類型欄位，則可將排名屬性設定為動態( <span class="uicontrol"></span><span class="codeph"></span>&lt;search-if-score rank="dynamic" lower=XX upper=YY&gt; Exper Light)，以檢查動態頁面排名。 您可以將排名屬性設為靜態( <span class="codeph"> &lt;search-if-score rank="static" lower=XX upper=YY&gt; </span>)，以檢查靜態頁面排名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-field name="field-name" value="value"&gt; ...&lt;/search-if-field&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-field name="field-name" value="value"&gt; ...&lt;/search-if-not-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>這些進階標籤會根據「名稱」屬性中指定的欄位是否包含內容，在它們之間包含HTML。 如果指定了可選的"value"屬性，則標籤會根據給定值是否與當前結果中欄位的值匹配（或不匹配），在它們之間包含HTML。 這些標籤僅在結果循環( <span class="codeph"> &lt;search-results&gt;和 </span><span class="codeph"> &lt;/search-results&gt;標籤之間)中 </span> 運作。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 結果循環錨點連結標籤 {#section_C5FAEF520E9E42ADAD1F90651922AA02}

請參 [閱關於結果循環標籤](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629)。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-link target="frame-name" hbx-enable="yes/no" hbx-linkid-name="field-name" hbx-linkid-none="text" hbx-linkid-length="XX" &gt;...&lt;/search-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>這對標籤會在它們之間的HTML周圍建立錨點連結。 點按連結時，會顯示結果頁面。 選用的target屬性會指定可畫格瀏覽器應顯示結果頁面的指定視窗。 </p> <p>將hbx-enable屬性設為"yes"，以運用HBX提供的分析。 將hbx-linkid-name設為您要追蹤的中繼資料欄位名稱。 例如，若要依SKU編號追蹤搜尋結果，請將hbx-linkid-name設為包含SKU資訊的中繼資料欄位名稱。 </p> <p>目前不支援日期類型欄位。 hbx-linkid-name的值會附加至產生之錨點的連結ID。 每當命名的Meta-data欄位空白時，hbx-linkid-none屬性的值會附加至連結ID。 hbx-linkid-length的值會限制從Meta標籤擷取和顯示的字元數。 預設字元數為12。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-smart-link target="frame-name" hbx-enable="yes/no" hbx-linkid-name="field-name" hbx-linkid-none="text" hbx-linkid-length="XX"&gt;...&lt;/search-smart-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>這對標籤類似 <span class="codeph"> &lt;search-link&gt; ...&lt;/search-link&gt;標 </span> 記。 按一下產生的錨點連結時，會顯示結果頁面，但頁面會捲動至結果前的最接近錨點標籤。 對於PDF連結，Acrobat檢視器會顯示包含結果的頁面。 選用的target屬性會指定可畫格瀏覽器應顯示結果頁面的指定視窗。 </p> <p>將hbx-enable屬性設為"yes"，以運用HBX提供的分析。 將hbx-linkid-name設為您要追蹤的中繼資料欄位名稱。 例如，若要依SKU編號追蹤搜尋結果，請將hbx-linkid-name設為包含SKU資訊的中繼資料欄位名稱。 </p> <p>目前不支援日期類型欄位。 hbx-linkid-name的值會附加至產生之錨點的連結ID。 每當命名的Meta-data欄位空白時，hbx-linkid-none屬性的值會附加至連結ID。 hbx-linkid-length的值會限制從Meta標籤擷取和顯示的字元數。 預設字元數為12。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-link-extension&gt;...&lt;/search-if-link-extension&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-link-extension&gt;...&lt;/search-if-not-link-extension&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果值屬性指定與結果的URL結尾相符的副檔名，這些標籤會包含它們之間的HTML。 此標籤對於根據連結副檔名將圖形加入搜尋結果中非常有用。 value屬性是一個或多個副檔名（分隔空格）的清單，如下所示：VALUE="。pdf"或VALUE="。html .htm"。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 循環位置條件標籤 {#section_E0C29DDA09E043C9A396F36334F05EBB}

下列標籤有條件地包含它們之間的文字。 它們只能出現在「循環」標籤中：&lt; `search-results>` and `<search-field-values>`它們用於測試當前結果在結果集中的位置。

請參 [閱關於結果循環標籤](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629)。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-first&gt;...&lt;/search-if-first&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-first&gt;...&lt;/search-if-not-first&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果目前的結果是（或不是）頁面上的第一個結果(在 <span class="codeph"> &lt;search-results&gt; </span>)或第一個欄位值(在 <span class="codeph"></span>&lt;search-field-values&gt;內使用)，這些標籤會包含它們之間的文字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-last&gt;...&lt;/search-if-last&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-last&gt;...&lt;/search-if-not-last&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果目前的結果是（或不是）頁面上的最後一個結果(在 <span class="codeph"> &lt;search-results&gt; </span>)或最後一個欄位值(在 <span class="codeph"></span>&lt;search-field-values&gt;內使用)，這些標籤會包含兩者之間的文字。 此標籤可用於在結果之間插入分隔符。 例如，這會在結果之 <span class="codeph"> 間插入&lt;hr&gt; </span> 標籤： </p> <p> <code class="syntax html"> &lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&lt;search-lt&gt;tr&lt;search-if-alt&gt;&nbsp;class="alt"&lt;/search-if-alt&gt;&lt;search-gt&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td&gt;&lt;search-url&gt;&lt;/td&gt; 
      &nbsp;&nbsp;&nbsp;&lt;/tr&gt; 
      &lt;/search-results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-inner&gt;...&lt;/search-if-inner&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-inner&gt;...&lt;/search-if-not-inner&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果目前的結果不是頁面上的第一個或最後一個結果(在 <span class="codeph"> &lt;search-results&gt; </span>)，或不是第一個或最後一個欄位值(在 <span class="codeph"></span>&lt;search-field-values&gt;內使用)，這些標籤會包含它們之間的文字。 標籤的not版本會測試結果是第一個還是最後一個。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-alt&gt;...&lt;/search-if-alt&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-alt&gt;...&lt;/search-if-not-alt&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果目前的結果是（或不是）頁面上的替代結果(在 <span class="codeph"> &lt;search-results&gt; </span>)或替代欄位值(在 <span class="codeph"></span>&lt;search-field-values&gt;內使用)，這些標籤會包含它們之間的文字。 「替代」結果為頁面上的第二、第四、第六等。 此示例將不同的類應用於替代表行。 請注意使用 <span class="codeph"> &lt;search-lt&gt; </span><span class="codeph"> &lt;search-gt&gt; </span> ，以允許將&lt;search-if-alt&gt;標籤置於 <span class="codeph"></span><span class="codeph"></span> &lt;tr&gt;標籤內。 </p> <p> <code class="syntax html"> &nbsp;&nbsp;&nbsp;&nbsp;&lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-lt&gt;tr&lt;search-if-alt&gt;&nbsp;class="alt"&lt;/search-if-alt&gt;&lt;search-gt&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td&gt;&lt;search-url&gt;&lt;/td&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/tr&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-even&gt;...&lt;/search-if-even&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-even&gt;...&lt;/search-if-not-even&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果目前的結果是（或不是）偶數編號的結果(在 <span class="codeph"> &lt;search-results&gt; </span>)或偶數編號的欄位值(在 <span class="codeph"></span>&lt;search-field-values&gt;中使用)，這些標籤會包含它們之間的文字。 如果搜索結果的&lt;search-index&gt;值為偶數，則 <span class="codeph"> 搜索結果 </span> 的編號為偶數。 換句話說，如果它在整個結果集中的位置是均勻的。 這可能與 <span class="codeph"> &lt;search-if-alt&gt;不同，&lt;search-if-alt&gt; </span> 會測試結果在頁面上的位置，而不是在整個結果集中。 以下兩個表格說明了差異： </p> </td> 
  </tr> 
 </tbody> 
</table>

### 第一頁，sp_n=1

<table>  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>索引 </p> </th> 
   <th colname="col2" class="entry"> <p>結果 </p> </th> 
   <th colname="col3" class="entry"> <p>扯平？ </p> </th> 
   <th colname="col4" class="entry"> <p>Alt? </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>第一個結果 </p> </td> 
   <td colname="col3"> <p>無 </p> </td> 
   <td colname="col4"> <p>無 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>第二個結果 </p> </td> 
   <td colname="col3"> <p>是 </p> </td> 
   <td colname="col4"> <p>是 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>第三個結果 </p> </td> 
   <td colname="col3"> <p>無 </p> </td> 
   <td colname="col4"> <p>無 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>第四個結果 </p> </td> 
   <td colname="col3"> <p>是 </p> </td> 
   <td colname="col4"> <p>是 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>第五個結果 </p> </td> 
   <td colname="col3"> <p>無 </p> </td> 
   <td colname="col4"> <p>無 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 稍後的頁面，sp_n=10

<table>  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>索引 </p> </th> 
   <th colname="col2" class="entry"> <p>結果 </p> </th> 
   <th colname="col3" class="entry"> <p>扯平？ </p> </th> 
   <th colname="col4" class="entry"> <p>Alt? </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>10 </p> </td> 
   <td colname="col2"> <p>第十個結果 </p> </td> 
   <td colname="col3"> <p>是 </p> </td> 
   <td colname="col4"> <p>無 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>11 </p> </td> 
   <td colname="col2"> <p>第11個結果 </p> </td> 
   <td colname="col3"> <p>無 </p> </td> 
   <td colname="col4"> <p>是 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>12 </p> </td> 
   <td colname="col2"> <p>第十二個結果 </p> </td> 
   <td colname="col3"> <p>是 </p> </td> 
   <td colname="col4"> <p>無 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>13 </p> </td> 
   <td colname="col2"> <p>第13個結果 </p> </td> 
   <td colname="col3"> <p>無 </p> </td> 
   <td colname="col4"> <p>是 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>14 </p> </td> 
   <td colname="col2"> <p>第十四個結果 </p> </td> 
   <td colname="col3"> <p>是 </p> </td> 
   <td colname="col4"> <p>無 </p> </td> 
  </tr> 
 </tbody> 
</table>

最後，請注意， `<search-if-even>` 由於不分頁欄 `<search-if-alt>` 位值，因此搜尋欄位值一律相同。

## 欄位值清單標籤 {#section_D3298B5F976447DBA0032B883DCC91B1}

下列進階標籤會輸出欄位值，以及整組搜尋結果的相關資料。 這些標籤僅針對搜索查詢中的 `sp-sfvl-field` CGI參數指定的欄位產生輸出。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-list name="field-name" quotes="yes/no"逗號="yes/no" data="values/counts/results" separator="X" sortby="none/values/counts/results" max-items="XX" date-format-string" gmt=" gmt="yes/"ye/nage/no" languag=" yes/ys/languguage/javaguguge/javasuge/javaguage-id=" enage=" enage/javascript=" enage/javasugunage-id=" enco=" enagucasugunage/javagugucasinage-id=" enco="json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此標籤顯示整個結果集中唯一欄位值、值計數或結果計數的清單。 </p> <p>此標籤僅產生由搜索查詢中 <span class="codeph"> sp_sfvl_field </span> CGI參數指定的欄位的輸出。 可選的"quotes"屬性控制個別項目輸出是否用雙引號（或單引號，如果encoding=perl）括住。 「引號」的預設值為「yes」。 選用的「逗號」屬性可控制個別輸出項目是否以逗號分隔。 「逗號」的預設值為「是」。 可選的"data"屬性控制每個唯一欄位值是輸出(data="values")、每個唯一欄位值的總計數是輸出(data="counts")，還是輸出包含每個唯一值(data="results")的結果數。 「data」的預設值為「values」。 對於非清單類型欄位，data="counts"和data="results"是等同的。 分隔符屬性定義要在輸出值之間插入的單個字元或分隔符。 選用的「sortby」屬性控制輸出順序；sortby="none"意指無特定順序， sortby="values"意指依欄位值排序（依欄位的排序屬性以遞增或遞減順序排序）, sortby="counts"意指依欄位值計數的遞減順序排序，而sortby="results"意指依含每個值之結果數的遞減順序排序。 </p> <p>請注意，sortby="counts"和sortby="results"對於非清單類型欄位是等效的。 選用的「最大項目」屬性會限制要輸出的項目數。 「最大項目」的預設值為-1，這表示「輸出所有項目」。 </p> <p>最大項目的絕對限制為100。 「日期格式」、「gmt」和「語言」屬性只有在指定欄位的內容類型為「日期」時才相關。 「date-format」屬性採用UNIX樣式的日期格式字串，如「%A, %B %d, %Y」（對於「2016年7月25日星期一」）。 "gmt"預設為"yes"，並控制日期字串的時間部分應以GMT("yes")或帳戶的時區("no")輸出。 </p> <p>請參閱 <a href="../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4" type="section" format="dita" scope="local"> 日期格式字串</a>。 </p> <p>「語言」屬性控制輸出日期字串的語言和地區設定慣例。 "0"（預設值）表示「使用帳戶語言」。 任何其他「語言」值都會解讀為特定語言識別碼，例如，「en_US」意指「英文（美國）」。 可選的「encoding」屬性控制輸出字串字元是否為HTML編碼、JavaScript編碼、Perl編碼、URL編碼或未編碼，以便在結果頁面上輸出。 「encoding」的預設值為「html」。 </p> <p>請參閱 <a href="../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911" type="section" format="dita" scope="local"> 語言識別碼</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-list-count name="field-name" value="field-value" results="yes/no"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此標籤會顯示特定搜尋欄位值清單的計數資訊。 此標籤有三種不同的用途。 如果僅提供"name"屬性，此標籤會輸出整個結果集中指定欄位的唯一值數。 如果同時提供"name"和"value"屬性，此標籤會輸出整個結果集內給定值的總計數(for results="no")，或包含整個結果集中給定值的總計數(for results="yes")。 「results」的預設值為「no」。 注意：對於非清單類型欄位，results="yes"和results="no"是相等的。 如果未提供"value"屬性，則會忽略"results"的值。 此標籤僅產生由搜索查詢中 <span class="codeph"> sp-sfvl-field </span> CGI參數指定的欄位的輸出。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-field-value-list-count name="field-name" value="field-value"&gt;...&lt;/search-if-field-value-list-count&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-field-value-list-count name="field-name" value="field-value"&gt;...&lt;/search-if-not-field-value-list-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果具有指定屬性的 <span class="codeph"></span> &lt;search-field-value-list-count name="field-name" value="field-value"&gt;等同呼叫會（或不會）傳回大於零的值，則這些標籤會在它們之間顯示HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-single-field-value-list-count name="field-name"&gt;...&lt;/search-if-single-field-value-list-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果具有指定屬性的 <span class="codeph"></span> &lt;search-field-value-list-count name="field-name" value="field-value"&gt;等等呼叫會（或不會）傳回單一值，這些標籤會顯示它們之間的內容。 這通常用於帳戶使用刻面槽時。 有了Facet槽，您通常只想在關聯的名稱槽包含單一項目時顯示值槽。 在傳輸範本中執行此檢查比在表現層中執行檢查更有效。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 欄位值清單循環標籤 {#section_0717FA09F0FC449CB916883B0500A60E}

下列進階標籤會使用循環結構，從整個搜尋結果集列舉和輸出欄位值及相關資料。 這些標籤僅針對搜索查詢中的 `sp-sfvl-field` CGI參數指定的欄位產生輸出。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-values name="field-name" sortby="none/values/counts/results" max-items="XX"&gt;...&lt;/search-field-values&gt; </span> </p> </td> 
   <td colname="col2"> <p>此標籤會建立一個循環，用於枚舉整個結果集中特定欄位的欄位值和相關資料。 請勿將此標籤巢狀內嵌在另 <span class="codeph"> 一個&lt;search-field-values&gt;標籤 </span> 中。 "name"屬性指定包含要枚舉的值的欄位的名稱。 可選的"sortby"屬性控制枚舉順序："none"表示沒有特定順序，"values"表示依欄位值排序（依欄位的排序屬性以遞增或遞減順序排序）,sortby="counts"表示依欄位值計數的遞減順序排序，sortby="results"表示依含每個值之結果數的遞減順序排序。 </p> <p>請注意，sortby="counts"和sortby="results"對於非清單類型欄位是等效的。. 可選的「最大項目」屬性將迭代次數限制為給定值。 「最大項目」的預設值為-1，這表示「枚舉所有值」。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value date-format="date-format-string" encoding="html/javascript/json/url/none" gmt="yes/no" language="0/language-id"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此標籤會輸出目前&lt;search-field-values&gt;循環小版本的欄位值。 此標籤僅在 <span class="codeph"> &lt;search-field-values&gt;回圈內有 </span> 效。 只有在&lt;search-field-values&gt;標籤中指定欄位名稱的內容類型為"date"時，「date-format」、「gmt」和「language」屬性才相關。 「date-format」屬性採用UNIX樣式的日期格式字串，如「%A, %B %d, %Y」（對於「2020年7月25日星期一」）。 </p> <p>請參閱 <a href="../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4" type="section" format="dita" scope="local"> 日期格式字串</a>。 </p> <p>可選的「encoding」屬性控制輸出字串字元是否為HTML編碼、JavaScript編碼、Perl編碼、URL編碼或未編碼，以便在結果頁面上輸出。 「encoding」的預設值為「none」。 通常，您不需要指定編碼屬性。 "gmt"預設為"yes"，並控制日期字串的時間部分應以GMT("yes")或帳戶的時區("no")輸出。 「語言」屬性控制輸出日期字串的語言和地區設定慣例。 "0"（預設值）表示「使用帳戶語言」。 任何其他「語言」值都會解讀為特定語言識別碼，例如，「en_US」意指「英文（美國）」。 </p> <p>請參閱 <a href="../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911" type="section" format="dita" scope="local"> 語言識別碼</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-count results="yes/no"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此標籤會輸出與目前&lt;search-field-values&gt; <span class="codeph"> 循環小版本相關 </span> 的計數。 輸出計數是包含欄位值的整個結果集中的結果數(results="yes")，或整個結果集中欄位值的總計。 「results」的預設值為「no」。 </p> <p>對於非清單類型欄位，results="yes"和results="no"是相等的。 此標籤僅在 <span class="codeph"> &lt;search-field-values&gt;回圈內有 </span> 效。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-counter&gt; </span> </p> </td> 
   <td colname="col2"> <p>此標籤會輸出目前&lt;search-field-values&gt;循 <span class="codeph"> 環迭代的序 </span> 數計數器。 此標籤僅在 <span class="codeph"> &lt;search-field-values&gt;回圈內有 </span> 效。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 建議標籤 {#section_C28EB8B4F7DC4E278A0F143BCFEEB1AC}

Sempless提供方便使用的「您是指？」 服務，以建議替代搜尋詞。 例如，如果使用者拼錯搜尋詞，建議可協助使用者建議正確的拼字來尋找結果。 系統也可以建議相關關鍵字，協助使用者發現結果。 產生建議時，建議服務會使用兩本字典：一個是根據帳戶語言(在 **[!UICONTROL Indexing]** > **[!UICONTROL Words and Languages]** > **[!UICONTROL Language]**)，另一個是根據帳戶索引中的關鍵字唯一建立。

>[!NOTE]
>
>「建議」服務不適用於中文、日文或韓文。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-expensions&gt;...&lt;/search-if-expeliations&gt; </span> </p> </td> 
   <td colname="col2"> <p>使用任何「建議」範本標籤來包住這些標籤，例如 <span class="codeph"> &lt;search-seccuption&gt; </span><span class="codeph"> 、 </span>&lt;search-seccuption-link&gt;等等。 如果搜尋產生建議，搜尋引擎會輸出並處理開啟與關閉標籤之間的一切。 如果搜尋未產生建議，則不會輸出任何巢狀內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-expensions&gt;...&lt;/search-expeliations&gt; </span> </p> </td> 
   <td colname="col2"> <p>此標籤會產生「建議」回圈，其中包含建議搜尋詞的清單（例如，「打算」、「預期」和「打算」，以原始輸入為「意向」的查詢）。 產生詞語清單時，搜尋引擎最多重複5次巢狀內嵌的HTML和／或範本標籤，這是建議的最大數目。 使用count屬性來指定產生的建議數（介於0-5之間）。 </p> <p>&lt;search- <span class="codeph"> explications&gt;標 </span> 簽可在頁面上多次顯示，以重複建議清單。 根據每個產量的結果數來排序多個建議。 </p> <p>在開啟 <span class="codeph"> 和關閉&lt;search-if-explications&gt;標籤之 </span> 間巢狀內嵌&lt;search-explications&gt;標籤 <span class="codeph"></span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-seccommendation-link&gt;...&lt;/search-seckument-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>此標籤會使用選取的建議搜尋詞來產生原始搜尋查詢的連結，而非原始搜尋詞。 標籤接受並只列印任何HTML屬性，例如類別、目標和樣式。 標籤也可以接受URL屬性，其值將用作所產生連結的基本URL。 標籤只能顯示在 <span class="codeph"> &lt;search-expiliations&gt;回 </span> 圈中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-seccument-text/&gt; </span> </p> </td> 
   <td colname="col2"> <p>此標籤會列出目前建議的查詢詞語（例如，「打算」原本輸入為「意向」的查詢）。 標籤沒有屬性，只能顯示在 <span class="codeph"> &lt;search-expiliations&gt;循 </span> 環中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-not-expensions&gt;...&lt;/search-if-not-expeliations&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果搜尋未產生任何建議，搜尋引擎會輸出並處理開啟與關閉標籤之間的一切。 如果搜尋產生建議，則不會輸出任何巢狀內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if[-not]-first-sembuction&gt;...&lt;/search-if[-not]-first-seccommendation&gt; </span> </p> </td> 
   <td colname="col2"> <p>這些條件標籤會根據建議回圈中建議的詞語是否是第一個詞語，在它們之間包含HTML。 標籤必須出現在開啟和關閉 <span class="codeph"> &lt;search-seccommendation&gt;標籤之 </span> 間。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if[-not]-last-sembuction&gt;...&lt;/search-if[-not]-last-seccommendation&gt; </span> </p> </td> 
   <td colname="col2"> <p>這些條件標籤會根據建議回圈中建議的詞語是否為最後一個詞語，在它們之間包含HTML。 標籤必須出現在開啟和關閉 <span class="codeph"> &lt;search-seccommendation&gt;標籤之 </span> 間。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-seccument-index&gt; </span> </p> </td> 
   <td colname="col2"> <p>此標籤會傳回目前建議搜尋詞的數值索引。 標籤必須出現在開啟和關閉 <span class="codeph"> &lt;search-seccommendation&gt;標籤之 </span> 間。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-seckument-total&gt; </span> </p> </td> 
   <td colname="col2"> <p>此標籤會傳回產生的建議搜尋詞總數。 標籤必須出現在開啟和關閉 <span class="codeph"> &lt;search-seccommendation&gt;標籤之 </span> 間。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-seckument-result-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>此標籤會傳回建議搜尋詞的結果總數。 標籤必須出現在開啟和關閉 <span class="codeph"> &lt;search-seccommendation&gt;標籤之 </span> 間。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範本字串標籤 {#section_67E3D529661F4F03A1FF469D9D658CAF}

下列標籤會在範本中該點將字串輸出至HTML。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-body&gt; </span> </p> </td> 
   <td colname="col2"> <p>HTML body標籤，內含「基本外觀」區段在「範本」連結下所設定的任何「搜尋連結色彩」設定。 新增背景屬性至此標籤，以在結果頁面上顯示背景影像。 任何新增至此標籤的顏色屬性都會覆寫「基本外觀」區段所設定的「搜尋連結顏色」設定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-header&gt; </span> </p> </td> 
   <td colname="col2"> <p>在「範本」連結下的「基本外觀」區段中設定的「搜尋結果標題」HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-cdata&gt;...&lt;/search-cdata&gt; </span> </p> </td> 
   <td colname="col2"> <p>search-cdata標籤將替換為其XML等效標籤： <span class="codeph"> &lt;search-cdata&gt; </span> 已替換為 <span class="codeph"> &lt;![CDATA["和&lt;/search-cdata&gt;標 </span> 記被" <span class="codeph"> ]]&gt; </span>"替換。 XML剖析器不會剖析開啟與關閉標籤之間的任何資訊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-query query-number="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>訪客輸入的查詢。 進階的可選「query-number」屬性可控制此標籤輸出的編號查詢字串。 例如， <span class="codeph"> &lt;search-query query-number=1&gt; </span> 會輸出 <span class="codeph"> sp_q_1 </span> cgi參數的內容。 如果未指定"query-number"，或如果query-number是"0"，則輸出主查詢( <span class="codeph"> sp_q </span>)。 可選的「encoding」屬性控制輸出是否為HTML編碼、JavaScript編碼、Perl編碼、URL編碼或未編碼，以便在結果頁面上輸出。 「encoding」的預設值為「html」。 通常，您不需要指定編碼屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-total&gt; </span> </p> </td> 
   <td colname="col2"> <p>此搜尋結果的總計計數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>此頁所報告的結果計數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-lower&gt; </span> </p> </td> 
   <td colname="col2"> <p>此頁面報告的第一個結果數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-upper&gt; </span> </p> </td> 
   <td colname="col2"> <p>此頁面上最後報告的結果數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-prev-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>上一頁所報告的結果數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-next-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>下一頁所報告的結果數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-time&gt; </span> </p> </td> 
   <td colname="col2"> <p>此搜索的秒數時間。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-logo&gt; </span> </p> </td> 
   <td colname="col2"> <p>為您的帳戶設定的「搜尋」標誌的HTML（如果有）。 此標誌是給予網站搜尋／銷售評分的影像 </p> <p>目前，大部分帳戶都沒有關聯的搜尋標誌。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-collection all="name"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此搜尋結果的集合。 選用的「all」屬性可用來指定代表整個網站之系列的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-form&gt; ...&lt;/search-form&gt; </span> </p> </td> 
   <td colname="col2"> <p>插入開始和結束表單標籤。 將方法和操作屬性插入begin form標籤中。 接受其他屬性，包括語言的dir="RTL"屬性，以及與JavaScript相關的"name"和"onSubmit"屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-account&gt; </span> </p> </td> 
   <td colname="col2"> <p>插入指定帳號的表單輸入標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-gallery&gt; </span> </p> </td> 
   <td colname="col2"> <p>插入指定圖庫編號的表單輸入標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-query query-number="XX"&gt; </span> </p> </td> 
   <td colname="col2"> <p>插入指定查詢字串的表單輸入標籤。 進階的可選「query-number」屬性會控制表單輸入標籤使用的編號查詢。 例如， <span class="codeph"> &lt;search-input-query query-number=1&gt; </span> 為 <span class="codeph"> sp_q_1查詢輸出表單輸入標 </span> 記。 如果未指定"query-number"或"query-number"為"0"，則會插入主 <span class="codeph"> sp_q查詢的輸 </span> 入標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-collections all="name"&gt; </span> </p> </td> 
   <td colname="col2"> <p>插入表單選擇標籤和關聯的HTML，顯示系列選擇菜單。 選用的「all」屬性可用來指定代表整個網站之系列的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-lt&gt; </span> </p> </td> 
   <td colname="col2"> <p>在結果頁面上的其他HTML或範本標籤內插入其中一個「搜尋」範本標籤的輸出。 <span class="codeph"> &lt;search-lt&gt;插 </span> 入小於字元。 使用 <span class="codeph"> &lt;search-lt&gt;和 </span><span class="codeph"> &lt;search-gt&gt; </span> 可提供逸出標籤定義的方式，以便您可以使用「搜尋」範本標籤作為屬性值。 當回應搜尋而轉譯範本時，小於號(&lt;)會取代 <span class="codeph"> &lt;search-lt&gt;標 </span> 記。 例如， <span class="codeph"> &lt;search-link&gt; </span> 等同 <span class="codeph"> 於&lt;search-lt&gt;a href="&lt;search-url&gt;"&lt;search-gt&gt; </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>20 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-gt&gt; </span> </p> </td> 
   <td colname="col2"> <p>在結果頁面上的其他HTML或範本標籤內插入其中一個「搜尋」範本標籤的輸出。 <span class="codeph"> &lt;search-gt&gt;會 </span> 插入大於字元。 使用 <span class="codeph"> &lt;search-lt&gt;和 </span> &lt;search-gt&gt; <span class="codeph"></span> 可提供逸出標籤定義的方式，以便您可以使用其他範本標籤作為屬性值。 當回應搜尋而轉譯範本時，大於號(&gt;)會取代 <span class="codeph"> &lt;search-gt&gt;標 </span> 記。 例如， <span class="codeph"> &lt;search-link&gt; </span> 等同 <span class="codeph"> 於&lt;search-lt&gt;a href="&lt;search-url&gt;"&lt;search-gt&gt; </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>21 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-param name="param-name" length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>傳回目前搜尋請求中名為"param-name"的cgi參數值。 可選的「encoding」屬性控制輸出是否為HTML編碼、JavaScript編碼、Perl編碼、URL編碼或未編碼，以便在結果頁面上輸出。 「encoding」的預設值為「html」。 通常，您不需要指定編碼屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>22 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release on October 30 2014--> <span class="codeph"> &lt;search-trace encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> 
    <!--<p>This global core search template tag outputs a representation of the submitted core search query, including any "fuzzy-search" query term expansions that happen by way of synonyms, sound-alikes, and so forth. </p>--> <p>編碼 <span class="codeph"> 屬 </span> 性是可選的；預設值為 <span class="codeph"> json </span>。 </p> <p> <p>注意： 僅當使用核心搜索查詢參 <span class="codeph"> 數指定sp_trace=1 </span> 時，此標籤才具有輸出。 </p> </p> <p>請參閱後端搜尋CGI參數中 <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" format="dita" scope="local"> 的表格第48行</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範本錨點連結標籤 {#section_3A51D27616C541E2B818CC52B2B856BA}

以下是標籤，這些標籤會使錨點連結包圍HTML。 點按時，錨點連結會要求顯示另一頁結果。 選用屬性「count」會要求在頁面上顯示許多結果。 如果未指定，則會使用目前頁面上請求的計數。 進階的選用「URL」屬性會控制關聯連結導向的網域。 依預設，網域為 `https://search.atomz.com/search/`，但您可以使用URL屬性來變更此網域。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-next URL="https://search.yourdomain.com/search/"&gt; ...&lt;/search-next&gt; </span> </p> <p> <span class="codeph"> &lt;search-prev URL="https://search.yourdomain.com/search/"&gt; ...&lt;/search-prev&gt; </span> </p> </td> 
   <td colname="col2"> <p>顯示結果的下一頁或上一頁。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-sort-by-date URL="https://search.yourdomain.com/search/"&gt; ...&lt;/search-sort-by-date&gt; </span> </p> <p> <span class="codeph"> &lt;search-sort-by-score URL="https://search.yourdomain.com/search/"&gt; ...&lt;/search-sort-by-score&gt; </span> </p> </td> 
   <td colname="col2"> <p>依日期或相關性排序結果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-show-sugramies URL="https://search.yourdomain.com/search/"&gt; ...&lt;/search-show-summaries&gt; </span> </p> <p> <span class="codeph"> &lt;search-hide-sugramins URL="https://search.yourdomain.com/search/"&gt; ...&lt;/search-hide-summarians&gt; </span> </p> </td> 
   <td colname="col2"> <p>顯示或隱藏摘要。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範本條件標籤 {#section_18D9BC66DE484881932FD2F7EA9D170D}

可讓您有條件地在它們之間加入HTML的標籤。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-results&gt;...&lt;/search-if-results&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-results&gt;...&lt;/search-if-not-results&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果目前頁面包含任何（或無）搜尋結果，這些標籤會包含HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-prev-count&gt;...&lt;/search-if-prev-count&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-prev-count&gt;...&lt;/search-if-not-prev-count&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-next-count&gt;...&lt;/search-if-next-count&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-next-count&gt;...&lt;/search-if-not-next-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果上一頁或下一頁有任何（或無）與其關聯的結果，這些標籤會包含HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-sort-by-score&gt;...&lt;/search-if-sort-by-score&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-sort-by-score&gt;...&lt;-search-if-not-sort-by-score&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-sort-by-date&gt;...&lt;/search-if-sort-by-date&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-sort-by-date&gt;...&lt;/search-if-not-sort-by-date&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果目前頁面是或不是，這些標籤會包含HTML，請依相關性或日期排序。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-show-sumarys&gt;...&lt;/search-if-show-summaries&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-hide-sumarians&gt;...&lt;/search-if-hide-summarys&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果目前頁面顯示或隱藏摘要，這些標籤會包含HTML。 您可以使用這些標籤來包含或排除搜尋結果的任何部分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-input-collections&gt;...&lt;/search-if-input-collections&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-input-collections&gt;...&lt;/search-if-not-input-collections&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果系列是在產生目前頁面的搜尋結果時指定，這些標籤會包含HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-advanced&gt;...&lt;/search-if-advanced&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-advanced&gt;...&lt;/search-if-not-advanced&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果為搜索查詢指 <span class="codeph"> 定了sp_advanced=1 </span> CGI參數，則這些標籤包括HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-bad-param name="parameter-name"&gt;...&lt;/search-if-bad-param&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-bad-param name="parameter-name"&gt;...&lt;/search-if-not-bad-param&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果給定參數無效，則這些標籤包括或排除它們之間的HTML。 </p> <p>目前僅支 <span class="codeph"> 援sp_q_location[_#] </span> 參數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-param name="param-name" value="param-value"&gt;...&lt;/search-if-param&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-param name="param-name" value="param-value"&gt;...&lt;/search-if-not-param&gt; </span> </p> </td> 
   <td colname="col2"> <p>這些進階標籤會根據「name」屬性中指定的CGI參數是否具有「value」屬性中指定的值，在它們之間包含HTML。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-sort-by-field name="field-name"&gt;...&lt;/search-if-sort-by-field&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-sort-by-field name="field-name"&gt;...&lt;/search-if-not-sort-by-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>如果目前的頁面是，或不是，則這些進階標籤會包含它們之間的HTML，並依指定欄位名稱排序。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範本表單控制標籤 {#section_45AFC414ACA74825B72FEAA8456F8DD2}

可讓您控制搜尋範本中核取方塊、選項按鈕和清單方塊的預設選取 `<form>` 狀態的標籤。

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>標記 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input&gt; </span> </p> </td> 
   <td colname="col2"> <p>用於範本中，以取代 <span class="codeph"> &lt;input&gt;標 </span> 記。 當標籤寫入瀏覽器時，單字輸入 <span class="codeph"> 會取 </span> 代 <span class="codeph"></span> search-input，而標籤中的所有其他資訊會依現狀輸出。 此外，如果標 <span class="codeph"> 簽中 </span> 指定的名稱會列為CGI參數，而標籤中指定的值是該CGI參數的值，則會在標籤的結尾 <span class="codeph"> 加上已檢查的 </span><span class="codeph"></span> 字詞。 這樣，您就可以自動將搜索結果中的預設單選按鈕或複選框狀態與當前查詢相同。 </p> <p>例如，核取方塊的HTML程式碼可能如下所示： </p> <p> <span class="codeph"> &lt;input type=checkbox name="sp_w" value="exact"&gt;沒有類似音效的符合 </span> </p> <p>該核取方塊的對應範本代碼如下： </p> <p> <span class="codeph"> &lt;search-input type=checkbox name="sp_w" value="exact"&gt;沒有類似音效的符合 </span> </p> <p>如果查詢的CGI參數字串包含 <span class="codeph"> sp_w=exact </span>，則寫入瀏覽器且搜尋結果顯示的標籤如下(已檢查的字詞會 <span class="codeph"></span> 插入標籤結尾): </p> <p> <span class="codeph"> &lt;input type=checkbox name="sp_w" value="exact" checked&gt;未勾選類似音效的符合 </span> </p> <p>如果查詢的CGI參數字串不包含 <span class="codeph"> sp_w=exact </span>，則寫入瀏覽器且搜尋結果顯示的標籤如下(標籤中未列出檢查 <span class="codeph"></span> 的字詞): </p> <p> <span class="codeph"> &lt;input type=checkbox name="sp_w" value="exact"&gt;沒有類似音效的符合 </span> </p> <p>&lt;search-input&gt; <span class="codeph"> 標籤對於將核取方塊 </span> 和選項按鈕放入您的搜尋範本很有用。 如果您有要新增至搜尋範本中 <span class="codeph"> &lt;form&gt;的核取方塊或選項按鈕 </span> ，請使用 <span class="codeph"> &lt;search-input...&gt; </span> 取代 <span class="codeph"> &lt;input...&gt; </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-select&gt; ...&lt;/search-select&gt; </span> </p> <p> <span class="codeph"> &lt;search-option&gt; ...&lt;/search-option&gt; </span> </p> </td> 
   <td colname="col2"> <p>&lt;form&gt;標籤中的下拉式清 <span class="codeph"> 單 </span> 方塊是以 <span class="codeph"> &lt;select&gt;標籤開始，並以&lt;/select&gt;標籤結 </span><span class="codeph"></span> 束。 關聯 <span class="codeph"> 的 </span> CGI參數的名稱列在 <span class="codeph"> &lt;select&gt;標籤中 </span> 。 在&lt;select&gt;標 <span class="codeph"> 記後面 </span> 是&lt;option&gt;標籤的清單，它們指 <span class="codeph"></span> 定要在清單框內顯示的值。 </p> <p>&lt; <span class="codeph"> search-select&gt; </span>、 <span class="codeph"> &lt;/search-select&gt; </span>、 <span class="codeph"> &lt;search-option&gt;和 </span><span class="codeph"></span><span class="codeph"></span> &lt;/search-option&gt;標籤提供與&lt;search-input&gt;標籤類似的功能。 亦即，如果 <span class="codeph"> &lt;-select標籤中的&lt;search is lised a CGI名稱，且如果將CGI參數的值列為特定搜尋 </span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span> &lt;搜尋選項標籤中的值，則在傳送至瀏覽器的&lt;option&gt;標籤的結尾處自動加上選取的字。 這樣，您就可以自動讓搜尋結果中的預設清單方塊選擇與目前查詢相同。 </p> <p>例如，典型清單框如下所示： </p> <p> <code class="syntax html"> &lt;select&nbsp;name="sp_x"&nbsp;size=1&gt; 
      &lt;option&nbsp;value="any"&nbsp;selected&gt;Anywhere&lt;/option&gt; 
      &lt;option&nbsp;value="title"&gt;Title&lt;/option&gt; 
      &lt;option&nbsp;value="desc"&gt;Description&lt;/option&gt; 
      &lt;option&nbsp;value="keys"&gt;Keywords&lt;/option&gt; 
      &lt;option&nbsp;value="body"&gt;Body&lt;/option&gt; 
      &lt;option&nbsp;value="alt"&gt;Alternate&nbsp;text&lt;/option&gt; 
      &lt;option&nbsp;value="url"&gt;URL&lt;/option&gt; 
      &lt;option&nbsp;value="target"&gt;Target&lt;/option&gt; 
      &lt;/select&gt; </code> </p> <p>該清單框的相應模板代碼如下： </p> <p> <code class="syntax html"> &lt;search-select&nbsp;name="sp_x"&nbsp;size=1&gt; 
      &lt;search-option&nbsp;value="any"&gt;Anywhere&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="title"&gt;Title&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="desc"&gt;Description&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="keys"&gt;Keywords&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="body"&gt;Body&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="alt"&gt;Alternate&nbsp;text&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="url"&gt;URL&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="target"&gt;Target&lt;/search-option&gt; 
      &lt;/search-select&gt; </code> </p> <p>如果您想要在搜尋範本中新增至 <span class="codeph"> &lt;form&gt; </span> ，請使用 <span class="codeph"> &lt;search-select. </span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span>.取代&lt;select.&lt;sect.&lt;/select. 2003&lt;Search-option. 2003. 2003. 2003. 2003. 2000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000/option&gt;訂購。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-sort-by-field name="field-name" count="XX"&gt; ...&lt;/search-sort-by-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>這些進階標籤會在它們之間的HTML周圍建立錨點連結。 按一下此錨點時，會顯示在指定欄位上排序結果的頁面。 可選的 <span class="codeph"> count屬 </span> 性指定要在結果頁上顯示的結果數。 如果 <span class="codeph"> 省略 </span> 計數，則會使用目前頁面上使用的計數。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 日期格式字串 {#section_4BBDBBEF2B96414497617CD4B52D96E4}

您可以在日期格式字串中使用下列轉換規格：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>日期格式字串 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%A </p> </td> 
   <td colname="col2"> <p> 相符項目：完整工作日名稱的國家代表，例如「星期一」。 「語言學 <span class="uicontrol"> &gt;字 </span> 詞與語言 <span class="uicontrol"> &gt;語言」中的設 </span> 定會 <span class="uicontrol"></span> 決定國家代表。 </p> <p>請參閱 <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> 關於字詞和語言</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a </p> </td> 
   <td colname="col2"> <p> 相符項目：縮寫工作日名稱的國家代表，其中縮寫是前三個字元，例如"Mon"。 「語言學 <span class="uicontrol"> &gt;字 </span> 詞與語言 <span class="uicontrol"> &gt;語言」中的設 </span> 定會 <span class="uicontrol"></span> 決定國家代表。 </p> <p>請參閱 <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> 關於字詞和語言</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%B </p> </td> 
   <td colname="col2"> <p> 符合完整月份名稱的國家代表，例如"June"。 「語言學 <span class="uicontrol"> &gt;字 </span> 詞與語言 <span class="uicontrol"> &gt;語言」中的設 </span> 定會 <span class="uicontrol"></span> 決定國家代表。 </p> <p>請參閱 <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> 關於字詞和語言</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%b </p> </td> 
   <td colname="col2"> <p> 相符項目：縮寫月份名稱的國家代表，其中縮寫是前三個字元，例如"Jun"。 「語言學 <span class="uicontrol"> &gt;字 </span> 詞與語言 <span class="uicontrol"> &gt;語言」中的設 </span> 定會 <span class="uicontrol"></span> 決定國家代表。 </p> <p>請參閱 <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> 關於字詞和語言</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%D </p> </td> 
   <td colname="col2"> <p>相當於"%m/%d/%y"，例如"07/25/13"。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%d </p> </td> 
   <td colname="col2"> <p> 將當月的某天與小數數字相符(01-31)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%e </p> </td> 
   <td colname="col2"> <p> 將月中的某天與小數數字相符(1-31)。 位數前面有空白。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%H </p> </td> 
   <td colname="col2"> <p> 將24小時時鐘與小數數字相匹配(00-23)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%h </p> </td> 
   <td colname="col2"> <p> 相符項目：縮寫月份名稱的國家代表，其中縮寫是前三個字元，例如"Jun"（與%b相同）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%I </p> </td> 
   <td colname="col2"> <p> 將12小時時鐘與十進位數字相符(01-12)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%j </p> </td> 
   <td colname="col2"> <p> 將年中的某天與小數數字相匹配(001-366)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%k </p> </td> 
   <td colname="col2"> <p> 將（24小時時鐘）與小數數字(0-23)相匹配。 位數前面有空白。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%l </p> </td> 
   <td colname="col2"> <p> 將12小時時鐘與十進位數字相匹配(1-12)。 位數前面有空白。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%M </p> </td> 
   <td colname="col2"> <p> 與分鐘比對為小數(00-59)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%m </p> </td> 
   <td colname="col2"> <p> 將月份與小數數字相符(01-12)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%p </p> </td> 
   <td colname="col2"> <p> 符合"ante meridiem"或"post meridiem"（例如"PM"）的國家代表。 「語言學 <span class="uicontrol"> &gt;字 </span> 詞與語言 <span class="uicontrol"> &gt;語言」中的設 </span> 定會 <span class="uicontrol"></span> 決定國家代表。 </p> <p>請參閱 <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> 關於字詞和語言</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%R </p> </td> 
   <td colname="col2"> <p>相當於"%H:%M"，例如"13:23"。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%r </p> </td> 
   <td colname="col2"> <p>相當於"%I:%M:%S %p"，例如"01:23:45 PM"。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%S </p> </td> 
   <td colname="col2"> <p> 將第二個值與十進位數字相符(00-60)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%T </p> </td> 
   <td colname="col2"> <p>相當於"%H:%M:%S"，例如"13:26:47"。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%U </p> </td> 
   <td colname="col2"> <p> 匹配年份的周數（星期日作為一週的第一天）作為小數數(00-53)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%v </p> </td> 
   <td colname="col2"> <p>相當於"%e-%b-%Y"，例如"2013年7月25日"。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Y </p> </td> 
   <td colname="col2"> <p> 與以十進位數字表示的世紀相符，例如"2013"。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%y </p> </td> 
   <td colname="col2"> <p> 與沒有世紀的年份相匹配，作為十進位數字(00-99)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Z </p> </td> 
   <td colname="col2"> <p> 符合時區名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%% </p> </td> 
   <td colname="col2"> <p> 符合 "%". </p> </td> 
  </tr> 
 </tbody> 
</table>

## 語言識別碼 {#section_0490DECC00E34691ADE5A9ED90A6D911}

下表包含每個支援語言的語言識別碼。 您可以在下列範本標籤中，將這些識別碼當做選用「語言」屬性的值：

* `search-date` 和 `search-display-field`.

   請參 [閱結果循環字串標籤](../c-appendices/c-templates.md#section_80D68334E8D04A33937A6E58ABAAA320)。

* `search-field-value-list` 請參 [閱欄位值清單標籤](../c-appendices/c-templates.md#section_D3298B5F976447DBA0032B883DCC91B1)。

* `search-field-value` 請參 [閱欄位值清單循環標籤](../c-appendices/c-templates.md#section_0717FA09F0FC449CB916883B0500A60E)。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>語言 </p> </th> 
   <th colname="col2" class="entry"> <p>語言 identifier </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>保加利亞文（保加利亞） </p> </td> 
   <td colname="col2"> <p> bg_BG </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中文（中國） </p> </td> 
   <td colname="col2"> <p> zh_CN </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中文（香港） </p> </td> 
   <td colname="col2"> <p> zh_HK </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中文（新加坡） </p> </td> 
   <td colname="col2"> <p>zh_SG </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中文（台灣） </p> </td> 
   <td colname="col2"> <p> zh_TW </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>捷克文（捷克文） </p> </td> 
   <td colname="col2"> <p> cs_CZ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>丹麥文（丹麥） </p> </td> 
   <td colname="col2"> <p> da_DK </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>荷蘭文（比利時） </p> </td> 
   <td colname="col2"> <p> nl_BE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>荷蘭文（荷蘭） </p> </td> 
   <td colname="col2"> <p> nl_NL </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>英文（澳洲） </p> </td> 
   <td colname="col2"> <p> en_AU </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>英文（加拿大） </p> </td> 
   <td colname="col2"> <p> en_CA </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>英文（大不列顛） </p> </td> 
   <td colname="col2"> <p> en_GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>英文（美國） </p> </td> 
   <td colname="col2"> <p> en_US </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>法文（比利時） </p> </td> 
   <td colname="col2"> <p> fr_BE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>法文（加拿大） </p> </td> 
   <td colname="col2"> <p>fr_CA </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 芬蘭文（芬蘭） </p> </td> 
   <td colname="col2"> <p> fi_FI </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>法文（法國） </p> </td> 
   <td colname="col2"> <p> fr_FR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>法文（瑞士） </p> </td> 
   <td colname="col2"> <p> fr_CH </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>德文（奧地利） </p> </td> 
   <td colname="col2"> <p> de_AT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>德文（德國） </p> </td> 
   <td colname="col2"> <p> de_DE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>德文（瑞士） </p> </td> 
   <td colname="col2"> <p> de_CH </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>希臘文（希臘） </p> </td> 
   <td colname="col2"> <p> el_GR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>愛爾蘭蓋爾語（愛爾蘭） </p> </td> 
   <td colname="col2"> <p> ga_IE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>義大利文（義大利） </p> </td> 
   <td colname="col2"> <p> it_IT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日文（日本） </p> </td> 
   <td colname="col2"> <p> ja_JP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>韓文（韓國） </p> </td> 
   <td colname="col2"> <p> ko_KR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>挪威文（挪威） </p> </td> 
   <td colname="col2"> <p> no_NO </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>波蘭文（波蘭） </p> </td> 
   <td colname="col2"> <p> pl_PL </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>葡萄牙文（巴西） </p> </td> 
   <td colname="col2"> <p> pt_BR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>葡萄牙文（葡萄牙） </p> </td> 
   <td colname="col2"> <p> pt_PT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>俄文（前蘇聯） </p> </td> 
   <td colname="col2"> <p> ru_SU </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>斯洛伐克文（斯洛伐克） </p> </td> 
   <td colname="col2"> <p> sk_SK </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>斯洛伐克文（斯洛維尼亞） </p> </td> 
   <td colname="col2"> <p>sl_SI </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>西班牙文（墨西哥） </p> </td> 
   <td colname="col2"> <p> es_MX </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>西班牙文（西班牙） </p> </td> 
   <td colname="col2"> <p> es_ES </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>瑞典文（瑞典） </p> </td> 
   <td colname="col2"> <p> sv_SE </p> </td> 
  </tr> 
 </tbody> 
</table>

## 指定內容類型HTTP標題 {#section_AEED823E9938448A9EDB2F286D9CFD90}

您可以使用下列標籤來指定「內容類型」HTTP回應標題：

`<search-content-type-header [content="MIME-type"] [charset="charset-name"]>`

和 `content` 屬 `charset` 性是可選的。 此標籤應盡早出現在範本中。 也建議在或之前顯示 `<search-html-meta-charset>` ，因 `<search-xml-decl>`為它會影響這些標籤的行為。

如果您未指定屬 `content` 性，則值預 `MIME-type` 設為在 **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** >中設定的值 **[!UICONTROL Content Types]**。 如果您指定 `content` 屬性，則會將其用作標 `content` 記的預設 `<search-html-meta-charset>` 屬性。

如果您未指定屬 `charset` 性，則不會將 `charset` 任何值寫入標 `content-type` 題。

如果指 `charset="1"` 定，則實際值 `charset-name` 是 `sp_f` CGI參數的值。 如果搜 `sp_f` 尋未提交CGI參數，則會從帳戶設定 `charset-name` 讀取實際值。 您可以在> > >下檢視或變更與您的帳戶關聯 **[!UICONTROL Settings]** 的字 **[!UICONTROL My Profile]** 元 **[!UICONTROL Personal Information]** 集 **[!UICONTROL Character Encoding]**。

請參 [閱設定您的個人使用者資訊](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6)。

通過將特定字元集名稱列為值（如或）, `charset` 可以選擇 `charset="iso-8859-1"` 該名稱 `charset="Shift-JIS"`。

如果您指定 `charset` 屬性，則會將其用作和標 `charset` 簽的 `<search-html-meta-charset>` 預設屬性，以 `<search-xml-decl>` 及輸出到標 `content-type` 題。

## 在HTML範本中指定字元集 {#section_E0D1816ABB5846BEBE9C26D5980CCBE6}

預設的HTML搜尋結果範本會透過下列標籤指定與目前帳戶關聯的字元集：

`<search-html-meta-charset [content="MIME-type"] [charset="charset-name"]>`

內容和字元集屬性是選用的。 此標籤必須出現在範本 `<head>` 的HTML區段中。 此標籤會在範本產生的HTML頁面上產生下列標籤：

`<meta http-equiv="content-type" content="MIME-type; charset=charset-name">`

如果您未指定內容屬性，則實際值的預 `MIME-type` 設值為兩個值之一。 如果標 `<search-content-type-header>` 簽指定屬 `content` 性，則會使用該值。 否則，所用的值是「 > >」標籤中 **[!UICONTROL Templates]** 的 **[!UICONTROL Settings]** 值 **[!UICONTROL Content Type]** 集。

如果未指定屬性， `charset` 則實際值將默 `charset-name` 認為兩個值之一。 如果標 `<search-content-type-header>` 簽指定屬 `charset` 性，則會使用該值。 否則，實際值會從您 `charset-name` 的帳戶設定中讀取。 您可以在> > >下檢視或變更與您的帳戶關聯 **[!UICONTROL Settings]** 的字 **[!UICONTROL My Profile]** 元 **[!UICONTROL Personal Information]** 集 **[!UICONTROL Character Encoding]**。

請參 [閱設定您的個人使用者資訊](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6)。

如果指 `charset="1"` 定，則實際值 `charset-name` 是 `sp_f` CGI參數的值。 如果搜 `sp_f` 尋未提交CGI參數，則實際值為 `charset-name` （若已指定） `<search-content-type-header>` 標籤中設定的值，或是在帳戶設定中設定的值。

可以指定特定字元集名稱，如中 `charset="charset-name"`。 For example, `charset="iso-8859-1"` or `charset="Shift-JIS"`.

標 `<search-html-meta-charset>` 記為選用。 如果您移除它，瀏覽器會採用下列 `content-type`預設值： `content="text/html; charset=ISO-8859-1"`。 您也可以選擇將標籤取 `<search-html-meta-charset>` 代為您自己的 `http-equiv` 標籤。

## 在XML模板中指定字元集 {#section_17DC31CDCC104F5F8081466B41A96E9D}

預設的XML搜索結果模板通過以下標籤指定與當前帳戶關聯的字元集：

`<search-xml-decl [charset="charset-name"]>`

屬 `charset` 性為可選。 此標籤必須出現在範本頂端，但必須出現在任何標籤之 `<search-content-type-header>` 後。 此標籤會在XML檔案上產生下列標籤，這些標籤是從範本產生的：

`<?xml version="1.0" encoding="charset-name" standalone="yes" ?>`

如果您未指定 `charset`，則實際值預 `charset-name` 設為兩個值之一。 如果 `<search-content-type-header>` 指定 `charset` 了屬性，則使用該值。 否則，實際值會從您 `charset-name` 的帳戶設定中讀取。 您可以在> > >下檢視或變更與您的帳戶關聯 **[!UICONTROL Settings]** 的字 **[!UICONTROL My Profile]** 元 **[!UICONTROL Personal Information]** 集 **[!UICONTROL Character Encoding]**。

請參 [閱設定您的個人使用者資訊](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6)。

如果指 `charset="1"` 定，則實際值 `charset-name` 是 `sp_f` CGI參數的值。 如果搜 `sp_f` 尋未提交CGI參數，則實際值為 `charset-name``<search-content-type-header>` （若已指定）在標籤中設定的值，或是（在帳戶設定中設定）。

如果需要，可以指定特定的字元集名 `charset="charset-name"`稱，如中。 例如, `charset="iso-8859-1" or charset="Shift-JIS"`。

您可以選擇以您自己的 `<search-xml-decl>` 標籤來取代標 `?xml` 記。

## 在其他範本中包含搜尋範本 {#section_7D1FCD3D9E2340C291E354C9720E8BC0}

要將一個搜索模板包含在另一個中，請使用標 `<search-include>` 記，將檔案屬性設定為要包括的模板檔案的名稱，如下例所示：

`<search-include file="seo/seo_search_title.tpl" />`

SEO搜尋範本區段位於子資 `seo/` 料夾中，而一般搜尋範本位於子資 `templates/` 料夾中。 只有。tpl檔案有意義加入此內容。

## 管理網站的多個傳輸範本 {#reference_12AAB3B9F4C74C11956F1DBA95714C2F}

您可以針對每個區域使用不同的搜尋傳輸範本，來控制網站上搜尋結果的外觀。

<!-- 

r_managing_multiple_templates.xml

 -->

若要完成這種搜尋功能，您可以在網站搜尋／銷售中管理您的傳輸範本。 或者，您可以在「發佈」中管理傳輸範本。 如同網站搜尋／銷售，「發佈」可讓您編輯、預覽和發佈多個搜尋傳輸範本。

要設定搜索表單以使用特定傳輸模板（預設值除外），請使用查 `sp_t` 詢參數。 例如，假設您有一個搜尋範本，稱為「清除」，用於您網站的已標籤銷售區。 您使用標準HTML搜尋表單，並加入下列其他表單程式碼：

`<input type=hidden name="sp_t" value="clearance">`

當客戶點按包含此行代碼的標準表單時，會顯示「清倉」搜尋傳輸範本及其搜尋結果。

請參 [閱在搜尋表單中使用系列](../c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3)。

請參 [閱搭配使用框架](../c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5)。

請參 [閱範例進階搜尋表單](../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A)。
