---
description: 每當您的網站變更時，您都可以執行指令碼或程式，要求搜尋自動機使用遠端控制來執行索引。
seo-description: 每當您的網站變更時，您都可以執行指令碼或程式，要求搜尋自動機使用遠端控制來執行索引。
seo-title: 關於為索引進行遠程控制
solution: Target
title: 關於為索引進行遠程控制
topic: Index,Site search and merchandising
uuid: 20e230c6-5c1a-4bf4-bff3-b8236d14ab21
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a
workflow-type: tm+mt
source-wordcount: '1064'
ht-degree: 1%

---


# 關於索引的遠程控制{#about-remote-control-for-indexing}

每當您的網站變更時，您都可以執行指令碼或程式，要求搜尋自動機使用遠端控制來執行索引。

## 使用遠程控制項為{#concept_C79B322190E84106A434E5C6D4A4118F}編製索引

遙控索引請求通常來自伺服器上的指令碼或程式。

自動機執行的索引步驟與從[!DNL Index]菜單手動啟動的步驟相同。 要提交遠程控制請求，請配置必要的密碼和響應字串。

## 如何發出遠程控制請求{#section_42FAB2BAB25A4E24BEA69566C6D1C70F}

要發出遠程控制請求，請根據資料中心的位置使用以下格式示例：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>資料中心位置 </p> </th> 
   <th colname="col2" class="entry"> <p>範例 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>倫敦 </p> </td> 
   <td colname="col2"> <p> <code> https://center.lon5.atomz.com/search/cgiindex.tk? <b>sp_a=sp99999999&amp;sp_password=xxxxxx&amp;sp_operation=op</b> </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>北美 </p> </td> 
   <td colname="col2"> <p> <code> https://center.atomz.com/search/cgiindex.tk? <b>sp_a=sp99999999&amp;sp_password=xxxxxx&amp;sp_operation=op</b> </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>新加坡 </p> </td> 
   <td colname="col2"> <p> <code> https://center.sin2.atomz.com/search/cgiindex.tk? <b>sp_a=sp99999999&amp;sp_password=xxxxxx&amp;sp_operation=op</b> </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

