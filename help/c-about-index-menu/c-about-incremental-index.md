---
description: 您可以使用「增量索引」來為即時或分段網站的「片段」建立索引，例如經常變更的頁面集合。
solution: Target
subtopic: Incremental Index
title: 關於增量索引
topic: Index,Site search and merchandising
uuid: b1ee9b08-dcbe-4ffe-b0b4-d379daaac9b5
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1357'
ht-degree: 0%

---


# 關於增量索引{#about-incremental-index}

您可以使用「增量索引」來為即時或分段網站的「片段」建立索引，例如經常變更的頁面集合。

## 使用增量索引{#concept_A7770F0552D14C47B3DDB65DB78FFFEE}

增量索引只需數秒即可執行，對於需要數小時才能完成索引的大型網站非常有用。

當生成增量索引時，會顯示狀態資訊，例如索引過程中的開始時間、佔用時間和錯誤。 此外，還會顯示有關上一個索引狀態的資訊。

您可以隨時停止或重新啟動增量索引過程。

當您為即時網站建立新的增量索引時，客戶可以繼續使用您的上次增量索引來搜尋您的網站。

## 配置分段網站{#task_46A367B0786C4C90BFFA5D3F95FD86C0}的增量索引

您可以指定網站URL和URL遮色片，以設定要加入增量「索引」的網站頁面。

**若要設定分段網站的增量索引**

