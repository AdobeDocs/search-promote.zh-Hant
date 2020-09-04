---
description: 使用「中繼資料」功能表可自訂搜尋定義和索引插入。
seo-description: 使用「中繼資料」功能表可自訂搜尋定義和索引插入。
seo-title: 關於中繼資料選單
solution: Target
subtopic: Metadata
title: 關於中繼資料選單
topic: Settings,Site search and merchandising
uuid: f12fc863-a140-45e8-b219-3dbfdef099cd
translation-type: tm+mt
source-git-commit: 552f93f1f630c64bbe3d5c8a87c4f5895ae6868c
workflow-type: tm+mt
source-wordcount: '8039'
ht-degree: 1%

---


# 關於中繼資料選單{#about-the-metadata-menu}

使用「中繼資料」功能表可自訂搜尋定義和索引插入。

## 關於定義 {#concept_AE48035C210145169BE067D396975620}

您可以使 [!DNL Definitions] 用自訂HTML和中繼資料欄位的內容與相關性，這些欄位是客戶提交搜尋查詢時所考慮的。

您可以編輯已預先定義的欄位。 或者，您也可以根據中繼資料標籤內容建立新的使用者定義欄位。 每個定義都顯示在頁面上的單一行 [!DNL Staged Definitions] 上。

另請參閱 [關於資料視圖](../c-about-reports-menu/c-about-data-views.md#concept_DCA897D074464BC1861AA47B40CC86C3)。

## 新增中繼標籤欄位 {#task_6DF188C0FC7F4831A4444CA9AFA615E5}

您可以定義並新增您自己的中繼資料標籤欄位。

在客戶看到新中繼標籤定義的效果之前，您必須重建網站索引。

**若要新增meta標籤欄位**

1. 在產品功能表上，按一下 **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**。
1. 在頁面上 [!DNL Definitions] ，按一下 **[!UICONTROL Add New Field]**。
1. 在頁 [!DNL Add Field] 面上，設定您想要的選項。

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
      <li id="li_996FF38457AB4C6DB22B15850A0830CC"> 您最多可輸入20個字元的名稱。 </li> 
      <li id="li_C1019E587995444D9587D5EA495D719E"> 名稱不區分大小寫，但會依您輸入名稱的方式顯示和儲存。 </li> 
      <li id="li_E55404D6CE354EC89CFFEB1048A11F44"> 您不能使用「分段定義」頁面上表格中所顯示之預先定義欄位中 <span class="wintitle"> 的名 </span> 稱。 </li> 
      <li id="li_7CE328AE3B5F45A8A09E2DA7ECB62551"> 不能將單字"any"用作用戶定義的欄位名的值。 </li> 
      <li id="li_9B8287EED1784E79BFCBBBA956705CD2"> 不能編輯預定義欄位的名稱。 </li> 
      </ul> </p> <p> 欄位名稱範例： </p> <p> 
      <ul id="ul_5881669913D04E35A6D4A6D31BEE7DF3"> 
        <li id="li_0AFFB8B516FE40F8A615C2F578F2CEA3"> 作者 </li> 
        <li id="li_7F0ADFBFB21E4B84ACA8A1CEBFE344D1"> PublishDate </li> 
        <li id="li_6D1BEB3D19AC499E9227EC115AEB6296"> 狂野 </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>中繼標籤名稱 </p> </td> 
      <td colname="col2"> <p>決定與定義欄位關聯的內容。 </p> <p>名稱清單最多可包含255個字元。 而且，名稱可包含HTML meta標籤名稱屬性中允許的任何字元。 </p> <p>您可以在單一欄位定義中指定多個中繼標籤。 </p> <p>多個值必須以逗號分隔，任何指定網頁上都能找到的最左側中繼標籤名稱優先。 </p> <p>例如，假設您已定義名為"auth"的欄位。 欄位名稱具有關聯的中繼標籤「author, dc.author」。 在本例中，如果兩個中繼標籤都出現在網頁上，則會建立「author」中繼標籤的內容索引並搜尋「dc.author」的內容。 </p> <p>使用者定義的欄位定義中至少必須有一個中繼標籤名稱。 預先定義的欄位不需要有關聯的meta標籤。 但是，如果指定一個或多個中繼標籤，則中繼標籤的內容會覆寫每個標籤的目前資料來源。 </p> <p>例如，如果中繼標籤"dc.title"與預先定義的"title"欄位相關聯，則會將來自"dc.title"中繼標籤的內容索引於任何特定檔案的標 <code>
        &lt;title&gt; 
      </code> 簽上。 </p> <p>其範例包括:  </p> <p> 
      <ul id="ul_0132E15FC19E4C0CA13CD5A12EA3BBEC"> 
      <li id="li_ECD3B194FECB4C2090CAEC8449320D3F"> dc.date </li> 
      <li id="li_09C76BC7AC7348859D01989697212E31"> 描述 </li> 
      <li id="li_9230C0450F9D424087D1F127048DA311"> 獨資公司 </li> 
      </ul> </p> </td> 
    </tr> 
      <tr> 
      <td colname="col1"> <p>資料類型 </p> </td> 
      <td colname="col2"> <p>每個欄位都有關聯的資料類型，例如文字、數字、日期、版本、排名或位置。 此資料類型確定如何為欄位的內容編製索引、搜索和（可選）排序。 </p> <p>建立欄位定義後，您無法變更資料類型。 </p> <p>使用下列資訊可協助您選取與欄位所含資訊相關的資料類型。 </p> <p> 
      <ul id="ul_A3AD5A0CF354410F836311F39151B8A6"> 
      <li id="li_9F412DA7D9EF497BA6E65F9CE10F3046"> <span class="uicontrol"> 文字 </span> 資料類型欄位會視為字元字串。 </li> 
      <li id="li_AD78B75644AE40208F0239311015611F"> <span class="uicontrol"> 數字 </span> 資料類型欄位被視為整數或浮點數值。 </li> 
      <li id="li_0B46975C589148E9A7C32A8D250487B7"> <span class="uicontrol"> 日期 </span> 資料類型欄位被視為日期／時間指定符。 您可以在新增或編輯新欄位時自訂允許的日期／時間格式。 </li> 
      <li id="li_BB68CB1DBE0543AC9000B3DEDFB28E7E"> <span class="uicontrol"> 版本 </span> 資料類型欄位會視為自由格式的數值資料。 例如，1.2.3在1.2.2之前排序。 </li> 
      <li id="li_0BA895B4DADA46528A7A4161EEB1521E"> <span class="uicontrol"> 排名 </span> 資料類型欄位會被視為與「數字」類型欄位相同，只不過這些欄位會額外影響搜尋結果中的排名／相關性計算。 <p>請參閱<a href="../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397" type="concept" format="dita" scope="local">關於排名規則</a>。 </p> </li> 
      <li id="li_459405DA437049AD88AA1FAC28F04720"> <span class="uicontrol"> 位置 </span> 資料類型欄位被視為世界上任何位置的物理位置。 允許的位置格式包括： <p> 
      <ul id="ul_D2CEBFA1A5504AA996BA2F7641AFB7F3"> 
      <li id="li_5283A2F2D5D84840B3D920C08D43654C"> 5位或9位郵遞區號的形式為DDDD或DDDD-DDD，其中每個"D"是0-9位。 </li> 
      <li id="li_A5CD4DFC90164BC68183DB7D10603B7C"> 以DDD格式的三位區號。 </li> 
      <li id="li_9DAEAE64BC7F4902B25043D998C8F56D"> 緯度／經度對的格式為±DD.DDDD±DDD.DDDD，其中第一個數字指定緯度，第二個數字指定經度。 </li> 
      </ul> </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>允許清單 </p> </td> 
      <td colname="col2"> <p>僅在選取「文字」或「編 <span class="uicontrol"> 號」資 </span>料類型 <span class="uicontrol"> 時才 </span> 可用。 </p> <p>在此欄位的中繼資料內容中，個別索引分隔的值。 </p> <p>例如，選取「允許清單」時，內容「紅色、黃色、綠色、藍色」會視為4個個別值，而非1。 此處理方式對於範圍搜尋(使 <code>
        sp_q_min 
      </code>用、 <code>
        sp_q_max 
      </code>或 <code>
        sp_q_exact 
      </code>)以及 <code>
        &lt;search-field-value-list&gt; 
      </code>、 <code>
        &lt;search-field-values&gt; 
      </code>和最有用 <code>
        &lt;search-display-field-values&gt; 
      </code>。 </p> <p>如果選取「版本」資料類型，則無法使用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> 動態Facet </p> </td> 
      <td colname="col2"> <p> 
        <!--NEW 2/2/2014--> <p>附註: 此功能預設不會啟用。請聯絡技術支援以啟動供您使用。 啟動後，它會出現在使用者介面中。 </p> </p> <p>將已識別的Facet設為動態。 </p> <p>Facet建立在meta標籤欄位之上。 中繼標籤欄位是Adobe Search&amp;Promote的低階核心搜尋層。 另一方面，Facet則屬於GS（引導式搜尋）的一部分，即Adobe Search&amp;Promote的高階表現層。 但是，Facet擁有meta標籤欄位，meta標籤欄位對Facet一無所知。 </p> <p>請參 <a href="../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> 閱關於動態面 </a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>允許重複資料消除 </p> </td> 
      <td colname="col2"> <p>選中此選項可啟用此欄位的重複資料消除。 也就是說，允許在搜索時通過Search CGI參數指定 <code>
          sp_dedupe_field 
        </code> 此欄位。 </p> <p>請參 <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> 閱搜索CGI參 </a>數。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>表名 </p> </td> 
      <td colname="col2"> <p>將給定欄位與給定表名永久關聯。 </p> <p>只要在核心搜尋CGI參數或範本標籤中提及此欄位，表名就會自動提供。 此功能允許通過表匹配來選擇動態刻面，但您也可以將其用於非動態刻面欄位（如果需要）。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>清單分隔符號 </p> </td> 
      <td colname="col2"> <p>僅在選取「允 <span class="uicontrol"> 許清單」 </span> 時可用。 </p> <p>指定將個別清單值分開的字元。 您可以指定多個字元，每個字元都視為值分隔符號。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>依預設進行搜尋 </p> </td> 
      <td colname="col2"> <p>在選中時，即使在給定搜索查詢中未明確指定欄位，也搜索欄位內容。 如果您取消選取此選項，則只會在要求時搜尋欄位。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>垂直更新欄位 </p> </td> 
      <td colname="col2"> <p> <p>附註: 此功能預設不會啟用。請聯絡技術支援以啟動供您使用。 啟動後，它會出現在使用者介面中。 </p> </p> <p>將標識的欄位設定為「垂直更新」欄位。 </p> <p>「垂直更新」欄位是要透過「垂直更新」程式(「索引&gt; <span class="uicontrol"> 垂直 </span> 更新」 <span class="uicontrol"> )更新的候選 </span>欄位。 由於「垂直更新」的建立方式，因此無法在自由文字搜尋中搜尋這些欄位的內容。 選中此選項會導致在任何類型的索引操作期間不將此欄位的內容添加到"word"索引中。 它還在「垂直更新」操作期間啟用此欄位的更新。 </p> <p>若要進一步瞭解垂直更新，請參閱 <a href="../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> 垂直更新 </a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>相關性 </p> </td> 
      <td colname="col2"> <p>您可以編輯預先定義和使用者定義欄位的相關性。 </p> <p>關聯性是在1-10級別上指定的。 設定1表示它最不相關，10表示最相關。 當軟體在每個欄位中考慮查詢符合時，會考量到這些值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>排序 </p> </td> 
      <td colname="col2"> <p>指定何時通過Search CGI參數按命名欄位對結果 <code>
          sp_s 
        </code> 進行排序。 </p> <p>請參 <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> 閱搜索CGI參 </a>數。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>語言 </p> </td> 
      <td colname="col2"> <p>僅在選取「排名」、「編 <span class="uicontrol"> 號」或「日 </span>期」資料類型時 <span class="uicontrol"></span><span class="uicontrol"></span> 才可用。 </p> <p>控制在為此欄位的日期、數字和排名值編製索引時應用的語言和地區設定慣例。 </p> <p>您可以選擇套用帳戶語言（「語言學&gt;字詞與語言」）。 或者，您可以套用與包含每個數字或日期值的檔案相關聯的語言，或特定語言。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>日期格式 </p> </td> 
      <td colname="col2"> <p>僅在選取資料類型「日 <span class="uicontrol"> 期」 </span> 時可用。 </p> <p>控制在為此欄位的日期值編製索引時識別的日期格式。 </p> <p>每個日期欄位都會提供日期格式字串的預設清單。 您可以新增至清單或編輯清單以符合您自己網站的需求。 </p> <p>請參閱 <a href="../c-appendices/r-date-formats.md#reference_4D1FC1F6B9F44857967188496D8D335B" type="reference" format="dita" scope="local"> 日期格式 </a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>測試日期格式 </p> </td> 
      <td colname="col2"> <p>僅在將資料類型「日 <span class="uicontrol"> 期」選 </span> 為「資料類型」時可用。 </p> <p>可讓您預覽您所指定的日期格式，以確保其格式正確。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>時區 </p> </td> 
      <td colname="col2"> <p>僅在將資料類型「日 <span class="uicontrol"> 期」選 </span> 為「資料類型」時可用。 </p> <p>控制在為不指定時區的此欄位的日期值編製索引時應用的假定時區。 </p> <p>例如，如果您的帳戶時區設為「美國／洛杉磯」，而您選取「使用帳戶時區」 <span class="uicontrol"></span>，則下列沒有指定時區的中繼日期值會被視為太平洋時間，計入日光節約： </p> <p>&lt;meta name="dc.date" content="Mon, 05 2012年9月2013:12:00"&gt; </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最不重要的排名值 </p> </td> 
      <td colname="col2"> <p>僅在選取「排名」資料類 <span class="uicontrol"> 型 </span> 為「資料類型」時可用。 </p> <p>控制代表任何檔案之最低排名的排名值。 </p> <p>如果您的檔案排名從最低排名的0到最高排名的10，則您將此值設為0。 </p> <p>如果您的檔案排名從最高排名的1到最低排名的10，則將此值設為10。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>預設排名值 </p> </td> 
      <td colname="col2"> <p>僅在選取「排名」資料類 <span class="uicontrol"> 型 </span> 為「資料類型」時可用。 </p> <p>控制當檔案不包含為此排名欄位定義的任何中繼標籤時所使用的排名值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最重要的排名值 </p> </td> 
      <td colname="col2"> <p>僅在選取「排名」資料類 <span class="uicontrol"> 型 </span> 為「資料類型」時可用。 </p> <p>控制代表任何檔案之最高排名的排名值。 </p> <p>如果您的檔案排名從最低排名的0到最高排名的10，則您將此值設為10。 </p> <p>如果您的檔案排名從最高排名的1到最低排名的10，則將此值設為1。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>預設單位 </p> </td> 
      <td colname="col2"> <p>僅在選擇「位置」資料類 <span class="uicontrol"> 型 </span> 作為「資料類型」時可用。 </p> <p>控制距離值的處理以進行鄰近搜尋。 </p> <p>如果將預設單位設定為 <span class="uicontrol"> Miles </span>，則應用於此欄位的任何鄰近搜索最小／最大距離標準(通過 <code>
        sp_q_min[_#] 
      </code><code>
        sp_q_max[_#] 
      </code> Search CGI參數)將被視為miles，否則視為kmels。 </p> <p>此選項還控制應用於鄰近搜索輸出欄位時應用於搜索結果模 <code>
        &lt;Search-Display-Field&gt; 
      </code> 板標籤輸出的預設距離單位。 </p> <p>請參 <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> 閱關於鄰近搜尋 </a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>建立範圍說明？ </p> </td> 
      <td colname="col2"> <p>僅當選擇「 <span class="uicontrol"> 編號」 </span> 作為「資料類型」時可用。 </p> <p>控制欄位範圍說明的自動建立，以便與「設計&gt;導覽 <span class="uicontrol"> &gt;刻面 </span> 」 <span class="uicontrol"> 搭配 </span> 使用 <span class="uicontrol"></span>。 </p> <p>請參閱 <a href="../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5" format="dita" scope="local"> 關於刻面 </a>。 </p> <p> <p>注意： 如果此欄位已勾選「 <span class="uicontrol"> 垂直更新欄 </span> 位」，則在「垂直更新」期間會更新產生的欄位範圍說明欄位。 不過，建議在「範圍欄位」中識別的欄位 <span class="uicontrol"> 也勾選「 </span> 垂直 <span class="uicontrol"> 更新欄位」 </span> 。 </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>範圍欄位 </p> </td> 
      <td colname="col2"> <p>僅在勾選「建 <span class="uicontrol"> 立範圍說明」 </span> 時可用。 </p> <p>「文 <span class="uicontrol"> 字」 </span> 欄位將更新為目前欄位的範圍說明。 此清單包含所 <span class="uicontrol"> 有尚 </span> 未用於「欄位範圍」產生其他欄位的「文字」欄位。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>範圍值 </p> </td> 
      <td colname="col2"> <p>僅當選中「 <span class="uicontrol"> 建立範圍說明」 </span> 並選中「範圍 <span class="uicontrol"> 欄位」項 </span> 目時可用。 </p> <p>建立欄位範圍說明時要使用的空白分隔資料點清單。 例如: </p> <code> 10&amp;nbsp;20&amp;nbsp;50&amp;nbsp;100&amp;nbsp;1000 </code> <p>您可以按任何順序輸入這些值。 值在保存之前會進行排序並刪除重複項。 您也可以指定負值和非整數值。 </p> <p>對於此欄位的每個值： 
      <ul id="ul_C4B41AF5AADF4B84B9C489CE82FF7075"> 
      <li id="li_90736394A5AE4F5CA6B47687BCB627AA">如果值小於(&lt;)範圍值中的最 <span class="uicontrol"> 小值 </span>, <span class="uicontrol"> 則使用「小於」格 </span> 式 </li> 
      <li id="li_A5C272B2D26A468CA07EB2046B2EA8A7">如果值大於或等於(&gt;=)「範圍值」中的最 <span class="uicontrol"> 大值 </span>，則 <span class="uicontrol"> 使用「大於」格 </span> 式。 </li> 
      <li id="li_9DDFB70E1E824CF4819C57450C1A6DD2">否則，會找到「範圍」，其中欄位值介於兩個連續的「範圍值」 <span class="uicontrol"> (大於(&gt;)小值且小於或等於(&lt;=)大值)之間，並使用 </span> 「中間格式 <span class="uicontrol"></span> 」。 </li> 
    </ul> </p> <p>例如，上述值集範例將定義一組值的說明： 
    <ul id="ul_03ED30D5A19346AB8E6809BDD186A9A9"> 
      <li id="li_F97A6B3763954EFE9B6751F472AF7D20">少於10 </li> 
      <li id="li_12B6F636A6444B8292E0BFE4F55032DF">大於或等於10且小於20 </li> 
      <li id="li_545A2EAF5BD046B5AD59B77DB43DCD14">大於或等於20且小於50 </li> 
      <li id="li_26A8CD2422524D2CBD36794C6908572A">大於或等於50且小於100 </li> 
      <li id="li_05EBEEE68DC348E0821F1CC16D04D69C">大於或等於100和小於10000 </li> 
      <li id="li_9513A6B519394780A6A41B80762A0370">大於或等於10000 </li> 
      </ul> </p> <p>請參 <span class="uicontrol"> 閱使用大於測試？ </span> 來變更這些測試的執行方式。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>「小於」格式 </p> </td> 
      <td colname="col2"> <p>僅當選中「 <span class="uicontrol"> 建立範圍說明」 </span> 並選中「範圍 <span class="uicontrol"> 欄位」項 </span> 目時可用。 </p> <p>此範本用來指定小於「範圍值」中最小值的值的範圍 <span class="uicontrol"> 說明 </span>。 最小值將用數字預留位置標籤 <span class="uicontrol"> ~N~表示 </span>。 例如: </p> <code> Less&amp;nbsp;than&amp;nbsp;~N~ </code> <p>或: </p> <code> ~N~&amp;nbsp;and&amp;nbsp;below </code> <p>通常，值將格式化為「原樣」-即，對於「5 10 20」的「範圍值」定義和提供的值1，生成的範圍描述將只是「小於5」之類的內容。 <span class="uicontrol"></span> 如果您希望它為"4.99及以下版本"，請將 <span class="uicontrol"> Precision設 </span> 為 <span class="uicontrol"> 2，並 </span> 使用下列格式： </p> <code> ~n~&amp;nbsp;and&amp;nbsp;below </code> <p>在「 <span class="uicontrol"> 小於」格式 </span>中，小寫 <span class="uicontrol"> ~n~將導致值根據 </span><i></i><span class="uicontrol"></span> Precision設定四捨五入。 </p> <p>注意：若要依原樣在範圍說明中加入任何數值預留位置，請使用反斜線(\)首碼指定——例如。 <span class="uicontrol"> \~N~ </span> 或 <span class="uicontrol"> \~n~ </span>。 若要包含反斜線字元，請使用另一個反斜線來指定該字元，例如 <span class="uicontrol"> \\ </span> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>中間格式 </p> </td> 
      <td colname="col2"> <p>僅當選中「 <span class="uicontrol"> 建立範圍說明」 </span> 並選中「範圍 <span class="uicontrol"> 欄位」項 </span> 目時可用。 </p> <p>此範本用來指定值的範圍說明，這些值介於「範圍值」中找到的最小值和最大值之 <span class="uicontrol"> 間 </span>。 對於給定範圍，低範圍值將使用數字預留位置標籤 <span class="uicontrol"> ~L~ </span>，而高範圍值將使用標籤 <span class="uicontrol"> ~H~來表示 </span>。 例如: </p> <code> ~L~&amp;nbsp;to&amp;nbsp;~H~ </code> <p>或: </p> <code> Between&amp;nbsp;~L~&amp;nbsp;and&amp;nbsp;~H~ </code> <p>或: </p> <code> Less&amp;nbsp;than&amp;nbsp;~H~&amp;nbsp;and&amp;nbsp;greater&amp;nbsp;than&amp;nbsp;~L~ </code> <p>通常，值的格式為「原樣」-即，對於「5 10 20」的「範圍值」定義和提供的值為8，生成的範圍描述將只是「5到10」之類的。 <span class="uicontrol"></span> 如果您希望它為"5到9.99"，並向下調整較高值 <i></i>，請將 <span class="uicontrol"> Precision設 </span> 置為 <span class="uicontrol"> 2 </span> ，然後使用下列格式： </p> <code> Between&amp;nbsp;~L~&amp;nbsp;and&amp;nbsp;~h~ </code> <p>同樣地， <span class="uicontrol"> ~ </span> L~可以被~l~ <span class="uicontrol"> ~取代，使低值值向上調整 </span> ，也根據精度 <i></i><span class="uicontrol"></span> 設定。 這表示定義如下： </p> <code> Between&amp;nbsp;~l~&amp;nbsp;and&amp;nbsp;~H~ </code> <p>如果 <span class="uicontrol"> 精度 </span> 值為 <span class="uicontrol"> 2，則 </span> 會建立「介於5.01和10」。 </p> <p>小寫 <span class="uicontrol"> ~l~ </span> ，使小寫值按精度設定向上捨入，小寫 <i>~h，使小寫值</i><span class="uicontrol"></span><span class="uicontrol"></span><i></i>&gt;down。 </p> <p>注意：若要依原樣在範圍說明中加入任何數值預留位置，請使用反斜線(\)首碼指定——例如。 <span class="uicontrol"> \~L~ </span> 或 <span class="uicontrol"> \~h~ </span>。 若要包含反斜線字元，請使用另一個反斜線來指定該字元，例如 <span class="uicontrol"> \\ </span> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>「大於」格式 </p> </td> 
      <td colname="col2"> <p>僅當選中「 <span class="uicontrol"> 建立範圍說明」 </span> 並選中「範圍 <span class="uicontrol"> 欄位」項 </span> 目時可用。 </p> <p>此範本用於指定大於「範圍值」中最大值的值的範圍 <span class="uicontrol"> 說明 </span>。 最大值將使用數值預留位置標籤 <span class="uicontrol"> ~N~來表示 </span>。 例如: </p> <code> Greater&amp;nbsp;than&amp;nbsp;~N~ </code> <p>或: </p> <code> ~N~&amp;nbsp;and&amp;nbsp;above </code> <p>通常，值將格式化為「原樣」-即，對於「5 10 20」的「範圍值」定義和提供的值 <span class="uicontrol"></span> 30，生成的範圍說明將只是「大於20」之類的。 如果您希望它為"20.01及更高版本"，請將 <span class="uicontrol"> Precision </span> 設 <span class="uicontrol"> 為2，並 </span> 使用下列格式： </p> <code> ~n~&amp;nbsp;and&amp;nbsp;above </code> <p>在「 <span class="uicontrol"> 大於」格式 </span>中，小寫 <span class="uicontrol"> ~n~將使值根據 </span> Precision設定四捨五入 <i></i><span class="uicontrol"></span> 。 </p> <p>注意：若要依原樣在範圍說明中加入任何數值預留位置，請使用反斜線(\)首碼指定——例如。 <span class="uicontrol"> \~N~ </span> 或 <span class="uicontrol"> \~n~ </span>。 若要包含反斜線字元，請使用另一個反斜線來指定該字元，例如 <span class="uicontrol"> \\ </span> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>精確度 </p> </td> 
      <td colname="col2"> <p>僅當選中「 <span class="uicontrol"> 建立範圍說明」 </span> 並選中「範圍 <span class="uicontrol"> 欄位」項 </span> 目時可用。 </p> <p>一個整數值，它指定小數點右側的位數。 這也控制捨入操作。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>刪除前導零？ </p> </td> 
      <td colname="col2"> <p>僅當選中「 <span class="uicontrol"> 建立範圍 </span> 說明」、選擇「範圍欄位」 <span class="uicontrol"> 項並設定了非零精度值時，才 </span><span class="uicontrol"></span> 可用。 </p> <p>我們是否應將"0.50"顯示為"。50"? </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>刪除尾隨零？ </p> </td> 
      <td colname="col2"> <p>僅當選中「 <span class="uicontrol"> 建立範圍 </span> 說明」、選擇「範圍欄位」 <span class="uicontrol"> 項並設定了非零精度值時，才 </span><span class="uicontrol"></span> 可用。 </p> <p>我們是否應將"10.00"顯示為"10"? </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>顯示數千個分隔符？ </p> </td> 
      <td colname="col2"> <p>僅當選中「 <span class="uicontrol"> 建立範圍說明」 </span> 並選中「範圍 <span class="uicontrol"> 欄位」項 </span> 目時可用。 </p> <p>我們應該將"10000"顯示為"10,000"嗎？ 將使用地區設定特定值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>調整零值？ </p> </td> 
      <td colname="col2"> <p>僅當選中「 <span class="uicontrol"> 建立範圍說明」 </span> 並選中「範圍 <span class="uicontrol"> 欄位」項 </span> 目時可用。 </p> <p>顯示四捨五入零值時，應根據「精度」( <span class="uicontrol"> Precision)設定將其四捨五入還是 </span> 縮小？ 例如顯示"0.01"? </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>使用大於進行測試？ </p> </td> 
      <td colname="col2"> <p>僅當選中「 <span class="uicontrol"> 建立範圍說明」 </span> 並選中「範圍 <span class="uicontrol"> 欄位」項 </span> 目時可用。 </p> <p>當每個值與「範圍值」中的值進行比較(以 <span class="uicontrol"> 遞減順序處理 </span><i><b></b></i> )時，依預設會使用「大於」或「等於」(&gt;=)運算子來比較該值，一旦此測試成功就會停止。 這表示在一組範圍值（例如「10 20 50 100 1000」）中，值100會落在範圍100到1000之間，因為100的確是&gt;= 100。 <span class="uicontrol"></span> 如果您希望它落在50到100之間，請勾選此選項，以便讓比較使用Greater Than(&gt;)運算子。 </p> <p>例如，若是此欄位的每個值，在勾選此選項時： 
      <ul id="ul_969621B1BD914FA5BD73ED21F8841010"> 
      <li id="li_157BEFDA7D0E44C481F4E4BC9046EF24">如果值小於或等於(&lt;=)範圍值中的最 <span class="uicontrol"> 小值 </span>, <span class="uicontrol"> 則使用「小於」格 </span> 式 </li> 
      <li id="li_737EE666CA6243A8864E17A311CF3ACC">如果值大於(&gt;)範圍值中的最 <span class="uicontrol"> 大值 </span>, <span class="uicontrol"> 則使用「大於」格 </span> 式 </li> 
      <li id="li_353A9820F7F74CCCBB3281EC4CB48734">否則，將會在欄位值介於兩個連續的 <span class="uicontrol"> 「範圍值」 </span> (大於或等於(&gt;=)小值且小於(&lt;)大值之間)之間找到範圍，並使用「中間格式 <span class="uicontrol"></span> 」 </li> 
    </ul> </p> <p>和，若未勾選： 
    <ul id="ul_945844C33C2E4D95A598C4876E15F211"> 
      <li id="li_653B6E2934574DA3B4BCEF07D0A84527">如果值小於(&lt;)範圍值中的最 <span class="uicontrol"> 小值 </span>, <span class="uicontrol"> 則使用「小於」格 </span> 式 </li> 
      <li id="li_AECA6880002F40FAB1820B37237550A7">如果值大於或等於(&gt;=)範圍值中的最 <span class="uicontrol"> 大值 </span>, <span class="uicontrol"> 則使用「大於」格 </span> 式 </li> 
      <li id="li_ECB2DF7CA592497298E9ADC708220366">否則，若欄位值介於兩個連續的 <span class="uicontrol"> Range </span> Values(大於(&gt;)小值且小於或等於(&lt;=)大值)之間，則會使用 <span class="uicontrol"> Mentride Format </span> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>測試 </p> </td> 
      <td colname="col2"> <p>僅當選中「 <span class="uicontrol"> 建立範圍說明」 </span> 並選中「範圍 <span class="uicontrol"> 欄位」項 </span> 目時可用。 </p> <p>提供範例數值，然後按「測試」 <span class="uicontrol"> 按鈕 </span> 以查看如何建立「範圍欄位」。 生成的範圍說明將顯示在窗口中。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

   另請參 [閱新增中繼標籤欄位](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。
1. 按一下 **[!UICONTROL Add]**.
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參 [閱配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可選）在頁 [!DNL Definitions] 面上，執行下列任一項作業：

   * 按一 **[!UICONTROL History]** 下以回復您所做的任何變更。

      請參 [閱使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。

## 編輯預先定義或使用者定義的中繼標籤欄位 {#task_0A7657B63596421BB6DB3ED44F827AB3}

您只能編輯預先定義之中繼標籤中的特定欄位，或編輯使用者定義的中繼標籤中的所有欄位。

在您的中繼標籤變更的效果顯現給客戶之前，您必須重建網站索引。

**若要編輯預先定義或使用者定義的中繼標籤欄位**

1. 在產品功能表上，按一下 **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**。
1. 在頁 [!DNL Definitions] 面上，在表格 [!DNL Actions] 的欄中，按一下 **[!UICONTROL Edit]** 您要變更的meta標籤欄位名稱列中。
1. 在頁 [!DNL Pinned Keyword Results Manager] 面的表格中，按一 **[!UICONTROL Edit]** 下您要變更之關鍵字列中的。
1. 在頁 [!DNL Edit Field] 面上，設定您想要的選項。

   如果您選擇變更預先定義的中繼標籤欄位，請注意並非所有欄位都可編輯。

   請參閱「新增中繼標籤欄 [位」下方的選項表](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參 [閱配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可選）在頁 [!DNL Definitions] 面上，執行下列任一項作業：

   * 按一 **[!UICONTROL History]** 下以回復您所做的任何變更。

      請參 [閱使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。

## 刪除用戶定義的meta標籤欄位 {#task_9361EF38B5E743038B6672FA6CF70FD3}

您可以刪除您不再需要或使用的使用者定義中繼標籤欄位。

您無法刪除預先定義的中繼標籤欄位。 不過，您可以編輯特定欄位。

請參 [閱編輯預先定義或使用者定義的中繼標籤欄位](../c-about-settings-menu/c-about-metadata-menu.md#task_0A7657B63596421BB6DB3ED44F827AB3)。

在您的刪除meta標籤效果對客戶可見之前，您必須重建網站索引。

**刪除用戶定義的meta標籤欄位**

1. 在產品功能表上，按一下 **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**。
1. 在頁 [!DNL Definitions] 面上，在表格 [!DNL User-defined fields] 的區段中，按一 **[!UICONTROL Delete]** 下您要移除的meta標籤欄位名稱列中。
1. 在「確認」對話方塊中，按一下 **[!UICONTROL OK]**。
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參 [閱配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可選）在頁 [!DNL Definitions] 面上，執行下列任一項作業：

   * 按一 **[!UICONTROL History]** 下以回復您所做的任何變更。

      請參 [閱使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。

## 關於注射 {#concept_DA091920671948A0A893A26B3A2FAAE5}

您可以使 [!DNL Injections] 用將內容插入網頁，而不需自行編輯頁面。

您可以將內容附加至特定索引欄位，例如「target」或「body」，或以新值取代索引內容。 例如，如果您將新內容插入「目標」中繼標籤欄位，則會將這項資訊視為硬式編碼頁面內容。 無論您的網站頁面是否具有對應的內容，您都可以編輯任何預先定義的中繼標籤欄位的內容。 例如，您可以編輯下列預先定義之中繼標籤欄位名稱的內容：

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

## 使用試驗場注射 {#section_74939EA9E6EA4D2A92E8066B3B11CF92}

您可選擇在頁 **[!UICONTROL Test]** 面上使 [!DNL Staged Injections] 用。 您可輸入測試欄位名稱（例如「title」或「body」）、原始欄位值（例如「Home Page」），以及您網站的測試URL。 結果值將顯示供參考。 測試期間不會變更目前的值。

## 使用現場注射定義 {#section_C1BBF19DE8EF4A6F8CC3ED691F3953A9}

注射定義有以下形式：

```
append|replace field [regexp] URL value
```

`append|replace`, `field`, `URL`。 而項 `value` 目則為強制性。 每行輸入一個注入定義。 以下範例包含6種不同的注射定義。

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
   <td colname="col1"> <p> <span class="codeph"> append|replace </span> </p> </td> 
   <td colname="col2"> <p>選擇「附加」以新增注入定義的值(「Adobe:聯絡我們」或「立即開售！」 中)轉換為現有欄位的內容。 選擇「取代」，以定義的值覆寫現有欄位內容。 如果欄位目前沒有內容，則會自動新增定義的值，而不論使用哪個選項（附加或取代）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> 欄位 </span> </p> </td> 
   <td colname="col2"> <p>欄位名稱為必填。 以下是十個可使用的預先定義欄位名稱： </p> <p> 
     <ul id="ul_B9336FA53023474EAEE399116E7FC972"> 
      <li id="li_C621203DCD2B4875A54A1DD19F0B5B90"> <span class="codeph"> alt </span> </li> 
      <li id="li_9217E6A037254BEDBB8D006B70D7670D"> <span class="codeph"> body </span> </li> 
      <li id="li_DCDC50F93F224F02897419B745E09399"> <span class="codeph"> charset </span> </li> 
      <li id="li_D95668236B6547B99966668C82B302AB"> <span class="codeph"> 日期 </span> </li> 
      <li id="li_D2071681274345C3B97E9ADA6D223271"> <span class="codeph"> desc </span> </li> 
      <li id="li_26683A9209454A438D811187FB929482"> <span class="codeph"> 鍵 </span> </li> 
      <li id="li_A5E19F81B872402CA62B5AB9497E030D"> <span class="codeph"> language </span> </li> 
      <li id="li_FD0B1CD9E6304B18B9D7F57E61015107"> <span class="codeph"> 目標 </span> </li> 
      <li id="li_400D7E3F3E9B47EFB2FF5C0D278DB573"> <span class="codeph"> 標題 </span> </li> 
      <li id="li_449BCBEE4F64424BB69F780C10F5956C"> <span class="codeph"> url </span> </li> 
     </ul> </p> <p>每個欄位名稱都與您網站頁面上的元素相對應。 例如，如果您指定欄 <span class="codeph"> 位名 </span> 稱desc，則可以將插入定義值新增至與您網站頁面上的「中繼」標籤說明相對應的欄位。 </p> <p>如果頁面上沒有描述Meta標籤，則定義的內容會為您建立標籤。 desc植入中指 <span class="codeph"> 定 </span> 的內容會像硬式編碼中繼描述內容一樣顯示在結果頁面上。 </p> <p>您也可以使用相同的欄位名稱建立多個定義。 例如，假設您有下列注射： </p> <p> <code> replace&nbsp; <b>title</b>&nbsp;https://www.mysite.com/&nbsp;Welcome&nbsp;to&nbsp;My&nbsp;Site </code> </p> <p> <code> replace&nbsp; <b>title</b>&nbsp;https://www.mysite.com/company/*.html&nbsp;My&nbsp;Site:&nbsp;Contact </code> </p> <p>上述範例中的所有網站頁面都會收到一個插入標題「歡迎使用我的網站」。 「/company/」資料夾中的頁面會插入新標題「我的網站：聯絡我們」，以取代上一個。 </p> <p>注意，注入按注入在「現場注入定義」( <span class="wintitle"> Field Injection Definitions)文本框中的顯示順 </span> 序應用。 如果相同欄位（本範例中的「標題」）在相同位置的頁面上定義多次，則較晚的定義優先。 </p> <p> <span class="codeph"> [regexp] </span> -可選 如果您選擇使用regexp選 <span class="codeph"> 項， </span> 則定義的URL會視為規則運算式。 </p> <p>請參閱 <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> 規則運算式 </a>。 </p> <p>以下定義： </p> <p> <code> replace&nbsp;target&nbsp; <b>regexp&amp;nbsp;^.*/products/.*\.html$</b>&nbsp;Important&nbsp;information </code> </p> <p> 「重要資訊」會插入與規則運算式^相符之所有頁面的「目標」欄 <span class="codeph"> 位。*/products/.*\.html$ </span>. </p> <p>因此，您有下列功能： </p> <p> <code> https://www.mydomain.com/products/page1.html 
      &nbsp;&nbsp;&nbsp;&nbsp;(Will&nbsp;receive&nbsp;"target"&nbsp;content) </code> </p> <p> <code> https://www.mydomain.com/product/oldstuff.html 
      &nbsp;&nbsp;&nbsp;&nbsp;(Will&nbsp;not&nbsp;receive&nbsp;"target"&nbsp;content) </code> </p> <p>在下列範例中： </p> <p> <code> append&amp;nbsp;title&amp;nbsp;regexp&amp;nbsp;^.*\.pdf$&amp;nbsp;Millennium&amp;nbsp;Science </code> </p> <p>此注入會附加"Millennium Science"至所有以"。pdf"副檔名結尾之頁面的"title"內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> URL </span> </p> </td> 
   <td colname="col2"> <p>需要URL，並指定要插入哪些檔案。 </p> <p>URL是下列任一項： </p> <p> 
     <ul id="ul_C5C74F6D5EA943B293742989EB822751"> 
      <li id="li_382392DB778D4E14BFFC96D35A861951"> 完整路徑，如https://www.mydomain.com/products.html </li> 
      <li id="li_EA2BD0FB66A44CD0844613316F6174D4"> 部分路徑，如https://www.mydomain.com/products </li> 
      <li id="li_D5E0D6D897C8493ABBFC65517CD4A7DB"> 使用萬用字元的URL，如https://www.mydomain.com/*.html </li> 
     </ul> </p> <p>URL值中不得含有任何空格字元。 如果使 <span class="codeph"> 用regexp </span> 選項，URL會被視為規則運算式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> value </span> </p> </td> 
   <td colname="col2"> <p>值是必填項，用來取代或新增至現有欄位內容。 您可以為相同欄位名稱指定多個值。 例如: </p> <p>附加 <b>密鑰</b> https://www.mysite.com/travel/ <b>summer</b>、 <b>beach</b>、 <b>sand</b> </p> <p>附加 <b>金鑰</b> https://www.mysite.com/travel/fare/*.html <b>cempents</b> </p> <p>在上例中，"summer, beach, sand"一詞會附加至"/travel/"目錄中所有頁面的"keys"欄位。 "/travel/fare/"目錄中所有頁面上的"keys"欄位也會附加"cheex tickets"一詞。 </p> </td> 
  </tr> 
 </tbody> 
</table>

另請參閱 [選擇要編目和索引的內容類型](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8)。

## 新增欄位插入定義 {#task_E86566FA1FF74CF68115C0ADA05172AE}

您可以使 [!DNL Injections] 用將內容插入網頁，而不需自行編輯頁面。

您可選擇在頁 **[!UICONTROL Test]** 面上使 [!DNL Injections] 用。 您可輸入測試欄位名稱（例如「title」或「body」）、原始欄位值（例如「Home Page」），以及您網站的測試URL。 結果值將顯示供參考。 測試期間不會變更目前的值。

**若要新增欄位插入定義**

1. 在產品功能表上，按一下 **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]**。
1. （可選）在頁 [!DNL Injections] 面的區 [!DNL Test Field Injections] 域中，輸入測試欄位、測試原始值和測試URL，然後按一下 **[!UICONTROL Test]**。
1. 在欄位 [!DNL Field Injection Definitions] 中，每行輸入一個注射定義。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）執行下列任一項作業：

   * 按一 **[!UICONTROL History]** 下以回復您所做的任何變更。

      請參 [閱使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。

## 關於屬性載入器 {#concept_9EF38E98811B42CDA41996432B9AD209}

使用 [!DNL Attribute Loader] 定義其他輸入來源，以增加從網站編目的資料。

>[!NOTE]
>
>若要使用「屬性載入器」，您可能需要由Adobe帳戶代表或Adobe支援在您的帳戶中啟用它。

您可以使用資料饋送輸入來源來存取儲存在與網站上通常發現的格式不同的表單中的內容。 您可使用其中一種可用的編目方法來完成此作業。 然後，這些來源的資料可以注入到已編目內容的資料中。

將「屬性載入器」定義新增至頁面後， [!DNL Staged Attribute Loader Definitions] 您可以變更「名稱」值和「類型」值以外的任何組態設定

該頁 [!DNL Attribute Loader] 面顯示以下資訊：

* 已配置並添加的已定義屬性載入器配置的名稱。
* 已添加的每個連接器的以下資料源類型之一：

   * **文字** -簡單的「平面」檔案、逗號分隔、定位點分隔或其他一致分隔格式。
   * **動態消息** - XML動態消息。

* 是否為下次編目和索引啟用配置。
* 資料源的地址。

另請參 [閱屬性插入程式對文字和動態消息的運作方式……](../c-about-settings-menu/c-about-metadata-menu.md#section_E059A33D61EE4DB0972A37B8A35E9E16)

另請參閱 [關於配置多屬性載入器](../c-about-settings-menu/c-about-metadata-menu.md#section_4CC49C74EF294608A184E233F215ADFF)

另請參 [閱關於新增屬性時預覽的使用……](../c-about-settings-menu/c-about-metadata-menu.md#section_E9CAB000A94C4D9189786C1EDB1CDB46)

## 屬性插入程式如何在屬性載入器中處理文字和饋送組態 {#section_E059A33D61EE4DB0972A37B8A35E9E16}

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
   <td colname="col3"> <p>對於文字和動態消息設定，它是簡單的檔案下載。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>將下載的資料來源劃分為個別的偽檔案。 </p> </td> 
   <td colname="col3"> <p>對於 <span class="uicontrol"> 文 </span>字，每行以新行分隔的文字都對應於個別檔案，並使用指定的分隔字元（例如逗號或制表符）進行剖析。 </p> <p>對於 <span class="uicontrol"> 動 </span>態消息，每份檔案的資料會使用下列格式的規則運算式模式擷取： </p> <p> <code class="syntax js"> &lt;${Itemtag}&gt;(.*?)&lt;/${Itemtag}&gt; </code> </p> <p>使用「屬 <span class="uicontrol"> 性載入 </span> 器添加」頁 <span class="wintitle"></span> 上的「映射」，建立資料的快取副本，然後為Crawler建立連結清單。 該資料儲存在本地快取中，並填入配置的欄位。 </p> <p>將解析的資料寫入本地快取。 </p> <p>此快取稍後會讀取，以建立Crawler所需的簡單HTML檔案。 例如， </p> <p> <code class="syntax html"> &lt;html&gt;&lt;head&gt; 
      &lt;title&gt;{title}&lt;/title&gt; 
      &lt;meta&nbsp;name="{field}"&nbsp;content="{data}"&nbsp;/&gt; 
      ... 
      &lt;/head&gt;&lt;body&gt; 
      {body} 
      &lt;/body&gt;&lt;/html&gt; </code> </p> <p>&lt;title&gt; <span class="codeph"> 元素 </span> 僅在映射存在於「標題」中繼資料欄位時產生。 同樣地， <span class="codeph"> &lt;body&gt;元 </span> 素只會在映射存在於「Body」中繼資料欄位時產生。 </p> <p> <b>重要</b>:不支援為預先定義的URL meta標籤指派值。 </p> <p>對於所有其他映射， <span class="codeph"> 會為 </span> 在原始文檔中找到資料的每個欄位生成&lt;meta&gt;標籤。 </p> <p>每個文檔的欄位將添加到快取中。 對於寫入到快取的每個文檔，也會生成連結，如以下示例所示： </p> <p> <code class="syntax html"> &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      .... </code> </p> <p>配置的映射必須有一個欄位被標識為主鍵。 此映射構成從快取中讀取資料時使用的密鑰。 </p> <p>Crawler可識別URL <span class="codeph"> 索引： </span> 方案首碼，接著可存取本機快取資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>編目快取的檔案集。 </p> </td> 
   <td colname="col3"> <p>該 <span class="codeph"> 指數： </span> 連結將添加到Crawler的待處理清單中，並以正常的編目序列進行處理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>處理每份檔案。 </p> </td> 
   <td colname="col3"> <p>每個連結的索引鍵值都對應快取中的項目，因此編目每個連結會導致該檔案的資料從快取中擷取。 然後，它會「組合」到HTML影像中，並加以處理並新增至索引。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 關於配置多個屬性載入器 {#section_4CC49C74EF294608A184E233F215ADFF}

您可以為任何帳戶定義多個屬性載入器組態。

新增屬性載入器時，您可選擇使用 **[!UICONTROL Setup Maps]** 該功能下載資料來源的範例。 系統會檢查資料是否適合。

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
   <td colname="col2"> <p>先試用標籤，再使用垂直條( <span class="codeph"> | </span>)，最後加上逗號( <span class="codeph"> 、 </span>)。 如果您在按一下「設定對應」之前已指 <span class="uicontrol"> 定分隔 </span>字元值，則會改用該值。 </p> <p>最佳配合方案會在Map欄位中填入適當的Tag和Field值的猜測。 另外，顯示所解析資料的採樣。 如果您知道檔 <span class="uicontrol"> 案包含頁首行， </span> 請務必在第一行中選取頁首。 設定函式使用此資訊更好地標識生成的映射條目。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>資訊源 </p> </td> 
   <td colname="col2"> <p>下載資料來源並執行簡單的XML剖析。 </p> <p>產生的XPath識別碼會顯示在Map表格的Tag列中，而欄位中也會顯示類似的值。 這些行僅標識可用資料，不生成更複雜的XPath定義。 但是，它仍然很有幫助，因為它描述了XML資料並標識了Itemtag。 </p> <p> <p>注意： 「設定對應」功能會下載整個XML來源以執行其分析。 如果檔案很大，此操作可能超時。 </p> </p> <p>成功後，此函式將標識所有可能的XPath項，其中許多項不適合使用。 請務必檢查產生的地圖定義，並移除您不需要或想要的地圖定義。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>「設定映射」功能可能無法用於大型XML資料集，因為其檔案解析器嘗試將整個檔案讀入記憶體。 因此，您可能會遇到記憶體不足的狀況。 但是，當在編製索引時處理同一文檔時，它不會讀入記憶體。 相反，大型檔案會「在外出時」進行處理，不會先完全讀入記憶體。

## 關於在添加屬性載入器時使用預覽 {#section_E9CAB000A94C4D9189786C1EDB1CDB46}

屬性載入器資料會在索引操作之前載入。

新增「屬性載入器」時，您可選擇使用該功 **[!UICONTROL Preview]** 能來驗證資料，就像儲存資料一樣。 它會針對設定執行測試，但不會將設定儲存至帳戶。 測試訪問已配置的資料源。 但是，它將下載快取寫入臨時位置；它與索引爬蟲所使用的主快取資料夾不衝突。

預覽僅處理由 **Acct:IndexConnector-Preview-Max-Documents控制的5個文檔的預設處理**。 預覽的文檔以源格式顯示，如同向索引爬蟲顯示。 顯示畫麵類似網頁瀏覽器中的「檢視來源」功能。 您可以使用標準導覽連結，在預覽集中導覽檔案。

預覽不支援XML設定，因為此類檔案會直接處理，而不會下載至快取。

## 新增屬性載入器定義 {#task_A735E5EF763343A9B675E1A3B09AFDBC}

每個「屬性載入器」配置都定義資料來源和映射，以將為該來源定義的資料項目與索引中的中繼資料欄位建立關聯。

>[!NOTE]
>
>若要使用「屬性載入器」，您可能需要由Adobe帳戶代表或Adobe支援在您的帳戶中啟用它。

在新定義和已啟用定義的效果顯現給客戶之前，請重建您的網站索引。

**若要新增屬性載入器定義**

1. 在產品功能表上，按一下 **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**。
1. 在頁面上 [!DNL Stage Attribute Loader Definitions] ，按一下 **[!UICONTROL Add New Attribute Loader]**。
1. 在頁面 [!DNL Attribute Loader Add] 上，設定您想要的設定選項。 可用的選項取決於您選 **[!UICONTROL Type]** 擇的選項。

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
      <td colname="col2"> <p>屬性載入器組態的唯一名稱。 您可以使用英數字元。 也允許使用字元"_"和"-"。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>類型 </p> </td> 
      <td colname="col2"> <p>資料來源。 您選擇的資料來源類型會影響「屬性載入器新增」頁面上可用的 <span class="wintitle"> 產生選 </span> 項。 您可以從下列選項中選擇： </p> <p> 
      <ul id="ul_1ADC3DFBC929467385F7465BE8E13635"> 
      <li id="li_64FCD749F55442BAB316BD474128D4F9"> <span class="uicontrol"> 文字 </span> <p>簡單的平面文字檔案、逗號分隔、定位點分隔或其他一致分隔格式。 每行以新行分隔的文本都對應於單個文檔，並使用指定的分隔符進行解析。 </p> <p>您可以將每個值或欄對應至由欄號引用的中繼資料欄位，從1(1)開始。 </p> </li> 
      <li id="li_2A4F16CE6DCE4114B7F8E4FE156252BB"> <span class="uicontrol"> 資訊源 </span> <p>下載包含多列資訊的主要XML檔案。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>資料來源類型：文字</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>已啟用 </p> </td> 
      <td colname="col2"> <p>將配置「開啟」以便使用。 或者，您可以關閉配置，以防止其被使用。 </p> <p> <b>注意</b>:會忽略停用的屬性載入器組態。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>主機地址 </p> </td> 
      <td colname="col2"> <p>指定資料所在的伺服器主機的地址。 </p> <p>如果需要，可以指定資料源文檔的完整URI（統一資源標識符）路徑，如以下示例所示： </p> <p> <code otherprops="syntax html"> https://www.somewhere.com/some_path/some_file.tsv </code> </p> <p>或  </p> <p> <code class="syntax html"> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.csv </code> </p> <p>URI被劃分為「主機地址」、「檔案路徑」、「協定」和（可選）「用戶名」和「密碼」欄位的相應條目 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>檔案路徑 </p> </td> 
      <td colname="col2"> <p>指定簡單平面文本檔案、逗號分隔、制表符分隔或其他一致分隔格式檔案的路徑。 </p> <p>路徑相對於主機地址的根目錄。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>通訊協定 </p> </td> 
      <td colname="col2"> <p>指定用於訪問檔案的協定。 您可以從下列選項中選擇： </p> <p> 
      <ul id="ul_F6BC10FD51CA4A1D855B2B3212838A9C"> 
      <li id="li_79FB7DC65E774ABBB23E57BF98AD9738"> HTTP <p>如有必要，您可以輸入適當的驗證憑證來存取HTTP伺服器。 </p> </li> 
      <li id="li_BAA9AD5E4B014E09B3A66C94022B7225"> HTTPS <p>如有必要，您可以輸入適當的驗證憑證以存取HTTPS伺服器。 </p> </li> 
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
      <td colname="col1"> <p>重試次數 </p> </td> 
      <td colname="col2"> <p>指定失敗的FTP、SFTP、HTTP或HTTPS連線的重試次數上限。 此值必須介於0和10之間。 </p> <p>值為零(0)將阻止重試嘗試。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>編碼 </p> </td> 
      <td colname="col2"> <p>指定在指定的資料源檔案中使用的字元編碼系統。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>分隔字元 </p> </td> 
      <td colname="col2"> <p>指定要用來描述指定資料源檔案中每個欄位的字元。 </p> <p>逗號字元( <span class="codeph"> , </span>)是分隔字元的範例。 逗號用作欄位分隔字元，可協助您在指定的資料來源檔案中分隔資料欄位。 </p> <p>選擇 <span class="uicontrol"> 標籤？ </span> 以使用水準標籤字元作為分隔字元。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>第一列的標題 </p> </td> 
      <td colname="col2"> <p>指出資料來源檔案中的第一列僅包含標題資訊，而非資料。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>過時天數 </p> </td> 
      <td colname="col2"> <p>設定「屬性載入器」資料的下載之間的最小間隔。 在下載刷新頻率間隔內發生的索引觸發下載將被忽略。 當您將此值設為預設值1時，屬性載入器資料在24小時內不會下載多次。 在下載刷新頻率間隔內發生的所有搜索索引都使用上次下載的資料集。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>地圖 </p> </td> 
      <td colname="col2"> <p>使用列號指定列到元資料映射。 </p> <p> 
      <ul id="ul_981AE2C6D30443BDBFC6575D413732A2"> 
      <li id="li_A42CB9DFFF8C45A7BAC2D471FE96CEBE"> <span class="uicontrol"> 欄 </span> <p> 指定列號，第一列為1(1)。 要為每個列添加新的映射行，請在「操作」( <span class="wintitle"> Action </span>)下單 <span class="uicontrol"> 擊+ </span>。 </p> <p>您不需要參考資料來源中的每一欄。 您可以選擇跳過值。 </p> </li> 
      <li id="li_26E8C9554A5D4BC5A5073D6385E3626F"> <span class="uicontrol"> 欄位 </span> <p>定義用於每個生成的&lt;meta&gt;標籤的名稱屬性值。 </p> </li> 
      <li id="li_5DFA514B7F9549B98D6CBC095A66033C"> <span class="uicontrol"> 中繼資料? </span> <p>使「 <span class="uicontrol"> 欄位 </span> 」成為下拉式清單，您可從中選取目前帳戶的已定義中繼資料欄位。 </p> <p>視需 <span class="uicontrol"> 要 </span> ，欄位值可以是未定義的中繼資料欄位。 未定義的中繼資料欄位有時對建立篩選指令檔所使用的 <span class="wintitle"> 內容很有用 </span>。 </p> <p>請參閱 <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> 關於篩選指令 </a>碼。 </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892C95"> <span class="uicontrol"> 主鍵？ </span> <p>只有一個欄位被標識為主鍵。 此欄位將用作「外鍵」，以將屬性載入器資料與索引中的相應文檔匹配。 </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892D96"> <span class="uicontrol"> 刪除HTML? </span> <p>勾選此選項時，會移除在此欄位資料中找到的任何HTML標籤。 </p> </li> 
      <li id="li_359D2902859B4C5BADB0BA26F0BA4DC0"> <span class="uicontrol"> 動作 </span> <p>可讓您新增列至地圖或從地圖移除列。 列的順序不重要。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>資料來源類型：動態消息</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>已啟用 </p> </td> 
      <td colname="col2"> <p>將配置「開啟」以便使用。 或者，您可以關閉配置，以防止其被使用。 </p> <p> <b>注意</b>:會忽略停用的屬性載入器組態。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>主機地址 </p> </td> 
      <td colname="col2"> <p>指定資料所在的伺服器主機的地址。 </p> <p>如果需要，可以指定資料源文檔的完整URI（統一資源標識符）路徑，如以下示例所示： </p> <p> <code class="syntax html"> https://www.somewhere.com/some_path/some_file.tsv </code> </p> <p>或  </p> <p> <code class="syntax html"> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.csv </code> </p> <p>URI被劃分為「主機地址」、「檔案路徑」、「協定」和（可選）「用戶名」和「密碼」欄位的相應條目。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>檔案路徑 </p> </td> 
      <td colname="col2"> <p>指定包含多個「行」資訊的主XML文檔的路徑。 </p> <p>路徑相對於主機地址的根目錄。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>通訊協定 </p> </td> 
      <td colname="col2"> <p>指定用於訪問檔案的協定。 您可以從下列選項中選擇： </p> <p> 
      <ul id="ul_976A34FD14A841F2B610C1C0CCBB82B9"> 
      <li id="li_05BBA0F670F14431A89AE4178F1A6F94"> HTTP <p>如有必要，您可以輸入適當的驗證憑證來存取HTTP伺服器。 </p> </li> 
      <li id="li_100446691F304572B8FC3F083F86A2CB"> HTTPS <p>如有必要，您可以輸入適當的驗證憑證以存取HTTPS伺服器。 </p> </li> 
      <li id="li_027088A8E30444DAA8CCCC5B0BAA74C1"> FTP <p>您必須輸入正確的驗證憑證才能存取FTP伺服器。 </p> </li> 
      <li id="li_DCEF9D5C99354990B03E29083C2ED8DC"> SFTP <p>您必須輸入正確的驗證憑證才能存取SFTP伺服器。 </p> </li> 
      <li id="li_44E34FF2AB0D429EB3408106E6FCF780"> 檔案 </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Itemtag </p> </td> 
      <td colname="col2"> <p>標識可用於標識指定資料源檔案中各個XML行的XML元素。 </p> <p>例如，在Adobe XML檔案的下列動態消息片段中，Itemtag值是記 <span class="codeph"> 錄 </span>: </p> <p> <code class="syntax xml"> &lt;?xml&nbsp;version="1.0"&nbsp;encoding="utf-8"?&gt; 
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
      <td colname="col2"> <p>指定中繼資料欄位，其值會用作「屬性載入器」設定資料的查詢「索引鍵」。 如果未選擇任何值(<b>—無—</b>)，則此配置的資料不可用於排名計算(<b>規則</b> &gt; <b>排名規則</b> &gt;編 <b></b>輯規則)。 當您選取值時，此欄位的值會用於使用此組態資料交叉參考網站搜尋／銷售檔案。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>過時天數 </p> </td> 
      <td colname="col2"> <p>設定「屬性載入器」資料的下載之間的最小間隔。 在下載刷新頻率間隔內發生的索引觸發下載將被忽略。 當您將此值設為預設值1時，屬性載入器資料在24小時內不會下載多次。 在下載刷新頻率間隔內發生的所有搜索索引都使用上次下載的資料集。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>地圖 </p> </td> 
      <td colname="col2"> <p>可讓您使用XPath運算式指定XML元素對中繼資料的映射。 </p> <p> 
      <ul id="ul_604108C0277C4892AE8A40CA39889ABD"> 
      <li id="li_0AF92270AE9F4BA8B2C7EE41FABC0F34"> <span class="uicontrol"> 標記 </span> <p>指定已解析XML資料的XPath表示法。 使用上述Adobe XML檔案範例，在選項Itemtag下，可使用下列語法來對應它： </p> <p> <code class="syntax xml"> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
        /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>上述語法的轉譯如下： </p> <p> 
        <ul id="ul_6400EBD08D424EADA1612FE4F7EFB640"> 
        <li id="li_9958F9B40D42434195597DBA9F2AF28F"> <code class="syntax xml"> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p>記錄 <span class="codeph"> 元素 </span> 的顯示url屬性 <span class="codeph"> 會映射 </span> 至中繼資料欄位 <span class="codeph"> page-url </span>。 </p> </li> 
        <li id="li_759013EA02CD48BE971A55B0A6A11424"> <code class="syntax xml"> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>該內 <span class="codeph"> 容包含在元資料元 </span> 素內的任何元元素的內容屬性，包含 <span class="codeph"> 記錄元素，其名稱為元資料欄位標題的 </span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span>，其中記錄元素的名稱為元資料欄位標題的映射。 </p> </li> 
        <li id="li_E741CA59197D462EB2946EDE874AFDC8"> <code class="syntax xml"> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>該內 <span class="codeph"> 容包含在元資料元 </span> 素內的任何元元素的內容，該元資料元素中包含 <span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span>記錄元素，其名稱屬性是描述，其映射是描述元資料欄位的映射，該元資料欄位是描述元資料屬性的。 </p> </li> 
        <li id="li_E35EAE3D284D46D485D9064D7BB6AB13"> <code class="syntax xml"> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>所 <span class="codeph"> 述內容屬性包含在元資料元 </span> 素中的任何元元素的內容，所述元資料元素的名稱包含在 <span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span>記錄元素中，所述記錄元素的名稱是所述元資料域主體的映射的映射。 </p> </li> 
        </ul> </p> <p>XPath是一個相對複雜的符號。 如需詳細資訊，請造訪下列位置： </p> <p>請參閱 <a href="https://www.w3schools.com/xpath/" scope="external" format="html"> https://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_8147075D7ACD4811A7ED335F23FE62A6"> <span class="uicontrol"> 欄位 </span> <p>定義用於每個生成的&lt;meta&gt;標籤的 <span class="codeph"> 名稱屬 </span> 性值。 </p> </li> 
      <li id="li_2380199D63BF425A919606D8232FA6E2"> <span class="uicontrol"> 中繼資料? </span> <p>使「 <span class="uicontrol"> 欄位 </span> 」成為下拉式清單，您可從中選取目前帳戶的已定義中繼資料欄位。 </p> <p>視需 <span class="uicontrol"> 要 </span> ，欄位值可以是未定義的中繼資料欄位。 未定義的中繼資料欄位有時對建立篩選指令檔所使用的 <span class="wintitle"> 內容很有用 </span>。 </p> <p>請參閱 <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> 關於篩選指令 </a>碼。 </p> <p>當屬性載入器在任何地圖欄位上處理具有多次點擊的XML檔案時，會將多個值串連在產生的快取檔案中的單一值中。 依預設，這些值會使用逗號分隔字元來組合。 不過，假設對應的欄位 <span class="wintitle"> 值 </span> 是已定義的中繼資料欄位。 此外，該欄位還設定了「允 <span class="wintitle"> 許清單」 </span> 屬性。 在這種情況下，欄位的「清單分隔符」值（定義的第一個分隔符）將用於級聯。 </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC70E"> <span class="uicontrol"> 主鍵？ </span> <p>只有一個欄位被標識為主鍵。 此欄位將用作「外鍵」，以將屬性載入器資料與索引中的相應文檔匹配。 </p> </li> 
      <li id="li_80D6AF130FCE40AC972FE4B605B86BF6"> <span class="uicontrol"> 刪除HTML? </span> <p>勾選此選項時，會移除在此欄位資料中找到的任何HTML標籤。 </p> </li> 
      <li id="li_D40E2F9AD8AD49FC9AC4B8C75BA31E28"> <span class="uicontrol"> 動作 </span> <p>可讓您新增列至地圖或從地圖移除列。 列的順序不重要。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. （可選）按一 **[!UICONTROL Setup Maps]** 下以下載資料來源的範例。 系統會檢查資料是否適合。
1. 按一 **[!UICONTROL Add]** 下，將設定新增至頁 [!DNL Attribute Loader Definitions] 面。
1. 在頁面上 [!DNL Attribute Loader Definitions] ，按一下 **[!UICONTROL rebuild your staged site index]**。
1. （可選）在頁 [!DNL Attribute Loader Definitions] 面上，執行下列任一項作業：

   * 按一 **[!UICONTROL History]** 下以回復您所做的任何變更。

      請參 [閱使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。

## 編輯屬性載入器定義 {#task_AA2D1B2BCAFA44A6A0C59A0318274E80}

您可以編輯已定義的現有屬性載入器。

>[!NOTE]
>
>若要使用「屬性載入器」，您可能需要由Adobe帳戶代表或Adobe支援在您的帳戶中啟用它。

並非所有屬性載入器選項都可供您變更，例如下拉式清單中的「屬性載入器名稱」 [!DNL Type] 或「類型」。

**若要編輯屬性載入器定義**

1. 在產品功能表上，按一下 **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**。
1. 在頁面 [!DNL Attribute Loader] 上，在欄標題 [!DNL Actions] 下，按一下「屬性載入器 **[!UICONTROL Edit]** 」定義名稱，您要變更其設定。
1. 在頁面 [!DNL Attribute Loader Edit] 上，設定您想要的選項。

   請參閱「新增屬性載入器 [定義」下的選項表](../c-about-settings-menu/c-about-metadata-menu.md#task_A735E5EF763343A9B675E1A3B09AFDBC)。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （選用）在頁 [!DNL Attribute Loader Definitions] 面上按一下 **[!UICONTROL rebuild your staged site index]**。
1. （可選）在頁 [!DNL Attribute Loader Definitions] 面上，執行下列任一項作業：

   * 按一 **[!UICONTROL History]** 下以回復您所做的任何變更。

      請參 [閱使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。

## 複製屬性載入器定義 {#task_9B40D5ECFC81411E9480F62A0FD5F2E0}

您可以複製現有的「屬性載入器」定義，以用作要建立的新「屬性載入器」的基礎。

>[!NOTE]
>
>若要使用「屬性載入器」，您可能需要由Adobe帳戶代表或Adobe支援在您的帳戶中啟用它。

複製「屬性載入器」定義時，預設會停用複製的定義。 若要啟用或「開啟」定義，您必須從頁面中編輯定義， [!DNL Attribute Loader Edit] 然後選取 **[!UICONTROL Enable]**。

請參 [閱編輯屬性載入器定義](../c-about-settings-menu/c-about-metadata-menu.md#task_AA2D1B2BCAFA44A6A0C59A0318274E80)。

**複製屬性載入器定義**

1. 在產品功能表上，按一下 **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**。
1. 在頁面 [!DNL Attribute Loader] 上，在欄標題 [!DNL Actions] 下，按一下以取 **[!UICONTROL Copy]** 得您要複製其設定的屬性載入器定義名稱。
1. 在頁面 [!DNL Attribute Loader Copy] 上，輸入定義的新名稱。
1. 按一下 **[!UICONTROL Copy]**.
1. （可選）在頁 [!DNL Attribute Loader Definitions] 面上，執行下列任一項作業：

   * 按一 **[!UICONTROL History]** 下以回復您所做的任何變更。

      請參 [閱使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。

## 重新命名屬性載入器定義 {#task_58D5DFD7EBC04111BCB91118E4440DB4}

您可以更改現有屬性載入器定義的名稱。

>[!NOTE]
>
>若要使用「屬性載入器」，您可能需要由Adobe帳戶代表或Adobe支援在您的帳戶中啟用它。

**要更名屬性載入器定義**

1. 在產品功能表上，按一下 **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**。
1. 在頁面 [!DNL Attribute Loader] 上，在欄標題 [!DNL Actions] 下，按一下要 **[!UICONTROL Rename]** 變更的「屬性載入器」定義名稱。
1. 在頁 [!DNL Attribute Loader Rename] 面上，在欄位中輸入定義的新名 [!DNL Name] 稱。
1. 按一下 **[!UICONTROL Rename]**.
1. （可選）在頁 [!DNL Attribute Loader Definitions] 面上，執行下列任一項作業：

   * 按一 **[!UICONTROL History]** 下以回復您所做的任何變更。

      請參 [閱使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。

## 載入屬性載入器資料 {#task_2F3C55189B0A4049AB2113F2291CC181}

您可以將設定的「屬性載入器」資料下載至網站搜尋／銷售。

此頁 [!DNL Data Load] 顯示有關上次屬性載入程式資料載入操作狀態的以下資訊：

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
   <td colname="col2"> <p>指出上次資料載入嘗試的成功或失敗。 或者，它顯示已在進行中的資料載入操作的狀態。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>開始時間 </p> </td> 
   <td colname="col2"> <p>顯示上次資料載入操作開始的日期和時間。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>停止時間 </p> </td> 
   <td colname="col2"> <p>顯示上次資料載入操作的完成日期和時間。 或者，它表示當前資料載入操作仍在進行中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**要載入屬性載入器資料**

1. 在產品功能表上，按一下 **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**。
1. 在頁面上 [!DNL Attribute Loader Definitions] ，按一下 **[!UICONTROL Load Attribute Loader Data]**。
1. 在頁面 **[!UICONTROL Attribute Loader Data Load]** 上，執行下列其中一項作業：

   * 按一下 **[!UICONTROL Start Load]** 以啟動載入操作。

      在資料載入操作期間，**Progress行提供** 有關其進度的資訊。

   * 按一下 **[!UICONTROL Stop Load]** 以停止載入操作。

1. 按一 **[!UICONTROL Close]** 下以返回頁 [!DNL Attribute Loader Definitions] 面。

## 預覽屬性載入器資料 {#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0}

您可以使用「預覽」來檢視最近載入的屬性載入器資料。

表格中的「行」列顯示每行資料的編號，指示「屬性載入器」值的載入原始順序。

其餘的欄會顯示與每個項目相關聯的值。

如果表為空，表示您尚未載入任何屬性載入器資料。 您可以關閉頁 [!DNL Attribute Loader Data Preview] 面，然後載入「屬性載入器」資料。

請參閱 [載入屬性載入器資料](../c-about-settings-menu/c-about-metadata-menu.md#task_2F3C55189B0A4049AB2113F2291CC181)。

**若要預覽屬性載入器資料**

1. 在產品功能表上，按一下 **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**。
1. 在頁面 [!DNL Attribute Loader Definitions] 的欄下，按一 [!DNL Actions] 下您要 **[!UICONTROL Preview]** 檢視其下載資料的設定。
1. 在頁面 [!DNL Attribute Loader Data Preview] 上，使用頁面頂端和底部的導覽和檢視選項來檢視資料。

   按一下表格中的任何欄標題，以遞增或遞減順序排序資料。
1. 執行下列任一操作：

   * 按一 **[!UICONTROL Download to Desktop]** 下以下載並將表格儲存為。xlt檔案。
   * 當您完成預覽「屬性載入器」資料並返回先前檢視的頁面時，請關閉頁面。

## 檢視屬性載入器定義的設定 {#task_EA99A9694FE948ADA82C1DBA0667851B}

您可以查看現有屬性載入器定義的配置設定。

在將屬性載入器定義新增至頁面後，您 [!DNL Attribute Loader Definitions] 便無法變更其「類型」設定。 您必須先刪除定義，然後新增定義。

>[!NOTE]
>
>若要使用「屬性載入器」，您可能需要由Adobe帳戶代表或Adobe支援在您的帳戶中啟用它。

**查看屬性載入器定義的設定**

1. 在產品功能表上，按一下 **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**。
1. 在頁面 [!DNL Attribute Loader] 的欄標題下，按一 [!DNL Actions] 下「屬性載入器」 **[!UICONTROL Edit]** 定義名稱，您可檢視或編輯其設定。

## 從最近的「屬性載入器」資料載入中檢視記錄檔 {#task_9C7D6E34BB6C4A40B7CA3EE36ACB0837}

您可以使用 [!DNL View Log] 檢查最新下載程式的屬性載入器資料記錄檔。 您也可以使用記錄檢視來監視執行中的下載。

請參閱 [載入屬性載入器資料](../c-about-settings-menu/c-about-metadata-menu.md#task_2F3C55189B0A4049AB2113F2291CC181)。

**從最近的「屬性載入器」資料載入中檢視記錄檔**

1. 在產品功能表上，按一下 **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**。
1. 在頁面上 [!DNL Attribute Loader Definitions] ，按一下 **[!UICONTROL View Log]**。 記錄頁、
1. 在頁面 [!DNL Attribute Loader Data Log] 上，使用頁面頂端和底部的導覽和檢視選項來檢視記錄檔資訊。
1. 完成後，關閉頁面以返回頁 [!DNL Attribute Loader Definitions] 面。

## 刪除屬性載入器定義 {#task_E8980F66888B476E98C228C1D307EDF8}

您可以刪除不再需要或使用的現有屬性載入器定義。

>[!NOTE]
>
>若要使用「屬性載入器」，您可能需要由Adobe帳戶代表或Adobe支援在您的帳戶中啟用它。

**刪除屬性載入器定義**

1. 在產品功能表上，按一下 **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**。
1. 在頁面 [!DNL Attribute Loader Definitions] 上，在欄標題 [!DNL Actions] 下，按一下 **[!UICONTROL Delete]** 您要移除的「屬性載入器」定義名稱。
1. 在頁面上 [!DNL Attribute Loader Delete] ，按一下 **[!UICONTROL Delete]**。
