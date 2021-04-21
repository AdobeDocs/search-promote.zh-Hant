---
description: 使用「重寫規則」功能表來設定編目和搜尋URL和標題規則。
solution: Target
subtopic: Rewrite Rules
title: 關於重寫規則菜單
topic-legacy: Settings,Site search and merchandising
uuid: 77ee84dd-fdba-4d34-ae8e-2fe786599800
exl-id: cff17ead-6997-4ff6-a995-7ca020b06d50
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '10197'
ht-degree: 0%

---

# 關於重寫規則菜單{#about-the-rewrite-rules-menu}

使用「重寫規則」功能表來設定編目和搜尋URL和標題規則。

## 關於編目清單儲存URL規則{#concept_B71CF4C8030A4A74A22C3BFE4DE3B865}

「編目URL規則」會指定如何重寫它在Web內容中遇到的URL。 您可以指定不限數量的規則和條件，並可以控制所遇到URL的任何部分。

<!-- 

c_about_crawl_list_store_url_rules.xml

 -->

編目規則對於重寫URL的動態部分最有用，例如作業識別碼，此識別碼對每位造訪您網站的客戶都是唯一的。 您也可以使用重寫規則，從搜尋自動機隱藏URL的部分，例如查詢參數。 依預設，不會指定任何規則，也不會執行URL重寫。

當網站編目時，內嵌內容URL會儲存在要編目之其他網頁的臨時清單中。 在將URL新增至此清單之前，會先套用商店重寫規則。 通常，「商店」重寫規則用於從URL移除作業階段ID或強制執行特定的作業階段ID以進行編目。 當搜索自動機從清單中檢索URL時，檢索重寫規則將用於再次操作該URL的部分。 通常，擷取規則會用來將時間敏感資料插入URL。 這個最終URL可用來從您的網站擷取頁面。

