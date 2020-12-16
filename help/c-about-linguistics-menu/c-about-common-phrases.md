---
description: 您可以定義您網站上使用的常見片語，如此當客戶輸入搜尋查詢時，就不需要在您定義的片語周圍輸入引號。
seo-description: 您可以定義您網站上使用的常見片語，如此當客戶輸入搜尋查詢時，就不需要在您定義的片語周圍輸入引號。
seo-title: 關於常見片語
solution: Target
title: 關於常見片語
topic: Linguistics,Site search and merchandising
uuid: 0f980a22-d826-4476-97de-0e9c14549bc8
translation-type: tm+mt
source-git-commit: 8efa90ac2927b263b7d48ccbf25d4b0e917dac79
workflow-type: tm+mt
source-wordcount: '1216'
ht-degree: 1%

---


# 關於常見片語{#about-common-phrases}

您可以定義您網站上使用的常見片語，如此當客戶輸入搜尋查詢時，就不需要在您定義的片語周圍輸入引號。

## 使用常見片語{#concept_4946E53586DF492EAEB1B7F757FD440F}

>[!NOTE]
>
>「常用片語」功能不會出現在使用者介面中，因為預設未啟用。 請聯絡技術支援以啟用此功能供您使用。

「常用片語」是多字詞片語的集合，在客戶搜尋時可加以辨識。 它會將片語視為單字的組合群組，而非個別單字。 當客戶在您的網站上輸入搜尋查詢時，他們可以使用雙引號將詞語周圍識別片語，例如「太平洋」。 不過，當您新增常見片語群組時，當客戶在搜尋查詢中找到相符的片語時，會自動為其執行報價步驟。

例如，假設客戶進入您的網站時輸入下列搜尋查詢：

`hotels near the pacific ocean`

若不加上`pacific ocean`周圍的引號，客戶的搜尋會傳回世界各地任何海洋附近的酒店，但並非客戶想要的結果。

不過，當您新增常見片語&quot;Pacific Ocean&quot;時，其搜尋查詢會自動轉換為下列：

`hotels near the "pacific ocean"`

使用「常見片語」並不妨礙客戶在片語的片語周圍明確使用引號。相反地，當在其搜尋查詢中找到已定義的片語時，它只會加引號。

此搜索查詢擴展適用於後端搜索CGI參數`sp_q`和`sp_q_#`,

請參閱[後端搜尋CGI參數](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)中的表行25、26和32。

## 添加常見片語{#task_35C84FABCD9042C5B48C5C788B752871}

您可以新增「常用片語」，以確保搜尋查詢能準確傳回具有客戶輸入之所有字詞的網頁，其順序和鄰近度完全相同。

在新增「常用片語」時，您可以使用「常用片語」首頁面上的「尋找」功能。 「尋找」功能可讓您搜尋現有片語，並找出其所在的群組。

