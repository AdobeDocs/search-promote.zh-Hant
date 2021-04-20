---
description: 使用指令碼式索引，您可以編寫、更新和維護增量索引選項，而無需登錄。 搜索自動機從伺服器上托管的文本檔案中讀取說明。
solution: Target
subtopic: Scripted Index
title: 關於指令碼式索引
topic: Index,Site search and merchandising
uuid: 51e726ad-414b-4cbd-8a68-fefc3cf9b565
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1730'
ht-degree: 0%

---


# 關於指令碼式索引{#about-scripted-index}

使用指令碼式索引，您可以編寫、更新和維護增量索引選項，而無需登錄。 搜索自動機從伺服器上托管的文本檔案中讀取說明。

## 使用指令碼式索引{#concept_34F58D551BC04BFB8ADC294B9DA9199D}

## 關於配置指令碼式增量索引{#section_161D254065E143F3A39F3FC09C400090}

要使用指令碼式索引，請使用「指令碼式增量索引配置」頁來指定位於伺服器上的指令碼檔案（純文字檔案檔案）的URL。 例如, `https://www.mysite.com/indexlist.txt`。當您的網站變更時，您可以手動或自動將指令區塊新增至文字檔案（新聞摘要、股票行情或其他變更檔案的資訊送達時，會觸發指令碼）。

當指令碼式增量索引開始時，搜索自動機讀取文本檔案並運行在該檔案中找到的新命令。 預設情況下，搜索自動機僅處理由檔案日期確定的新命令。 除非您在配置指令碼索引時勾選&#x200B;**[!UICONTROL Clear Date]**，否則搜索自動機「記住」最近處理的塊的日期指定符。

## 關於指令碼檔案{#section_B312E40539F44C6583B4F9637D428E19}

您在URL中指定的指令碼檔案是位於伺服器上的純文字檔案。 您可以對行尾序列使用歸位、換行或兩者。 空白行包含零個或多個空格字元，後面接著行尾序列。 所有命令均不區分大小寫。

文本檔案以塊的形式組織，這些塊描述了搜索自動機在執行指令碼式增量索引時所使用的資訊。

區塊依日期排序，文字檔上方有最舊的區塊，下方有最新的區塊。 每個塊以單行date-command和date-specifier命令開始，並以空行分隔符結束，如以下塊示例中所示（在之間是幾個命令）:

