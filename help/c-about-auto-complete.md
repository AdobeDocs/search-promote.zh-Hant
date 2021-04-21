---
description: 您可以設定「自動完成」的各個區域，以控制自動完成啟用的搜尋表單的產生，以及自動完成資料。js檔案，此檔案會包含在自動完成啟用的搜尋表單中。
solution: Target
subtopic: Auto-Complete
title: 關於自動完成
topic-legacy: Design,Site search and merchandising
uuid: 3dfdd14d-2044-4f01-a5bc-fcb2eb0d5068
exl-id: a1d08c0a-6c68-4da2-88d2-fe953d333536
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 1%

---

# 關於自動完成{#about-auto-complete}

您可以設定「自動完成」的各個區域，以控制自動完成啟用的搜尋表單的產生，以及自動完成資料。js檔案，此檔案會包含在自動完成啟用的搜尋表單中。

## 關於自動完成{#concept_093A9CD754864BA79B456FE4BEB64578}

每當「自動完成設定」頁面已保存更改時，檔案[!DNL autocomplete_data.js]將重新生成並發佈到搜索內容網路。

## 配置自動完成{#task_F491F2BFC4D24A61BBDC48B9059C11BB}

您可以設定和設定選項，以控制自動完成搜尋表單和檔案的產生。

<!-- 

t_configuring_auto-complete.xml

 -->

設定自動完成後，您可以檢視產生的HTML來源以供審核。 HTML來源是您複製並貼入網站頁面的內容。

請參閱[預覽在您的……上顯示的搜尋表單](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714)。

請參閱[設定自動完成Word清單](c-about-auto-complete.md#task_1F8E0F346263443383F8CFD2C7AB35D4)。

請參閱[設定自動完成CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96)。

**若要設定自動完成**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete Setup]**」。
1. 在[!DNL Auto-Complete Setup]頁面上，設定您想要的選項。

   另請參閱[預覽搜尋表單，如您的……](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714)。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>選項 </p> </th> 
      <th colname="col2" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>最大建議數 </p> </td> 
      <td colname="col2"> <p>指定要在自動完成建議清單中顯示的項目數上限。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最小輸入字元數 </p> </td> 
      <td colname="col2"> <p>指定客戶在顯示建議之前，必須在自動完成搜尋表單中輸入的字元數。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最大快取條目數 </p> </td> 
      <td colname="col2"> <p>指定先前要求在客戶瀏覽器中快取的自動完成建議數目上限。 通常，應將此設定保留為預設值1000。 </p> <p>雖然您可以將此選項設定為0以完全停用瀏覽器快取，但不建議使用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>表單名稱 </p> </td> 
      <td colname="col2"> <p>指定啟用自動完成搜尋表單「表單」標籤的「名稱」屬性。 例如， </p> <p> <span class="filepath"> &lt;form name="SiteSearch" method="get" action="https://sp1004337c.guided.t1.atomz.com" target="_blank"&gt; </span> </p> <p>其中<span class="filepath"> SiteSearch </span>是表單標籤的名稱屬性。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Div標籤ID </p> </td> 
      <td colname="col2"> <p>指定啟用自動完成搜尋表單「div」標籤的ID屬性。 例如， </p> <p> <span class="filepath"> &lt;div id="autocomplete"&gt; </span> </p> <p>其中<span class="filepath"> autocomplete </span>是div標籤的屬性。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>輸入標籤ID </p> </td> 
      <td colname="col2"> <p>指定啟用自動完成搜尋表單「input」標籤的ID屬性。 例如， </p> <p> <span class="filepath"> &lt;input type="text" id="q" name="q" /&gt; </span> </p> <p>其中， <span class="filepath"> q </span>是輸入標籤的id屬性。 </p> </td> 
      </tr> 
      <tr>
      <td colname="col1"> <p>顯示陰影 </p> </td>
      <td colname="col2"> <p>在自動完成建議清單中新增外觀下垂式陰影。 </p> </td>
      </tr>
      <tr>
      <td colname="col1"> <p>僅在片語的開頭匹配 </p> </td>
      <td colname="col2"> <p>只建議符合輸入文字開頭的結果。 </p> </td>
      </tr>
      <tr>
      <td colname="col1"> <p>支援UTF-8字元集 </p> </td>
      <td colname="col2"> <p>正確處理非ASCII字元。 </p> </td>
      </tr>
    </tbody> 
   </table>

