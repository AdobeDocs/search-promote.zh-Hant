---
description: 您可以使用「完整索引」為分段或即時網站的所有頁面建立索引。 索引功能可協助您的客戶在執行搜尋時，更輕鬆地找到他們所尋找的項目或所需項目。
seo-description: 您可以使用「完整索引」為分段或即時網站的所有頁面建立索引。 索引功能可協助您的客戶在執行搜尋時，更輕鬆地找到他們所尋找的項目或所需項目。
seo-title: 關於完整索引
solution: Target
subtopic: Full Index
title: 關於完整索引
topic: Index,Site search and merchandising
uuid: dce1eafd-5aea-4945-8305-8f9e7dc392df
translation-type: tm+mt
source-git-commit: 7af85dd37f06fe506e5f57e28a25385ca7ab3db5
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 0%

---


# 關於完整索引{#about-full-index}

您可以使用「完整索引」為分段或即時網站的所有頁面建立索引。 索引功能可協助您的客戶在執行搜尋時，更輕鬆地找到他們所尋找的項目或所需項目。

## 使用完整索引{#concept_C69BD21863FD4856B49326F35DB570D3}

當生成完整索引時，會顯示狀態資訊，如索引過程中的開始時間、用時和錯誤。 此外，還會顯示有關上一個索引狀態的資訊。

如果您變更了需要重新產生索引的帳戶設定，狀態可能會讀取「重新產生」。 在重新產生期間，會套用帳戶設定以建立更新的網站索引。

您可以隨時停止或重新啟動索引建立程式。

雖然新的索引是針對即時網站建立，但客戶仍可使用您的最後一個索引繼續搜尋您的網站。 此外，還會顯示有關上一個索引狀態的資訊。

## 設定即時網站{#task_6760F3256D004A228B38968DF15421F0}的完整索引排程

您可以指定要搜尋網站並更新索引的時間和日期。

您選取的時間會根據「帳戶設定」中設定的時區為本機時間。

請參閱[設定您的帳戶設定](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

Web伺服器通常會安排在半夜停工進行維護。 如果伺服器在計畫的索引時間內關閉，則索引過程將失敗。 請確定您選取了一天中的某個時間，您的Web伺服器才可用。

索引排程僅適用於您的即時索引；您無法計劃分段索引。

**若要設定即時網站的完整索引排程**

1. 在產品功能表上，按一下「**[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Schedule]**」。
1. 在&#x200B;**[!UICONTROL Time]**&#x200B;下拉式清單中，選取您要開始建立完整索引的小時數。
1. 選擇要運行完整索引的一天或多天。
1. 按一下 **[!UICONTROL Save Changes]**.

## 執行即時或分段網站的完整索引{#task_F7FE04D8A1654A7787FCCA31B45EB42D}

您可以使用「完整索引」為分段或即時網站的所有頁面建立索引。 索引功能可協助您的客戶在執行搜尋時，更輕鬆地找到他們所尋找的項目或所需項目。

**若要執行即時或分段網站的完整索引**

1. 在產品功能表上，執行下列其中一項作業：

   * 按一下&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Index]**。

   * 按一下&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Staged Index]**。

1. 設定所需的索引選項。

   <table> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> <p>選項 </p> </th> 
    <th colname="col2" class="entry"> <p>說明 </p> </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>清除索引快取 </p> </td> 
    <td colname="col2"> <p>從索引快取中刪除所有文檔。 </p> <p>選取後，每個網站頁面都會從您的伺服器下載。 如果選中並禁用此設定，則您的帳戶將設定為每次執行完整索引時清除快取。 或者，有些先前變更的帳戶設定現在需要完整索引。 </p> <p>取消選取時，所有已建立索引的頁面都會保留在索引中，直到Web伺服器指出該頁面已不存在為止。 即使該頁面的連結已移除，此情況仍然正確。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>重新產生待定 </p> </td> 
    <td colname="col2"> <p>如果您對已大幅變更索引內容的帳戶設定進行了變更，請選取「If you have changes your account settings that have argially changed your index contents」（如果您已變更了索引的內容）。 重大變動包括對下列任一項目作出變更： 
    <ul id="ul_4EB8FF692FEB47BBB9A64D61299380D1"> 
    <li id="li_7CF8D286512F4210BEA3DB9F0EFA097A">同義字 </li> 
    <li id="li_8178ABC342BB4365B3927E20433756E3">集合 </li> 
    <li id="li_57C8BD06BFA64AFAA2C9EF2CC59520EF">中繼資料 </li> 
    <li id="li_C4B6A7DA023B4A43991D03EC592170C9">排除的字詞 </li> 
    <li id="li_9E0AD4B6DDC24A5A8FB5C2C1CCD5348A">帳戶語言 </li> 
    <li id="li_338F107547DF48AAA0EF90F4AD8664A5">排名 </li> 
    <li id="li_7F49B86D94974E79AAD381A64A1400F2">切換區分大小寫的搜尋 </li> 
    <li id="li_E8FE6EE240A840AC826ADF4294AAC6F6">切換變音支援 </li> 
    <li id="li_51763D482DCB4ED0972966F492B8C0F2">切換數字索引 </li> 
    </ul> </p> <p>在進行其他編目之前，會先透過所有索引資料進行快速傳遞，以符合新帳戶設定。 </p> <p>只有當您對分段網站執行完整索引時，才可使用此選項。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>計算所有頁面 </p> </td> 
    <td colname="col2"> <p>即使在您達到帳戶頁面限制後，仍可繼續搜尋網站頁面。 </p> <p>您的索引中不會新增其他頁面，但您可以確定網站上的檔案總數。 </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. 按一下 **[!UICONTROL Full Index Now]**.
1. （可選）如果發生索引錯誤，請按一下&#x200B;**[!UICONTROL View Errors]**&#x200B;以查看相關日誌。

## 檢視即時或分段網站{#task_02E5E944C56B4EB19CC1FF321F3221B8}的完整索引記錄

當即時完整索引或分段完整索引完成時，您可以檢視其相關記錄檔，以疑難排解發生的任何錯誤。

您無法匯出記錄檔，也無法儲存記錄檔。 日誌仍可供查看，直到新索引出現。

**若要檢視即時或分段網站的完整索引記錄**

1. 在產品功能表上，執行下列其中一項作業：

   * 按一下&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Log]**。

   * 按一下&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Staged Log]**。

1. 在記錄頁的上方或下方，執行下列任一作業：

   * 使用導覽選項&#x200B;**[!UICONTROL First]**、**[!UICONTROL Prev]**、**[!UICONTROL Next]**、**[!UICONTROL Last]**&#x200B;或&#x200B;**[!UICONTROL Go to line]**&#x200B;在日誌中移動。

   * 使用顯示選項&#x200B;**[!UICONTROL Errors only]**、**[!UICONTROL Wrap line]**&#x200B;或&#x200B;**[!UICONTROL Show]**&#x200B;來調整您所看到的內容。

