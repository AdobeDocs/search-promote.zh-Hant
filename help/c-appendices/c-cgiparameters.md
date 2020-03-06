---
description: 'null'
seo-description: 'null'
seo-title: CGI參數
solution: Target
title: CGI參數
topic: Appendices,Site search and merchandising
uuid: a5f43547-bc15-44aa-ba23-6b8b573e09d2
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a

---


# CGI參數{#cgi-parameters}

## CGI參數 {#concept_F395999090FE4926B38BC73D5E612800}

## 搜索CGI參數 {#reference_DA27A8B0728246DA94994885E1353890}

提供搜尋表單程式碼，您可將其複製並貼至網站的HTML( **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**)。

請參 [閱將搜索表單的HTML代碼複製到……](../c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

您也可以設定搜尋表單本身或指令碼中所列的參數。 除了下面列出的參數外，您還可以使用後端搜尋參數來控制搜尋。

請參 [閱後端搜尋CGI參數](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。

搜尋請求包含基本URL。 基本URL會指出客戶正在搜尋的帳戶，以及一組CGI參數（金鑰值配對），用以指出如何傳回相關帳戶所需的搜尋結果。

基本URL與特定帳戶以及分段或即時環境相關聯。 您可以向帳戶管理員請求基本URL的多個別名。 例如，一家名為Megacorp的公司可能有兩個與其帳戶關聯的基本URL: `https://search.megacorp.com` 和 `https://stage.megacorp.com`。 前者URL會搜尋其即時索引，後者URL則會搜尋其分段索引。

支援三種格式的CGI參數。 預設情況下，您的帳戶配置為使用分號分隔CGI參數，如下例所示：

`https://search.megacorp.com?q=shoes;page=2`

如果您願意，您可以讓帳戶管理員設定您的帳戶，使用&amp;符號來分隔CGI參數，如下列範例所示：

`https://search.megacorp.com?q=shoes&page=2`

另外也支援第三種格式，稱為SEO格式，其中正斜線用來取代分隔符號， `/` 等號如下例所示：

`https://search.megacorp.com/q/shoes/page/2`

只要使用SEO格式傳送請求，所有輸出連結都會以相同格式傳回。

| 引導搜尋參數 | 範例 | 說明 |
|--- |--- |--- |
| q | `q=string` | 指定搜索的查詢字串。 此參數會對應至後端 `sp_q` 搜尋參數。  請參 [閱後端搜尋CGI參數](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| q# | `q#=string` | Faceting（在指定欄位內搜尋）是透過編號q和x參數來完成。  q參數會定義您在Facet中搜尋的詞語，如對應的編號x參數所示。<br>例如，如果您有兩個刻面，其名稱為size和color，則可以有q1=small;x1=size;q2=red;x2=color。  此參數會對應至後端 `sp_q_exact_#` 搜尋參數。  <br>請參 [閱後端搜尋CGI參數](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| x 中的頁面載入要求# | `q#=string` | Faceting（在指定欄位內搜尋）是透過編號q和x參數來完成。  q參數會定義您在Facet中搜尋的詞語，如對應的編號x參數所示。 <br>例如，如果您有兩個刻面，其名稱為size和color，則可以有q1=small;x1=size;q2=red;x2=color。  此參數會對應至後端 `sp_x_#` 搜尋參數。  <br>請參 [閱後端搜尋CGI參數](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| 集合 | `collection=string` | 指定要用於搜尋的系列。  此參數會對應至後端 `sp_k` 搜尋參數。  請參 [閱後端搜尋CGI參數](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| 計數 | `count=number` | 指定顯示的結果總計。  預設值定義於 [!UICONTROL Settings ] > [!UICONTROL Searching ] > [!UICONTROL Searches ]中。.  此參數會對應至後端 `sp_c` 搜尋參數。  請參 [閱後端搜尋CGI參數](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| 頁面 | `page=number` | 指定返回的結果頁。 |
| 排名 | `rank=field` | 指定用於靜態排名的排名欄位。  欄位必須是關聯性大於0的「排名」類型欄位。  此參數會對應至後端 `sp_sr` 參數。  請參 [閱後端搜尋CGI參數](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| 排序 | `sort=number` | 指定排序順序。<br>「0」是預設值，並依關聯分數排序；「1」按日期排序；&quot;-1&quot;不排序。  使用者可以指定參數值的欄位 `sp_s` 名稱。  例如， `sp_s=title` 根據標題欄位中包含的值對結果排序。 當使用欄位名稱做為參數值時， ` sp_s ` 結果會依該欄位排序，然後依相關性子排序。  To enable this feature, click [!UICONTROL Settings ] > [!UICONTROL Metadata ] > [!UICONTROL Definitions ]. 在「定義」頁面上，按一 [!UICONTROL Add New Field ] 下或按一 [!UICONTROL Edit ] 下特定欄位名稱。 在下拉 [!UICONTROL Sorting ] 式清單中，選取或 [!UICONTROL Ascending ] 選取 [!UICONTROL Descending ]。 此參數會對應至後端 `sp_s` 搜尋參數。 <br>請參 [閱後端搜尋CGI參數]。(../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |

## 後端搜尋CGI參數 {#reference_582E85C3886740C98FE88CA9DF7918E8}

通常客戶會與稱為引導式搜尋的表現層互動。 不過，理論上可以略過引導式搜尋層，並直接使用本頁所述的CGI參數與後端核心搜尋互動。

您可以從下表中選擇後端搜索CGI參數：
<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>單一查詢支援 </p> </th> 
   <th colname="col03" class="entry"> <p>多重查詢支援 </p> </th> 
   <th colname="col3" class="entry"> <p>範例 </p> </th> 
   <th colname="col4" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>sp_a </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_a=字串 </span> </p> </td> 
   <td colname="col4"> <p>指定帳號字串。 此參數為必要參數，且必須是有效的帳號字串。 您可以在「設定&gt;帳戶選項&gt;帳戶設 <span class="uicontrol"> 定」 </span> 下，找到您的 <span class="uicontrol"> 帳戶 </span> 號碼字串 <span class="uicontrol"></span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>sp_advanced </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_advanced= 0或1 </span> </p> </td> 
   <td colname="col4"> <p>如果 <span class="codeph"> sp_advanced=1隨查詢提交，則搜尋表單會使用 </span> &lt;search-if-advanced&gt;標籤和搜尋範本中 <span class="codeph"></span><span class="codeph"></span> &lt;/search-if-advanced&gt;標籤之間的所有代碼。 將忽略 <span class="codeph"> &lt;search-if-not-advanced&gt;標籤和 </span> &lt;/search-if-not-advanced&gt;標籤之間的所 <span class="codeph"></span> 有代碼。 如果 <span class="codeph"> sp_advanced=0 </span> （或任何其他值）已提交，則會忽略&lt;search-if-advanced&gt;範本區塊，並使用&lt;search-if-not-advanced&gt;範本區塊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>sp_c </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_c=數 </span> </p> </td> 
   <td colname="col4"> <p>指定要顯示的結果總計。 預設值為 10。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>sp_context_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_context_field= <i>field</i> </code> </p> </td> 
   <td colname="col4"> <p>收集指定欄位的內容相關資訊。 收集的資訊會透過&lt;search-context&gt;範本標籤在搜尋結果 <span class="codeph"> 中輸 </span> 出。 The default value is <span class="codeph"> body </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>sp_d </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_d=類型 </span> </p> </td> 
   <td colname="col4"> <p>指定要執行的日期範圍搜尋的類型。 可能的類型為 <span class="codeph"> sp_start_day、 </span> sp_start_month、 <span class="codeph"> sp_start_start_start_manth、 </span>sp_start_start_year、 <span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span> sp_start_start_year、sp_start_day、sp_end Day、sp_end Hadign等。用來判斷要搜尋的日期範圍。 <span class="codeph"> 只有在 </span> 您的搜尋表單包含依自訂範圍(透過 <span class="codeph"> sp_date_range </span>)或特定開始和結束日期範圍進行搜尋的選項時，才需要sp_d。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_d_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_d_#=類型 </span> </p> </td> 
   <td colname="col4"> <p>指定要對相應的sp_q_#查詢執行的日期 <span class="codeph"> 範圍搜索的類 </span> 型。 "#"會以1到16之間的數字取代(例如， <span class="codeph"> sp_d_8 </span>，套用至編號的查詢 <span class="codeph"> sp_q_8 </span>)。 </p> <p>可以將類型設為 <span class="codeph"></span> any，這表示不執行日期範圍搜索、自定義，這表示 <span class="codeph"> sp_date的值用於確定要搜索的日期，具體表示sp_date_date的值用於確定要搜索的日期，並指 </span> sp_q_day_min_, sp_q_ <span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span> q_min_min_最大月數q_max_month_q，最大月數q_max_year_q。 只有當您的搜尋表單 <span class="codeph"> 包含依自訂範圍(透過 </span> sp_date_range_#)或依特定開始和結束日期範圍進行搜尋的選項時，才需要使用 <span class="codeph"></span>sp_d_#。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>sp_date_range </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_date_range= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>指定要套用至搜尋的預先定義日期範圍。 大於或等於零的值會指定今天之前要搜尋的天數— 例如，值"0"指定"今天"，值"1"指定"今天和昨天"，值"30"指定"在過去30天內"等。 </p> <p>低於零的值會指定自訂範圍，如下所示： </p> <p>-1 = "無"，與指定無日期範圍相同。 </p> <p>-2 = "本週"，在當周的週日到週六搜尋。 </p> <p>-3 = "上週"，在當周前一週的星期日到星期六進行搜尋。 </p> <p>-4 = "本月"，搜尋當月日期。 </p> <p>-5 = "上個月"，搜尋當月前一個月的日期。 </p> <p>-6 = 「今年」，其搜索日期在當年。 </p> <p>-7 = 「去年」，搜尋日期在當年前一年。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_date_range_# </p> </td> 
   <td colname="col3"> <p> <code> sp_date_range_#= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>指定要套用至對應sp_q_#查詢的預 <span class="codeph"> 定日期范 </span> 圍。 "#"會以1到16之間的數字取代(例如， <span class="codeph"> sp_date_range_8 </span>，套用至編號的 <span class="codeph"> sp_q_8 </span>)。 </p> <p>大於或等於零的值指定今天之前要搜索的天數。 例如，0的值指定今天；值1表示今天和昨天；值30指定在最近30天內，依此類推。 </p> <p>低於零的值會指定自訂範圍，如下所示： </p> <p>-1 = "無"，與指定無日期範圍相同。 </p> <p>-2 = "本週"，在當周的週日到週六搜尋。 </p> <p>-3 = "上週"，在當周前一週的星期日到星期六進行搜尋。 </p> <p>-4 = "本月"，搜尋當月日期。 </p> <p>-5 = "上個月"，搜尋當月前一個月的日期。 </p> <p>-6 = 「今年」，其搜索日期在當年。 </p> <p>-7 = 「去年」，搜尋日期在當年前一年。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>9 </p> </td> 
   <td colname="col2"> <p>sp_dedupe_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_dedupe_field= <i>fieldname</i> </code> </p> </td> 
   <td colname="col4"> <p>指定一個欄位，用於刪除上的重複搜索結果。 該欄位上的所有重複結果都會從搜尋結果中移除。 例如，如果 <span class="codeph"> sp_dedupe_field=title </span>，則搜索結果中只顯示給定標題的頂部結果（沒有兩個結果具有相同的標題欄位內容）。 對於多值（允許清單）類型欄位，將使用整個欄位內容進行比較。 只能指定一個欄位。 欄位名稱中不允許使用「表限定詞」。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>10 </p> </td> 
   <td colname="col2"> <p>sp_e </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_e=數字 </span> </p> </td> 
   <td colname="col4"> <p>指定應針對查詢字串中具有數字以上字元的任何字詞，進行自動萬用字元擴增。 換言之， <span class="codeph"> sp_e=5指 </span> 定應以萬用字元'*'來擴充包含5個或更多字元的字詞，例如"query"或"number"，使搜尋等同於搜尋"query*"或"number*"。 字元數較少的字詞不會展開，因此搜尋「word」時不會自動擴充萬用字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>11 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_e_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_e_#=數字 </span> </p> </td> 
   <td colname="col4"> <p>指定自動通配符擴展對來自具有多於數字字元的 <span class="codeph"> sp_q_#查 </span> 詢字串的任何字進行。 換言之， <span class="codeph"> sp_e_2=5指定 </span> sp_q_2查詢字串中包含5個以上字元的字詞（例如「query」或「number」）應以萬用字元「 <span class="codeph"> * </span><span class="codeph"></span>」展開，使搜尋等同於搜尋「query*」或「number*」。 字元數較少的字詞不會展開，因此在 <span class="codeph"> sp_q_2中搜尋"word"時 </span> 不會自動擴充萬用字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>12 </p> </td> 
   <td colname="col2"> <p>sp_end_day、sp_end_month、sp_end_year </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_end_day= <i>number</i>,sp_end_month= <i>number</i>, sp_end_year= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>這三重數值指定搜尋的結束日期範圍，且必須以集合形式提供。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>13 </p> </td> 
   <td colname="col2"> <p>sp_f </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_f=字串 </span> </p> </td> 
   <td colname="col4"> <p>指定查詢參數字串的字元集(例如 <span class="codeph"> sp_q </span>)。 此字串必須始終與包含搜尋表單之頁面的字元集相符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>14 </p> </td> 
   <td colname="col2"> <p>sp_field_table </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_field_ table=table: field,field... </code> </p> </td> 
   <td colname="col4"> <p>定義由給定欄位組成的邏輯資料表。 例如，由"color"、"size"和"price"欄位組成的名為"items"的表格會定義為： </p> <p> <span class="codeph"> sp_field_table=items:color,size,price </span> </p> <p>邏輯表與已勾選「允許清單」的欄位(在「設定&gt;中繼資料 <span class="uicontrol"> &gt;定義」 </span> 下)搭配使用時，最 <span class="uicontrol"></span><span class="uicontrol"></span>有用的方式是： 所有將欄位名稱作為值的CGI參數和模板標籤，可以選擇指定表名，後面跟有"。" 在欄位名稱之前(例如， <span class="codeph"> sp_x_1=tablename.fieldname </span>)。 </p> <p>例如，要搜索包含一個或多個「大」（其中項目表示為並行元資料行）大小為「大」的「紅色」項目的文檔，可以使用以下內容： </p> <p> <code> sp_q_exact_1=red&amp;sp_x_1=items.color&amp; sp_q_exact_2=large&amp;sp_x_2=items.size&amp;sp_field_table=items:color,size,price </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>15 </p> </td> 
   <td colname="col2"> sp_i </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_i= <span class="varname"> 值 </span></span> </p> </td> 
   <td colname="col4"> <p>產生報表時忽略搜尋。 </p> <p>使用此查詢可屏蔽某些後端搜索，如Did You Mean生成的搜索，或管理員在成員中心生成的搜索。 由於使用者不產生這些搜尋類型，因此不會顯示在各種Adobe Search&amp;Promote報表中。 </p> <p>有效值 <span class="codeph"> 為sp_i=1 </span> 和 <span class="codeph"> sp_i=2 </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>16 </p> </td> 
   <td colname="col2"> <p>sp_k </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_k=字串 </span> </p> </td> 
   <td colname="col4"> <p> 指定要用於搜尋的系列。 預設為無系列，表示搜尋應包含整個網站。 </p> <p>請參閱 <a href="../c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3" type="reference" format="dita" scope="local"> 在搜尋表單中使用系列 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>17 </p> </td> 
   <td colname="col2"> <p>sp_l </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_l=字串 </span> </p> </td> 
   <td colname="col4"> <p>指定查詢參數字串的語言(如 <span class="codeph"> sp_q </span>)。 字串 <i> 應 <span class="codeph"></span></i> 是標準地區設定ID，其中包含ISO-639語言程式碼（可選）以及ISO-3166國家／地區程式碼。 例如，英文為"en"或"en_US"，日文為"ja"或"ja_JP"。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>18 </p> </td> 
   <td colname="col2"> <p>sp_literal </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_literal= 0或1 </span> </p> </td> 
   <td colname="col4"> <p> 設 <span class="codeph"> 定sp_literal=1會 </span> 暫時停用所有可能解譯查詢中字詞的功能。 使用此參數時，無論同義字、替代字詞表單和相似音符匹配，都只有查詢的常值字詞匹配文檔。 </p> <p>請注意， <span class="codeph"> sp_literal=0 </span> 沒有意義，如果使用，則會忽略。 </p> <p>請參閱 <a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" type="concept" format="dita" scope="local"> 關於字典 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>19 </p> </td> 
   <td colname="col2"> <p>sp_m </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_m=數 </span> </p> </td> 
   <td colname="col4"> <p> 指定是否顯示摘要。 1是，0是否。 預設值為 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>20 </p> </td> 
   <td colname="col2"> <p>sp_n </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_n=數 </span> </p> </td> 
   <td colname="col4"> <p> 指定啟動搜索結果的結果數。 預設值為 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>21 </p> </td> 
   <td colname="col2"> <p>sp_not_found_page </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_not_found_page= url </span> </p> </td> 
   <td colname="col4"> <p> 指定如果沒有搜尋結果，是否要重新導向至指定的URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>22 </p> </td> 
   <td colname="col2"> <p>sp_p </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_p= any/all/phrase </span> </p> </td> 
   <td colname="col4"> <p> 指定要執行的預設搜索類型。 使用任何 <span class="codeph"> 表 </span> 示搜尋包含查詢字串中任何字詞的檔案。 全部的使 <span class="codeph"> 用表 </span> 示搜尋包含查詢字串中所有字詞的檔案。 使用片語 <span class="codeph"> 表 </span> 示查詢字串會被視為引號片語，且會忽略所有使用者類型的引號。 </p> <p>對於 <span class="codeph"> 詞 </span> 組 <span class="codeph"> 和所有字 </span>元，會停用搜尋字詞前的"+"和"-"規格，並忽略這些字元。 如 <span class="codeph"> 果sp_p不存 </span> 在，或者設定為空字串或任何字串，則允許使用標準"+"和"-"字首。 </p> <p>如需在搜尋中使用加號("+")和減號("-")的詳細資訊，請參閱搜尋秘訣說明。 </p> <p>請參閱<a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local">關於搜尋</a>。 </p> <p>有關使用sp_p參數的示例，請參見示例高級 <span class="codeph"> 搜索表 </span> 單。 </p> <p>請參閱 <a href="../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A" type="reference" format="dita" scope="local"> 進階搜尋表單範例 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>23 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_p_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_p_#= any/all/phrase </span> </p> </td> 
   <td colname="col4"> <p>指定要使用對應的sp_q_#查詢執行的 <span class="codeph"> 預設搜索類 </span> 型。 "#"會以1到16之間的數字取代(例如， <span class="codeph"> sp_p_8 </span> 適用於編號的查詢 <span class="codeph"> sp_q_8 </span>)。 使用任何 <span class="codeph"> 表 </span> 示傳回包含查詢字串中任何字詞的檔案。 使用全部 <span class="codeph"> 表 </span> 示傳回包含查詢字串中所有字詞的檔案。 使用片語 <span class="codeph"> 表 </span> 示將查詢字串視為完整的片語（且會忽略所有使用者類型的引號）。 </p> <p>如果您指定全 <span class="codeph"> 部或片 </span> 語， <span class="codeph"></span>則會在搜尋字詞被忽略之前，先指定任何加號和減號。 如 <span class="codeph"> 果省略sp_p_# </span> ，或將其設定為空字串或 <span class="codeph"> 任何 </span>，則允許使用標準"+"和"-"前置詞。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>24 </p> </td> 
   <td colname="col2"> <p>sp_pt </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_pt= <i>exact/equivalent/compatible</i> </code> </p> </td> 
   <td colname="col4"> <p> 指定要應用的目標匹配類型。 使用精確 <span class="codeph"> 表示 </span> 僅在與目標內容內的查詢字串完全相符的檔案中，才產生目標符合。 使用等 <span class="codeph"> 值 </span> 就像使用精確，但字的順序並不重要。 使用相容 <span class="codeph"> 性 </span> 會根據sp_p參數的值自動設定目標符 <span class="codeph"> 合類 </span> 型。 如果所有的sp_p，或者其他的sp_p，則使用精確 <span class="codeph"> 的 </span> 使用，或者使 <span class="codeph"> 用等 </span> 效的p_p <span class="codeph"></span><span class="codeph"></span><span class="codeph"></span> 。 sp_pt的缺 <span class="codeph"> 省值 </span> 是相 <span class="codeph"> 容的 </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>25 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_pt_# </p> </td> 
   <td colname="col3"> <p> <code> sp_pt_#= <i>exact/equivalent/compatible</i> </code> </p> </td> 
   <td colname="col4"> <p>指定要與對應的sp_q_#查詢一起應用的目 <span class="codeph"> 標匹配類 </span> 型。 "#"會以1到16之間的數字取代(例如， <span class="codeph"> sp_p_8 </span> 適用於編號的查詢 <span class="codeph"> sp_q_8 </span>)。 使用精確 <span class="codeph"> 表示 </span> 僅在與目標內容內的查詢字串完全相符的檔案中，才產生目標符合。 使用等 <span class="codeph"> 值詞 </span> 類似 <span class="codeph"> 精確，但 </span>詞的順序並不重要。 使用相容 <span class="codeph"> 性 </span> 會根據對應的 <span class="codeph"> sp_p_#參數值自動設定目標符合類型 </span> :如 <span class="codeph"> 果 </span> sp_p_#是全部或片語，則會使用精確值 <span class="codeph"> ，否則會使用 </span> 相等 <span class="codeph"></span> 值。 sp_pt_#的缺 <span class="codeph"> 省值與 </span> sp_ <span class="codeph"> pt_#相容 </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>26 </p> </td> 
   <td colname="col2"> <p>sp_q </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q=字串 </span> </p> </td> 
   <td colname="col4"> <p> 指定搜索的查詢字串。 空字串導致未顯示任何結果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>27 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_q_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_#=文本 </span> </p> </td> 
   <td colname="col4"> <p>此參數允許在搜索表單上建立多個查詢。 sp_q_ <span class="codeph"> #參數包含 </span> 要用於給定編號查詢的查詢字串。 搜索請求最多可以引用16個不同編號的查詢( <span class="codeph"> sp_q_1 </span> 到 <span class="codeph"> sp_q_16 </span>)。 </p> <p>例如，提交下清單格會傳回所有包含"great"和"books"的檔案。 </p> <p> <code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="books"&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>28 </p> </td> 
   <td colname="col2"> <p>sp_q_day、sp_q_month、sp_q_year </p> </td> 
   <td colname="col03"> <p> sp_q _day_#、sp_q _month_#、sp_q _year_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_day=整數值 </span> </p> <p> <span class="codeph"> sp_q_month=整數值 </span> </p> <p> <span class="codeph"> sp_q_year=整數值 </span> </p> <p> <span class="codeph"> sp_q_day_#=整數值 </span> </p> <p> <span class="codeph"> sp_q_month_#=整數值 </span> </p> <p> <span class="codeph"> sp_q_year_#=整數值 </span> </p> </td> 
   <td colname="col4"> <p>這些參數可用來指定特定查詢的確切日期。 sp_q_ <span class="codeph"> day 、 </span><span class="codeph"> sp_q_month </span>和 <span class="codeph"> sp_q_year參數適用於主查詢( </span><span class="codeph"></span>sp_q主查詢)。 </p> <p>#參 <span class="codeph"> 數 </span>會以1到16之間的數字取代(例如， <span class="codeph"> sp_q_day_6 </span>，此值會套用至編號的查詢 <span class="codeph"> sp_q_6 </span>)。 依預設，會相對於格林威治標準時間搜尋所有日期。 </p> <p>以下程式碼區段可讓使用者在日期為"Jan"的檔案中搜尋"orange"。 1st, 2000」(位於名為PublishDate的使用者定義欄位 <span class="codeph"> 中) </span>: </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt; Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;On&nbsp;:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Month &lt;input&nbsp;type="text"&nbsp;name="sp_q_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Year&nbsp; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>29 </p> </td> 
   <td colname="col2"> <p>sp_q_location </p> </td> 
   <td colname="col03"> <p>sp_q_location_# </p> </td> 
   <td colname="col3"> <p> <code> sp_q_location=<i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code> </p> <p> <code> sp_q_location_#= <i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code> </p> </td> 
   <td colname="col4"> <p>這些參數將位置與主查詢或編號查詢關聯。 使用 <span class="codeph"> sp_q_location </span> 會影響主查詢 <span class="codeph"> sp_q_location_# </span> (其中， <span class="codeph"></span> #被1到16的數字替換)，影響給定的編號查詢。 這些參數用於對針對每個站點頁面編製索引的位置資料執行最小和／或最大距離接近搜索。 值的格式決定其解釋。 </p> <p>DDD（三位數）格式的值被解釋為美國電話區域；DDDDD或DDDD-DDDD格式的值被解釋為美國的zipcode;DDDD的形式為±DDD.DDDD.DDDD被解釋為經緯度對。 每個值都需要符號。 例如，+38.6317+120.5509指定緯度38.6317，經度120.5509。 </p> <p>請參 <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> 閱關於鄰近搜尋 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>30 </p> </td> 
   <td colname="col2"> <p>sp_q_max_referent_distance </p> </td> 
   <td colname="col03"> <p>sp_q_max_releated_distance _# </p> </td> 
   <td colname="col3"> <p> <code> sp_q_max_relevant_distance= <i>value</i> </code> </p> <p> <code> sp_q_max_relevant_distance_#= <i>value</i> </code> </p> </td> 
   <td colname="col4"> <p>這些參數控制應用於鄰近搜索的相關性計算。 使用 <span class="codeph"> sp_q_max_releated_distance </span> 會影響主查詢 <span class="codeph"> sp_q_max_releated_distance_# </span> (其中 <span class="codeph"></span> #被1到16的數字替換)，這會影響給定的編號查詢。 </p> <p>sp_q_max_ <span class="codeph"> releated_distance的預設值 </span> 為100。 </p> <p>鄰近元件的完美關聯分數代表距離0。 鄰近元件的最小相關性分數代表剛好超過指定 <span class="codeph"> sp_q_max_releated_distance_#值的距 </span> 離。 </p> <p>請參 <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> 閱關於鄰近搜尋 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>31 </p> </td> 
   <td colname="col2"> <p>sp_q_min_day、sp_q_min_month、sp_q_min_year </p> <p>sp_q_max_day、sp_q_max_month、sp_q_max_year </p> </td> 
   <td colname="col03"> <p>sp_q_min_day_#、sp_q_min_month_#、sp_q_min_year_# </p> <p> sp_q_max_day_#、sp_q_max_month_#、sp_q_max_year_# </p> </td> 
   <td colname="col3"> <p> <code> sp_q_min_day=<i>integer value</i> </code> </p> <p> <code> sp_q_min_month=<i>integer value</i> </code> </p> <p> <code> sp_q_min_year=<i>integer value</i> </code> </p> <p> <code> sp_q_max_day=<i>integer value</i> </code> </p> <p> <code> sp_q_max_month=<i>integer value</i> </code> </p> <p> <code> sp_q_max_year=<i>integer value</i> </code> </p> <p> <code> sp_q_min_day_#=<i>integer value</i> </code> </p> <p> <code> sp_q_min_month_#=<i>integer value</i> </code> </p> <p> <code> sp_q_min_year_#=<i>integer value</i> </code> </p> <p> <code> sp_q_max_day_#=<i>integer value</i> </code> </p> <p> <code> sp_q_max_month_#=<i>integer value</i> </code> </p> <p> <code> sp_q_max_year_#=<i>integer value</i> </code> </p> </td> 
   <td colname="col4"> <p>這些參數可用來設定特定查詢的最小和最大日期範圍。 sp_ <span class="codeph"> min_day、 </span>sp_q_min_month <span class="codeph"> 、 </span>_q_min_year、 <span class="codeph"> sp_sp_max_year、 </span>sp_max_year和 <span class="codeph"></span><span class="codeph"></span><i></i><span class="codeph"></span>sp_max_yearQ參數套用至主查詢(sp_q Main Query Q)。 </p> <p>參 <span class="codeph"> 數名 </span>稱中的#會以1到16之間的數字取代(例如， <span class="codeph"> sp_q_min_day_6應 </span> 用於編號的查詢 <span class="codeph"> sp_q_6 </span>)。 </p> <p>只指定最小日期、最大日期或最小日期和最大日期都是合法的。 但是，對於給定的最小或最大值集，必須指定所有三個日期參數（日、月和年）。 依預設，會相對於格林威治標準時間搜尋所有日期。 </p> <p>下列程式碼區段可讓使用者在名為 <span class="codeph"> PublishDate的使用者定義欄位中，搜尋日期介於2000年1月1日至2000年12月31日之間的檔案中的「橘色」字 </span>: </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;Between:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_min_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Start&nbsp;Year 
      And:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_max_day_1"&nbsp;size="2"&nbsp;value="31"&gt;&nbsp;End&nbsp;Day 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_month_1"&nbsp;size="2"&nbsp;value="12"&gt;&nbsp;End&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;End&nbsp;Year </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>32 </p> </td> 
   <td colname="col2"> <p>sp_q_min,sp_q_max </p> </td> 
   <td colname="col03"> <p>sp_q _min_#、sp_q _max_#、sp_q exact_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_min=值 </span> </p> <p> <span class="codeph"> sp_q_max=值 </span> </p> <p> <span class="codeph"> sp_q_min_#=值 </span> </p> <p> <span class="codeph"> sp_q_max_#=值 </span> </p> <p> <span class="codeph"> sp_q_exact_#=value </span> </p> </td> 
   <td colname="col4"> <p>這些參數指定要套用至主查詢或編號查詢的最小值（和／或最大值）。 使用 <span class="codeph"> sp_q_min </span>、sp_q_max和 <span class="codeph"> sp_q_exact會 </span>影響主查詢( <span class="codeph"></span><span class="codeph"></span>sp_q主查詢)。 </p> <p>將參 <span class="codeph"> 數名 </span>稱中的#替換為1到16之間的數字(例如， <span class="codeph"> sp_q_min_8適 </span> 用於編號的查 <span class="codeph"> 詢sp_q_8 </span>)。 </p> <p>使用 <span class="codeph"> sp_q_exact_# </span> 是指定 <span class="codeph"> sp_q_min_#和 </span> sp_q_max_#的速記，它們的值相 <span class="codeph"></span> 同。 如 <span class="codeph"> 果指定sp_q_exact_# </span> ，則會忽略任何對應的 <span class="codeph"> sp_q_min_# </span> 或 <span class="codeph"> sp_q_max_#參 </span> 數。 </p> <p>sp_q_ <span class="codeph"> min_# </span>、 <span class="codeph"> sp_q_max_# </span> 和 <span class="codeph"></span> sp_q_exact_#參數可以選擇性地指定多個"|"分隔值。 例如，要搜索在「顏色」欄位中包含綠色或紅色值的文檔： <span class="codeph"> ...&amp;sp_q_exact_1=green|red&amp;sp_x_1=color </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>33 </p> </td> 
   <td colname="col2"> <p>sp_q_nocp </p> </td> 
   <td colname="col03"> <p>sp_q _nocp _# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_nocp= 1或0 </span> </p> <p> <span class="codeph"> sp_q_nocp_#= 1或0 </span> </p> </td> 
   <td colname="col4"> <p>預設參數值為 <span class="codeph"> 0, </span> 表示執行「公用片語」展開。 </p> <p>對於相應的 <span class="codeph"> 搜索查 </span> 詢設定為1時，不執行「常用片語」擴展。 </p> <p>使 <span class="codeph"> 用sp_q_nocp </span> 會影響主搜索查詢 <span class="codeph"> 參數sp_q </span>。 若要將此參數套用至編號的搜尋查詢，請 <span class="codeph"> 將 </span> 參數名稱中的#取代為對應的編號。 例如， <span class="codeph"> sp_q_nocp_8 </span> 適用於編號的搜 <span class="codeph"> 索查詢sp_q_8 </span>。 </p> <p> 
     <!--See also <xref href="c_about_common_phrases.xml#concept_4946E53586DF492EAEB1B7F757FD440F" format="dita" scope="local">About Common Phrases</xref>--> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>34 </p> </td> 
   <td colname="col2"> <p>sp_q_required </p> </td> 
   <td colname="col03"> <p>sp_q_required_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_required= 1或0或-1 </span> </p> <p> <span class="codeph"> sp_q_required_#= 1或0或-1 </span> </p> </td> 
   <td colname="col4"> <p>此參數可確定匹配是否必須(1)、可以(0)或不能(-1)出現在相應查詢中，以便在結果頁上返回文檔。 </p> <p>使用 <span class="codeph"> sp_q_required會 </span> 影響主查詢( <span class="codeph"> sp_q </span>)。 </p> <p>若要套用至已編號的查詢，請將參數名稱中的 <span class="codeph"></span> #取代為對應的編號(例如， <span class="codeph"> sp_q_required_8 </span> 套用至已編號的查詢 <span class="codeph"> sp_q_8 </span>)。 參數的預設值為1（必須匹配）。 </p> <p>若要在使用者定義的「平台」欄位中搜尋包含"calc"字詞但不包含"mac"、"win"或"all"的檔案，您的HTML搜尋表單可能包含下列行： </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="platform"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="calc"&gt; 
      Exclude:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="mac&nbsp;win&nbsp;all"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_q_required_1"&nbsp;value="-1"&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>35 </p> </td> 
   <td colname="col2"> <p>sp_redirect_if_one_result </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_redirect_ 
      if_one_result= <i>0 or 1</i> </code> </p> </td> 
   <td colname="col4"> <p>指定如果只有一個搜尋結果，是否重新導向至搜尋結果URL。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>36 </p> </td> 
   <td colname="col2"> <p>sp_referrer </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_referrer= url </span> </p> </td> 
   <td colname="col4"> <p>指定搜尋的反向連結URL。 在搜尋重寫規則中，搜尋結果會連結回與搜尋表單相同的網站時，此功能十分有用。 </p> <p>預設值是瀏覽器傳送的標準CGI HTTP_REFERRER值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>37 </p> </td> 
   <td colname="col2"> <p>sp_ro </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_ro=字 <span class="varname"> 段 </span>: <span class="varname"> 相關性 </span></span> </p> </td> 
   <td colname="col4"> <p>允許選擇性搜尋時間、每個欄位名稱、相關性控制。 參 <span class="codeph"> 數名 </span> 稱中的ro代表「相關性覆寫」。 該參數接受一或多個欄位名稱，後面接有冒號字元，後面接有0-10的相關性值。 </p> <p>例如，若要將欄位名稱"body"的關聯值設為10，當客戶執行搜尋時，參數會顯示如下： </p> <p> <span class="codeph"> sp_ro=body:10 </span> </p> <p>或者，若要在參數字串中指定多個欄位相關性覆寫，您可以使用垂直號分隔字元。 例如，若要將欄位名稱"body"和"title"的關聯值設為9，當客戶執行搜尋時，參數會顯示如下： </p> <p> <span class="codeph"> sp_ro=body:9|title:9 </span> </p> <p> <p>注意： 指定未參與相關搜尋的欄位沒有作用。 例如，如果您設定 <span class="codeph"> sp_ro=title:10 </span>，但未搜尋標題欄位名稱，則 <span class="codeph"> sp_ro </span><span class="codeph"></span> 參數無效。 換言之，使用sp_ro參數指定欄位名 <span class="codeph"> 稱並不會自 </span> 動搜尋該欄位；而只會覆寫該欄位的相關設定。 </p> </p> <p>請參 <a href="../c-about-settings-menu/c-about-metadata-menu.md#task_0A7657B63596421BB6DB3ED44F827AB3" type="task" format="dita" scope="local"> 閱編輯預定義或用戶定義的元標籤欄位 </a>。 </p> <p>請參 <a href="../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C" type="concept" format="dita" scope="local"> 閱關於查詢清除規 </a>則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>38 </p> </td> 
   <td colname="col2"> <p>sp_s </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_s=數字 </span> </p> </td> 
   <td colname="col4"> <p>指定排序順序。 Zero(0)是預設值，表示依相關性分數排序。 一(1)表示依日期排序，-1表示不排序。 </p> <p>您可以為sp_s參數的值指定 <span class="codeph"> 欄位名 </span> 稱。 例如， <span class="codeph"> sp_s=title會根據 </span> 標題欄位中包含的值對結果排序。 當使用欄位名作為 <span class="codeph"> sp_s參數的值時 </span> ，結果將按該欄位排序，然後按相關性子排序。 </p> <p>將「排序」欄位設定為「啟用 <span class="uicontrol"> 參考的中 </span><span class="uicontrol"></span><span class="uicontrol"></span><span class="uicontrol"></span><span class="uicontrol"></span> 繼資料」&gt;「啟用參考的定義」中的「升序」或「降序」。 </p> <p>您也可以在搜尋表單中多次設定 <span class="codeph"> sp_s參數，將數個排序欄 </span> 位指派給單一查詢。 下列範本行會設定搜尋結果，先依藝術家名稱、相簿名稱，再依追蹤名稱排序。 </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="artist"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="album"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="track"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Music&nbsp;Search"&gt; </code> </p> <p>您也可以在欄位名稱之前指定表格名稱限定詞，例如items.price，對符合表格的欄位資料進行排序。 有關表 <span class="codeph"> 匹配的詳細資訊，請 </span> 參閱sp_field_table參數。 </p> <p>如果按接近度進行搜索，則可以通過指定「接近度輸出欄位」來根據鄰近度對結果進行排序。 </p> <p>請參 <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> 閱關於鄰近搜尋 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>39 </p> </td> 
   <td colname="col2"> <p>sp_sr </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_sr=欄位 </span> </p> </td> 
   <td colname="col4"> <p>指定用於靜態排名的排名欄位。 欄位必須是關聯性大於0的「排名」類型欄位。 如果未 <span class="codeph"> 為查詢 </span> 提供sp_sr參數，則會自動選擇類型為Rank的欄位。 </p> <p>若要停用特定查詢的靜態排名，請為 <span class="codeph"> sp_sr加入NULL值 </span> (例如 <span class="codeph"> &lt;input type="hidden" name="sp_sr" value=""&gt; </span>)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>40 </p> </td> 
   <td colname="col2"> <p>sp_sfvl_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_sfvl_field=字串 </span> </p> </td> 
   <td colname="col4"> <p>指定要與搜尋範本中的 <span class="codeph"> &lt;search-field-value-list&gt;標籤搭配使用 </span> 的欄位名稱。 </p> <p>您可以指定 <span class="codeph"> 多個sp_sfvl_field </span> 參數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>41 </p> </td> 
   <td colname="col2"> <p> sp_sfvl_df_count </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_sfvl_df_count= <span class="varname"> &lt;整數值&gt; </span></span> </p> </td> 
   <td colname="col4"> <p> 
     <!--NEW 2/2/2014-->請求此搜 <span class="codeph"> 尋的最 <span class="varname"> 多 </span> &lt;integer_value&gt; </span> search-field-value-list動態 <span class="codeph"></span> 刻面欄位。 </p> <p>預設值為 0。最大允許值是為指定索引定義的dynamic-facet欄位、dynamic-facet-field-count的目前數目。 小於0的整數值會視為0。 在dynamic-facet-field-count <span class="codeph"> 上方指定的整數值 </span> 會限制為 <span class="codeph"> dynamic-facet-field-count </span>。 忽略非整數值；它們被視為預設值。 </p> <p>給定切片的搜索上限為此切片的 <span class="codeph"> dynamic-facet-field-count值允許的最大sp_sfvl_df_count </span><span class="codeph"></span> 值。 合併切片結果時， <span class="codeph"> sp_sfvl_df_count的有效最大值 </span> 是所有切片上 <span class="codeph"></span> 的最大實際sp_sfvl_df_count。 </p> <p>請參 <a href="../c-about-design-menu/c-about-dynamic-facets.md#task_D17F484130E448258100BAC1EEC53F39" format="dita" scope="local"> 閱設定動態面 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>42 </p> </td> 
   <td colname="col2"> <p> sp_sfvl_df_exclude </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> <span class="codeph"> sp_sfvl_df_exclude= &lt; <span class="varname"> field_name </span>&gt;[|&lt; <span class="varname"> field_name </span></span>&gt;||... </p> </td> 
   <td colname="col4"> <p> 指定要排除在此搜尋考量之外的特定動態Facet欄位清單。 </p> <p>依預設，會考慮所有動態Facet欄位。 </p> <p>請參 <a href="../c-about-design-menu/c-about-dynamic-facets.md#task_D17F484130E448258100BAC1EEC53F39" format="dita" scope="local"> 閱設定動態面 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>43 </p> </td> 
   <td colname="col2"> <p> sp_sfvl_df_include </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> <span class="codeph"> sp_sfvl_df_include= &lt; <span class="varname"> field_name </span>&gt;[|&lt; <span class="varname"> field_name </span></span>&gt;||... </p> </td> 
   <td colname="col4"> <p> 指定要包含在搜尋結果中的特定動態Facet欄位清單。 </p> <p> <p>注意： sp_ <span class="codeph"> sfvl_df_count參數 </span> 可決定要傳回的動態Facet欄位總數，包括透過 <span class="codeph"> sp_sfvl_df_include指定的任何欄位 </span>。 也就是說，使 <span class="codeph"> 用sp_sfvl_df_include不允許傳回動態Facet欄位的總計計數超過 </span> sp_sfvl_df_count <span class="codeph"></span>。 </p> </p> <p>請參 <a href="../c-about-design-menu/c-about-dynamic-facets.md#task_D17F484130E448258100BAC1EEC53F39" format="dita" scope="local"> 閱設定動態面 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>44 </p> </td> 
   <td colname="col2"> <p>sp_staged </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_staged= 0或1 </span> </p> </td> 
   <td colname="col4"> <p>如 <span class="codeph"> 果sp_staged=1 </span> 與查詢一起提交，則運行的查詢是分段搜索。 </p> <p>分段搜索使用當前分段的所有元件，包括索引和模板。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>45 </p> </td> 
   <td colname="col2"> <p>sp_start_day、sp_start_month、sp_start_year </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_start_day=數字 </span> </p> <p> <span class="codeph"> sp_start_month=數字 </span> </p> <p> <span class="codeph"> sp_start_year=數字 </span> </p> </td> 
   <td colname="col4"> <p>此三分數值指定搜尋的開始日期範圍，您可將其提供為一組。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>46 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_建議_q </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_sowlect_q=數 </span> </p> </td> 
   <td colname="col4"> <p>sp_ <span class="codeph"> sowkent_q參 </span> 數決定要與Sowskent服務一起使用的 <span class="codeph"> sp_q[_#] </span> 參數。 </p> <p>sp_sowkent_q的預設值為 <span class="codeph"> 0，這表示搜尋引擎使用 </span> sp_q的值來 <span class="codeph"></span> 判斷建議。 </p> <p>設 <span class="codeph"> 定sp_sowkent_q=1 </span> 以使用 <span class="codeph"> sp_q_1的值來 </span> 判斷建議，依此類推。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>47 </p> </td> 
   <td colname="col2"> <p>sp_t </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_t=字串 </span> </p> </td> 
   <td colname="col4"> <p>指定要使用的傳輸模板。 </p> <p>如果您想要針對搜尋帳戶中的每個區域使用不同的搜尋傳輸範本，以控制網站上核心搜尋結果的外觀，此參數很實用。 </p> <p>預設傳輸範本為「search」。 </p> <p>請參 <a href="../c-appendices/c-templates.md#reference_12AAB3B9F4C74C11956F1DBA95714C2F" type="reference" format="dita" scope="local"> 閱管理網站的多個傳輸範本 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>48 </p> </td> 
   <td colname="col2"> <p>sp_trace </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_trace= 0或1 </span> </p> </td> 
   <td colname="col4"> <p>當設為 <span class="codeph"> sp_stage=1時， </span>會啟用模擬器中的核心搜尋追蹤功能。 </p> <p>請參閱 <a href="../c-about-simulator.md#concept_020AA6751E32421A96A3455508364C7E" format="dita" scope="local"> 關於模擬器 </a>。 </p> <p> <p>注意： 如果未指定此參數，則核心搜索不會收集跟蹤資訊，且相關的核心搜索模板標籤沒有輸出。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>49 </p> </td> 
   <td colname="col2"> <p>sp_w,sp_w_control </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_w= <i>sound-alike-enable</i> </code> </p> <p> <code> sp_w_control=<i>sound-alike-control</i> </code> </p> </td> 
   <td colname="col4"> <p>指定應針對此特定查詢啟用或停用類似音效比對。 </p> <p>忽略「完全」的sp_w_control。 類似音效的比對已停用。 </p><p>忽略「Alike」的sp_w_control。 相似音效比對已啟用</p><p>「Anything（其他）」的sp_w_control是1。 類似音效的比對已停用。 </p><p>「Anything（其他）」的sp_w_control是其它任何值。 相似音效比對已啟用。 </p>sp_w_ <span class="codeph"> control參數可 </span> 讓您建立負面或正面措辭的核取方塊，供使用者控制類似音效的比對。 </p> <p>如 <span class="codeph"> 果使用sp_w_control=0 </span> ，則會使用一個措辭負面的核取方塊來設定 <span class="codeph"></span> sp_w參數，如下列範例所示： </p> <p> <code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="0"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="exact"&gt;No&nbsp;Sound-Alike&nbsp;matching </code> </p> <p>如果 <span class="codeph"> 使用sp_w_control=1 </span> ，則會使用措辭正面的核取方塊來設定 <span class="codeph"> sp_w </span> 參數，如下所示： </p> <p> <code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="1"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="alike"&gt;Sound-Alike&nbsp;matching </code> </p> <p>請參閱範例進階搜尋表單，以取得有關使用 <span class="codeph"> sp_w_control和 </span><span class="codeph"> sp_w參數的更多範例 </span> 。 </p> <p>請參閱 <a href="../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A" type="reference" format="dita" scope="local"> 進階搜尋表單範例 </a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>50 </p> </td> 
   <td colname="col2"> <p>sp_x </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_x=欄位 </span> </p> </td> 
   <td colname="col4"> <p>指定要搜索查詢字串的欄位。 任意表示搜尋所有欄位。 title表示僅搜尋標題欄位。 desc意指僅搜尋檔案說明欄位。 鍵表示僅搜尋檔案關鍵字。 body意指僅搜尋內文文字。 alt表示僅搜索替代文本。 url表示僅搜尋URL值。 target意指僅搜尋目標關鍵字。 在任何這些情況下，都會忽略對應 <span class="codeph"></span> sp_q參數中的"text:"、"desc:"、"keys:"、"body:"、"alt:"、"url:"和"target:"欄位字首的使用者規格。 如 <span class="codeph"> 果sp_x不存 </span> 在，或者設定為空字串或任何字串，則允許使用標準用戶欄位前置詞。 有關欄位前置詞的詳細資訊，請參閱搜索提示說明。 </p> <p>請參閱<a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local">關於搜尋</a>。 </p> <p>如需使用sp_x參數的範例，請參閱進階搜 <span class="codeph"> 尋表單說 </span> 明範例。 </p> <p>請參閱 <a href="../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A" type="reference" format="dita" scope="local"> 進階搜尋表單範例 </a>。 </p> <p>您可以建立以sp_x=any設定，在「選項&gt;元資料定義」下，搜索 <span class="uicontrol"> 「按預設搜索」設定為「按選項&gt; </span><span class="uicontrol"> 「元資料定義」的所有欄位 </span> , <span class="uicontrol"></span><span class="uicontrol"></span><span class="codeph"></span>以執行搜索。 預定義和用戶定義欄位都可用作sp_x參 <span class="codeph"> 數的 </span> 值。 </p> <p>您也可以多次設定sp_x參數，將多個欄位指派 <span class="codeph"> 給單 </span> 一查詢。 下列範本行可讓使用者查詢「Great Books」的「title」和「author」欄位。 </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="title"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="author"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Great&nbsp;Books"&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>51 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_x_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_x_#=欄位名 </span> </p> </td> 
   <td colname="col4"> <p>此參數指定要在對應的 <span class="codeph"> sp_q_#查詢中搜索的字 </span> 段。 # <span class="codeph"> 的 <span class="codeph"> 號 </span> 會以1到16(例如， </span> sp_x_8 <span class="codeph"></span>)之間的數字取代。 field-name是任何預先定義或使用者定義的欄位。 </p> <p>如果未為特定編 <span class="codeph"> 號的查詢提供 </span> sp_x_#參數，則在「Metadata <span class="uicontrol"> &gt; </span> Definitions」（通過查詢搜索）設定下，所有定義為「By Default <span class="uicontrol"></span><span class="uicontrol"></span><span class="uicontrol"></span> Set」（預設設定）的欄位都將被搜索。 </p> <p>例如，提交下清單格會傳回所有包含"great"的檔案，其中也包含"Fitzgerald"（在"author"欄位中）: </p> <p> <code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="author"&gt;Search&nbsp;only&nbsp;documents&nbsp;written&nbsp;by:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="Fitzgerald"&gt; </code> </p> <p>在單一搜尋請求中提供多個相同 <span class="codeph"> sp_x </span> 或 <span class="codeph"></span> sp_x_#參數例項，可將多個欄位名稱與特定查詢或編號查詢建立關聯。 </p> <p>例如，若要在"body"和"keys"欄位中搜尋"flower"，您可以建立包含下列資訊的搜尋表單： </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="body"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="keys"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="flower"&gt; </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 使用後端搜尋CGI參數的典型範例 {#section_260012BBC2514CC9A8E02E53DE8B41EE}

下列連結查詢會以&quot;Music&quot;作為搜尋查詢，開始搜尋，並使用所有預設參數。 請注意，URL會分割為兩行，以利閱讀。 在您的HTML中，此連結應全部在一行上。

```
<a href="https://search.atomz.com/search/?sp_q=Music&sp_a=sp99999999"> 
Testing...</a>
```

相同的功能通常以表單來定義：

```
<form action="https://search.atomz.com/search/"> 
<input size=12 name="sp_q" value="Music"><br> 
<input type=hidden name="sp_a" value="sp99999999"> 
<input type=submit value="Search"><br> 
</form>
```

在開始搜索時，通常應使用預設參數。 如此，第一頁會依相關性排序，並允許客戶選擇其他頁面和其他選項。 如果您網站上的搜尋表單包含系列選項，請將系列名稱作為參數傳入。

## 使用後端搜尋CGI參數的詳細範例 {#section_5FA3C620D5124FB2AB28857F8D8473F6}

下清單單查詢會顯 `25` 示結果開始 `10`。 系統不會顯示摘要，排序順序是按日期，且會使用名為的 `support` 系列。 只會傳回最近30天內的檔案。

```
<form action="https://search.atomz.com/search/"> 
<input size=12 name="sp_q"><br> 
<input type=hidden name="sp_a" value="sp99999999"> 
<input type=submit value="Search"><br> 
<input type=hidden name=sp_n value=10> 
<input type=hidden name=sp_c value=25> 
<input type=hidden name=sp_m value=0> 
<input type=hidden name=sp_s value=1> 
<input type=hidden name=sp_k value="support"> 
<input type=hidden name=sp_date_range value=30> 
</form>
```

