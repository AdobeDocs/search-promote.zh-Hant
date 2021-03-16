---
description: 您可以使用搜尋引擎最佳化(SEO)中繼標籤，協助您量身打造頁面的特定元素，進而改善搜尋引擎的位置。
solution: Target
subtopic: SEO
title: 關於SEO
topic: 設定、網站搜尋與銷售
uuid: 5c5d64f5-fe79-4489-85c6-399d1437f2c4
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1206'
ht-degree: 1%

---


# 關於SEO{#about-seo}

您可以使用搜尋引擎最佳化(SEO)中繼標籤，協助您量身打造頁面的特定元素，進而改善搜尋引擎的位置。

## 使用SEO {#concept_C58BFCE720824A2B9B5F5E613CFD4C0B}

您可以將每個元素定義為開頭文字，後面接著單字清單。 字詞清單可包含下列：

* 您網站上在選取時段（例如「上個月」）的熱門搜尋片語，但須受您的自訂排除所限。
* 頁面來源搜尋中一或多個欄位的值集。
* 您在清單中定義的靜態字詞和片語

人們最常用的SEO頁面元素是頁面標題，以及「關鍵字」和「說明」中繼標籤。 您可以定義這三個頁面元素的設定。 此外，您可以針對三種頁面類型分別定義這三種設定：搜尋結果頁、瀏覽頁和項目詳細資訊頁。

當您儲存或預覽SEO設定時，會產生搜尋（傳輸）範本的小區段，您可使用`<search-include>`範本標籤加入其他搜尋範本中。 例如，您可以將「搜尋結果頁面標題」欄位包含在另一個範本中，其中包含下列項目：

```
<search-include file="seo/seo_search_title.tpl" />
```

SEO欄位的`<search-include>`標籤`file`屬性的9個可能值如下：

* `seo/seo_search_title.tpl`
* `seo/seo_search_description.tpl`
* `seo/seo_search_keywords.tpl`
* `seo/seo_browse_title.tpl`
* `seo/seo_browse_description.tpl`
* `seo/seo_browse_keywords.tpl`
* `seo/seo_item_title.tpl`
* `seo/seo_item_description.tpl`
* `seo/seo_item_keywords.tpl`

若要在簡報範本中使用SEO欄位，請完成數個步驟。

首先，如上所述，您使用`<search-include>`在`<general>`元素中將所需欄位包含在XML搜尋範本中。

然後，將每個`<search-include>`標籤包圍為`<general-field>`和`</general-field>`標籤，並提供`name`屬性中的欄位名稱，如下例所示：

```
<general> 
    <general-field name="seo_search_title"><search-include file="seo/seo_search_title.tpl" /></general-field> 
    <general-field name="seo_search_description"><search-include file="seo/seo_search_description.tpl" /></general-field> 
    <general-field name="seo_search_keywords"><search-include file="seo/seo_search_keywords.tpl" /></general-field> 
</general>
```

然後，在簡報範本中，您可以使用`<guided-general-field>`標籤，在您需要的任何地方插入命名欄位，如下列範例所示：

```
<title><guided-general-field gsname="default" field="seo_search_title"></title> 
<meta name="description" content="<guided-general-field gsname="default" field="seo_search_description">"/> 
<meta name="keywords" content="<guided-general-field gsname="default" field="seo_search_keywords">"/>
```

請注意，使用`gsname`屬性來指定「預設」搜尋。

總之，您可以定義可在網頁中使用的9個不同SEO欄位。 其中包括：

* 搜尋結果頁面——標題、說明和關鍵字
* 瀏覽頁——標題、說明和關鍵字
* 項目詳細資訊頁面——標題、說明和關鍵字

所有9個欄位皆以類似設定定義。 事實上，這9個欄位的名稱（例如「搜尋結果頁面」中的「標題」欄位）只是您使用這些欄位的建議。 您可以在簡報範本和搜尋範本中，在任何內容中使用任何欄位。

另請參閱[關於模板](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5)。

另請參閱[演示模板標籤](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)。