1. 在產品功能表上，按一下「**[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Configuration]**」。
1. 在&#x200B;**[!UICONTROL Incremental Index Configuration]**&#x200B;頁面上，使用各種欄位來指定您要索引的頁面。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>欄位 </p> </th> 
      <th colname="col2" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>新增或更新URL </p> </td> 
      <td colname="col2"> <p>指定URL。 </p> <p>搜索自動機僅對自上次編製索引以來已更改的指定文檔進行索引。 </p> <p>此外，搜索自動機會跟蹤包含在指定文檔中的連結，並僅對已更改的文檔進行索引。 </p> <p>此欄位只能包含檔案URL，而不能像下列範例那樣包含遮色片： </p> <p> 
        <code>
          https://www.mydomain.com/products/new.html 
        </code> </p> <p>您可搭配URL使用下列關鍵字： </p> <p> 
        <ul id="ul_62D1082ACBD547D092B10D72C56A3A1E"> 
          <li id="li_32C2B21DE75C4459908384CC44822F7D"> 
          <code>
            noindex 
          </code> <p>如果您不想為頁面上符合指定URL的文字建立索引，但想要遵循頁面的連結，請新增 
            <code>
              noindex 
            </code>在URL後面，如下例所示： </p> <p> 
            <code>
              https://www.mydomain.com/products/new.html noindex 
            </code> </p> <p>請確定您已分隔 
            <code>
              noindex 
            </code>（從含空格的URL）;逗號不是有效的分隔符號。 </p> </li> 
          <li id="li_33AB62B669084BF7B976F4308715E435"> 
          <code>
            nofollow 
          </code> <p>如果您想要為頁面上符合指定URL的文字建立索引，但不想追隨頁面的連結，請新增 
            <code>
              nofollow 
            </code>在URL後面，如下例所示： </p> <p> 
            <code>
              https://www.mydomain.com/products/new.html nofollow 
            </code> </p> <p> 請確定您已分隔 
            <code>
              nofollow 
            </code>（從含空格的URL）;逗號不是有效的分隔符號。 </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>尋找和更新URL遮色片 </p> </td> 
      <td colname="col2"> <p>指定簡單的URL遮色片——完整路徑、部分路徑或使用萬用字元或規則運算式的路徑。 </p> <p>搜索自動機僅查找自上次編製索引以來更改的所有匹配文檔和索引。 </p> <p>此外，搜索自動機會跟蹤匹配文檔中包含的連結，並僅對已更改的頁進行索引。 例如: </p> <p> 
      <code>
        https://www.mydomain.com/products/household/*.html 
      </code> </p> <p>您也可以使用規則運算式，如下列範例所示： </p> <p> 
      <code>
        regexp ^https://www\.mydomain\.com/products/household/.*\.html$ 
      </code> </p> <p>請參閱<a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local">規則運算式</a>。 </p> <p>您也可以使用關鍵字 
      <code>
        nofollow 
      </code>和 
      <code>
        noindex 
      </code>，如上文<span class="uicontrol">新增或更新URL </span>所述。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>包含和排除URL遮色片 </p> </td> 
      <td colname="col2"> <p>指定簡單的包含或排除URL遮色片——完整路徑、部分路徑或使用萬用字元或規則運算式的路徑。 </p> <p>搜索自動機根據指定的掩碼類型查找和索引("include")或忽略("exclude")文檔。 </p> <p> 在為網站建立索引時，會依外觀順序遵循方向。 例如，下列遮色片清單： </p> <p> 
      <code>
        include https://www.mydomain.com/products/household/lightbulbs*.html 
      </code> </p> <p> 
      <code>
        exclude https://www.mydomain.com/products/ 
      </code> </p> <p>索引頁 
      <code>
        lightbulbs1.html 
      </code>和 
      <code>
        lightbulbs2.html 
      </code>。 但是，它不會為列在產品目錄下的任何其他頁面建立索引。 </p> <p>首先出現的URL遮色片一律優先於稍後出現在清單中的URL遮色片。 此外，如果搜索自動機遇到與包含蒙版和排除蒙版匹配的文檔，則首先列出的蒙版優先。 </p> <p>您也可以使用關鍵字 
      <code>
        nofollow 
      </code>和 
      <code>
        noindex 
      </code>，如上文<span class="uicontrol">新增或更新URL </span>所述。 </p> <p>請參閱<a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164" type="concept" format="dita" scope="local">關於URL遮色片</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>包含和排除日期遮色片 </p> </td> 
      <td colname="col2"> <p>指定簡單的包含或排除日期遮色片——完整路徑、部分路徑或使用萬用字元或規則運算式的路徑。 </p> <p>搜索自動機根據URL和文檔日期查找和索引（「包含」）或忽略（「排除」）文檔。 </p> <p>您可以使用下列日期遮色片類型： </p> <p> 
      <ul id="ul_8958ED54C8EF405AA259236595ED3ABA"> 
      <li id="li_0A7841767E004F088CA6FA42E99B9F32"> 
      <code>
        include-days NNN 
      </code> <p>搜索自動機為所有與指定的URL掩碼匹配且為NNN天或更舊的文檔編製索引。 </p> <p>您可以使用下列一個或多個關鍵字跟隨URL遮色片： 
        <ul id="ul_22A38D5F38B344ABB02B16EB1865813B"> 
        <li id="li_B89CC37DC2A1428185E86FFCB9DDB193">nofollow </li> 
        <li id="li_C2579B3A338D4AF987C3F518806734B0">noindex </li> 
        <li id="li_0527BF7103F34B83AC3E684069B899F7">server-date </li> 
        </ul> </p> <p>例如，以下遮色片包含/archive/support檔案夾中0天或更舊的所有檔案： </p> <p> 
        <code>
          include-days 0 https://www.mydomain.com/archive/support/ 
        </code> </p> </li> 
      <li id="li_7663ABED40DD4E159F746E4F92BB6407"> 
      <code>
        include-date YYYY-MM-DD 
      </code> <p>搜索自動機為所有與指定的URL蒙版匹配且舊版或舊版YYYY-MM-DD日期相同的文檔編製索引。 </p> <p>您可以使用下列一個或多個關鍵字跟隨URL遮色片： </p> <p> 
        <ul id="ul_57BF37A413BB4A4D962863DACE56F395"> 
        <li id="li_88CAB9AB583B4754A5C53478BD1108FF">nofollow </li> 
        <li id="li_999E1CD34FDE4A1B9C332B4AA8C2887D">noindex </li> 
        <li id="li_05646FACF3524D2A9E201A23770E357F"> server-date </li> 
        </ul> </p> <p>下列遮色片範例包含日期為2011年7月25日或之前的/archive/檔案夾中的所有檔案： </p> <p> 
        <code>
          include-date 2011-07-25 https://www.mydomain.com/archive/ 
        </code> </p> </li> 
      <li id="li_172692DEDA8744B3AA492701D24C2D80"> 
      <code>
        exclude-days NNN 
      </code> <p>停用所有符合指定URL遮色片且為NNN天數或更舊之檔案的索引。 </p> <p>或者，您可以依關鍵字追蹤URL遮色片 
        <code>
          server-date 
        </code>。 </p> <p>下列遮色片範例會從索引中排除所有90天以上的PDF檔案： </p> <p> 
        <code>
          exclude-days 90 *.pdf 
        </code> </p> </li> 
      <li id="li_26078517744D4AECBE1351008926CBAE"> 
      <code>
        exclude-date YYYY-MM-DD 
      </code> <p>停用符合指定URL遮色片且舊版或舊版日期YYYY-MM-DD之所有檔案的索引。 </p> <p>或者，您可以依關鍵字追蹤URL遮色片 
        <code>
          server-date 
        </code>。 </p> <p>下列遮色片範例會排除日期為2004年4月23日或之前的/archive/檔案夾中的所有檔案： </p> <p> 
        <code>
          exclude-date 2004-04-23 https://www.mydomain.com/archive/ 
        </code> </p> </li> 
      </ul> </p> <p>請參閱<a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_F4F1F58A646F4A86B8650EC46FDCEF66" type="concept" format="dita" scope="local">關於日期遮色片</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>刪除URL </p> </td> 
      <td colname="col2"> <p>指定URL。 </p> <p>搜索自動機從搜索索引中查找並刪除指定的文檔。 如果指定的頁面已經在您的搜索索引中，則自動機會在添加或更新任何其他頁面之前將其刪除。 </p> <p>此欄位只能包含檔案URL，而不能包含遮色片。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>尋找和刪除URL遮色片 </p> </td> 
      <td colname="col2"> <p>指定簡單的URL遮色片——完整路徑、部分路徑或使用萬用字元或規則運算式的遮色片。 </p> <p>如果指定的URL遮色片與搜尋索引中的頁面相符，搜尋自動機會在新增或更新任何其他頁面之前，先刪除頁面。 例如: </p> <p> 
      <code>
        https://www.mydomain.com/products/1998/household/* 
      </code> </p> <p>您也可以使用規則運算式，如下列範例所示： </p> <p> 
      <code>
        regexp ^https://www\.mydomain\.com/products/199[567]/.*$ 
      </code> </p> <p>請參閱<a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local">規則運算式</a>。 </p> </td> 
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

