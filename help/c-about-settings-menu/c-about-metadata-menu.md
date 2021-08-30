---
description: 使用「中繼資料」功能表可自訂搜尋定義和索引插入。
solution: Target
subtopic: Metadata
title: 關於中繼資料功能表
topic-legacy: Settings,Site search and merchandising
uuid: f12fc863-a140-45e8-b219-3dbfdef099cd
exl-id: 53d62da9-c5bd-4c4a-bb89-743704f66f7f
source-git-commit: 95bf92df17d7832df72e8d883a22f9063e53a18d
workflow-type: tm+mt
source-wordcount: '8028'
ht-degree: 1%

---

# 關於中繼資料功能表{#about-the-metadata-menu}

使用「中繼資料」功能表可自訂搜尋定義和索引插入。

## 關於定義 {#concept_AE48035C210145169BE067D396975620}

您可以使用[!DNL Definitions]自定義客戶提交搜索查詢時考慮的HTML和元資料欄位的內容和相關性。

您可以編輯已預先定義的欄位。 或者，您也可以根據中繼資料標籤內容建立新的使用者定義欄位。 每個定義都顯示在[!DNL Staged Definitions]頁面的單一行上。

另請參閱[關於資料檢視](../c-about-reports-menu/c-about-data-views.md#concept_DCA897D074464BC1861AA47B40CC86C3)。

## 新增中繼標籤欄位 {#task_6DF188C0FC7F4831A4444CA9AFA615E5}

您可以定義並新增自己的中繼資料標籤欄位。

在新元標籤定義的效果可供客戶查看之前，您必須重建網站索引。

**添加新元標籤欄位**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**」。
1. 在[!DNL Definitions]頁面上，按一下&#x200B;**[!UICONTROL Add New Field]**。
1. 在[!DNL Add Field]頁面上，設定您想要的選項。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>選項 </p> </th> 
      <th colname="col2" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>欄位名稱 </p> </td> 
      <td colname="col2"> <p>指定用於引用欄位的名稱。 </p> <p>欄位名稱必須符合下列規則： </p> <p> 
      <ul id="ul_D39D09CD7E7D41A59ECB6C5A6F4F263D"> 
      <li id="li_11CE852BE3C64CEF90FEC7A6E1079E13"> 名稱只能包含英數字元。 </li> 
      <li id="li_7FC340E7C58545C88CE9AF4AF09AD7AD"> 名稱中允許破折號，但不允許空格。 </li> 
      <li id="li_996FF38457AB4C6DB22B15850A0830CC"> 您最多可以輸入20個字元的名稱。 </li> 
      <li id="li_C1019E587995444D9587D5EA495D719E"> 名稱不區分大小寫，但會與您鍵入的名稱一樣顯示和儲存。 </li> 
      <li id="li_E55404D6CE354EC89CFFEB1048A11F44"> 不能使用預定義欄位中存在的名稱，如<span class="wintitle">分段定義</span>頁上的表中所示。 </li> 
      <li id="li_7CE328AE3B5F45A8A09E2DA7ECB62551"> 不能將單字"any"用作用戶定義欄位名稱的值。 </li> 
      <li id="li_9B8287EED1784E79BFCBBBA956705CD2"> 無法編輯預定義欄位的名稱。 </li> 
      </ul> </p> <p> 欄位名稱範例： </p> <p> 
      <ul id="ul_5881669913D04E35A6D4A6D31BEE7DF3"> 
        <li id="li_0AFFB8B516FE40F8A615C2F578F2CEA3"> 作者 </li> 
        <li id="li_7F0ADFBFB21E4B84ACA8A1CEBFE344D1"> PublishDate </li> 
        <li id="li_6D1BEB3D19AC499E9227EC115AEB6296"> 野性 </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>中繼標籤名稱 </p> </td> 
      <td colname="col2"> <p>決定與定義欄位相關聯的內容。 </p> <p>名稱清單的長度最多可為255個字元。 而且，名稱可以包含HTML中繼標籤名稱屬性中允許的任何字元。 </p> <p>您可以在單一欄位定義中指定多個中繼標籤。 </p> <p>多個值必須以逗號分隔，任何指定網頁上最左側的中繼標籤名稱優先。 </p> <p>例如，假設您已定義名為「auth」的欄位。 欄位名稱具有關聯的中繼標籤「author, dc.author」。 在此案例中，如果兩個中繼標籤都出現在網頁上，則「作者」中繼標籤的內容會編列索引，並搜尋「dc.author」的內容。 </p> <p>用戶定義的欄位定義中必須至少包含一個元標籤名稱。 預先定義的欄位不需要有相關聯的中繼標籤。 但是，如果指定了一個或多個元標籤，則元標籤的內容將覆蓋每個標籤的當前資料源。 </p> <p>例如，如果元標籤「dc.title」與預先定義的「title」欄位相關聯，則來自「dc.title」元標籤的內容會與 
      <code>
        &lt;title&gt; 
      </code>標籤。 </p> <p>其範例包括:  </p> <p> 
      <ul id="ul_0132E15FC19E4C0CA13CD5A12EA3BBEC"> 
      <li id="li_ECD3B194FECB4C2090CAEC8449320D3F"> dc.date </li> 
      <li id="li_09C76BC7AC7348859D01989697212E31"> 說明 </li> 
      <li id="li_9230C0450F9D424087D1F127048DA311"> 獨資企業 </li> 
      </ul> </p> </td> 
    </tr> 
      <tr> 
      <td colname="col1"> <p>資料類型 </p> </td> 
      <td colname="col2"> <p>每個欄位都有相關聯的資料類型，例如文字、數字、日期、版本、排名或位置。 此資料類型決定欄位內容的索引、搜尋及選擇性排序方式。 </p> <p>建立欄位定義後，便無法變更資料類型。 </p> <p>使用下列資訊可協助您選取與欄位所包含資訊相關的資料類型。 </p> <p> 
      <ul id="ul_A3AD5A0CF354410F836311F39151B8A6"> 
      <li id="li_9F412DA7D9EF497BA6E65F9CE10F3046"> <span class="uicontrol"> 文字 </span> 資料類型欄位視為字元字串。 </li> 
      <li id="li_AD78B75644AE40208F0239311015611F"> <span class="uicontrol"> 數字 </span> 資料類型欄位視為整數或浮點數值。 </li> 
      <li id="li_0B46975C589148E9A7C32A8D250487B7"> <span class="uicontrol"> 日期 </span> 資料類型欄位視為日期/時間說明符。新增或編輯新欄位時，您可以自訂允許的日期/時間格式。 </li> 
      <li id="li_BB68CB1DBE0543AC9000B3DEDFB28E7E"> <span class="uicontrol"> 版 </span> 本資料類型欄位視為自由格式數值資料。例如，1.2.3在1.2.2之前排序。 </li> 
      <li id="li_0BA895B4DADA46528A7A4161EEB1521E"> <span class="uicontrol"> 排名 </span> 資料類型欄位的處理方式與「數字」類型欄位相同，只是這些欄位會額外影響搜尋結果中的排名/關聯性計算。 <p>請參閱<a href="../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397" type="concept" format="dita" scope="local">關於排名規則</a>。 </p> </li> 
      <li id="li_459405DA437049AD88AA1FAC28F04720"> <span class="uicontrol"> 位 </span> 置資料類型欄位被視為世界上任何地方的物理位置。允許的位置格式包括： <p> 
      <ul id="ul_D2CEBFA1A5504AA996BA2F7641AFB7F3"> 
      <li id="li_5283A2F2D5D84840B3D920C08D43654C"> 5位或9位的郵遞區號，格式為DDDDD或DDDDD-DDD，其中每個「D」是0-9位。 </li> 
      <li id="li_A5CD4DFC90164BC68183DB7D10603B7C"> 以DDD形式表示的三位數區號。 </li> 
      <li id="li_9DAEAE64BC7F4902B25043D998C8F56D"> 形式為±DD.DDD±DDD.DDD的經緯度對，其中第一個數字指定緯度，第二個數字指定經度。 </li> 
      </ul> </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>允許清單 </p> </td> 
      <td colname="col2"> <p>僅當選擇了<span class="uicontrol">文本</span>或<span class="uicontrol">數字</span>時可用。 </p> <p>在此欄位的中繼資料內容中，個別索引分隔值。 </p> <p>例如，選取「允許清單」時，內容「紅、黃、綠、藍」會被視為四個個別值，而非一個。 此處理對於範圍搜索最有用(使用 
      <code>
        sp_q_min 
      </code>, 
      <code>
        sp_q_max 
      </code>，或 
      <code>
        sp_q_exact 
      </code>)和 
      <code>
        &lt;search-field-value-list&gt; 
      </code>, 
      <code>
        &lt;search-field-values&gt; 
      </code>和 
      <code>
        &lt;search-display-field-values&gt; 
      </code>。 </p> <p>如果選取了「版本」資料類型，則無法使用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> 動態面 </p> </td> 
      <td colname="col2"> <p> 
        <!--NEW 2/2/2014--> <p>附註: 此功能預設不會啟用。請連絡技術支援以啟用供您使用。 啟動後，它會顯示在使用者介面中。 </p> </p> <p>將已識別的面向設定為動態。 </p> <p>Facet會建置在中繼標籤欄位上。 中繼標籤欄位是低階的核心搜尋層，是AdobeSearch&amp;Promote。 另一方面，刻面是GS（引導式搜尋）的一部分，即高階的AdobeSearch&amp;Promote呈現層。 Facet擁有元標籤欄位，但元標籤欄位對Facet一無所知。 </p> <p>請參閱<a href="../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local">關於動態面</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>允許重複資料消除 </p> </td> 
      <td colname="col2"> <p>核取此選項可啟用此欄位的重複資料刪除。 也就是說，允許在搜尋時透過 
        <code>
          sp_dedupe_field 
        </code>搜索CGI參數。 </p> <p>請參閱<a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local">搜索CGI參數</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>表名 </p> </td> 
      <td colname="col2"> <p>將指定欄位與指定表名永久關聯。 </p> <p>只要在核心搜尋CGI參數或範本標籤中提及此類欄位，表名就會自動提供。 此功能可透過表格比對來選取動態Facet，但您也可以視需要將其用於非動態Facet欄位。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>清單分隔字元 </p> </td> 
      <td colname="col2"> <p>僅當選擇<span class="uicontrol">允許清單</span>時可用。 </p> <p>指定將各個清單值分開的字元。 您可以指定多個字元，每個字元都視為值分隔符號。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>預設搜尋 </p> </td> 
      <td colname="col2"> <p>當選中時，即使在給定搜索查詢中未顯式指定該欄位，也搜索該欄位內容。 如果您取消選取此選項，則只有在請求時才會搜尋欄位。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>垂直更新欄位 </p> </td> 
      <td colname="col2"> <p> <p>附註: 此功能預設不會啟用。請連絡技術支援以啟用供您使用。 啟動後，它會顯示在使用者介面中。 </p> </p> <p>將標識欄位設定為「垂直更新」欄位。 </p> <p>「垂直更新」欄位是可通過「垂直更新」過程（<span class="uicontrol">索引</span> &gt; <span class="uicontrol">垂直更新</span>）更新的候選欄位。 由於進行「垂直更新」的方式，因此無法在自由文字搜尋中搜尋這些欄位的內容。 選中此選項會導致在任何類型的索引操作期間，此欄位的內容未添加到「word」索引中。 它還允許在「垂直更新」操作期間更新此欄位。 </p> <p>若要深入了解垂直更新，請參閱<a href="../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local">關於垂直更新</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>相關性 </p> </td> 
      <td colname="col2"> <p>您可以編輯預先定義和使用者定義欄位的相關性。 </p> <p>1-10分級指定相關性。 1的設定表示它最不相關，10是最相關。 當軟體在每個欄位中考慮查詢符合時，會考慮這些值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>排序 </p> </td> 
      <td colname="col2"> <p>指定何時按命名欄位排序結果，方法為 
        <code>
          sp_s 
        </code>搜索CGI參數。 </p> <p>請參閱<a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local">搜索CGI參數</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>語言 </p> </td> 
      <td colname="col2"> <p>僅當選擇了「<span class="uicontrol">排名</span>」、「<span class="uicontrol">數字</span>」或「<span class="uicontrol">日期</span>」時可用。 </p> <p>控制在為此欄位的日期、數字和排名值編製索引時應用的語言和區域設定慣例。 </p> <p>您可以選擇套用帳戶語言（語言學&gt;字詞和語言）。 或者，您可以應用與包含每個數字或日期值的文檔相關聯的語言，或特定語言。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>日期格式 </p> </td> 
      <td colname="col2"> <p>只有在選取資料類型<span class="uicontrol">日期</span>時才可用。 </p> <p>控制為此欄位的日期值編製索引時識別的日期格式。 </p> <p>為每個日期欄位提供日期格式字串的預設清單。 您可以新增至清單或編輯清單以符合您自己網站的需求。 </p> <p>請參閱<a href="../c-appendices/r-date-formats.md#reference_4D1FC1F6B9F44857967188496D8D335B" type="reference" format="dita" scope="local">日期格式</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>測試日期格式 </p> </td> 
      <td colname="col2"> <p>僅當選擇資料類型<span class="uicontrol">日期</span>時可用。 </p> <p>可讓您預覽指定的日期格式，以確保格式正確。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>時區 </p> </td> 
      <td colname="col2"> <p>僅當選擇資料類型<span class="uicontrol">日期</span>時可用。 </p> <p>控制在為未指定時區的此欄位建立日期值索引時應用的假定時區。 </p> <p>例如，如果帳戶時區設定為"America/Los Angeles"，而您選取<span class="uicontrol">使用帳戶時區</span>，則下列沒有指定時區的中繼日期值，會視為太平洋時間，計算日光節約時間： </p> <p>&lt;meta name="dc.date" content="Mon, 05 Sep 201213:12:00"&gt; </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最不重要的排名值 </p> </td> 
      <td colname="col2"> <p>僅當選擇資料類型<span class="uicontrol"> Rank </span>時可用。 </p> <p>控制表示任何文檔的最低級別的排名值。 </p> <p>如果文檔排名從最低排名的0到最高排名的10，則將此值設定為0。 </p> <p>如果文檔排名從最高排名的1到最低排名的10，則將此值設定為10。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>預設排名值 </p> </td> 
      <td colname="col2"> <p>僅當選擇資料類型<span class="uicontrol"> Rank </span>時可用。 </p> <p>如果文檔不包含為此排名欄位定義的任何元標籤，則控制所使用的排名值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最重要的排名值 </p> </td> 
      <td colname="col2"> <p>僅當選擇資料類型<span class="uicontrol"> Rank </span>時可用。 </p> <p>控制表示任何文檔的最大排名的排名值。 </p> <p>如果文檔排名從最低排名的0到最高排名的10，則將此值設定為10。 </p> <p>如果文檔排名從最高排名的1到最低排名的10，則將此值設定為1。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>預設單位 </p> </td> 
      <td colname="col2"> <p>僅當選擇資料類型<span class="uicontrol">位置</span>時可用。 </p> <p>控制近距搜索的距離值處理。 </p> <p>如果將預設單位設定為<span class="uicontrol">英里</span>，則應用到此欄位的任何鄰近搜索最小/最大距離標準(通過 
      <code>
        sp_q_min[_#] 
      </code>或 
      <code>
        sp_q_max[_#] 
      </code>搜尋CGI參數)視為英里，否則視為公里。 </p> <p>此選項還控制應用於輸出的預設距離單位 
      <code>
        &lt;Search-Display-Field&gt; 
      </code>搜尋結果範本標籤套用至鄰近地區搜尋輸出欄位時。 </p> <p>請參閱<a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local">關於鄰近搜尋</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>建立範圍說明？ </p> </td> 
      <td colname="col2"> <p>僅當選擇<span class="uicontrol">數字</span>作為資料類型時可用。 </p> <p>控制欄位範圍說明的自動建立，以便與<span class="uicontrol">設計</span> &gt; <span class="uicontrol">導覽</span> &gt; <span class="uicontrol"> Facets </span>搭配使用。 </p> <p>請參閱<a href="../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5" format="dita" scope="local">關於Facets </a>。 </p> <p> <p>注意： 如果此欄位已勾選「垂直更新欄位」 </span> ，則在「垂直更新」期間會更新生成的「欄位範圍」說明欄位。 <span class="uicontrol">但建議在<span class="uicontrol">範圍欄位</span>中識別的欄位也勾選了<span class="uicontrol">垂直更新欄位</span>。 </span></p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>範圍欄位 </p> </td> 
      <td colname="col2"> <p>只有在勾選「建立範圍說明」 </span>時才可用。<span class="uicontrol"> </span></p> <p>要更新的<span class="uicontrol">文字</span>欄位，包含當前欄位的範圍說明。 此清單包含尚未與「欄位範圍」生成的其他欄位一起使用的所有<span class="uicontrol">文本</span>欄位。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>範圍值 </p> </td> 
      <td colname="col2"> <p>僅當選中了「建立範圍描述」 </span>並選擇了「<span class="uicontrol">範圍欄位</span>」項時可用。<span class="uicontrol"> </span></p> <p>建立「欄位範圍」說明時要使用的空白分隔資料點清單。 例如： </p> <code> 10&amp;nbsp;20&amp;nbsp;50&amp;nbsp;100&amp;nbsp;1000 </code> <p>您可以按任何順序輸入這些值。 值會先排序並移除重複項目，再儲存。 您也可以指定負值和非整數值。 </p> <p>針對此欄位的每個值： 
      <ul id="ul_C4B41AF5AADF4B84B9C489CE82FF7075"> 
      <li id="li_90736394A5AE4F5CA6B47687BCB627AA">如果值小於(&lt;)<span class="uicontrol">範圍值</span>中的最小值，則使用<span class="uicontrol"> "Less Than"格式</span> </li> 
      <li id="li_A5C272B2D26A468CA07EB2046B2EA8A7">如果值大於或等於(&gt;=)<span class="uicontrol">範圍值</span>中的最大值，則使用<span class="uicontrol"> "Greater Than" Format </span>。 </li> 
      <li id="li_9DDFB70E1E824CF4819C57450C1A6DD2">否則，會找到「範圍」，其中欄位值落在兩個連續的<span class="uicontrol">範圍值</span>之間(大於(&gt;)小於(&lt;=)大於(&lt;=))，並且使用<span class="uicontrol">中間格式</span>。 </li> 
    </ul> </p> <p>例如，上述值集範例將定義值的一組說明： 
    <ul id="ul_03ED30D5A19346AB8E6809BDD186A9A9"> 
      <li id="li_F97A6B3763954EFE9B6751F472AF7D20">少於10 </li> 
      <li id="li_12B6F636A6444B8292E0BFE4F55032DF">大於或等於10且小於20 </li> 
      <li id="li_545A2EAF5BD046B5AD59B77DB43DCD14">大於或等於20且小於50 </li> 
      <li id="li_26A8CD2422524D2CBD36794C6908572A">大於或等於50且小於100 </li> 
      <li id="li_05EBEEE68DC348E0821F1CC16D04D69C">大於或等於100且小於10000 </li> 
      <li id="li_9513A6B519394780A6A41B80762A0370">大於或等於10000 </li> 
      </ul> </p> <p>請參閱使用大於測試？ <span class="uicontrol"></span> 以變更這些測試的執行方式。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>「小於」格式 </p> </td> 
      <td colname="col2"> <p>僅當選中了「建立範圍描述」 </span>並選擇了「<span class="uicontrol">範圍欄位</span>」項時可用。<span class="uicontrol"> </span></p> <p>這是用於指定小於<span class="uicontrol">範圍值</span>中最小值的範圍說明的模板。 最小值將使用數值佔位符標籤<span class="uicontrol"> ~N~ </span>來表示。 例如： </p> <code> Less&amp;nbsp;than&amp;nbsp;~N~ </code> <p>或: </p> <code> ~N~&amp;nbsp;and&amp;nbsp;below </code> <p>通常，值的格式為「as-is」 — 即，對於「5 10 20」的<span class="uicontrol">範圍值</span>定義和提供的值1，生成的範圍說明將只是「小於5」。 如果您希望其為「4.99及以下版本」，請將<span class="uicontrol"> Precision </span>設定為<span class="uicontrol"> 2 </span>並使用以下格式： </p> <code> ~n~&amp;nbsp;and&amp;nbsp;below </code> <p>在<span class="uicontrol"> "小於"格式</span>中，小寫<span class="uicontrol"> ~n~ </span>將使值根據<span class="uicontrol"> Precision </span>設定捨入<i></i>。 </p> <p>注意：若要在範圍說明中加入任何數值預留位置，請以反斜線(\)首碼指定，例如<span class="uicontrol"> \~N~ </span>或<span class="uicontrol"> \~n~ </span>。 若要包含反斜線字元，請使用另一個反斜線來指定，例如<span class="uicontrol"> \\ </span>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>中間格式 </p> </td> 
      <td colname="col2"> <p>僅當選中了「建立範圍描述」 </span>並選擇了「<span class="uicontrol">範圍欄位</span>」項時可用。<span class="uicontrol"> </span></p> <p>這是用於指定介於<span class="uicontrol">範圍值</span>中找到的最小值和最大值之間的值的範圍說明的模板。 對於給定範圍，較低範圍值將使用數值佔位符標籤<span class="uicontrol"> ~L~ </span>來表示，而較高範圍值將使用標籤<span class="uicontrol"> ~H~ </span>來表示。 例如： </p> <code> ~L~&amp;nbsp;to&amp;nbsp;~H~ </code> <p>或: </p> <code> Between&amp;nbsp;~L~&amp;nbsp;and&amp;nbsp;~H~ </code> <p>或: </p> <code> Less&amp;nbsp;than&amp;nbsp;~H~&amp;nbsp;and&amp;nbsp;greater&amp;nbsp;than&amp;nbsp;~L~ </code> <p>通常，這些值將格式化為「原樣」 — 即，對於「5 10 20」的<span class="uicontrol">範圍值</span>定義和提供的值8，生成的範圍描述將只是「5到10」之類的內容。 如果您希望其為「介於5和9.99之間」，且值較高時向下調整<i></i>，請將<span class="uicontrol"> Precision </span>設定為<span class="uicontrol"> 2 </span>並使用此格式： </p> <code> Between&amp;nbsp;~L~&amp;nbsp;and&amp;nbsp;~h~ </code> <p>同樣地，<span class="uicontrol"> ~L~ </span>可以用<span class="uicontrol"> ~l~ </span>取代，以便根據<span class="uicontrol"> Precision </span>設定調整<i>向上</i>的較低值。 這表示定義如下： </p> <code> Between&amp;nbsp;~l~&amp;nbsp;and&amp;nbsp;~H~ </code> <p>如果<span class="uicontrol"> Precision </span>值為<span class="uicontrol"> 2 </span>，將建立「介於5.01和10之間」。 </p> <p>小寫<span class="uicontrol"> ~l~ </span>將根據<span class="uicontrol"> Precision </span>設定使小寫<i>up</i>捨入，小寫<span class="uicontrol"> ~h~ </span>將使大小寫<i>down</i>捨入。 </p> <p>注意：若要在範圍說明中加入任何數值預留位置，請以反斜線(\)首碼指定，例如<span class="uicontrol"> \~L~ </span>或<span class="uicontrol"> \~h~ </span>。 若要包含反斜線字元，請使用另一個反斜線來指定，例如<span class="uicontrol"> \\ </span>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>"Greater Than"格式 </p> </td> 
      <td colname="col2"> <p>僅當選中了「建立範圍描述」 </span>並選擇了「<span class="uicontrol">範圍欄位</span>」項時可用。<span class="uicontrol"> </span></p> <p>這是用於指定大於<span class="uicontrol">範圍值</span>中最大值的值的範圍說明的模板。 最大值將使用數值預留位置標籤<span class="uicontrol"> ~N~ </span>來表示。 例如： </p> <code> Greater&amp;nbsp;than&amp;nbsp;~N~ </code> <p>或: </p> <code> ~N~&amp;nbsp;and&amp;nbsp;above </code> <p>通常，值的格式為「as-is」 — 即，對於「5 10 20」的<span class="uicontrol">範圍值</span>定義和提供的值30，生成的範圍說明將只是「大於20」。 如果您希望其為「20.01及更高版本」，請將<span class="uicontrol"> Precision </span>設定為<span class="uicontrol"> 2 </span>並使用以下格式： </p> <code> ~n~&amp;nbsp;and&amp;nbsp;above </code> <p>在<span class="uicontrol"> "Greater Than" Format </span>中，小寫<span class="uicontrol"> ~n~ </span>將根據<span class="uicontrol"> Precision </span>設定使值捨入<i> up</i>。 </p> <p>注意：若要在範圍說明中加入任何數值預留位置，請以反斜線(\)首碼指定，例如<span class="uicontrol"> \~N~ </span>或<span class="uicontrol"> \~n~ </span>。 若要包含反斜線字元，請使用另一個反斜線來指定，例如<span class="uicontrol"> \\ </span>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>精準度 </p> </td> 
      <td colname="col2"> <p>僅當選中了「建立範圍描述」 </span>並選擇了「<span class="uicontrol">範圍欄位</span>」項時可用。<span class="uicontrol"> </span></p> <p>一個整數值，它指定小數點右側的位數。 這也會控制捨入操作。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>刪零？ </p> </td> 
      <td colname="col2"> <p>僅當選中了「建立範圍描述」 </span>，選擇了「<span class="uicontrol">範圍欄位</span>」項，並設定了「非零<span class="uicontrol">精度</span>」值時，才可用。<span class="uicontrol"> </span></p> <p>是否應將"0.50"顯示為"。50"? </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>刪除尾隨零？ </p> </td> 
      <td colname="col2"> <p>僅當選中了「建立範圍描述」 </span>，選擇了「<span class="uicontrol">範圍欄位</span>」項，並設定了「非零<span class="uicontrol">精度</span>」值時，才可用。<span class="uicontrol"> </span></p> <p>是否應將「10.00」顯示為「10」？ </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>顯示千分位分隔符？ </p> </td> 
      <td colname="col2"> <p>僅當選中了「建立範圍描述」 </span>並選擇了「<span class="uicontrol">範圍欄位</span>」項時可用。<span class="uicontrol"> </span></p> <p>我們應將"10000"顯示為"10,000"嗎？ 將使用特定於地區的值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>調整零值？ </p> </td> 
      <td colname="col2"> <p>僅當選中了「建立範圍描述」 </span>並選擇了「<span class="uicontrol">範圍欄位</span>」項時可用。<span class="uicontrol"> </span></p> <p>顯示四捨五入的零值時，應根據<span class="uicontrol"> Precision </span>設定向上或向下四捨五入？ 即顯示「0.01」？ </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>使用大於進行測試？ </p> </td> 
      <td colname="col2"> <p>僅當選中了「建立範圍描述」 </span>並選擇了「<span class="uicontrol">範圍欄位</span>」項時可用。<span class="uicontrol"> </span></p> <p>當每個值與<span class="uicontrol">範圍值</span>中按<i><b>降序</b></i>順序處理的值進行比較時，預設情況下，使用大於或等於(&gt;=)運算子進行比較，一旦此測試成功就停止。 這表示，若有一組<span class="uicontrol">範圍值</span>（如「10 20 50 100 1000」），則值100將落在範圍100到1000之間，因為100實際上是&gt;= 100。 如果您希望其範圍介於50到100之間，請核取此選項，這會導致比較使用大於(&gt;)運算子，而非。 </p> <p>例如，若勾選此選項，則此欄位的每個值都會： 
      <ul id="ul_969621B1BD914FA5BD73ED21F8841010"> 
      <li id="li_157BEFDA7D0E44C481F4E4BC9046EF24">如果值小於或等於(&lt;=)<span class="uicontrol">範圍值</span>中的最小值，則使用<span class="uicontrol"> "小於"格式</span> </li> 
      <li id="li_737EE666CA6243A8864E17A311CF3ACC">如果值大於(&gt;)<span class="uicontrol">範圍值</span>中的最大值，則將使用<span class="uicontrol"> "Greater Than" Format </span> </li> 
      <li id="li_353A9820F7F74CCCBB3281EC4CB48734">否則，將會找到欄位值落在兩個連續<span class="uicontrol">範圍值</span>(大於或等於(&gt;=)小於(&lt;)大小值)之間的範圍，並使用<span class="uicontrol">中間格式</span> </li> 
    </ul> </p> <p>和，若取消勾選： 
    <ul id="ul_945844C33C2E4D95A598C4876E15F211"> 
      <li id="li_653B6E2934574DA3B4BCEF07D0A84527">如果值小於(&lt;)<span class="uicontrol">範圍值</span>中的最小值，則使用<span class="uicontrol"> "Less Than"格式</span> </li> 
      <li id="li_AECA6880002F40FAB1820B37237550A7">如果值大於或等於(&gt;=)<span class="uicontrol">範圍值</span>中的最大值，則將使用<span class="uicontrol"> "Greater Than" Format </span> </li> 
      <li id="li_ECB2DF7CA592497298E9ADC708220366">否則，將會找到欄位值落在兩個連續<span class="uicontrol">範圍值</span>(大於(&gt;)小值且小於或等於(&lt;=)大值)之間的範圍，並使用<span class="uicontrol">中間格式</span> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>測試 </p> </td> 
      <td colname="col2"> <p>僅當選中了「建立範圍描述」 </span>並選擇了「<span class="uicontrol">範圍欄位</span>」項時可用。<span class="uicontrol"> </span></p> <p>提供示例數值，然後按<span class="uicontrol"> Test </span>按鈕以查看如何建立「範圍」欄位。 產生的「範圍」說明會顯示在視窗中。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

   另請參閱[新增中繼標籤欄位](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。
1. 按一下 **[!UICONTROL Add]**.
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參閱[配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （選用）在[!DNL Definitions]頁面上，執行下列任一操作：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以還原您所做的任何更改。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送階段設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 編輯預先定義或使用者定義的中繼標籤欄位 {#task_0A7657B63596421BB6DB3ED44F827AB3}

您只能編輯預先定義的中繼標籤中的特定欄位，或編輯使用者定義的中繼標籤中的所有欄位。

在客戶看到元標籤變更的效果之前，您必須重建網站索引。

**要編輯預定義或用戶定義的元標籤欄位**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**」。
1. 在[!DNL Definitions]頁面的[!DNL Actions]列中，按一下要更改的元標籤欄位名稱行中的&#x200B;**[!UICONTROL Edit]**。
1. 在[!DNL Pinned Keyword Results Manager]頁面的表格中，按一下您要變更之關鍵字列中的&#x200B;**[!UICONTROL Edit]** 。
1. 在[!DNL Edit Field]頁面上，設定您想要的選項。

   如果您選擇對預先定義的中繼標籤欄位進行變更，請注意，並非所有欄位都可編輯。

   請參閱[新增中繼標籤欄位](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)下的選項表。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參閱[配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （選用）在[!DNL Definitions]頁面上，執行下列任一操作：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以還原您所做的任何更改。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送階段設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 刪除用戶定義的元標籤欄位 {#task_9361EF38B5E743038B6672FA6CF70FD3}

您可以刪除不再需要或使用的使用者定義中繼標籤欄位。

您無法刪除預先定義的中繼標籤欄位。 不過，您可以編輯特定欄位。

請參閱[編輯預定義或用戶定義的元標籤欄位](../c-about-settings-menu/c-about-metadata-menu.md#task_0A7657B63596421BB6DB3ED44F827AB3)。

在客戶看到刪除元標籤的效果之前，您必須重建網站索引。

**刪除用戶定義的元標籤欄位**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**」。
1. 在[!DNL Definitions]頁面的[!DNL User-defined fields]區段中，按一下您要移除之中繼標籤欄位名稱列中的&#x200B;**[!UICONTROL Delete]** 。
1. 在確認對話框中，按一下&#x200B;**[!UICONTROL OK]**。
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參閱[配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （選用）在[!DNL Definitions]頁面上，執行下列任一操作：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以還原您所做的任何更改。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送階段設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 關於插入 {#concept_DA091920671948A0A893A26B3A2FAAE5}

您可以使用[!DNL Injections]將內容插入網頁，而無需自行編輯頁面。

您可以將內容附加至特定索引欄位，例如「target」或「body」，或以新值取代索引內容。 例如，如果您將新內容插入「目標」中繼標籤欄位，系統會將此資訊視為硬式編碼頁面內容。 無論您的網站頁面是否具有對應內容，您都可以編輯任何預先定義之中繼標籤欄位的內容。 例如，您可以編輯下列預先定義之中繼標籤欄位名稱的內容：

* alt
* body
* charset
* date
* desc
* 鍵
* language
* Target
* title
* url

## 使用測試現場注射 {#section_74939EA9E6EA4D2A92E8066B3B11CF92}

您可以選擇在[!DNL Staged Injections]頁面上使用&#x200B;**[!UICONTROL Test]**。 您輸入測試欄位名稱（例如「title」或「body」）、原始欄位值（例如「Home Page」），以及來自您網站的測試URL。 結果值會顯示供參考。 測試期間不會變更目前的值。

## 使用欄位插入定義 {#section_C1BBF19DE8EF4A6F8CC3ED691F3953A9}

注入定義的形式如下：

```
append|replace field [regexp] URL value
```

`append|replace`、`field`、`URL`。 和`value`項是必需的。 每行輸入一個注入定義。 以下示例包含6種不同的插入定義。

```
replace title  https://www.yoursite.com/company/contactus.html Adobe: Contact Us 
append body https://www.yoursite.com/products/* On Sale Now! 
append target https://www.yoursite.com/news/bob_white/ Regular Weekly Feature 
append target regexp https://www.yoursite.com/travel/mr_travel/.*\column.html$ Regular Weekly Feature 
replace charset https://www.yoursite.com/japanese/intro.txt shift-jis 
replace language https://www.yoursite.com/japanese/intro.txt ja_JP
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>注射定義 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> append|replace  </span> </p> </td> 
   <td colname="col2"> <p>選擇"append"以添加插入定義的值("Adobe:聯繫我們」或「立即銷售！」 （在上述範例中）轉換為現有欄位的內容。 選擇「取代」以以定義值覆寫現有欄位內容。 如果欄位目前沒有內容，則會自動新增定義的值，而不論使用哪個選項（附加或取代）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> 欄位  </span> </p> </td> 
   <td colname="col2"> <p>欄位名稱為必填。 以下是您可使用的十個預先定義欄位名稱： </p> <p> 
     <ul id="ul_B9336FA53023474EAEE399116E7FC972"> 
      <li id="li_C621203DCD2B4875A54A1DD19F0B5B90"> <span class="codeph"> Alt </span> </li> 
      <li id="li_9217E6A037254BEDBB8D006B70D7670D"> <span class="codeph"> body </span> </li> 
      <li id="li_DCDC50F93F224F02897419B745E09399"> <span class="codeph"> charset </span> </li> 
      <li id="li_D95668236B6547B99966668C82B302AB"> <span class="codeph"> 日期 </span> </li> 
      <li id="li_D2071681274345C3B97E9ADA6D223271"> <span class="codeph"> desc  </span> </li> 
      <li id="li_26683A9209454A438D811187FB929482"> <span class="codeph"> 鍵  </span> </li> 
      <li id="li_A5E19F81B872402CA62B5AB9497E030D"> <span class="codeph"> language </span> </li> 
      <li id="li_FD0B1CD9E6304B18B9D7F57E61015107"> <span class="codeph"> 目標  </span> </li> 
      <li id="li_400D7E3F3E9B47EFB2FF5C0D278DB573"> <span class="codeph"> 標題 </span> </li> 
      <li id="li_449BCBEE4F64424BB69F780C10F5956C"> <span class="codeph"> url </span> </li> 
     </ul> </p> <p>每個欄位名稱都對應至您網站頁面上的元素。 例如，如果您指定欄位名稱<span class="codeph"> desc </span>，則可以將插入定義值新增至與您網站頁面上之說明中繼標籤對應的欄位。 </p> <p>如果您的頁面上不存在任何說明中繼資料標籤，則定義的內容會為您建立標籤。 <span class="codeph"> desc </span>插入中指定的內容會像硬式編碼的元描述內容一樣顯示在結果頁面上。 </p> <p>您也可以使用相同的欄位名稱建立多個定義。 例如，假設您有下列注射： </p> <p> <code> replace&nbsp; <b>title</b>&nbsp;https://www.mysite.com/&nbsp;Welcome&nbsp;to&nbsp;My&nbsp;Site </code> </p> <p> <code> replace&nbsp; <b>title</b>&nbsp;https://www.mysite.com/company/*.html&nbsp;My&nbsp;Site:&nbsp;Contact </code> </p> <p>上述範例中的所有網頁都會收到插入的標題「歡迎使用我的網站」。 「/company/」資料夾中的頁面會插入新標題「My Site:與我們連絡」，取代前一個。 </p> <p>請注意，注射會以其在<span class="wintitle"> 「欄位插入定義」 </span>文本框中的顯示順序應用。 如果針對相同位置的頁面定義相同欄位（此範例中為「標題」）多次，則優先於後續定義。 </p> <p> <span class="codeph"> [regexp]  </span>  — 可選。如果您選擇使用<span class="codeph"> regexp </span>選項，則定義的URL會被視為規則運算式。 </p> <p>請參閱<a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local">規則運算式</a>。 </p> <p>以下定義中： </p> <p> <code> replace&nbsp;target&nbsp; <b>regexp&amp;nbsp;^.*/products/.*\.html$</b>&nbsp;Important&nbsp;information </code> </p> <p> 在符合規則運算式<span class="codeph">^的所有頁面上，「重要資訊」都會插入「target」欄位。*/products/.*\.html$ </span>. </p> <p>因此，您有下列項目： </p> <p> <code> https://www.mydomain.com/products/page1.html 
      &nbsp;&nbsp;&nbsp;&nbsp;(Will&nbsp;receive&nbsp;"target"&nbsp;content) </code> </p> <p> <code> https://www.mydomain.com/product/oldstuff.html 
      &nbsp;&nbsp;&nbsp;&nbsp;(Will&nbsp;not&nbsp;receive&nbsp;"target"&nbsp;content) </code> </p> <p>在下列範例中： </p> <p> <code> append&amp;nbsp;title&amp;nbsp;regexp&amp;nbsp;^.*\.pdf$&amp;nbsp;Millennium&amp;nbsp;Science </code> </p> <p>此插入會將「Millennium Science」附加至所有以「.pdf」副檔名結尾之頁面的「title」內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> URL </span> </p> </td> 
   <td colname="col2"> <p>需要URL，並指定要插入的檔案。 </p> <p>URL是下列任一項： </p> <p> 
     <ul id="ul_C5C74F6D5EA943B293742989EB822751"> 
      <li id="li_382392DB778D4E14BFFC96D35A861951"> 完整路徑，如https://www.mydomain.com/products.html </li> 
      <li id="li_EA2BD0FB66A44CD0844613316F6174D4"> 部分路徑，如https://www.mydomain.com/products中所示 </li> 
      <li id="li_D5E0D6D897C8493ABBFC65517CD4A7DB"> 使用萬用字元的URL，如https://www.mydomain.com/*.html中 </li> 
     </ul> </p> <p>URL值中不得有任何空格字元。 若使用<span class="codeph"> regexp </span>選項，則會將URL視為規則運算式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> value </span> </p> </td> 
   <td colname="col2"> <p>值為必要值，可用來取代或新增至現有欄位內容。 您可以為相同的欄位名稱指定多個值。 例如： </p> <p>附加<b>keys</b> https://www.mysite.com/travel/ <b>summer</b>, <b>beach</b>, <b>sand</b> </p> <p>附加<b>keys</b> https://www.mysite.com/travel/fare/*.html <b>廉價票證</b> </p> <p>在上述範例中，"summer, beach, sand"一詞會附加至"/travel/"目錄中所有頁面的"keys"欄位。 "/travel/fare/"目錄中所有頁面上的"keys"欄位也附加"ceys tickets"一詞。 </p> </td> 
  </tr> 
 </tbody> 
</table>

另請參閱[選擇要爬網的內容類型和索引](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8)。

## 新增欄位插入定義 {#task_E86566FA1FF74CF68115C0ADA05172AE}

您可以使用[!DNL Injections]將內容插入網頁，而無需自行編輯頁面。

您可以選擇在[!DNL Injections]頁面上使用&#x200B;**[!UICONTROL Test]**。 您輸入測試欄位名稱（例如「title」或「body」）、原始欄位值（例如「Home Page」），以及來自您網站的測試URL。 結果值會顯示供參考。 測試期間不會變更目前的值。

**添加欄位插入定義**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]**」。
1. （可選）在[!DNL Injections]頁面的[!DNL Test Field Injections]區域中，輸入測試欄位、測試原始值和測試URL，然後按一下&#x200B;**[!UICONTROL Test]**。
1. 在[!DNL Field Injection Definitions]欄位中，為每行輸入一個插入定義。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （選用）執行下列任一操作：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以還原您所做的任何更改。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送階段設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 關於屬性載入器 {#concept_9EF38E98811B42CDA41996432B9AD209}

使用[!DNL Attribute Loader]定義其他輸入來源以增加從網站編目的資料。

>[!NOTE]
>
>若要使用「屬性載入器」，您可能需要由Adobe帳戶代表或Adobe支援在您的帳戶中啟用它。

您可以使用資料摘要輸入來源來存取儲存在表單中的內容，該表單與網站上通常發現的表單不同。 您使用其中一個可用的編目方法來執行此作業。 然後，可將這些來源的資料插入到已編目內容的資料中。

將「屬性載入器」定義添加到[!DNL Staged Attribute Loader Definitions]頁後，可以更改除「名稱」值和「類型」值之外的任何配置設定

[!DNL Attribute Loader]頁面會顯示下列資訊：

* 已配置並添加的已定義屬性載入器配置的名稱。
* 已新增每個連接器的下列資料來源類型之一：

   * **文字**  — 簡單的「一般」檔案、逗號分隔、定位點分隔或其他一致分隔格式。
   * **摘要**  - XML摘要。

* 是否為下一個爬網和索引啟用配置。
* 資料源的地址。

另請參閱[屬性插入程式如何用於文字和摘要……](../c-about-settings-menu/c-about-metadata-menu.md#section_E059A33D61EE4DB0972A37B8A35E9E16)

另請參閱[關於配置多個屬性載入器](../c-about-settings-menu/c-about-metadata-menu.md#section_4CC49C74EF294608A184E233F215ADFF)

另請參閱[關於新增屬性時使用預覽……](../c-about-settings-menu/c-about-metadata-menu.md#section_E9CAB000A94C4D9189786C1EDB1CDB46)

## 屬性插入程式如何用於屬性載入器中的文字和摘要設定 {#section_E059A33D61EE4DB0972A37B8A35E9E16}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>步驟 </p> </th> 
   <th colname="col2" class="entry"> <p>程序 </p> </th> 
   <th colname="col3" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>下載資料來源。 </p> </td> 
   <td colname="col3"> <p>對於文字和摘要設定，這是簡單的檔案下載。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>將下載的資料來源劃分為個別偽檔案。 </p> </td> 
   <td colname="col3"> <p>對於<span class="uicontrol">文本</span>，每行以新行分隔的文本都對應於單個文檔，並使用指定的分隔符（如逗號或制表符）進行分析。 </p> <p>對於<span class="uicontrol">摘要</span>，每個檔案的資料會使用下列格式的規則運算式模式擷取： </p> <p> <code class="syntax js"> &lt;${Itemtag}&gt;(.*?)&lt;/${Itemtag}&gt; </code> </p> <p>使用<span class="uicontrol">在<span class="wintitle">屬性載入器添加</span>頁上的</span>映射，建立資料的快取副本，然後為Crawler建立連結清單。 資料儲存在本機快取中，並填入已設定的欄位。 </p> <p>將解析的資料寫入本地快取。 </p> <p>此快取稍後將被讀取，以建立Crawler所需的簡單HTML文檔。 例如， </p> <p> <code class="syntax html"> &lt;html&gt;&lt;head&gt; 
      &lt;title&gt;{title}&lt;/title&gt; 
      &lt;meta&nbsp;name="{field}"&nbsp;content="{data}"&nbsp;/&gt; 
      ... 
      &lt;/head&gt;&lt;body&gt; 
      {body} 
      &lt;/body&gt;&lt;/html&gt; </code> </p> <p><span class="codeph"> &lt;title&gt; </span>元素只有在與「標題」元資料欄位有映射時才產生。 同樣地，<span class="codeph"> &lt;body&gt; </span>元素只有在與Body元資料欄位有映射時才產生。 </p> <p> <b>重要</b>:不支援為預先定義的URL中繼標籤指派值。 </p> <p>對於所有其他映射，將為在原始文檔中找到資料的每個欄位生成<span class="codeph"> &lt;meta&gt; </span>標籤。 </p> <p>每個檔案的欄位會新增至快取。 對於寫入快取的每個文檔，也生成一個連結，如以下示例所示： </p> <p> <code class="syntax html"> &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      .... </code> </p> <p>配置的映射必須有一個欄位標識為主鍵。 此對應會構成從快取擷取資料時所使用的金鑰。 </p> <p>Crawler可識別URL <span class="codeph">索引：</span>配置前置詞，可接著存取本機快取的資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>對快取的文檔集進行爬網。 </p> </td> 
   <td colname="col3"> <p><span class="codeph">索引：</span>連結將添加到爬網程式的待處理清單中，並以正常爬網順序進行處理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>處理每個文檔。 </p> </td> 
   <td colname="col3"> <p>每個連結的索引鍵值對應於快取中的項目，因此對每個連結進行編目會導致從快取中擷取該檔案的資料。 然後，它會「組合」成HTML影像，並加以處理並新增至索引。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 關於配置多個屬性載入器 {#section_4CC49C74EF294608A184E233F215ADFF}

您可以為任何帳戶定義多個屬性載入器設定。

新增屬性載入器時，您可以選擇使用功能&#x200B;**[!UICONTROL Setup Maps]**&#x200B;來下載資料來源的範例。 會檢查資料是否適合。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p> 屬性載入器類型 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>文字 </p> </td> 
   <td colname="col2"> <p>先嘗試制表符，然後使用垂直條(<span class="codeph"> | </span>)，最後加上逗號(<span class="codeph"> 、 </span>)。 如果您在按一下「<span class="uicontrol">設定映射</span>」之前已指定分隔字元值，則會改用該值。 </p> <p>最佳配適方案會在地圖欄位中填入適當標籤和欄位值的猜測。 此外，顯示所分析資料的採樣。 如果您知道檔案包含標題列，請務必選取第一列</span>中的<span class="uicontrol">標題。 設定函式會使用此資訊來更好地識別產生的對應項目。 </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>資訊源 </p> </td> 
   <td colname="col2"> <p>下載資料源並執行簡單的XML解析。 </p> <p>生成的XPath標識符顯示在映射表的標籤行中，並且在欄位中顯示類似的值。 這些行僅標識可用資料，不會生成更複雜的XPath定義。 但是，它仍然很有幫助，因為它描述了XML資料並標識了Itemtag。 </p> <p> <p>注意： 「設定映射」函式將下載整個XML源以執行其分析。 如果檔案很大，則此操作可能會超時。 </p> </p> <p>成功後，此函式將標識所有可能的XPath項，其中許多項不理想使用。 請務必檢查產生的地圖定義，並移除您不需要或想要的定義。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>「設定映射」功能可能不適用於大型XML資料集，因為其檔案解析器嘗試將整個檔案讀入記憶體。 因此，您可能會遇到記憶體不足的情況。 但是，當在編製索引時處理同一文檔時，它不會讀入記憶體。 相反，大型文檔「在移動時」被處理，並且不會先完全讀入記憶體。

## 關於新增屬性載入器時使用預覽 {#section_E9CAB000A94C4D9189786C1EDB1CDB46}

屬性載入器資料在索引操作之前載入。

新增屬性載入器時，您可以選擇使用功能&#x200B;**[!UICONTROL Preview]**&#x200B;來驗證資料，就像儲存資料一樣。 它會針對設定執行測試，但不會將設定儲存至帳戶。 測試存取已設定的資料來源。 但是，它將下載快取寫入臨時位置；它與索引編目器使用的主快取資料夾不衝突。

預覽僅處理由&#x200B;**Acct:IndexConnector-Preview-Max-Documents**&#x200B;控制的五個文檔的預設值。 預覽的文檔以源格式顯示，如向索引編目程式顯示。 顯示與Web瀏覽器中的「檢視來源」功能類似。 可以使用標準導航連結導航預覽集中的文檔。

預覽不支援XML配置，因為此類文檔是直接處理的，不會下載到快取中。

## 新增屬性載入器定義 {#task_A735E5EF763343A9B675E1A3B09AFDBC}

每個「屬性載入器」配置定義一個資料源和映射，以將為該源定義的資料項與索引中的元資料欄位相關。

>[!NOTE]
>
>若要使用「屬性載入器」，您可能需要由Adobe帳戶代表或Adobe支援在您的帳戶中啟用它。

在客戶看到新定義和已啟用定義的效果之前，請重建網站索引。

**添加屬性載入器定義**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**」。
1. 在[!DNL Stage Attribute Loader Definitions]頁面上，按一下&#x200B;**[!UICONTROL Add New Attribute Loader]**。
1. 在[!DNL Attribute Loader Add]頁面上，設定您想要的設定選項。 可用的選項取決於您選取的&#x200B;**[!UICONTROL Type]**。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>選項 </p> </th> 
      <th colname="col2" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>名稱 </p> </td> 
      <td colname="col2"> <p>屬性載入器配置的唯一名稱。 您可以使用英數字元。 也允許使用字元「_」和「 — 」。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>類型 </p> </td> 
      <td colname="col2"> <p>資料的來源。 您選擇的資料源類型會影響生成的選項，這些選項在「<span class="wintitle">屬性載入器添加</span>」頁上可用。 您可以選擇下列項目： </p> <p> 
      <ul id="ul_1ADC3DFBC929467385F7465BE8E13635"> 
      <li id="li_64FCD749F55442BAB316BD474128D4F9"> <span class="uicontrol"> 文字 </span> <p>簡單的平面文本檔案、逗號分隔、制表符分隔或其他一致的分隔格式。 每行以新行分隔的文本都對應於單個文檔，並使用指定的分隔符進行分析。 </p> <p>您可以從1(1)開始，將每個值或欄對應至由欄號參考的中繼資料欄位。 </p> </li> 
      <li id="li_2A4F16CE6DCE4114B7F8E4FE156252BB"> <span class="uicontrol"> 資訊源 </span> <p>下載包含多個「行」資訊的主XML文檔。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>資料源類型：文字</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>已啟用 </p> </td> 
      <td colname="col2"> <p>將設定「開啟」以供使用。 或者，您可以關閉設定，以防止使用。 </p> <p> <b>注意</b>:禁用的屬性載入器配置將被忽略。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>主機地址 </p> </td> 
      <td colname="col2"> <p>指定資料所在的伺服器主機的地址。 </p> <p>如果需要，可以指定資料源文檔的完整URI（統一資源標識符）路徑，如以下示例所示： </p> <p> <code otherprops="syntax html"> https://www.somewhere.com/some_path/some_file.tsv </code> </p> <p>或  </p> <p> <code class="syntax html"> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.csv </code> </p> <p>URI被劃分為「主機地址」、「檔案路徑」、「協定」以及（可選）「用戶名」和「密碼」欄位的相應條目 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>檔案路徑 </p> </td> 
      <td colname="col2"> <p>指定簡單普通文本檔案、逗號分隔、制表符分隔或其他一致分隔格式檔案的路徑。 </p> <p>路徑相對於主機地址的根。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>通訊協定 </p> </td> 
      <td colname="col2"> <p>指定用於訪問檔案的協定。 您可以選擇下列項目： </p> <p> 
      <ul id="ul_F6BC10FD51CA4A1D855B2B3212838A9C"> 
      <li id="li_79FB7DC65E774ABBB23E57BF98AD9738"> HTTP <p>如有必要，您可以輸入正確的驗證憑據以訪問HTTP伺服器。 </p> </li> 
      <li id="li_BAA9AD5E4B014E09B3A66C94022B7225"> HTTPS <p>如有必要，您可以輸入正確的驗證憑據以訪問HTTPS伺服器。 </p> </li> 
      <li id="li_E716ABB169DD408BA91F1CA27F445A16"> FTP <p>您必須輸入正確的驗證憑證才能存取FTP伺服器。 </p> </li> 
      <li id="li_FD7143019C5244C3B8A5B1B5AA84859A"> SFTP <p>您必須輸入正確的驗證憑證才能存取SFTP伺服器。 </p> </li> 
      <li id="li_38E0036C1365419F9D00083CACA34AFB"> 檔案 </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>逾時 </p> </td> 
      <td colname="col2"> <p>指定FTP、SFTP、HTTP或HTTPS連線的逾時（秒）。 此值必須介於30和300之間。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>重試 </p> </td> 
      <td colname="col2"> <p>指定失敗FTP、SFTP、HTTP或HTTPS連線的重試次數上限。 此值必須介於0和10之間。 </p> <p>值為零(0)將阻止重試嘗試。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>編碼 </p> </td> 
      <td colname="col2"> <p>指定指定的資料源檔案中使用的字元編碼系統。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>分隔字元 </p> </td> 
      <td colname="col2"> <p>指定您要用來勾勒指定資料來源檔案中每個欄位的字元。 </p> <p>逗號字元(<span class="codeph"> 、 </span>)是分隔字元的範例。 逗號可做為欄位分隔字元，有助於分隔您指定之資料來源檔案中的資料欄位。 </p> <p>選擇<span class="uicontrol">頁簽？ </span> 使用水準定位字元作為分隔符。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>第一列的標題 </p> </td> 
      <td colname="col2"> <p>指示資料源檔案中的第一行僅包含標題資訊，而不包含資料。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>過時天數 </p> </td> 
      <td colname="col2"> <p>設定屬性載入器資料下載之間的最小間隔。 在下載重新整理頻率間隔內發生的索引觸發下載會被忽略。 將此值設為預設值1時，屬性載入器資料在24小時內不會下載多次。 在下載刷新頻率間隔內發生的所有搜索索引都使用上次下載的資料集。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>地圖 </p> </td> 
      <td colname="col2"> <p>使用列號指定列到元資料的映射。 </p> <p> 
      <ul id="ul_981AE2C6D30443BDBFC6575D413732A2"> 
      <li id="li_A42CB9DFFF8C45A7BAC2D471FE96CEBE"> <span class="uicontrol"> 欄 </span> <p> 指定列號，第一列為1(1)。 若要為每個欄新增對應列，請在「<span class="wintitle">動作</span>」下方按一下「<span class="uicontrol"> + </span>」。 </p> <p>您不需要參考資料來源中的每一欄。 反之，您可以選擇略過值。 </p> </li> 
      <li id="li_26E8C9554A5D4BC5A5073D6385E3626F"> <span class="uicontrol"> 欄位 </span> <p>定義用於每個生成的&lt;meta&gt;標籤的名稱屬性值。 </p> </li> 
      <li id="li_5DFA514B7F9549B98D6CBC095A66033C"> <span class="uicontrol"> 中繼資料? </span> <p>使<span class="uicontrol">欄位</span>成為下拉清單，您可從中為當前帳戶選擇定義的元資料欄位。 </p> <p>如果需要，<span class="uicontrol">欄位</span>值可以是未定義的元資料欄位。 未定義的中繼資料欄位有時有助於建立<span class="wintitle">篩選指令碼</span>所使用的內容。 </p> <p>請參閱<a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local">關於篩選指令碼</a>。 </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892C95"> <span class="uicontrol"> 主鍵？  </span> <p>只有一個欄位被識別為主鍵。 此欄位將用作「外鍵」，以匹配屬性載入器資料與索引中的相應文檔。 </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892D96"> <span class="uicontrol"> 脫HTML?  </span> <p>核取此選項時，會移除在此欄位資料中找到的任何HTML標籤。 </p> </li> 
      <li id="li_359D2902859B4C5BADB0BA26F0BA4DC0"> <span class="uicontrol"> 動作 </span> <p>可讓您將列新增至地圖，或從地圖中移除列。 列的順序並不重要。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>資料源類型：摘要</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>已啟用 </p> </td> 
      <td colname="col2"> <p>將設定「開啟」以供使用。 或者，您可以關閉設定，以防止使用。 </p> <p> <b>注意</b>:禁用的屬性載入器配置將被忽略。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>主機地址 </p> </td> 
      <td colname="col2"> <p>指定資料所在的伺服器主機的地址。 </p> <p>如果需要，可以指定資料源文檔的完整URI（統一資源標識符）路徑，如以下示例所示： </p> <p> <code class="syntax html"> https://www.somewhere.com/some_path/some_file.tsv </code> </p> <p>或  </p> <p> <code class="syntax html"> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.csv </code> </p> <p>URI被劃分為「主機地址」、「檔案路徑」、「協定」以及（可選）「用戶名」和「密碼」欄位的相應條目。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>檔案路徑 </p> </td> 
      <td colname="col2"> <p>指定包含多個「行」資訊的主XML文檔的路徑。 </p> <p>路徑相對於主機地址的根。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>通訊協定 </p> </td> 
      <td colname="col2"> <p>指定用於訪問檔案的協定。 您可以選擇下列項目： </p> <p> 
      <ul id="ul_976A34FD14A841F2B610C1C0CCBB82B9"> 
      <li id="li_05BBA0F670F14431A89AE4178F1A6F94"> HTTP <p>如有必要，您可以輸入正確的驗證憑據以訪問HTTP伺服器。 </p> </li> 
      <li id="li_100446691F304572B8FC3F083F86A2CB"> HTTPS <p>如有必要，您可以輸入正確的驗證憑據以訪問HTTPS伺服器。 </p> </li> 
      <li id="li_027088A8E30444DAA8CCCC5B0BAA74C1"> FTP <p>您必須輸入正確的驗證憑證才能存取FTP伺服器。 </p> </li> 
      <li id="li_DCEF9D5C99354990B03E29083C2ED8DC"> SFTP <p>您必須輸入正確的驗證憑證才能存取SFTP伺服器。 </p> </li> 
      <li id="li_44E34FF2AB0D429EB3408106E6FCF780"> 檔案 </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Itemtag </p> </td> 
      <td colname="col2"> <p>標識可用於標識指定資料源檔案中各個XML行的XML元素。 </p> <p>例如，在AdobeXML文檔的以下摘要片段中，Itemtag值為<span class="codeph">記錄</span>: </p> <p> <code class="syntax xml"> &lt;?xml&nbsp;version="1.0"&nbsp;encoding="utf-8"?&gt; 
        &lt;!DOCTYPE&nbsp;gsafeed&nbsp;PUBLIC&nbsp;"-//Google//DTD&nbsp;GSA&nbsp;Feeds//EN"&nbsp;""&gt; 
        &lt;gsafeed&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;datasource&gt;marketplace&lt;/datasource&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;feedtype&gt;incremental&lt;/feedtype&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;group&nbsp;action="add"&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa/ 
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=1&nbsp;action="add"&nbsp;mimetype="text/html"displayurl="https://www.adobe.com/cfusion/marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=1"&gt; 
        &lt;metadata&gt; 
        &lt;meta&nbsp;name="mp_mkt"&nbsp;content="1"/&gt; 
        &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
        dbreferenced/marketplaceicons/icn_air.png"/&gt; 
        &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;AIR&nbsp;Marketplace"/&gt; 
        &lt;meta&nbsp;name="description"&nbsp;content="Discover&nbsp;new&nbsp;applications&nbsp;..."/&gt; 
        &lt;/metadata&gt; 
        &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;AIR&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Discover&nbsp;new&nbsp;applications&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;&lt;/cntent&gt; 
        &lt;/record&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa/ 
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=2&nbsp;action="add"&nbsp;mimetype="text/html"&nbsp;displayurl="https://www.adobe.com/cfusion/ 
        marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=2"&gt; 
        &lt;metadata&gt; 
        &lt;meta&nbsp;name="mp_mkt"&nbsp;content="2"/&gt; 
        &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
        dbreferenced/marketplaceicons/icn_photoshop.png"/&gt; 
        &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;Photoshop&nbsp;Marketplace"/&gt; 
        &lt;meta&nbsp;name="description"&nbsp;content="Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;..."/&gt; 
        &lt;/metadata&gt; 
        &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;Photoshop&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;/content&gt; 
        &lt;/record&gt; 
        ... 
        &lt;record&gt; 
        ... 
        &lt;/record&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/group&gt; 
        &lt;/gsafeed&gt; 
        </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>交叉引用欄位名稱 </p> </td> 
      <td colname="col2"> <p>指定元資料欄位，其值將用作屬性載入器配置資料中的查找「鍵」。 如果未選擇任何值(<b> - None—</b>)，則此配置的資料無法用於排名計算(<b>Rules</b> &gt; <b>Ranking Rules</b> &gt; <b>Edit Rules</b>)。 當您選取值時，此欄位的值會用來交叉參考網站搜尋/銷售檔案與此設定的資料。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>過時天數 </p> </td> 
      <td colname="col2"> <p>設定屬性載入器資料下載之間的最小間隔。 在下載重新整理頻率間隔內發生的索引觸發下載會被忽略。 將此值設為預設值1時，屬性載入器資料在24小時內不會下載多次。 在下載刷新頻率間隔內發生的所有搜索索引都使用上次下載的資料集。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>地圖 </p> </td> 
      <td colname="col2"> <p>可讓您使用XPath運算式指定XML元素對中繼資料的對應。 </p> <p> 
      <ul id="ul_604108C0277C4892AE8A40CA39889ABD"> 
      <li id="li_0AF92270AE9F4BA8B2C7EE41FABC0F34"> <span class="uicontrol"> 標記 </span> <p>指定已解析XML資料的XPath表示。 使用上面的示例AdobeXML文檔，在選項Itemtag下，可以使用以下語法進行映射： </p> <p> <code class="syntax xml"> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
        /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>上述語法轉譯為： </p> <p> 
        <ul id="ul_6400EBD08D424EADA1612FE4F7EFB640"> 
        <li id="li_9958F9B40D42434195597DBA9F2AF28F"> <code class="syntax xml"> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p><span class="codeph">顯示<span class="codeph">記錄</span>元素的 </span>屬性映射到元資料欄位<span class="codeph"> page-url </span>。 </p> </li> 
        <li id="li_759013EA02CD48BE971A55B0A6A11424"> <code class="syntax xml"> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>包含在<span class="codeph">元資料</span>元素內的<span class="codeph">內容</span>元素的<span class="codeph">屬性，該元資料</span>元素包含在<span class="codeph">記錄</span>元素內，其名稱屬性為<span class="codeph">標題</span>，映射到元資料欄位<span class="codeph">標題</span>。 </p> </li> 
        <li id="li_E741CA59197D462EB2946EDE874AFDC8"> <code class="syntax xml"> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>包含在<span class="codeph">記錄</span>元素內的<span class="codeph">元資料</span>元素中的<span class="codeph">內容</span>屬性，其名稱屬性為<span class="codeph">說明</span>，映射到元資料欄位<span class="codeph"> desc </span>。</span><span class="codeph"> </span></p> </li> 
        <li id="li_E35EAE3D284D46D485D9064D7BB6AB13"> <code class="syntax xml"> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>包含在<span class="codeph">記錄</span>元素內的<span class="codeph">元資料</span>元素中的<span class="codeph">內容</span>屬性（其名稱屬性為<span class="codeph">說明</span>）映射到元資料欄位<span class="codeph"> body </span>。</span><span class="codeph"> </span></p> </li> 
        </ul> </p> <p>XPath是相對複雜的表示法。 如需詳細資訊，請前往下列位置： </p> <p>請參閱<a href="https://www.w3schools.com/xml/xpath_intro.asp" scope="external" format="html"> https://www.w3schools.com/xml/xpath_intro.asp </a> </p> </li> 
      <li id="li_8147075D7ACD4811A7ED335F23FE62A6"> <span class="uicontrol"> 欄位 </span> <p>定義用於每個生成的<span class="codeph"> &lt;meta&gt; </span>標籤的名稱屬性值。 </p> </li> 
      <li id="li_2380199D63BF425A919606D8232FA6E2"> <span class="uicontrol"> 中繼資料? </span> <p>使<span class="uicontrol">欄位</span>成為下拉清單，您可從中為當前帳戶選擇定義的元資料欄位。 </p> <p>如果需要，<span class="uicontrol">欄位</span>值可以是未定義的元資料欄位。 未定義的元資料欄位有時對建立<span class="wintitle">篩選指令碼</span>使用的內容很有幫助。 </p> <p>請參閱<a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local">關於篩選指令碼</a>。 </p> <p>當屬性載入器在任何映射欄位上處理具有多個點擊的XML檔案時，多個值會串連到產生的快取檔案中的單一值。 依預設，這些值會使用逗號分隔字元結合。 但是，假設對應的<span class="wintitle">欄位</span>值是定義的中繼資料欄位。 此外，該欄位還設定了<span class="wintitle">允許清單</span>屬性。 在此情況下，在串連中使用欄位的「清單分隔符」值（定義的第一個分隔符）。 </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC70E"> <span class="uicontrol"> 主鍵？  </span> <p>只有一個欄位被識別為主鍵。 此欄位將用作「外鍵」，以匹配屬性載入器資料與索引中的相應文檔。 </p> </li> 
      <li id="li_80D6AF130FCE40AC972FE4B605B86BF6"> <span class="uicontrol"> 脫HTML?  </span> <p>核取此選項時，會移除在此欄位資料中找到的任何HTML標籤。 </p> </li> 
      <li id="li_D40E2F9AD8AD49FC9AC4B8C75BA31E28"> <span class="uicontrol"> 動作 </span> <p>可讓您將列新增至地圖，或從地圖中移除列。 列的順序並不重要。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. （可選）按一下&#x200B;**[!UICONTROL Setup Maps]**&#x200B;下載資料來源的範例。 會檢查資料是否適合。
1. 按一下&#x200B;**[!UICONTROL Add]**&#x200B;將配置添加到[!DNL Attribute Loader Definitions]頁。
1. 在[!DNL Attribute Loader Definitions]頁面上，按一下&#x200B;**[!UICONTROL rebuild your staged site index]**。
1. （選用）在[!DNL Attribute Loader Definitions]頁面上，執行下列任一操作：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以還原您所做的任何更改。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送階段設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 編輯屬性載入器定義 {#task_AA2D1B2BCAFA44A6A0C59A0318274E80}

您可以編輯已定義的現有屬性載入器。

>[!NOTE]
>
>若要使用「屬性載入器」，您可能需要由Adobe帳戶代表或Adobe支援在您的帳戶中啟用它。

並非所有屬性載入器選項都可供您更改，例如[!DNL Type]下拉清單中的「屬性載入器名稱」或「類型」。

**編輯屬性載入器定義**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**」。
1. 在[!DNL Attribute Loader]頁的[!DNL Actions]列標題下，按一下&#x200B;**[!UICONTROL Edit]**&#x200B;獲取要更改其設定的屬性載入器定義名稱。
1. 在[!DNL Attribute Loader Edit]頁面上，設定您想要的選項。

   請參閱[添加屬性載入器定義](../c-about-settings-menu/c-about-metadata-menu.md#task_A735E5EF763343A9B675E1A3B09AFDBC)下的選項表。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）在[!DNL Attribute Loader Definitions]頁面上，按一下&#x200B;**[!UICONTROL rebuild your staged site index]**。
1. （選用）在[!DNL Attribute Loader Definitions]頁面上，執行下列任一操作：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以還原您所做的任何更改。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送階段設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 複製屬性載入器定義 {#task_9B40D5ECFC81411E9480F62A0FD5F2E0}

您可以複製現有的「屬性載入器」定義，以用作要建立的新「屬性載入器」的基礎。

>[!NOTE]
>
>若要使用「屬性載入器」，您可能需要由Adobe帳戶代表或Adobe支援在您的帳戶中啟用它。

複製「屬性載入器」定義時，預設會停用複製的定義。 若要啟用或「開啟」定義，必須從[!DNL Attribute Loader Edit]頁面編輯該定義，然後選取&#x200B;**[!UICONTROL Enable]**。

請參閱[編輯屬性載入器定義](../c-about-settings-menu/c-about-metadata-menu.md#task_AA2D1B2BCAFA44A6A0C59A0318274E80)。

**複製屬性載入器定義**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**」。
1. 在[!DNL Attribute Loader]頁的[!DNL Actions]列標題下，按一下&#x200B;**[!UICONTROL Copy]**&#x200B;以獲取要複製其設定的屬性載入器定義名稱。
1. 在[!DNL Attribute Loader Copy]頁面上，輸入定義的新名稱。
1. 按一下 **[!UICONTROL Copy]**.
1. （選用）在[!DNL Attribute Loader Definitions]頁面上，執行下列任一操作：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以還原您所做的任何更改。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送階段設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 更名屬性載入器定義 {#task_58D5DFD7EBC04111BCB91118E4440DB4}

您可以更改現有屬性載入器定義的名稱。

>[!NOTE]
>
>若要使用「屬性載入器」，您可能需要由Adobe帳戶代表或Adobe支援在您的帳戶中啟用它。

**更名屬性載入器定義**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**」。
1. 在[!DNL Attribute Loader]頁的[!DNL Actions]列標題下，按一下&#x200B;**[!UICONTROL Rename]**&#x200B;以獲取要更改的屬性載入器定義名稱。
1. 在[!DNL Attribute Loader Rename]頁面的[!DNL Name]欄位中輸入定義的新名稱。
1. 按一下 **[!UICONTROL Rename]**.
1. （選用）在[!DNL Attribute Loader Definitions]頁面上，執行下列任一操作：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以還原您所做的任何更改。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送階段設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 載入屬性載入器資料 {#task_2F3C55189B0A4049AB2113F2291CC181}

您可以將已設定的屬性載入器資料下載至網站搜尋/銷售。

[!DNL Data Load]頁顯示有關上次屬性載入器資料載入操作的狀態的以下資訊：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>狀態欄位 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>狀態  </p> </td> 
   <td colname="col2"> <p>指示上次資料載入嘗試的成功或失敗。 或者，它會顯示已在進行中的資料載入操作的狀態。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>開始時間 </p> </td> 
   <td colname="col2"> <p>顯示上次資料載入操作開始的日期和時間。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>停止時間 </p> </td> 
   <td colname="col2"> <p>顯示上次資料載入操作的完成日期和時間。 或者，它表示目前的資料載入操作仍在進行中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**載入屬性載入器資料的方式**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**」。
1. 在[!DNL Attribute Loader Definitions]頁面上，按一下&#x200B;**[!UICONTROL Load Attribute Loader Data]**。
1. 在&#x200B;**[!UICONTROL Attribute Loader Data Load]**&#x200B;頁面上，執行下列其中一項操作：

   * 按一下&#x200B;**[!UICONTROL Start Load]**&#x200B;以啟動載入操作。

      在資料載入操作期間，**Progress**&#x200B;行提供有關其進度的資訊。

   * 按一下&#x200B;**[!UICONTROL Stop Load]**&#x200B;以停止載入操作。

1. 按一下&#x200B;**[!UICONTROL Close]**&#x200B;返回[!DNL Attribute Loader Definitions]頁。

## 預覽屬性載入器資料 {#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0}

您可以使用「預覽」檢視最近載入的屬性載入器資料。

表中的「行」列顯示每行資料的編號，指示載入屬性載入器值的原始順序。

其餘欄顯示與每個條目相關聯的值。

如果表為空，表示您尚未載入任何屬性載入器資料。 您可以關閉[!DNL Attribute Loader Data Preview]頁面，然後載入「屬性載入器」資料。

請參閱[載入屬性載入器資料](../c-about-settings-menu/c-about-metadata-menu.md#task_2F3C55189B0A4049AB2113F2291CC181)。

**預覽屬性載入器資料**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**」。
1. 在[!DNL Attribute Loader Definitions]頁面的[!DNL Actions]欄下方，按一下&#x200B;**[!UICONTROL Preview]**&#x200B;以取得您要檢視其下載資料的設定。
1. 在[!DNL Attribute Loader Data Preview]頁面上，使用頁面頂端和底部的導覽和檢視選項來檢視資料。

   按一下表格中的任何欄標題，以遞增或遞減順序排序資料。
1. 執行下列任一操作：

   * 按一下&#x200B;**[!UICONTROL Download to Desktop]**&#x200B;以下載該表並將其另存為.xlt檔案。
   * 預覽完「屬性載入器」資料時，關閉頁面，並返回先前檢視的頁面。

## 查看屬性載入器定義的設定 {#task_EA99A9694FE948ADA82C1DBA0667851B}

您可以檢閱現有「屬性載入器」定義的組態設定。

將「屬性載入器」定義添加到[!DNL Attribute Loader Definitions]頁後，無法更改其「類型」設定。 請改為刪除定義，然後新增定義。

>[!NOTE]
>
>若要使用「屬性載入器」，您可能需要由Adobe帳戶代表或Adobe支援在您的帳戶中啟用它。

**查看屬性載入器定義的設定**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**」。
1. 在[!DNL Attribute Loader]頁的[!DNL Actions]列標題下，按一下&#x200B;**[!UICONTROL Edit]**&#x200B;獲取要查看或編輯其設定的屬性載入器定義名稱。

## 從最近的「屬性載入器」資料載入中檢視記錄檔 {#task_9C7D6E34BB6C4A40B7CA3EE36ACB0837}

您可以使用[!DNL View Log]檢查最新下載過程的屬性載入器資料日誌檔案。 您也可以使用記錄檢視來監視執行中的下載。

請參閱[載入屬性載入器資料](../c-about-settings-menu/c-about-metadata-menu.md#task_2F3C55189B0A4049AB2113F2291CC181)。

**從最近的「屬性載入器」資料載入中查看日誌**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**」。
1. 在[!DNL Attribute Loader Definitions]頁面上，按一下&#x200B;**[!UICONTROL View Log]**。 記錄頁，
1. 在[!DNL Attribute Loader Data Log]頁面上，使用頁面頂端和底部的導覽和檢視選項來檢視記錄資訊。
1. 完成後，關閉頁面以返回[!DNL Attribute Loader Definitions]頁面。

## 刪除屬性載入器定義 {#task_E8980F66888B476E98C228C1D307EDF8}

您可以刪除不再需要或使用的現有屬性載入器定義。

>[!NOTE]
>
>若要使用「屬性載入器」，您可能需要由Adobe帳戶代表或Adobe支援在您的帳戶中啟用它。

**刪除屬性載入器定義**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**」。
1. 在[!DNL Attribute Loader Definitions]頁的[!DNL Actions]列標題下，按一下&#x200B;**[!UICONTROL Delete]**&#x200B;以獲取要刪除的屬性載入器定義名稱。
1. 在[!DNL Attribute Loader Delete]頁面上，按一下&#x200B;**[!UICONTROL Delete]**。