或 

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>字串與值 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_a= sp99999999  </span> </p> </td> 
   <td colname="col2"> <p> 您的帳號。 </p> <p>您可以在<span class="uicontrol"><b>Settings</b> </span> &gt; <span class="uicontrol"> <b>Account Options</b> </span> &gt; <span class="uicontrol"> <b>Account Settings</b> </span>下找到您的帳戶號碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_lines= N  </span> </p> </td> 
   <td colname="col2"> <p>可讓您檢查正在運行的索引編目的狀態。 </p> <p> <span class="codeph">  N </span> 是正整數或全 <span class="codeph"> 部 </span>。如果這是數值，則對應的索引記錄檔的最後一行<span class="codeph"> N </span>會包含在JSON回應中。 </p> <p>如果值為<span class="codeph">所有</span>，則返回整個檔案。 </p> <p>如果值為<span class="codeph"> 0 </span>，則不返回日誌資訊。 此值是運行索引狀態查詢的預設值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_operation= op  </span> </p> </td> 
   <td colname="col2"> <p>可讓您指定下列其中一個要執行的索引作業： </p> <p> 
     <ul id="ul_6CA190AC41694BC293FC7C6BABA629FE"> 
      <li id="li_EFC76E31D47E473F9A56B2EBA8A97CA1"> <span class="codeph"> full_index  </span> <p>搜尋機器人會執行您網站的完整索引。 </p> </li> 
      <li id="li_A9ACE21718804A21B3DA7B84AB6729D3"> <span class="codeph"> 增量索引  </span> <p>搜索自動機使用在<span class="uicontrol"><b>Index</b> </span> &gt; <span class="uicontrol"><b>Incremental Index</b> </span> &gt; <span class="uicontrol">Configuration</b></span>下設定的配置來運行增量索引。<b> </b></p> </li> 
      <li id="li_722FE409AE454AD48ACE95C4CDC7A00B"> <span class="codeph"> 垂直索引  </span> <p>搜索自動機使用在<span class="uicontrol"><b>Index</b> </span> &gt; <span class="uicontrol"> <b></span> &gt; <span class="uicontrol"><b>Configuration</b></span>下設定的配置運行垂直更新。</b> </span></p> <p>請參閱<a href="../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local">關於垂直更新</a>。 </p> </li> 
      <li id="li_A40B513CE17043A4925CE3D4DE0B48A4"> <span class="codeph"> script_index  </span> <p>搜索自動機使用在<span class="uicontrol"><b>索引</b> </span> &gt; <span class="uicontrol"><b>指令碼化索引</b> </span> &gt; <span class="uicontrol">配置</b></span>下指定的文本檔案運行增量索引。<b> </b></p> </li> 
      <li id="li_A0BC7F1373B14393997BAB7690FD3EF7"> <span class="codeph"> full_staged_index  </span> <p>搜尋自動機會執行您網站的完整分段索引。 </p> </li> 
      <li id="li_47753E358457443A95B384A278FACA83"> <span class="codeph"> incremental_staged_index  </span> <p>搜索自動機使用在<span class="uicontrol"><b>Index</b> </span> &gt; <span class="uicontrol"><b>Incremental Index</b> </span> &gt; <span class="uicontrol">Configuration</b></span>下設定的配置來運行增量分段索引。<b> </b></p> </li> 
      <li id="li_C8B5F8F1208E438ABEFDF9129A6B14A3"> <span class="codeph"> 垂直_staged_index  </span> <p>搜索自動機使用在<span class="uicontrol"><b>Index</b> </span> &gt; <span class="uicontrol"> <b></span> <span class="uicontrol"><b>Configuration</b></span>下設定的配置運行垂直分段更新。</b> </span></p> </li> 
     </ul> </p> <p>注意： 若要使用「垂直更新」，您可能需要由Adobe帳戶代表或Adobe支援在您的帳戶中啟用它。 </p> <p>請參閱<a href="../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local">關於垂直更新</a>。 </p> <p>您可以將<span class="codeph"> _saved </span>附加到上述任何<span class="codeph"> sp_operation </span>值，使搜索自動機嘗試使用保存的內容。 例如，您可以指定下列項目： </p> <p> <code class="syntax html"> sp_operation=full_index_saved </code> </p> <p>或  </p> <p> <code class="syntax html"> sp_operation=full_staged_index_saved </code> </p> <p>或者，您可將<span class="codeph"> _status </span>附加至上述任何<span class="codeph"> sp_operation </span>值，以請求目前或最近的操作的狀態報告。 例如，您可以指定下列項目： </p> <p> <code class="syntax html"> sp_operation=full_index_status </code> </p> <p>或  </p> <p> <code class="syntax html"> sp_operation=full_staged_index_status </code> </p> <p>結果會以JSON物件傳回。 包括<span class="codeph"> sp_lines=N </span>以包括關聯日誌檔案的N行。 如果N為負數，則會包含最後N行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_operation= pushlive  </span> </p> </td> 
   <td colname="col2"> <p> 可讓您遠端推送即時分段索引。 </p> <p>任何將<span class="codeph"> _saved </span>附加至推送即時作業的嘗試都會被忽略。 </p> <p>當您執行<span class="codeph"> pushlive </span>操作時，會將OK、Priority或Error響應文本字串返回到伺服器。 您可以在<span class="wintitle"> Remote Control </span>頁面上指定這些響應字串。 </p> <p>請參閱<a href="../c-about-index-menu/c-about-remote-control-for-indexing.md#task_57C296258404448DA7A5ADC9B7232391" format="dita" scope="local">配置遠程控制以編製索引</a>。 </p> <p>如果您在沒有分段索引時推送為即時，則不會發生任何動作，並傳回「確定」回應字串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_password= xxxxxx  </span> </p> </td> 
   <td colname="col2"> <p>遙控密碼。 </p> </td> 
  </tr> 
 </tbody> 
</table>

搜尋會以適當HTTP回應的形式傳回資料。 完整回應由HTTP狀態、HTTP回應標題、空白行和回應字串組成。

例如，假設您執行以下遠程控制請求：

```
https://center.atomz.com/search/cgiindex.tk?sp_a=sp99999999&sp_password=my-password&sp_operation=full_index
```

以下是來自伺服器的響應：

```
Status: 200 OK 
Content-type: text/plain 
OK
```

或者，假設您執行下列遠程控制狀態請求：

```
https://center.atomz.com/search/cgiindex.tk?sp_a=sp99999999&sp_password=my-password&sp_operation=full_index_status
```

來自伺服器的回應可能如下所示：

```
Status: 200 OK 
Content-type: application/json; charset=utf-8 
{ 
    "current_time": "2017-08-27T10:58:58-0700", 
    "start_time": "2017-07-25T16:40:07-0800", 
    "end_time": "2017-07-25T16:40:20-0800", 
    "elapsed_seconds": 13, 
    "elapsed_seconds_fmt": "13s", 
    "state": "finished", 
    "docs_indexed": 3, 
    "depth": 0, 
    "errors": 0, 
    "status": 1, 
    "message": "ok" 
}
```

要獲取與此索引操作關聯的日誌清單的前10行及其狀態，請使用以下查詢：

```
https://center.atomz.com/search/cgiindex.tk?sp_a=sp99999999&sp_password=my-password&sp_operation=full_index_status&sp_lines=10
```

來自伺服器的響應：

