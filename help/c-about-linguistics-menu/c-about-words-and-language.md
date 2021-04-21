---
description: 您可以使用「字詞和語言」來判斷搜尋詞與網頁內容的匹配方式。
solution: Target
title: 關於字詞和語言
topic-legacy: Linguistics,Site search and merchandising
uuid: 793d7a40-4609-44b8-a170-536eb1434537
exl-id: bfc84879-1fd1-4c86-beab-353469014c64
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 0%

---

# 關於字詞和語言{#about-words-language}

您可以使用[!DNL Words & Language]來判斷搜尋詞與網頁內容的匹配方式。

## 使用字詞和語言{#concept_CEB4B9576F3C4E2EB87B352EEC738D79}

在[!DNL Words & Language]設定的效果可供網站訪客使用（包括您對這些設定所做的任何變更）之前，您必須重新產生網站索引。 與建立索引不同，重新生成不需要編目您的網頁，只需幾秒鐘。

## 設定搜尋詞與您網頁內容的比對方式{#task_351A9144A51F4B41923BDBACDEF3B616}

您可以使用「字詞與語言」來判斷網站搜尋／銷售如何將搜尋詞與網頁內容相符。

<!-- 

t_configuring_how_search_terms_matched_to_your_web_content.xml

 -->

**若要設定搜尋詞與您網頁內容的匹配方式**

