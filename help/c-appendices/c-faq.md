---
description: 閱讀有關Search&amp;Promote的常見問題
solution: Target
title: 常見問題
topic: 附錄、網站搜尋與銷售
uuid: 4ce454a4-e770-4587-91a0-a25491818ac6
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '8648'
ht-degree: 0%

---


# 常見問題{#frequently-asked-questions}

## AdobeFlash{#reference_4A25BBDE32214AF5A1A454F38FD51243}

常見問題頁面，討論在網站上建立SWF檔案索引和搜尋的支援。

以下是有關SWF檔案的常見問題：

* [何時編目SWF檔案並建立索引？](#section_01BB5259140D4D5FB04CCB7A1A63DE99)
* [我要如何為SWF建立索引……](#section_0A6A52CC70D4495BBE14D91906318F95)
* [如何辨識SWF檔案？](#section_B36C0536AB544F509601DC6A11A8E656)
* [SWF檔案如何建立索引？](#section_36856058A4B54FA5ABF921344F50410C)
* [SWF檔案會計為頁面嗎？](#section_0158D6DE70BC40D78E2374787B9F58AB)
* [我要如何防止個別SWF檔案的索引……](#section_E38AD37989EF410B97AF5125057BFD22)
* [如何防止SWF檔案建立索引……](#section_DF2606A50E9A44859CFA0D44D7C5F2E4)
* [我為何無法在我的網站上搜尋中文、日文或韓文SWF檔案？](#section_EE1A3A705AE74148BD195A0CE513A5C4)

## 何時編目SWF檔案並建立索引？{#section_01BB5259140D4D5FB04CCB7A1A63DE99}

如果SWF檔案包含在HTML頁面的內嵌或物件標籤中，則會編目並建立索引，如下列範例所示：

```
<embed src="Flash-file-URL">  
 
<object>  
<param name=movie value="Flash-file-URL">  
</object> 
```

如果您將檔案URL列為入口點，也會辨識SWF檔案。

請參閱[新增多個您要建立索引的URL入口點](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)。

## 我要如何為SWF檔案建立索引？{#section_0A6A52CC70D4495BBE14D91906318F95}

若要搜尋和索引SWF檔案，請選取內容類型&#x200B;**[!UICONTROL Adobe Flash Movies]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)。

只要Flash檔案是從HTML文檔中的`<embed>`標籤或`<object>`標籤引用的，就會對文本編製索引，並搜索檔案中列出的所有URL。

如果您的檔案未從`<embed>`標籤或`<object>`標籤引用，您可以在HTML檔案的`<a href=...>`標籤中列出SWF檔案，或列為URL入口點。

請參閱[新增多個您要建立索引的URL入口點](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)。

## 如何辨識SWF檔案？{#section_B36C0536AB544F509601DC6A11A8E656}

SWF檔案由下列MIME類型識別：

`application/x-shockwave-flash`

如果副檔名為。swf，也可以使用`application/octet-stream`&quot;或`text/plain` MIME類型識別SWF檔案。

配置錯誤的伺服器可能會對SWF檔案使用不同的MIME類型。 如果您在編目和索引SWF檔案時遇到問題，請務必檢查您的伺服器組態。

## SWF檔案如何建立索引？{#section_36856058A4B54FA5ABF921344F50410C}

SWF檔案中包含的文字會建立索引，就像在封閉的HTML頁面中是`<body>`文字一樣。 如果搜尋結果找到內嵌SWF檔案中的文字，結果會實際連結至封閉的HTML頁面，而非SWF檔案。 這樣，SWF檔案就會以正確的內容顯示。

如果SWF檔案包含URL做為「載入影片」動作，則參照的SWF檔案中的文字會作為封閉HTML頁面的一部分建立索引。

如果SWF檔案包含URL做為「Get URL」（取得URL）動作，URL會稍後編目並建立索引，就像HTML `<a href=...>`參考稍後會編目並建立索引一樣。

如果SWF檔案列為URL入口點，SWF檔案文字會以單一頁面建立索引。 從入口點SWF連結直接尋找文字至影片，而非封閉HTML頁面的搜尋結果。

請參閱[新增多個您要建立索引的URL入口點](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)。

## SWF檔案會計為頁面嗎？{#section_0158D6DE70BC40D78E2374787B9F58AB}

無.SWF檔案會視為其封閉HTML頁面的一部分。 SWF檔案中包含的所有「載入影片」URL也會視為封閉HTML頁面的一部分。 因此，從HTML頁面參考的SWF檔案不會計為帳戶的頁面總數的「頁面」。

如果SWF檔案列為URL入口點，則該SWF檔案和該SWF檔案中列出的所有「載入影片」URL都會計為帳戶頁面總計的一個「頁面」。

## 我要如何防止個別SWF檔案的索引？{#section_E38AD37989EF410B97AF5125057BFD22}

為防止對SWF檔案編製索引，可以向封閉的HTML文檔添加自動機meta標籤(`<meta name="ROBOTS" content="NOINDEX">`)或`<noindex>`標籤。 亦即，包含`<embed>`或`<object>`標籤的檔案。

您也可以使用robots meta標籤(`<meta name="ROBOTS" content="NOFOLLOW">`)來防止SWF檔案中包含的下列URL。 如果封閉的HTML檔案已停用後續功能，則SWF檔案中列為「取得URL」動作的URL將不會後續。

## 我要如何防止SWF檔案在我的網站上建立索引？{#section_DF2606A50E9A44859CFA0D44D7C5F2E4}

若要停用SWF索引功能，請取消選取內容類型&#x200B;**[!UICONTROL Adobe Flash Movies]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)。

您也可以選擇使用[!DNL URL Masks]來停用SWF檔案的索引。

請參閱[將URL遮色片新增至……的索引部分或非索引部分。](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1)。

若要停用SWF索引，請輸入下列其中一個URL遮色片：

* `exclude *.swf` （如果您不使用規則運算式）
* `exclude regexp ^.*\.swf$` （如果您使用規則運算式）

請參閱[規則運算式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

## 我為何無法在我的網站上搜尋中文、日文或韓文SWF檔案？{#section_EE1A3A705AE74148BD195A0CE513A5C4}

網站搜尋／銷售從使用AdobeFlash建立的SWF檔案取得UTF-8。 UTF-8不包含語言指示。 如果您選擇了內容類型&#x200B;**[!UICONTROL Adobe Flash Movies]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)，則必須使用中繼資料插入來指定SWF檔案使用的語言。

請參閱[添加欄位插入定義](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

舊版SWF檔案也不指定字元集。 如果您選取SWF內容類型&#x200B;**[!UICONTROL Adobe Flash Movies]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)，則必須使用中繼資料插入來指定SWF檔案中使用的字元集。

## 一般搜尋{#reference_E2C675162789452A9B99C6633B12CBEF}

常見問題頁面，討論網站搜尋／銷售如何協助造訪您網站的客戶找到所要搜尋的內容。

以下是一般搜尋的常見問題：

* [我是否必須安裝任何軟體才能使用網站……](#section_02AB2AFF71984F9DAA3AF2B7C0847A22)
* [當我的網站超過頁面限制時，會發生什麼情況？](#section_ECA5FA01032D4322BABA4E2C7FE498C1)
* [如何變更每週的電子郵件地址……](#section_AE27F63DD13F425B940C8E7D9ED5C614)
* [我的客戶在網站搜尋／銷售資訊的安全性如何？](#section_5484CB954167412BB7F0480CB0C504B8)
* [我客戶資訊的隱私權如何？](#section_8FB493F15E51454BA92A0C83E14C0CC7)
* [我可以在搜尋中顯示自己的橫幅廣告嗎……](#section_611EB8B32C16418386CB7DC7FB6954B8)

以下是與搜尋功能有關的常見問題：

* [我可以自訂網站的搜尋結果嗎？](#section_A64B3A621B794DF78D35ED06D9C43D0B)
* [我可以看看客戶在我的……](#section_73709E1B0E82478DA7B4D15B6C845F33)
* [我要如何控制哪些內容類型(PDF、文字、Flash、MP3和Microsoft Office)已建立索引並加以搜尋？](#section_0AB8CB4B6BFA4286AA082055FEBFBE1C)
* [是否支援以ASP、JSP、PHP、CFM或Perl為基礎的內容，以動態方式產生網頁？](#section_E279F004F1C542A2B9773B832E7B013F)
* [如何使用同義字來改善搜尋結果……](#section_E6E36E12514F4D7BAB01F8D1AB61D57B)
* [我是否控制搜尋結果的順序……](#section_C6361048502745779D9749A842C4C370)
* [我是否可變更搜尋結果頁面的語言……](#section_6EE41DA8241247D48BBEB061A50599C5)
* [我的Adobe上能有不止一個網站嗎……](#section_AFA8825182094660A71EEC84B8329D6D)
* [我可以搜尋多個網域嗎？](#section_BFBB0E9861D942F095B56CF0A8F16596)
* [我是否可將網站細分為不同的區段，如此……](#section_52153A9DE9F9493B967A70583848B2A4)
* [如何排除我網站的部分內容……](#section_D452EDE153654EF398F4A87780C6D43B)
* [支援哪些字元集？](#section_A62A6F8F15804F968C77F2DEBDE8F8FD)
* [如果我變更或更新我的網站，該怎麼辦？](#section_489050E0EBC14D0594DBBAA0CCF4F6BA)
* [我的網站是否可自動建立索引？](#section_9C7D41636238488691ECDFEE4D4E5103)
* [我在我的網站上使用密碼。我是否仍能使用網站搜尋／銷售？](#section_4618EB5B66704640B5502D1B5CB4B32E)
* [您是否支援對https的搜索和索引，或……](#section_D5BB8B8FBEA4405583E86B4AEC37151B)
* [網站搜尋／銷售是否遵守我網站上的robots.txt檔案？](#section_73BBF6FE93C64C109F45CBC2FA394DB2)
* [我網站的某些部分必須經常更新，因此……](#section_6D2FB1DE1B8A49729F9CCAE2A2770AB3)
* [我可以使用指令碼或程式來啟動增量……](#section_0B6BB039557A42AA876D35D748E17DD0)

## 我是否必須安裝任何軟體才能使用網站搜尋／銷售？{#section_02AB2AFF71984F9DAA3AF2B7C0847A22}

無.這是網站搜尋／銷售的主要優勢。 引擎是專業應用程式，完全托管在我們的高效能伺服器上，並加以維護。 這使得軟體比其他搜尋解決方案更容易使用。 您只需將少量的HTML程式碼新增至您的網頁，讓網站的客戶可以輸入搜尋。 網站搜尋／銷售會處理所有其餘的工作。

## 當我的網站超過頁面限制時，會發生什麼情況？{#section_ECA5FA01032D4322BABA4E2C7FE498C1}

我們會持續提供您的搜尋服務，讓您的訪客可以不間斷地搜尋您的網站。 若要查看您的網站是否超過頁面限制，請檢閱完整索引狀態或即時記錄。

請參閱[關於完整索引](../c-about-index-menu/c-about-full-index.md#concept_C69BD21863FD4856B49326F35DB570D3)。

請參閱[檢視即時或分段的完整索引記錄……](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8)。

## 如何變更每週報表的傳送電子郵件地址？{#section_AE27F63DD13F425B940C8E7D9ED5C614}

每週報告會傳送給每個作用中帳戶的擁有者。 您可以按一下&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]**&#x200B;來變更電子郵件地址。 如果您有多個作用中的搜尋帳戶，則所有電子報都會傳送至新位址。

請參閱[設定您的個人使用者資訊](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6)。

## 我的客戶在網站搜尋／銷售資訊的安全性如何？{#section_5484CB954167412BB7F0480CB0C504B8}

網站搜尋／銷售是安全、快速、穩定且易於使用的。 您不會被迫使用Cookie（雖然您可以的話）來使用我們的產品，而且敏感資訊（例如密碼）永遠不會放在任何URL連結上，這些URL連結稍後可從您的瀏覽器中擷取。

## 我客戶資訊的隱私權如何？{#section_8FB493F15E51454BA92A0C83E14C0CC7}

Adobe致力於尊重其客戶和訪客的隱私權。 請參閱Adobe[隱私中心](https://www.adobe.com/privacy.html)。

## 我可以在搜尋結果頁面上顯示自己的橫幅廣告嗎？{#section_611EB8B32C16418386CB7DC7FB6954B8}

是.您可以控制搜尋結果的外觀和內容。 在您網站的搜尋結果範本中，您可以建立連至您自己橫幅交換網路的連結，例如LinkExchange或SmartClicks。 您的訪客進行的任何點擊都會正確計入您的橫幅廣告交換帳戶。

## 我可以自訂網站的搜尋結果嗎？{#section_A64B3A621B794DF78D35ED06D9C43D0B}

是.這是網站搜尋／銷售的獨家功能。 透過我們先進的範本技術和HTML的一些知識，您可以精確控制搜尋結果的顯示方式。

請參閱[搜尋範本標籤](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

您的伺服器和網站搜尋／銷售伺服器之間的轉換完全順暢且對客戶不可見。 如果您不知道HTML，或您沒有時間建立自訂範本，則可從Adobe內部專業網頁開發人員團隊所建立的各種吸引人、現成可用的範本中選擇。

## 我可以在我的網站上看到客戶正在搜尋哪些內容嗎？{#section_73709E1B0E82478DA7B4D15B6C845F33}

是.我們會持續提供搜尋統計資料，以瞭解過去兩個月來訪客在您網站上進行的搜尋。 您可以隨時在產品功能表的報表下檢視這些統計資料。 搜尋報表會提供您有關訪客在您網站上尋找哪些內容的重要資訊。 您可使用此資訊來改善設計或調整網站搜尋／銷售引擎，以更好地為訪客服務。

## 我要如何控制哪些內容類型(PDF、文字、Flash、MP3和Microsoft Office)已建立索引並加以搜尋？{#section_0AB8CB4B6BFA4286AA082055FEBFBE1C}

您可以輕鬆設定帳戶，以啟用或停用在PDF檔案、純文字檔案、Flash影片、MP3檔案或Microsoft Office檔案中找到的文字索引和搜尋功能。

這些設定會在[!DNL Staged Content Types]頁面上控制。

請參閱[關於內容類型](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07)。

## 是否支援以ASP、JSP、PHP、CFM或Perl為基礎的內容，以動態方式產生網頁？{#section_E279F004F1C542A2B9773B832E7B013F}

靜態或動態產生的HTML網頁會建立索引，包括從資料庫或任何其他後端程式建立的網頁。 由於瀏覽器所看到的HTML程式碼已建立索引，因此只要這些後端架構產生HTML頁面，您就可以在網站上使用網站搜尋／銷售。

搜尋機器人會從[!DNL Account Settings]中指定之網站位址的第一頁開始，爬行您的網站，並追蹤頁面間的連結。

請參閱[設定您的帳戶設定](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

當搜尋自動機爬蟲並索引您網站的所有頁面時，您可以使用搜尋引擎來搜尋您的網站。 換言之，如果動態產生的檔案與來自其他頁面的連結交織在您的網站中，搜尋機器人仍可以編目並索引動態內容。

在您的網站內容編目並建立索引後，您網站的客戶可以在已建立索引的內容中搜尋資訊。

## 如何使用同義字來改善網站的搜尋結果？{#section_E6E36E12514F4D7BAB01F8D1AB61D57B}

當您希望訪客尋找與其搜尋查詢相關的頁面時，可以使用同義字。

例如，假設您的網站上有一個頁面，其中包含要銷售的產品價目表。 不過，在檢查網站搜尋／銷售所提供的搜尋報表後，您會發現客戶在搜尋中會尋找「成本」、「費用」或「費用」。 這些字詞不會在搜尋結果中顯示您的價目表頁面。 使用[!DNL Dictionaries]中的[!DNL Add Synonyms]功能，您可以指定這些單字都是同義字，而且無論客戶使用哪個搜尋詞，您的客戶都可以找到您的價目表。

請參閱[關於字典](../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034)。

## 我是否可控制搜尋結果的順序？{#section_C6361048502745779D9749A842C4C370}

是.使用進階關聯介面，您可以控制特定搜尋查詢傳回的頁面。 如果您想確定客戶在查詢特定字詞時會看到特定頁面，此功能會很有用。

請參閱[新增中繼標籤欄位](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。

## 我可以變更搜尋結果頁面的語言嗎？{#section_6EE41DA8241247D48BBEB061A50599C5}

是.網站搜尋／銷售範本在可讓您建立使用您選擇的語言並符合網站外觀的結果頁面時十分靈活。

範本包含文字、標準HTML標籤和特殊標籤的組合，這些標籤定義為顯示搜尋結果。 當客戶執行搜索時，搜索自動機讀取模板，使用標準HTML標籤輸出文本，並基於特殊模板標籤插入結果連結。

請參閱[搜尋範本標籤](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

如果要更改結果語言，可以編輯模板上顯示的英文文本。

請參閱[編輯演示或傳輸模板](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3)。

## 我可以在我的Adobe客戶登入中擁有多個網站嗎？{#section_AFA8825182094660A71EEC84B8329D6D}

是.只需單一Adobe客戶登入，您就可以管理許多不同網站的不同搜尋引擎。 在「帳戶」下選擇並管理帳戶。

請參閱[選擇要使用的不同帳戶](../c-about-accounts-menu.md#task_03C0FE918E2D44529CDC3B8DB75D1B26)。

## 我可以搜尋多個網域嗎？{#section_BFBB0E9861D942F095B56CF0A8F16596}

是.您可以使用[!DNL URL Entrypoints]來設定存取多個網域。 提供您擁有之其他網域的URL登入點。 請記住，您必須擁有索引未擁有的網域的權限。

請參閱[關於URL入口點](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

## 我可以將網站細分為不同的區段，讓客戶可以個別或整個網站搜尋其中任何區段嗎？{#section_52153A9DE9F9493B967A70583848B2A4}

是.包含「系列」功能，可讓客戶搜尋您網站的特定區域，以快速找到所要的內容。

請參閱[關於系列](../c-about-settings-menu/c-about-searching-menu.md#concept_62E42ACE53D54EEE9273433B86259127)。

例如，客戶可以搜尋與產品銷售資訊相關的URL集合，或是與支援服務相關的URL集合。 您可以設定系列，讓客戶看到系列的下拉式清單或一組核取方塊。

## 如何排除網站的部分內容，使其不受搜尋？{#section_D452EDE153654EF398F4A87780C6D43B}

是.指定URL遮色片，以決定您要包含或排除在索引之外的網站頁面。 URL遮色片會決定網站頁面是否出現在您的搜尋結果中。

請參閱[關於URL遮色片](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164)。

請參閱[關於URL遮色片指令碼](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B)。

若要防止搜尋個別網頁的部分，您可以排除頁面的某些部分以建立索引。 使用`<noindex>`和`</noindex>`標籤環繞文字。 如果您想從搜尋中排除導覽文字，此方法很實用。

## 支援哪些字元集？{#section_A62A6F8F15804F968C77F2DEBDE8F8FD}

網頁通常會使用類似下列的中繼標籤來指定字元集：

`<META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=iso-8859-1">`

網站搜尋／銷售引擎會使用現今網際網路上使用的所有常用字元集，正確索引網頁。 部分支援的字元集包括：

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>阿拉伯文(ISO-8859-6) </p> </td> 
   <td colname="col2"> <p>繁體中文；Big5) </p> </td> 
   <td colname="col3"> <p>日文(Shift_JIS) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>阿拉伯文(Windows-1256) </p> </td> 
   <td colname="col2"> <p>繁體中文；EUC-TW) </p> </td> 
   <td colname="col3"> <p>俄文(KOI8-R) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>波羅的海(ISO-8859-4) </p> </td> 
   <td colname="col2"> <p>西里爾文(ISO-8859-5) </p> </td> 
   <td colname="col3"> <p>南歐(ISO-8859-3) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>波羅的海(Windows-1257) </p> </td> 
   <td colname="col2"> <p>西里爾文(Windows-1251) </p> </td> 
   <td colname="col3"> <p>土耳其文(ISO-8859-9) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中歐(ISO-8859-2) </p> </td> 
   <td colname="col2"> <p>希臘文(ISO-8859-7) </p> </td> 
   <td colname="col3"> <p>土耳其文(Windows-1254) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中歐(Windows-1250) </p> </td> 
   <td colname="col2"> <p>希臘文(Windows-1253) </p> </td> 
   <td colname="col3"> <p>Unicode(UTF-8) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中文(ISO-2022-CN) </p> </td> 
   <td colname="col2"> <p>希伯來文(ISO-8859-8) </p> </td> 
   <td colname="col3"> <p>US-ASCII(us-ascii) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中文(ISO-2022-CN-EXT) </p> </td> 
   <td colname="col2"> <p>希伯來文(Windows-1255) </p> </td> 
   <td colname="col3"> <p>西歐(ISO-8859-1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中文(簡體；EUC-CN) </p> </td> 
   <td colname="col2"> <p>日文(EUC-JP) </p> </td> 
   <td colname="col3"> <p>西歐(ISO-8859-15) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中文(簡體；GB2312) </p> </td> 
   <td colname="col2"> <p>日文(ISO-2022-JP) </p> </td> 
   <td colname="col3"> <p>西歐語系(Windows-1252) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中文(簡體；GBK) </p> </td> 
   <td colname="col2"> <p>日文(ISO-2022-JP-1) </p> </td> 
   <td colname="col3"> <p>西歐文(x-mac-roman) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>中文(簡體；HZ-GB-2312) </p> </td> 
   <td colname="col2"> <p>日文(ISO-2022-JP-2) </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

請聯絡技術支援以詢問上述未列出的字元集。

## 如果我變更或更新我的網站，該怎麼辦？{#section_489050E0EBC14D0594DBBAA0CCF4F6BA}

變更網站內容後，您可以執行完整索引或增量索引。 網站搜尋／銷售下載及索引任何變更的網站內容。 建立索引完成後，您的客戶可以搜尋新內容。 您也可以在特定時間和特定日期排程網站的自動索引。

請參閱[執行即時或分段網站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

請參閱[執行即時或分段網站的遞增索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。

請參閱[設定即時網站的完整索引排程](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0)。

請參閱[設定即時網站的遞增索引排程](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33)。

## 我的網站是否可自動建立索引？{#section_9C7D41636238488691ECDFEE4D4E5103}

是.您可以每天排程網站的自動索引。

除了每日自動索引外，您還可以選擇頻繁變更其網站的部分，以增量方式建立索引。 在已排程自動索引的日，您可以控制索引發生的時間。 此外，您隨時都可以手動啟動網站索引。

請參閱[設定即時網站的完整索引排程](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0)。

請參閱[設定即時網站的遞增索引排程](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33)。

## 我在我的網站上使用密碼。 我是否仍能使用網站搜尋／銷售？{#section_4618EB5B66704640B5502D1B5CB4B32E}

如果您使用HTTP基本驗證以密碼保護網站的某些部分，您可以指定網站搜尋／銷售可用來為網站建立索引的領域和密碼。

請參閱[新增密碼以存取您網站中需要的區域……](../c-about-settings-menu/c-about-crawling-menu.md#task_DED19D476FF04B48BB6456D5ECB8628A)。

## 您是否支援https或安全伺服器內容的編目和索引？{#section_D5BB8B8FBEA4405583E86B4AEC37151B}

是.您可以在安全伺服器(https)上編目和建立內容索引。

## 網站搜尋／銷售是否遵守我網站上的robots.txt檔案？{#section_73BBF6FE93C64C109F45CBC2FA394DB2}

是.機器人排除協定是符合的。 搜尋機器人會檢查robots.txt檔案（如果它存在於您的網站上）。 如果您的robots.txt檔案排除所有自動機來搜尋您的網站，則網站搜尋／銷售自動機也會排除。 若要僅允許網站搜尋／銷售自動機編目您的網站，請將robots.txt檔案的內容設定為：

```
User-agent: Atomz/1.0 
Disallow:
```

```
User-agent: * 
Disallow: /
```

您可以在以下網址進一步瞭解Web機器人和機器人排除協定：

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

## 網站的某些部分必須經常更新，以便客戶獲得最準確的搜尋結果。 增量索引是否有助於解決此問題？{#section_6D2FB1DE1B8A49729F9CCAE2A2770AB3}

是.此案例是建立遞增索引功能以促進網站搜尋／銷售的原因。 增量索引的主要優點是，它可讓公司頻繁地為網站中不斷變化的部分建立動態索引。 此類功能可確保您以「最快」的精確度顯示搜尋結果。

請參閱[執行即時或分段網站的遞增索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。

請參閱[設定即時網站的遞增索引排程](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33)。

## 後端資料庫是否支援動態產生的網頁，例如產品目錄或庫存管理系統？{#section_26896C556483457E879785E751583B16}

靜態或動態產生的HTML網頁，包括從資料庫建立的頁面或任何其他後端程式都會建立索引。 由於瀏覽器檢視的HTML程式碼已建立索引，因此只要後端資料庫資訊產生於HTML頁面，您就可以在網站上使用網站搜尋／銷售。

搜尋機器人會從[!DNL Account Settings]中指定之網站位址的第一頁開始，爬行您的網站，並追蹤頁面間的連結。

請參閱[設定您的帳戶設定](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

當搜尋自動機爬蟲並索引您網站的所有頁面時，您可以使用搜尋引擎來搜尋您的網站。 換言之，如果動態產生的檔案與來自其他頁面的連結交織在您的網站中，搜尋機器人仍可以編目並索引動態資料庫內容。

在您的網站內容編目並建立索引後，您網站的客戶可以在已建立索引的內容中搜尋資訊。

您可以輕鬆啟用完整內容搜尋，或以主題為基礎的搜尋範圍較窄，但僅限於標題中的資訊、中繼描述、中繼關鍵字檔案標籤，或全部三種。 使用中繼資料定義，您也可以在實際搜尋結果中建立自訂顯示欄位，例如產品影像。

請參閱[新增中繼標籤欄位](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。

## 我可以使用指令碼或程式來啟動網站的增量索引嗎？{#section_0B6BB039557A42AA876D35D748E17DD0}

是.您可以使用指令碼或程式來起始網站的增量索引，以及在內容變更或更新時，ping伺服器來索引網站。

請參閱[關於指令碼化索引](../c-about-index-menu/c-about-scripted-index.md#concept_34F58D551BC04BFB8ADC294B9DA9199D)。

## 功能實作{#reference_2D0C4A80B8D64051BA9694D562DCE663}

一個常見問題頁面，討論[!DNL Search&Promote]中各種功能實作。

以下是網站[!DNL Search&Promote]中功能實作的常見問題：

* [為什麼我的業務規則沒有運作？](#section_7FEB60383D8A4B11A60DFF9067274699)
* [為什麼排程索引、啟動索引錯誤，以及啟動分段索引時遇到問題？](#section_E05758193DF5436784B0145839989F75)
* [我的指數大小限制超出了我允許的界限。為什麼會發生這種情況，我該如何修正？](#section_12E7DA979C4C4B1D8A3A6415FC3DDA70)

## 為什麼我的業務規則沒有運作？{#section_7FEB60383D8A4B11A60DFF9067274699}

設定橫幅廣告出現時的業務規則，或協助決定結果出現的順序。 您也可以設定Facet中項目的位置，以及指定搜尋使用的範本。
重新排序業務規則，以變更其在簡報範本上執行的順序。 業務規則按照定義的順序運行；也就是說，規則的訂單編號越高，在流程中執行的時間越晚，超過了之前的規則。 通過在「業務規則」頁上表的「順序」列中輸入新編號，可以重新排序規則。

請參閱[關於業務規則](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD)。

## 為什麼排程索引、啟動索引錯誤，以及啟動分段索引時遇到問題？{#section_E05758193DF5436784B0145839989F75}

當生成索引時，無論其是完整索引還是增量索引編目狀態資訊都會即時顯示。 例如，您可以檢視索引建立程式期間發生的開始時間、用時和任何錯誤。 此外，還會顯示有關上一個索引狀態的資訊。 使用此資訊來疑難排解您遇到的索引錯誤。

如需排程索引，請參閱[設定即時網站的完整索引排程](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0)和[設定即時網站的增量索引排程](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33)。

如需啟動分段索引，請參閱[執行即時或分段網站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)或[執行即時或分段網站的遞增索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。

## 我的指數大小限制超出了我允許的界限。 為什麼會發生這種情況，我要如何解決？{#section_12E7DA979C4C4B1D8A3A6415FC3DDA70}

網站可能會逐漸成長，而且隨著時間推移，Search&amp;Promote會「發現」新增的更多檔案和網頁。 最終，您的帳戶可能會超過您的索引大小限制。在這種情況下，您可以考慮使用&#x200B;**[!UICONTROL URL Mask]**。 此功能可隱藏文檔和網頁，使其不需要或不需要建立索引的索引編目，從而減少索引大小。 另一個選擇是聯絡技術支援，讓您的索引大小限制在帳戶中設定得更大。

請參閱[關於URL遮色片](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164)。

如果您不確定該做什麼，請聯絡技術支援。 可能有許多其他變數會影響您的索引大小，若經過調整，可能也會影響您帳戶的帳單。

## 國際{#reference_F017C2968BFB446499EF1D3CE2CAC0FE}

一個常問的問題頁面，討論對19種以上語言的索引和搜尋支援，包括多位元組亞洲語言，例如中文（簡體和繁體）、日文和韓文。

以下是語言和字元集的常見問題：

* [控制搜索查詢的字元集編碼的內容……](#section_DF2E8570AFC2480FA199FD26C941A22F)
* [搜索的頁面的編碼與……的編碼匹配](#section_9E544F3DB7DE41618DC1BC8224B32C5A)
* [搜尋結果頁面使用何種編碼？](#section_DA68670F35D54EAABF7DBB010F4409BF)
* [我是否可在Unicode、UTF-8、編碼頁面上使用網站搜尋／銷售？](#section_130997CB08934A13A5261D85CF88040C)
* [我為何無法在網站上搜尋中文、日文或韓文PDF檔案？](#section_539AFF482F814D28B5929F683D2F2175)
* [我為何無法在我的網站上搜尋中文、日文或韓文SWF檔案？](#section_9C0849528AFF4C10AA97A2C912992638)
* [為什麼我無法在我的網站上搜尋中文、日文或韓文的Microsoft Office檔案？](#section_6764BA6863AF492EBA9BE5CCC12CDD1F)
* [為什麼我無法在我的網站上搜尋中文、日文或韓文MP3檔案？](#section_DB6D60CF46F94125BF4E54AF3036DBFC)
* [我需要做點特別的事來……](#section_A8BA6DDD3A6048319D3530BCFD6DA1A5)
* [中文、日文或韓文字型為何會出現在Netscape 4.7及更舊版本的搜尋結果中？](#section_DF42567063304F918D406AC76529DFB7)

## 什麼控制搜尋查詢的字元集編碼？{#section_DF2E8570AFC2480FA199FD26C941A22F}

您的搜尋帳戶的「Web表單」區段包含您用來新增搜尋功能至網站的範例搜尋表單。 如果您查看此搜尋表單程式碼，可以找到類似下列的行：

`<input type=hidden name="sp_f" value="iso-8859-1">`

此程式碼行會告訴搜尋引擎傳入的查詢是以iso-8859-1編碼，這是西歐語言的常用編碼。 您可以前往產品功能表，然後按一下「**[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]**」，以變更此設定。 在[!DNL Personal Information]頁面的&#x200B;**[!UICONTROL Character Encoding]**&#x200B;下拉式清單中，選取新的編碼。

請參閱[設定您的個人使用者資訊](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6)。

您也可以編輯搜尋表單的`sp_f`行，手動變更網頁上的編碼值。 請記住，搜尋表單的`sp_f`值必須符合顯示表單之頁面的字元集編碼。

## 僅搜尋其編碼與搜尋查詢編碼相符的頁面嗎？{#section_9E544F3DB7DE41618DC1BC8224B32C5A}

預設情況下，否。 只要您的網站頁面正確識別其字元集編碼，即使頁面使用多種編碼，搜尋查詢的編碼和頁面的編碼之間也會進行必要的轉換。

## 搜尋結果頁面使用何種編碼？{#section_DA68670F35D54EAABF7DBB010F4409BF}

帳戶的字元集編碼會決定結果範本的預設編碼。

請參閱[設定您的個人使用者資訊](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6)。

您可以進一步瞭解如何在HTML範本中指定字元集。

請參閱[搜尋範本標籤](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

## 我是否可在Unicode、UTF-8、編碼頁面上使用網站搜尋／銷售？{#section_130997CB08934A13A5261D85CF88040C}

是.但是，Unicode字元集（例如UTF-8）無法提供足夠的資訊來判斷頁面所使用的語言。 若要正確搜尋這些頁面，必須指定語言。 要確定文檔語言，資訊按以下順序處理：

* 您的伺服器為檔案傳送的內容語言HTTP標題。
* 文檔`<HEAD>`部分中的META元素（例如`META HTTP-EQUIV="Content-Language" Content="ja_JP"`）。

* `<HTML>`標籤的LANG屬性（例如`<HTML LANG="ja_JP">`）。

如果您的伺服器未設定為傳送「內容語言HTTP」標題，而您的檔案既不包含語言META元素，也不包含`<HTML>`標籤的語言屬性，您可以使用中繼資料插入來指定適當的語言。

請參閱[添加欄位插入定義](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

## 我為何無法在網站上搜尋中文、日文或韓文PDF檔案？{#section_539AFF482F814D28B5929F683D2F2175}

網站搜尋／銷售從Adobe PDF檔案取得UTF-8，而無語言指示。 如果您選取&#x200B;**[!UICONTROL PDF Documents]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)，則必須使用中繼資料插入來指定PDF檔案中使用的語言。

請參閱[添加欄位插入定義](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

## 我為何無法在我的網站上搜尋中文、日文或韓文SWF檔案？{#section_9C0849528AFF4C10AA97A2C912992638}

網站搜尋／銷售從AdobeFlash影片檔取得UTF-8，這些影片檔案是使用AdobeFlash建立，沒有語言指示。 如果您選擇了內容類型&#x200B;**[!UICONTROL Adobe Flash Movies]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)，則必須使用中繼資料插入來指定SWF檔案中使用的語言。

對於Flash版本4或更舊版本的SWF檔案，不指定檔案中字元的字元集。 如果您選擇了內容類型&#x200B;**[!UICONTROL Adobe Flash Movies]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)，則必須使用中繼資料插入來指定SWF檔案中使用的字元集。

請參閱[添加欄位插入定義](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

## 為什麼我無法在我的網站上搜尋中文、日文或韓文的Microsoft Office檔案？{#section_6764BA6863AF492EBA9BE5CCC12CDD1F}

網站搜尋／銷售從Microsoft Office檔案（Microsoft Word、Microsoft Excel和Microsoft PowerPoint）取得UTF-8，而無語言指示。 如果您選擇了內容類型&#x200B;**[!UICONTROL Microsoft Office Files]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)，則必須使用元資料插入來指定Microsoft Office檔案中使用的語言。

請參閱[添加欄位插入定義](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

## 為什麼我無法在我的網站上搜尋中文、日文或韓文MP3檔案？{#section_DB6D60CF46F94125BF4E54AF3036DBFC}

如果您選擇內容類型&#x200B;**[!UICONTROL Text in MP3 Music Files]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)，則必須使用中繼資料插入來指定用於編碼MP3檔案的字元集。

請參閱[添加欄位插入定義](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

## 我是否需要做任何特殊動作，才能讓網站上的。txt檔案正確索引？{#section_A8BA6DDD3A6048319D3530BCFD6DA1A5}

如果您選擇了內容類型&#x200B;**[!UICONTROL Text Documents]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)，則必須使用元資料插入來指定用於編碼。txt檔案的字元集。

請參閱[添加欄位插入定義](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

## 中文、日文或韓文字型為何會出現在Netscape 4.7及更舊版本的搜尋結果中？{#section_DF42567063304F918D406AC76529DFB7}

如果您的帳戶使用預設範本、其中一個現成可用的範本，或以這些範本為基礎的範本，則可能包含將Arial或Helvetica指定為字型的字型標籤。 例如, `<font face="arial, helvetica" size="+1">`。當使用Arial或Helvetica字型面時，Netscape 4.7和舊版不會顯示中文、日文或韓文字元。 移除`face`屬性，或以更適合中文、日文或韓文的字型面取代字型面。

## 低頁數{#reference_4344E3E3CB2948939860F8C078BD7773}

常問的問題頁面，討論與低索引頁面計數相關的常見問題。

以下是關於低索引頁面計數的常見問題：

* [您檢查過索引日誌嗎？](#section_D6626536DC3D40DDA4A1224F1CB276BF)
* [您的URL中是否有輸入錯誤？](#section_BD2CEABC5D0F4A0DA38F3AD72ABBA676)
* [入口點網頁是否有其他頁面的連結……](#section_1C2D6ED54E7249268B555D9DC33352B3)
* [是您網站上內嵌於……的其他頁面的連結](#section_EE34A67D60A844EBB0921C03544FF63E)
* [網頁上的HTML標籤是否位於……](#section_F31A2F5D2C284AC084158A5BD763DC5D)
* [您的……中是否有錯誤的HTML注釋標籤](#section_D1C39D79341845CB9C38579AABDF3A24)
* [您的網頁是否包含其他網頁的連結……](#section_F8082759184049AAA8FA6342C1F84389)
* [您是否在URL中使用虛擬網域服務……](#section_2861F09EA21A45E6B7E15F032739CDF3)
* [您的網頁是否使用中繼重新整理標籤？](#section_5A2F544C237C49B8B1A7FE0C45371C0D)
* [您的網頁是否使用中繼機器人標籤？](#section_36275A33DDFE4620BABA948F8A63DBD2)
* [您的網站是否使用Robots排除檔案？](#section_BF7B663347814F58AD736066C86B7D25)

## 您檢查過索引日誌嗎？{#section_D6626536DC3D40DDA4A1224F1CB276BF}

索引記錄檔包含網站搜尋／銷售自動機在建立網站索引時收集的詳細資訊。 記錄檔包含已編目和遇到錯誤的連結清單。 檢查索引日誌是確定網站上所有頁面未建立索引的最佳開始位置。

請參閱[檢視即時或分段的完整索引記錄……](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8)。

請參閱[查看即時或分段的增量索引日誌……](../c-about-index-menu/c-about-incremental-index.md#task_E668E1F1240C476DAA1CA783DC728232)。

## 您的URL中是否有輸入錯誤？{#section_BD2CEABC5D0F4A0DA38F3AD72ABBA676}

當您在HTML表單中輸入冗長的URL時，可能會導致一或多個印刷錯誤。 請記住，URL不應包含任何空格。 此外，請注意，有些Web伺服器會以區分大小寫的方式處理URL。

在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**」。 在[!DNL Staged URL Entrypoints]頁面上，驗證以下內容：

* 您的URL中沒有任何印刷錯誤。
* URL中的字元都使用正確的外框。
* URL中沒有空格字元。

若要測試您的URL登入點，請複製URL並貼至網頁瀏覽器，以查看您的網站是否出現。 如果未顯示，請再次勾選，以確保您的URL路徑未發生任何錯誤。

請參閱[關於URL入口點](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

## 登入點網頁是否包含您網站上其他頁面的連結？{#section_1C2D6ED54E7249268B555D9DC33352B3}

網站搜尋／銷售機器人會像客戶一樣爬行您的網站；依循頁面間的連結。 在搜尋機器人找到您網站上的其他頁面並建立索引之前，連結必須存在於入口點網頁中。

請參閱[新增多個您要建立索引的URL入口點](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)。

## 您網站上其他頁面的連結是否內嵌在JavaScript中？{#section_EE34A67D60A844EBB0921C03544FF63E}

您可以在您的網站上使用複雜的導覽技術，例如使用JavaScript連結至其他頁面的滾動動作和功能表。 不過，網站搜尋／銷售自動機無法跟隨內嵌於JavaScript的連結。

您可使用的一個解決方案，就是在包含JavaScript的HTML中，將其他頁面的隱藏連結置入。 雖然您網站的客戶看不到這些連結，但搜尋機器人仍會尋找和編目這些連結。 您可以將隱藏的標籤放置在頁面底部的`</body>`標籤之前。 它們可能如下所示：

```
<a href="/mydir/mypag1.html"></a> 
<a href="/mydir/mypag2.html"></a>
```

另一個解決方案是將網站上其他頁面的URL列為要編目和索引的入口點。 以`https://`開頭的URL，如下所示：

```
https://www.mydomain.com/mydir/mypag1.html 
https://www.mydomain.com/mydir/mypag2.html
```

請參閱[新增多個您要建立索引的URL入口點](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)。

## 網頁上的HTML標籤是否順序無效？{#section_F31A2F5D2C284AC084158A5BD763DC5D}

HTML規格要求`<html>`、`<head>`和`<body>`標籤遵循HTML文檔中的特定序列。 所有網頁中的標籤都必須有下列順序：

```
<html> 
<head> 
...  
<i>head tags go here</i> ... 
</head> 
<body> 
...  
<i>body tags go here</i> ... 
</body> 
</html>
```

如果HTML標籤順序不正確，則網站搜尋／銷售自動機無法正確解析您的網頁並建立其索引。 以下是未在正確順序中的標籤範例：

```
<body> 
<head> 
...  
<i>head tags are here</i> ... 
</head> 
...  
<i>body tags are here</i> ... 
</body>
```

在這種情況下，請將`<html>`、`<head>`和`<body>`標籤置於網頁上的正確序列中。

## 您的網頁中是否有錯誤的HTML註解標籤？{#section_D1C39D79341845CB9C38579AABDF3A24}

請確定您仔細檢閱並更正網頁中的任何無效HTML注釋。

HTML規範要求HTML注釋以字元`<!--`開頭，以字元`-->`結尾。 很容易忽略格式錯誤的注釋，這些注釋會導致網站搜尋／銷售自動機不正確剖析您網頁上的標籤。 格式錯誤的註解可能導致網站搜尋／銷售自動機遺漏其他必須加以剖析的重要標籤。 請留意網頁中`<body>`標籤前的注釋。

以下是正確格式注釋的示例：

`<!-- This HTML comment is OK. -->`

以下是錯誤格式注釋的範例：

```
<!- This HTML comment is improperly formed. -> 
<! This HTML comment is also improperly formed. >
```

## 您的網頁是否包含其他網域頁面的連結？{#section_F8082759184049AAA8FA6342C1F84389}

通常，網站可由網站伺服器上實際存在且網域位址不同的頁面組成。 例如，若您的主要網站位址為：

`https://www.mydomain.com/`

您的網站可能也會在其他網域上有頁面，例如：

`https://www.otherdomain.com/`

依預設，網站搜尋／銷售自動機不會跟隨除主網域以外網域的連結。 不過，只要為搜尋帳戶設定額外的登入點，您就可以輕鬆為多個網域建立索引。

在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**」。 新增您網站的「主要網站入口點」URL。 然後，將其他URL登入點新增至包含網站頁面的任何其他網域。 例如，您可將主要URL入口點設為：

`https://www.mydomain.com/`

並新增下列其他網站URL入口點：

`https://www.otherdomain.com/`

## 您的URL是否使用虛擬網域服務？{#section_2861F09EA21A45E6B7E15F032739CDF3}

您可能使用虛擬網域服務（有時稱為「網域重新導向服務」），為客戶提供更佳的URL以連至您的網站。 例如，假設您網站的實際位址如下：

`https://www.myispdomain.com/~myname/mywebpages/`

不過，您使用虛擬網域服務，讓客戶可以透過下列位址來到您的網站：

`https://myname.adomain.com/`

或 

`https://adomain.com/myname/`

依預設，網站搜尋／銷售自動機不會跟隨除主網域以外網域的連結。 不過，只要為搜尋帳戶設定額外的登入點，您就可以輕鬆為多個網域建立索引。

在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**」。 將「主網站URL入口點」新增至網站的虛擬網域名稱。 然後，新增額外的登入點至您網站實際所在的網域。

例如，您可將主要URL入口點設定為：

`https://myname.adomain.com/`

並新增下列其他網站URL入口點：

`https://www.myispdomain.com/~myname/mywebpages/`

## 您的網頁是否使用中繼重新整理標籤？{#section_5A2F544C237C49B8B1A7FE0C45371C0D}

許多網站的首頁在`<head>...</head>`標籤之間包含中繼重新整理標籤，類似下列：

`<meta http-equiv="Refresh" content="0;URL=https://www.adomain.com/apath/afile.html">`

在某些情況下，網站搜尋／銷售自動機無法跟隨中繼重新整理URL來索引您網站的內容。 透過設定額外的入口點，可輕鬆解決此問題。

在產品功能表上，按一下「**[!UICONTROL Settings]** >編目> **[!UICONTROL URL Entrypoints]**」。 將另一個入口點新增至meta refresh標籤的URL。

## 您的網頁是否使用中繼機器人標籤？{#section_36275A33DDFE4620BABA948F8A63DBD2}

有時網頁會使用中繼自動機標籤來控制定期嘗試編目網站的網頁自動機。 中繼自動機標籤會出現在網頁的`<head>...</head>`標籤之間，其外觀類似下列標籤：

`<meta name="robots" content="noindex, nofollow">`

由於網站搜尋／銷售機器人本身就是網頁機器人，所以它會遵循中繼機器人標籤的方向。 以此方式排除其他自動機，也排除網站搜尋／銷售自動機。

您可以在以下網址進一步瞭解Web機器人和機器人排除協定：

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

移除或修改您要在網站上建立索引之網頁上的中繼自動機標籤。

## 您的網站是否使用Robots排除檔案？{#section_BF7B663347814F58AD736066C86B7D25}

有時，網站的頁面名為robots.txt，會排除所有或特定的機器人進行編目。 若要查看您的網站是否有robots.txt檔案，請在頂層網域下方尋找，如下所示：

`https://www.yourdomain.com/robots.txt`

robots.txt檔案的內容看起來類似下列文字：

```
User-agent: * 
Disallow: /
```

由於網站搜尋／銷售機器人本身是網頁機器人，因此會遵循robots.txt檔案中的指示——排除網站搜尋／銷售機器人。 若要解決此問題，請編輯robots排除檔案(robots.txt)，以允許網站搜尋／銷售自動機按如下方式編目和索引您的網站：

```
User-agent: Atomz/1.0 
Disallow: 
 
User-agent: * 
Disallow: /
```

## Microsoft Office {#reference_A85FCC8A96514A7584F4D2A8AC8111D1}

常見問題頁面，討論在網站上建立Microsoft® Office檔案索引和搜尋的支援。

以下是有關Microsoft Office檔案的常見問題：

* [在Microsoft Office檔案中建立索引的是什麼？](#section_8681DADFCFE24B7787B1FC08D431EE28)
* [未在Microsoft Office檔案中建立索引的內容……](#section_BD53BDABFDD94D7EB0E1F55EC18017BB)
* [Microsoft Office檔案與HTML頁面的索引方式有何不同……](#section_C104B44684F340549A6B9EB8F39EDDBB)
* [如何防止Microsoft Office檔案建立索引……](#section_FEBA71274CD14CB99731ADF982087F4C)

## 在Microsoft Office檔案中建立索引的是什麼？{#section_8681DADFCFE24B7787B1FC08D431EE28}

Microsoft Word檔案、Microsoft Excel檔案和Microsoft PowerPoint檔案的完整內容已建立索引。

Microsoft Word檔案的下列部分已建立索引：

* 標題
* 關鍵字
* 主旨（說明）
* 文字內容
* 其他檔案的超連結

Microsoft Excel檔案的下列部分已建立索引：

* 標題
* 關鍵字
* 主旨（說明）
* 儲存格中的文字
* 儲存格中數值公式的值

Microsoft PowerPoint檔案的下列部分已建立索引：

* 標題
* 關鍵字
* 主旨（說明）
* 每張投影片上的文字

## 哪些內容未在Microsoft Office檔案中建立索引？{#section_BD53BDABFDD94D7EB0E1F55EC18017BB}

包含在Microsoft Office檔案中的圖形，或包含圖形中的任何文字，都不會建立索引。 自訂屬性定義不會建立中繼資料的索引。 特殊欄位中的某些文字（例如PowerPoint檔案中的頁首和頁尾）也不會建立索引。

## Microsoft Office檔案與HTML頁面的索引有何不同？{#section_C104B44684F340549A6B9EB8F39EDDBB}

搜尋自動機對Microsoft Office檔案和HTML檔案進行索引的不同之處在於，每個HTML檔案都是個別頁面，而單一Microsoft Office檔案可代表數百個頁面。 因此，每個頁面在Microsoft Office檔案中都會計為您搜尋帳戶下的個別頁面。

## 如何防止在我的網站上建立Microsoft Office檔案的索引？{#section_FEBA71274CD14CB99731ADF982087F4C}

如果不希望搜索自動機搜索和索引Microsoft Office檔案，請取消選擇內容類型&#x200B;**[!UICONTROL Microsoft Office Files]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)。

您也可以使用[!DNL URL Masks]來停用Microsoft Office檔案的索引。

輸入下列URL遮色片：

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>如果您不使用規則運算式 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_DFEC911DA11C484C8E4671A0F00E1F88"> 
     <li id="li_2E50374E3869426B97353A5A8CBE09EC">exclude *.doc </li> 
     <li id="li_9089D11161524D90849CA88F703772B6">exclude *.xls </li> 
     <li id="li_7F6CFC6212E64C04AAF38E21A667C763">exclude *.ppt </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>如果您使用規則運算式 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_012A45C3EC04460EA09C0ECFB49A8FA9"> 
     <li id="li_0C239F0A536D465F85A98EBF7B6ADF27">排除regexp ^。*\.doc$ </li> 
     <li id="li_9F91DA35A2A646ACAFF2BA37F9136E2A">排除regexp ^。*\.xls$ </li> 
     <li id="li_9D768D9EA2DB44FBB00A1979E21672E2">排除regexp ^。*\.ppt$ </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

請參閱[將URL遮色片新增至……的索引部分或非索引部分。](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1)。

請參閱[規則運算式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

## MP3 {#reference_7614250EE81C4EEFA43E57A6A74E83D7}

常見問題頁面，討論在網站上建立MP3音樂檔案索引與搜尋的支援。

以下是有關MP3檔案的常見問題。

* [何時編目MP3檔案並建立索引？](#section_538EA1682C9C47E3A62640BB25D84C36)
* [我要怎麼爬，找索引……](#section_3CD794446E3545379C14E9F222118665)
* [如何識別MP3檔案？](#section_230E7336965A424F96C5CCF1D3C2D103)
* [MP3檔案中有哪些索引？](#section_E99D252B27CA4946AED3FCD3ABD8779D)
* [MP3檔案會計為頁面嗎？](#section_9910BEB6617D4D2090558CDF6C65D16B)
* [我要如何防止個別MP3檔案的索引……](#section_C989DC1D3D3841B38F683A462195DC05)
* [如何防止MP3檔案建立索引？](#section_305D2B28D1124776B6DC0C62A17827C6)
* [我為什麼無法在網站上搜尋中文、日文或韓文MP3檔案？](#section_06A48DA3F9E742CC93CC8B5CCD7382FA)

## 何時編目MP3檔案並建立索引？{#section_538EA1682C9C47E3A62640BB25D84C36}

MP3檔案的編目和索引有兩種方式。 最常見的方式是來自HTML檔案中的錨點href標籤：

`<a href="MP3-file-URL"></a>`

第二種方式是將MP3檔案的URL輸入為URL入口點。

請參閱[關於URL入口點](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

## 我要做什麼才能在網站上編目和索引MP3檔案？{#section_3CD794446E3545379C14E9F222118665}

要激活帳戶的MP3搜索和索引，請在產品菜單中按一下&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**。 在[!DNL Staged Content Types]頁面上，選擇&#x200B;**[!UICONTROL Text in MP3 Music Files]**。

請參閱[關於內容類型](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07)。

## 如何識別MP3檔案？{#section_230E7336965A424F96C5CCF1D3C2D103}

MP3檔案的MIME類型是「audio/mpeg」。

## MP3檔案中有哪些索引？{#section_E99D252B27CA4946AED3FCD3ABD8779D}

MP3檔案可選擇儲存少量的文字資訊。 這些資訊可包含相簿名稱、藝術家姓名、歌名、歌曲類型、發行年份和注釋。 這些資訊會儲存在檔案的最後端，稱為TAG。 包含TAG資訊的MP3檔案按以下方式編製索引：

* 歌曲標題會被視為HTML頁面的標題。
* 注釋會被視為為HTML頁面定義的說明。
* 類型會被視為為HTML頁面定義的關鍵字。
* 藝術家名稱、相簿名稱和發行年份會被視為HTML檔案的正文。

## MP3檔案會計為頁面嗎？{#section_9910BEB6617D4D2090558CDF6C65D16B}

是的，您網站上編目並建立索引的每個MP3檔案會計為一頁。

## 我要如何防止個別MP3檔案的索引？{#section_C989DC1D3D3841B38F683A462195DC05}

使用`<nofollow>`和`</nofollow>`標籤來環繞連結至MP3檔案的錨記。 搜索自動機不會跟隨這些標籤之間的連結。

另一種方法是將MP3檔案的URL新增為排除遮色片。

請參閱[關於URL遮色片](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164)。

請參閱[關於URL遮色片指令碼](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B)。

## 如何防止MP3檔案建立索引？{#section_305D2B28D1124776B6DC0C62A17827C6}

要控制帳戶的MP3索引，最簡單的方法是取消選取[!DNL Staged Content Types]頁面上的&#x200B;**[!UICONTROL Text in MP3 Music Files]**。

請參閱[選擇要編目的內容類型和索引](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8)。

您也可以使用「URL遮色片」功能，以依副檔名停用MP3索引。 若要這麼做，請在產品功能表上按一下「**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**」。 輸入以下蒙版之一：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>如果您的帳戶…… </p> </th> 
   <th colname="col2" class="entry"> <p>輸入下列URL遮色片 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>不使用規則運算式 </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> exclude *.mp3  </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用規則運算式 </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> 排除regexp ^。*\.mp3$ </span> </p> </td> 
  </tr> 
 </tbody> 
</table>

請參閱[規則運算式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

## 我為什麼無法在網站上搜尋中文、日文或韓文MP3檔案？{#section_06A48DA3F9E742CC93CC8B5CCD7382FA}

若要搜尋中文、日文或韓文MP3檔案，請在產品選單上按一下&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]** > **[!UICONTROL Text in MP3 Music Files]**。 然後，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]**」，並指定用來編碼MP3檔案的字元集。

請參閱[選擇要編目的內容類型和索引](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8)。

請參閱[關於注射](../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5)。

## PDF {#reference_F127C4915A0D436DA34E5D75ABFBB21B}

常見問題頁面，討論在網站上建立PDF檔案索引和搜尋的支援。

以下是有關PDF檔案的常見問題：

* [PDF檔案中的索引項目為何？](#section_62BFCD7158B44F2BB3B1864224B50174)
* [哪些PDF檔案未建立索引？](#section_A14B353AE503408896BACBBF3F748FA0)
* [如何計算建立索引的PDF檔案？](#section_C35DE36A65D649BD8FF314E9EFD990A6)
* [搜尋結果是否可顯示PDF圖示？](#section_829CE82CC3544502A13D27C4DB820189)
* [搜尋結果是否可連結至……](#section_A06E7F7017E6441E98209D288EE57BF6)
* [如何防止PDF檔案在上建立索引……](#section_96671419A822486AAC654D8DAD819940)
* [我為何無法在網站上搜尋中文、日文或韓文PDF檔案？](#section_D41CA8EFCA0242EA8CF5F8F1924E4CD8)

## PDF檔案中的索引項目為何？{#section_62BFCD7158B44F2BB3B1864224B50174}

PDF檔案的完整內容已建立索引。 PDF檔案的下列部分已建立索引：

* 標題
* 關鍵字
* 主旨（說明）
* 文字內容

## 哪些PDF檔案未建立索引？{#section_A14B353AE503408896BACBBF3F748FA0}

PDF目錄、檔案中的任何圖形，或包含圖形的任何文字，都不會建立索引。

## 如何計算建立索引的PDF檔案？{#section_C35DE36A65D649BD8FF314E9EFD990A6}

每個PDF檔案都會計為單一檔案，包括包含多頁的PDF。

## 搜尋結果是否可顯示PDF圖示？{#section_829CE82CC3544502A13D27C4DB820189}

是.使用範本中的`<search-if-link-extension>`標籤，在搜尋結果中加入PDF圖示或其他圖形或文字：

```
<search-results> 
  ... 
  <search-if-link-extension value=".pdf"> 
    <img src="/search/i/pdficon.gif"> 
  </search-if-link-extension> 
  ... 
</search-results>
```

PDF圖示可協助您的客戶知道搜尋結果連結至可能非常大的PDF檔案。 檔案大小對透過調制解調器或行動裝置存取您網站的客戶可能很重要。

## 搜尋結果是否可連結至PDF檔案中的特定頁面？{#section_A06E7F7017E6441E98209D288EE57BF6}

是.使用智慧型連結範本標籤(`<search-smart-link>...</search-smart-link>`)，客戶可以按一下以開啟第一個包含搜尋結果的PDF頁面。

若要使用智慧型連結，請將範本搜尋結果區段中的`<search-link>...</search-link>`標籤取代為`<search-smart-link>...</search-smart-link>`標籤。 當客戶按一下智慧型連結標籤產生的連結時，他們會前往與其搜尋查詢相關的第一個PDF頁面。

>[!NOTE]
>
>若要使用此功能，客戶必須使用最新版的Adobe AcrobatReader(或Adobe Acrobat)，其中必須包含反白顯示外掛程式和外部視窗處理程式(EWH)外掛程式。 此外，其Web瀏覽器必須使用Netscape Navigator的Adobe Acrobat插件（您可以使用任何接受此Netscape Navigator插件的瀏覽器）或Internet Explorer 4.0及更新版本的AcrobatActiveX控制項。

請參閱[搜尋範本標籤](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

## 如何防止PDF檔案在我的網站上建立索引？{#section_96671419A822486AAC654D8DAD819940}

如果不希望搜索自動機搜索和索引PDF檔案，請取消選擇內容類型&#x200B;**[!UICONTROL PDF Documents]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)。

您也可以選擇使用[!DNL URL Masks]來停用PDF索引。

請參閱[將URL遮色片新增至……的索引部分或非索引部分。](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1)。

若要停用PDF索引，請輸入下列其中一個URL遮色片：

* `exclude *.pdf` （如果您不使用規則運算式）
* `exclude regexp ^.*\.pdf$` （如果您使用規則運算式）

請參閱[規則運算式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

## 我為何無法在網站上搜尋中文、日文或韓文PDF檔案？{#section_D41CA8EFCA0242EA8CF5F8F1924E4CD8}

網站搜尋／銷售從PDF檔案取得UTF-8，而無語言指示。 如果您選取了內容類型&#x200B;**[!UICONTROL PDF Documents]**(**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**)，則必須使用中繼資料插入來指定PDF檔案中使用的語言。

請參閱[添加欄位插入定義](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE)。

## 頁數過多{#reference_48A748BC1ED14844ACAC2735C8388E8A}

常見問題頁面，說明索引器計數頁面數目多於實際頁數的部分原因，以及每種情況的解決方案。

如果您確定您的網站低於頁面限制，但索引器會告訴您已達限制，您應檢視這些常見問題和可能的解決方案答案。

* [您檢查過各種索引日誌嗎？](#section_C929BF9FDA6B4C9A9078C45AFE80EFE8)
* [CGI程式是否在您的網站上建立索引？](#section_86ED8A641B3841EC80153B4F107548FD)
* [您的伺服器是否啟用目錄瀏覽功能？](#section_073C88EEE74F4CA0AD2C7145D4810B22)
* [您的網站上是否有論壇或新聞群組？](#section_8DCB94F0850A41B9B2EA885F779E2F84)
* [您的網站上是否有PDF或Microsoft Office檔案……](#section_455FC5438DF74E68AB9A31D359EAD4D9)
* [您有多個URL入口點嗎？](#section_8C54AFD7DF56472A9364D516482B534C)
* [您是否已超過……的內部位元組或時間限制](#section_AE1BE61A58864FFE81F0BCEED2EBB15D)

## 您檢查過各種索引日誌嗎？{#section_C929BF9FDA6B4C9A9078C45AFE80EFE8}

索引記錄檔包含網站搜尋／銷售自動機在為您的網站建立索引時收集的詳細資訊。 記錄檔包含所有已編目連結和遇到錯誤的清單。 當您嘗試判斷哪些頁面要建立索引時，檢查索引日誌是開始的最佳位置。

請參閱[檢視即時或分段的完整索引記錄……](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8)。

請參閱[查看即時或分段的增量索引日誌……](../c-about-index-menu/c-about-incremental-index.md#task_E668E1F1240C476DAA1CA783DC728232)。

請參閱[查看即時或……的指令碼式增量索引日誌](../c-about-index-menu/c-about-scripted-index.md#task_CBFCE9B9A87B4DF7A2A35A6E83DE93D7)。

請參閱[查看即時或分段的已再生索引日誌……](../c-about-index-menu/c-about-regenerate-index.md#task_61CE8F9E7BF84BA89A8D482B2106BB15)。

請參閱[檢視即時或分段網站的重新排名索引記錄](../c-about-index-menu/c-about-re-rank-index.md#task_3C76107DFAC1495FACD3ABB0A688208D)。

## CGI程式是否在您的網站上建立索引？{#section_86ED8A641B3841EC80153B4F107548FD}

CGI程式使用URL參數，這些參數有時會導致索引器編目多個「假」URL。 如果站點搜索／銷售正在讀取CGI程式，並在其中跟隨帶有CGI參數的URL，則可能有數倍的頁面被搜索和編製索引，這對搜索索引不有用。 典型的CGI參數出現在具有`?`或`&`字元的URL中。

您可以使用「URL遮色片」功能來遮色片CGI程式的索引。 您可以對URL前置詞進行掩碼，或使用規則運算式來對CGI指令碼進行掩碼。

請參閱[關於URL遮色片](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164)。

請參閱[關於URL遮色片指令碼](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B)。

請參閱[規則運算式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

## 您的伺服器是否啟用目錄瀏覽功能？{#section_073C88EEE74F4CA0AD2C7145D4810B22}

當Web伺服器啟用了目錄瀏覽，且指定目錄中沒有index.html檔案時，對該目錄的訪問可以顯示該目錄中的檔案清單。 通常，頁面頂端有連結可讓您按一下&#x200B;**[!UICONTROL Name]**、**[!UICONTROL Last modified]**、**[!UICONTROL Size]**&#x200B;等，以不同方式排序清單。 通常，這些項目會在網站搜尋／銷售索引記錄檔中顯示為URL，結尾處會顯示字元如`?M=A`。 網站搜尋／銷售索引器會將這些連結作為連結，這可能導致為多個「假」URL建立索引。

通常，設計良好的網站會在每個目錄中放置索引檔案，或者會針對那些沒有索引檔案的目錄禁用目錄瀏覽。 幸運的是，如果您無法變更頁面或停用伺服器端的目錄清單，有一個簡單的方法可遮住這些「假」URL。

要完成此任務，請按一下&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**。 新增遮色片，以遮色任何包含`?`字元的URL。 您可以輸入下列規則運算式遮色片來執行此工作：

`exclude regexp ^.*\?.*$`

建立遮色片後，請確定您已重新索引網站。

請參閱[執行即時或分段網站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

請參閱[執行即時或分段網站的遞增索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。

## 您的網站上是否有論壇或新聞群組？{#section_8DCB94F0850A41B9B2EA885F779E2F84}

如果您的網站上正在搜尋論壇或新聞群組，則可能會依循不同顯示選項或排序選項的URL。 此行為表示同一頁面已建立多次索引。

通常，論壇或新聞群組會隨附其搜尋引擎。 在這種情況下，您可使用[!DNL URL Masks]來遮罩網站搜尋／銷售的論壇。

在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**」。 在[!DNL Staged URL Masks]頁面上，將論壇的URL輸入為排除的URL遮色片，以遮色片。

請參閱[將URL遮色片新增至……的索引部分或非索引部分。](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1)。

建立遮色片後，請務必重新建立網站的索引。

請參閱[執行即時或分段網站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

請參閱[執行即時或分段網站的遞增索引……](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB)。

## 您的網站上是否有PDF或Microsoft Office檔案？{#section_455FC5438DF74E68AB9A31D359EAD4D9}

如果您的網站上有PDF檔案或[!DNL Microsoft Office]檔案，您可能會發現只有幾個檔案的索引大小會計算許多頁面。 編製索引的頁面數比您擁有的檔案多，是因為PDF或Microsoft Office檔案中的每個頁面都會計為個別頁面。

在產品功能表上，按一下「**[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Index]**」。 在[!DNL Full Index]頁面上，選擇&#x200B;**[!UICONTROL Count All Pages]**，然後按一下&#x200B;**[!UICONTROL Full Index Now]**&#x200B;以查看總頁數。 如果您不想將PDF檔案或Microsoft Office檔案建立索引，可以在&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**&#x200B;下停用此內容類型。

請參閱[執行即時或分段網站的完整索引……](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D)。

請參閱[關於內容類型](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07)。

## 您有多個URL入口點嗎？{#section_8C54AFD7DF56472A9364D516482B534C}

網站搜尋／銷售自動機會從指定的URL入口開始編目，並追蹤該特定網域中所有內容的所有找到連結。 如果您已指定許多URL入口點，可能會編目大量頁面。

在其他網域的登入點檔案標題中，使用「排除協定」的`nofollow`標籤，如下所示：

```
<html> 
<head> 
<meta name="robots" content="nofollow"> 
</head>
```

上述程式碼會告訴網站搜尋／銷售自動機為頁面內容建立索引，但不要跟隨其他頁面的連結。

您可以在以下網址進一步瞭解Web機器人和機器人排除協定：

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

如果您無法存取其他網域上的頁面來源，則可移除多個URL入口點。 這樣做有助於將索引活動限制在那些您希望客戶能夠搜索其內容的域。

請參閱[關於URL入口點](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

## 您是否已超過網站搜尋／銷售的內部位元組或時間限制？{#section_AE1BE61A58864FFE81F0BCEED2EBB15D}

檢查您的帳戶是否已在「完整索引狀態」畫面上達到限制。 如果狀態報告您的索引大於允許值，或是花了比允許值更長的時間，您的網站就無法建立完整的索引。 您可以修正此錯誤，以獲得正確的涵蓋範圍和網站頁面計數。

為了保護網站搜尋／銷售伺服器，位元組和時間有內部限制。 只有當編目的檔案很大，或當網站搜尋／銷售嘗試觸及的伺服器緩慢時，才會達到這些限制。

如果您達到時間限制，請確定您的伺服器已連線，並稍後再次嘗試索引。 如果您達到位元組限制，請檢視索引記錄來檢查已編目的檔案。 它們有異常大嗎？ 如果您看到其中任一訊息，請連絡技術支援。
