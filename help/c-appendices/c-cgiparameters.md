---
description: 瞭解如何使用各種CGI參數。
solution: Target
title: CGI參數
topic: 附錄、網站搜尋與銷售
uuid: a5f43547-bc15-44aa-ba23-6b8b573e09d2
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1943'
ht-degree: 1%

---


# CGI參數{#cgi-parameters}

## CGI參數{#concept_F395999090FE4926B38BC73D5E612800}

## 搜索CGI參數{#reference_DA27A8B0728246DA94994885E1353890}

提供搜尋表單程式碼，您可將其複製並貼至網站的HTML(**[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**)。

請參閱[將搜索表單的HTML代碼複製到……](../c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7)。

您也可以設定搜尋表單本身或指令碼中所列的參數。 除了下面列出的參數外，您還可以使用後端搜尋參數來控制搜尋。

請參閱[後端搜尋CGI參數](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。

搜尋請求包含基本URL。 基本URL會指出客戶正在搜尋的帳戶，以及一組CGI參數（金鑰值配對），用以指出如何傳回相關帳戶所需的搜尋結果。

基本URL與特定帳戶以及分段或即時環境相關聯。 您可以向帳戶管理員請求基本URL的多個別名。 例如，一家名為Megacorp的公司可能有兩個與其帳戶關聯的基本URL:`https://search.megacorp.com`和`https://stage.megacorp.com`。 前者URL會搜尋其即時索引，後者URL則會搜尋其分段索引。

支援三種格式的CGI參數。 預設情況下，您的帳戶配置為使用分號分隔CGI參數，如下例所示：

`https://search.megacorp.com?q=shoes;page=2`

如果您願意，您可以讓帳戶管理員設定您的帳戶，使用&amp;符號來分隔CGI參數，如下列範例所示：

`https://search.megacorp.com?q=shoes&page=2`

另外還支援另一種格式，稱為SEO格式，其中正斜線`/`用來取代分隔符號，並與下列範例中的等號相同：

`https://search.megacorp.com/q/shoes/page/2`

只要使用SEO格式傳送請求，所有輸出連結都會以相同格式傳回。

| 引導搜尋參數 | 範例 | 說明 |
|--- |--- |--- |
| q | `q=string` | 指定搜索的查詢字串。 此參數會映射至`sp_q`後端搜尋參數。  請參閱[後端搜尋CGI參數](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| q# | `q#=string` | Faceting（在指定欄位內搜尋）是透過編號q和x參數來完成。  q參數會定義您在Facet中搜尋的詞語，如對應的編號x參數所示。<br>例如，如果您有兩個刻面，其名稱為size和color，則可以有q1=small;x1=size;q2=red;x2=color。此參數會映射至`sp_q_exact_#`後端搜尋參數。  <br>請參 [閱後端搜尋CGI參數](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| x 中的頁面載入要求# | `q#=string` | Faceting（在指定欄位內搜尋）是透過編號q和x參數來完成。  q參數會定義您在Facet中搜尋的詞語，如對應的編號x參數所示。 <br>例如，如果您有兩個刻面，其名稱為size和color，則可以有q1=small;x1=size;q2=red;x2=color。此參數會映射至`sp_x_#`後端搜尋參數。  <br>請參 [閱後端搜尋CGI參數](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| 集合 | `collection=string` | 指定要用於搜尋的系列。  此參數會映射至`sp_k`後端搜尋參數。  請參閱[後端搜尋CGI參數](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| 計數 | `count=number` | 指定顯示的結果總計。  預設值定義於[!UICONTROL Settings ] > [!UICONTROL Searching ] > [!UICONTROL Searches ]。.  此參數會映射至`sp_c`後端搜尋參數。  請參閱[後端搜尋CGI參數](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| 頁面 | `page=number` | 指定返回的結果頁。 |
| 排名 | `rank=field` | 指定用於靜態排名的排名欄位。  欄位必須是關聯性大於0的「排名」類型欄位。  此參數會映射至`sp_sr`後端參數。  請參閱[後端搜尋CGI參數](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |
| 排序 | `sort=number` | 指定排序順序。<br>「0」是預設值，並依關聯分數排序；「1」按日期排序；&quot;-1&quot;不排序。使用者可以指定`sp_s`參數值的欄位名稱。  例如，`sp_s=title`會根據標題欄位中包含的值來排序結果。 當使用欄位名稱作為` sp_s `參數的值時，結果會依該欄位排序，然後依相關性子排序。  若要啟用此功能，請按一下「[!UICONTROL Settings ] > [!UICONTROL Metadata ] > [!UICONTROL Definitions ]」。 在「定義」頁面上，按一下[!UICONTROL Add New Field ]或按一下[!UICONTROL Edit ]獲取特定欄位名稱。 在[!UICONTROL Sorting ]下拉式清單中，選取[!UICONTROL Ascending ]或[!UICONTROL Descending ]。 此參數會映射至`sp_s`後端搜尋參數。 <br>請參 [閱後端搜尋CGI參數]。(../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。 |

## 後端搜尋CGI參數{#reference_582E85C3886740C98FE88CA9DF7918E8}

通常客戶會與稱為引導式搜尋的表現層互動。 但是，理論上可以略過引導式搜尋層，並直接使用本頁所述的CGI參數與後端核心搜尋互動。

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
   <td colname="col3"> <p> <code>sp_a= string </code> </p> </td> 
   <td colname="col4"> <p>指定帳號字串。 此參數為必要參數，且必須是有效的帳號字串。 您可以在「<span class="uicontrol">設定</span> &gt; <span class="uicontrol">帳戶選項</span> &gt; <span class="uicontrol">帳戶設定</span>」下找到您的帳戶號碼字串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>sp_advanced </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_advanced= 0 or 1 </code> </p> </td> 
   <td colname="col4"> <p>如果<code>sp_advanced=1 </code>隨查詢提交，則搜索模板中<code>&lt;search-if-advanced&gt; </code>標籤和<code>&lt;/search-if-advanced&gt; </code>標籤之間的所有代碼都將用於搜索表單。 將忽略<code>&lt;search-if-not-advanced&gt; </code>標籤和<code>&lt;/search-if-not-advanced&gt; </code>標籤之間的所有代碼。 如果提交了<code>sp_advanced=0 </code>（或任何其他值），則會忽略&lt;search-if-advanced&gt;範本區塊，並使用&lt;search-if-not-advanced&gt;範本區塊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>sp_c </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_c= number </code> </p> </td> 
   <td colname="col4"> <p>指定要顯示的結果總計。 預設值為 10。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>sp_context_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_context_field= <i>field</i> </code> </p> </td> 
   <td colname="col4"> <p>收集指定欄位的內容相關資訊。 收集的資訊會透過<code>&lt;search-context&gt; </code>範本標籤輸出至搜尋結果。 預設值為 <code>body </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>sp_d </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_d= type </code> </p> </td> 
   <td colname="col4"> <p>指定要執行的日期範圍搜尋的類型。 類型的可能值是任意值，這表示不執行日期範圍搜索、自定義，指出應使用<code>sp_date_range </code>的值確定要搜索的日期，並具體指出使用<code>sp_start_day </code>、<code>sp_start_month </code>、<code>sp_start_year </code>、<code>sp_end_day </code>、<code>sp_end_month </code>和<code>sp_end_year </code>中的值確定要搜索的日期範圍。 <code>sp_d </code> 只有在您的搜尋表單包含依自訂範圍(依方式 <code>sp_date_range </code>)或依特定開始和結束日期範圍進行搜尋的選項時，才需要此選項。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_d_# </p> </td> 
   <td colname="col3"> <p> <code>sp_d_#= type </code> </p> </td> 
   <td colname="col4"> <p>指定要對相應<code>sp_q_# </code>查詢執行的日期範圍搜索的類型。 "#"被1到16之間的數字取代（例如<code>sp_d_8 </code>，適用於編號的查詢<code>sp_q_8 </code>）。 </p> <p>您可以將<code>type </code>設為任何，這表示不執行日期範圍搜尋、自訂，指出<code>sp_date_range_# </code>的值用於決定要搜尋的日期，而具體指出<code>sp_q_min_day_# </code>、<code>sp_q_min_month_# </code>、<code>sp_q_min_year_# </code>、<code>sp_q_max_day_# </code>、<code>sp_q_max_month_# </code>和<code>sp_q_max_year_# </code>中的值應用於決定日期範圍。 只有當您的搜尋表單包含依自訂範圍（透過<code>sp_date_range_# </code>）或依特定開始和結束日期範圍進行搜尋的選項時，才需要使用<code>sp_d_# </code>。 </p> </td> 
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
   <td colname="col4"> <p>指定要套用至對應<code>sp_q_# </code>查詢的預先定義日期範圍。 "#"被1到16之間的數字取代（例如<code>sp_date_range_8 </code>，適用於編號的查詢<code>sp_q_8 </code>）。 </p> <p>大於或等於零的值指定今天之前要搜索的天數。 例如，0的值指定今天；值1表示今天和昨天；值30指定在最近30天內，依此類推。 </p> <p>低於零的值會指定自訂範圍，如下所示： </p> <p>-1 = "無"，與指定無日期範圍相同。 </p> <p>-2 = "本週"，在當周的週日到週六搜尋。 </p> <p>-3 = "上週"，在當周前一週的星期日到星期六進行搜尋。 </p> <p>-4 = "本月"，搜尋當月日期。 </p> <p>-5 = "上個月"，搜尋當月前一個月的日期。 </p> <p>-6 = 「今年」，其搜索日期在當年。 </p> <p>-7 = 「去年」，搜尋日期在當年前一年。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>9 </p> </td> 
   <td colname="col2"> <p>sp_dedupe_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_dedupe_field= <i>fieldname</i> </code> </p> </td> 
   <td colname="col4"> <p>指定一個欄位，用於刪除上的重複搜索結果。 該欄位上的所有重複結果都會從搜尋結果中移除。 例如，若是<code>sp_dedupe_field=title </code>，則搜尋結果中只會顯示指定標題的頂端結果（沒有兩個結果會有相同的標題欄位內容）。 對於多值（允許清單）類型欄位，將使用整個欄位內容進行比較。 只能指定一個欄位。 欄位名稱中不允許使用「表限定詞」。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>10 </p> </td> 
   <td colname="col2"> <p>sp_e </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_e= number </code> </p> </td> 
   <td colname="col4"> <p>指定應針對查詢字串中具有數字以上字元的任何字詞，進行自動萬用字元擴增。 換言之，<code>sp_e=5 </code>指定應以萬用字元'*'來擴充包含5個或更多字元的字詞，例如"query"或"number"，使搜尋等同於搜尋"query*"或"number*"。 字元數較少的字詞不會展開，因此搜尋「word」時不會自動擴充萬用字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>11 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_e_# </p> </td> 
   <td colname="col3"> <p> <code>sp_e_#= number </code> </p> </td> 
   <td colname="col4"> <p>指定自動通配符擴展對於具有多於數字字元的對應<code>sp_q_# </code>查詢字串中的任何字進行。 換言之，<code>sp_e_2=5 </code>指定在<code>sp_q_2 </code>查詢字串中含有5個或多個字元的字詞，例如"query"或"number"，應以萬用字元' <code>* </code>'展開，使搜尋等同於搜尋"query*"或"number*"。 字元數較少的字詞不會展開，因此在<code>sp_q_2 </code>中搜尋"word"時，不會自動擴充萬用字元。 </p> </td> 
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
   <td colname="col3"> <p> <code>sp_f= string </code> </p> </td> 
   <td colname="col4"> <p>指定查詢參數字串的字元集（如<code>sp_q </code>）。 此字串必須始終與包含搜尋表單之頁面的字元集相符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>14 </p> </td> 
   <td colname="col2"> <p>sp_field_table </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_field_ table=table: field,field... </code> </p> </td> 
   <td colname="col4"> <p>定義由給定欄位組成的邏輯資料表。 例如，由"color"、"size"和"price"欄位組成的名為"items"的表格會定義為： </p> <p> <code>sp_field_table=items:color,size,price </code> </p> <p>邏輯表與已選中「允許清單」的欄位（在<span class="uicontrol">設定</span> &gt; <span class="uicontrol">元資料</span> &gt; <span class="uicontrol">定義</span>下）一起使用時最有用。 所有將欄位名稱作為值的CGI參數和模板標籤，可以選擇指定表名，後面跟有"。" 在欄位名稱之前（例如<code>sp_x_1=tablename.fieldname </code>）。 </p> <p>例如，要搜索包含一個或多個「大」（其中項目表示為並行元資料行）大小為「大」的「紅色」項目的文檔，可以使用以下內容： </p> <p> <code> sp_q_exact_1=red&amp;sp_x_1=items.color&amp; sp_q_exact_2=large&amp;sp_x_2=items.size&amp;sp_field_table=items:color,size,price </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>15 </p> </td> 
   <td colname="col2"> sp_i </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> </p></td><td colname="col4"><p></p><p></p><p><code>sp_i=1 </code><code>sp_i=2 </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_k= string </code></p></td><td colname="col4"><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_l= string </code></p></td><td colname="col4"><p><code>sp_q </code><code>string </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_literal= 0 or 1 </code></p></td><td colname="col4"><p><code>sp_literal=1 </code></p><p><code>sp_literal=0 </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_m= number </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_n= number </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_not_found_page= url </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_p= any/all/phrase </code></p></td><td colname="col4"><p><code>any </code><code>all </code><code>phrase </code></p><p><code>phrase </code><code>all </code><code>sp_p </code></p><p></p><p></p><p><code>sp_p </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_p_#= any/all/phrase </code></p></td><td colname="col4"><p><code>sp_q_# </code><code>sp_p_8 </code><code>sp_q_8 </code><code>any </code><code>all </code><code>phrase </code></p><p><code>all </code><code>phrase </code><code>sp_p_# </code><code>any </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_pt= <i>exact/equivalent/compatible</i> </code></p></td><td colname="col4"><p><code>exact </code><code>equivalent </code><code>compatible </code><code>sp_p </code><code>exact </code><code>sp_p </code><code>all </code><code>phrase </code><code>equivalent </code><code>sp_pt </code><code>compatible </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_pt_#= <i>exact/equivalent/compatible</i> </code></p></td><td colname="col4"><p><code>sp_q_# </code><code>sp_p_8 </code><code>sp_q_8 </code><code>exact </code><code>equivalent </code><code>exact </code><code>compatible </code><code>sp_p_# </code><code>exact </code><code>sp_p_# </code><code>equivalent </code><code>sp_pt_# </code><code>compatible </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q= string </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_#= text </code></p></td><td colname="col4"><p><code>sp_q_# </code><code>sp_q_1 </code><code>sp_q_16 </code></p><p></p><p><code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="books"&gt; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_day= integer value </code></p><p><code>sp_q_month= integer value </code></p><p><code>sp_q_year= integer value </code></p><p><code>sp_q_day_#= integer value </code></p><p><code>sp_q_month_#= integer value </code></p><p><code>sp_q_year_#= integer value </code></p></td><td colname="col4"><p><code>sp_q_day </code><code>sp_q_month </code><code>sp_q_year </code><code>sp_q </code></p><p><code># </code><code>sp_q_day_6 </code><code>sp_q_6 </code></p><p><code>PublishDate </code></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt; Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;On&nbsp;:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Month &lt;input&nbsp;type="text"&nbsp;name="sp_q_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Year&nbsp; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_q_location=<i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code></p><p><code> sp_q_location_#= <i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code></p></td><td colname="col4"><p><code>sp_q_location </code><code>sp_q_location_# </code><code># </code></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_q_max_relevant_distance= <i>value</i> </code></p><p><code> sp_q_max_relevant_distance_#= <i>value</i> </code></p></td><td colname="col4"><p><code>sp_q_max_relevant_distance </code><code>sp_q_max_relevant_distance_# </code><code># </code></p><p><code>sp_q_max_relevant_distance </code></p><p><code>sp_q_max_relevant_distance_# </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p><p></p></td><td colname="col03"><p></p><p></p></td><td colname="col3"><p><code> sp_q_min_day=<i>integer value</i> </code></p><p><code> sp_q_min_month=<i>integer value</i> </code></p><p><code> sp_q_min_year=<i>integer value</i> </code></p><p><code> sp_q_max_day=<i>integer value</i> </code></p><p><code> sp_q_max_month=<i>integer value</i> </code></p><p><code> sp_q_max_year=<i>integer value</i> </code></p><p><code> sp_q_min_day_#=<i>integer value</i> </code></p><p><code> sp_q_min_month_#=<i>integer value</i> </code></p><p><code> sp_q_min_year_#=<i>integer value</i> </code></p><p><code> sp_q_max_day_#=<i>integer value</i> </code></p><p><code> sp_q_max_month_#=<i>integer value</i> </code></p><p><code> sp_q_max_year_#=<i>integer value</i> </code></p></td><td colname="col4"><p><code>sp_q_min_day </code><code>sp_q_min_month </code><code>sp_q_min_year </code><code>sp_q_max_day </code><code>sp_q_max_month </code><code>sp_q </code></p><p><code># </code><code>sp_q_min_day_6 </code><code>sp_q_6 </code></p><p></p><p><code>PublishDate </code></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;Between:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_min_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Start&nbsp;Year 
      And:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_max_day_1"&nbsp;size="2"&nbsp;value="31"&gt;&nbsp;End&nbsp;Day 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_month_1"&nbsp;size="2"&nbsp;value="12"&gt;&nbsp;End&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;End&nbsp;Year </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_min= value </code></p><p><code>sp_q_max= value </code></p><p><code>sp_q_min_#= value </code></p><p><code>sp_q_max_#= value </code></p><p><code>sp_q_exact_#=value </code></p></td><td colname="col4"><p><code>sp_q_min </code><code>sp_q_max </code><code>sp_q_exact </code><code>sp_q </code></p><p><code># </code><code>sp_q_min_8 </code><code>sp_q_8 </code></p><p><code>sp_q_exact_# </code><code>sp_q_min_# </code><code>sp_q_max_# </code><code>sp_q_exact_# </code><code>sp_q_min_# </code><code>sp_q_max_# </code></p><p><code>sp_q_min_# </code><code>sp_q_max_# </code><code>sp_q_exact_# </code><code>...&amp;sp_q_exact_1=green|red&amp;sp_x_1=color </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_nocp= 1 or 0 </code></p><p><code>sp_q_nocp_#= 1 or 0 </code></p></td><td colname="col4"><p><code>0 </code></p><p><code>1 </code></p><p><code>sp_q_nocp </code><code>sp_q </code><code># </code><code>sp_q_nocp_8 </code><code>sp_q_8 </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_required= 1 or 0 or -1 </code></p><p><code>sp_q_required_#= 1 or 0 or -1 </code></p></td><td colname="col4"><p></p><p><code>sp_q_required </code><code>sp_q </code></p><p><code># </code><code>sp_q_required_8 </code><code>sp_q_8 </code></p><p></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="platform"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="calc"&gt; 
      Exclude:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="mac&nbsp;win&nbsp;all"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_q_required_1"&nbsp;value="-1"&gt; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_redirect_ 
      if_one_result= <i>0 or 1</i> </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_referrer= url </code></p></td><td colname="col4"><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p></p></td><td colname="col4"><p><code>ro </code></p><p></p><p><code>sp_ro=body:10 </code></p><p></p><p><code>sp_ro=body:9|title:9 </code></p><p><p><code>sp_ro=title:10 </code><code>title </code><code>sp_ro </code><code>sp_ro </code></p></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_s= number </code></p></td><td colname="col4"><p></p><p><code>sp_s </code><code>sp_s=title </code><code>sp_s </code></p><p></p><p><code>sp_s </code></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="artist"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="album"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="track"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Music&nbsp;Search"&gt; </code></p><p><code>sp_field_table </code></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_sr= field </code></p></td><td colname="col4"><p><code>sp_sr </code></p><p><code>sp_sr </code><code>&lt;input type="hidden" name="sp_sr" value=""&gt; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_sfvl_field= string </code></p></td><td colname="col4"><p><code>search-field-value-list</code></p><p><code>sp_sfvl_field </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p></p></td><td colname="col4"><p><code>search-field-value-list </code></p><p><code>dynamic-facet-field-count </code><code>dynamic-facet-field-count </code></p><p><code>sp_sfvl_df_count </code><code>dynamic-facet-field-count </code><code>sp_sfvl_df_count </code><code>sp_sfvl_df_count </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p></p><p></p></td><td colname="col4"><p></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p></p><p></p></td><td colname="col4"><p></p><p><p><code>sp_sfvl_df_count </code><code>sp_sfvl_df_include </code><code>sp_sfvl_df_include </code><code>sp_sfvl_df_count </code></p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_staged= 0 or 1 </code></p></td><td colname="col4"><p><code>sp_staged=1 </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_start_day= number </code></p><p><code>sp_start_month= number </code></p><p><code>sp_start_year= number </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_suggest_q= number </code></p></td><td colname="col4"><p><code>sp_suggest_q </code><code>sp_q[_#] </code></p><p><code>sp_suggest_q </code><code>sp_q </code></p><p><code>sp_suggest_q=1 </code><code>sp_q_1 </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_t= string </code></p></td><td colname="col4"><p></p><p></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_trace= 0 or 1 </code></p></td><td colname="col4"><p><code>sp_stage=1 </code></p><p></p><p><p></p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_w= <i>sound-alike-enable</i> </code></p><p><code> sp_w_control=<i>sound-alike-control</i> </code></p></td><td colname="col4"><p></p><p></p><p></p><p></p><p></p><code>sp_w_control </code></p><p><code>sp_w_control=0 </code><code>sp_w </code></p><p><code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="0"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="exact"&gt;No&nbsp;Sound-Alike&nbsp;matching </code></p><p><code>sp_w_control=1 </code><code>sp_w </code></p><p><code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="1"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="alike"&gt;Sound-Alike&nbsp;matching </code></p><p><code>sp_w_control </code><code>sp_w </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_x= field </code></p></td><td colname="col4"><p><code>sp_q </code><code>sp_x </code></p><p></p><p><code>sp_x </code></p><p></p><p><code>sp_x=any </code><code>sp_x </code></p><p><code>sp_x </code></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="title"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="author"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Great&nbsp;Books"&gt; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_x_#= field-name </code></p></td><td colname="col4"><p><code>sp_q_# </code><code> # </code><code>sp_x_8 </code></p><p><code>sp_x_# </code></p><p></p><p><code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="author"&gt;Search&nbsp;only&nbsp;documents&nbsp;written&nbsp;by:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="Fitzgerald"&gt; </code></p><p><code>sp_x </code><code>sp_x_# </code></p><p></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="body"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="keys"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="flower"&gt; </code></p></td></tr></tbody></table>

## 使用後端搜尋CGI參數{#section_260012BBC2514CC9A8E02E53DE8B41EE}的典型範例

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

## 使用後端搜尋CGI參數{#section_5FA3C620D5124FB2AB28857F8D8473F6}的詳細範例

以下表單查詢顯示`25`結果，從結果`10`開始。 系統不會顯示摘要，排序順序是依日期，並使用名為`support`的系列。 只會傳回最近30天內的檔案。

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