1. 在產品功能表上，按一下「**[!UICONTROL Linguistics]** > **[!UICONTROL Words & Language]**」。
1. 在[!DNL Words & Languages]頁面上，設定您想要的選項。

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
      <td colname="col2"> <p>預設未選取。 </p> <p>確定大寫字母是否與小寫字母區分。 例如，選取「成功」時，會將「成功」與「成功」區分開，搜尋結果在兩者之間可能會有所不同。 </p> </td> 
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
      <td colname="col2"> <p>預設未選取。 </p> <p>選取此選項後，您就可以在字母數值轉換時分割Token，以允許部分或產品Token上的自由文字比對。 </p> <p>例如，假設您的網站上一或多個頁面的內文內容中有<span class="codeph"> 910XT </span>的產品識別碼。 當此選項<i>未選取</i>時，<span class="keyword">AdobeSearch&amp;Promote</span>在搜尋<span class="codeph"> 910XT </span>時，會找出與此產品識別碼相符的項目。 而且，在<span class="uicontrol">啟用</span>搜尋連結時，<span class="keyword">AdobeSearch&amp;Promote</span>也會找到<span class="codeph"> 910 XT </span>。 但是，它不會只找到<span class="codeph"> 910 </span>或<span class="codeph"> XT </span>的實例。 </p> <p>當您選取「部分字母數字元合</span>」時，索引器會將這些混合的字母數字代號分割為多個代號。 <span class="uicontrol">例如，將產品標識符（如<span class="codeph">XYZ123 </span>）索引到三個Token中：<span class="codeph"> XYZ123 </span>、<span class="codeph"> XYZ </span>和<span class="codeph"> 123 </span>。 這類功能允許在任何這些變體上進行搜尋時間自由文字比對。 </span></p> <p>在另一個範例中，假設您有產品識別碼<span class="codeph"> AB910XT </span>。 如果選擇<span class="uicontrol">部分字母數字匹配</span> <i>和</i>的<span class="uicontrol">啟用</span>搜索連接，<span class="keyword">AdobeSearch&amp;Promote</span>將其索引為<span class="codeph"> AB910XT </span>、<span class="codeph"> AB </span>、<span class="codeph"> 910 </span>和<span class="codeph"> XT </span>。 然後，例如，當用戶搜索<span class="codeph"> 910XT </span>時，搜索將展開，並查找<span class="codeph"> 910XT </span>、<span class="codeph"> 910 </span>或<span class="codeph"> XT </span>的實例。 </p> <p> <p>注意： <span class="uicontrol">預設未啟用搜尋Concat-Div-Enable </span>。 請聯絡技術支援以啟用您使用的功能。 </p> </p> <p> <p>注意： <span class="uicontrol">部分字母數字匹配</span>將全局應用於所有索引欄位。 但是，它只影響文本匹配；它不會影響精確匹配或範圍匹配。 </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>相似音效比對 </p> </td> 
      <td colname="col2"> <p>依預設選取。 </p> <p>發音相同的字詞會相符，例如「health」和「helth」。 此功能可讓客戶輕鬆搜尋，儘管拼字錯誤。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>替代字Forms </p> </td> 
      <td colname="col2"> <p>預設值為<b>預設替代字詞Forms</b>。 </p> <p>您可以從「替代字詞Forms」下拉式清單中選取下列選項： 
      <ul id="ul_CAC73FB4D1384312BB5DD327D3D66948"> 
      <li id="li_F4E76CD27EA34AC5BC81E648BC6CBA4C"><b>無</b> <p>在建立索引期間，不會套用字詞乾或替代字詞表單。 </p> </li> 
      <li id="li_3186FD1F3BC94A5CB66FFF8EA6726D81"><b>預設替代字詞Forms</b> <p>在建立索引期間，會自動完成字根。 </p> </li> 
      <li id="li_5815DE0795E0423C9C84C62B96A3F841"><b>網域字典</b> <p>您設定為詞乾字典的任何網域字典都會使用替代字詞表單的來源。 </p> <p>請參閱<a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" type="concept" format="dita" scope="local">關於字典</a>。 </p> <p>請參閱<a href="../c-about-linguistics-menu/c-about-dictionaries.md#task_541E8453A12F4A8E89CF6F595469F074" type="task" format="dita" scope="local">將字典配置為詞乾字典</a>。 </p> </li> 
      </ul> </p> <p>如果<span class="keyword">AdobeSearch&amp;Promote</span>中啟用了片語相干，請注意，片語中也會出現替代片語。 </p> <p>請參閱<a href="../c-searchpromote-release-notes/c-rn-06-19-14-version-815.md#concept_E8CEBC65A28A4E61BDE69B4B4DA55E73" format="dita" scope="local">Search&amp;Promote8.15.0發行說明(6/19/2014)</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>語言 </p> </td> 
      <td colname="col2"> <p>預設值為<b>英文（美國）</b>。 </p> <p>所選語言確保根據世界所選部分使用的慣例來分析日期和數值。 </p> <p>當<span class="uicontrol">替代字Forms</span>設為<span class="uicontrol">預設替代字Forms</span>或<span class="uicontrol">網域字典</span>時，字詞表單和字尾會根據所選語言的語言規則而改變。 </p> <p>依預設，「語言」設定不會用來判斷從您網站讀取的頁面語言。 讀取頁面的語言由其HTTP標題或頁面本身的元標籤決定。 您的網站可能包含許多不同語言的頁面。 無論此處選擇的語言為何，每個頁面都會正確讀取和建立索引。 </p> <p>如果您對網站上的某些頁面使用Unicode字元集編碼，例如UTF-8，請確定這些頁面的語言皆已正確指定。 如果Unicode文檔不存在相應的HTTP標頭或元標籤，則可以使用<span class="uicontrol">設定</span> &gt; <span class="uicontrol">元資料</span> &gt; <span class="uicontrol">插入</span>來指定相應的語言。 </p> <p>勾選「套用至沒有指定語言的檔案」? <span class="uicontrol"></span> 使用「語言」設定，以便從您的網站讀取沒有明確設定的頁面。只有<i>某些</i>檔案沒有語言設定時，才使用此設定。 如果您的檔案的<i>無</i>具有語言設定，或受影響的檔案集是眾所周知且可管理的小清單，請使用<span class="uicontrol">設定</span> &gt; <span class="uicontrol">中繼資料</span> &gt; <span class="uicontrol">插入</span>。 </p> <p>請參閱<a href="../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5" type="concept" format="dita" scope="local">關於注射</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>使用反編譯程式？ </p> </td> 
      <td colname="col2"> <p> <p>注意： 此功能僅用於丹麥文和德文。 此外，此功能預設未啟用。 請聯絡技術支援以啟用您使用的功能。 啟用後，<b>使用解壓縮程式？</b> 選項僅在您從本表稍早說明的「語 <span class="uicontrol"> 言」下 </span> 拉式清單中選 <span class="uicontrol"> 擇丹麥文或德文時，才會顯示 </span> 在使 <span class="uicontrol">  </span> 用者介面中。 </p> </p> <p>選擇<span class="uicontrol">使用解壓縮程式時？ </span>，服務會劃分丹麥文或德文複合字詞，這可讓元件字詞與原始複合字詞一起建立索引。 </p> <p>若要瞭解此功能的運作方式，請在文字欄位中輸入字詞，然後按一下「<span class="uicontrol">測試</span>」。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 按一下 **[!UICONTROL Save Settings]**.
1. 若要預覽變更結果，請按一下&#x200B;**[!UICONTROL regenerate your staged site index]**&#x200B;重建分段網站索引。
1. （可選）執行下列任一項作業：

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。