1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 配置自動完成Word清單{#task_1F8E0F346263443383F8CFD2C7AB35D4}

設定「自動完成」會以建議的形式顯示給客戶的字詞和片語清單。

<!-- 

t_configuring_auto-complete_word_list.xml

 -->

請參閱[設定自動完成](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB)。

請參閱[設定自動完成CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96)。

**若要設定自動完成字詞清單**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete Word List]**」。
1. 在[!DNL Auto-Complete Word List]頁面上，設定您想要的選項。

   請參閱[預覽在您的……上顯示的搜尋表單](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714)。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>選項 </p> </th> 
      <th colname="col2" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>熱門搜尋時段 </p> </td> 
      <td colname="col2"> <p> 控制客戶最近搜尋中包含字詞和片語的時段。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> 最大搜索數 </p> </td> 
      <td colname="col2"> <p>控制要包含在自動完成字詞清單中的搜尋字詞和片語數目上限。 其中包含最熱門的字詞和片語，也是最受歡迎的字詞。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>欄位名稱 </p> </td> 
      <td colname="col2"> <p>每個欄位名稱定義一個要包含索引值的欄位的名稱。 使用+和——可添加或刪除欄位名。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最大值計數 </p> </td> 
      <td colname="col2"> <p>定義選定欄位名稱允許的欄位值的最大計數。 其中包括也是最受參考的頂端值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>新增這些字詞和片語 </p> </td> 
      <td colname="col2"> <p> 自動完成的字詞清單會填入此區域所列的字詞和片語。 </p> <p> 按一下「編輯<span class="uicontrol"></span>」以檢視清單或新增字詞和片語至清單。 完成後，按一下「保存更改</span>」。<span class="uicontrol"> </span></p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>移除這些字詞和片語 </p> </td> 
      <td colname="col2"> <p> 此區域中的項目不會顯示在自動完成的字詞清單中。 </p> <p> 按一下「編輯<span class="uicontrol"></span>」以檢視清單或新增字詞和片語至清單。 完成後，按一下「保存更改</span>」。<span class="uicontrol"> </span></p> <p> 此清單中允許使用規則運算式。 若要在此清單中指定規則運算式，請以<code>regexp</code>開頭一行，後面接著單一空格，後面接著規則運算式。 字詞清單中與規則運算式相符的任何行都會移除。 </p> <p> <b>重要</b>:只有在先前已在其他應用程式中使用規則運算式時，才應使用規則運算式。 </p> <p>請參閱<a href="c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local">規則運算式</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>忽略大小寫 </p> </td> 
      <td colname="col2"> <p>自動完成單詞清單中僅按字母大寫／小寫區分的重複條目被刪除；所有字詞清單條目都強制為小寫。 </p> <p>如果您希望「自動完成」建議顯示為「首字母大寫」或「所有大寫」，請新增 
        <code>
          text-transform : capitalize; 
        </code>或 
        <code>
          text-transform : uppercase; 
        </code>自動完成CSS內容的CSS文字屬性，位於「/*樣式，用於結果項目*/」下。 </p> <p>請參閱<a href="c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96" type="task" format="dita" scope="local">設定自動完成CSS </a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>重新索引時更新 </p> </td> 
      <td colname="col2"> <p>每個成功的帳戶重新索引後，自動完成的字詞清單會自動重新產生。 </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。
   * 按一下&#x200B;**[!UICONTROL Preview Word List]**&#x200B;以儲存您所做的任何變更，然後開啟[!DNL Auto-Complete Word List Preview]頁面，您可在其中檢視自動完成建議清單。 使用頁面頂端附近的導覽選項來檢視和調整顯示的清單。 完成後，按一下&#x200B;**[!UICONTROL Close]**&#x200B;返回[!DNL Auto-Complete Word List]頁。

      請參閱[使用歷史記錄選項](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 設定自動完成CSS {#task_EECE35DEB6C94F4A8A5B42B4DED76D96}

使用「自動完成CSS」來設定您要使用的自動完成階層式樣式表。

<!-- 

t_configuring_auto-complete_css.xml

 -->

自動完成CSS會控制[!DNL autocomplete_styles.css]的內容，此內容會包含在自動完成的搜尋表單中。 您在此處指定的CSS會控制自動完成建議清單的視覺呈現方式。 如需可能的視覺化簡報構想範例，請參閱下列內容：

[https://developer.yahoo.com/yui/examples/autocomplete/ac_skinning.html](https://developer.yahoo.com/yui/examples/autocomplete/ac_skinning.html).

[設定自動完成字詞清單](c-about-auto-complete.md#task_1F8E0F346263443383F8CFD2C7AB35D4)。

[設定自動完成](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB)。

完成自動完成CSS的設定後，您可以預覽搜尋表單，查看您指定的CSS在外觀和版面中是否可接受。

請參閱[預覽在您的……上顯示的搜尋表單](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714)。

**重要**:若要套用自訂自動完成的CSS，您必須從HTML程式碼中顯示的第二行移除註解標籤。然後，您會將同一行移至包含搜尋表單之頁面的標題區段內。

請參閱[將搜索表單的HTML代碼複製到……](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7)。

**若要設定自動完成CSS**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete CSS]**」。
1. 在[!DNL Auto-Complete CSS]文字欄位中，貼上或輸入您要與自動完成建議清單產生關聯的階層式樣式表資訊。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 預覽搜尋表單，如同它在您的網站{#task_437B35EFA5424603A08AF8E79E6B4714}上所顯示

根據您設定的「自動完成」和「自動完成」CSS，您可以預覽搜尋表單的顯示方式（如果您要將HTML程式碼新增至網站）。

<!-- 

t_previewing_the_search_form_as_it_would_appear_on_your_website.xml

 -->

請參閱[設定自動完成](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB)。

請參閱[設定自動完成CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96)。

請參閱[將搜索表單的HTML代碼複製到……](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7)。

請參閱[在搜尋表單中使用系列](c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3)。

請參閱[使用框架與表單](c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5)。

請參閱[範例進階搜尋表單](c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A)。

請參閱[進階搜尋表單HTML程式碼](c-appendices/c-searchforms.md#reference_9AAD4A46B68D4D48865508982CB86DB9)。

請參閱[進階搜尋表單範本代碼](c-appendices/c-searchforms.md#reference_D762C22E754E462DBEECD88D2C3FA579)。

**若要預覽搜尋表單在您網站上的顯示效果**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Search Form]**」。
1. （可選）按一下&#x200B;**[!UICONTROL HTML code]**，查看您複製並貼入網站頁面的HTML。

## 將搜尋表單的HTML程式碼複製至您網站的頁面{#task_A3A01EA800F24C0AA33902387E0362C7}

根據您設定的「自動完成」和「自動完成」CSS，您可以預覽搜尋表單的顯示方式（如果您要將HTML程式碼新增至網站）。

<!-- 

t_copying_the_html_code_of_the_search_form_into_the_pages_of_your_website.xml

 -->

請參閱[設定自動完成](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB)。

請參閱[設定自動完成CSS](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96)。

請參閱[將搜索表單的HTML代碼複製到……](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7)。

請參閱[在搜尋表單中使用系列](c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3)。

請參閱[使用框架與表單](c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5)。

請參閱[範例進階搜尋表單](c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A)。

請參閱[進階搜尋表單HTML程式碼](c-appendices/c-searchforms.md#reference_9AAD4A46B68D4D48865508982CB86DB9)。

請參閱[進階搜尋表單範本代碼](c-appendices/c-searchforms.md#reference_D762C22E754E462DBEECD88D2C3FA579)。

**若要將搜尋表單的HTML程式碼複製至您網站的頁面**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**」。

   >[!NOTE]
   >
   >請勿變更表單來源中的`form name=`值。

1. （可選）執行下列任一項作業：

   * 如果您設定了自動完成CSS，並想要將樣式套用至搜尋表單，請從HTML程式碼中顯示的第二行移除註解標籤。 接著，將同一行移至包含搜尋表單之頁面的標題區段內。
   * 為獲得最佳效能，請移動列在HTML程式碼底部的標籤，並將它們放置在包含搜尋表單之每個頁面的內文區段底部。

1. 復製程式碼並貼到您網站的網頁中，讓搜尋表格顯示。