另請參閱[搜索模板標籤](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

另請參閱[設定搜尋結果字詞清單](../c-about-settings-menu/c-about-seo.md#task_A459A3734EC04042BA52C81184251DD4)。

## 配置搜索結果單詞清單{#task_A459A3734EC04042BA52C81184251DD4}

您可以設定搜尋結果字詞和片語的清單，這些字詞和片語包含在頁面標題、說明和關鍵字中。

**若要設定搜尋結果字詞清單**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Search Result Pages]**」。
1. 在[!DNL SEO Browse Pages Word List]頁面上，在各自的[!DNL Title]、[!DNL Description]和[!DNL Keywords]群組中，設定您想要的選項。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>選項 </p> </th> 
      <th colname="col2" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>標題 |說明 |關鍵字開頭為 </p> </td> 
      <td colname="col2"> <p>您要在字詞清單前面顯示的文字。 </p> <p>例如，您可能希望「關鍵字」清單以「品牌」開頭。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>在 </p> </td> 
      <td colname="col2"> <p>包含搜尋的時段。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最大搜索數 </p> </td> 
      <td colname="col2"> <p>包含的最大搜索數。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>包含欄位值 </p> </td> 
      <td colname="col2"> <p>結果單字清單中包含的欄位值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>新增這些字詞和片語 </p> </td> 
      <td colname="col2"> <p>列出您要新增至搜尋結果頁面標題、瀏覽頁標題或項目詳細資料頁面標題的字詞。 </p> <p>按一下<b>編輯</b>將單詞添加到清單中。 </p> <p>您可以每行新增一個字詞或片語。 完成後，按一下<b>保存更改</b>，然後關閉頁面以返回主SEO頁。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>移除這些字詞和片語（包含的欄位值除外） </p> </td> 
      <td colname="col2"> <p>列出要從搜尋結果頁面標題、瀏覽頁標題或項目詳細資訊頁面標題中移除的字詞。 </p> <p>按一下<b>編輯</b>將單詞添加到刪除清單中。 </p> <p>您可以每行新增一個字詞或片語。 完成後，按一下<b>保存更改</b>，然後關閉頁面以返回主SEO頁。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. （可選）按一下「預覽範例輸出」**，預覽您所設定之SEO欄位的產生值。**

   請參閱[預覽您設定的SEO中繼標籤](../c-about-settings-menu/c-about-seo.md#task_3F97949E193C4F92A104AD117FE49621)。
1. 按一下&#x200B;**「儲存變更」**。
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參閱[設定分段網站的遞增索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可選）在[!DNL SEO Search Results Word List]頁面上，執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 配置瀏覽頁單詞清單{#task_D7A1D765A92A4D6C94E672B3A86ECB5A}

您可以設定包含在頁面標題、說明和關鍵字中的瀏覽頁字詞和片語清單。

**若要設定瀏覽頁字詞清單**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Browse Pages]**」。
1. 在[!DNL SEO Browse Pages Word List]頁面上，在各自的[!DNL Title]、[!DNL Description]和[!DNL Keywords]群組中，設定您想要的選項。

   請參閱[設定搜尋結果字詞清單](../c-about-settings-menu/c-about-seo.md#task_A459A3734EC04042BA52C81184251DD4)下的選項表。
1. （可選）按一下「預覽範例輸出」**，預覽您所設定之SEO欄位的產生值。**

   請參閱[預覽您設定的SEO中繼標籤](../c-about-settings-menu/c-about-seo.md#task_3F97949E193C4F92A104AD117FE49621)。
1. 按一下&#x200B;**「儲存變更」**。
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參閱[設定分段網站的遞增索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可選）在[!DNL SEO Browse Pages Word List]頁面上，執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 配置項目詳細資訊字詞清單{#task_761538C519B34164BE189F13C39B2495}

您可以設定頁面標題、說明和關鍵字中包含的項目詳細資料字詞和片語清單。

**要配置項目詳細資訊單字清單**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Item Detail Pages]**」。
1. 在[!DNL SEO Item Detail Word List]頁面上，在各自的[!DNL Title]、[!DNL Description]和[!DNL Keywords]群組中，設定您想要的選項。

   請參閱[設定搜尋結果字詞清單](../c-about-settings-menu/c-about-seo.md#task_A459A3734EC04042BA52C81184251DD4)下的選項表。
1. （可選）按一下「預覽範例輸出」**，預覽您所設定之SEO欄位的產生值。**

   請參閱[預覽您設定的SEO中繼標籤](../c-about-settings-menu/c-about-seo.md#task_3F97949E193C4F92A104AD117FE49621)。
1. 按一下&#x200B;**「儲存變更」**。
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參閱[設定分段網站的遞增索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可選）在[!DNL SEO Item Detail Word List]頁面上，執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 預覽您設定的{#task_3F97949E193C4F92A104AD117FE49621} SEO中繼標籤

您可以預覽您設定的SEO欄位的產生值，以查看在何處插入的項目。

SEO欄位可包含欄位值，因此搜尋結果可能取決於您指定的搜尋查詢。

**若要預覽您設定的SEO中繼標籤**

1. 在產品功能表上，按一下「**[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Search Result Pages]**」。
1. 在SEO頁面上，按一下「預覽範例輸出」**。**
1. 在[!DNL SEO Preview]頁面的[!DNL Enter sample query]欄位中，輸入您要搜尋的查詢詞。
1. 按一下&#x200B;**搜尋**。

   產生的「標題」、「說明」和「關鍵字」欄位會根據您剛輸入的搜尋查詢，顯示插入頁面的內容。
1. 按一下&#x200B;**關閉**&#x200B;返回主SEO頁。
