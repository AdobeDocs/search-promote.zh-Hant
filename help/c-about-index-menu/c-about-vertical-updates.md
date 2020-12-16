---
description: 您可以使用「垂直更新」快速更新索引的部分，而不需要處理大量資料。
seo-description: 您可以使用「垂直更新」快速更新索引的部分，而不需要處理大量資料。
seo-title: 關於垂直更新
solution: Target
subtopic: Vertical Update
title: 關於垂直更新
topic: Index,Site search and merchandising
uuid: ded09e89-5a52-4e8c-a6f7-3e25b4191183
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 0%

---


# 關於垂直更新{#about-vertical-update}

您可以使用「垂直更新」快速更新索引的部分，而不需要處理大量資料。

## 使用垂直更新{#concept_E65A70C9C2E04804BF24FBE1B3CAD899}

垂直索引只需數秒即可執行，對於大容量電子商務網站非常有用，因為這些網站需要數小時才能完整或逐步建立索引。

當生成垂直索引時，會顯示狀態資訊，如索引過程中的開始時間、用時和錯誤。

您可以隨時停止或重新啟動垂直索引程式。

當新的垂直索引更新您的即時網站時，客戶仍可使用您目前的索引繼續搜尋您的網站。

>[!NOTE]
>
>預設情況下，[!DNL Adobe Search&Promote]中未啟用此功能。 請聯絡技術支援以啟用您使用的功能。

「垂直更新」特別意在用於使用IndexConnector來提供搜尋索引內容的eCommerce-style [!DNL Adobe Search&Promote]帳戶。 典型的使用案例是[!DNL Adobe Search&Promote]索引代表可搜尋的產品目錄，而且需要能夠快速更新經常變更的值，例如現有庫存、可用性和／或價格。 「垂直更新」與「增量索引」有些類似，只不過它只更新了每個文檔的部分，而「增量索引」則用新版本替換整個文檔。

術語「垂直更新」是指[!DNL Adobe Search&Promote]索引可以影像化為柱狀表的概念，每列對應於[!DNL Adobe Search&Promote]元資料欄位定義，每行對應於文檔。 「垂直更新」程式會取代一或多欄，而不需要變更其他欄的內容。

當內容的主要來源IndexConnector饋送包含建立索引所需的所有必要資料元素時，「垂直更新」饋送是主饋送的子集，它使用相同的IndexConnector &quot;schema&quot;來定義資料元素，但僅包含&#x200B;*需要更新的資料項目。*

至少，「垂直更新」饋送必須包含「主鍵」元素（如IndexConnector配置中的&#x200B;**主鍵**&#x200B;核取方塊所識別）和至少一個要更新的資料元素。

例如，主IndexConnector饋送看起來可能類似下列（但通常包含更多資料項目）:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<products>
<product>
  <id><![CDATA[123]]></id>
  <title><![CDATA[Title for product 123]]></title>
  <description><![CDATA[Description for product 123.]]></description>
  <price>3.99</price>
  <link><![CDATA[https://www.somewhere.com/products/123]]></link>
  <image><![CDATA[https://www.somewher.com/images/products/123.jpg]]></image>
  <label><![CDATA[PROD123]]></label>
  <inventory>100</inventory>
  <brand><![CDATA[brand123]]></brand>
  ...
</product>
<product>
...
</product>
</products>
```

需要的是只能快速更新`<price>`和`<inventory>`值，因為這些值在客戶的網站上會快速變更。 垂直更新動態消息可能如下所示：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<products>
<product>
  <id><![CDATA[123]]></id>
  <price>3.50</price>
  <inventory>90</inventory>
</product>
<product>
...
</product>
</products>
```

這些資訊通常儲存在客戶伺服器上的單獨檔案中，而IndexConnector的「垂直檔案路徑」配置設定指向此檔案。 「垂直更新」程式讀取此新內容並更新現有的[!DNL Adobe Search&Promote]索引，此時僅更新`<price>`和`<inventory>`的值。 後續搜尋會傳回新更新的內容。

>[!NOTE]
在此範例中，`<price>`和`<inventory>`中繼資料欄位必須已定義，並勾選「垂直更新欄位」選項。****

另請參閱[關於索引的遠程控制](../c-about-index-menu/c-about-remote-control-for-indexing.md#concept_C79B322190E84106A434E5C6D4A4118F)和[添加新的meta標籤欄位](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。

## 設定分段網站的垂直更新{#task_46A367B0786C4C90BFFA5D3F95FD86C0}

您可以指定URL，以設定您要納入垂直更新的索引連接器來源。

**若要設定分段網站的垂直更新**

1. 在產品功能表上，按一下「**[!UICONTROL Index]** > **[!UICONTROL Vertical Update]** > **[!UICONTROL Configuration]**」。
1. 在&#x200B;**[!UICONTROL Vertical Update Configuration]**&#x200B;頁面的「更新URL」欄位中，指定您要建立索引之頁面的URL。

   搜索自動機僅更新在指定的「索引連接器」源中標識的文檔。

   此欄位只能包含「索引連接器URL」，如下列範例所示：

   `index:product_catalog`。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 檢視即時或分段網站的垂直更新記錄{#task_E668E1F1240C476DAA1CA783DC728232}

當即時垂直更新或分段垂直更新完成時，您可以檢視其相關記錄檔，以疑難排解可能發生的任何錯誤。

您無法匯出「垂直更新」記錄檔，也無法儲存。 日誌檔案在下一個索引出現之前仍然可供查看。

**若要檢視即時或分段網站的垂直更新記錄檔**

1. 在產品功能表上，執行下列其中一項作業：

   * 按一下&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Vertical Update]** > **[!UICONTROL Live Log]**。

   * 按一下&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Vertical Update]** > **[!UICONTROL Staged Log]**。

1. 在記錄頁的上方或下方，執行下列任一作業：

   * 使用導覽選項&#x200B;**[!UICONTROL First]**、**[!UICONTROL Prev]**、**[!UICONTROL Next]**、**[!UICONTROL Last]**&#x200B;或&#x200B;**[!UICONTROL Go to line]**&#x200B;在日誌中移動。

   * 使用顯示選項&#x200B;**[!UICONTROL Errors only]**、**[!UICONTROL Wrap line]**&#x200B;或&#x200B;**[!UICONTROL Show]**&#x200B;來調整您所看到的內容。

