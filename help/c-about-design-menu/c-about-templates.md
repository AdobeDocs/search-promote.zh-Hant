---
description: 您可以使用範本來管理您的簡報範本和傳輸範本。
seo-description: 您可以使用範本來管理您的簡報範本和傳輸範本。
seo-title: 關於範本
solution: Target
title: 關於範本
topic: Design,Site search and merchandising
uuid: f5805d3e-43bf-4e13-95df-b6bd6b762d11
translation-type: tm+mt
source-git-commit: 60cedaac1846e384a37699a42bf7fda33828e1c0
workflow-type: tm+mt
source-wordcount: '2661'
ht-degree: 1%

---


# 關於模板{#about-templates}

您可以使用&#x200B;**[!UICONTROL Templates]**&#x200B;來管理簡報範本和傳輸範本。

## 關於模板{#concept_06EB481B14864E18A8AE2BCD1D6EF0B5}

<!-- 

c_about_templates.xml

 -->

您可以新增、編輯、複製、重新命名或刪除簡報範本和傳輸範本。 當您按一下「範本」(Templates)表格中的現有範本名稱時，它會在編輯器（或檢視器）視窗中開啟，您可在此視窗中進行變更。

您可以使用範本名稱下拉式清單中的「步驟記錄」功能，回復您對範本所做的任何變更。

您可以勾選範本表格中範本對應的&#x200B;**[!UICONTROL Minimize]**&#x200B;核取方塊，以降低簡報範本的頁面重量。 借由降低範本的頁面權重，您可以動態地將內嵌JavaScript和CSS降到最低。 您也可以移除HTML中的多餘空白字元。 將簡報範本的頁面重量減到最低，有助於更快速地傳遞搜尋結果。

您可以按一下檔案名稱旁的下拉式清單，然後按一下&#x200B;**[!UICONTROL Preview minimized]**，以預覽最小化範本的外觀。 如果您最小化主演示模板，請務必記得啟用最小化包含範本（使用`guided-include`標籤）模板，因為此選項不可繼承。

即使您將簡報範本減到最低，您仍可編輯相同範本的「未最小化」版本。

您可以使用搜尋前規則、搜尋後規則和業務規則來決定何時使用其他簡報範本。 常有的規則，例如「針對每個搜尋，將目標範本設為xxxx」。 當您在「範本」表格中變更「預設」範本時，此規則似乎沒有作用。

請參閱[關於預搜索規則](../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F)。