## 設定即時網站{#task_2A46BA189ECC4317A9D5C6E99A336F33}的增量索引計畫

您可以選擇增量索引頻率和用於搜索和更新增量索引的基本時間。

您選取的時間會根據「帳戶設定」中設定的時區為本機時間。

請參閱[設定您的帳戶設定](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

Web伺服器通常會安排在半夜停工進行維護。 如果伺服器在計畫的索引時間內關閉，則索引過程將失敗。 請確定您選取了一天中的某個時間，您的Web伺服器才可用。

索引排程僅適用於您的即時索引；您無法計劃分段索引。

**若要設定即時網站的遞增索引排程**

1. 在產品功能表上，按一下「**[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Live Schedule]**」。
1. 在&#x200B;**[!UICONTROL Incremental Index Schedule]**&#x200B;頁面的&#x200B;**[!UICONTROL Incrementally Index]**&#x200B;下拉式清單中，選取索引頻率（以小時或分鐘為單位）。
1. 在&#x200B;**[!UICONTROL Base Time]**&#x200B;下拉式清單中，選取要重新產生新增索引的開始時間。
1. 按一下 **[!UICONTROL Save Changes]**.

## 執行即時或分段網站的遞增索引{#task_9BFB6157F3884B2FAECB7E0E9CA318CB}

您可以使用「增量索引」來為即時或分段網站的「片段」建立索引，例如經常變更的頁面集合。

**若要執行即時或分段網站的遞增索引**

1. 在產品功能表上，執行下列其中一項作業：

   * 按一下&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Live Index]**。

   * 按一下&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Staged Index]**。

1. 按一下 **[!UICONTROL Incremental Index Now]**.
1. （可選）如果發生索引錯誤，請按一下&#x200B;**[!UICONTROL View Errors]**&#x200B;以查看相關日誌。

## 檢視即時或分段網站{#task_E668E1F1240C476DAA1CA783DC728232}的增量索引記錄

當活動增量索引或分段增量索引完成時，您可以查看其關聯日誌以排除任何發生的錯誤。


您無法匯出記錄檔，也無法儲存記錄檔。 日誌仍可供查看，直到新索引出現。

**若要檢視即時或分段網站的增量索引記錄檔**

1. 在產品功能表上，執行下列其中一項作業：

   * 按一下&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Live Log]**。

   * 按一下&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Staged Log]**。

1. 在記錄頁的上方或下方，執行下列任一作業：

   * 使用導覽選項&#x200B;**[!UICONTROL First]**、**[!UICONTROL Prev]**、**[!UICONTROL Next]**、**[!UICONTROL Last]**&#x200B;或&#x200B;**[!UICONTROL Go to line]**&#x200B;在日誌中移動。

   * 使用顯示選項&#x200B;**[!UICONTROL Errors only]**、**[!UICONTROL Wrap line]**&#x200B;或&#x200B;**[!UICONTROL Show]**&#x200B;來調整您所看到的內容。

