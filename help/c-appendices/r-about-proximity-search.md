---
description: 「鄰近搜尋」可讓您將唯一位置與網站上的任何頁面建立關聯，然後依離指定位置的鄰近（距離）搜尋並排序結果。
solution: Target
title: 關於鄰近搜尋
topic: 附錄、網站搜尋與銷售
uuid: 24fc9265-3400-46a7-b6e0-4de5b049a39a
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 0%

---


# 關於近似搜索{#about-proximity-search}

「鄰近搜尋」可讓您將唯一位置與網站上的任何頁面建立關聯，然後依離指定位置的鄰近（距離）搜尋並排序結果。

例如，假設您已將美國郵遞區號中繼資料填入網站的頁面，例如：

```
<meta name="zipcode" content="84057">
```

然後，您可以設定帳戶，為郵遞區號中繼資料建立索引。 在&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]** > **[!UICONTROL Add New Field]**&#x200B;的[!DNL Add Field]頁面上，您設定了下列選項：

* 欄位名稱: `zip`
* 中繼標籤名稱：`zipcode`
* 資料類型: **[!UICONTROL Location]**
* 排序: **[!UICONTROL Ascending]**
* 預設單位：**[!UICONTROL Miles]**

在建立網站索引後，您會執行下列搜尋：

```
...&sp_q_location_1=84057&sp_x_1=zip&sp_q_max_1=100&sp_s=zip_proximity
```

結果集包含任何位於郵遞區號84057100英里內的檔案，依此郵遞區號的升序排序。

您也可以使用美國地區的電話區號。 或者，您可以使用經緯度對來指定網站中繼資料和搜尋准則中的位置。 根據所提供資料的形式自動確定位置類型。

三位數的位置值（「DDD」，其中每個「D」代表0-9的小數位）被視為美國電話區號。

五或五破四位數位置值（「DDDD」或「DDDD-DDD」）視為美國郵遞區號。

將&quot;±DDD.DDDD.DDDD&quot;精確形式的位置值視為經緯度對。 第一個簽名數值指定緯度，而第二個簽名數值代表經度。

**重要**:如果您指定正緯度值或正經度值，或兩者皆是，URL中的「+」字元必須編碼為 `%2b`。否則，&quot;+&quot;會解釋為空格，且值不會識別為有效位置。 例如，假設您的緯度值為+49.2394，經度值為-123.1892。URL的位置部分（編碼為&quot;+&quot;）如下所示：

```
...&sp_q_location_1=%2b49.2394-123.1892...
```

* 正緯度值代表赤道以北的度數。
* 負緯度值代表赤道以南的度數。
* 正經度值代表「主子午線」的「東部」度數。
* 負經度值代表「Prime Meridian」（主經度）的西側度。

例如，值&quot;+48.8577+002.2950&quot;代表赤道以北48.8577度，黃金經域以東2.295度，即埃菲爾鐵塔在法國巴黎的確切位置。 數字元號和每個數字是必需的，即使前導零和尾隨零也是如此。 例如，三個值&quot;48.8577+2.2950&quot;、&quot;+48.8577+2.2950&quot;和&quot;+48.8577+02.295&quot;不是位置。 第一個值缺少緯度上的前導符號。 第二個值遺失經度上的兩個前導零。 第三個值遺失經度上的尾隨零。 請務必仔細檢查索引日誌中是否存在與位置相關的問題。

當您依鄰近度搜尋時，會針對該搜尋建立特殊的「鄰近輸出欄位」。 該欄位將填入在搜索標準中指定的位置和與每個搜索結果相關聯的位置之間的相對距離。 此特殊欄位會針對在搜尋准則中使用的位置類型欄位命名，並在結尾加上&quot;_proximity&quot;。

在上述範例搜尋中，結果會依「zip_proximity」的遞增順序排序。 即，指定郵遞區號(84057)與每個結果的「郵遞區號」欄位位置之間的距離。 您也可以使用此特殊的「相近度輸出欄位」，使用`<Search-Display-Field>`搜尋範本標籤，以公里或公里顯示每個搜尋結果的相對距離。

請參閱[搜尋範本標籤](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4)。

您也可以不使用sp_s選項進行搜尋。 在這種情況下，結果按分數排序（sp_s=0，這是預設值）。分數受每個結果相對於鄰近搜索位置的相對距離的影響，該距離由sp_q_location[_#]參數指定。 添加新的cgi參數sp_q_max_releated_distance[#]，以選擇性地控制應用於鄰近搜索的相關性計算。

以下是鄰近相關性搜尋範例：

```
...&sp_q_location_1=84057&sp_x_1=zip&sp_q_max_1=100&sp_q_2=shirt&sp_x_2=title&sp_q_max_relevant_distance_2=50
```

結果集包含任何位於郵遞區號84057100英里內的檔案，並在標題欄位中包含&quot;shirt&quot;一詞，依受鄰近相關性分數影響的分數排序。 鄰近元件的完美關聯分數代表距離0。 鄰近度元件的最小相關性分數代表距離超過50英里。

您可以在「搜索CGI參數」參考主題中查看`sp_location`、`sp_location_#`、`sp_q_min`、`sp_q_min_#`、`sp_q_max`、`sp_q_max_#`和`sp_s`，以瞭解有關鄰近搜索的更多資訊。

請參閱[搜索CGI參數](../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890)。

請參閱[新增中繼標籤欄位](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)。