請參閱[關於搜尋後規則](../c-about-rules-menu/c-about-post-search-rules.md#concept_AF6ADFCC0ADF4A788003964939917FDE)。

請參閱[關於業務規則](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD)。

## 關於演示模板{#section_ACDDEA5C499E481C828A517C230D4596}

簡報範本是客戶在網站上檢視搜尋結果時所看到的HTML範本。

在您的表現層中，您可以有單一的表現範本，來呈現來自不同來源的多項搜尋結果。 您可以定義任意數量的簡報範本，甚至可以使用`include`命令定義其他範本共用的簡報範本。 簡報範本是所有設計元件（例如刻面、選單和階層連結）匯整在一起的地方。 若要顯示各種設計元件，您必須使用簡報範本標籤。

請參閱[簡報範本標籤](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)

當您有多個簡報範本時，您可在何種條件下定義使用各種簡報範本。 您可以根據傳入的CGI參數和Cookie來選擇要使用的演示模板。 或者，您可以根據先前搜尋的結果來切換您使用的簡報範本。

當您使用多個簡報範本時，請務必指出您希望搜尋結果一開始顯示的範本。 您可以使用「模板」(Templates)表格的&#x200B;**[!UICONTROL Default]**&#x200B;列來執行此操作。

## 關於傳輸模板{#section_35FD3E8AAA4E4695A737DB7E00C3258B}

傳輸範本可以是XML或JSON範本，可將資料從後端搜尋傳遞至引導式搜尋表現層。

依預設，您的帳戶會設定為使用XML傳輸範本。 不過，如果您偏好使用JSON將資料傳遞至「引導式搜尋」，請聯絡可協助您的Adobe諮詢。

在您的表現層中，您可以有單一的表現範本，來呈現多個搜尋的結果。 每個搜尋都可以使用相同的傳輸範本或自訂傳輸範本，將資料傳遞至表現層。 由於傳輸範本僅用於將資料傳遞至表現層，因此它不得有任何HTML用於顯示搜尋結果。 範本使用傳輸範本標籤來傳遞搜尋結果和填入Facet的結果。 在這些標籤中，標準搜尋範本標籤可用來顯示實際值。

請參閱[搜尋範本標籤](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

**XML傳輸模板特定標籤**

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>XML傳輸範本標籤 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-xml&gt;&lt;/guided-xml&gt; </span> </p> </td> 
   <td colname="col2"> <p>這些是表示層用來偵測傳輸範本中必須剖析的根XML標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;general&gt;&lt;/general&gt; </span> </p> </td> 
   <td colname="col2"> <p>這組標籤圍繞搜索模板標籤，這些標籤根據結果集提供摘要資料。 通常，這些標籤包含搜尋標籤，用於搜尋結果總數、最低結果和最高結果。 您可以使用<span class="codeph"> general-field </span>標籤定義任意數量的附加全局欄位。 </p> <p> <b>範例</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;general&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;total&gt;&lt;search-total&nbsp;/&gt;&lt;/total&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;lower&gt;&lt;search-lower&nbsp;/&gt;&lt;/lower&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;upper&gt;&lt;search-upper&nbsp;/&gt;&lt;/upper&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;general-field&nbsp;name="my_custom_field"&gt;Some&nbsp;global&nbsp;content&lt;/general-field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/general&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;results&gt;&lt;/results&gt; </span> </p> </td> 
   <td colname="col2"> <p>這組標籤會包住搜尋結果，讓「搜尋指南」知道要在何處尋找。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result&gt;&lt;/result&gt; </span> </p> </td> 
   <td colname="col2"> <p>這組標籤會包住每個搜尋結果，因此引導式搜尋會識別單一搜尋結果的內容開始和結束的位置。 </p> <p> <b>範例</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;index&gt;&lt;search-index&nbsp;/&gt;&lt;/index&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;loc&gt;&lt;search-cdata&gt;&lt;search-url&nbsp;length="500"&nbsp;/&gt;&lt;/search-cdata&gt;&lt;/loc&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;attribute-table name="tablename"&gt; </span> </p> </td> 
   <td colname="col2"> <p>此標籤可讓您重複檢視多值清單中的每個項目，以產生單一結果。 僅在結果中使用標籤。 其主要用途是讓您重複屬於結果欄位的屬性。 </p> <p> <b>範例</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;index&gt;&lt;search-index&nbsp;/&gt;&lt;/index&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;loc&gt;&lt;search-url&nbsp;/&gt;&lt;/loc&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;title&gt;&lt;search-title&nbsp;/&gt;&lt;/title&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;attribute-table&nbsp;name="downloads"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;field&nbsp;name="download_title"&gt;&lt;search-display-field&nbsp;name="download_title"&nbsp;/&gt;&lt;/field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;field&nbsp;name="download_link"&nbsp;delimiter="|"&gt;&lt;search-display-field&nbsp;name="download_link"&nbsp;/&gt;&lt;/field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/attribute-table&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facets&gt;&lt;/facets&gt; </span> </p> </td> 
   <td colname="col2"> <p>這組標籤會傳遞填入Facet的結果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet name="name"&gt;&lt;/facet&gt; </span> </p> </td> 
   <td colname="col2"> <p>每個Facet都必須有其自己的Facet標籤，其中name參數與Facet名稱相符。 搜尋標籤會在Facet標籤中用於Facet值。 </p> <p>請參閱<a href="../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5" type="concept" format="dita" scope="local">關於Facet </a>。 </p> <p> <b>範例</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;facets&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;facet&nbsp;name="brand"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/facet&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;facet&nbsp;name="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/facet&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/facets&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;suggestions&gt;&lt;/suggestions&gt; </span> </p> </td> 
   <td colname="col2"> <p>這組標籤會包住您的「您的意思」建議，讓「搜尋指南」識別哪些XML節點包含建議。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;suggestion&gt;&lt;/suggestion&gt; </span> </p> </td> 
   <td colname="col2"> <p>這組標籤會包住每個「您的意思」建議。 </p> <p> <b>範例</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;search-if-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;suggestion&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;value&gt;&lt;search-suggestion-text&nbsp;/&gt;&lt;/value&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;count&gt;&lt;search-suggestion-result-count&nbsp;/&gt;&lt;/count&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/suggestion&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-if-suggestions&gt; </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**JSON傳輸範本特定標籤**

已知從搜尋引擎傳遞JSON與XML的速度較快，因為它的裝載較小，剖析器也較快。 不過，當您使用JSON時，請小心使用，以確保輸出內容為嚴格的JSON，因為剖析器不容許。

如果您是JSON的新手，可使用下列連結和範例來協助您開始使用：

* JSON簡介。 請參閱[https://www.json.org/](https://www.json.org/)。
* 測試您的JSON以確保其有效。 請參閱[https://jsonlint.com/](https://jsonlint.com/)。

**範例JSON範本**

```
{ 
 "general": 
 { 
  "total" : "<search-total />", 
  "lower" : "<search-lower />", 
  "upper" : "<search-upper />", 
  "rbt-trigger-list" : "<search-rbta-trigger-id-list>", 
  "fields" :  
  [ 
   { 
    "name" : "seo_search_title", 
    "value" : "<search-include file="seo/seo_search_title.tpl" />" 
   }, 
   { 
    "name" : "seo_search_keywords", 
    "value" : "<search-include file="seo/seo_search_keywords.tpl" />" 
   } 
  ] 
 }, 
 
 <search-if-suggestions> 
 "suggestions": 
  [ 
  <search-suggestions> 
  { 
   "suggestion":"<search-suggestion-text />", 
   "count": "<search-suggestion-result-count>" 
  }<search-if-not-last-suggestion>,</search-if-not-last-suggestion> 
  </search-suggestions> 
 ], 
 </search-if-suggestions> 
 
 "facets" : 
 [ 
  { 
   "name" : "leveli", 
   "values" : [ <search-field-value-list name="leveli" quotes="yes" sortby="values" data="values" encoding="json"/>], 
   "counts" : [<search-field-value-list name="leveli" quotes="no" sortby="values" data="results" />] 
  }, 
  { 
   "name" :"levelii", 
   "values" : [<search-field-value-list name="levelii" quotes="yes" sortby="values" data="values" encoding="json"/>], 
   "counts" : [<search-field-value-list name="levelii" quotes="no" sortby="values" data="results" />] 
  }, 
  { 
   "name" : "brand", 
   "values" : [<search-field-value-list name="brand" quotes="yes" sortby="values" data="values" encoding="json"/>], 
   "counts" : [<search-field-value-list name="brand" quotes="no" sortby="values" data="results" />] 
  }, 
 ], 
 "results" : 
 [ 
  <search-results> 
  { 
   "fields" : 
   [ 
    { 
     "name" : "index", 
     "value" : "<search-index />" 
    }, 
    { 
     "name" : "loc", 
     "value" : "<search-display-field name="url" length="500" encoding="json"/>" 
    }, 
    { 
     "name" : "title", 
     "value" : "<search-display-field name="title" encoding="json"/>" 
    }, 
    { 
     "name" : "img_url_thumbnail", 
     "value" : "<search-display-field name="img_url_thumbnail" encoding="json"/>" 
    }, 
    { 
     "name" : "description", 
     "value" : "<search-display-field name="description" encoding="json"/>" 
    }, 
    { 
     "name" : "mdi", 
     "value" : "<SEARCH-RBTA-DISPLAY-MDI-FIELD>" 
    } 
   ] 
  }<search-if-not-last>,</search-if-not-last>  
  </search-results> 
 ] 
}
```

**具有結果屬性表的JSON結果區範例**

```
{ 
 "results" : 
 [ 
  <search-results> 
  { 
   "fields" : 
   [ 
    { 
     "name" : "index", 
     "value" : "<search-index />" 
    }, 
    { 
     "name" : "loc", 
     "value" : "<search-display-field name="url" length="500" encoding="json"/>" 
    } 
   ], 
   "tables" : 
   [ 
    { 
     "name" : "downloads", 
     "fields" : 
     [ 
      { 
       "name" : "download_title", 
       "value" : <search-display-field name="download_title" encoding="json"/> 
      }, 
      { 
       "name" : "download_link", 
       "value" : <search-display-field name="download_link" encoding="json"/> 
      } 
     ] 
    } 
   ] 
  }<search-if-not-last>,</search-if-not-last>  
  </search-results> 
 ] 
}
```

**具有關聯欄位之Facet的JSON Facet區段範例**

```
{ 
 facets" : 
 [ 
  { 
   "name" : "t1", 
   "values" : [<search-field-value-list name="t1" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />], 
   "counts" : [<search-field-value-list name="t1" quotes="yes" commas="yes" data="results" sortby="values" />], 
   "custom-fields" : 
   [ 
    { 
     "name" : "taxonmyId", 
     "value" : [<search-field-value-list name="tax1" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />] 
    } 
   ] 
  } 
 ] 
}
```

**槽刻面的JSON Facet區段範例**

```
{ 
  "facets" : 
  [  
   { 
    "name" : "fvalue0", 
                  "dynamic" : 1, 
                  "display-names" : [<search-field-value-list name="fname0" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />], 
    "values" : [<search-field-value-list name="fvalue0" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />], 
    "counts" : [<search-field-value-list name="fvalue0" quotes="no" commas="yes" data="results" sortby="values" />] 
   } 
  ] 
} 
```

## 添加新的演示或傳輸模板檔案{#task_73199757B6E748CAA604902FF913F012}

您可以使用&#x200B;**[!UICONTROL Add Template]**&#x200B;將簡報範本(.tmpl)或傳輸範本(.tpl)新增至[!DNL Templates]頁面。

<!-- 

t_adding_a_new_presentation_or_transport_template_file.xml

 -->

**若要新增簡報或傳輸範本檔案**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Templates]**」。
1. 在[!DNL Templates]頁面上，按一下&#x200B;**[!UICONTROL Add New Template]**。
1. 在[!DNL Add Template]對話方塊中，設定您想要的選項。

   <!-- 
   
   r_add_template_options.xml
   
   -->

   | 選項 | 說明 |
   |--- |--- |
   | 新檔案名稱 | 指定要添加的模板的名稱。 會根據您選取的範本類型，自動將正確的副檔名新增至檔案名稱。  簡報範本有。tmpl副檔名；傳輸範本的副檔名為。tpl。 |
   | 新範本類型 | 可讓您選擇要新增的簡報或傳輸範本。  請參閱[關於模板](../c-about-design-menu/c-about-templates.md)。 |

   另請參閱[編輯演示或傳輸模板](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3)。
1. 按一下 **[!UICONTROL Add]**.
1. （可選）在[!DNL Templates]頁面上，執行下列其中一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 編輯演示或傳輸模板{#task_800E0E2265C34C028C92FEB5A1243EC3}

您可以使用範本編輯器來檢視和編輯簡報和傳輸範本檔案的內容。

<!-- 

t_editing_a_template.xml

 -->

您可以編輯和測試分段簡報和傳輸範本，而您的網站訪客則會繼續使用即時版本的範本。 您可使用搜尋網域URL的分段版本來測試分段範本。 例如，您可以通過運行具有設定為傳輸模板名稱的`sp_t`的分段查詢(`sp_staged=1`)來測試分段傳輸模板。 當您對版面的顯示方式感到滿意時，可在範本編輯器中使用&#x200B;**[!UICONTROL Push Live]**&#x200B;來即時推播範本。 範本上線後，網站訪客就會開始使用它。

使用簡報範本標籤參考，瞭解如何將簡報範本連結至引導式搜尋元件，例如刻面、階層連結和功能表。

請參閱[簡報範本標籤](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)

使用傳輸範本標籤參考，進一步瞭解要用於傳輸範本的標籤。

請參閱[傳輸範本標籤](../c-appendices/c-templates.md#reference_227D199F5A7248049BE1D405C0584751)

**[!UICONTROL To edit a presentation or a transport template]**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Templates]**」。
1. 在[!DNL Templates]頁面上，按一下簡報或傳輸範本檔案名稱。
1. 在[!DNL Template Editor]頁面上，對標籤和編碼進行變更。

   請留意您在[!DNL Template Editor]中所做的變更；沒有「還原」功能。 如果您進行了不想要的更改，並想要返回到檔案的先前版本，可按一下&#x200B;**[!UICONTROL Cancel]**&#x200B;返回模板表（假定您到目前為止未保存任何更改）。 如果您已儲存變更，則可在編輯器中使用&#x200B;**[!UICONTROL History]**&#x200B;來回復這些變更。
1. （可選）按一下&#x200B;**[!UICONTROL Insert Symbol]**，輸入美國英文鍵盤上沒有對應鍵的特殊字元和符號。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

1. 完成時關閉「模板編輯器」頁；您會返回「範本」頁面。

## 複製演示或傳輸模板檔案{#task_B744AB3384C84DD59C33CD25E18C2C90}

您可以使用&#x200B;**[!UICONTROL Copy Template]**&#x200B;複製現有的簡報範本(.tmpl)或傳輸範本(.tpl)，並將它新增至「範本」頁面，以節省時間。

<!-- 

t_copying_a_presentation_or_a_transport_template.xml

 -->

您必須變更範本名稱、範本類型或兩者。 如果您未進行任何變更，則不會複製範本。

您必須已新增範本，才能複製範本。

請參閱[新增簡報或傳輸範本檔案](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)。

**複製演示或傳輸模板檔案**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Templates]**」。
1. 在[!DNL Templates]頁面中，在您要複製的範本名稱旁的下拉式清單中，按一下&#x200B;**[!UICONTROL Copy]**。
1. 在[!DNL Copy Template]對話方塊中，設定您想要的一或多個選項。
1. 按一下 **[!UICONTROL Copy]**.
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 更名演示文稿或傳輸模板檔案{#task_CC30050FC2DE4898BF44379D8378EB31}

您可以使用[!DNL Rename Template]來變更現有簡報範本(.tmpl)或傳輸範本(.tpl)的名稱。

<!-- 

t_renaming_a_presentation_or_a_transport_template_file.xml

 -->

您也可以視需要變更範本類型。

您必須已新增範本，才能重新命名範本。

請參閱[新增簡報或傳輸範本檔案](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)。

**更名演示或傳輸模板檔案**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Templates]**」。
1. 在[!DNL Templates]頁面中，在您要重新命名的範本名稱旁的下拉式清單中，按一下&#x200B;**[!UICONTROL Rename]**。
1. 在[!DNL Rename Template]對話方塊中，設定您想要的一或多個選項。
1. 按一下 **[!UICONTROL Rename]**.
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 刪除演示或傳輸模板檔案{#task_67E532C2B83A449687737E3B06C5AA58}

您可以使用&#x200B;**[!UICONTROL Delete Template]**&#x200B;移除現有的簡報範本(.tmpl)或傳輸範本(.tpl)。

<!-- 

t_deleting_a_presentation_or_a_transport_template_file.xml

 -->

您可能已擁有已推送至即時的分段範本對應版本。 如果是，請確定您使用&#x200B;**[!UICONTROL Staging]**&#x200B;將已刪除的範本推送為即時，如此也會從即時環境中刪除。 或者，您也可以在「範本」頁面上使用&#x200B;**[!UICONTROL Push Live]**。

請參閱[關於測試](../c-about-staging.md#concept_08B8F3CA1F4241108F14BA7FC7806CA7)

請參閱[即時推送階段設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)

您必須已新增範本，才能刪除範本。

請參閱[新增簡報或傳輸範本檔案](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)

**刪除演示或傳輸模板檔案**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Templates]**」。
1. 在[!DNL Templates]頁面上，在要刪除的範本名稱旁的下拉式清單中，按一下&#x200B;**[!UICONTROL Delete]**。
1. 在[!DNL Delete Template]對話框中，按一下&#x200B;**[!UICONTROL Delete.]**
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 預覽簡報範本已最小化{#task_1757B6207CC74221AE4BFFE5674D320B}

您可以使用&#x200B;**[!UICONTROL Preview minimized]**&#x200B;來查看簡報範本的頁面重量減輕後，如果您選擇將其減至最小。

<!-- 

t_previewing_the_presentation_template_minimized.xml

 -->

如果您將主要簡報範本最小化，請務必記得啟用最小化包含範本（使用引導式包含標籤），因為此選項不可繼承。

請參閱[降低您的簡報範本的頁面重量……](../c-about-design-menu/c-about-templates.md#task_B09BB3CE89714DEAAE8D9A899CF3009E)

您必須已新增範本，才能將範本最小化。

請參閱[新增簡報或傳輸範本檔案](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)

您可以預覽傳輸範本檔案的XML程式碼。

請參閱[預覽傳輸範本檔案的XML](../c-about-design-menu/c-about-templates.md#task_58C6C52078E14AD88D2B2F0B3C439AE8)

**若要預覽最小化的簡報範本**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Templates]**」。
1. 在[!DNL Templates]頁面上，在簡報範本名稱旁的下拉式清單中，按一下&#x200B;**[!UICONTROL Preview minimized]**。

   使用「模板」(Templates)表格中的&#x200B;**[!UICONTROL Type]**&#x200B;列，按演示和傳輸對模板進行排序。
1. （可選）在[!DNL Preview Minimized Template]頁面上，勾選&#x200B;**[!UICONTROL Wrap lines]**&#x200B;以讀取已定義視窗中的標籤。
1. 按一下 **[!UICONTROL Close]**.
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 降低網站上簡報範本的頁面重量{#task_B09BB3CE89714DEAAE8D9A899CF3009E}

您可以使用範本表格中的&#x200B;**[!UICONTROL Minimize]**&#x200B;選項來降低簡報範本的頁面重量。

<!-- 

t_reducing_the_page_weight_of_a_presentation_template.xml

 -->

借由降低範本的頁面權重，您可以動態地將內嵌JavaScript和CSS降到最低。 您也可以移除HTML中的多餘空白字元。 將簡報範本的頁面重量減到最低，有助於更快速地傳遞搜尋結果。

您也可以使用&#x200B;**[!UICONTROL Preview minimized]**&#x200B;預覽最小化的演示模板的外觀。

請參閱[預覽最小化的簡報範本](../c-about-design-menu/c-about-templates.md#task_1757B6207CC74221AE4BFFE5674D320B)。

**[!UICONTROL To reduce the page weight of a presentation template on your website]**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Templates]**」。
1. 在[!DNL Templates]頁面的[!DNL Minimize]欄下，勾選您要在網站上以最小化方式推送的一或多個簡報範本檔案方塊。

   使用[!DNL Templates]表格中的&#x200B;**[!UICONTROL Type]**&#x200B;欄，依「簡報」和「傳輸」排序範本。
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 將預設簡報範本檔案設定為用於您的網站{#task_C1E8CE817E4D43E096167A347C54DD53}

當您有多個簡報範本時，可以指出最初用於顯示搜尋結果的範本。

<!-- 

t_setting_the_default_presentation_template_file_to_use.xml

 -->

您可以使用搜尋前規則、搜尋後規則和業務規則來決定何時應使用其他簡報範本。

請參閱[關於預搜索規則](../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F)。

請參閱[關於搜尋後規則](../c-about-rules-menu/c-about-post-search-rules.md#concept_AF6ADFCC0ADF4A788003964939917FDE)。

請參閱[關於業務規則](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD)。

常有的規則，例如「針對每個搜尋，將目標簡報範本設為xxxx」。 有了此類規則，變更「範本」頁面上的「預設」範本似乎無效。

**[!UICONTROL To set the default presentation template file to use on your website]**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Templates]**」。
1. 在[!DNL Templates]頁面的[!DNL Default]欄下，按一下您要當做預設值的對應簡報範本檔案的選項按鈕。

   使用[!DNL Templates]表格中的&#x200B;**[!UICONTROL Type]**&#x200B;欄，依「簡報」和「傳輸」排序範本。
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 預覽傳輸模板檔案{#task_58C6C52078E14AD88D2B2F0B3C439AE8}的XML

您可以使用[!DNL Preview]來查看已添加的傳輸模板的XML。

<!-- 

t_previewing_the_xml_of_a_transport_template_file.xml

 -->

您必須已新增傳輸範本，才能預覽範本的XML。

請參閱[新增簡報或傳輸範本檔案](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)。

您可以預覽最小化的簡報範本檔案，以檢視其減少的頁面重量。

請參閱[預覽最小化的簡報範本](../c-about-design-menu/c-about-templates.md#task_1757B6207CC74221AE4BFFE5674D320B)。

**預覽傳輸模板檔案的XML**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Templates]**」。
1. 在[!DNL Templates]頁面中，在傳輸模板名稱旁的下拉清單中，按一下&#x200B;**[!UICONTROL Preview]**。

   使用[!DNL Templates]表格中的&#x200B;**[!UICONTROL Type]**&#x200B;欄，依「簡報」和「傳輸」排序範本。
1. 關閉查看窗口並返回[!DNL site search/merchandising]。
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

