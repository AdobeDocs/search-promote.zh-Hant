---
description: 您可以使用「排名規則」，根據包含的中繼標籤內容和相關的Adobe Analytics量度，控制客戶搜尋結果的相對位置或排名。
seo-description: 您可以使用「排名規則」，根據包含的中繼標籤內容和相關的Adobe Analytics量度，控制客戶搜尋結果的相對位置或排名。
seo-title: 關於排名規則
solution: Target
subtopic: Ranking Rules
title: 關於排名規則
topic: Rules,Site search and merchandising
uuid: 21962f9a-1d9c-442f-a6c4-5f452436c640
translation-type: tm+mt
source-git-commit: 552f93f1f630c64bbe3d5c8a87c4f5895ae6868c
workflow-type: tm+mt
source-wordcount: '4647'
ht-degree: 0%

---


# 關於排名規則{#about-ranking-rules}

您可以使用「排名規則」，根據包含的中繼標籤內容和相關的Adobe Analytics量度，控制客戶搜尋結果的相對位置或排名。

## 使用排名規則{#concept_F555C076759B4E81B925441CFE707397}

您可以定義排名規則，以根據每份檔案的內容，影響檔案在搜尋結果中的相對位置。 您可以根據中繼標籤內容、Adobe Analytics量度（如果您的帳戶已設定為可與Adobe Analytics搭配使用）或Adobe Analytics HBX量度（如果您的帳戶設定為可與Adobe Analytics HBX搭配使用）來建立排名規則。

您可以設定包含具有所需特性（例如特定品牌名稱或價格）的中繼標籤的網頁，或具有所需Adobe Analytics關鍵績效指標（例如獨特檢視器）的網頁，以獲得比不具備所需特性的網頁更高的排名。 新增或編輯排名規則，然後重新建立網站索引，即可輕鬆更新「喜好」特性。

如果您定義了多個類型為「排名」的中繼標籤，則可建立個別規則集合，以用於計算各種排名欄位。 您可以新增排名規則群組，然後將其指派給其中一個已定義的排名欄位。 規則群組通常包含一或多個規則定義，但也可參照其他規則群組，因此您可以建立一或多個常用規則群組，在計算多個排名時共用這些規則群組。

請參閱[新增排名規則群組](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)。

正排名值會將搜尋結果提升到最上方；負排名值會將搜尋結果降至搜尋結果的底部。 排名值的一般範圍是1.0，這是搜尋結果中的最大升級，而-1.0是最大降級。 雖然您可以透過編輯中繼資料定義中的「排名」欄位來自訂此範圍，但通常不需要這種自訂類型。

