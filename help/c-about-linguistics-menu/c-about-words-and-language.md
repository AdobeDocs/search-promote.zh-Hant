---
description: 您可以使用「字詞和語言」來判斷搜尋詞與網頁內容的匹配方式。
seo-description: 您可以使用「字詞和語言」來判斷搜尋詞與網頁內容的匹配方式。
seo-title: 關於字詞和語言
solution: Target
title: 關於字詞和語言
topic: Linguistics,Site search and merchandising
uuid: 793d7a40-4609-44b8-a170-536eb1434537
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# 關於字詞和語言{#about-words-language}

您可用來 [!DNL Words & Language] 判斷搜尋詞與網頁內容的匹配方式。

## 使用字詞和語言 {#concept_CEB4B9576F3C4E2EB87B352EEC738D79}

在設定的效果 [!DNL Words & Language] 可供網站訪客使用（包括您對這些設定所做的任何變更）之前，您必須重新產生網站索引。 與建立索引不同，重新生成不需要編目您的網頁，只需幾秒鐘。

## 設定搜尋詞與您網頁內容的匹配方式 {#task_351A9144A51F4B41923BDBACDEF3B616}

您可以使用「字詞與語言」來判斷網站搜尋／銷售如何將搜尋詞與網頁內容相符。

<!-- 

t_configuring_how_search_terms_matched_to_your_web_content.xml

 -->

**若要設定搜尋詞與您網頁內容的匹配方式**

