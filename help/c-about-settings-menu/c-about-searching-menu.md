---
description: 使用「搜尋」功能表可設定排除的字詞、系列、限制、預覽和框架。
solution: Target
subtopic: Searching
title: 關於「搜索」菜單
topic: Settings,Site search and merchandising
uuid: 072111fc-a32b-4acb-8337-cb21bcdb5542
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '11170'
ht-degree: 1%

---


# 關於「搜索」菜單{#about-the-searching-menu}

使用「搜尋」功能表可設定排除的字詞、系列、限制、預覽和框架。

## 關於搜索{#concept_207105CF26B1448F8A3D223787C56AB8}

您可以使用「搜尋」來定義和自訂您的簡報範本可參照的已命名搜尋。

<!-- 

c_about_searches.xml

 -->

在簡報範本中，您可以參考在「搜尋」模組中定義的任何已命名搜尋。 反過來，這又可讓您輕鬆自訂為特定範本集所執行的搜尋類型。

若要從搜尋結果中排除常用片語和常用字詞，請參閱[設定排除的字詞](../c-about-linguistics-menu/c-about-excluded-words.md#task_60BF6BB7A66C48479D2BBB32C0F38CDE)。

若要定義網站的特定可搜尋區域，請參閱[新增系列](../c-about-settings-menu/c-about-searching-menu.md#task_07732D0F00104E59AD421297A704B2F6)。

要為搜索結果連結指定目標幀，請參閱[使用框架與表單](../c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5)。

若要根據HTTP反向連結、IP位址或請求方案（HTTP或HTTPS）限制搜尋，請參閱「預覽」中的「設定值」。[](../c-about-settings-menu/c-about-searching-menu.md#task_CE267A0FF621474E80AB43B67B1C28D7)

## 搜尋提示{#section_22F0E2BCF259459FA5F49FBCC0F09A7C}

若要取得更詳細的搜尋結果，您可使用下列搜尋提示。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>搜尋提示 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>檢查拼字 </p> </td> 
   <td colname="col2"> <p>請確定您的搜尋詞拼寫正確。 如果在<span class="uicontrol">語言學</span> &gt; <span class="uicontrol">字詞與語言</span>中啟用了<span class="uicontrol">相似音效比對</span>，搜尋引擎會嘗試尋找與您的搜尋詞聽起來類似的字詞。 不過，最好嘗試正確拼寫搜尋詞。 </p> <p>請參閱<a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local">關於字詞與語言</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用多個字詞 </p> </td> 
   <td colname="col2"> <p>範例: 
     <code>
       our free product 
     </code> </p> <p>與單字查詢相比，多字查詢可傳回更精細的結果。 </p> <p>例如， 
     <code>
       our free product 
     </code>會傳回更相關的結果， 
     <code>
       product 
     </code>。 </p> <p>請記住，即使相關結果不包含所有查詢詞，仍會傳回這些結果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用類似字詞 </p> </td> 
   <td colname="col2"> <p>範例: 
     <code>
       safe secure privacy security 
     </code> </p> <p>您在搜尋查詢中使用的字詞越相似，搜尋結果就越相關。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用適當的大寫 </p> </td> 
   <td colname="col2"> <p>範例: 
     <code>
       Search Template Reference 
     </code> </p> <p>大寫專有名詞。 如果您使用小寫字詞，搜尋引擎會比對該字詞的任何大小寫。 </p> <p>例如，若您輸入 
     <code>
       search 
     </code>，搜尋引擎會傳回包含"search"、"Search"和"SEARCH"字詞的所有檔案。 不過，如果您在 
     <code>
       Search 
     </code>時，搜尋引擎會傳回僅包含大寫字詞的檔案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用引號 </p> </td> 
   <td colname="col2"> <p>範例: 
     <code>
       "our pledge to you" 
     </code> </p> <p>使用引號尋找必須彼此相鄰的字詞，例如"我們向你保證"。 若沒有周圍的引號，搜尋結果會包含"our"、"prentite"、"to"和"you"等字詞，但未必如此。 相反，這些單字可能會以任何順序出現在檔案中的任何位置。 </p> <p> 如果您使用「進階搜尋表單」搭配<span class="uicontrol">任何</span>、<span class="uicontrol">所有</span>和<span class="uicontrol">片語</span>的選項按鈕，則您只能在選取<span class="uicontrol">任何</span>時使用引號。 如果選取<span class="uicontrol">所有</span>或<span class="uicontrol">片語</span>，則會忽略引號。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用+（加號）或-（減號） </p> </td> 
   <td colname="col2"> <p>範例: 
     <code>
       +"template language" 
     </code> </p> <p>使用+可指出搜尋詞或片語必須出現在搜尋結果中。 </p> <p>使用——指出搜尋詞或片語必須不在搜尋結果中。 </p> <p>您必須在引號中包含一個片語。 正如上述範例所示，加號或減號與搜尋詞之間不留空格。 </p> <p> 如果您使用「進階搜尋表單」搭配<span class="uicontrol">任何</span>、<span class="uicontrol">所有</span>和<span class="uicontrol">片語</span>的選項按鈕，則您只能在選取<span class="uicontrol">任何</span>時使用引號。 如果選取了<span class="uicontrol">所有</span>或<span class="uicontrol">片語</span>，則會忽略加號和減號修飾元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用欄位搜尋 </p> </td> 
   <td colname="col2"> <p>範例: </p> <p> 
     <ul id="ul_F7CFF7652894402E8D19D6BA49792530"> 
      <li id="li_27492EF933C5437CB2C499746EC8CF39"> 
       <code>
         title:about 
       </code> </li> 
      <li id="li_BD21505122104FD0B16A4DAD777811DA"> 
       <code>
         desc:"Our Team" 
       </code> </li> 
      <li id="li_8264630F8B3D46BF872EFEB1D69DB6BE"> 
       <code>
         keys:login 
       </code> </li> 
      <li id="li_EBB81CBFC6DA45E99A524890DCD56E9F"> 
       <code>
         body:security 
       </code> </li> 
      <li id="li_6A852E35D6984A2C94144AB6C6D2DFA0"> 
       <code>
         alt:"join now" 
       </code> </li> 
      <li id="li_F4C5699360484D12ACD62BBFB84A7904"> 
       <code>
         url:help 
       </code> </li> 
      <li id="li_B2DBBA2239E74D98868D92B3EDEF5B51"> 
       <code>
         target:Adobe 
       </code> </li> 
     </ul> </p> <p>欄位搜尋可讓您針對出現在檔案特定部分的字詞建立特定搜尋。 </p> <p>您可以對內文(body:)、標題文字(title:)、alt文字(alt:)、中繼描述(desc:)、中繼關鍵字(keys:)、URL(url:)或中繼目標關鍵字(target:)執行欄位搜尋。 在欄位名稱中使用小寫，然後立即加上冒號。 冒號和搜尋詞之間沒有空格。 </p> <p>欄位搜尋後面只有一個字或片語。 片語必須包含在引號中。 </p> <p>如果您使用「高級搜索表單」和欄位名的清單框，則在選擇<span class="uicontrol">任何</span>時，您只能在單字或短語之前輸入欄位名。 如果在清單框中選擇了任何其他高級搜索表單欄位，則將忽略特定欄位名。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用萬用字元 </p> </td> 
   <td colname="col2"> <p>範例: </p> <p> 
     <ul id="ul_D8E3867EB15641B0A6E55AD546CCB4DD"> 
      <li id="li_CB8B8FC15EB14B13BB33BB69F5206303"> 
       <code>
         wh* 
       </code> </li> 
      <li id="li_5350A934648C4C81BD6C0875061B426B"> 
       <code>
         "wh* are" 
       </code> </li> 
      <li id="li_7965A2F7186F40039D2F0736299D11B1"> 
       <code>
         415-*-* 
       </code> </li> 
     </ul> </p> <p>萬用字元搜尋會擴充特定請求的符合數。 *字元用作萬用字元。 </p> <p>例如，搜索 
     <code>
       wh* 
     </code>會找到"what"、"why"、"when"、"whewh"和以"wh"開頭的任何其他字詞。 搜尋*her*時，會找到"here"、"whether"、"toghere"、"gathering"和任何包含"her"的字詞。 </p> <p>您可以結合萬用字元與+和——修飾元、片語的引號，以及欄位搜尋指定符。 </p> <p>搜尋 
     <code>
       +wh* -se*ch 
     </code>會尋找所有含有以"wh"開頭且不包含以"se"開頭且以"ch"結尾的字詞的頁面。 </p> <p>搜尋 
     <code>
       "wh* are" 
     </code>會尋找片語"where are"、"what are"、"why are"等。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 添加新搜索定義{#task_98D3A168AB5D4F30A1ADB6E0D48AB648}

您可以使用[!DNL GS Add Search]面板，在表現層中設定並新增引導式搜尋元件的搜尋定義，例如刻面、階層連結、頁面導覽、選單和最近的搜尋。

<!-- 

t_adding_a_new_definition.xml

 -->

新增搜尋定義後，請務必在簡報範本中參照，以便顯示。

請參閱[關於模板](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5)。

**若要新增搜尋定義**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Searches]**」。
1. 在[!DNL Searches]頁面上，按一下&#x200B;**[!UICONTROL Add New Search]**。
1. 在&#x200B;**[!UICONTROL GS Add Search]**&#x200B;頁面上，設定您想要的選項。

   <!-- 
   
   r_gs_search_options.xml
   
   -->

   請注意，選取簡報範本的處理規則可以覆寫其中一些選項。

   請參閱[添加新搜索定義](../c-about-settings-menu/c-about-searching-menu.md#task_98D3A168AB5D4F30A1ADB6E0D48AB648)或[編輯搜索定義](../c-about-settings-menu/c-about-searching-menu.md#task_AF1FFB1AEF874C13AB359C28F74BF461)。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>選項 </p> </th> 
      <th colname="col2" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>搜尋 名稱 </p> </td> 
      <td colname="col2"> <p>標識已定義搜索的名稱。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>來源 </p> </td> 
      <td colname="col2"> <p>可讓您選取要使用的後端搜尋。 您可以從<span class="wintitle"> SiteSearch </span>或<span class="wintitle"> Merchandising </span>中選擇。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>帳戶 </p> </td> 
      <td colname="col2"> <p>此選項僅在選擇<span class="uicontrol">Search&amp;Promote</span>作為源時可用。 </p> <p>可讓您選取您要搜尋的網站搜尋／銷售帳戶。 通常，搜尋會在您目前使用的帳戶中搜尋。 不過，您的簡報範本可以對任何其他帳戶使用後端搜尋。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>伺服器名稱/IP </p> </td> 
      <td colname="col2"> <p>只有在您選擇<span class="uicontrol">銷售</span>作為來源時，此選項才可用。 </p> <p>指定<span class="wintitle">銷售</span>搜尋應存取之<span class="wintitle">銷售</span>伺服器的完整名稱。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>伺服器埠 </p> </td> 
      <td colname="col2"> <p>只有在您選擇<span class="uicontrol">銷售</span>作為來源時，此選項才可用。 </p> <p>指定<span class="wintitle">銷售</span>伺服器埠號。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>金字塔 </p> </td> 
      <td colname="col2"> <p>只有在您選擇<span class="uicontrol">銷售</span>作為來源時，此選項才可用。 </p> <p>指定<span class="wintitle">銷售</span>伺服器內的金字塔。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>結果數 </p> </td> 
      <td colname="col2"> <p>指定您要傳回的搜尋結果數。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>第一頁結果的數目（如果不同） </p> </td> 
      <td colname="col2"> <p>指定在第一頁傳回的結果數。 如果您需要與其他頁面不同，請使用此選項。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>欄數 </p> </td> 
      <td colname="col2"> <p>指定將搜索結果拆分到的列數。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>搜索類型 </p> </td> 
      <td colname="col2"> <p>此選項僅在選擇<span class="uicontrol">Search&amp;Promote</span>作為源時可用。 </p> <p>可讓您從下列三種搜尋類型中選擇。 </p> <p> 
        <ul id="ul_2F6FA9EFD8DB49EEAB866C3D070E2644"> 
          <li id="li_ECFEBEDD86FF4DE2BB768423B3B91B5E"> <span class="uicontrol"> 全部 </span> <p>搜尋包含查詢字串中所有字詞的檔案。 </p> <p>在停用搜尋字詞並忽略這些字元之前，請使用「+」和「-」。 </p> </li> 
          <li id="li_62EB215BDDE74DF0BF76B3BD5B96776F"> <span class="uicontrol"> 任何 </span> <p>允許使用"+"和"-"字首。 </p> </li> 
          <li id="li_3D71982C0BBA41AFA353069AF3F2F6D8"> <span class="uicontrol"> 片語  </span> <p>查詢字串會視為引號字串，並忽略所有使用者類型的引號。 </p> <p>在停用搜尋字詞並忽略這些字元之前，請使用「+」和「-」。 </p> </li> 
        </ul> </p> <p> 如果您希望查詢中的每個字詞都可能選擇facet值，則您的主要搜尋應一律使用<span class="uicontrol">所有</span>。 </p> <p>您可以檢閱搜尋查詢中使用+和——修飾元的搜尋秘訣。 </p> <p>請參閱<a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local">關於搜尋</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>集合 </p> </td> 
      <td colname="col2"> <p>此選項僅在選擇<span class="uicontrol">Search&amp;Promote</span>作為源時可用。 </p> <p>識別索引中您要搜尋的系列。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>促銷活動 </p> </td> 
      <td colname="col2"> <p>此選項僅在選擇<span class="uicontrol">Search&amp;Promote</span>作為源時可用。 </p> <p>可讓您根據您指定的<span class="uicontrol">結果數</span>，從搜尋結果中使用隨機選擇。 </p> <p>促銷活動是舊有的概念。 因此，我們建議您在網站搜尋／銷售中使用新的橫幅管理系統。 </p> <p>請參閱<a href="../c-about-design-menu/c-about-banners.md#concept_5BBE01FEC6134393B43CC917C8CC64DA" type="concept" format="dita" scope="local">關於橫幅廣告</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>套用Facet參數 </p> </td> 
      <td colname="col2"> <p>只有在選擇<span class="uicontrol">Search&amp;Promote</span>作為源，並選擇<span class="uicontrol">促銷搜索</span>時，此選項才可用。 </p> <p>指定促銷搜尋會使用選取的刻面來縮小促銷範圍。 大多數促銷搜尋帳戶都不使用此選項。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>如果沒有匹配的促銷，請提供預設促銷 </p> </td> 
      <td colname="col2"> <p>只有在選擇<span class="uicontrol">Search&amp;Promote</span>作為源，並選擇<span class="uicontrol">促銷搜索</span>時，此選項才可用。 </p> <p>指定如果促銷的初始搜索未找到任何內容，則會執行另一個促銷搜索。 促銷的第二次搜尋會捨棄關鍵字。 相反地，它會尋找任何將「is_default」中繼資料欄位設為「yes」的促銷。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>反白顯示搜尋 </p> </td> 
      <td colname="col2"> <p>從要在「英雄區域」中反白顯示的主要搜尋中提取選取數目的結果。 </p> <p>通常，反白顯示搜尋與主要搜尋的搜尋准則類似，但使用不同的排名機制反白顯示特定結果。 軟體會從主搜索中刪除重複項。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>基本搜尋 </p> </td> 
      <td colname="col2"> <p>只有選擇了<span class="uicontrol">突出顯示搜索</span> ，此選項才可用。 </p> <p>可讓您選取具有反白顯示結果的搜尋。 此搜索將刪除重複項。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>重複資料消除優先順序 </p> </td> 
      <td colname="col2"> <p>只有選擇了<span class="uicontrol">突出顯示搜索</span> ，此選項才可用。 </p> <p>可讓您進行多個反白顯示搜尋。 </p> <p>當您有多個反白顯示搜尋時，您需要指定重複資料消除的優先順序，其中「1」是最高優先順序。 </p> <p>例如，假設您有兩個反白顯示搜尋：暢銷書和新產品。 理論上說。 暢銷商品也有可能是新產品。 在這種情況下，您希望從新產品和主搜索中刪除重複項。 因此，您將暢銷書的優先順序設為1，而新產品的優先順序設為2。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>參數 </p> </td> 
      <td colname="col2"> <p>可讓您將CGI參數新增至搜尋。 </p> <p>請參閱<a scope="local" href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita">後端搜尋CGI參數</a>。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 按一下 **[!UICONTROL Add]**.
1. （可選）在[!DNL Searches]頁面上，執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 編輯搜索定義{#task_AF1FFB1AEF874C13AB359C28F74BF461}

您可以使用[!DNL Staged GS Edit Search]面板來重新配置引導式搜尋表現層的現有搜尋定義。

<!-- 

t_editing_a_search_definition.xml

 -->

編輯搜尋定義後，請確定您已在簡報範本中參考過它，以便顯示。

請參閱[關於模板](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5)。

**要編輯搜索定義**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Searches]**」。
1. 在[!DNL Searches]頁面的表格中，按一下您要變更之定義列中的&#x200B;**[!UICONTROL Edit]**。
1. 在&#x200B;**[!UICONTROL GS Edit Search]**&#x200B;頁面上，設定您想要的選項。

   <!-- 
   
   r_gs_search_options.xml
   
   -->

   請注意，選取簡報範本的處理規則可以覆寫其中一些選項。

   請參閱[添加新搜索定義](../c-about-settings-menu/c-about-searching-menu.md#task_98D3A168AB5D4F30A1ADB6E0D48AB648)或[編輯搜索定義](../c-about-settings-menu/c-about-searching-menu.md#task_AF1FFB1AEF874C13AB359C28F74BF461)。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>選項 </p> </th> 
      <th colname="col2" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>搜尋 名稱 </p> </td> 
      <td colname="col2"> <p>標識已定義搜索的名稱。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>來源 </p> </td> 
      <td colname="col2"> <p>可讓您選取要使用的後端搜尋。 您可以從<span class="wintitle"> SiteSearch </span>或<span class="wintitle"> Merchandising </span>中選擇。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>帳戶 </p> </td> 
      <td colname="col2"> <p>此選項僅在選擇<span class="uicontrol">Search&amp;Promote</span>作為源時可用。 </p> <p>可讓您選取您要搜尋的網站搜尋／銷售帳戶。 通常，搜尋會在您目前使用的帳戶中搜尋。 不過，您的簡報範本可以對任何其他帳戶使用後端搜尋。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>伺服器名稱/IP </p> </td> 
      <td colname="col2"> <p>只有在您選擇<span class="uicontrol">銷售</span>作為來源時，此選項才可用。 </p> <p>指定<span class="wintitle">銷售</span>搜尋應存取之<span class="wintitle">銷售</span>伺服器的完整名稱。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>伺服器埠 </p> </td> 
      <td colname="col2"> <p>只有在您選擇<span class="uicontrol">銷售</span>作為來源時，此選項才可用。 </p> <p>指定<span class="wintitle">銷售</span>伺服器埠號。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>金字塔 </p> </td> 
      <td colname="col2"> <p>只有在您選擇<span class="uicontrol">銷售</span>作為來源時，此選項才可用。 </p> <p>指定<span class="wintitle">銷售</span>伺服器內的金字塔。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>結果數 </p> </td> 
      <td colname="col2"> <p>指定您要傳回的搜尋結果數。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>第一頁結果的數目（如果不同） </p> </td> 
      <td colname="col2"> <p>指定在第一頁傳回的結果數。 如果您需要與其他頁面不同，請使用此選項。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>欄數 </p> </td> 
      <td colname="col2"> <p>指定將搜索結果拆分到的列數。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>搜索類型 </p> </td> 
      <td colname="col2"> <p>此選項僅在選擇<span class="uicontrol">Search&amp;Promote</span>作為源時可用。 </p> <p>可讓您從下列三種搜尋類型中選擇。 </p> <p> 
        <ul id="ul_E1D8B3DE9DB24DE4813D53F6298A03A6"> 
          <li id="li_C3DD7AA7699B477A9EE0731CFC012630"> <span class="uicontrol"> 全部 </span> <p>搜尋包含查詢字串中所有字詞的檔案。 </p> <p>在停用搜尋字詞並忽略這些字元之前，請使用「+」和「-」。 </p> </li> 
          <li id="li_4C66B9EFEFA042908A4D3730F9F54EB0"> <span class="uicontrol"> 任何 </span> <p>允許使用"+"和"-"字首。 </p> </li> 
          <li id="li_37E9AD42A61C4E31A0816DFB8E71118D"> <span class="uicontrol"> 片語  </span> <p>查詢字串會視為引號字串，並忽略所有使用者類型的引號。 </p> <p>在停用搜尋字詞並忽略這些字元之前，請使用「+」和「-」。 </p> </li> 
        </ul> </p> <p> 如果您希望查詢中的每個字詞都可能選擇facet值，則您的主要搜尋應一律使用<span class="uicontrol">所有</span>。 </p> <p>您可以檢閱搜尋查詢中使用+和——修飾元的搜尋秘訣。 </p> <p>請參閱<a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local">關於搜尋</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>集合 </p> </td> 
      <td colname="col2"> <p>此選項僅在選擇<span class="uicontrol">Search&amp;Promote</span>作為源時可用。 </p> <p>識別索引中您要搜尋的系列。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>促銷活動 </p> </td> 
      <td colname="col2"> <p>此選項僅在選擇<span class="uicontrol">Search&amp;Promote</span>作為源時可用。 </p> <p>可讓您根據您指定的<span class="uicontrol">結果數</span>，從搜尋結果中使用隨機選擇。 </p> <p>促銷活動是舊有的概念。 因此，我們建議您在網站搜尋／銷售中使用新的橫幅管理系統。 </p> <p>請參閱<a href="../c-about-design-menu/c-about-banners.md#concept_5BBE01FEC6134393B43CC917C8CC64DA" type="concept" format="dita" scope="local">關於橫幅廣告</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>套用Facet參數 </p> </td> 
      <td colname="col2"> <p>只有在選擇<span class="uicontrol">Search&amp;Promote</span>作為源，並選擇<span class="uicontrol">促銷搜索</span>時，此選項才可用。 </p> <p>指定促銷搜尋會使用選取的刻面來縮小促銷範圍。 大多數促銷搜尋帳戶都不使用此選項。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>如果沒有匹配的促銷，請提供預設促銷 </p> </td> 
      <td colname="col2"> <p>只有在選擇<span class="uicontrol">Search&amp;Promote</span>作為源，並選擇<span class="uicontrol">促銷搜索</span>時，此選項才可用。 </p> <p>指定如果促銷的初始搜索未找到任何內容，則會執行另一個促銷搜索。 促銷的第二次搜尋會捨棄關鍵字。 相反地，它會尋找任何將「is_default」中繼資料欄位設為「yes」的促銷。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>反白顯示搜尋 </p> </td> 
      <td colname="col2"> <p>從要在「英雄區域」中反白顯示的主要搜尋中提取選取數目的結果。 </p> <p>通常，反白顯示搜尋與主要搜尋的搜尋准則類似，但使用不同的排名機制反白顯示特定結果。 軟體會從主搜索中刪除重複項。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>基本搜尋 </p> </td> 
      <td colname="col2"> <p>只有選擇了<span class="uicontrol">突出顯示搜索</span> ，此選項才可用。 </p> <p>可讓您選取具有反白顯示結果的搜尋。 此搜索將刪除重複項。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>重複資料消除優先順序 </p> </td> 
      <td colname="col2"> <p>只有選擇了<span class="uicontrol">突出顯示搜索</span> ，此選項才可用。 </p> <p>可讓您進行多個反白顯示搜尋。 </p> <p>當您有多個反白顯示搜尋時，您需要指定重複資料消除的優先順序，其中「1」是最高優先順序。 </p> <p>例如，假設您有兩個反白顯示搜尋：暢銷書和新產品。 理論上說。 暢銷商品也有可能是新產品。 在這種情況下，您希望從新產品和主搜索中刪除重複項。 因此，您將暢銷書的優先順序設為1，而新產品的優先順序設為2。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>參數 </p> </td> 
      <td colname="col2"> <p>可讓您將CGI參數新增至搜尋。 </p> <p>請參閱<a scope="local" href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita">後端搜尋CGI參數</a>。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）在[!DNL Searches]頁面上，執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 刪除搜索定義{#task_1D8E991E4C4146B7A7311FAE5DAA3742}

您可以刪除不再需要或使用的參考線搜尋定義。

<!-- 

t_deleting_a_search_definition.xml

 -->

請參閱[關於模板](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5)。

**刪除搜索定義**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Searches]**」。
1. 在[!DNL Searches]頁面的表格中，按一下您要移除之定義列中的&#x200B;**[!UICONTROL Delete]**。
1. 在[!DNL Confirmation]對話框中，按一下&#x200B;**[!UICONTROL OK]**。
1. （可選）在[!DNL Searches]頁面上，執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 關於固定結果關鍵字管理器{#concept_0C5F152C029C485D8872C6795CBCD7C7}

您可以手動將搜尋結果釘選至特定位置。 這些固定結果與特定搜尋查詢或關鍵字相關聯。 您可以使用[!DNL Pinned Result Keyword Manager]來管理所有具有固定結果的關鍵字。

<!-- 

c_about_pinned_results_keyword_manager.xml

 -->

## 要遵循{#section_ED67A24BE884468286F34FA5DFF826D7}的關鍵字搜尋規則

您在面板中輸入的搜索查詢具有以下規則：

* 前導和尾隨空格會從查詢中刪除。
* 不允許特殊搜索字元，例如：

   * 通配符與星號(*)匹配。
   * 沒有必要或不可要使用加號或減號（+或-）。
   * 沒有帶有冒號字元(:)的欄位指定字元。
   * 無逗號或雙引號（，或&quot;）。

* 允許在查詢中使用空格分隔的多個詞語或字詞。
* 大寫字母被轉換成小寫字母。

搜尋詞的記憶與原狀完全相同；您必須再次使用完全相同的搜尋詞，才能取得完全相同的結果。

固定結果不支援區分大小寫。 所有關鍵字的大寫字母都轉換為小寫字母。

## 重新排序搜索結果{#section_46FBE5279C7740A09D6DC9F54FE104AA}

當您在[!DNL Stage Add New Keyword]面板或[!DNL Staged Edit Keyword]面板中搜尋關鍵字時，搜尋結果會反映下次索引作業後可能發生的情況。 您可以使用三種不同的方法之一來重新排序表格中的搜尋結果。

第一個方法是使用&#x200B;**[!UICONTROL Pinned]**&#x200B;核取方塊。 此複選框用於將結果釘到特定位置。 選中該複選框時，該複選框上方的所有搜索結果也會被固定。 此功能可確保上述複選框的所有結果都按該特定順序顯示。 取消釘選搜尋結果會使其落在所有目前釘選的結果之下。

第二種方法是在表格中使用拖放功能。 您可以使用拖放方式將結果移至新位置。 將結果拖曳到新位置後，新位置上方的所有結果都會被固定。 此自動釘選功能可確保其餘結果會出現在最近拖曳的結果上方。

第三種方法是在&quot;#&quot;欄中輸入特定位置，以設定固定結果的順序。 與拖放不同，只有在下次開啟[!DNL Staged Edit Keyword]面板時，模擬搜尋結果的順序才會明顯。 設定目前未釘選列的訂單編號，可確保至少能釘選多個項目。 設定當前已固定行的訂單編號會設定當前已固定項目內該項目的順序。 但是，它不會增加固定項目的數目。

在儲存搜尋結果時，您可以在「關鍵字」欄位中輸入完全相同的查詢，再次檢視結果。

## 關於固定的搜索結果{#section_46780B7812F249F3B45503161C4FBDEE}

搜尋結果通常依相關性分數排序。 但是，固定搜索結果忽略相關性分數，並嘗試用其預定位置覆蓋自然順序。 通過確保結果保持相對原狀，其上的其他已知搜索結果必須固定。

面板上顯示的搜尋結果會模擬下一個索引後出現的內容。 但是，對原始文檔的更改或對成員中心的某些配置的更改可能會產生不一致的結果。 例如，在索引之後才會知道更改文檔的內容。

固定結果在索引後會以類似或相同的順序顯示，因為它們忽略了相關性。 未釘住的結果在指數後回落至其自然位置；未固定結果的順序不保證。

## 新增關鍵字{#task_8CED128DADD34D0DAD2C64B64D0D6B06}

您可以新增關鍵字及其固定結果。

<!-- 

t_adding_a_new_keyword.xml

 -->

新增關鍵字時，您可以重新排序搜尋結果，並將其釘選至特定位置。

**若要新增關鍵字**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Pinned Results]**」。
1. 在[!DNL Pinned Keyword Results Manager]頁面上，按一下&#x200B;**[!UICONTROL Add New Keyword]**。
1. 在[!DNL Add New Keyword]頁面的&#x200B;**[!UICONTROL Keyword]**&#x200B;欄位中，輸入搜尋查詢，然後按一下&#x200B;**[!UICONTROL Search Keyword]**。

   <!-- 
   
   r_keyword_options.xml
   
   -->

   可使用「編輯表」按鈕調整查看搜索結果表的方式。 例如，您可使用欄清單來顯示或隱藏特定欄。 您也可以使用拖放方式重新排列欄的順序。

   下表說明表編輯器中的列屬性。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>欄 </p> </th> 
      <th colname="col2" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>訂購 </p> </td> 
      <td colname="col2"> <p>指定列外觀的數字順序。 您可以拖放欄以自動更新順序。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>欄位名稱 </p> </td> 
      <td colname="col2"> <p>標識出現在<span class="wintitle">「分段添加新關鍵字</span>」面板和<span class="wintitle">「分段編輯關鍵字</span>」面板的<span class="wintitle">「模擬搜索結果</span>」表中的列標題的名稱。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>包含 </p> </td> 
      <td colname="col2"> <p>如果選中該框，則列將出現在「固定結果表」中。 如果該框為空或取消選中，則列將從表中消失。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>將URL顯示為影像 </p> </td> 
      <td colname="col2"> <p>如果指派給此欄的meta欄位有圖形或圖片的URL，勾選此方塊會將HTML影像標籤置於其周圍，而圖片便會出現。 遺失的圖片或錯誤的連結是空的。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>欄位長度 </p> </td> 
      <td colname="col2"> <p>可讓您輸入文字在以省略號(...)截斷前顯示的最大長度。 如果欄設為將URL顯示為影像，則此欄位沒有作用。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. （可選）執行下列任一項作業：

   * 重新排序搜尋結果。
   * 按一下&#x200B;**[!UICONTROL Edit Table]**&#x200B;調整[!DNL Simulated Search Results]表的視圖。 完成後，按一下&#x200B;**[!UICONTROL Save Changes]**&#x200B;返回[!DNL Add New Keyword]面板。

1. 按一下 **[!UICONTROL Save Search Results]**.
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參閱[設定分段網站的遞增索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可選）在[!DNL Pinned Results Keyword Manager]頁面上，執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 編輯關鍵字{#task_30C550A7350B4394B5B43536368A84B1}

您可以編輯現有關鍵字及其固定結果。

<!-- 

t_editing_a_keyword.xml

 -->

在編輯關鍵字時，您可以重新排序搜尋結果，並將其釘選至特定位置。

**若要編輯關鍵字**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Pinned Results]**」。
1. 在[!DNL Pinned Keyword Results Manager]頁面的表格中，按一下您要變更之關鍵字列中的&#x200B;**[!UICONTROL Edit]**。
1. 在[!DNL Edit Keyword]頁面的&#x200B;**[!UICONTROL Keyword]**&#x200B;欄位中，輸入搜尋查詢，然後按一下&#x200B;**[!UICONTROL Search Keyword]**。

   請確定您遵循關鍵字搜尋規則。

   <!-- 
   
   r_keyword_options.xml
   
   -->

   可使用「編輯表」按鈕調整查看搜索結果表的方式。 例如，您可使用欄清單來顯示或隱藏特定欄。 您也可以使用拖放方式重新排列欄的順序。

   下表說明表編輯器中的列屬性。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>欄 </p> </th> 
      <th colname="col2" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>訂購 </p> </td> 
      <td colname="col2"> <p>指定列外觀的數字順序。 您可以拖放欄以自動更新順序。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>欄位名稱 </p> </td> 
      <td colname="col2"> <p>標識出現在<span class="wintitle">「分段添加新關鍵字</span>」面板和<span class="wintitle">「分段編輯關鍵字</span>」面板的<span class="wintitle">「模擬搜索結果</span>」表中的列標題的名稱。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>包含 </p> </td> 
      <td colname="col2"> <p>如果選中該框，則列將出現在「固定結果表」中。 如果該框為空或取消選中，則列將從表中消失。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>將URL顯示為影像 </p> </td> 
      <td colname="col2"> <p>如果指派給此欄的meta欄位有圖形或圖片的URL，勾選此方塊會將HTML影像標籤置於其周圍，而圖片便會出現。 遺失的圖片或錯誤的連結是空的。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>欄位長度 </p> </td> 
      <td colname="col2"> <p>可讓您輸入文字在以省略號(...)截斷前顯示的最大長度。 如果欄設為將URL顯示為影像，則此欄位沒有作用。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. （可選）執行下列任一項作業：

   * 重新排序搜尋結果。
   * 按一下&#x200B;**[!UICONTROL Edit Table]**&#x200B;調整[!DNL Simulated Search Results]表的視圖。

      請參閱[新增關鍵字](../c-about-settings-menu/c-about-searching-menu.md#task_8CED128DADD34D0DAD2C64B64D0D6B06)。

      完成後，按一下&#x200B;**[!UICONTROL Save Changes]**&#x200B;返回[!DNL Add New Keyword]面板。

1. 按一下 **[!UICONTROL Save Search Results]**.
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參閱[設定分段網站的遞增索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可選）在[!DNL Pinned Results Keyword Manager]頁面上，執行下列任一操作：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 刪除關鍵字{#task_F17D6357D6DD416495E6D4117899D81D}

您可以刪除不再需要或使用的關鍵字。

<!-- 

t_deleting_a_keyword.xml

 -->

新增關鍵字時，您可以重新排序搜尋結果，並將其釘選至特定位置。

**刪除關鍵字**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Pinned Results]**」。
1. 在[!DNL Pinned Keyword Results Manager]頁面的表格中，按一下您要移除之關鍵字列中的&#x200B;**[!UICONTROL Delete]**。
1. 在[!DNL Delete Keyword]頁面上，按一下&#x200B;**[!UICONTROL Delete]**。
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參閱[設定分段網站的遞增索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可選）在[!DNL Pinned Results Keyword Manager]頁面上，執行下列任一操作：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 關於系列{#concept_62E42ACE53D54EEE9273433B86259127}

您可以使用「系列」來允許客戶搜尋網站的特定區域，以便他們快速找到所要的內容。

<!-- 

c_about_collections.xml

 -->

請參閱[關於搜尋](../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8)。

請參閱[在搜尋表單中使用系列](../c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3)。

例如，客戶可以搜尋與產品銷售或支援服務相關的URL集合。 在客戶可以使用您指定的系列之前，請務必在「搜尋表單」功能表下更新您的搜尋表單。

在「系列」設定的效果對客戶可見之前，請先重建您的網站索引。

您可以在選用的&#x200B;**[!UICONTROL Test Collections]**&#x200B;欄位中輸入您的其中一個網站URL，然後按一下&#x200B;**[!UICONTROL Test]**&#x200B;來測試您的系列。 指定頁面所屬的系列會傳回。

每個系列都會在具有名稱和URL遮色片的單一行上指定。 URL遮色片可包含下列項目：

* 完整路徑，例如`https://www.mydomain.com/products.html`
* 部分路徑，如`https://www.mydomain.com/products`
* 規則運算式

   若要將遮色片設為規則運算式，請在系列名稱和URL遮色片之間插入關鍵字`regexp`。

   請參閱[規則運算式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

「系列」欄位中的每一行只能包含一個URL遮色片。 不過，您可以為不同行上的相同系列名稱指定多個URL遮色片。 下列範例包含4個不同的系列名稱和5個URL遮色片：

```
Company Info https://www.yoursite.com/company 
Products https://www.yoursite.com/products 
FAQs regexp ^.*/faqs 
Support https://www.yoursite.com/email_support/ 
Support https://www.yoursite.com/phone_support/
```

在此範例中，在您更新搜尋表單以包含這些系列後，客戶可以個別選取和搜尋每個定義的系列。 `Support`系列包含與URL遮色片都相符的檔案，因此在選取此系列時，會同時搜尋`www.yoursite.com/email_support/`和`www.yoursite.com/phone_support`中的檔案。

## 新增系列{#task_07732D0F00104E59AD421297A704B2F6}

您可以新增系列，讓客戶搜尋您網站的特定區域，以便快速找到所要的內容。

<!-- 

t_adding_collections.xml

 -->

請確定您重建網站索引，以便讓客戶能夠看到URL遮色片的結果。

請參閱[設定分段網站的遞增索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**若要新增系列**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Collections]**」。
1. 在[!DNL Collections]欄位中，輸入系列名稱和URL遮色片位址，每行一個。
1. （可選）在[!DNL Collections]頁面的&#x200B;**[!UICONTROL Test Collections]**&#x200B;欄位中，輸入您網站的測試URL遮色片，然後按一下&#x200B;**[!UICONTROL Test]**。

   隨即顯示測試系列輸出視窗，顯示系列的URL和名稱。
1. 新增系列後，按一下&#x200B;**[!UICONTROL Save Changes]**。
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參閱[設定分段網站的遞增索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可選）在[!DNL Collections]頁面上，執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 關於限制{#concept_B5B527E04EBF4E9AB5956EEF881DDBF1}

在執行搜尋之前，會檢查反向連結URL和IP位址，以判斷是否可從該位置進行搜尋。 您在[!DNL Restrictions]中指定的內容會決定是否允許搜尋。 如果不允許搜尋，則傳回一般錯誤頁面給請求者。

<!-- 

c_about_restrictions.xml

 -->

您可以將限制設定指定為反向連結URL遮色片或IP位址遮色片。 這兩種限制都使用遮色片來允許搜尋，並排除遮色片來拒絕搜尋。

如果同時傳遞反向連結URL和IP位址限制條件，則允許搜尋。 如果任一設定不允許搜索，則搜索將失敗，無論允許其他限制。

例如，如果搜尋請求的「HTTP反向連結」欄位符合「排除」反向連結URL遮色片，則搜尋會失敗，即使請求的IP位址符合「包含」IP位址遮色片亦然。 如果沒有與反向連結URL或IP位址相符的遮色片，預設會包含該位置。

在單行上輸入每個包含蒙版或排除蒙版。

## 新增反向連結URL遮色片或IP位址遮色片限制{#task_E6FF2DD83E8D4B00A0E2809DC13A56C9}

您可以將限制設定指定為「反向連結URL遮色片」或「IP位址遮色片」。 這兩種限制都使用遮色片來允許搜尋，並排除遮色片來拒絕搜尋。 如果同時傳遞反向連結URL和IP位址限制條件，則允許搜尋。

<!-- 

t_adding_url_mask_or_jp_address_restrictions.xml

 -->

**若要新增反向連結URL遮色片或IP位址遮色片限制**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Restrictions]**」。
1. 在[!DNL Restrictions]頁面上，設定您想要的限制選項。 輸入反向連結URL遮色片位址、IP位址遮色片位址，或（可選）自訂網頁的URL位址，這些網頁會顯示給不允許搜尋您網站的客戶。

   <!-- 
   
   r_restriction_options.xml
   
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
      <td colname="col1"> <p>反向連結URL遮色片 </p> </td> 
      <td colname="col2"> <p>會讀取HTTP反向連結標題中的反向連結URL。 如果遮色片是包含遮色片，則符合反向連結URL的第一個遮色片會決定是否允許搜尋。 或者，如果遮色片是排除遮色片，則會決定是否禁止搜尋。 如果沒有與反向連結URL相符的遮色片，則會包含該URL並允許搜尋。 </p> <p> 如果您的搜尋範本包含新的搜尋表單，或您的搜尋範本可包含「下一個10」、「上一個10」或「隱藏摘要」等連結，則您會將搜尋結果範本列為「包含」遮色片。 最簡單的方式是使用規則運算式，如下列範例所示： </p> <p> <span class="codeph"> 包含regexp ^https?://[^/]*\.atomz\.com/。*[?&amp;]sp_a=sp1000130e.*$ </span> </p> <p>下列範例包含5種不同的反向連結URL遮色片： </p> <p> <code> include&nbsp;https://www.mydomain.com/search/ 
          include&nbsp;https://search.mydomain.com/ 
          include&nbsp;regexp&nbsp;^https://www.mydomain.com/help/.*/search/ 
          include&nbsp;regexp&nbsp;^https?://[^/]*\.atomz\.com/.*[?&amp;]sp_a=sp1000130e.*$ 
          exclude&nbsp;* </code> </p> <p>如果反向連結URL遮色片如下： </p> <p> <code> https://www.mydomain.com/search/searchpage.html&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
          https://search.mydomain.com/advanced/&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
          https://www.mydomain.com/help/products/search/advanced/&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
          https://www.mydomain.com/help/products/&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] 
          https://www.anotherdomain.com/&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] 
          blank&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>IP位址遮色片 </p> </td> 
      <td colname="col2"> <p>如果遮色片是包含遮色片，則符合IP位址的第一個遮色片會決定是否允許搜尋。 或者，如果遮色片是排除遮色片，則會決定是否允許或禁止搜尋。 如果沒有掩碼與請求的IP地址匹配，則會包括該IP地址並允許搜索。 </p> <p>以下範例顯示4種不同的IP位址遮色片。 </p> <p> <code> include&nbsp;64.128.192.* 
          include&nbsp;192.168. 
          include&nbsp;regexp&nbsp;^209\.42\.97\.[1-5]+ 
          exclude&nbsp;* </code> </p> <p>如果反向連結IP位址遮罩如下： </p> <p> <code> 64.128.192.10&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
          192.168.10.127&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
          209.42.97.14&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
          64.128.193.10&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] 
          192.169.10.14&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] 
          209.42.97.68&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>僅允許使用HTTPS的搜尋 </p> </td> 
      <td colname="col2"> <p>將搜尋限制為HTTPS。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>應將不允許的請求傳送至的URL </p> </td> 
      <td colname="col2"> <p> 受限制的使用者會重新導向至您在此處輸入的URL。 此選項可讓您自行建立自訂錯誤頁面，以便顯示給不允許搜尋您網站的客戶。 </p> <p>如果您未指定URL，則當受限制的使用者嘗試搜尋您的網站時，會傳回一般錯誤頁面。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 關於預覽{#concept_DF293FD3B02C467F8842C8C21D62F294}

您在[!DNL Preview]中設定的查詢字串和參數，在軟體中測試或預覽搜尋表格時都會使用。

<!-- 

c_about_preview.xml

 -->

另請參閱[關於搜索](../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8)。

## 在預覽{#task_CE267A0FF621474E80AB43B67B1C28D7}中設定值

在軟體中測試或預覽搜尋表單時，您所設定的預覽值隨時都會使用。

<!-- 

t_setting_values_in_preview.xml

 -->

**若要在預覽中設定值**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Preview]**」。
1. 在[!DNL Preview]頁面上，設定您想要的選項。

   <!-- 
   
   r_preview_options.xml
   
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
      <td colname="col1"> <p>查詢 </p> </td> 
      <td colname="col2"> <p>依預設，查詢字串會設為<span class="codeph"> * </span>，這通常會傳回結果。 不過，您可以指定更專屬於網站內容的查詢。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>參數 </p> </td> 
      <td colname="col2"> <p>參數的設定有名稱和值。 您可以指定所需的任意數量的其他參數。 例如，您可以使用<span class="codeph"> sp_q_1 </span>和<span class="codeph"> sp_x_1 </span>參數指定其他搜索標準。 參數值<span class="codeph"> sp_q_1=windows&amp;sp_x_1=platform </span>會建立預覽搜尋，除了主查詢外，還會在搜尋頁面的"platform"中繼標籤中尋找值"windows"。 </p> <p>請參閱<a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local">後端搜尋CGI參數</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>主機 </p> </td> 
      <td colname="col2"> <p>如果您的網站使用私人網域標籤，請設定正確的主機名稱，以準確預覽搜尋結果。 </p> <p>如需私人網域標籤的詳細資訊，請聯絡客戶支援。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 關於動態消息{#concept_FEBFEE51A3AB49F88CBA0D16E2AD6916}

搜尋索引會視為您網站的大型資料庫。 有了正確中繼標籤中的足夠資訊，資訊就會收集並組織或匯集到資料饋送中。 您可以將這些資料饋送提交至其他服務，例如協力廠商收件者。

<!-- 

c_about_feeds.xml

 -->

在您的網站編目並建立索引後，您就可產生自動饋送，並將它們送出至協力廠商的有機搜尋引擎和購物引擎。 您可以建立下列串流饋送：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>動態消息類型 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Recommendations </p> </td> 
   <td colname="col2"> <p>Recommendations 動態消息與Adobe Recommendations提供資料匯集功能。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>一般動態消息 </p> </td> 
   <td colname="col2"> <p>您可以使用「一般動態消息」類型實作許多動態消息。 系統會根據您網站的索引進行自訂搜尋查詢。 資料會透過使用顯示搜尋結果的相同範本語言自訂搜尋範本傳回。 這種彈性表示您可以將動態消息提交給更多廠商，而不只是特定的動態消息類型。 </p> <p>您可以使用以下幫助主題中的說明添加傳輸（搜索）模板： </p> <p>請參閱<a href="../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012" type="task" format="dita" scope="local">新增簡報或傳輸範本檔案</a>。 </p> <p> 新增範本後，請使用搜尋範本標籤加以編輯，以定義您要包含的搜尋中繼資料欄位及其格式。 </p> <p>請參閱<a href="../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3" type="task" format="dita" scope="local">編輯簡報或傳輸範本</a>。 </p> <p>請參閱<a href="../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4" type="reference" format="dita" scope="local">搜尋範本標籤</a>。 </p> <p>請記得傳輸範本檔案的名稱。 當您指定動態消息的條件時，可使用名稱將一般動態消息系結至範本。 </p> <p>如果您先前曾與其他動態消息搭配使用，請記得您將動態消息欄位對應至搜尋中繼資料欄位。 一般饋送在<span class="uicontrol">建立饋送</span>精靈中沒有此特定步驟。 範本會改為指定中繼資料和中繼資料的格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Google Merchant </p> </td> 
   <td colname="col2"> <p>Google Merchant Center讓人們透過數種Google服務銷售產品。 它有一個資料匯集元件，您可以在其中定期提交可供銷售的產品清單。 </p> <p>和任何協力廠商的動態消息供應商一樣，Google商家中心有您在認定動態消息合法之前所符合的特定標準。 如需詳細資訊，請連絡您的客戶代表，並造訪Google Merchant檔案。 以下是Google商家中心在驗證動態消息時所考慮的快速摘要： </p> 
    <ul id="ul_3D84D4A6A4BF4C08860F86403F8F9CD6"> 
     <li id="li_5B6516CC7BC7493B8B8E8AFB454E573F">每個產品都有產品頁面；專屬URL。 </li> 
     <li id="li_5A6D5AD5E1B54A94B224D19E888B5443"> 每個產品變體在動態消息中都有個別的項目。 </li> 
     <li id="li_89748D3241B34A4493576DAC38681988"> 每個產品都有影像URL，最好是源自您的伺服器。 產品變體具有顯示其實際變化的特定影像。 換句話說，不同的鞋色不應共用相同的影像。 </li> 
     <li id="li_A594AD19480F41EAA72181355F28447B"> 每項產品都有特定資訊，例如可用性、條件、說明、類別和價格。 </li> 
     <li id="li_0955B3A6ED2746D2B7CB42DC8AB27D3A">一般而言，每個產品都有唯一的識別碼，例如ISBN、UPC、JAN或EAN等。 </li> 
     <li id="li_2C371653F1C5471FA638F3A3818ABC17">一般而言，每項產品都會以Google的產品分類法分類。 </li> 
     <li id="li_6EB392A5A0BE490FAED5BC5E83228E32"> 服裝產品有額外的必填欄位，例如性別、年齡組、顏色和大小。 </li> 
     <li id="li_44B91FA9A95F4172A2F03F8206E9081E"> 稅金和運費在Google商家中心內指定為帳戶設定，或在此動態消息內以產品為基礎指定。 </li> 
     <li id="li_71A63E9905B840C0A04F6CDAA23C9AB0"> 定制產品和某些服裝產品可以免除某些規則，但您必須與谷歌聯繫，以獲得相關許可和有關此類豁免的詳細資訊。 </li> 
    </ul> <p>有許多詳細資訊可控制動態消息驗證。 如需動態消息管理的相關資訊，請參閱Google Merchant檔案。 Google經常變更規格，因此請經常查看檔案。 </p> <p>與Google Merchant Center關聯的動態消息通常稱為Google Product Search動態消息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Google網站地圖 </p> </td> 
   <td colname="col2"> <p>Google網站地圖可讓您影響Google搜尋您網站的方式。 匯集資料饋送（在此例中為網站地圖）會定期提交至Google網站地圖。 網站地圖包含可存取網際網路的URL，以及可與每個URL關聯的特定資訊，例如上次修改日期或頁面優先順序。 向谷歌提供此類資訊，可以增加搜索和索引特定頁面的頻率和機率。 在某些情況下，網站地圖會用來通告其爬蟲在正常情況下無法存取的連結清單。 </p> <p>如果您想要使用我們的動態消息功能建立Google網站地圖，請聯絡您的客戶代表。 Google已將其Google網站地圖服務公開給大眾，並在其Google網站管理員工具頁面提供檔案。 </p> <p> <b>建立Google網站地圖摘要的需求</b> </p> <p>若要建立Google網站地圖摘要，請確定您已設定Google網站地圖的Google網站主控工具帳戶。 如需設定Google網站地圖，請參閱Google網站管理員工具檔案。 </p> <p>您也需要決定如何傳送網站地圖檔案。 一般而言，網站地圖檔案來自您的網域，尤其是您網站的根目錄。 簡單的模型是讓檔案透過FTP傳送至您的伺服器。 另一個解決方案是將網站地圖檔案的要求重新導向至網站搜尋／銷售內容網路。 請洽詢您的諮詢代表，以協調和設定網站地圖饋送的傳送。 </p> </td> 
  </tr> 
 </tbody> 
</table>

如果您對自動摘要感興趣，請聯絡專業服務部門尋求協助。 每個饋送在資料品質和檔案傳輸方面都有嚴格的要求。

當您使用&#x200B;**[!UICONTROL Create Feed]**&#x200B;精靈來建構欄位時，您選取的動態消息類型會影響顯示哪些選項。 每種類型的動態消息都有不同的資料格式。 請確定您遵循正確的資料格式，以避免動態消息收件者拒絕動態消息，或將不當資料張貼給客戶。 除了資料格式外，廠商通常有一或多種偏好的接收資料方式。 請參閱廠商的檔案，瞭解其動態消息。

建立動態消息的挑戰在於如何比對網站搜尋／銷售與動態消息之間的資料。 通常，從索引搜索中檢索的資料格式錯誤或缺少。 以下是一些問題，可協助您在建立動態消息時著重於要尋找的內容。

* 您與動態消息收件者有何種業務關係？
* 您是否必須向動態消息收件者註冊並建立帳戶？
* 誰將監控並處理有關供應商的動態消息問題？ 一般而言，您有責任管理廠商的帳戶。 例如，Google Sitemap需要有WebMaster帳戶和某人來監控網站地圖的運行狀況。
* 動態消息的資料格式為何？
* 您的索引是否符合動態消息的字元編碼？ 當您的資料有制表符或逗號時，以制表符分隔和以逗號分隔的資料格式會變成問題。
* 當您的資料中有標籤或逗號時，該怎麼辦？
* 索引中是否有含空資料的頁面？
* 摘要收件者是否可接受空白資料？ 您可以編輯軟體擷取資料的准則，以解決空白資料。
* 資料格式是否與動態消息收件者想要的內容一致？ 例如，有些饋送收件者會針對價格和貨幣的顯示方式進行特定的說明。
* 供應商是否有可接受的最大項目數？ 您可以限制搜尋准則的結果，以解決此潛在問題。
* 廠商要如何接收動態消息？ 支援FTP提交和HTTP代管。

## 建立動態消息{#task_63179C1FC359497483CD6CE13FD1C250}

您可以建立一或多個資料饋送。

<!-- 

t_creating_a_feed.xml

 -->

**若要建立動態消息**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]**」。
1. 在[!DNL Feeds]頁面上，從&#x200B;**[!UICONTROL Create Feed]**&#x200B;下拉式清單中選取動態消息類型。
1. 視您選取的動態消息類型而定，在[!DNL Create Feed]對話方塊中，設定精靈每個面板中所識別的選項。

   <!-- 
   
   r_feed_options.xml
   
   -->

   可用的選項會依您所建立或編輯的動態消息類型而略有不同。

   **Adobe Recommendations**

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>面板 </p> </th> 
      <th colname="col2" class="entry"> <p>精靈面板名稱 </p> </th> 
      <th colname="col3" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>1 </p> </td> 
      <td colname="col2"> <p>摘要名稱 </p> </td> 
      <td colname="col3"> <p>指定動態消息的名稱。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>2 </p> </td> 
      <td colname="col2"> <p>欄位地圖 </p> </td> 
      <td colname="col3"> <p>可讓您將廠商特定的饋送欄位對應至網站搜尋／銷售中繼資料欄位。 精靈中的此對應步驟很重要，因為它可讓動態消息將索引中欄位與動態消息資料欄位之間的資訊建立關聯。 在大多數情況下，除<span class="wintitle">一般饋送</span>外，關聯會儲存在動態產生的搜尋範本中。 </p> <p><span class="wintitle">欄位映射</span>表中的每一行都表示欄位映射。 在表格的「添加／刪除」列中，按一下<span class="uicontrol"> + </span>添加新欄位映射行；按一下<span class="uicontrol"> - </span>從表中刪除當前選定的欄位映射行。 若要將動態消息欄位與網站搜尋／銷售中繼資料欄位建立關聯，請使用個別的下拉式清單來選擇所要的欄位。 </p> <p> <b>Adobe Recommendations的欄位映射</b> </p> <p>建議資料饋送是CSV檔案，資料欄以逗號分隔。 「欄位對應」表格上每個對應的外觀順序很重要，因為它們會決定CSV饋送檔案中欄的順序。 按照以下順序建立映射行——每行是必需的： </p> <p> 
        <ol id="ol_49C739D04DD340168DC6C1F794544C35"> 
          <li id="li_A95D9C5A353746A3A0D38F200AC2EEA2"> id </li> 
          <li id="li_044763D4C7054CEB948C94590735D74F"> name </li> 
          <li id="li_832F07CA0E3F4E10A4AE30171F3E8541"> categoryId </li> 
          <li id="li_2A33FB42F7E942ED881BA1F478542C4D"> 訊息 </li> 
          <li id="li_A76E66B2366845B0B63ED5C200531ADD"> thumbnailURL </li> 
          <li id="li_518CCD5E7E404521AB8199981BA86F76"> value </li> 
          <li id="li_14A0A8FCC2B34B758E1FBB98E3F2DFB2"> pageURL </li> 
          <li id="li_36D22F1603394AF89E0C7ADB18AAAAB7"> inventory </li> 
          <li id="li_ABDB9C762BBC4F27B82FEA4425A8DDC4"> margin </li> 
        </ol> </p> <p> <b>進階使用</b> </p> <p>在您對應上述前九個必要的動態消息欄位後，您可以建立自己的自訂欄位。 在「<span class="wintitle">饋送欄位</span>」下拉式清單中，按一下「自訂</span>」。 <span class="uicontrol">在關聯的文字欄位中，輸入該欄位的自訂標籤名稱。 如果動態消息需要特定於供應商的特殊欄位，此自訂選項很實用。 </span></p> <p> <p>注意： 雖然「建議饋送」規格指出每個欄位名稱必須加上前置詞"entity"，但在本例中並不需要。 </p> </p> <p>您也可以建立自訂中繼資料欄位。 在<span class="wintitle">中繼資料欄位</span>下拉式清單中，按一下<span class="uicontrol">自訂</span>。 在關聯的文字欄位中，輸入自訂中繼資料欄位值。 值會插入預先產生的範本中，也可用來插入自訂搜尋範本標籤。 </p> <p>請參閱<a href="../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4" type="reference" format="dita" scope="local">搜尋範本標籤</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>3 </p> </td> 
      <td colname="col2"> <p>搜尋標準 </p> </td> 
      <td colname="col3"> <p>產生饋送檔案時，會使用搜尋查詢來篩選資料。 您可以在此面板中定義用於搜尋查詢的篩選器。 </p> 
        <ul id="ul_799ECF61C03A44878C7182F8B88CC3AD"> 
        <li id="li_0763F600A4FB4650ACC28BF337EB50AF"> <span class="uicontrol"> 中繼欄位  </span> <p>定義您要篩選的中繼資料欄位。 </p> <p> <b>進階使用</b> </p> <p>由於過濾系統是標準搜索查詢，因此您可以從下拉清單中選擇<span class="uicontrol">自由格式</span>以輸入CGI搜索參數及其值。 需要URL逸出。 將忽略搜索引數<span class="codeph"> sp_q </span>。 您可以建立多列自由表單文字方塊。 在每一行之間，引數會自動以&amp;'s分隔。 </p> <p>請參閱<a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local">搜索CGI參數</a>。 </p> </li> 
        <li id="li_756B776902AE4A0E95524442D663343E"> <span class="uicontrol"> 標準 </span> <p>定義篩選操作。 您從下拉式清單中選擇的篩選操作會套用在第三欄中輸入的常數值。 </p> </li> 
        <li id="li_7ADEDB8747B241D78AC50F1AC75AE695"> <span class="uicontrol"> 值 </span> <p>常數值。 </p> </li> 
        <li id="li_4039A9BC2F74460B83BFF662B58DAA1B"> <span class="uicontrol"> 動作 </span> <p>新增欄位對應列，或刪除目前反白顯示的列。 </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>4 </p> </td> 
      <td colname="col2"> <p>檔案提交 </p> </td> 
      <td colname="col3"> <p>可讓您設定提交動態消息檔案的排程，並設定您要用來上傳檔案的方法。 </p> 
        <ul id="ul_55E253F83BDA46BAABF2BE38F0918E80"> 
        <li id="li_877A376B5B30422FAC816E31D50EA508"> <span class="uicontrol"> 排程 </span> <p>設定動態消息提交的最大頻率。 選取「<span class="uicontrol">永不</span>」會關閉動態消息。 其他值會定義動態消息在再次送出之前等待的時段。 何時提交動態消息的決定是在每個索引上完成。 換言之，在索引結束時，會檢查動態消息，以查看其是否已過期，且需要由廠商更新並提交。 此外，它也可用來防止帳戶過度提交給廠商。 有些廠商針對上傳頻率過高的資料饋送來源制定政策。 請務必檢查資料饋送廠商的提交頻率政策。 
          <!--The time of the last upload and the status of the upload feed is displayed here. If any other feeds are currently running, their status appears here instead. Each account processes one feed at a time. --> 
          <!--ick <uicontrol>Manual Upload</uicontrol> to generate the feed and push the files to the final destination. Any schedule restrictions that you have already set are ignored. --> </p> <p> 
          <!--If <uicontrol>Manual Upload</uicontrol> is dimmed (inactive), the account is currently processing this feed or another feed. An account only works with one feed at a time. --> </p> </li> 
        <li id="li_760F5068D3ED46C582AE41392A2CA342"> <span class="uicontrol"> 上傳方法  </span> <p>大部份的動態消息有兩種散發檔案的方式：FTP和代管內容網路。 </p> 
          <ul id="ul_666759EDDD034537AA7C0ED936A2F315"> 
          <li id="li_B4AD5CEEBB7B41C0B8DC291B95DC5F83"> <span class="uicontrol"> FTP </span> <p>網站搜尋／銷售伺服器使用被動式FTP。 </p> <p>FTP是將檔案推送至其他伺服器的唯一方式。 </p> <p> <span class="uicontrol"> FTP伺服 </span> 器——指定FTP伺服器的名稱。請勿包含通訊協定或「ftp://」之前。 </p> <p> <span class="uicontrol"> FTP使用者 </span> 名稱——指定FTP帳戶的名稱。 </p> <p> <span class="uicontrol"> FTP密 </span> 碼——指定FTP帳戶的密碼。 </p> <p> <span class="uicontrol"> FTP檔案名 </span> 稱——指定要傳輸的檔案名稱。如果動態消息產生多個檔案，此名稱是範本，通常會在名稱結尾但在副檔名之前增加一個數字。 例如：basename.xml, basename1.xml, basename2.xml, ..., basename-Nth.xml </p> <p> <span class="uicontrol"> FTP目 </span> 錄——如果需要特定目錄路徑，請在此處輸入。請勿將檔案名稱包含在路徑中。 </p> </li> 
          <li id="li_C082D3993C6C469B9067F207703BE619"> <span class="uicontrol"> 代管內容網路  </span> <p>「內容網路」是從網站搜尋／銷售的網站伺服器伺服檔案的方式。 動態消息的收件者使用HTTP請求從Web伺服器提取它。 要設定此設定的唯一資訊是<span class="uicontrol">內容網路檔案名</span>。 檔案名稱是所提供檔案的基本名稱。 僅使用副檔名為檔案名稱的檔案名稱。 根據動態消息，檔案名稱是多個檔案的範本，其中動態消息可能會以下列格式產生多個檔案：basename.xml、basename1.xml、basename2.xml、...、basename-Nth.xml。 </p> <p>輸入基本檔案名稱並成功儲存動態消息後，精靈的「驗證」面板會顯示「內容網路」檔案的URL。 成功處理動態消息後，URL會變為作用中。 廠商可從此URL取得動態消息資料。 多個檔案使用相同的URL路徑。 但是，請務必根據枚舉方案替換或更改檔案名。 </p> </li> 
          </ul> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>5 </p> </td> 
      <td colname="col2"> <p>驗證 </p> </td> 
      <td colname="col3"> <p>當您進入「<span class="wintitle">驗證</span>」面板時，您的動態消息會儲存在該點。 不過，實際的動態消息檔案要等到稍後才會儲存。 </p> <p><span class="wintitle">驗證</span>面板可讓您執行下列動作： </p> 
        <ul id="ul_0C6EFB38E06F401696084863D85CBD0D"> 
        <li id="li_07FC9F04C7F640048546F9DC5D91DA1D"> <span class="uicontrol"> 資料檢視  </span> <p>可讓您按一下連結，以透過以表格形式顯示的資料檢視來檢查動態消息輸出。 資料檢視也可協助您疑難排解，顯示選取哪些中繼欄位，以及精靈中<span class="wintitle">搜尋准則</span>面板中任何指定的搜尋准則對饋送輸出有何影響。 資料檢視會動態產生，因此隨時都可使用。 </p> </li> 
        <li id="li_67046A56D08C48298E5A3E1F9C4A8AF3"> <span class="uicontrol"> 摘要檔案  </span> <p>在網站搜尋／銷售伺服器產生動態消息檔案後，您可以使用<span class="uicontrol"> 「動態消息檔案</span>」下拉式清單來檢視伺服器中的檔案。 新的瀏覽器標籤或新的瀏覽器視窗會與動態消息的內容一起出現。 此方法可協助您疑難排解格式問題的動態消息。 請注意，您不會從最終目標或廠商本身檢視檔案。 </p> <p> 如果動態消息是新的，則下拉式清單會是空的，直到您產生動態消息檔案為止。 </p> </li> 
        <li id="li_99D66C7AD87A475CB3D831D514DB78A0"> <span class="uicontrol"> 內容網路連結  </span> <p>如果您在精靈的<span class="wintitle">檔案提交</span>面板中選擇<span class="uicontrol">代管內容網路</span>作為上傳方法，URL會顯示在此處。 如果您尚未產生任何動態消息檔案，則URL在成功產生動態消息之前無效。 </p> </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

   **一般動態消息**

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>面板 </p> </th> 
      <th colname="col2" class="entry"> <p>精靈面板名稱 </p> </th> 
      <th colname="col3" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>3 </p> </td> 
      <td colname="col2"> <p>摘要名稱 </p> </td> 
      <td colname="col3"> <p>指定動態消息的名稱。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>2 </p> </td> 
      <td colname="col2"> <p>搜尋標準 </p> </td> 
      <td colname="col3"> <p>產生饋送檔案時，會使用搜尋查詢來篩選資料。 您可以在此面板中定義用於搜尋查詢的篩選器。 </p> 
        <ul id="ul_C750687E69A647D0A4440FF1B6CC7E05"> 
        <li id="li_B5C3B8523D71472E9508A04E23AC0211"> <span class="uicontrol"> 中繼欄位  </span> <p>定義您要篩選的中繼資料欄位。 </p> <p> <b>進階使用</b> </p> <p>由於過濾系統是標準搜索查詢，因此您可以從下拉清單中選擇<span class="uicontrol">自由格式</span>以輸入CGI搜索參數及其值。 需要URL逸出。 將忽略搜索引數<span class="codeph"> sp_q </span>。 您可以建立多列自由表單文字方塊。 在每一行之間，引數會自動以&amp;'s分隔。 </p> <p>請參閱<a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local">搜索CGI參數</a>。 </p> </li> 
        <li id="li_D1E49834BBEA42CC8C49AE7D72037C53"> <span class="uicontrol"> 標準 </span> <p>定義篩選操作。 您從下拉式清單中選擇的篩選操作會套用在第三欄中輸入的常數值。 </p> </li> 
        <li id="li_D5F0651B834F4EACAD15A2D154A0737B"> <span class="uicontrol"> 值 </span> <p>常數值。 </p> </li> 
        <li id="li_FC8F382BD20C4518BC2230D4B4954591"> <span class="uicontrol"> 動作 </span> <p>新增欄位對應列，或刪除目前反白顯示的列。 </p> </li> 
        </ul> <p>一般饋送需要指定特殊的CGI參數。 若要系結與此饋送關聯的特殊範本，請定義<span class="codeph"> sp_t </span>參數。 將<span class="codeph"> sp_t </span>的值設定為傳輸模板檔案的名稱。 例如，如果您新增了名為<span class="codeph"> super_feed.tpl </span>的傳輸範本檔案，您會建立自訂CGI搜尋參數為<span class="codeph"> sp_t=super_feed </span>。 在從<span class="wintitle">元欄位</span>下拉清單中選擇<span class="uicontrol">自由格式</span>之前，輸入<span class="codeph"> sp_t </span>的文本框不會出現。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>1 </p> </td> 
      <td colname="col2"> <p>檔案提交 </p> </td> 
      <td colname="col3"> <p>可讓您設定提交動態消息檔案的排程，並設定您要用來上傳檔案的方法。 </p> 
        <ul id="ul_30E830C41F6A4526822AF1FD3083075A"> 
        <li id="li_79EAFDBD2B9F411EA985CAEC1BAF3926"> <span class="uicontrol"> 排程 </span> <p>設定動態消息提交的最大頻率。 選取「<span class="uicontrol">永不</span>」會關閉動態消息。 其他值會定義動態消息在再次送出之前等待的時段。 何時提交動態消息的決定是在每個索引上完成。 換言之，在索引結束時，會檢查動態消息，以查看其是否已過期，且需要由廠商更新並提交。 此外，它也可用來防止帳戶過度提交給廠商。 有些廠商針對上傳頻率過高的資料饋送來源制定政策。 請確定您已檢查動態消息供應商的提交頻率政策。 
          <!--he time of the last upload and the status of the upload feed is displayed here. If any other feeds are currently running, their status appears here instead. Each account processes one feed at a time. --> 
          <!--<uicontrol>Manual Upload</uicontrol> to generate the feed and push the files to the final destination. Any schedule restrictions that you have already set are ignored. --> </p> <p> 
          <!--If <uicontrol>Manual Upload</uicontrol> is dimmed (inactive), the account is currently processing this feed or another feed. An account only works with one feed at a time. --> </p> </li> 
        <li id="li_20BF70A19E7E45BA91CD972E2FCE0EA4"> <span class="uicontrol"> 上傳方法  </span> <p>大部份的動態消息有兩種散發檔案的方式：FTP和代管內容網路。 </p> 
          <ul id="ul_5888C2E9097645CE89938EE09F8CB4F1"> 
          <li id="li_EA9ED19F3BEA4BEAB1A9F2C2FAFF85F7"> <span class="uicontrol"> FTP  </span> <p>網站搜尋／銷售伺服器使用被動式FTP。 </p> <p>FTP是將檔案推送至其他伺服器的唯一方式。 </p> <p> <span class="uicontrol"> FTP伺服 </span> 器——指定FTP伺服器的名稱。請勿包含通訊協定或「ftp://」之前。 </p> <p> <span class="uicontrol"> FTP使用者 </span> 名稱——指定FTP帳戶的名稱。 </p> <p> <span class="uicontrol"> FTP密 </span> 碼——指定FTP帳戶的密碼。 </p> <p> <span class="uicontrol"> FTP檔案名 </span> 稱——指定要傳輸的檔案名稱。如果動態消息產生多個檔案，此名稱是範本，通常會在名稱結尾但在副檔名之前增加一個數字。 例如：basename.xml, basename1.xml, basename2.xml, ..., basename-Nth.xml </p> <p> <span class="uicontrol"> FTP目 </span> 錄——如果需要特定目錄路徑，請在此處輸入。請勿將檔案名稱包含在路徑中。 </p> </li> 
          <li id="li_181268A7EE40456CA1DB768E8C66EEB9"> <span class="uicontrol"> 代管內容網路  </span> <p>「代管內容網路」是從網站搜尋／銷售的網站伺服器伺服檔案的方式。 動態消息的收件者使用HTTP請求從Web伺服器提取它。 要設定此設定的唯一資訊是<span class="uicontrol">內容網路檔案名</span>。 檔案名稱是所提供檔案的基本名稱。 僅使用副檔名為檔案名稱的檔案名稱。 
            <!--Depending on the feed, the file name is a template for multiple files where the feed might generate multiple files in the following format: basename.xml, basename1.xml, basename2.xml, ..., basename-Nth.xml. --> </p> <p>輸入基本檔案名稱並成功儲存動態消息後，精靈的「驗證」面板會顯示「內容網路」檔案的URL。 成功處理動態消息後，URL會變為作用中。 廠商可從此URL取得動態消息資料。 </p> </li> 
          </ul> </li> 
        <li id="li_4DF56FA607A7479296CDA042A63C5A2C"> <p> <b>保留標籤？</b> </p> <p>在動態消息中保留標籤字元。 </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>4 </p> </td> 
      <td colname="col2"> <p>驗證 </p> </td> 
      <td colname="col3"> <p>當您進入「<span class="wintitle">驗證</span>」面板時，您的動態消息會儲存在該點。 不過，實際的動態消息檔案要等到稍後才會儲存。 </p> <p><span class="wintitle">驗證</span>面板可讓您執行下列動作： </p> 
        <ul id="ul_7420C415987448A796DD979CF5FA2EB6"> 
        <li id="li_AF02E8609B7B4F20A01AF4E010308E15"> <span class="uicontrol"> 資料檢視  </span> <p>可讓您按一下連結，以透過以表格形式顯示的資料檢視來檢查動態消息輸出。 資料檢視也可協助您疑難排解，顯示選取哪些中繼欄位，以及精靈中<span class="wintitle">搜尋准則</span>面板中任何指定的搜尋准則對饋送輸出有何影響。 資料檢視會動態產生，因此隨時都可使用。 </p> </li> 
        <li id="li_32CEB8885C184354BFA1773BA66DB7A7"> <span class="uicontrol"> 摘要檔案  </span> <p>在網站搜尋／銷售伺服器產生動態消息檔案後，您可以使用<span class="uicontrol"> 「動態消息檔案</span>」下拉式清單來檢視伺服器中的檔案。 新的瀏覽器標籤或新的瀏覽器視窗會與動態消息的內容一起出現。 此方法可協助您疑難排解格式問題的動態消息。 請注意，您不會從最終目標或廠商本身檢視檔案。 </p> <p> 如果動態消息是新的，則下拉式清單會是空的，直到您產生動態消息檔案為止。 </p> </li> 
        <li id="li_8D1B876B0EC2455C8654EC573EC53FA9"> <span class="uicontrol"> 內容網路連結  </span> <p>如果您在精靈的<span class="wintitle">檔案提交</span>面板中選擇<span class="uicontrol">代管內容網路</span>作為上傳方法，URL會顯示在此處。 如果您尚未產生任何動態消息檔案，則URL在成功產生動態消息之前無效。 </p> </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

   **Google商家中心**

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>面板 </p> </th> 
      <th colname="col2" class="entry"> <p>精靈面板名稱 </p> </th> 
      <th colname="col3" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>1 </p> </td> 
      <td colname="col2"> <p>摘要名稱 </p> </td> 
      <td colname="col3"> <p>指定動態消息的名稱。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>2 </p> </td> 
      <td colname="col2"> <p>欄位地圖 </p> </td> 
      <td colname="col3"> <p>可讓您將廠商特定的饋送欄位對應至網站搜尋／銷售中繼資料欄位。 精靈中的此對應步驟很重要，因為它可讓動態消息將索引中欄位與動態消息資料欄位之間的資訊建立關聯。 在大多數情況下，除<span class="wintitle">一般饋送</span>外，關聯會儲存在動態產生的搜尋範本中。 </p> <p>「欄位映射」表中的每一行都表示欄位映射。 在表格的<span class="wintitle"> 「新增／移除</span>」欄中，按一下「<span class="uicontrol"> + </span>」以新增欄位對應列；按一下<span class="uicontrol"> - </span>從表中刪除當前選定的欄位映射行。 若要將動態消息欄位與網站搜尋／銷售中繼資料欄位建立關聯，請使用個別的下拉式清單來選擇所要的欄位。 </p> <p> <b>進階使用</b> </p> <p>您可以建立自己的自訂欄位。 在「<span class="wintitle">饋送欄位</span>」下拉式清單中，按一下「自訂</span>」。 <span class="uicontrol">在關聯的文字欄位中，輸入該欄位的自訂標籤名稱。 如果動態消息需要特定於供應商的特殊欄位，此自訂選項很實用。 </span></p> <p>您也可以建立自訂中繼資料欄位。 在<span class="wintitle">中繼資料欄位</span>下拉式清單中，按一下<span class="uicontrol">自訂</span>。 在關聯的文字欄位中，輸入自訂中繼資料欄位值。 值會插入預先產生的範本中，也可用來插入自訂搜尋範本標籤。 </p> <p>請參閱<a href="../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4" type="reference" format="dita" scope="local">搜尋範本標籤</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>1 </p> </td> 
      <td colname="col2"> <p>搜尋標準 </p> </td> 
      <td colname="col3"> <p>產生饋送檔案時，會使用搜尋查詢來篩選資料。 您可以在此面板中定義用於搜尋查詢的篩選器。 </p> 
        <ul id="ul_8179321A58BB4C72B0CDB2B2BEC58FE4"> 
        <li id="li_9F8008A2398A4667B106BC49C94E5E3E"> <span class="uicontrol"> 中繼欄位  </span> <p>定義您要篩選的中繼資料欄位。 </p> <p> <b>進階使用</b> </p> <p>由於過濾系統是標準搜索查詢，因此您可以從下拉清單中選擇<span class="uicontrol">自由格式</span>以輸入CGI搜索參數及其值。 需要URL逸出。 將忽略搜索引數<span class="codeph"> sp_q </span>。 您可以建立多列自由表單文字方塊。 在每一行之間，引數會自動以&amp;'s分隔。 </p> <p>請參閱<a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local">搜索CGI參數</a>。 </p> </li> 
        <li id="li_50C9CE59E9E5418895F8C1A070560063"> <span class="uicontrol"> 標準 </span> <p>定義篩選操作。 您從下拉式清單中選擇的篩選操作會套用在第三欄中輸入的常數值。 </p> </li> 
        <li id="li_9F86D0F5010046A4A9F93DBA5FB158B3"> <span class="uicontrol"> 值 </span> <p>常數值。 </p> </li> 
        <li id="li_1051AFD5AEA447D0AF5FAB305E1D1E64"> <span class="uicontrol"> 動作 </span> <p>新增欄位對應列，或刪除目前反白顯示的列。 </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>4 </p> </td> 
      <td colname="col2"> <p>檔案提交 </p> </td> 
      <td colname="col3"> <p>可讓您設定提交動態消息檔案的排程，並設定您要用來上傳檔案的方法。 </p> 
        <ul id="ul_A6A3C333AADD4438B835BF3E16E2AEFF"> 
        <li id="li_FCC4DAF198E149278B5CFB870CB6218C"> <span class="uicontrol"> 排程 </span> <p>設定動態消息提交的最大頻率。 選取「<span class="uicontrol">永不</span>」會關閉動態消息。 其他值會定義動態消息在再次送出之前等待的時段。 何時提交動態消息的決定是在每個索引上完成。 換言之，在索引結束時，會檢查動態消息，以查看其是否已過期，且需要由廠商更新並提交。 此外，它也可用來防止帳戶過度提交給廠商。 有些廠商針對上傳頻率過高的資料饋送來源制定政策。 請確定您已檢查動態消息供應商的提交頻率政策。 </p> <p> 
          <!--The time of the last upload and the status of the upload feed is displayed here. If any other feeds are currently running, their status appears here instead. Each account processes one feed at a time. --> </p> <p> 
          <!--Click <uicontrol>Manual Upload</uicontrol> to generate the feed and push the files to the final destination. Any schedule restrictions that you have already set are ignored. --> </p> <p> 
          <!--If <uicontrol>Manual Upload</uicontrol> is dimmed (inactive), the account is currently processing this feed or another feed. An account only works with one feed at a time. --> </p> </li> 
        <li id="li_2D9ECAFB8E8544D39B486F7BC3DCE589"> <span class="uicontrol"> 上傳方法  </span> <p>大部份的動態消息有兩種散發檔案的方式：FTP和代管內容網路。 </p> <p>提交資料饋送的建議上傳方法為<span class="uicontrol"> FTP </span>。 Google Merchant Center會為此目的主控FTP伺服器。 請參閱Google商家中心說明，以設定此Google產品搜尋饋送的個別Google FTP帳戶。 </p> 
          <ul id="ul_BC0D8B541068407883CAC948496DBD0A"> 
          <li id="li_DB28CA23C94A4AF09E1A0EB06DF8F40C"> <span class="uicontrol"> FTP  </span> <p>網站搜尋／銷售伺服器使用被動式FTP。 </p> <p>FTP是將檔案推送至其他伺服器的唯一方式。 </p> <p> <span class="uicontrol"> FTP伺服 </span> 器——指定FTP伺服器的名稱。在本例中，它是 
            <code>
              uploads.google.com 
            </code>。 請勿包含通訊協定或「ftp://」之前。 </p> <p> <span class="uicontrol"> FTP使用者 </span> 名稱——指定FTP帳戶的名稱。 </p> <p> <span class="uicontrol"> FTP密 </span> 碼——指定FTP帳戶的密碼。 </p> <p> <span class="uicontrol"> FTP檔案名 </span> 稱——指定要傳輸的檔案名稱。如果動態消息產生多個檔案，此名稱是範本，通常會在名稱結尾但在副檔名之前增加一個數字。 例如：basename.xml, basename1.xml, basename2.xml, ..., basename-Nth.xml </p> <p> <span class="uicontrol"> FTP目 </span> 錄——如果需要特定目錄路徑，請在此處輸入。請勿將檔案名稱包含在路徑中。 </p> </li> 
          <li id="li_5990927146434DAF89273F4636D21437"> <span class="uicontrol"> 代管內容網路  </span> <p>「內容網路」是從網站搜尋／銷售的網站伺服器伺服檔案的方式。 動態消息的收件者使用HTTP請求從Web伺服器提取它。 </p> <p> 
            <!--After the base filename is entered and the feed is successfully saved, the URL of the Content Network file is displayed on the Verification panel of the wizard. The URL becomes active after the feed is successfully processed. The vendor can get the feed data from this URL. Multiple files use the same URL path. However, be sure that you replace or change the filename according to the enumeration scheme. --> </p> </li> 
          </ul> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>5 </p> </td> 
      <td colname="col2"> <p>驗證 </p> </td> 
      <td colname="col3"> <p>當您進入「<span class="wintitle">驗證</span>」面板時，您的動態消息會儲存在該點。 不過，實際的動態消息檔案要等到稍後才會儲存。 </p> <p><span class="wintitle">驗證</span>面板可讓您執行下列動作： </p> 
        <ul id="ul_4A94355A8DF840A3BAF6BD5E9F11C27F"> 
        <li id="li_825697CB36B34C4AB5959B15EDDB55F1"> <span class="uicontrol"> 資料檢視  </span> <p>可讓您按一下連結，以透過以表格形式顯示的資料檢視來檢查動態消息輸出。 資料檢視也可協助您疑難排解，顯示選取哪些中繼欄位，以及精靈中<span class="wintitle">搜尋准則</span>面板中任何指定的搜尋准則對饋送輸出有何影響。 資料檢視會動態產生，因此隨時都可使用。 </p> </li> 
        <li id="li_91B8B5F5F9DE4A13863CD62F74AA6206"> <span class="uicontrol"> 摘要檔案  </span> <p>在網站搜尋／銷售伺服器產生動態消息檔案後，您可以使用<span class="uicontrol"> 「動態消息檔案</span>」下拉式清單來檢視伺服器中的檔案。 新的瀏覽器標籤或新的瀏覽器視窗會與動態消息的內容一起出現。 此方法可協助您疑難排解格式問題的動態消息。 請注意，您不會從最終目標或廠商本身檢視檔案。 </p> <p> 如果動態消息是新的，則下拉式清單會是空的，直到您產生動態消息檔案為止。 </p> </li> 
        <li id="li_4A5EC089628E43029A38F8919888FF0A"> <span class="uicontrol"> 內容網路連結  </span> <p>如果您在精靈的<span class="wintitle">檔案提交</span>面板中選擇<span class="uicontrol">代管內容網路</span>作為上傳方法，URL會顯示在此處。 如果您尚未產生任何動態消息檔案，則URL在成功產生動態消息之前無效。 </p> </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

   **Google網站地圖**

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>面板 </p> </th> 
      <th colname="col2" class="entry"> <p>精靈面板名稱 </p> </th> 
      <th colname="col3" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>3 </p> </td> 
      <td colname="col2"> <p>摘要名稱 </p> </td> 
      <td colname="col3"> <p>指定動態消息的名稱。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>2 </p> </td> 
      <td colname="col2"> <p>欄位地圖 </p> </td> 
      <td colname="col3"> <p>可讓您將廠商特定的饋送欄位對應至網站搜尋／銷售中繼資料欄位。 精靈中的此對應步驟很重要，因為它可讓動態消息將索引中欄位與動態消息資料欄位之間的資訊建立關聯。 在大多數情況下，除<span class="wintitle">一般饋送</span>外，關聯會儲存在動態產生的搜尋範本中。 </p> <p>「欄位映射」表中的每一行都表示欄位映射。 在表格的「添加／刪除」列中，按一下<span class="uicontrol"> + </span>添加新欄位映射行；按一下<span class="uicontrol"> - </span>從表中刪除當前選定的欄位映射行。 若要將動態消息欄位與中繼資料欄位建立關聯，請使用個別的下拉式清單來選擇所要的欄位。 </p> <p> <b>進階使用</b> </p> <p>您可以建立自己的自訂欄位。 在「<span class="wintitle">饋送欄位</span>」下拉式清單中，按一下「自訂</span>」。 <span class="uicontrol">在關聯的文字欄位中，輸入該欄位的自訂標籤名稱。 如果動態消息需要特定於供應商的特殊欄位，此自訂選項很實用。 </span></p> <p>您也可以建立自訂中繼資料欄位。 在<span class="wintitle">中繼資料欄位</span>下拉式清單中，按一下<span class="uicontrol">自訂</span>。 在關聯的文字欄位中，輸入自訂中繼資料欄位值。 值會插入預先產生的範本中，也可用來插入自訂搜尋範本標籤。 </p> <p>請參閱<a href="../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4" type="reference" format="dita" scope="local">搜尋範本標籤</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>3 </p> </td> 
      <td colname="col2"> <p>搜尋標準 </p> </td> 
      <td colname="col3"> <p>產生饋送檔案時，會使用搜尋查詢來篩選資料。 您可以在此面板中定義用於搜尋查詢的篩選器。 </p> 
        <ul id="ul_994585E89A044BD3A89A99D30F277432"> 
        <li id="li_61FA9246B9824E3C8124958C8EBFF0DA"> <span class="uicontrol"> 中繼欄位  </span> <p>定義您要篩選的中繼資料欄位。 </p> <p> <b>進階使用</b> </p> <p>由於過濾系統是標準搜索查詢，因此您可以從下拉清單中選擇<span class="uicontrol">自由格式</span>以輸入CGI搜索參數及其值。 需要URL逸出。 將忽略搜索引數<span class="codeph"> sp_q </span>。 您可以建立多列自由表單文字方塊。 在每一行之間，引數會自動以&amp;'s分隔。 </p> <p>請參閱<a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local">搜索CGI參數</a>。 </p> </li> 
        <li id="li_A5D00883738845C8B8F612A7521F160F"> <span class="uicontrol"> 標準 </span> <p>定義篩選操作。 您從下拉式清單中選擇的篩選操作會套用在第三欄中輸入的常數值。 </p> </li> 
        <li id="li_5A312C2984454C2CB518CA453AD9F6D2"> <span class="uicontrol"> 值 </span> <p>常數值。 </p> </li> 
        <li id="li_666AAE1BC7A2432E91953B08EC7394DC"> <span class="uicontrol"> 動作 </span> <p>新增欄位對應列，或刪除目前反白顯示的列。 </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>4 </p> </td> 
      <td colname="col2"> <p>檔案提交 </p> </td> 
      <td colname="col3"> <p>可讓您設定提交動態消息檔案的排程，並設定您要用來上傳檔案的方法。 </p> 
        <ul id="ul_49B3255BE669424B925BBAEE4C9B385F"> 
        <li id="li_939828C774D440EBB0769F6D5B0BBA23"> <span class="uicontrol"> 排程 </span> <p>設定動態消息提交的最大頻率。 選取「<span class="uicontrol">永不</span>」會關閉動態消息。 其他值會定義動態消息在再次送出之前等待的時段。 何時提交動態消息的決定是在每個索引上完成。 換言之，在索引結束時，會檢查動態消息，以查看其是否已過期，且需要由廠商更新並提交。 此外，它也可用來防止帳戶過度提交給廠商。 有些廠商針對上傳頻率過高的資料饋送來源制定政策。 請確定您已檢查動態消息供應商的提交頻率政策。 </p> <p> 
          <!--The time of the last upload and the status of the upload feed is displayed here. If any other feeds are currently running, their status appears here instead. Each account processes one feed at a time. --> </p> <p> 
          <!--Click <uicontrol>Manual Upload</uicontrol> to generate the feed and push the files to the final destination. Any schedule restrictions that you have already set are ignored. --> </p> <p> 
          <!--If <uicontrol>Manual Upload</uicontrol> is dimmed (inactive), the account is currently processing this feed or another feed. An account only works with one feed at a time. --> </p> </li> 
        <li id="li_07B5BCF7936241A7915C4898B231184B"> <span class="uicontrol"> 上傳方法  </span> <p>大部份的動態消息有兩種散發檔案的方式：FTP和代管內容網路。 </p> 
          <ul id="ul_74FA98A82754469BA5FADCC63FC364F7"> 
          <li id="li_02940B712D6444A8B65C0A51834187E6"> <span class="uicontrol"> FTP  </span> <p>網站搜尋／銷售伺服器使用被動式FTP。 </p> <p>FTP是將檔案推送至其他伺服器的唯一方式。 </p> <p> <span class="uicontrol"> FTP伺服 </span> 器——指定FTP伺服器的名稱。請勿包含通訊協定或「ftp://」之前。 </p> <p> <span class="uicontrol"> FTP使用者 </span> 名稱——指定FTP帳戶的名稱。 </p> <p> <span class="uicontrol"> FTP密 </span> 碼——指定FTP帳戶的密碼。 </p> <p> <span class="uicontrol"> FTP檔案名 </span> 稱——指定要傳輸的檔案名稱。如果動態消息產生多個檔案，此名稱是範本，通常會在名稱結尾但在副檔名之前增加一個數字。 例如：basename.xml, basename1.xml, basename2.xml, ..., basename-Nth.xml </p> <p> <span class="uicontrol"> FTP目 </span> 錄——如果需要特定目錄路徑，請在此處輸入。請勿將檔案名稱包含在路徑中。 </p> </li> 
          <li id="li_EAE504436CD84452BA04BE51855A2BEF"> <span class="uicontrol"> 代管內容網路  </span> <p>「內容網路」是從網站搜尋／銷售的網站伺服器伺服檔案的方式。 動態消息的收件者使用HTTP請求從Web伺服器提取它。 </p> <p> 
            <!--After the base filename is entered and the feed is successfully saved, the URL of the Content Network file is displayed on the Verification panel of the wizard. The URL becomes active after the feed is successfully processed. The vendor can get the feed data from this URL. Multiple files use the same URL path. However, be sure that you replace or change the filename according to the enumeration scheme. --> </p> </li> 
          </ul> </li> 
        </ul> <p>請注意，上傳方法中的任一方法都要求您在<span class="wintitle">主網站地圖URL </span>欄位中指定Google用來擷取網站地圖的URL。 網站地圖檔案的名稱也會在此處確定。 如果您的網站地圖很大，則可能存在多個檔案，命名約定是在檔案末尾附加一個索引號，從編號1開始。 第一個檔案或索引檔案沒有索引，如<span class="codeph"> sitemap.xml </span>、<span class="codeph"> sitemap1.xml </span>、<span class="codeph"> sitemap2.xml </span>中……<span class="codeph"> sitemap12.xml </span>。 </p> <p>如果您選擇<span class="uicontrol">代管內容網路</span>作為上傳方法，檔案的URL會有相同的檔名，但URL會有代管服務的路徑和主機名稱。 因此，您會將網站地圖的請求重新導向至「代管內容網路」。 您也應該能夠從相同位置提取檔案。 </p> <p>建立動態消息檔案並送出至中介目標後，Google會被Ping化，讓他們知道網站地圖動態消息已就緒。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>5 </p> </td> 
      <td colname="col2"> <p>驗證 </p> </td> 
      <td colname="col3"> <p>當您進入「<span class="wintitle">驗證</span>」面板時，您的動態消息會儲存在該點。 不過，實際的動態消息檔案要等到稍後才會儲存。 </p> <p><span class="wintitle">驗證</span>面板可讓您執行下列動作： </p> 
        <ul id="ul_A1D889A84972419599FC83F39EA2676A"> 
        <li id="li_C8ED077B6DD1461E85A4914C1CFDBE88"> <span class="uicontrol"> 資料檢視  </span> <p>可讓您按一下連結，以透過以表格形式顯示的資料檢視來檢查動態消息輸出。 資料檢視也可協助您疑難排解，顯示選取哪些中繼欄位，以及精靈中<span class="wintitle">搜尋准則</span>面板中任何指定的搜尋准則對饋送輸出有何影響。 資料檢視會動態產生，因此隨時都可使用。 </p> </li> 
        <li id="li_DACEE40703AF40EFBCD90D43825CE9C1"> <span class="uicontrol"> 摘要檔案  </span> <p>在產生動態消息檔案後，您可以使用<span class="uicontrol"> 「動態消息檔案</span>」下拉式清單來檢視伺服器中的檔案。 新的瀏覽器標籤或新的瀏覽器視窗會與動態消息的內容一起出現。 此方法可協助您疑難排解格式問題的動態消息。 請注意，您不會從最終目標或廠商本身檢視檔案。 </p> <p> 如果動態消息是新的，則下拉式清單會是空的，直到您產生動態消息檔案為止。 </p> </li> 
        <li id="li_1C530354B4F34EC79D92CEFEB5B39ED7"> <span class="uicontrol"> 內容網路連結  </span> <p>如果您在精靈的<span class="wintitle">檔案提交</span>面板中選擇<span class="uicontrol">代管內容網路</span>作為上傳方法，URL會顯示在此處。 如果您尚未產生任何動態消息檔案，則URL在成功產生動態消息之前無效。 </p> </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

1. 完成嚮導中的步驟後，按一下&#x200B;**[!UICONTROL Close]**。

## 編輯動態消息{#task_B855D28CD99B4FA58E2D4D4FD6DC9CEB}

您可以編輯現有動態消息的設定。

<!-- 

t_editing_a_feed.xml

 -->

>[!NOTE]
>
>當您編輯動態消息時，無法變更動態消息類型。 如果您需要變更動態消息類型，請刪除現有的動態消息，然後以您想要的類型新增動態消息。

請參閱[刪除動態消息](../c-about-settings-menu/c-about-searching-menu.md#task_7E39A140E69D43C6B61FB42E81051269)。

**若要編輯動態消息**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]**」。
1. 進行以下一項操作: 

* 在[!DNL Feeds]頁面的表格[!DNL Name]欄下，按一下動態消息名稱旁的下拉式清單，然後按一下&#x200B;**[!UICONTROL Edit feed]**。

* 在[!DNL Feeds]頁面的[!DNL Name]欄下，按一下您要變更的動態消息名稱。

1. 在動態消息精靈中，針對精靈中的每個面板設定您想要的選項。

   請參閱&#x200B;**新增動態消息下的選項表。**
1. 在嚮導的末尾，在[!DNL Verification]面板中，按一下&#x200B;**[!UICONTROL Close]**。

## 刪除動態消息{#task_7E39A140E69D43C6B61FB42E81051269}

您可以刪除不再需要或使用的動態消息。

<!-- 

t_deleting_a_feed.xml

 -->

**若要刪除動態消息**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]**」。
1. 在[!DNL Feeds Menu]畫面的[!DNL Actions]欄下方，按一下&#x200B;**[!UICONTROL Delete]**&#x200B;以取得您要移除的動態消息名稱。
1. 在[!DNL Delete feed]對話方塊中，按一下&#x200B;**[!UICONTROL Yes]**&#x200B;以確認刪除。

## 檢視動態消息檔案{#task_1E413C7650DE466EA68925F72E086884}

您可前往「動態消息」精靈的最後一個面板，讓您快速存取檢視動態消息的資料檢視，或從伺服器下載任何目前的動態消息檔案。 如果您想要驗證並檢查動態消息輸出，此功能會很有用。

<!-- 

t_viewing_feed_files.xml

 -->

**若要檢視動態消息檔案**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]**」。
1. 在[!DNL Feeds]頁面的表格[!DNL Name]欄下，按一下動態消息名稱旁的下拉式清單，然後按一下&#x200B;**[!UICONTROL View Feed Files]**。
1. 在動態消息嚮導的[!DNL Verification]面板中，按一下&#x200B;**[!UICONTROL Show Data View]**。
1. 按一下 **[!UICONTROL Close]**.

## 測試沒有檔案上傳的動態消息{#task_F1F390F72E0A4886B6CD4CD86EDB4C8C}

您可以測試動態消息，而不需將檔案上傳至最終目的地。

<!-- 

t_testing_a_feed_with_no_file_upload.xml

 -->

**若要測試沒有檔案上傳的動態消息**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]**」。
1. 在[!DNL Feeds]頁面的表格[!DNL Name]欄下，按一下動態消息名稱旁的下拉式清單，然後按一下&#x200B;**[!UICONTROL Test Feed (No file upload)]**。
1. 在[!DNL Feeds]頁面上，[!DNL Feed Status]欄會在測試期間和測試後進行更新。

## 產生並上傳動態消息{#task_C9A57827C7674035B62A22D310DDAA0C}

不論您在動態消息精靈的[!DNL File Submission]面板中設定的排程為何，您都可以手動產生動態消息檔案並送出至最終目的地。

<!-- 

t_generating_and_uploading_a_feed.xml

 -->

另請參閱[建立動態消息](../c-about-settings-menu/c-about-searching-menu.md#task_63179C1FC359497483CD6CE13FD1C250)。

**若要產生和上傳動態消息**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]**」。
1. 在[!DNL Feeds]頁面的表格[!DNL Name]欄下，按一下動態消息名稱旁的下拉式清單，然後按一下&#x200B;**[!UICONTROL Generate and Upload Feed]**。
1. 在[!DNL Feeds]頁面上，[!DNL Feed Status]欄會在產生和上傳資料饋送期間及之後更新。