使用HTTP 1.1樣式時，低於10th的所有序數日期都需要前導零。 例如，11月6日是11月6日，而非11月6日。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>命令 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>date-command </p> </td> 
   <td colname="col2"> <p>每個塊的第一行以兩個日期命令之一開頭： </p> <p> 
     <ul id="ul_9C1B229B7F1846C490B853FC34989E77"> 
      <li id="li_31FEF1A7163842BDBB0ABE779D07045A"> <span class="codeph"> 日期  </span> <p>使用「日期」命令指示日期指定符將由日、日、時和時區組成。 </p> </li> 
      <li id="li_0918D5B090014C1A852CB80BB7C2867C"> <span class="codeph"> 秒 </span> <p>使用<span class="codeph">秒</span>表示日期指定符將包含一個時間（以紀元秒為單位）（例如784111777）。 使用<span class="codeph">秒</span>時，請確保塊之間的秒數增加。 </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日期指定符 </p> </td> 
   <td colname="col2"> <p><span class="codeph"> date-specifier </span>命令通常記錄將塊資訊添加到檔案中的順序日期和時間（date命令）或時間秒（秒命令）。 例如: </p> <p> <code> date&nbsp;Sun,&nbsp;06&nbsp;Nov&nbsp;1994&nbsp;08:49:37&nbsp;GMT&nbsp;(HTTP&nbsp;1.1&nbsp;style) 
      date&nbsp;Sunday,&nbsp;06-Nov-94&nbsp;08:49:37&nbsp;GMT&nbsp;(HTTP&nbsp;1.0&nbsp;style) 
      date&nbsp;Sun&nbsp;Nov&nbsp;6&nbsp;08:49:37&nbsp;1994&nbsp;(Unix&nbsp;asctime()&nbsp;date&nbsp;style) 
      seconds&nbsp;784111777&nbsp;(Unix&nbsp;epoch-seconds&nbsp;style) </code> </p> <p>使用HTTP 1.1樣式時，低於10th的所有序數日期都需要前導零。 例如，11月6日是11月6日，而非11月6日。 </p> <p>搜尋自動機會「記住」最近處理過的區塊的日期指定字元，並僅索引其認為「較新」的資訊。 (即時對搜索機器人並不重要。 相反，與先前處理的時間相比的時間才是重要的。) </p> <p>例如，搜索自動機讀取日期指定符為10:00 p.m的塊後，它不會讀取記錄時間在10:00 p.m.之前的任何塊，而不管索引操作何時運行。 在最壞的情況下，您可能會在日期指定字元中錯誤地輸入"2040"，而非"2004"。 在這種情況下，搜索機器人在下次索引操作期間對2040塊進行索引，然後拒絕讀取任何其他資訊塊（除非有一個2040年後日期）。 如果發生此情況，請移除文字檔案中所有先前處理過的區塊，按一下「清除日期</span>」，然後即時推送。<span class="uicontrol"> </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>留言行 </p> </td> 
   <td colname="col2"> <p>以"#"字元開始注釋行。 </p> <p>每條注釋行都必須是自己的行；您無法鍵入行章節附註釋。 </p> <p>注釋行不被視為空白行。 它也可以出現在區塊中的任何位置，即使是在日期或秒數命令之前，如下列範例所示： </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;#Added&nbsp;by&nbsp;Cathy&nbsp;Read&nbsp;after&nbsp;the&nbsp;Y2K&nbsp;seminar 
      &nbsp;&nbsp;&nbsp;&nbsp;date&nbsp;Mon,&nbsp;29&nbsp;Dec&nbsp;1999&nbsp;09:32:20&nbsp;GMT&nbsp; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>action-command </p> </td> 
   <td colname="col2"> <p>每個文本塊可以包含任意數量的操作命令。 以下action-command選項與標準增量索引的選項相對應： </p> <p> 
     <ul id="ul_8E1435350A0F416BB8F7826CD3886E74"> 
      <li id="li_22181666628C48A28A6A0BA1F7CA8E77"> 
       <code>
         add 
       </code> <p>搭配URL使用。 搜索自動機僅對自上次索引操作以來更改的指定URL編製索引。 此外，搜索自動機會跟蹤包含在指定文檔中的連結，並僅對已更改的文檔進行索引。 </p> <p>您可以在URL後面加上 
        <code>
          nofollow 
        </code>或 
        <code>
          noindex 
        </code>關鍵字，如下列範例所示： </p> <p> <code> add&amp;nbsp;https://www.mydomain.com/&amp;nbsp;noindex </code> </p> </li> 
      <li id="li_8E47BF07DB24417083883F5BF40D6B9E"> 
       <code>
         update 
       </code> <p>搭配URL遮色片使用。 搜索自動機查找並更新與指定的URL蒙版匹配的所有文檔。 </p> <p>您可以在URL後面加上 
        <code>
          nofollow 
        </code>或 
        <code>
          noindex 
        </code>關鍵字，如下列範例所示： </p> <p> <code> update&amp;nbsp;https://www.mydomain.com/products/ </code> </p> </li> 
      <li id="li_B3EC8B1670D54F66A1D8411A694EF7E4"> 
       <code>
         include 
       </code>或 <code>
         exclude 
       </code> <p>搭配URL遮色片使用。 搜索自動機根據指定的掩碼類型查找和索引("include")或忽略("exclude")文檔。 </p> <p>例如， </p> <p> <code> include&amp;nbsp;https://www.mydomain.com/products/household/lightbulbs*.html </code> </p> <p>或  </p> <p> <code> exclude&amp;nbsp;https://www.mydomain.com/archive/ </code> </p> </li> 
      <li id="li_050B54B735F0475E93806455FA6DC6A5"> 
       <code>
         include-date 
       </code>或 <code>
         exclude-date 
       </code> <p>搭配URL遮色片使用。 搜索自動機根據URL和文檔日期查找和索引（「包含」）或忽略（「排除」）文檔。 可使用下列類型的遮色片： </p> <p> 
        <ul id="ul_23A15CB492214B86BE84D8E6EA1820AE"> 
         <li id="li_0C7051AC3B5A4C57A3E477F7B6246611"> 
          <code>
            include-days NNN 
          </code> <p>搜索自動機為所有與指定的URL掩碼匹配且為NNN天或更舊的文檔編製索引。 </p> <p>您可以跟隨URL遮色片和關鍵字 
           <code>
             nofollow 
           </code>, 
           <code>
             noindex 
           </code>和／或 
           <code>
             server-date 
           </code>。 </p> </li> 
         <li id="li_983A10E2ED5D434EA9031F32143F4EF4"> 
          <code>
            include-date YYYY-MM-DD 
          </code> <p> 搜尋自動機會索引所有符合指定URL遮色片且舊版或舊版日期YYYY-MM-DD的檔案，其中"YYYY"是4位元年，"MM"是1或2位元月(1-12),"DD"是1或2位元日(1-31)。 </p> <p>您可以跟隨URL遮色片和關鍵字 
           <code>
             nofollow 
           </code>, 
           <code>
             noindex 
           </code>和／或 
           <code>
             server-date 
           </code>。 </p> </li> 
         <li id="li_733CE1B748024CECA7FBE00D7BC7B88A"> 
          <code>
            exclude-days NNN 
          </code> <p> 禁用所有與指定的URL掩碼匹配且為NNN天或更舊的文檔的索引。 </p> <p>您可以使用關鍵字跟隨URL遮色片 
           <code>
             server-date 
           </code>。 </p> </li> 
         <li id="li_90056A0B96CC4DA3854711860A15CE89"> 
          <code>
            exclude-date YYYY-MM-DD 
          </code> <p>停用符合指定URL遮色片且舊版或舊版日期YYYY-MM-DD之所有檔案的索引。 </p> <p>您可以使用關鍵字跟隨URL遮色片 
           <code>
             server-date 
           </code>。 </p> </li> 
        </ul> </p> </li> 
      <li id="li_AA78F22B60FE4535BE73BA87A8992C08"> 
       <code>
         delete 
       </code> <p>指定URL。 搜索自動機從由URL標識的索引中刪除文檔。 </p> </li> 
      <li id="li_9C63061568AA4D57A4FEBCF6DB9194EC"> 
       <code>
         deletemask 
       </code> <p>搜索自動機從與指定的URL掩碼匹配的索引中刪除文檔。 </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