```
Status: 200 OK 
Content-type: application/json; charset=utf-8 
{ 
    "current_time": "2017-08-27T10:59:30-0700", 
    "start_time": "2017-07-25T16:40:07-0800", 
    "end_time": "2017-07-25T16:40:20-0800", 
    "elapsed_seconds": 13, 
    "elapsed_seconds_fmt": "13s", 
    "state": "finished", 
    "docs_indexed": 3, 
    "depth": 0, 
    "errors": 0, 
    "offset": 672, 
    "lines": [ 
        "07/25 16:40:07 PST   ======== Starting manual crawl of account sp99999999. ========", 
        "07/25 16:40:08 PST   Loading existing data", 
        "07/25 16:40:08 PST   Downloading entrypoint https://www.atomz.com/", 
        "07/25 16:40:08 PST   Robots.txt exclude mask: https://www.atomz.com/snap", 
        "07/25 16:40:08 PST   Exclude mask: regexp ^https://www.atomz.com/$", 
        "07/25 16:40:08 PST   Include mask: https://www.atomz.com/", 
        "07/25 16:40:08 PST   Downloading https://www.atomz.com/style.css", 
        "07/25 16:40:09 PST   Ignoring https://www.atomz.com/style.css, document type 'text/css'.", 
        "07/25 16:40:09 PST   Downloading https://www.atomz.com/privacy.html", 
        "07/25 16:40:09 PST   Downloading https://www.atomz.com/terms.html" 
    ], 
    "status": 1, 
    "message": "ok" 
}
```

請注意`offset`值。 此值標識日誌檔案中的檔案偏移位置，其中讀取為左。 若要讀取檔案中的&#x200B;*next*&#x200B;十行，請在此範例中，在傳送至伺服器的請求中加入`&sp_offset=672`。

使用`sp_offset`，您可以有效地通過日誌檔案進行頁面設定。

若要取得記錄檔的&#x200B;*last*&#x200B;十行以及狀態，請將計數指定為負數。 例如，指定`sp_lines=`，其值為`-10`，如下所示：

```
https://center.atomz.com/search/cgiindex.tk?sp_a=sp99999999&sp_password=my-password&sp_operation=full_index_status&sp_lines=-10
```

來自伺服器的響應：

```
Status: 200 OK 
Content-type: application/json; charset=utf-8 
{ 
    "current_time": "2017-08-27T11:01:14-0700", 
    "start_time": "2017-07-25T16:40:07-0800", 
    "end_time": "2017-07-25T16:40:20-0800", 
    "elapsed_seconds": 13, 
    "elapsed_seconds_fmt": "13s", 
    "state": "finished", 
    "docs_indexed": 3, 
    "depth": 0, 
    "errors": 0, 
    "lines": [ 
        "07/25 16:40:20 PST   End Time: 07/25/2017 16:40:20 PST", 
        "07/25 16:40:20 PST   Elapsed Time: 13 seconds", 
        "07/25 16:40:20 PST   Pages Crawled: 3 pages", 
        "07/25 16:40:20 PST   Pages Indexed: 3 pages", 
        "07/25 16:40:20 PST   Words/Bytes Indexed: 2373 words/ 20618 bytes", 
        "07/25 16:40:20 PST   Errors: 0", 
        "07/25 16:40:20 PST   *** Index Summary ***", 
        "07/25 16:40:20 PST   Total Pages: 3", 
        "07/25 16:40:20 PST   --------------------------------------------------------------------", 
        "07/25 16:40:20 PST   ======== Finish manual crawl of account sp99999999: Done. ========" 
    ], 
    "status": 1, 
    "message": "ok" 
}
```

請注意，此處沒有返回`offset`值，因為此操作在檔案末尾完成，並且沒有其他行可供讀取。

## 配置遠程控制以編製{#task_57C296258404448DA7A5ADC9B7232391}索引

每當您的網站變更時，您都可以使用「遠端控制」從伺服器執行指令碼或程式，要求搜尋自動機執行索引。

**配置遠程控制以編製索引**

1. 在產品功能表上，按一下「**[!UICONTROL Index]** > **[!UICONTROL Remote Control]**」。
1. 在[!DNL Remote Control]頁面上，將每個配置欄位選項設定為能夠自動從伺服器提交索引請求以索引您的網站。

   <table> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> <p>選項 </p> </th> 
    <th colname="col2" class="entry"> <p>說明 </p> </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>遠程控制密碼 </p> </td> 
    <td colname="col2"> <p>指定遠程控制密碼。 </p> <p> 密碼區分大小寫，至少有6個字元長，且必須至少包含一個字母。 建議您也至少包含一個數字。 </p> <p>請勿使用您的網站搜尋／銷售登入密碼。 </p> <p>每個遠程控制請求都會使用您的密碼。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>確定響應字串 </p> </td> 
    <td colname="col2"> <p>可讓您在請求的索引操作成功開始時指定「確定」響應文本字串。 在這種情況下，搜索自動機將您的「確定」(OK)響應字串返回到伺服器。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>優先順序回應字串 </p> </td> 
    <td colname="col2"> <p>如果在執行遠程請求時正在執行另一個索引操作，則搜索自動機無法執行請求的索引。 在這種情況下，您的優先順序回應文字字串會傳回至伺服器。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>錯誤回應字串 </p> </td> 
    <td colname="col2"> <p>可讓您指定「錯誤」回應文字字串。如果您的密碼不正確，或是發生其他錯誤。 在這種情況下，搜索自動機會將錯誤響應字串返回伺服器。 </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. 按一下 **[!UICONTROL Save Changes]**.