1. 在產品功能表上，按一下 **[!UICONTROL Linguistics]** > **[!UICONTROL Words & Language]**。
1. 在頁 [!DNL Words & Languages] 面上，設定您想要的選項。

   <!-- 
   
   r_words_and_languages_options.xml
   
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
      <td colname="col1"> <p>區分大小寫 </p> </td> 
      <td colname="col2"> <p>預設未選取。 </p> <p>確定大寫字母是否與小寫字母區分。 例如，選取「成功」時，會將「成功」與「成功」區分開，而搜尋結果在兩者之間可能會有所不同。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>變音符號敏感性 </p> </td> 
      <td colname="col2"> <p>依預設選取。 </p> <p> 判斷包含變音符號字元的字詞是否與不包含變音符號字詞區分。 例如，選取「pagina」時，會將「página」與「página」區分。 如果您的網站使用非英文語言，請取消選取此選項。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>數量 </p> </td> 
      <td colname="col2"> <p>依預設選取。 </p> <p>確定是否對包含數字的單字編製索引。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>忽略撇號 </p> </td> 
      <td colname="col2"> <p>預設未選取。 </p> <p>從查詢中移除撇號。 例如，搜尋"Tree's"會傳回與搜尋"Trees"相同的結果。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>忽略連字型大小 </p> </td> 
      <td colname="col2"> <p>預設未選取。 </p> <p>連字型大小會從查詢中移除。 例如，搜尋"blue-bell"會傳回與搜尋"bluebell"相同的結果。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>部分字母數字匹配 </p> </td> 
      <td colname="col2"> <p>預設未選取。 </p> <p>選取此選項後，您就可以在字母數值轉換時分割Token，以允許部分或產品Token上的自由文字比對。 </p> <p>例如，假設您的網站上一或多個頁面的內文內 <span class="codeph"> 容中 </span> 有產品識別碼910XT。 如果未選取 <i>此選項</i> , <span class="keyword"> Adobe Search&amp;Promote會在搜尋910XT時 </span> 尋找與此產品識別碼相符的 <span class="codeph"> 項目 </span>。 此外， <span class="uicontrol"> 在開啟「搜尋概念 </span> 轉換」後， <span class="keyword"> Adobe Search&amp;Promote </span> 也會找到 <span class="codeph"> 910 XT </span>但是，它不會只找到 <span class="codeph"> 910或 </span><span class="codeph"> XT </span> 的例項。 </p> <p>當您選取「部 <span class="uicontrol"> 分英數字元比 </span>對」時，索引器會將這些混合英數字元代號分割為多個代號。 例如，將產品標識符(如 <span class="codeph"> XYZ123) </span> 索引到三個Token中： <span class="codeph"> XYZ 123 </span>、 <span class="codeph"> XYZ </span>和 <span class="codeph"> 123 </span>。 這類功能允許在任何這些變體上進行搜尋時間自由文字比對。 </p> <p>在另一個範例中，假設您有產品識別碼 <span class="codeph"> AB910XT </span>。 如果選擇「 <span class="uicontrol"> 部分匹配」並開啟「搜索 </span><i>-Div-Concat-Div-Enable」,</i><span class="uicontrol"></span><span class="keyword"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span><span class="codeph"></span>Adobe Concat-Div-Concanced I=AB910AB AB AB Adobe Adobe Promate Lignesing Adistindinding Resonginging Resondin An Resonging Reson Reso An Reson Reson Reson An Prosisisin（部分匹配）」（部分匹配），並啟用搜索)。 然後，例如，當用戶搜索 <span class="codeph"> 910XT </span>時，搜索將展開，並查找 <span class="codeph"> 910XT、910或 </span><span class="codeph"></span><span class="codeph"></span>XT的實例。 </p> <p> <p>注意： 預 <span class="uicontrol"> 設未啟用「搜 </span> 尋概念-Div-Enable」。 請聯絡技術支援以啟用您使用的功能。 </p> </p> <p> <p>注意： 「部 <span class="uicontrol"> 分字母數字匹 </span> 配」會全局應用於所有索引欄位。 但是，它只影響文本匹配；它不會影響精確匹配或範圍匹配。 </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>相似音效比對 </p> </td> 
      <td colname="col2"> <p>依預設選取。 </p> <p>發音相同的字詞會相符，例如「health」和「helth」。 此功能可讓客戶輕鬆搜尋，儘管拼字錯誤。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>替代Word表格 </p> </td> 
      <td colname="col2"> <p>預設值為 <b>預設替代字詞表單</b>。 </p> <p>您可以從「替代字詞表單」下拉式清單中選取下列選項： 
      <ul id="ul_CAC73FB4D1384312BB5DD327D3D66948"> 
      <li id="li_F4E76CD27EA34AC5BC81E648BC6CBA4C"><b>無</b> <p>在建立索引期間，不會套用字詞乾或替代字詞表單。 </p> </li> 
      <li id="li_3186FD1F3BC94A5CB66FFF8EA6726D81"><b>預設替代字詞表單</b> <p>在建立索引期間，會自動完成字根。 </p> </li> 
      <li id="li_5815DE0795E0423C9C84C62B96A3F841"><b>網域字典</b> <p>您設定為詞乾字典的任何網域字典都會使用替代字詞表單的來源。 </p> <p>請參閱 <a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" type="concept" format="dita" scope="local"> 關於字典 </a>。 </p> <p>請參 <a href="../c-about-linguistics-menu/c-about-dictionaries.md#task_541E8453A12F4A8E89CF6F595469F074" type="task" format="dita" scope="local"> 閱將字典配置為詞乾字典 </a>。 </p> </li> 
      </ul> </p> <p>如果在 <span class="keyword"> Adobe Search&amp;Promote中啟用了片語相關 </span>功能，請注意，片語中也會出現替代字詞表單。 </p> <p>請參 <a href="../c-searchpromote-release-notes/c-rn-06-19-14-version-815.md#concept_E8CEBC65A28A4E61BDE69B4B4DA55E73" format="dita" scope="local"> 閱Search&amp;Promote 8.15.0發行說明(2014/6/19) </a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>語言 </p> </td> 
      <td colname="col2"> <p>預設為 <b>英文（美國）</b>。 </p> <p>所選語言確保根據世界所選部分使用的慣例來分析日期和數值。 </p> <p>當「替 <span class="uicontrol"> 代字詞表單」 </span> 設為「預設替代字詞表單」或「網域字典」時 <span class="uicontrol"></span><span class="uicontrol"></span>，字詞表單和字尾會根據所選語言的語言規則而變更。 </p> <p>依預設，「語言」設定不會用來判斷從您網站讀取的頁面語言。 讀取頁面的語言由其HTTP標題或頁面本身的元標籤決定。 您的網站可能包含許多不同語言的頁面。 無論此處選擇的語言為何，每個頁面都會正確讀取和建立索引。 </p> <p>如果您對網站上的某些頁面使用Unicode字元集編碼，例如UTF-8，請確定這些頁面的語言皆已正確指定。 如果您的Unicode檔案不存在適當的HTTP標題或元標籤，您可以使用 <span class="uicontrol"> 「設定 </span> &gt; <span class="uicontrol"> 中繼資料 </span> &gt; <span class="uicontrol"> 插入」 </span> 來指定適當的語言。 </p> <p>勾選「 <span class="uicontrol"> 套用至沒有指定語言的檔案」? </span> 使用「語言」設定，以便從您的網站讀取沒有明確設定的頁面。 只有部分檔案沒 <i>有語言設定</i> 時，才使用此設定。 如果您 <span class="uicontrol"> 的文 </span> 件沒有語言設定，或者文 <span class="uicontrol"> 件是受影響檔案的語言設定集，則使用「Metadata </span><span class="uicontrol"></span><i></i> &gt; Inpertions」（中繼資料&gt;插入）。 </p> <p>請參 <a href="../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5" type="concept" format="dita" scope="local"> 閱注射 </a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>使用反編譯程式？ </p> </td> 
      <td colname="col2"> <p> <p>注意： 此功能僅用於丹麥文和德文。 此外，此功能預設未啟用。 請聯絡技術支援以啟用您使用的功能。 啟用後，使用解 <b>壓縮器？</b> 選項僅在您從本表前面所述的「語言」下拉 <span class="uicontrol"> 清單中選 </span> 擇「丹麥文」或「德文」時 <span class="uicontrol"></span><span class="uicontrol"></span> ，才會顯示在用戶介面中。 </p> </p> <p>當您選擇「使 <span class="uicontrol"> 用反編譯器」時？ </span>，服務會劃分丹麥文或德文複合字詞，這可讓元件字詞與原始複合字詞一起建立索引。 </p> <p>若要瞭解此功能的運作方式，請在文字欄位中輸入字詞，然後按一下「測 <span class="uicontrol"> 試」 </span>。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 按一下 **[!UICONTROL Save Settings]**.
1. 若要預覽變更結果，請按一下以 **[!UICONTROL regenerate your staged site index]** 重建分段網站索引。
1. （可選）執行下列任一項作業：

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。