另請參閱[關於URL遮色片](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164)。

## 指令碼檔案示例{#section_9F580F20E7214751B157A28B392BD64E}

在以下指令碼檔案示例中，如果日期指定符在日期之後是最近處理的塊的日期指定符，則搜索自動機將處理這些塊。 如果是，則會執行下列索引作業：

* 從索引中刪除`y2k-problems.html`。
* 將`no-y2k-problems.html`添加到搜索索引中，並且不跟隨`no-y2k-problems.html`的任何連結。

* 編目時，從搜尋索引中排除與`housewares.htm`和`lightfixtures.htm`l相符的URL。

* 在`www.mydomain.com`下包括所有其他目錄和文檔。
* 更新`products`和`information`目錄內的所有文檔，搜索和索引自上次索引操作以來更改的所有子連結。

* 在編目時，排除網站`archive`區段中的URL（如果URL的日期是1999年1月1日或之前）。
* 從搜尋索引中排除與`housewares.html`和`lightfixtures.html`相符的URL。

* 在`help`目錄中為檔案編製索引，但不從這些檔案編目或為任何連結編製索引。
* 搜索並索引為`www.mydomain.com`遇到的任何其他檔案。

```
# Start of file. 
# Added by John Smith 
date Sat, 01 Jan 2004 16:05:53 PST 
exclude https://www.mydomain.com/housewares.html 
exclude https://www.mydomain.com/lightfixtures.html 
include https://www.mydomain.com/ 
delete https://www.mydomain.com/y2k-problems.html 
add https://www.mydomain.com/no-y2k-problems.html nofollow 
 
date Sun, 02 Jan 2004 20:19:08 PST 
# Added by the wire service updater 
exclude-date 1999-01-01 https://www.mydomain.com/archive server-date 
exclude https://www.mydomain.com/housewares.html 
exclude https://www.mydomain.com/lightfixtures.html 
include https://www.mydomain.com/help/ nofollow 
include https://www.mydomain.com/ 
# no add files, just update existing files 
# update all files in the "products" directory 
update https://www.mydomain.com/products/ 
# update all files in the "information" directory 
update regexp ^https://www\.mydomain\.com/information/.*$ 
# End of file.
```

## 配置指令碼式增量索引{#task_05AE040FE75E40FFAA5E10B6B6D4D255}

您可以指定已建立的指令碼，該指令碼可以寫入、更新和維護增量索引，而無需登錄。 搜索自動機從伺服器上托管的文本檔案中讀取指令，以執行增量索引。