請參閱[關於定義](../c-about-settings-menu/c-about-metadata-menu.md#concept_AE48035C210145169BE067D396975620)。

如果您在「設定>中繼資料>定義」下定義了多個排名欄位，則可以選擇建立其他排名規則集，每個排名欄位各一個。 您可以定義其他排名規則集，而不直接與排名欄位關聯。 此彈性可讓您建立一組通用規則，以便在計算一或多個排名值時共用。

**重要**:您必須先完成數個帳戶設定步驟，才能使用排名規則。

請參閱[設定排名](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5)

## 設定排名{#task_4CEBC13925B047FC95BDC217B48089C5}

您必須先完成數個帳戶設定步驟，才能使用排名規則。

**若要設定排名**

1. 從以下選項中選擇：

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>任務 </p> </th> 
      <th colname="col2" class="entry"> <p>設定 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>若要建立以中繼標籤為基礎的排名規則 </p> </td> 
      <td colname="col2"> <p> 
      <ol id="ol_28ABB980143948DFA79AC4360AAB7556"> 
      <li id="li_544075CFA0964C6F8FAF7941AAA9ECCC"> 在產品功能表上，按一下「設定<span class="uicontrol"> </span> &gt; <span class="uicontrol">中繼資料</span> &gt; <span class="uicontrol">定義</span>」。 </li> 
      <li id="li_F237F13B89E8425080C15D3BD697652C"> 在「定義」頁面上，按一下「添加新欄位」 <span class="uicontrol">。</span> </li> 
      <li id="li_2A839874D71D45FEA661B3D3B8BE2A86"> 在「添加欄位」頁的「<span class="uicontrol">欄位名</span>」文本欄位中，鍵入 
      <code>
        rank 
      </code>;在「<span class="uicontrol">中繼標籤名稱</span>」文字欄位中，輸入 
      <code>
        rank 
      </code>;在<span class="uicontrol">資料類型</span>下拉清單中，選擇<span class="uicontrol">排名</span>。 保留所有其他欄位選項。 <p>請參閱<a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local">後端搜尋CGI參數</a>中的查詢參數<span class="codeph"> sp_sr </span>。 </p> </li> 
      <li id="li_8E91AF4BE51A4A41ABBF9680DDE0B7CE">按一下<span class="uicontrol">「新增」</span>。 </li> 
      </ol> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>若要建立以Adobe Analytics量度為基礎的排名規則 </p> </td> 
      <td colname="col2"> <p> 
      <ol id="ol_BE57CBC303D941778B10D855ADC93C68"> 
      <li id="li_8DF5D8F924B24ECBBD2D93C76C69D00C"> 請確定您已在網站搜尋／銷售中設定Adobe Analytics驗證。 <p>請參閱<a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_8AA93F6273B747F9B4DE9E8DFBCBDC42" type="task" format="dita" scope="local">設定Adobe Analytics量度驗證</a>。 </p> </li> 
      <li id="li_CF7DD073FC5A432DADBD282AA8BB9920"> 選取並新增可用的報表套裝。 <p>請參閱<a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0" type="task" format="dita" scope="local">新增Adobe Analytics報表套裝</a>。 </p> </li> 
      <li id="li_9A63448577D04E028DF211D8715F943A"> 設定您要用於建立新排名規則的Adobe Analytics量度清單。 <p>請參閱<a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664" type="task" format="dita" scope="local">編輯報表套裝</a>的Adobe Analytics量度。 </p> </li> 
      <li id="li_1ACA3611D9B44AC394604CD89209C966"> 載入您網站頁面的初始Adobe Analytics量度。 <p>請參閱<a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181" type="task" format="dita" scope="local">載入Adobe Analytics資料</a>。 </p> </li> 
      </ol> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 新增一或多個排名規則。

   請參閱[新增排名規則](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A)。

1. 按一下&#x200B;**[!UICONTROL regenerate your staged site index]**&#x200B;以執行網站的完整重新索引（來自&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Full Index]**）。

   請參閱[執行即時或分段網站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

   請參閱[設定分段網站的遞增索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. 檢查&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**&#x200B;中「排名」欄中的值，確認您的排名規則已正確套用。

## 關於依{#topic_770815CF1B2A491F83FF765871B6F1B8}年齡對檔案進行排名

您可以依HTML檔案的年齡，以指數衰減函式來排名。 衰減速率是使用選擇的半衰期常數來指定的，該值在降至其初始值的一半之前必須經過的時間量。

年齡排名以下列兩個公式為基礎：

`K = -ln(2) / H`

`RANK = e^(K * T)`

變數`H`和`T`是此函式的輸入：`H`是所要的半衰期，`T`是檔案的年齡，以秒為單位。 `K` 是計算的半衰期， `RANK` 是指定年齡值的指數衰減。結果值為0到1。 較新的檔案與較舊的檔案相比，其排名值更接近1。 理論上，檔案不應達到0，但捨入錯誤可能導致結果為0。

## 使用年齡排名{#section_D716507D589442C6B7848892BD28F966}的要求

* 您的帳戶應已正確設定以進行排名。 如果未配置，請參閱[配置排名](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5)。
* HTML檔案必須有HTML meta標籤欄位，以表示其出生日期、開始日期（時間戳記）或某些其他有意義的日期值。
* 特殊的內建函式`search_get_age_rank()`（如「新增或編輯排名規則」頁面中所指定）可用來計算檔案的年齡排名。 下節將詳細說明年齡排名函式的一般使用。 最後，給出了一個實例，說明了年齡排序的特點。

## 在「新增排名規則」頁面或「編輯排名規則」頁面{#section_34BC5276F2AB4419AD92872A397CA0AF}上使用search_get_age_rank()

指定`search_get_age_rank()`如下：

`search_get_age_rank(Birthdate#Half_Life#Default_Rank)`

* 出生日期——檔案的出生日期或開始日期必須是根據欄位的日期格式設定的日期字串。 此日期格式化字串必須是欄位參考，如`{field_name}`。
* Half_Life —— 半衰期是值降至初始值的一半之前必須經過的時間。 此值以天數表示，它是整數或浮點數。
* Default_Rank —— 在出生日期無效或日期未來時，預設排名將用作安全網。 如果其關聯的中繼資料欄位也有有效的預設值，則無法使用此預設值。 此處的值是浮點數或整數。 如果您遇到使用預設值的問題，請參閱下方的建議。

請參閱[新增排名規則](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A)。

請參閱[編輯排名規則](../c-about-rules-menu/c-about-ranking-rules.md#task_5EBF55A43D6545FEA46BAE5E586FA275)。

**範例**

在下列範例中，

`search_get_age_rank({birthdate}#28#0.20)`

檔案`birthdate`欄位中包含的日期會以時間戳記傳入。 半衰期為28天。 如果日期無效，預設排名值為0.20。

請參閱[新增排名規則](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A)中的選項表。

在「新增排名規則」頁面或「編輯排名規則」頁面的「值／排名」區段中，您只能將`search_get_age_rank`與自訂規則搭配使用。 因此，請務必從「值／排名」下拉式清單中選擇「自訂」****。 當規則使用年齡排名函式時，規則的值部分不允許空格。 請確定函式引數中或它們之間沒有空格。 此外，任何數學或條件運算子之間都沒有空格。

以下是值／排名規則的範例——與文字欄位關聯的規則：

`regexp .* search_get_age_rank({other_field}#365#0.20)`

此範例假設`other_field`包含日期值。 如果此欄位本身不是日期類型欄位，則會使用與預先定義的「日期」欄位相關聯的日期格式來解譯此值。 否則，將使用此欄位的日期格式。 每當文檔的欄位（規則的資料源標識的欄位為非空）和函式的返回值（從0到1）是指定的排名時，都使用此值／排名條目。

對於與數值欄位關聯的規則，尤其是日期欄位：

`9999999999 search_get_age_rank({other_field}#365#0.20)`

在處理每個文檔時，`other_field`中的值將使用欄位的日期格式定義轉換為Unix的&quot;epoc&quot;格式。 此值用於`search_get_age_rank()`呼叫。 由於每個「紀元」值都小於99999999999（至少目前），規則只提供函式的返回值（從0到1）作為排名。

在上述兩個範例中，規則的「資料來源」通常與`search_get_age_rank()`函式- `other_field`中使用的欄位相同。

## 將年齡排名整合至排名規則{#section_A86D909687CC45E19D4EA7A4A9283F28}的範例

以下是如何將年齡排名整合至排名規則的範例。 此範例也會顯示年齡排名函式的原始結果和排名規則的結果。 該示例假設如下：

* 所編目的網頁具有名為&quot;bortidate&quot;的HTML meta標籤。 此標籤的內容是與檔案相關的時間戳記。
* 中繼資料定義具有胎日期標籤的定義元標籤欄位。 此欄位會設為鍵入「日期」。

**排名規則**

請參閱[新增中繼標籤欄位](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。

現在您新增了排名規則。 該規則的定義是使用文檔上的「出生日期」欄位。 新的排名規則會新增下列屬性集：

* 資料來源類型：Meta標籤
* 資料來源名稱：出生日期
* 權重／條件：10 —— 最大重要性
* 值／排名：9999999999search_get_age_rank({bortidate}#14#0.10)
* 預設排名：-1

這條規則做了幾件事。 規則的權重設為10。 排名值只是年齡——排名函式的結果，即0到1的值。 不能使用帶有`search_get_age_rank()`的空格。 此外，請注意，欄位「出生日期」會以大括弧括住。 最後，儲存此規則時，值／排名定義中的逗號會取代為`#`字元；這種行為是正常的。

**檢視結果**

使用「資料檢視」功能，快速查看年齡排名函式的結果。 新增適當的中繼資料欄位。 在示例中，`age_val`和`myrank`是應添加到「資料視圖」中的兩個元資料欄位。 `myrank`欄位顯示年齡排名如何影響排名值。 `age_val`欄位顯示該檔案指數衰減函式的原始輸出。

## 預設值{#section_CB109EF78F914E92955D512ACFC3310E}

以下是與函式`search_get_age_rank()`相關的三個預設值：

* 可輸入到`search_get_age_rank()`函式本身的預設值。
* 排名規則的預設排名值。
* 中繼資料定義的預設值。

根據故障發生的位置，您可能會得到不同的預設值。

例如，如果正確實作「排名和篩選」，則中繼資料定義的預設值永遠不會發生。 當沒有該中繼資料欄位的有效或已知內容時，此預設值是最後的度假值。 當`search_get_age_rank()`參照其自己的關聯標籤且該標籤在檔案中遺失時，排名規則的預設值可能會出現。 在此情況下，此規則會直接移至規則的預設值。 如果年齡排名函式參考其他排名規則的標籤，則如果參考的標籤遺失或無效，則可能會使用傳遞至該年齡排名函式的預設值。

## 新增排名規則{#task_A132789FD4E5423DAD090DCDA7311E8A}

您可以根據每個網頁的內容，新增[!DNL Ranking Rules]以影響網頁在搜尋結果中的相對位置。

請參閱[設定排名](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5)。

**若要新增排名規則**

1. 在產品功能表上，按一下「**[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**」。
1. （可選）如果您已建立規則群組並新增規則至群組，請在[!DNL Define Ranking Rules]頁面的&#x200B;**[!UICONTROL Select Rule Group]**&#x200B;下拉式清單中，選取包含您要編輯之規則的規則群組。

   請參閱[新增排名規則群組](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)。
1. 在[!DNL Define Ranking Rules]頁面上，按一下&#x200B;**[!UICONTROL Add Rule]**&#x200B;以新增排名規則，或新增對規則集的參考。
1. 在[!DNL Add Ranking Rule]頁面上，設定您想要的選項。 標有星號(*)的欄位為必填欄位。

   您選擇的「資料來源類型」會影響[!DNL Data Source Name]下拉式清單上可用的選項。 例如，如果您選取&#x200B;**[!UICONTROL Meta Tag]**&#x200B;作為「資料來源類型」,「資料來源名稱」會參照網站頁面上的中繼標籤名稱。 如果您選取&#x200B;**[!UICONTROL Adobe Analytics Metric (Number)]**,「資料來源名稱」會參照您在報表套裝中選取的其中一個Adobe Analytics量度名稱，如網站搜尋／銷售的&#x200B;**[!UICONTROL Edit Adobe Analytics Metrics]**&#x200B;頁面中所示。

   請參閱[編輯報表套裝的Adobe Analytics量度](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664)。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>選項 </p> </th> 
      <th colname="col2" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>資料來源類型 </p> </td> 
      <td colname="col2"> <p>判斷用來輸入此排名規則的資料來源特性。 </p> <p>您可從中選擇的資料來源類型包括： 
      <ul id="ul_B0A97BF0E314495985F44A642C86918D"> 
      <li id="li_4D8BDE32853540809AE78FF5FF5677A1"> <span class="uicontrol"> Meta標籤  </span> <p> 此規則以數值資料或儲存在您網站頁面上之命名中繼標籤中的文字資料為基礎。 </p> </li> 
      <li id="li_4976C31D67254C7F81D554EC49DDBB40"> <span class="uicontrol"> Adobe Analytics量度（數字）  </span> <p>此規則以與您的網站頁面關聯的數值Adobe Analytics量度為基礎。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>資料來源名稱 </p> </td> 
      <td colname="col2"> <p>如果您選擇<span class="uicontrol">中繼標籤</span>作為資料來源類型，這是網站頁面內找到的中繼標籤名稱。 下拉式選單中的名稱來自已定義中繼資料值的清單，這些值是在「設定&gt;中繼資料&gt;定義」中設定的。 </p> <p>請參閱<a scope="local" href="../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5" type="task" format="dita">新增中繼標籤欄位</a>。 </p> <p>如果您選擇「Adobe Analytics量度（數字）」作為「資料來源類型」，則此為Adobe Analytics量度的名稱。 下拉式選單中的名稱來自已定義的可用Adobe Analytics量度清單，這些量度是在「設定&gt; Adobe Analytics &gt;量度&gt;編輯」中設定的。 </p> <p>請參閱<a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664" type="task" format="dita" scope="local">編輯報表套裝</a>的Adobe Analytics量度。 </p> <p>如果您選取的Adobe Analytics量度名稱尚未在「<span class="uicontrol">設定</span> &gt; <span class="uicontrol">中繼資料</span> &gt; <span class="uicontrol">定義</span>」中定義，則會顯示文字欄位和「新增」按鈕。 輸入中繼資料欄位名稱（中繼資料欄位名稱不能超過20個字元），然後按一下「新增<span class="uicontrol">」。</span> </p> <p>當頁面與多個Adobe Analytics索引鍵（例如顯示多個產品的產品頁面）一起出現時，「組合配置」會指定如何處理與該頁面相關聯的多個Adobe Analytics量度值。 選擇以下選項之一： </p> <p> 
      <ul id="ul_D6E51748BB3949048A37C1895F2C0A58"> 
      <li id="li_04F00F382A264C96A519B0D975E25E94"> <span class="uicontrol"> 總計 </span> <p>傳回量度值的總和。 </p> </li> 
      <li id="li_FA44219B663F4CC197BD3A094EB84396"> <span class="uicontrol"> 平均 </span> <p>傳回值的平均值（總和除以值數）。 </p> </li> 
      <li id="li_F0EAAE1EA1754FFEB30F611E5550097B"> <span class="uicontrol"> 最大值  </span> <p>傳回最大的值。 </p> </li> 
      <li id="li_38E3E3F3D9AF4C57803B84B60223FB9D"> <span class="uicontrol"> 第一個 </span> <p>傳回與第一個索引鍵對應的值。 </p> </li> 
      <li id="li_4AEE470CE6BB4D899E975915EC226624"> <span class="uicontrol"> 最後一個 </span> <p>傳回與最後一個索引鍵對應的值。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>重量／條件 </p> </td> 
      <td colname="col2"> <p>包含簡單、單一的規則權重編號，或規則權重編號與測試條件的成對清單。 </p> <p>規則權重數是1-10的值，可指出此排名規則相對於其他排名規則在決定檔案的整體排名時的重要性。 規則權重越高，表示重要性越高。 零(0)的權重會忽略規則。 </p> <p>從下拉式清單中選擇「自訂<span class="uicontrol"></span>」，以定義規則權重／測試條件配對清單，自訂不同頁面的規則權重。 測試條件是用於測試「資料來源值」的Perl片段，或是在自訂篩選指令碼中定義的全域變數（例如，價格、品牌、季節或頁面檢視，如下例所示）。 如果測試條件評估為「true」，則會套用相關的規則權重值。 如果測試條件評估為"false"，則會評估清單中的下一個條件。 <code> 0&nbsp;({price}&nbsp;&gt;&nbsp;50.00)&nbsp;&amp;&amp;&nbsp;({brand}=~/Kuhl/)5&nbsp;{season}&nbsp;=~&nbsp;/Fall/10&nbsp;{pageviews}&nbsp;&gt;&nbsp;1000005 </code>在上述自訂建立的加權／條件範例中，如果第一個測試條件評估為"true"，則套用規則加權0。即價格包含大於50的值，而品牌包含「Kuhl」)。 如果第一個測試條件評估為"false"，則會評估下一個條件。 如果未滿足任何先前條件，則會指派規則權重5。 </p> <p>您應一律在清單結尾處提供沒有條件的規則權重。 如果您不這麼做，則規則的權重為0，在條件測試未評估為"true"時。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>值／排名 </p> </td> 
      <td colname="col2"> <p>由其中一個內建的排名函式或可能的資料來源內容以及所需的排名組成。 </p> <p>如果您選擇<span class="uicontrol"> Adobe Analytics量度（數字）</span>做為「資料來源類型」，則會顯示包含下列選項的下拉式清單： 
      <ul id="ul_104906B6AA8547BAB6979AA37C4FAB90"> 
      <li id="li_7656A2855A054DB8B64E90FE501517AA"> <span class="uicontrol"> 依順序自動排名（預設）  </span> <p>根據檔案的「Adobe Analytics量度」，計算根據檔案相對位置的排名。 例如，檔案與排名最前的檔案位置愈近，其排名就愈高。 </p> </li> 
      <li id="li_1A7D60EA6965434AA6D39B215C158306"> <span class="uicontrol"> 依值自動排名  </span> <p>根據檔案的「Adobe Analytics量度」，根據檔案的相對值來計算排名。 例如，檔案值與排名最前的檔案值越接近，其排名就越高。 </p> </li> 
      <li id="li_457DE44D6ADA40619DC77220BF12318E"> <span class="uicontrol"> 自訂 </span> <p>指定自訂設定。 例如，名稱為「品牌」的「資料來源」可能包含特定產品的品牌名稱。 您可以透過列出每個品牌及其排名來指定其相對重要性。 </p> </li> 
      </ul> </p> <p>自動排名計算傳回的排名值在0.0（最低）到1.0（最高）範圍內。 不會根據「設定&gt;中繼資料&gt;定義」下「排名」欄位所定義的範圍來調整這些欄位。 </p> <p>在下列範例中，如果特定搜尋結果的品牌資料來源與「DKNY」完全相符，則該結果的套用排名為0.5。否則，如果品牌為「Levis」，則套用的排名為0.1。「資料來源」內容必須符合設定值。 換言之，如果「資料來源」內容是「Levis Corp.」，則不符合「Levis」值。 忽略大小寫，因此"DKNY"與"dkny"和"Dkny"相符。<code> DKNY&nbsp;0.5 Levis&nbsp;0.1 Lee&nbsp;0.2 </code> </p> <p>作為更進階的選項，您可以指定值作為規則運算式。 例如，假設您的某些網站頁面包含「Levis」品牌值，而其他網站頁面則包含「Levis jeans」品牌值。 您可以使用與關鍵字一起指定的規則運算式 
      <code>
        regexp 
      </code>。 </p> <p>請參閱<a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local">規則運算式</a>。 </p> <p>在下列範例中，包含品牌內容「Levis jeans」的搜尋結果檔案會指派0.1的排名。與標準比較一樣，規則運算式會忽略大小寫。<code> DKNY&nbsp;0.5 regexp&nbsp;Levis.*&nbsp;0.1 Lee&nbsp;0.2 </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>預設排名 </p> </td> 
      <td colname="col2"> <p> 指定對不符合任何指定值的搜索結果文檔應用的排名。 在上述範例中，含有「品牌」資料來源的搜尋結果檔案會指派預設排名值，因為「差距」不符合任何已定義的值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>附註 </p> </td> 
      <td colname="col2"> <p>新增與您建立之排名規則定義或規則群組定義相關的資訊。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

   有效排名值的範圍通常為-1.0到1.0，如下所示：

   * `-1.0` 是&quot;最小排名（在搜尋結果中顯示較低）&quot;。
   * `0.0` 為&quot;中性排名（不變更搜尋結果順序）&quot;。
   * `1.0` 是&quot;最大排名(在搜尋結果中顯示較高。&quot;

   定義的排名應在每個規則的相同範圍內。 排名範圍也必須符合為&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**&#x200B;下的「排名」欄位所定義的範圍。

   請參閱[新增中繼標籤欄位](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。

   另請參閱[編輯排名規則](../c-about-rules-menu/c-about-ranking-rules.md#task_5EBF55A43D6545FEA46BAE5E586FA275)。
1. 按一下 **[!UICONTROL Add]**.
1. 若要預覽規則新增結果，請按一下&#x200B;**[!UICONTROL regenerate your staged site index]**&#x200B;重建分段網站索引。

   請參閱[執行即時或分段網站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

   請參閱[執行即時或分段網站的遞增索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 編輯排名規則{#task_5EBF55A43D6545FEA46BAE5E586FA275}

您可以編輯已新增的現有排名規則。

請參閱[設定排名](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5)。

**若要編輯排名規則**

1. 在產品功能表上，按一下「**[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**」。
1. （可選）如果您已建立規則群組並新增任何規則至群組，請在&#x200B;**[!UICONTROL Define Ranking Rules]**&#x200B;頁面的&#x200B;**[!UICONTROL Select Rule Group]**&#x200B;下拉式清單中，選取包含您要編輯之規則的規則群組。

   請參閱[新增排名規則群組](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)。
1. 在表格的&#x200B;**[!UICONTROL Actions]**&#x200B;欄標題下，按一下&#x200B;**[!UICONTROL Edit]**&#x200B;以取得您要變更的資料來源名稱。
1. 在[!DNL Edit Ranking Rule]頁面上，設定您想要的選項。 標有星號(*)的欄位為必填欄位。

   請參閱[新增排名規則](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A)下的選項表。
1. 按一下 **[!UICONTROL Save Changes]**.
1. 重建分段網站索引以預覽規則編輯的結果。

   請參閱[執行即時或分段網站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

   請參閱[執行即時或分段網站的遞增索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 刪除排名規則{#task_742A3BCC2A6E4164BE84CC7408807EBB}

您可以刪除不再需要使用的排名規則。

請參閱[設定排名](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5)。

請參閱[新增排名規則群組](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)。

**若要刪除排名規則**

1. 在產品功能表上，按一下「**[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**」。
1. （可選）如果您已建立規則群組並新增任何規則至群組，請在[!DNL Define Ranking Rules]頁面的&#x200B;**[!UICONTROL Select Rule Group]**&#x200B;下拉式清單中，選取包含您要刪除之規則的規則群組。
1. 在表格的&#x200B;**[!UICONTROL Actions]**&#x200B;欄標題下，按一下&#x200B;**[!UICONTROL Delete]**&#x200B;以取得您要變更的資料來源名稱。
1. 在[!DNL Delete Ranking Rule]頁面上，按一下&#x200B;**[!UICONTROL Delete]**。

   您會返回至[!DNL Define Ranking Rules]頁面。
1. 重建分段網站索引以預覽規則刪除的結果。

   請參閱[執行即時或分段網站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

   請參閱[執行即時或分段網站的遞增索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 新增排名規則群組{#task_B65081B3CC9E4330A7FEE77B7BCD36C8}

如果您已定義多個「排名」類型的中繼標籤，則可建立個別的規則集合，以用於計算各種排名欄位。 您可以新增排名規則群組，然後將其指派給其中一個已定義的排名欄位。

規則群組通常包含您新增的一或多個規則。 不過，規則群組也可以參考其他規則群組。 例如，您可以建立一或多個規則群組，然後將常用的規則新增至每個規則。 然後，這些規則會在計算多個排名時共用。

請參閱[編輯排名規則群組](../c-about-rules-menu/c-about-ranking-rules.md#task_D3EC0437E47144BC9E754FEF99C725E5)。

請參閱[刪除排名規則群組](../c-about-rules-menu/c-about-ranking-rules.md#task_BE5BE01F377843BEA9846E094A07F2EA)。

請參閱[檢閱排名規則群組](../c-about-rules-menu/c-about-ranking-rules.md#task_5694459D050C4254A25186038CD66B6E)。

**若要新增排名規則群組**

1. 在產品功能表上，按一下「**[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**」。
1. 在[!DNL Define Ranking Rules]頁面的&#x200B;**[!UICONTROL Select Rule Group]**&#x200B;下拉式清單右側，按一下&#x200B;**[!UICONTROL Add]**。
1. 在[!DNL Add Ranking Rule Group]頁面的&#x200B;**[!UICONTROL Rule Group Name]**&#x200B;欄位中，為新規則群組輸入唯一名稱。
1. 在&#x200B;**[!UICONTROL Rank Field Name]**&#x200B;下拉式清單中，選取您要與新規則群組關聯的排名中繼資料欄位名稱。 如果您不想指派排名，請選取&#x200B;**[!UICONTROL None]**。

   排名欄位名稱清單來自在&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**&#x200B;中新增的中繼資料定義。

   請參閱[新增中繼標籤欄位](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)中的選項表。
1. 按一下 **[!UICONTROL Add]**.
1. 重建分段網站索引以預覽新增規則的結果。

   請參閱[執行即時或分段網站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

   請參閱[執行即時或分段網站的遞增索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 編輯排名規則群組{#task_D3EC0437E47144BC9E754FEF99C725E5}

您可以編輯現有排名規則群組的設定。

請參閱[新增排名規則群組](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)。

**若要編輯排名規則群組**

1. 在產品功能表上，按一下「**[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**」。
1. 在[!DNL Define Ranking Rules]頁面的&#x200B;**[!UICONTROL Select Rule Group]**&#x200B;下拉式清單右側，按一下&#x200B;**[!UICONTROL Edit]**。
1. 在[!DNL Edit Ranking Rule Group]頁面的&#x200B;**[!UICONTROL Rule Group Name]**&#x200B;欄位中，輸入規則群組的唯一名稱。
1. 在&#x200B;**[!UICONTROL Rank Field Name]**&#x200B;下拉式清單中，選取您要與規則群組關聯的排名中繼資料欄位名稱。 如果您不想指派排名，請選取&#x200B;**[!UICONTROL None]**。

   排名欄位名稱清單來自在&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**&#x200B;中新增的中繼資料定義。

   請參閱[新增中繼標籤欄位](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)中的選項表。
1. 按一下 **[!UICONTROL Save Changes]**.
1. 重建分段網站索引以預覽新增規則的結果。

   請參閱[執行即時或分段網站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

   請參閱[執行即時或分段網站的遞增索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 刪除排名規則群組{#task_BE5BE01F377843BEA9846E094A07F2EA}

您可以刪除不再需要或使用的排名規則群組。 刪除群組時，新增至群組的任何規則也會隨之刪除。 您無法刪除預設的「排名規則」群組。

刪除組中包含的任何規則組的內容不會刪除；只會移除這些群組的參照。

請確定您已重新為網站建立索引，以便在搜尋結果中正確反映變更。

請參閱[新增排名規則群組](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)。

**若要刪除排名規則群組**

1. 在產品功能表上，按一下「**[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**」。
1. 在[!DNL Define Ranking Rules]頁面的&#x200B;**[!UICONTROL Select Rule Group]**&#x200B;下拉式清單中，選取您要刪除的群組。
1. 在&#x200B;**[!UICONTROL Select Rule Group]**&#x200B;下拉式清單的右側，按一下&#x200B;**[!UICONTROL Delete]**。
1. 在[!DNL Delete Ranking Rule Group]頁面上，按一下&#x200B;**[!UICONTROL Delete]**。
1. 重建分段網站索引以預覽新增規則的結果。

   請參閱[執行即時或分段網站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

   請參閱[執行即時或分段網站的遞增索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 檢閱排名規則群組{#task_5694459D050C4254A25186038CD66B6E}

您可以使用排名規則群組概述來查看每個群組的排名欄位名稱，以及相關的資料來源和加權。

請參閱[新增排名規則群組](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8)。

**若要檢閱排名規則群組**

1. 在產品功能表上，按一下「**[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**」。
1. 在[!DNL Define Ranking Rules]頁面的&#x200B;**[!UICONTROL Select Rule Group]**&#x200B;下拉式清單右側，按一下&#x200B;**[!UICONTROL Overview]**。
1. 在[!DNL Ranking Rule Groups Overview]頁面上，按一下&#x200B;**[!UICONTROL Close]**&#x200B;返回[!DNL Define Ranking Rules]頁面。
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 測試排名規則{#task_56F64EE7ED5B42E481F0990A9DD98ADB}

您可以提供適當的URL測試，以測試您已設定的排名規則定義。 會顯示計算中使用的量度，以及計算的排名值。

請參閱[關於排名規則](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397)。

**若要測試排名規則**

1. 在產品功能表上，按一下「**[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]**」。
1. 在[!DNL Define Ranking Rules]頁面的&#x200B;**[!UICONTROL Test URL]**&#x200B;區域中，輸入網站上網頁的URL。
1. 按一下 **[!UICONTROL Test]**.
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 調整與排名規則{#task_3CB6FC92A66F4D99874A42D55825DB64}相關的權重

您可以變更個別排名規則的相對貢獻，以及排名對最終搜尋結果的貢獻。

如果未定義「排名」，則搜尋結果會在&#x200B;**[!UICONTROL Adjust Ranking Weights]**&#x200B;頁面「規則與相關性」滑桿的&#x200B;**[!UICONTROL Natural Relevance]**&#x200B;一側100%。 這種平衡只表示搜尋結果僅依搜尋詞排序。

定義「排名」時，關聯的「排名」中繼資料欄位會指派一個「相關性」值，範圍從1到10。 值1表示計算的排名佔搜尋結果排序的10%，而自然相關性佔其餘90%。

如果您在規則群組中定義了多個規則，則每個規則的「權重」值會決定規則結果對總計計算排名的貢獻。 例如，假設您的「自然相關性」為80%，表示相關的「排名」欄位的相關性為2。 您也定義了兩個規則：一個重量為3，另一個重量為7。 在這種情況下，第一條規則對最終結果的貢獻為6%((3 /(3+7))* 20%)。 第二項規則對最終結果的貢獻為14%((7 /(3+7))* 20%)。

**若要調整與排名規則相關的權重**

1. 在產品功能表上，按一下「**[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Adjust Weights]**」。
1. 在[!DNL Adjust Ranking Weights]頁面的&#x200B;**[!UICONTROL Select Rule Group]**&#x200B;下拉式清單中，選取您要調整其排名權重的群組。
1. 拖曳滑桿以變更對應的貢獻值。

   圓形圖以圖形方式反映您所做的變更。
1. 按一下 **[!UICONTROL Save Changes]**.
1. 重建分段網站索引以預覽新增規則的結果。

   請參閱[執行即時或分段網站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

   請參閱[執行即時或分段網站的遞增索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。
1. （可選）執行下列任一項作業：

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。