請參閱[尋找包含片語](../c-about-linguistics-menu/c-about-common-phrases.md#task_20714969274740A7BB4DC71E705EA15E)中特定字詞的群組。

**若要新增常用片語群組**

1. 在產品功能表上，按一下「**[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**」。
1. 在[!DNL Common Phrases Groups]頁面上，按一下「新增片語群組」。****
1. 在[!DNL Add Common Phrase Group]頁面上，設定您想要的選項，並新增組成群組的所有片語。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>選項 </p> </th> 
      <th colname="col2" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>群組名稱 </p> </td> 
      <td colname="col2"> <p>必要。 </p> <p>通用片語的唯一名稱。 </p> <p>如果您稍後編輯「常用片語群組」，請注意，您無法變更「群組名稱」。 若要變更群組名稱，請使用<span class="uicontrol"> Rename</span>功能。 </p> <p>請參閱<a href="../c-about-linguistics-menu/c-about-common-phrases.md#task_168E07C59C0F40989D43E7010EFF22EB" format="dita" scope="local">更名常見片語</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>附註 </p> </td> 
      <td colname="col2"> <p>可選. </p> <p>新增與「常用片語」相關的資訊。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>片語 </p> </td> 
      <td colname="col2"> <p>必要。 </p> <p>可讓您指定最多5個字詞的片語。 若要調整最大字詞設定，請聯絡技術支援。 </p> <p>您輸入的每個片語在任何「常用片語群組」中都必須是唯一的。 </p> <p>使用「動作」欄中的加號(+)和減號(-)圖示來新增輸入的片語或刪除片語。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 按一下&#x200B;**「新增」**。
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 測試常見片語{#task_A0C344E051CA45A9A0588242F9DA675D}

如果您選取要與片語群組關聯的中繼資料欄位，則可測試特定片語的擴增。

當您測試片語的擴增時，會針對您與片語群組相關聯的中繼資料欄位，搜尋精確的片語。 片語會被搜尋，彷彿其周圍有引號。 所有其他中繼資料欄位只會搜尋片語中的字詞，而不會加上引號。 例如，假設您測試了片語`audi TT`。 傳回的結果可能如下：

`title|body|field3:"Audi TT" url|desc|keys|target|alt:Audi TT`

**若要測試常用片語**

1. 在產品功能表上，按一下「**[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**」。
1. 在[!DNL Common Phrases Groups]頁面的&#x200B;**包含**&#x200B;文字欄位的「測試片語」中，輸入您要測試其中繼資料擴增的片語。
1. 按一下 **[!UICONTROL Test]**.

   展開結果顯示在文本框中。
1. （可選）拖曳文字方塊的右下角以展開顯示區域。

## 尋找包含片語{#task_20714969274740A7BB4DC71E705EA15E}中特定字詞的群組

您可以使用[!DNL Find]在您新增的所有現有群組中搜尋片語中的特定字詞。

當您使用「尋找」時，它會找到下列項目：

* 其中，所有群組中都有完全相同的片語。
* 在所有群組中，片語中的任何字詞，不論片語中的字詞順序和鄰近度。

另請參閱[編輯常見片語](../c-about-linguistics-menu/c-about-common-phrases.md#task_5CAC3A133C5342EEAFE55A7EABCBCD61)。

**若要尋找包含片語中特定字詞的群組**

1. 在產品功能表上，按一下「**[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**」。
1. 在[!DNL Common Phrases Groups]頁面的&#x200B;**[!UICONTROL Find groups with phrases that contain]**&#x200B;文字欄位中，輸入片語。
1. 按一下 **[!UICONTROL Find]**.

   結果將顯示在文本框中。
1. （可選）執行下列一或多個作業：

   * 拖曳文字方塊的右下角，以展開顯示區域。
   * 在結果窗口中，按一下超連結的片語以開啟關聯組的編輯公用片語頁。

## 編輯常用片語{#task_5CAC3A133C5342EEAFE55A7EABCBCD61}

您可以編輯已新增之常用片語群組的現有欄位、附註和片語。 但是，要編輯組名，必須使用[!DNL Rename]功能。

另請參閱[更名公用片語組](../c-about-linguistics-menu/c-about-common-phrases.md#task_168E07C59C0F40989D43E7010EFF22EB)。

**若要編輯常用片語群組**

1. 在產品功能表上，按一下「**[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**」。
1. 在[!DNL Common Phrases Groups]頁面上，按一下群組名稱最右側的&#x200B;**[!UICONTROL Edit]**。
1. 在[!DNL Edit Common Phrase Group]頁面上，設定您想要的選項。

   請參閱[添加公用片語](../c-about-linguistics-menu/c-about-common-phrases.md#task_35C84FABCD9042C5B48C5C788B752871)下的選項表。
1. 按一下&#x200B;**「儲存變更」**。
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 更名公用片語{#task_168E07C59C0F40989D43E7010EFF22EB}

您可以變更現有「常用片語」群組的名稱。 但是，如果要更改公用片語的現有欄位、注釋和短語，則必須使用[!DNL Edit]功能。

請參閱[編輯常見片語](../c-about-linguistics-menu/c-about-common-phrases.md#task_5CAC3A133C5342EEAFE55A7EABCBCD61)。

**若要重新命名常見片語群組**

1. 在產品功能表上，按一下「**[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**」。
1. 在[!DNL Common Phrases Groups]頁面上，按一下群組名稱最右側的&#x200B;**[!UICONTROL Rename]**。
1. 在[!DNL Rename Common Phrase Group]頁面的&#x200B;**[!UICONTROL Group Name]**&#x200B;文字欄位中，輸入群組的新名稱。
1. 按一下&#x200B;**更名**。
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 刪除公用片語{#task_4106D282A2ED4A27B09EE5A8CAAEDA36}

您可以刪除已新增的任何常見片語群組。 如果您誤刪了組，可以使用[!DNL History]恢復組。

請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

**刪除常用片語組**

1. 在產品功能表上，按一下「**[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]**」。
1. 在[!DNL Common Phrases Groups]頁面上，按一下群組名稱最右側的&#x200B;**[!UICONTROL Delete]**。
1. 在[!DNL Delete Common Phrase Group]頁面上，按一下&#x200B;**[!UICONTROL Delete]**。
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