**配置指令碼式增量索引**

1. 在產品功能表上，按一下「**[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Configuration]**」。
1. 在&#x200B;**[!UICONTROL Scripted Incremental Index Configuration]**&#x200B;頁面的&#x200B;**[!UICONTROL Script File URL]**&#x200B;中，輸入位於您伺服器上的文字檔案指令碼的URL。

   請參閱[關於指令碼化索引](../c-about-index-menu/c-about-scripted-index.md#concept_34F58D551BC04BFB8ADC294B9DA9199D)。
1. （可選）如果您不希望搜索自動機「記住」最近處理的塊的日期指定符，請選中&#x200B;**[!UICONTROL Clear Date]**。

   預設情況下，搜索自動機只處理文本檔案中找到的新命令塊，該命令塊由檔案的日期確定。 如果您不想使用預設值，請勾選&#x200B;**[!UICONTROL Clear Date]**。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 為即時網站{#task_B3A87AC4AC784507859C23B9062BA11C}設定指令碼式增量索引計畫

您可以安排指令碼式增量索引以在一天中定期執行。

您選取的基本時間會根據「帳戶設定」中設定的時區為本機時間。

請參閱[設定您的帳戶設定](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

Web伺服器通常會安排在半夜停工進行維護。 如果伺服器在計畫的索引時間內關閉，則索引過程將失敗。 請確定您選取了一天中的某個時間，您的Web伺服器才可用。

索引排程僅適用於您的即時索引；不能計劃分段增量索引。

**要設定即時網站的指令碼式增量索引計畫**

1. 在產品功能表上，按一下「**[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Live Schedule]**」。
1. 在&#x200B;**[!UICONTROL Scripted Incremental Index Schedule]**&#x200B;頁面的&#x200B;**[!UICONTROL Read the Scripted Incrementally Indexing File]**&#x200B;下拉式清單中，選擇您希望指令碼增量索引文本檔案以小時或分鐘為單位運行的頻率。
1. 在&#x200B;**[!UICONTROL Base Time]**&#x200B;下拉式清單中，選取要重新產生新指令碼增量索引的開始時間。
1. 按一下 **[!UICONTROL Save Changes]**.

## 運行即時或分段網站{#task_6E6FC76EE1E84A5FADB3B67AD7B1DACB}的指令碼式增量索引

您可以使用指令碼增量索引來為即時或分段網站的「片段」建立索引，例如經常變更的頁面集合，而不需登入。

要使用此功能，請確定已配置指令碼式增量索引文本檔案。

請參閱[配置指令碼式增量索引](../c-about-index-menu/c-about-scripted-index.md#task_05AE040FE75E40FFAA5E10B6B6D4D255)。

**若要執行即時或分段網站的指令碼增量索引**

1. 在產品功能表上，執行下列其中一項作業：

   * 按一下&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Live Index]**。
   * 按一下&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Staged Index]**。

1. 按一下 **[!UICONTROL Scripted Index Now]**.
1. （可選）如果發生索引錯誤，請按一下&#x200B;**[!UICONTROL View Errors]**&#x200B;以查看相關日誌。

## 查看即時或分段網站{#task_CBFCE9B9A87B4DF7A2A35A6E83DE93D7}的指令碼式增量索引日誌

當活動完整指令碼索引或分段完整指令碼索引完成時，您可以查看其關聯日誌以排除任何發生的錯誤。

您無法匯出記錄檔，也無法儲存記錄檔。 不過，日誌仍可供查看，直到新索引出現。

**若要檢視即時或分段網站的增量索引記錄檔**

1. 在產品功能表上，執行下列其中一項作業：

   * 按一下&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Live Log]**。

   * 按一下&#x200B;**[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Staged Log]**。

1. 在記錄頁的上方或下方，執行下列任一作業：

   * 使用導覽選項&#x200B;**[!UICONTROL First]**、**[!UICONTROL Prev]**、**[!UICONTROL Next]**、**[!UICONTROL Last]**&#x200B;或&#x200B;**[!UICONTROL Go to line]**&#x200B;在日誌中移動。

   * 使用顯示選項&#x200B;**[!UICONTROL Errors only]**、**[!UICONTROL Wrap line]**&#x200B;或&#x200B;**[!UICONTROL Show]**&#x200B;來調整您所看到的內容。