請參閱[關於編目清單擷取URL規則](../c-about-settings-menu/c-about-rewrite-rules-menu.md#concept_EC8E2E48B99A458D8567B526C9827CBA)。

通常，您只使用「商店URL規則」。 只有當URL包含動態資料（如作業ID），且該動態資料會隨著時間而變更以維持有效時，才需要擷取URL規則。 在這種情況下，您會使用「儲存URL規則」，從所遇到的URL取得資料的最新狀態。 然後，當搜索自動機嘗試檢索頁面時，您使用「檢索URL規則」將該資料添加到每個URL。

每個規則都以重寫規則(RewriteRule)指令和一個或多個可選重寫條件(RewriteCond)指定。 規則的順序很重要。 規則集會依規則循環。 當規則符合時，它會循環執行任何對應的重寫條件。 以下列方式指定編目URL規則：

```
RewriteCond TestString CondPattern [Flags] 
RewriteRule Pattern Substitution [Flags]
```

遇到內嵌的URL時，搜尋自動機會嘗試將URL與每個編目規則的模式相符。 如果模式匹配，重寫引擎將查找相應的RewriteCond指令。 如果沒有條件，則URL會以由「替代」字串構成的新值取代，並繼續規則集中的下一個規則。 如果條件存在，則會依其列出順序加以處理。 重寫引擎嘗試將條件模式(CondPattern)與測試字串(TestString)相匹配。 如果兩者符合，則會處理下一個條件，直到沒有其他條件可用為止。 如果所有條件都符合，則URL會以規則中指定的替代項目取代。 如果條件未滿足，則完整條件集和相應規則將失敗。

## 關於RewriteRule指令{#section_162122340BB34F12BB9A36DC9349092B}

RewriteRule指令具有以下格式：

```
           
<i>RewriteRule Pattern Substitution [Flags]</i> 
        
```

`Pattern` 可以是POSIX規則運算式，會套用至目前的URL。「目前的URL」可能與原始要求的URL不同，因為舊版規則可能已比對並變更URL。

請參閱[規則運算式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

您不能使用&quot;not&quot;字元(&#39;!&#39;) 來為模式加上首碼。 「not」字元可讓您否定模式，即只有在目前的URL不符合此模式時，才會為true。 當比對負面模式或作為最終預設規則時，可使用&quot;not&quot;字元。

>[!NOTE]
>
>不能在模式中同時使用&quot;not&quot;字元和分組的萬用字元。 此外，當替代字串包含$N時，您無法使用否定的模式。

可以使用括弧在陣列中建立反參照，該反參照可由「替代」(Substitution)和「CondPattern」(CondPattern)參照。

**替** 代URL由包含以下內容的替代字串替換：

純文字檔案：傳遞的文字未變更。

背向參照提供對「陣列」或「條件陣列」的分組部分（內括弧）的訪問。 以下是兩種類型的回溯參照：

* **RewriteRule** Backreferences這些匹配對應RewriteRule模式中的回參考，格式為$N(0)  &lt;>例如, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2.`

* **RewriteCond回** 溯參考這些符合上次相符RewriteCondCondPattern中的回溯參考，格式為%N(0)  &lt;>

變數：這些變數的格式為%{NAME_OF_VARIABLE}，其中NAME_OF_VARIABLE是已定義變數名稱的字串。 有關設定環境變數的詳細資訊，請參閱`*[E]*`標籤。

函式：這些函式的格式為${NAME_OF_FUNCTION:key}，其中NAME_OF_FUNCTION如下：

* tolower使&#x200B;*key*&#x200B;中的所有字元都小寫。
* toupper使&#x200B;*key*&#x200B;中的所有字元都大寫。
* escape URL —— 對&#x200B;*key*&#x200B;中的所有字元進行編碼。
* 字元a...z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9&#39;、&#39;*&#39;、&#39;-&#39;、&#39;.&#39;、&#39;/&#39;、&#39;@&#39;和&#39;_&#39;未變；空格會轉譯為&#39;+&#39;，而所有其他字元則會轉換為其%xx URL編碼等同字元。
* 取消轉義會將&#39;+&#39;轉換回空格，所有%xx URL編碼字元都轉換回單一字元。

>[!NOTE]
>
>有一個特殊的替代字串：`'-'`，表示&quot;NO替代&quot;。 `'-'`字串常會與C(chain)標幟搭配使用，讓您在發生替代之前，將URL與數種模式相符。

**旗標**

（可選）將標籤括在方括弧`[]`中。 多個標幟以逗號分隔。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>旗標 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>最後一個規則。 </p> <p>停止重寫進程，不應用任何附加重寫規則。 使用此標幟可防止對目前URL進行任何進一步處理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>下一輪。 </p> <p> 使用上次重寫規則（而非原始URL）的URL，重新執行重寫程式（從第一個重寫規則開始）。 小心別製造死循環！ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>與下一個規則連結。 </p> <p>將目前規則連結至下一個規則（也可以將其連結至下一個規則，依此類推）。 如果規則匹配，則替代進程照常繼續。 如果規則不符合，則會跳過所有後續的連結規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>沒案子。 </p> <p> 當模式與目前的URL相符時，讓模式不區分大小寫（即，'A-Z'和'a-z'之間沒有差異）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>略過下一個規則。 </p> <p> 如果目前的規則相符，此標幟會強制重寫引擎略過規則集中的下一個num規則。 使用此標幟來建立偽if-then-else結構。 then-clause的最後一個規則變為skip=N，其中N是else-clause中的規則數。 </p> <p> <p>注意： 此標幟與'chain|C'標幟不同！) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>設定環境變數。 </p> <p>建立設定為值VAL的環境變數"VAR"，其中VAL可包含展開的規則運算式反向參照$N和%N。 您可多次使用此標幟來設定多個變數。 變數稍後可透過%{VAR}在下列RewriteCond模式中取消參考。 </p> <p>使用此標幟可移除並記住URL中的資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>儲存重寫規則和檢索重寫規則共用變數值。 由於這種行為，您可在遇到並儲存內嵌URL時，將變數設為時間敏感的sessionid值。 從臨時儲存清單中檢索下一個URL時，可以在檢索該頁之前向其添加最新的sessionid值。

**具有函式的RewriteRule示例**

假設您有區分大小寫的伺服器，以不同方式處理字串`"www.mydomain.com"`和`"www.MyDomain.com"`。 為了讓您的伺服器正常運作，請確定網域一律為`"www.mydomain.com"`，即使某些檔案包含參照`"www.MyDomain.com."`的連結。若要這麼做，您可使用下列規則：

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2
```

此重寫規則使用函式`tolower`重寫URL的網域部分，以確保其始終為小寫，如下所述：

1. 模式`(^https://([^/]*)(.*)$)`包含一個背向引用`([^/]*)`，它匹配URL中`https://`和第一個`/`之間的所有字元。 此模式也包含第二個反向參考`(.*)`，與URL中所有剩餘字元相符。

1. 替代`(https://${tolower:$1}$2)`會告訴搜尋引擎使用第一個反向參考`(https:// ${tolower:$1}$2)`上的`tolower`函式重寫URL，而URL的其餘部分則未變更`(https://${tolower:$1} $2)`。

因此，表單`https://www.MyDomain.com/INTRO/index.Html`的URL被重寫為`https://www.mydomain.com/INTRO/index.Html`。

## 關於RewriteCond指令{#section_CD5A19B2D3204F73B645411931FC34A1}

RewriteCond指令定義規則條件。 當RewriteCond在RewriteRule之前時，只有在規則的模式與當前標題匹配且附加條件適用時，才使用規則。 重寫條件採用下列形式：

```
           
<i>RewriteCond TestString CondPattern [Flags]</i> 
        
```

`TestString` 是一個字串，可以包含以下結構：

純文字檔案：傳遞的文字未變更。

背向參照提供對「陣列」或「條件陣列」的分組部分（內括弧）的訪問。 以下是兩種類型的回溯參照：

* **RewriteRule** Backreferences這些匹配對應RewriteRule模式中的回參考，格式為$N(0)  &lt;>例如, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2`。

* **RewriteCond回** 溯參考這些符合上次相符RewriteCondCondPattern中的回溯參考，格式為%N(0)&lt;>

變數：這些變數的格式為%{NAME_OF_VARIABLE}，其中NAME_OF_VARIABLE可以是已定義變數名稱的字串。 如需設定變數的詳細資訊，請參閱RewriteRule *`[E]`*&#x200B;標幟。

函式：這些函式的格式為${NAME_OF_FUNCTION:key}，其中NAME_OF_FUNCTION如下：

* tolower使&#x200B;*key*&#x200B;中的所有字元都小寫。
* toupper使&#x200B;*key*&#x200B;中的所有字元都大寫。
* escape URL會對索引鍵中的所有字元進行編碼。 字元a...z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;保留9&#39;、&#39;*&#39;、&#39;-&#39;、&#39;.&#39;、&#39;/&#39;、&#39;@&#39;和&#39;_&#39;不變，將空格轉換為&#39;+&#39;，並將所有其他字元轉換為其`%xx` URL編碼等同字元。
* 取消逸出會將&#39;+&#39;轉換回空格，所有`%xx` URL編碼字元都轉換回單一字元。

**CondPatternis** 標準的擴展規則表達式（含一些添加）。模式字串可以加上前置詞`!`字元（驚嘆號），以指定非相符模式。 您可使用下列其中一個特殊變數，而非實際規則運算式字串：

>[!NOTE]
>
>您也可以在所有測試前加上驚嘆號(&#39;!&#39;) 否定其意義。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern字串 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>從詞法上講，就更少了。 </p> <p> 將CondPattern視為純字串，並從語義上與TestString比較。 如果TestString的詞法小於CondPattern，則為true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>詞法上更大。 </p> <p> 將CondPattern視為純字串，並從語義上與TestString比較。 如果TestString的詞法大於CondPattern，則為true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>詞法上等於。 </p> <p> 將CondPattern視為純字串，並從語義上與TestString比較。 如果TestString在詞法上等於CondPattern，即兩個字串完全相同（字元逐字元），則為true。 如果CondPattern僅為""（兩個引號），則會比較TestString和空字串。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**標幟**
（選用）以方括弧括住標幟 `[]`。多個標幟以逗號分隔。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>旗標 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> 沒案子。 </p> <p>此標幟可讓測試不區分大小寫，即在擴充的TestString和CondPattern中，'A-Z'和'a-z'之間沒有差異。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p>或者下一個條件。 </p> <p>使用此標幟，將規則條件與本機OR（而非隱式AND）結合。 若沒有此標幟，您必須多次寫入第二個／規則。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**範例**

有些網頁會在訪客第一次造訪網站時指派「sessionid」 CGI變數。 此變數可用來識別訪客，而當訪客瀏覽網站時，會隨附該變數。 由於搜尋自動機看起來像是您網站的訪客，因此會指派一個「sessionid」編號。 搜尋自動機會保留此單一「sessionid」值，即使第二個網站頁面嘗試指派新值亦然。 為了確保這一點，您需要兩個重寫規則。

第一個規則用於識別和儲存sessionid變數：

```
RewriteCond  %{sessionid}  !.+ 
RewriteRule  ^.+sessionid= 
<b>([^&#]+)</b>.*$  -   
<i>[E=sessionid:$1]</i>
```

RewriteRule使用E標籤`([E=sessionid:$1])`將sessionid CGI參數的當前值分配給變數`sessionid`。 `$1`引用第一個回參考，它包含在RewriteRule模式`([^&#]+)`中的第一組括弧之間。

規則運算式`^&#]+`與字詞`sessionid`和下一個`**&**or**#**`字元之間的URL部分相符。 由於此RewriteRule僅用於為sessionid變數建立初始值，因此不會重寫。 請注意，規則的「替代」欄位設定為`-`，以指示不需要重寫。

RewriteCond會檢查變數`sessionid`(`%{sessionid}`)。 如果連一個字元(!..+)，則RewriteRule會符合。

使用此規則，URL會讀取為`https://www.domain.com/home/?sessionid=1234&function=start`，並將值`1234`指派給變數`sessionid`。

第二個規則用於重寫所有與下列RewriteRule模式匹配的URL:

```
RewriteRule   
<b>^(.+)</b>sessionid=[^&#]+ 
<i>(.*)$</i>  $1sessionid=%{sessionid}$2
```

RewriteRule模式包含兩個反向參照：`(.+)`和`(.*)`。 第一個回參考與`sessionid`之前的所有字元相符。 第二個反向參考與終止`&`或`#`後的所有字元匹配。

替代模式使用第一個回參考，接著字串&quot;sessionid=&quot;，接著第一個規則`%{sessionid}`所定義的作業階段ID變數值，接著第二個回參考，來重寫URL。`($1sessionid=%{sessionid} $2)`

請注意，此RewriteRule不包含RewriteCond。 因此，它會對所有符合RewriteRule *Pattern*&#x200B;的URL進行重寫。 因此，如果sessionid變數(`%{sessionid}`)的值為`1234`，則表單`https://www.domain.com/products/?sessionid=5678&function=buy`的URL被重寫為`https://www.domain.com/products/?sessionid=1234&function=buy`

## 確認{#section_B17088EF38244496BC1DDD4ECF75EB5B}

重寫引擎軟體最初由Apache Group開發，用於Apache HTTP伺服器項目(https://www.apache.org/)。

## 新增編目清單儲存URL規則{#task_22DD40DF95584B12BE8E6ECFBF579BCD}

您可以新增編目清單儲存URL規則，以指定如何重寫網頁內容中遇到的URL。 您可以指定不限數量的規則和條件，並可以控制所遇到URL的任何部分。

<!-- 

t_adding_a_crawl_list_store_url_rule.xml

 -->

**若要新增編目清單儲存URL規則**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Store URL Rules]**」。
1. 在[!DNL Crawl List Store URL Rules]欄位中，輸入您想要的規則。

   允許以「#」（雜湊）字元開頭的空白行和註解行。
1. （可選）在[!DNL Crawl List Store URL Rules]頁面的[!DNL Test Crawl List Store URL Rules]欄位中，輸入您要測試其編目規則的測試URL，然後按一下&#x200B;**Test**。
1. 按一下&#x200B;**「儲存變更」**。
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參閱[設定分段網站的遞增索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可選）在[!DNL Crawl List Store URL Rules]頁面上，執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 關於編目清單擷取URL規則{#concept_EC8E2E48B99A458D8567B526C9827CBA}

「編目URL規則」指定如何重寫網頁內容中遇到的URL。 您可以指定不限數量的規則和條件，並可以控制所遇到URL的任何部分。

<!-- 

c_about_crawl_list_retrieve_url_rules.xml

 -->

在客戶看到規則的效果之前，請務必重建網站索引。

編目規則對於重寫URL的動態部分最有用，例如作業識別碼，此識別碼對每位造訪您網站的客戶都是唯一的。 您也可以使用重寫規則，從搜尋自動機隱藏URL的部分，例如查詢參數。 依預設，不會指定任何規則，也不會執行URL重寫。

當網站編目時，內嵌內容URL會儲存在要編目之其他網頁的臨時清單中。 當搜索自動機從清單中檢索URL時，檢索重寫規則用於操作該URL的部分。 通常，擷取規則會用來將時間敏感資料插入URL。 這個最終URL可用來從您的網站擷取頁面。

只有當URL包含動態資料（如作業ID），且該動態資料隨時間變更而維持有效時，才需要擷取重寫規則。 在這種情況下，您會使用「商店重寫規則」，從所遇到的URL取得資料的最新狀態。 然後，當搜索自動機檢索頁面時，可以使用「檢索重寫規則」將該資料添加到每個URL。

每個規則都以重寫規則(RewriteRule)指令和一個或多個可選重寫條件(RewriteCond)指定。 規則的順序很重要。 規則集會依規則循環。 當規則符合時，它會循環執行任何對應的重寫條件。 以下列方式指定編目URL規則：

```
RewriteCond TestString CondPattern [Flags] 
RewriteRule Pattern Substitution [Flags]
```

遇到內嵌的URL時，搜尋自動機會嘗試將URL與每個編目規則的模式相符。 如果模式匹配，重寫引擎將查找相應的RewriteCond指令。 如果沒有條件，則URL會以由「替代」字串構成的新值取代，並繼續規則集中的下一個規則。 如果條件存在，則會依其列出順序加以處理。 重寫引擎嘗試將條件模式(CondPattern)與測試字串(TestString)相匹配。 如果兩者符合，則會處理下一個條件，直到沒有其他條件可用為止。 如果所有條件都符合，則URL會以規則中指定的替代項目取代。 如果條件未滿足，則完整條件集和相應規則將失敗。

## 關於RewriteRule指令{#section_32B24B29627946398AFBC5F869A610CB}

RewriteRule指令具有以下格式：

```
           
<i>RewriteRule Pattern Substitution [Flags]</i> 
        
```

`Pattern` 可以是POSIX規則運算式，會套用至目前的URL。「目前的URL」可能與原始要求的URL不同，因為舊版規則可能已比對並變更URL。

請參閱[規則運算式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

您不能使用&quot;not&quot;字元(&#39;!&#39;) 來為模式加上首碼。 「not」字元可讓您否定模式，即只有在目前的URL不符合此模式時，才會為true。 當比對負面模式或作為最終預設規則時，可使用&quot;not&quot;字元。

>[!NOTE]
>
>不能在模式中同時使用&quot;not&quot;字元和分組的萬用字元。 此外，當替代字串包含$N時，您無法使用否定的模式。

可以使用括弧在陣列中建立反參照，該反參照可由「替代」(Substitution)和「CondPattern」(CondPattern)參照。

**替** 代URL由包含以下內容的替代字串替換：

純文字檔案：傳遞的文字未變更。

背向參照提供對「陣列」或「條件陣列」的分組部分（內括弧）的訪問。 以下是兩種類型的回溯參照：

* **RewriteRule** Backreferences這些匹配對應RewriteRule模式中的回參考，格式為$N(0)  &lt;>例如, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2.`

* ** RewriteCond Backreferences**這些匹配的RewriteCondCattern中的反向引用採用%N格式(0 &lt;= N &lt;= 9)。

變數：這些變數的格式為%{NAME_OF_VARIABLE}，其中NAME_OF_VARIABLE是已定義變數名稱的字串。 有關設定環境變數的詳細資訊，請參閱&#x200B;*[E]*&#x200B;標籤。

函式：這些函式的格式為${NAME_OF_FUNCTION:key}，其中NAME_OF_FUNCTION如下：

* tolower使&#x200B;*key*&#x200B;中的所有字元都小寫。
* toupper使&#x200B;*key*&#x200B;中的所有字元都大寫。
* escape URL —— 對&#x200B;*key*&#x200B;中的所有字元進行編碼。
* 字元a...z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9&#39;、&#39;*&#39;、&#39;-&#39;、&#39;.&#39;、&#39;/&#39;、&#39;@&#39;和&#39;_&#39;未變；空格會轉譯為&#39;+&#39;，而所有其他字元則會轉換為其%xx URL編碼等同字元。
* 取消轉義會將&#39;+&#39;轉換回空格，所有%xx URL編碼字元都轉換回單一字元。

>[!NOTE]
>
>有一個特殊的替代字串：&#39;-&#39;表示「無替代」。 &#39;-&#39;字串常會與C(chain)標幟搭配使用，讓您在發生替代之前，將URL與數種模式相符。

**旗標**

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>旗標 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>最後一個規則。 </p> <p>停止重寫進程，不應用任何附加重寫規則。 使用此標幟可防止對目前URL進行任何進一步處理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>下一輪。 </p> <p> 使用上次重寫規則（而非原始URL）的URL，重新執行重寫程式（從第一個重寫規則開始）。 小心別製造死循環。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>與下一個規則連結。 </p> <p>將目前規則連結至下一個規則（也可以將其連結至下一個規則，依此類推）。 如果規則匹配，則替代進程照常繼續。 如果規則不符合，則會跳過所有後續的連結規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>沒案子。 </p> <p> 當模式與目前的URL相符時，讓模式不區分大小寫（即，'A-Z'和'a-z'之間沒有差異）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>略過下一個規則。 </p> <p> 如果目前的規則相符，此標幟會強制重寫引擎略過規則集中的下一個num規則。 使用此標幟來建立偽if-then-else結構。 then-clause的最後一個規則變為skip=N，其中N是else-clause中的規則數。 </p> <p> <p>注意： 此標幟與'chain|C'標幟不同！) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>設定環境變數。 </p> <p>建立設定為值VAL的環境變數"VAR"，其中VAL可包含展開的規則運算式反向參照$N和%N。 您可多次使用此標幟來設定多個變數。 變數稍後可透過%{VAR}在下列RewriteCond模式中取消參考。 </p> <p>使用此標幟可移除並記住URL中的資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>儲存重寫規則和檢索重寫規則共用變數值。 由於這種行為，您可在遇到並儲存內嵌URL時，將變數設為時間敏感的sessionid值。 從臨時儲存清單中檢索下一個URL時，可以在檢索該頁之前向其添加最新的sessionid值。

**具有函式的RewriteRule示例**

假設您有區分大小寫的伺服器，會以不同方式處理字串&quot;www.mydomain.com&quot;和&quot;www.MyDomain.com&quot;。 為了讓您的伺服器正常運作，請確定網域一律為「www.mydomain.com」，即使某些檔案包含參照「www.MyDomain.com」的連結亦然。 若要這麼做，您可使用下列規則：

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2
```

此重寫規則使用函式`tolower`重寫URL的網域部分，以確保其始終為小寫，如下所述：

1. 模式`(^https://([^/]*)(.*)$)`包含一個反向參考** `([^/]*)`**，它與URL中`https://`和第一個`/`之間的所有字元相符。 此模式也包含第二個反向參考`(.*)`，與URL中所有剩餘字元相符。
1. 替代`(https://${tolower:$1}$2)`會告訴搜尋引擎使用第一個反向參考`(https:// ${tolower:$1}$2)`上的`tolower`函式重寫URL，而URL的其餘部分則未變更`(https://${tolower:$1} $2)`。

因此，表單`https://www.MyDomain.com/INTRO/index.Html`的URL被重寫為`https://www.mydomain.com/INTRO/index.Html`。

## 關於RewriteCond指令{#section_ADD642A24B68452CB98294A0BD687EC3}

RewriteCond指令定義規則條件。 當RewriteCond在RewriteRule之前時，只有在規則的模式與當前標題匹配且附加條件適用時，才使用規則。 重寫條件採用下列形式：

```
           
<i>RewriteCond TestString CondPattern [Flags]</i> 
        
```

`TestString` 是一個字串，可以包含以下結構：

純文字檔案：傳遞的文字未變更。

背向參照提供對「陣列」或「條件陣列」的分組部分（內括弧）的訪問。 以下是兩種類型的回溯參照：

* **RewriteRule** Backreferences這些匹配對應RewriteRule模式中的回參考，格式為$N(0)  &lt;>例如, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2`。

* **RewriteCond回** 溯參考這些符合上次相符RewriteCondCondPattern中的回溯參考，格式為%N(0)&lt;>

變數：這些變數的格式為%{NAME_OF_VARIABLE}，其中NAME_OF_VARIABLE可以是已定義變數名稱的字串。 如需設定變數的詳細資訊，請參閱RewriteRule *`[E]`*&#x200B;標幟。

函式：這些函式的格式為${NAME_OF_FUNCTION:key}，其中NAME_OF_FUNCTION如下：

* tolower使&#x200B;*key*&#x200B;中的所有字元都小寫。
* toupper使&#x200B;*key*&#x200B;中的所有字元都大寫。
* escape URL會對索引鍵中的所有字元進行編碼。 字元a...z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9&#39;、&#39;*&#39;、&#39;-&#39;、&#39;.&#39;、&#39;/&#39;、&#39;@&#39;和&#39;_&#39;未變更，空格會轉換為&#39;+&#39;，而所有其他字元則會轉換為其%x URL編碼等同字元。
* 取消轉義會將&#39;+&#39;轉換回空格，所有%xx URL編碼字元都轉換回單一字元。

**CondPatternis** 標準的擴展規則表達式（含一些添加）。模式字串可以前置詞&#39;!&#39; 字元（驚嘆號），以指定不符合的模式。 您可使用下列其中一個特殊變數，而非實際規則運算式字串：

>[!NOTE]
>
>您也可以在所有測試前加上驚嘆號(&#39;!&#39;) 否定其意義。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern字串 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>從詞法上講，就更少了。 </p> <p> 將CondPattern視為純字串，並從語義上與TestString比較。 如果TestString的詞法小於CondPattern，則為true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>詞法上更大。 </p> <p> 將CondPattern視為純字串，並從語義上與TestString比較。 如果TestString的詞法大於CondPattern，則為true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>詞法上等於。 </p> <p> 將CondPattern視為純字串，並從語義上與TestString比較。 如果TestString在詞法上等於CondPattern，即兩個字串完全相同（字元逐字元），則為true。 如果CondPattern僅為""（兩個引號），則會比較TestString和空字串。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**標幟**
（選用）以方括弧括住標幟 `[]`。多個標幟以逗號分隔。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>旗標 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> 沒案子。 </p> <p>此標幟可讓測試不區分大小寫，即在擴充的TestString和CondPattern中，'A-Z'和'a-z'之間沒有差異。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p>或者下一個條件。 </p> <p>使用此標幟，將規則條件與本機OR（而非隱式AND）結合。 若沒有此標幟，您必須多次寫入第二個／規則。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**範例**

有些網頁會在訪客第一次造訪網站時指派「sessionid」 CGI變數。 此變數可用來識別訪客，而當訪客瀏覽網站時，會隨附該變數。 由於搜尋自動機看起來像是您網站的訪客，因此會指派一個「sessionid」編號。 搜尋自動機會保留此單一「sessionid」值，即使第二個網站頁面嘗試指派新值亦然。 為了確保這一點，您需要兩個重寫規則。

第一個規則用於識別和儲存sessionid變數：

```
RewriteCond  %{sessionid}  !.+ 
RewriteRule  ^.+sessionid= 
<b>([^&#]+)</b>.*$  -   
<i>[E=sessionid:$1]</i>
```

RewriteRule使用E標籤`([E=sessionid:$1])`將sessionid CGI參數的當前值分配給變數`sessionid`。 `$1`引用第一個回參考，它包含在RewriteRule模式`([^&#]+)`中的第一組括弧之間。

規則運算式`^&#]+`與字詞`sessionid`和下一個**&amp;**或**#*字元之間的URL部分相符。 由於此RewriteRule僅用於為sessionid變數建立初始值，因此不會重寫。 請注意，規則的「替代」欄位設定為`-`，以指示不需要重寫。

RewriteCond會檢查變數`sessionid`(`%{sessionid}`)。 如果連一個字元(!..+)，則RewriteRule會符合。

使用此規則，URL會讀取為`https://www.domain.com/home/?sessionid=1234&function=start`，並將值`1234`指派給變數`sessionid`。

第二個規則用於重寫所有與下列RewriteRule模式匹配的URL:

```
RewriteRule   
<b>^(.+)</b>sessionid=[^&#]+ 
<i>(.*)$</i>  $1sessionid=%{sessionid}$2
```

RewriteRule模式包含兩個反向參照：`(.+)`和`(.*)`。 第一個回參考與`sessionid`之前的所有字元相符。 第二個反向參考與終止`&`或`#`後的所有字元匹配。

替代模式使用第一個回參考，接著字串&quot;sessionid=&quot;，接著第一個規則`%{sessionid}`所定義的作業階段ID變數值，接著第二個回參考，來重寫URL。`($1sessionid=%{sessionid} $2)`

請注意，此RewriteRule不包含RewriteCond。 因此，它會對所有符合RewriteRule *Pattern*&#x200B;的URL進行重寫。 因此，如果sessionid變數(`%{sessionid}`)的值為`1234`，則表單`https://www.domain.com/products/?sessionid=5678&function=buy`的URL被重寫為`https://www.domain.com/products/?sessionid=1234&function=buy`

## 確認{#section_EC3A1DAEB5A54C93A265CB119DF91E9F}

重寫引擎軟體最初由Apache Group開發，用於Apache HTTP伺服器項目(https://www.apache.org/)。

## 添加搜索清單檢索URL規則{#task_94A28ED7DC404BFF9767DBB5ADEE6B7A}

您可以新增編目清單擷取URL規則，以指定在Web內容中遇到的URL如何重寫。 只有當URL包含動態資料（例如作業階段ID），且動態資料隨時間變更而維持有效時，才需要擷取重寫規則。

<!-- 

t_adding_crawl_list_retrieve_url_rules.xml

 -->

**若要新增編目清單擷取URL規則**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Retrieve URL Rules]**」。
1. 在[!DNL Crawl List Retrieve URL Rules]欄位中，輸入您想要的規則。

   允許以「#」（雜湊）字元開頭的空白行和註解行。
1. （可選）在[!DNL Crawl List Retrieve URL Rules]頁面的[!DNL Test Crawl List Retrieve URL Rules]欄位中，輸入您要測試其編目規則的測試URL，然後按一下&#x200B;**Test**。
1. 按一下&#x200B;**「儲存變更」**。
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參閱[設定分段網站的遞增索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可選）在[!DNL Crawl List Retrieve URL Rules]頁面上，執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 關於編目標題規則{#concept_BD3A576987DA4D93A998B0B9CDDC3C79}

「編目標題規則」指定在Web內容中遇到的標題儲存在搜尋索引中之前，如何加以重寫。

<!-- 

c_about_crawl_title_rules.xml

 -->

例如，您可以使用重寫規則來移除標題的一部分，例如組織名稱。 當網站編目時，遇到的標題會儲存在暫存緩衝區中。 不過，在將標題新增至此緩衝區之前，會先套用標題規則。 依預設，網站搜尋／銷售沒有編目標題規則，也未進行標題修改。

在客戶看得到規則的效果之前，請重建您的網站索引。

您可以使用「步驟記錄」功能，快速回復對「編目標題規則」所做的任何變更。

規則可包含兩個主要元素：rewriteRule和可選的RewriteCond。 您可以指定不限數目的規則和條件。 這些規則的順序很重要，因為規則集會依規則循環。 當規則符合時，它會循環執行任何（可選）對應的重寫條件。 以下列方式指定「編目URL」規則：

```
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i> 
 
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

遇到標題時，搜索自動機會嘗試將標題與每個編目規則的「模式」(Pattern)匹配。 如果模式匹配，重寫引擎將查找相應的RewriteCond指令。 如果沒有條件，則URL會以由「替代」字串構成的新值取代，並繼續規則集中的下一個規則。 如果條件存在，則會依其列出順序加以處理。 重寫引擎嘗試將條件模式(CondPattern)與測試字串(TestString)相匹配。 如果兩者符合，則會處理下一個條件，直到沒有其他條件可用為止。 如果所有條件都符合，則URL會以規則中指定的替代項目取代。 如果條件未滿足，則完整條件集和相應規則將失敗。

在文字方塊中輸入「編目URL規則」，然後按一下「儲存變更」。 允許以「#」（雜湊）字元開頭的空白行和註解行。 若要測試搜尋規則，您可以在「測試重寫規則」文字方塊中輸入測試URL，然後按一下「測試」。

## RewriteRule指令{#section_669445C505754E838E14029D6583D9B6}

每個RewriteRule指令都定義一個重寫規則。 規則依其列出順序套用。 重寫規則採用下列形式：

```
RewriteRule Pattern Substitution [Flags]
```

**** Patterncan是POSIX規則運算式，會套用至目前標題。「目前的標題」與原始標題不同，因為舊版規則已經相符和變更。

請參閱[規則運算式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

您可以使用&quot;not&quot;字元(&#39;!&#39;) 來為模式加上首碼。 「not」字元可讓您否定模式，即只有在目前標題不符合模式時，才使其為true。 當比對負面模式或作為最終預設規則時，可使用&quot;not&quot;字元。 注意：不能在模式中同時使用&quot;not&quot;字元和分組的萬用字元。 此外，當替代字串包含$N時，您無法使用否定的模式。

可以使用括弧建立可由「替代」(Substitution)和「CondPattern」(CondPattern)引用的反向參照。

**替** 代標題由替代字串替換。字串可包含下列項目：

純文字檔案——通過未更改的文本。

背向參照提供對「陣列」或「條件陣列」的分組部分（內括弧）的訪問。 以下是兩種類型的回溯參照：

* RewriteRule回參考

   這些匹配返回對應RewriteRule模式中的引用，格式為$N(0 &lt;= N &lt;= 9)。 例如, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`
* RewriteCond回參考

   這些匹配返回上次匹配的RewriteCondCondPattern中的引用，格式為%N(0 &lt;= N &lt;= 9)。

變數這些為%{NAME_OF_VARIABLE}格式的變數，其中NAME_OF_VARIABLE可以是定義變數名稱的字串。 有關設定環境變數的詳細資訊，請參閱`[E]`標籤。

函式以下是${NAME_OF_FUNCTION格式的函式：key}，其中NAME_OF_FUNCTION為：

* tolower使&#x200B;*key*&#x200B;中的所有字元都小寫。
* toupper使&#x200B;*key*&#x200B;中的所有字元都大寫。

>[!NOTE]
>
>有一個特殊的替代字串：&#39;-&#39;表示「無替代」。 &#39;-&#39;字串通常適用於C（鏈）標幟，可讓您在發生替代之前，將標題與數種模式相符。

**標幟** （選用）

標幟括在方括弧`[]`中，而多個標幟以逗號分隔：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>旗標 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>最後一個規則。 </p> <p> 停止重寫進程，不應用任何附加重寫規則。 使用此標幟可防止進一步處理目前標題。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>下一輪。 </p> <p> 使用來自上一個重寫規則的標題（而非原始標題）重新運行重寫進程（從第一個重寫規則再次開始）。 小心別造成死循環。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>與下一個規則連結。 </p> <p>將目前規則連結至下一個規則（也可以將其連結至下一個規則，依此類推）。 如果規則匹配，則替代進程照常繼續。 如果規則不符合，則會跳過所有後續的連結規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>沒案子。 </p> <p>當模式與目前標題相符時，使模式不區分大小寫（亦即，'A-Z'和'a-z'之間沒有差異）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>略過下一個規則或規則。 </p> <p> 如果目前的規則相符，此標幟會強制重寫引擎略過規則集中的下一個num規則。 使用它來建立偽if-then-else結構。 then-clause的最後一個規則變為skip=N，其中N是else-clause中的規則數。 (注意：這與'chain|C'標幟不同！) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>設定環境變數。 </p> <p> 建立設定為值VAL的環境變數"VAR"，其中VAL可包含規則運算式回參考、$N和%N，並加以擴充。 您可多次使用此標幟來設定多個變數。 變數稍後可透過%{VAR}在下列RewriteCond模式中參考。 使用此標幟可移除並記住標題中的資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## RewriteCond指令（可選）{#section_D664B71DE3884E0790531804C49A3222}

RewriteCond指令定義規則條件。 當RewriteCond在RewriteRule之前時，只有在規則的模式與當前標題匹配且附加條件適用時，才使用規則。

重寫條件指令採用以下形式：

```
RewriteCond TestString CondPattern [Flags] 
```

**** TestString是可包含下列結構的字串：

純文字檔案——通過未更改的文本。

背向參照提供對「陣列」或「條件陣列」的分組部分（內括弧）的訪問。 有兩種類型的反向參照：

* RewriteRule Backreferences這些匹配RewriteRule模式中的反向引用，格式為$N(0 &lt;= N &lt;= 9)。 例如, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`
* RewriteCond回溯參考這些符合的回溯參考位於上個相符的RewriteCondCondPattern中，格式為%N(0 &lt;= N &lt;= 9)。

變數這些為%{NAME_OF_VARIABLE}格式的變數，其中NAME_OF_VARIABLE可以是定義變數名稱的字串。 有關設定環境變數的詳細資訊，請參閱`[E]`標籤。

函式這些函式的格式為${NAME_OF_FUNCTION:key}，其中NAME_OF_FUNCTION為：

* tolower使&#x200B;*key*&#x200B;中的所有字元都小寫。
* toupper使&#x200B;*key*&#x200B;中的所有字元都大寫。
* escape URL會對索引鍵中的所有字元進行編碼。
* 字元a...z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9&#39;、&#39;*&#39;、&#39;-&#39;、&#39;.&#39;、&#39;/&#39;、&#39;@&#39;和&#39;_&#39;未變更，空格會轉換為&#39;+&#39;，而所有其他字元則會轉換為其%x URL編碼等同字元。
* 取消轉義會將&#39;+&#39;轉換回空格，所有%xx URL編碼字元都轉換回單一字元。

**CondPatternis** 標準的擴展規則表達式（含一些添加）。模式字串可以前置詞&#39;!&#39; 字元（驚嘆號），以指定不符合的模式。 您可使用下列其中一個特殊變數，而非實際的規則運算式字串。

>[!NOTE]
>
>您可以在所有測試前加上驚嘆號(&#39;!&#39;) 否定其意義。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern字串 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>從詞法上來說，它就更少了。 </p> <p>將<i>CondPattern</i>視為純字串，並從語義上與<i>TestString</i>進行比較。 如果<i>TestString</i>詞法上小於<i>CondPattern</i>，則為true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>詞法上更大。 </p> <p>將<i>CondPattern</i>視為純字串，並從語義上與<i>TestString</i>進行比較。 如果<i>TestString</i>詞法上大於<i>CondPattern</i>，則為true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p> 從詞法上講是相等的。 </p> <p>將<i>CondPattern</i>視為純字串，並從語義上與<i>TestString</i>進行比較。 如果<i>TestString</i>在語法上等於<i>CondPattern</i>，即，這兩個字串完全相同（逐字元），則為true。 如果<i>CondPattern</i>僅為""（兩個引號），則會比較<i>TestString</i>與空字串。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**標幟** （選用）

標幟括在方括弧`[]`中，而多個標幟以逗號分隔：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>旗標 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>沒案子。 </p> <p> 使測試不敏感。 即，在展開的<i>TestString</i>和<i>CondPattern中，'A-Z'和'a-z'之間沒有差異。</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p> 或者下一個條件。 </p> <p>使用此標幟，將規則條件與本機OR（而非隱式AND）結合。 若沒有此標幟，您必須多次寫入第二個／規則。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**範例**

假設您有一個標準標題格式的公司網站：「My Company」後面接著連字型大小，接著是頁面特定的說明（例如「My Company - Welcome」或「My Company - News」）。 您想要從標題中去除「My Company - 」，並在索引網站時將整個標題轉換為大寫字母。

以下重寫規則使用函式頭將標題的描述性部分僅重寫為大寫：

```
RewriteRule  ^My[[:blank:]]Company[[:blank:]]-[[:blank:]] 
<b>(.*)</b>$  ${toupper: 
<b>$1</b>}
```

規則的模式`(^My[[:blank:]]Company[[:blank:]]-[[:blank:]] (.*))`包含與&quot;My Company-&quot;後面的標題內容相符的回參考`(.*)`。 請記住，帶有括弧()的陣列的部分周圍會建立可由替代引用的反向引用。 在此範例中，替代(${toupper:**$1**})使用toupper函式重寫該回參考(**$1**)。

因此，&quot;My Company - Welcome&quot;表單的標題被改寫為&quot;WELCOME&quot;。

**確認**

重寫引擎軟體最初由Apache Group開發，用於Apache HTTP伺服器項目(https://www.apache.org/)。

## 新增編目標題規則{#task_272BB4C603BA4C9ABDBEEB398798B101}

您可以新增編目標題規則，以指定在Web內容中遇到的標題儲存在搜尋索引中之前，如何重寫這些標題。

<!-- 

t_adding_crawl_title_rules.xml

 -->

**若要新增編目標題規則**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl Title Rules]**」。
1. 在[!DNL Crawl Title Rules]欄位中，輸入您想要的規則。

   允許以「#」（雜湊）字元開頭的空白行和註解行。
1. （可選）在[!DNL Crawl Title Rules]頁面的[!DNL Test Crawl Title Rules]欄位中，輸入您要測試其搜尋規則的測試URL，然後按一下&#x200B;**Test**。
1. 按一下&#x200B;**「儲存變更」**。
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參閱[設定分段網站的遞增索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可選）在[!DNL Crawl Title Rules]頁面上，執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 關於搜尋URL規則{#concept_017EC95E68844B6C8CC9F874F0EC8D3C}

「搜尋URL規則」指定網站搜尋結果中的URL應該如何顯示。 規則會在完整URL上運作。 URL的任何部分都可加以操控，包括通常保留作業ID資訊的查詢引數。

<!-- 

c_about_search_url_rules.xml

 -->

通常，搜尋URL規則會用來將工作階段ID插入URL。 不過，您也可以使用搜尋URL規則來變更結果所顯示的網域名稱。 依預設，不會指定任何規則，也不會執行URL修改。

搜尋URL規則可包含兩個主要元素：rewriteRule和可選的RewriteCond。 當URL包含在搜尋結果中時，會使用規則來控制它。 您可以指定不限數目的搜尋URL規則和條件。 這些規則的順序很重要，因為規則集是循環規則。 當規則符合時，軟體會循環執行任何（可選）對應的重寫條件。 以下列方式指定「編目URL」規則：

```
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i> 
 
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

處理URL時，網站搜尋／銷售會嘗試將其與每個搜尋規則的「模式」相符。 如果比對失敗，重寫引擎會立即停止處理規則，並繼續處理規則集中的下一個規則。 如果模式匹配，重寫引擎將查找相應的RewriteCond指令。 如果沒有條件，URL會以新值取代。 此值由替代字串構成，並繼續與規則集中的下一個規則一起使用。 如果條件存在，則其列出順序是處理方式。 重寫引擎嘗試將條件模式(CondPattern)與測試字串(TestString)相匹配。 如果兩者符合，則會處理下一個條件，直到沒有其他條件可用為止。 如果所有條件都符合，URL會以規則中指定的替代項目取代。 如果條件未滿足，則完整條件集和相應規則將失敗。

## 關於RewriteRule指令{#section_A3473B5B90B74DA1970213113A90591E}

重寫規則採用下列形式：

```
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

**Patterncan** 是POSIX規則運算式，會套用至目前的URL。「目前的URL」可能與原始的URL不同，因為舊版規則可能已經相符並變更了它。

請參閱[規則運算式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

您可以使用&quot;not&quot;字元(&#39;!&#39;) 來為模式加上首碼。 「not」字元可讓您否定模式。 換言之，只有當目前的URL與模式不符時，才為true。 當比對負面模式或作為最終預設規則時，您可以使用&quot;not&quot;字元。 請注意，您不能在模式中同時使用&quot;not&quot;字元和分組的萬用字元。 此外，當替代字串包含$N時，您無法使用否定的模式。

可以使用括弧建立可由「替代」(Substitution)和「CondPattern」(CondPattern)引用的反向參照。

**替** 代URL由替代字串完全取代，可包含下列項目：

純文字檔案——通過未更改的文本。

背向參照提供對「陣列」(Pattern)或「條件陣列」(CondPattern)的分組部分（內括弧）的訪問。 有兩種類型的反向參照：

RewriteRule Backreferences這些匹配RewriteRule模式中的反向引用，格式為$N(0 &lt;= N &lt;= 9)。 例如, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

RewriteCond Backreferences —— 這些匹配的RewriteCondCondPattern中的回參考，格式為%N(0 &lt;= N &lt;= 9)。

函式：這些函式的格式為${NAME_OF_FUNCTION:key}，其中NAME_OF_FUNCTION為：

* tolower使&#x200B;*key*&#x200B;中的所有字元都小寫。
* toupper使&#x200B;*key*&#x200B;中的所有字元都大寫。
* escape URL —— 對&#x200B;*key*&#x200B;中的所有字元進行編碼。
* 字元a...z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9&#39;、&#39;*&#39;、&#39;-&#39;、&#39;.&#39;、&#39;/&#39;、&#39;@&#39;和&#39;_&#39;未變；空格會轉換為&#39;+&#39;;所有其他字元都會轉換為其%xx URL編碼等同字元。
* 取消轉義會將&#39;+&#39;轉換回空格，所有%xx URL編碼字元都轉換回單一字元。

>[!NOTE]
>
>有一個特殊的替代字串：&#39;-&#39;表示「無替代」。 &#39;-&#39;字串常與C（鏈）標幟搭配使用。 它可讓您在發生替代之前，將URL與數種模式相符。

**標幟** （選用）

標幟括在方括弧`[]`中，而多個標幟以逗號分隔：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>旗標 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>最後一個規則。 </p> <p> 停止重寫進程，不應用任何附加重寫規則。 使用此標幟可防止對目前URL進行任何進一步處理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p> 下一輪。 </p> <p>使用上次重寫規則（而非原始URL）的URL，重新執行重寫程式（從第一個重寫規則開始）。 小心不要造成死循環！ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p> 與下一個規則連結。 </p> <p>此標幟會將目前的規則系結至下一個規則，而下一個規則也可以連結至其下列規則，依此類推。 如果規則匹配，則替代進程照常繼續。 如果規則不符合，則會跳過所有後續的連結規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>沒案子。 </p> <p>此標幟會使「圖樣」不區分大小寫。 換言之，當模式與目前的URL相符時，'A-Z'和'a-z'之間沒有差異。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p>略過下一個規則或規則。 </p> <p> 如果目前的規則相符，此標幟會強制重寫引擎略過規則集中的下一個num規則。 使用它來建立偽if-then-else結構。 then-clause的最後一個規則變為skip=N，其中N是else-clause中的規則數。 (注意：這與'chain|C'標幟不同！) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>設定環境變數。 </p> <p> 此標幟會建立設為值VAL的環境變數「VAR」。 VAL可包含擴展的規則運算式反向引用$N和%N。 您可多次使用此標幟來設定多個變數。 變數稍後可透過%{VAR}在下列RewriteCond模式中取消參考。 使用此標幟可移除並記住URL中的資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>

請注意，「商店重寫規則」和「擷取重寫規則」會共用變數值。 因此，在遇到並儲存內嵌URL時，您可將變數設為時間敏感的sessionid值。 從臨時儲存清單中檢索下一個URL時，可以在檢索該頁之前向其添加最新的sessionid值。

**範例**

假設您有區分大小寫的伺服器。 它會以不同的方式處理字串&quot;www.mydomain.com&quot;和&quot;www.MyDomain.com&quot;。 為了讓伺服器正常運作，您必須確定網域一律為「www.mydomain.com」，即使某些檔案包含參照「www.MyDomain.com」的連結。 若要這麼做，您可使用下列規則：

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2 
```

此重寫規則使用函式「tolower」重寫URL的網域部分，以確保其始終為小寫：

1. 模式`(^https://([^/]*)(.*)$)`包含一個反向參考&#x200B;**`([^/]*)`**，它匹配URL中&quot;https://&quot;和第一個&quot;/&quot;之間的所有字元。 該模式還包含第二個回參考&#x200B;**(。*)**，該字元與URL中所有剩餘字元相符。

1. 替代`(https://${tolower:$1}$2)`會告訴搜尋引擎使用第一個反向參考`(https://**${tolower:$1**}$2)`上的&#x200B;**tolower**&#x200B;函式重寫URL，而URL的其餘部分則未變更`(https://${tolower:$1}*$2*)`。

因此，`https://www.MyDomain.com/INTRO/index.Html`格式的URL被重寫為`https://www.mydomain.com/INTRO/index.Html`

**RewriteCond指令** （可選）

RewriteCond指令定義規則條件。 當RewriteCond在RewriteRule之前時，只有在規則的模式與當前標題匹配且附加條件適用時，才使用規則。

重寫條件指令採用以下形式：

```
RewriteCond  
<i>TestString CondPattern [Flags]</i>
```

** TestString是可包含下列結構的字串：

純文字檔案：傳遞的文字未變更。

背向參照提供對「陣列」或「條件陣列」的分組部分（內括弧）的訪問。 有兩種類型的反向參照：

* ** RewriteRule Backreferences**這些與對應的RewriteRule模式中的反向參照相匹配，格式為$N(0 &lt;= N &lt;= 9)。 例如, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* **RewriteCond回** 溯參考這些符合上次相符RewriteCondCondPattern中的回溯參考，格式為%N(0)  &lt;>

變數這些為%{NAME_OF_VARIABLE}格式的變數，其中NAME_OF_VARIABLE可以是定義變數名稱的字串。 如需設定變數的詳細資訊，請參閱RewriteRule *`[E]`*&#x200B;標幟。

>[!NOTE]
>
>重寫規則通常使用變數。 來自目前URL的所有CGI參數都會自動設為變數。 例如，搜尋URL `"https://search.atomz.com/search/?sp_a=sp00000000&sp_q="Product"&session=1234&id=5678"`會自動提供四個變數，可在重寫規則中參考。 在此範例中，一個變數稱為「session」，其值為「1234」，而另一個變數稱為「id」，其值為「5678」。 （其他兩個變數為`sp_a`和`sp_q`。） 您應從網頁的搜尋表單中，將所有必要的變數傳遞為隱藏欄位。 在此範例中，您應傳遞「session」和「id」值，以識別執行搜尋的網站使用者。 若要在搜尋表單上傳遞隱藏欄位，請使用`<input type=hidden name="session" value="1234">`之類的標籤。

函式這些函式的格式為${NAME_OF_FUNCTION:key}，其中NAME_OF_FUNCTION為：

* tolower使&#x200B;*key*&#x200B;中的所有字元都小寫。
* toupper使&#x200B;*key*&#x200B;中的所有字元都大寫。
* escape URL —— 對&#x200B;*key*&#x200B;中的所有字元進行編碼。 字元a...z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9&#39;、&#39;*&#39;、&#39;-&#39;、&#39;.&#39;、&#39;/&#39;、&#39;@&#39;和&#39;_&#39;未變更，空格會轉換為&#39;+&#39;，而所有其他字元則會轉換為其%x URL編碼等同字元。
* 取消轉義會將&#39;+&#39;轉換回空格，所有%xx URL編碼字元都轉換回單一字元。

**CondPatternis** 標準的擴展規則表達式（含一些添加）。模式字串可以前置詞&#39;!&#39; 字元（驚嘆號），以指定不符合的模式。 您可使用下列其中一個特殊變數，而非實際的規則運算式字串。

您可以使用驚嘆號(&#39;!&#39;)來為所有這些測試加上前置詞 否定其意義。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern字串 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>從詞法上來說，它就更少了。 </p> <p> 將<i>CondPattern</i>視為純字串，並從語義上與<i>TestString</i>進行比較。 如果<i>TestString</i>詞法上小於<i>CondPattern</i>，則為true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>詞法上更大。 </p> <p> 將<i>CondPattern</i>視為純字串，並從語義上與<i>TestString</i>進行比較。 如果<i>TestString</i>詞法上大於<i>CondPattern</i>，則為true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>從詞法上講是相等的。 </p> <p> 將<i>CondPattern</i>視為純字串，並從語義上與<i>TestString</i>進行比較。 如果<i>TestString</i>在詞法上等於<i>CondPattern</i>，則為true。 也就是說，兩個字串完全相同（字元逐字元）。 如果<i>CondPattern</i>僅為""（兩個引號），則會比較<i>TestString</i>與空字串。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**標幟** （選用）

標幟括在方括弧`[]`中，而多個標幟以逗號分隔：

&#39;nocase|NC&#39;（無大寫）:這會讓測試不區分大小寫。 換言之，在展開的&#x200B;*TestString*&#x200B;和&#x200B;*CondPattern*&#x200B;中，&#39;A-Z&#39;和&#39;a-z&#39;之間沒有差異。

&#39;ornext|OR&#39;（或下一個條件）:使用此項，將規則條件與局部OR（而非隱式AND）結合。 若沒有此標幟，您必須多次寫入第二個／規則。

**範例**

有些網頁會在客戶第一次到達網站時指派「sessionid」 CGI變數。 此變數用來識別客戶，當客戶瀏覽網站時，會隨附該變數。 由於搜尋機器人看起來就像您網站的客戶，因此會指派一個「sessionid」編號。 搜尋自動機會保留此單一「sessionid」值，即使第二個網站頁面嘗試指派新值亦然。 為確保此，您需要以下重寫規則：

```
RewriteCond  %{sessionid}  .+ 
RewriteRule  ^ 
<b>(.+)</b>sessionid=[^&#]+ 
<i>(.*)</i>$   
<b>$1</b>sessionid=%{sessionid} 
<i>$2</i>
```

RewriteRule模式包含兩個反向參照：。+) 和 (.*)。 第一個回參考與&quot;sessionid=&quot;之前的所有字元相符。 第二個反向參照與作業ID終止&#39;&amp;&#39;或&#39;#&#39;後的所有字元相符。

替代模式使用第一個回參考，接著字串&quot;sessionid=&quot;，接著是作業階段ID變數的值，在URL中以CGI參數傳遞，接著是第二個回參考，來重寫URL。`($1sessionid=%{sessionid}$2)`。

**RewriteCond**&#x200B;檢查變數sessionid `(%{sessionid})`。 如果它至少包含一個字元(.+)，則RewriteRule會符合。

因此，如果搜尋查詢為`"https://search.atomz.com/search/?sp_a=sp99999999&sp_q=word&sessionid=5678"`，則會重寫所有搜尋結果URL，使「sessionid」值為&quot;5678&quot;，而非搜尋自動機在搜尋您的網站並儲存連結時遇到的「sessionid」值。

**確認**

重寫引擎軟體最初由Apache Group開發，用於Apache HTTP伺服器項目(https://www.apache.org/)。

## 新增搜尋URL規則{#task_50C77D1B53804AEEB20896F74265BD6F}

您可以新增搜尋URL規則，以指定網站搜尋結果中的URL的顯示方式。 規則會在完整URL上運作。 您可以控制URL的任何部分，包括通常保存會話ID資訊的查詢參數。

<!-- 

t_adding_search_url_rules.xml

 -->

**若要新增搜尋URL規則**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Search URL Rules]**」。
1. 在[!DNL Search URL Rules]欄位中，輸入您想要的規則。

   允許以「#」（雜湊）字元開頭的空白行和註解行。
1. （可選）在[!DNL Search URL Rules]頁面的[!DNL Test Search URL Rules]欄位中，輸入您要測試其編目規則的測試URL，然後按一下&#x200B;**Test**。
1. 按一下&#x200B;**「儲存變更」**。
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參閱[設定分段網站的遞增索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可選）在[!DNL Search URL Rules]頁面上，執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 關於搜索標題規則{#concept_C72D20F8DFF64EDE809AF4B72797E858}

「搜尋標題規則」指定網站搜尋結果中標題的顯示方式。 標題的任何部分都可進行操控。

<!-- 

c_about_search_title_rules.xml

 -->

重寫規則可用於移除標題的一部分，例如組織名稱。 依預設，網站搜尋／銷售沒有標題規則，也未進行標題修改。

標題規則可包含兩個主要元素：rewriteRule和可選RewriteCond。 可以指定不限數量的規則和條件。 這些規則的順序很重要，因為規則集會依規則循環。 當規則符合時，軟體會循環執行任何（可選）對應的重寫條件。 「搜尋標題規則」的指定方式如下：

```
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i> 
 
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

遇到標題時，網站搜尋／銷售會嘗試將其與每個編目規則的「模式」相符。 如果模式匹配，重寫引擎將查找相應的RewriteCond指令。 如果沒有任何條件，則標題將替換為由替代字串構建的新值，並繼續規則集中的下一個規則。 如果條件存在，則會依其列出順序加以處理。 重寫引擎嘗試將條件模式(CondPattern)與測試字串(TestString)相匹配。 如果兩者符合，則會處理下一個條件，直到沒有其他條件可用為止。 如果所有條件都符合，URL會以規則中指定的替代項目取代。 如果條件未滿足，則完整條件集和相應規則將失敗。

## RewriteRule指令{#section_3BF2B0FF89F74A26AE79D68FA3184B9B}

每個RewriteRule指令都定義一個重寫規則。 規則依其列出順序套用。 重寫規則採用下列形式：

```
RewriteRule Pattern Substitution [Flags]
```

**PatternA** POSIX規則運算式，可套用至目前標題。「目前的標題」可能與原始標題不同，因為舊版規則可能已經符合併變更了它。

請參閱[規則運算式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

您可以使用&quot;not&quot;字元(&#39;!&#39;) 來為模式加上首碼。 「not」字元可讓您否定模式。 也就是說，只有在目前標題不符合模式時才為true。 當比對負面模式或作為最終預設規則時，可使用&quot;not&quot;字元。 注意：不能在模式中同時使用&quot;not&quot;字元和分組的萬用字元。 此外，當替代字串包含$N時，您無法使用否定的模式。

可以使用括弧建立可由「替代」(Substitution)和「CondPattern」(CondPattern)引用的反向參照。

**替** 代標題由可包含以下內容的替代字串完全替換：

純文字檔案——通過未更改的文本。

**背** 向參照提供對「陣列」(Pattern)或「條件陣列」(CondPattern)的分組部分（內括弧）的訪問。以下是兩種類型的回溯參照：

* **RewriteRule** Backreferences這些匹配對應RewriteRule模式中的回參考，格式為$N(0)  &lt;>例如, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* ** RewriteCond Backreferences**這些匹配的RewriteCondCattern中的反向引用採用%N格式(0 &lt;= N &lt;= 9)。

**變** 數這些為%{NAME_OF_VARIABLE}格式的變數，其中NAME_OF_VARIABLE可以是定義變數名稱的字串。有關設定環境變數的詳細資訊，請參閱[E]標籤。 變數也可在產生搜尋結果的搜尋表單中定義。

**函** 數以下是${NAME_OF_FUNCTION格式的函式：key}，其中NAME_OF_FUNCTION為：

* tolower使&#x200B;*key*&#x200B;中的所有字元都小寫。
* toupper使&#x200B;*key*&#x200B;中的所有字元都大寫。

有一個特殊的替代字串：&#39;-&#39;表示「無替代」。 &#39;-&#39;字串通常與C（鏈）標幟搭配使用，讓您在發生替代之前，將標題與數種模式相符。

**標幟** （選用）

標幟括在方括弧`[]`中，而多個標幟以逗號分隔：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>旗標 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p> 最後一個規則。 </p> <p> 停止重寫進程，不應用任何附加重寫規則。 使用此標幟可防止進一步處理目前標題。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>下一輪。 </p> <p> 使用來自上次重寫規則的標題（而非原始標題！）重新運行重寫進程（從第一個重寫規則再次開始）。 小心別造成死循環。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'chain|C' </p> </td> 
   <td colname="col2"> <p>與下一個規則連結。 </p> <p> 此標幟會將目前的規則連結至下一個規則（也可以將其連結至下列規則，依此類推）。 如果規則匹配，則替代進程照常繼續。 如果規則不符合，則會跳過所有後續的連結規則。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> 沒案子。 </p> <p> 此標幟會使「圖樣」不區分大小寫。 即，當模式與當前標題匹配時，「A-Z」和「a-z」之間沒有差異。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'skip|S=num' </p> </td> 
   <td colname="col2"> <p> 略過下一個規則或規則。 </p> <p> 如果目前的規則相符，此標幟會強制重寫引擎略過規則集中的下一個num規則。 使用它來建立偽if-then-else結構。 then-clause的最後一個規則變為skip=N，其中N是else-clause中的規則數。 （這與'chain|C'標幟不同！） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>設定環境變數。 </p> <p> 此標幟會建立設為值VAL的環境變數"VAR"，其中VAL可包含規則運算式回參考，$N和%N，將加以擴充。 您可多次使用此標幟來設定多個變數。 變數稍後可透過%{VAR}在下列RewriteCond模式中參考。 使用此標幟可移除並記住標題中的資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## RewriteCond指令（可選）{#section_9D72B2AB454849A7B681BC39C506AAA3}

RewriteCond指令定義規則條件。 當RewriteCond在RewriteRule之前時，只有在規則的模式與當前標題匹配且附加條件適用時，才使用規則。

重寫條件指令採用以下形式：

```
RewriteCond TestString CondPattern [Flags]
```

**** TestString是可包含下列結構的字串：

純文字檔案——通過未更改的文本。

背向參照提供對「陣列」或「條件陣列」的分組部分（內括弧）的訪問。 有兩種類型的反向參照：

* **RewriteRule** Backreferences這些匹配對應RewriteRule模式中的回參考，格式為$N(0)  &lt;>例如, `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* **RewriteCond回** 溯參考這些符合上次相符RewriteCondCondPattern中的回溯參考，格式為%N(0)  &lt;>

**變** 數這些為%{NAME_OF_VARIABLE}格式的變數，其中NAME_OF_VARIABLE可以是定義變數名稱的字串。有關設定環境變數的詳細資訊，請參閱`[E]`標籤。 變數也可在產生搜尋結果的搜尋表單中定義。

**函** 數以下是${NAME_OF_FUNCTION:key}格式的函式，其中NAME_OF_FUNCTION為：

* tolower使&#x200B;*key*&#x200B;中的所有字元都小寫。
* toupper使&#x200B;*key*&#x200B;中的所有字元都大寫。
* escape URL —— 對&#x200B;*key*&#x200B;中的所有字元進行編碼。
* 字元a...z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9&#39;、&#39;*&#39;、&#39;-&#39;、&#39;.&#39;、&#39;/&#39;、&#39;@&#39;和&#39;_&#39;未變更，空格會轉換為&#39;+&#39;，而所有其他字元則會轉換為其%x URL編碼等同字元。
* 取消轉義會將&#39;+&#39;轉換回空格，所有%xx URL編碼字元都轉換回單一字元。

有一個特殊的替代字串：&#39;-&#39;表示「無替代」。 &#39;-&#39;字串通常與C(chain)標幟搭配使用，讓您在進行替代之前，將URL與數種模式相符。

**CondPatternA** 標準的擴充規則運算式，包含一些新增功能。模式字串可以前置詞&#39;!&#39; 字元（驚嘆號），以指定不符合的模式。 您可使用下列其中一個特殊變數，而非實際的規則運算式字串。

所有這些測試都可加上驚嘆號(&#39;!&#39;)的前置詞 否定其意義。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern字串 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>從詞法上來說，它就更少了。 </p> <p> 將<i>CondPattern</i>視為純字串，並從語義上與<i>TestString</i>進行比較。 如果<i>TestString</i>詞法上小於<i>CondPattern</i>，則為true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p> 詞法上更大。 </p> <p> 將<i>CondPattern</i>視為純字串，並從語義上與<i>TestString</i>進行比較。 如果<i>TestString</i>詞法上大於<i>CondPattern</i>，則為true。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>從詞法上講是相等的。 </p> <p> 將<i>CondPattern</i>視為純字串，並從語義上與<i>TestString</i>進行比較。 如果<i>TestString</i>在詞法上等於<i>CondPattern</i>，則為true。 也就是說，兩個字串完全相同（字元逐字元）。 如果<i>CondPattern</i>僅為""（兩個引號），則會比較<i>TestString</i>與空字串。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**標幟** （選用）

標幟括在方括弧`[]`中，而多個標幟以逗號分隔：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>旗標 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC'（無大寫） </p> </td> 
   <td colname="col2"> <p>使測試不敏感。 即，在展開的<i>TestString</i>和<i>CondPattern</i>中，'A-Z'和'a-z'之間沒有差異。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR'（或下一個條件） </p> </td> 
   <td colname="col2"> <p> 使用此項，將規則條件與局部OR（而非隱式AND）結合。 若沒有此標幟，您必須多次寫入第二個／規則。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範例 {#section_E7454FFE169E459AABD9D033651939CB}

假設您有一個標準標題格式的公司網站：「My Company」後面接著連字型大小，接著是頁面特定的說明（例如「My Company - Welcome」或「My Company - News」）。 您想要從標題中去除「My Company - 」，並在索引網站時將整個標題轉換為大寫字母。

以下重寫規則使用函式頭將標題的描述性部分僅重寫為大寫：

```
RewriteRule  ^My[[:blank:]]Company[[:blank:]]-[[:blank:]] 
<b>(.*)</b>$  ${toupper: 
<b>$1</b>} 
```

規則的模式`(^My[[:blank:]]Company[[:blank:]]-[[:blank:]] (.*))`包含與&quot;My Company-&quot;後面的標題內容相符的回參考&#x200B;**`(.*)`**。 請記住，帶有括弧()的陣列的部分周圍會建立可由替代引用的反向引用。 在此範例中，替代(${toupper:**$1**})使用toupper函式重寫該回參考(**$1**)。

因此，&quot;My Company - Welcome&quot;表單的標題被改寫為&quot;WELCOME&quot;。

**確認**

重寫引擎軟體最初由Apache Group開發，用於Apache HTTP伺服器項目(https://www.apache.org/)。

## 新增搜尋標題規則{#task_155CECB74BE3444384EDBBD04F41515E}

您可以新增搜尋標題規則，以指定網站搜尋結果中標題的顯示方式。 您可以控制標題的任何部分。

<!-- 

t_adding_search_title_rules.xml

 -->

**若要新增搜尋標題規則**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Search Title Rules]**」。
1. 在[!DNL Search Title Rules]欄位中，輸入您想要的規則。

   允許以「#」（雜湊）字元開頭的空白行和註解行。
1. （可選）在[!DNL Search Title Rules]頁面的[!DNL Test Search Title Rules]欄位中輸入測試標題，然後按一下&#x200B;**Test**。
1. 按一下&#x200B;**「儲存變更」**。
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參閱[設定分段網站的遞增索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可選）在[!DNL Search Title Rules]頁面上，執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。
