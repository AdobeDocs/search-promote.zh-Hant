---
description: 您可以使用回滾來備份和歸檔已生成的網站索引。 您也可以隨時恢復索引的備份。
seo-description: 您可以使用回滾來備份和歸檔已生成的網站索引。 您也可以隨時恢復索引的備份。
seo-title: 關於索引的回滾
solution: Target
subtopic: Rollback
title: 關於索引的回滾
topic: Index,Site search and merchandising
uuid: abed878a-71b3-4122-9822-7410f4427a9a
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a

---


# 關於索引的回滾{#about-rollback-for-indexes}

您可以使 [!DNL Rollback] 用來備份和存檔已生成的網站索引。 您也可以隨時恢復索引的備份。

## 對索引使用回滾 {#concept_0BC4BC975DB045A986C3607CF32705D8}

存檔包含四個索引：當前站點索引和三個先前的站點索引，搜索自動機會根據回滾配置設定自動歸檔這些索引。 每次為您的網站建立索引時，就會更新封存。 較新的索引會取代現有的已封存索引，讓封存檔永遠保持最新狀態。

每個已存檔的索引都列在存檔中，並包含以下資訊：

* 索引最終化的日期和時間。
* 索引年齡。
* 已編製索引的文檔數。
* 索引操作類型（完整、增量等）。
* 索引狀態，例如索引當前是否處於活動狀態，以及在下一個索引之後是否將保留或刪除。

每次為網站建立索引時，新索引就會新增至封存，並移除現有的封存索引。 但請注意，最舊的索引不一定是移除的索引。 將新索引添加到歸檔檔案時，會對每個歸檔索引與回滾配置設定中指定的年齡進行比較。 刪除與所需計畫最遠的索引。 例如，假設配置設定為24,48,72，且保存的索引的年齡為5、23、47和71。 將新索引添加到歸檔檔案時，最近的索引（過時5小時）將被刪除，因為其年齡與設定最遠。 為方便起見，當再次為站點編製索引時，將刪除哪個索引的存檔注釋。

在激活索引時，可以導航到用戶介面中的其他區域。 狀態指標會追蹤啟動進度，當您檢視頁面時即可使 [!DNL Rollback] 用。 如果已存檔的索引恢復，則會在「完整索引」、「增量索引」、「指令碼索引」和「重新生成」頁面的頂部通知用戶。 恢復索引時，不能執行索引操作。 如果回滾操作與已調度站點索引衝突，則將延遲已調度索引，直到回滾完成。 如果索引已在進行中，則取消該索引，前提是用戶確認回滾接收優先順序。

如果在搜索過程中發現錯誤，則搜索自動機不會更新回滾歸檔檔案，以保持歸檔檔案的完整性。 如果用戶取消索引操作，也不會進行更新。 如果索引操作超過最大時間、位元組、頁或文檔，Crawler會最終化索引並將其添加到歸檔檔案。 此外，如果索引操作期間未滿足最小頁數，Crawler將取消索引，而上一個索引仍處於活動狀態。

## 配置索引的回滾歸檔計畫 {#task_CD403B9AE2244B13A6B3861B5F9B055C}

您可以使 [!DNL Configure] 用來確定要儲存在回滾歸檔檔案中的索引檔案。 歸檔檔案可以儲存當前索引和三個備份索引。

欄位 **[!UICONTROL Schedule]** 包含三個以逗號分隔的值，代表目前的小時數。 例如，排程值24,48,72會指定24小時（目前或昨天）、48小時（目前或兩天前）和72小時（目前或三天前）。

搜尋會持續封存距離一天、兩天和三天前最近的網站索引。 已封存索引的實際時間和日期可能會因您網站的索引排程而異。

**要配置索引的回滾歸檔計畫，請執行以下操作：**

1. 在產品功能表上，按一下 **[!UICONTROL Index]** > **[!UICONTROL Rollback]** > **[!UICONTROL Configure]**。
1. 在頁面 [!DNL Rollback Configuration] 的欄位中，輸 **[!UICONTROL Schedule]** 入一個以小時為單位的命令分隔的三個索引頁清單。 將保存最接近這些年齡的索引。
1. 按一下 **[!UICONTROL Save Changes]**.

## 激活歸檔索引 {#task_5DCE3D660F6F4197993E92AA59227332}

您可以使用回滾來激活歸檔索引。

按一下回滾 **[!UICONTROL Activate]** 索引時，當前活動的索引將移到歸檔檔案中。

啟用已封存的索引後，您會返回頁 [!DNL Activate Index] 面。 將顯示有關索引回滾的資訊。 此外，表 [!DNL Activate] 中的列標 [!DNL Available Indexes] 識狀態為「活動索引」的回退索引。

1. 在產品功能表上，按一下 **[!UICONTROL Index]** > **[!UICONTROL Rollback]** > **[!UICONTROL Rollback]**。
1. 在頁 [!DNL Activate Index] 面上，在表格 [!DNL Available Indexes] 中，單 **[!UICONTROL Activate]** 擊要激活的關聯歸檔索引類型。

   使用「日期」、「年齡」、「頁面」和「操作」欄，幫助您確定要激活的索引。
1. 在頁面 [!DNL Verify Rollback] 上，查看索引資訊以驗證您選擇了正確的索引，然後按一下 **[!UICONTROL Activate Now]**。

## 查看所有索引回退的日誌 {#task_D2D9AA7203F0465FB5AE0D49212AC41C}

查看所有與回滾相關的操作的日期和時間。

**查看所有索引回退的日誌**

1. 在產品功能表上，執行下列其中一項作業：

   * Click **[!UICONTROL Index]** > **[!UICONTROL Re-Rank Index]** > **[!UICONTROL Live Log]**.

   * Click **[!UICONTROL Index]** > **[!UICONTROL Re-Rank Index]** > **[!UICONTROL Staged Log]**.

1. 在記錄頁的上方或下方，執行下列任一作業：

   * 使用導覽選 **[!UICONTROL First]**&#x200B;項、 **[!UICONTROL Prev]**、 **[!UICONTROL Next]**&#x200B;或 **[!UICONTROL Last]**&#x200B;在日誌 **[!UICONTROL Go to line]** 中移動。

   * 使用顯示選 **[!UICONTROL Errors only]**&#x200B;項 **[!UICONTROL Wrap line]**&#x200B;或 **[!UICONTROL Show]** 調整您所看到的內容。

