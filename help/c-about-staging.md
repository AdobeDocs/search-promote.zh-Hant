---
description: 測試功能可讓您測試和預覽對設定和設定所做的變更，而不會影響即時索引。
seo-description: 測試功能可讓您測試和預覽對設定和設定所做的變更，而不會影響即時索引。
seo-title: 關於測試
solution: Target
title: 關於測試
topic: Staging,Site search and merchandising
uuid: 2e5889a6-2e9c-4ac7-9d6e-d35e7cafda5b
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# 關於測試{#about-staging}

測試功能可讓您測試和預覽對設定和設定所做的變更，而不會影響即時索引。

## 關於測試 {#concept_08B8F3CA1F4241108F14BA7FC7806CA7}

測試功能可讓您測試和預覽對設定和設定所做的變更，而不會影響即時索引。

另請 [參閱元素ID:context_A5783D07C72042EC8886F300FFF62C50](c-about-simulator.md#context_A5783D07C72042EC8886F300FFF62C50)。

任何具有測試選項的頁 **[!UICONTROL Push All Live]** 面， **[!UICONTROL View Live Settings]** 或表示該頁面上的所有設定都可進行測試。 「索引」中的網頁除外。 此區域中的頁面會明確地用於分段索引或活動索引，以便您直接獨立控制兩個索引。

您幾乎可以放置任何項目，包括索引。 有些例外包括帳戶特定設定，這些設定同時影響分段和即時環境以及索引操作的計畫。 在預設下，當您儲存對可暫存之設定的任何變更時，系統會自動暫存。

當未啟 **[!UICONTROL Push All Live]** 用或 **[!UICONTROL View Lives Settings]** 選項時（暗顯），表示該頁面上的分段設定與即時設定相同。

對於已存放的項目，請注意，即時版本的設定是唯讀的；它只能透過即時推送階段設定來操控。

## 關於分段頁面上的歷史記錄 {#section_5BE780AFF26A450A9EFF4000DE53531B}

大部分的分段設 [!DNL History] 定在頁面的右上方區域有一個選項。 按一下 **[!UICONTROL History]**&#x200B;後，它可讓您回復您最近對已開啟之特定分段頁面所做的任何變更。

您也可以檢視變更記錄檔，以檢視其他歷史記錄檢視。 每次應用更改時，都會建立基礎資料檔案的備份版本。 「更改日誌」顯示每個此類修訂，顯示版本號、執行更改的用戶的電子郵件地址以及備份的日期。 帶有粗體版本值的條目表示當前版本。

See [Viewing the Change Log](c-about-reports-menu/c-about-reports-menu.md#task_166F1156719F4B3D834BEA8E249C8057).

## 「管理舞台——即時設定」頁面 {#section_E72B8CAF516345A5B6B6783CF6E512EE}

除了直接在 **[!UICONTROL Push All Live]** 指定頁 **[!UICONTROL View Live Settings]** 面內提供和選項外，您也可以使用 **[!UICONTROL Manage Stage-Live Settings]** 頁面執行相同的動作。 主 **[!UICONTROL Manage Stage-Live Settings]** 要產品選單中提供的頁面是集中位置，可顯示您帳戶中目前存放的所有設定。 您可以即時推送所有設定、僅即時推送選取的設定，或刪除設定。 不過，最佳實務是，請一律將所有分段項目推送至現場，以避免任何相依性問題。

頁面上的設定會分組為類別。 您可以展開每個類別，以顯示要存放的頁面設定。 目前，不會在舞台管理員中追蹤相依性。 因此，建議您一次推送除索引以外的所有內容。

您可以即時推送分段索引。 請務必先檢查分段索引是否過時或已損壞。 如果您犯了錯誤，並將分段索引推送至即時，您可以回滾舊的即時索引。 推送分段索引至現時通常需要不到30秒。

## 測試分段設定或索引 {#section_6800E52D20854A779946EAB600801F12}

在支援測試控制的頁面上，您可以針對分段或即時設定進行測試。 當您檢視分段設定時，分段設定會用於測試。 同樣地，當您檢視即時設定時，測試會使用即時設定。 在範本區段中，所有測試都是針對索引的分段版本進行。 要搜索分段索引，請將 `sp_staged` CGI參數設定為1。 這反過來表示您想使用分段索引。 如果分段索引不存在，則會搜尋您的即時索引，並視需要套用任何分段搜尋時間設定。

另請參閱 [後端搜索CGI參數](c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8)。

## 檢視即時設定 {#task_401A0EBDB5DB4D4CA933CBA7BECDC10F}

您可以從任何分段頁面檢視設定的即時版本。

<!-- 

t_viewing_live_settings.xml

 -->

如果 **[!UICONTROL View Live Settings]** 未啟用（暗灰色），表示該頁面的舞台設定和即時設定已同步。

**若要檢視即時設定**

1. 在任何具有分段設定的頁面上，按一 **[!UICONTROL View Live Settings]** 下以檢視即時版本的設定。
1. （可選）執行下列任一操作：

   * 按一 **[!UICONTROL View]** 下可查看為分段設定選取的目前選項。
   * 按一 **[!UICONTROL View Stage Settings]** 下可返回階段設定，您可在其中編輯或刪除設定。

## 即時推送舞台設定 {#task_44306783B4C0408AAA58B471DAF2D9A4}

您可以從任何分段頁面檢視或從中央頁面即時推播 **[!UICONTROL Manage Stage-Live Settings]** 設定。

<!-- 

t_pushing_live_settings_live.xml

 -->

當頁 **[!UICONTROL Push Live]** 面上的選項啟用（非暗灰色）時，表示有已分段的設定。 或者，這表示設定有編輯，當您儲存時，設定會變成階段。 當您按一下此選項時，任何未儲存的編輯都會儲存至暫存區。 如果沒有待審編輯，頁面的設定會立即即時推送。

**若要即時推播階段設定**

1. 進行以下一項操作: 

   * 在任何已選取「已轉移」為「檢視」的頁面上，按一下 **[!UICONTROL Push Live]**。
   * 在產品選單上，按一下 **[!UICONTROL Staging]**。 在頁面 **[!UICONTROL Manage Stage-Live Settings]** 上，執行下列其中一項作業：

   * 使用設定樹狀結構只檢查您要即時推送的設定，然後按一下 **[!UICONTROL Push Selected Live]**。
   * 按一下 **[!UICONTROL Push All Live]**.

## 從中央位置刪除舞台上線設定 {#task_B72BEA9269704B1399600A9CA273369B}

如果您有許多要刪除的設定，可以使用頁面 **[!UICONTROL Manage Stage-Live Settings]** 從一個集中位置刪除設定。

<!-- 

t_deleting_staged_settings_from_a_central_location.xml

 -->

**警告**:按一下時， **[!UICONTROL Delete Selected]**&#x200B;所有勾選的設定都會立即刪除；沒有確認對話框來確認您確實要刪除選定的設定。 此外，沒有與頁面相關聯的「步驟記錄」功能。 因此，您無法還原刪除。

**若要從中央位置刪除舞台即時設定**

1. 在產品選單上，按一下 **[!UICONTROL Staging]**。
1. 在頁面 **[!UICONTROL Manage Stage-Live Settings]** 上，使用設定樹狀結構只檢查您要刪除的設定。
1. 按一下 **[!UICONTROL Delete Selected]**.
