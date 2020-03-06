---
description: 使用「篩選」菜單，可以使用在編製索引之前更改Web文檔內容的指令碼。
seo-description: 使用「篩選」菜單，可以使用在編製索引之前更改Web文檔內容的指令碼。
seo-title: 關於篩選功能表
solution: Target
subtopic: Filtering
title: 關於篩選功能表
topic: Settings,Site search and merchandising
uuid: ebb08fa8-4e17-417d-868b-11fc2af9f284
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a

---


# 關於篩選功能表{#about-the-filtering-menu}

使用「篩選」菜單，可以使用在編製索引之前更改Web文檔內容的指令碼。

## 關於篩選指令碼 {#concept_E56B73D625854AB2A899EF2D56CFCB47}

您可以使 [!DNL Filtering Script] 用更改Web文檔的內容，然後對其進行索引。

您可以插入HTML標籤、移除不相關的內容，甚至根據檔案的URL、MIME類型和現有內容建立新的HTML中繼資料。 過濾指令碼是Perl指令碼，它提供強大的字串處理和規則運算式匹配的靈活性。 您可將篩選指令碼與初始化指令碼、終止指令碼、URL遮色片指令碼和測試URL搭配使用。

每次從您的網站讀取檔案時，都會執行篩選指令碼。 此指令碼會以標準篩選器的形式執行，換言之，從STDIN讀取資料，以某種方式轉換該資料，並將結果寫入STDOUT。 您可以使用篩選指令碼將狀態消息從篩選指令碼打印到索引日誌。 您可以將消息打印到STDERR，也可以通過子常式 `_search_debug_log()` 打印。

在「分段篩選指令碼」頁面的模式 **[!UICONTROL Expert (diff)]** 下可使用的某些GNU比較選項包括：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>GNUdiff選項 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -b </span> </p> </td> 
   <td colname="col2"> <p> 忽略空格量的變更。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -B </span> </p> </td> 
   <td colname="col2"> <p> 忽略插入或刪除空行的更改。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -c </span> </p> </td> 
   <td colname="col2"> <p> 使用上下文輸出格式，顯示三行上下文。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -C行 </span> </p> </td> 
   <td colname="col2"> <p> 使用上下文輸出格式，顯示上下文的行（整數），如果未指定行，則使用三行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -i </span> </p> </td> 
   <td colname="col2"> <p> 忽略大小寫更改；請考慮等同大寫和小寫字母。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -f </span> </p> </td> 
   <td colname="col2"> <p> 使輸出看起來類似於編輯指令碼，但更改了它們在檔案中的顯示順序。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -n </span> </p> </td> 
   <td colname="col2"> <p> 輸出RCS格式差；例 <span class="codeph"> 如-f </span> ，但每個命令都指定受影響的行數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>-u </p> </td> 
   <td colname="col2"> <p> 使用統一的輸出格式，顯示三行上下文。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -U線 </span> </p> </td> 
   <td colname="col2"> <p> 使用統一的輸出格式，顯示上下文的行（整數），如果未指定行，則使用三行。 </p> </td> 
  </tr> 
 </tbody> 
</table>

您可以在這些指令碼中使用局部變數、全域變數或兩者。 所有全域變數都會以命名空間&quot;main::&quot;為前置詞。 啟動篩選指令碼時，其環境包含以下標準檔案句柄：

* STDIN —— 無（讀取時立即返回EOF）
* STDOUT —— 取代HTML（如果資料列印至STDOUT，則會用來取代原始檔案）
* STDERR —— 打印到STDERR的資料打印到索引日誌中是錯誤

此外，您還可以使用子常式將自定義消息寫入 `_search_debug_log()` 索引日誌，如下例所示：

```
# Log information to the Index Log 
_search_debug_log("Done processing document: " . $main::search_url);
```

這些消息以前面的單 `DEBUG` 字顯示，不會記錄為錯誤。

以下是篩選的範例。 網頁 `<title>` 欄位通常以公司名稱開頭。 雖然這項資訊對於網站導覽有用，但搜尋時卻不相關。 如果所有MegaCorp網頁的標題都以共同字串開頭，例如：

```
<title>MegaCorp -- meaningful title 
here</title>
```

您應從每個文 `MegaCorp --`件標題的開頭移除「」，並計算使用篩選指令碼處理的每個檔案。 若要這麼做，您可使用下列指令碼：

```
# Make sure this is an HTML document. 
if ($main::ws_content_type =~ /^text\/html/) { 
    # Read the entire document into a local scalar variable. 
    my @docarray = <>; 
    my $doc = join("", @docarray); 
 
    # Remove "MegaCorp -- " from the title. 
    $doc =~ s/(<TITLE>)MegaCorp -- /$1/gis; 
 
    # Print the resulting document. 
    print $doc; 
 
    # Count that we've filtered one more document. 
    $main::doc_count++; 
}
```

## 全域變數 {#global-variables}

您可以在任何篩選指令碼中使用下列變數：

| 變數 | 說明 |
|--- |--- |
| `$main::search_crawl_type` | 值指示 `$main::search_crawl_type` 正在進行的索引操作的類型。  已過時的表單：索 `$main::ws_crawl_type` 引操作和相關值包括： <ul><li>完整索引：手動- `manual`</li><li>完整索引：排程- `auto`</li><li>完整索引：遠程控制- `CGI`</li><li>增量索引：手動- `manual-incremental`</li><li>增量索引：排程- `auto-incremental` </li><li>增量索引：遠程控制- `CGI-incremental`</li><li>原稿索引：手動- `manual-indexlist.txt` </li><li>原稿索引：排程- `auto-indexlist.txt`</li><li>原稿索引：遠程控制- `CGI-indexlist.txt`</li><li>重新產生- `manual-upgrade`</li></ul> |
| `$main::search_clear_cache` | 該值指示當前索引操作是否請求了「清除索引快取」索引選項。 如果請求「清除索引快取」，則 `$main::search_clear_cache` 值為「 `1`」。  已廢止的形式: `$main::ws_clear_cache` |
| `$main::search_fields` | 值包含帳戶中定義之中繼資料欄位的標籤分隔清單。 依預設，值為：  不 `url title desc keys target body alt date charset language` 建議使用的表單： `$main::ws_fields` |
| `$main::search_collections` | 值包含帳戶中定義之系列的以標籤分隔清單。  已廢止的形式: `$main::ws_collections` |
| `$main::search_url` | 該值是文檔的完全限定URL。  已廢止的形式: `$main::ws_url` |
| `$main::search_content_type` | 值是從http-equiv meta標籤擷取之檔案的內容類型。 典型值是「text/html;charset=iso-8859-1」。  已廢止的形式: `$main::ws_content_type` |
| `$main::search_content_class` | 該值是文檔的內容類，從content-type欄位派生。  已廢止的形式: `$main::ws_content_class` |
| `$main::search_syntax_check` | 該值反映了「檢查語法」按鈕的使用。 若按下，則值為1(1);否則，其值為0（零）。  已廢止的形式: `$main::ws_syntax_check` |
| `$main::search_last_mod_date` | 如果Web伺服器提供，此值包含文檔的上次修改日期的Epoch表示法（自1970年1月1日以來的秒數）。  您可以使用Perl localtime()庫調用來格式化此值。 |

### 快速提示 {#section_89A5C16911744AF98E232DF608C6A1F5}

* 所有全域變數都會以命名空間&quot;main::&quot;為前置詞： `$main::doc_count = 0;`
* 所有局部變數都以&quot;my&quot;宣告： `my $i = 0;`
* 子常式在初始化指令碼中定義。 他們不需要明確的「main::」命名空間： `sub my_sub {`  `...`

   `}`

* 在對文 `$main::search_content_type` 件進行更改之前測試。 測試可協助您避免對二進位檔案（例如SWF檔案或PDF檔案）進行粗心變更：

   `if ($main::search_content_type =~ /^text\/html/) { ...`

* 您 `$main::search_content_type` 的伺服器傳送的完整內容類型標題。 它有時可包含簡單的MIME類型，例如&quot;text/html&quot;。 或者，它可以包含MIME類型，後面跟有其他資訊，如文檔的字元集編碼，如「text/html;charset=iso-8859-1」。
* 對於每種非HTML檔案類型，都可 `$main::search_content_type` 以使用各種值。 測試指令碼中的每個值會變得麻煩。 例如，某些Word檔案的內容類型值為&quot;application/msword&quot;、&quot;application/vnd.ms-word&quot;或&quot;application/x-msword&quot;。 在這種情況下， `$main::search_content_class` 可以採用下列值：

   * html
   * pdf
   * 詞
   * excel
   * powerpoint
   * mp3
   * text

* 在範例中，測 `$main::search_content_class` 試&quot;word&quot;會比對三種可能的內容類型值。
* 如果從篩選指令碼中沒有列印到STDOUT，則檔案會與下載的檔案完全相同。 也就是說，如果您不需要變更檔案中的任何項目，則不需要將該檔案的STDIN複製至STDOUT。
* 如果要從文檔中刪除所有文本，請打印有效的檔案STDOUT。 例如，要完全刪除HTML文檔中的所有文本，請執行以下操作： `print "<html></html>";`

## 新增篩選指令碼 {#task_0AB84FD1133F47F9AA069A79BEA13A22}

過濾指令碼是一個Perl指令碼，用於從您的網站下載的每個文檔。

您可將篩選指令碼與初始化指令碼、終止指令碼和URL遮色片指令碼搭配使用。

請確定您重建網站索引，以便客戶能夠看到篩選指令碼的結果。

請參 [閱配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**若要新增篩選指令碼**

1. 在產品功能表上，按一下 **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Filtering Script]**。
1. （可選）在頁 [!DNL Filtering Script] 面的欄位 [!DNL Test URL] 中，輸入網站上檔案的URL。

   按一下測試選項，查看原始HTML文字的變更。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>選項 </p> </th> 
      <th colname="col2" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>測試URL欄位 </p> </td> 
      <td colname="col2"> <p>可讓您在網站上輸入檔案的URL。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>測試 </p> </td> 
      <td colname="col2"> <p>根據篩選指令碼和URL遮色片測試URL。 </p> <p>測試URL檔案會下載，然後用作篩選指令碼的STDIN輸入。 然後會執行初始化、篩選和終止指令碼。 如果篩選指令碼有任何STDOUT輸出，則該輸出會顯示在新的瀏覽器視窗中。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>僅測試 </p> </td> 
      <td colname="col2"> <p>僅測試指令碼的操作。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>預覽 </p> </td> 
      <td colname="col2"> <p>可讓您檢視頁面。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>完整視覺化 </p> </td> 
      <td colname="col2"> <p>生成文檔的完整表視圖。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>短視 </p> </td> 
      <td colname="col2"> <p>僅顯示前後視圖之間的差異。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>專家（比較） </p> </td> 
      <td colname="col2"> <p>使用提供的命令行選項顯示用於比較檔案的GNU diff命令的原始輸出。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>篩選指令碼 </p> </td> 
      <td colname="col2"> <p>可讓您將篩選指令碼貼入所提供的欄位。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>儲存變更 </p> </td> 
      <td colname="col2"> <p>儲存篩選指令碼。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>檢查語法 </p> </td> 
      <td colname="col2"> <p>可讓您執行初始化、篩選和終止指令碼，以快速檢查指令碼的語法。 它不會更新並儲存您的指令碼。 </p> <p>所有Perl編譯器錯誤和警告，以及所有STDERR輸出都會打印出來。 </p> <p>客戶必須先重建網站索引，才能看到指令碼的效果。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

   **GNU diff命令行選項**

   在「分段篩選指令碼」頁面的模式 **[!UICONTROL Expert (diff)]** 下可使用的某些GNU比較選項包括：

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>GNU diff命令行選項 </p> </th> 
      <th colname="col2" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -b </span> </p> </td> 
      <td colname="col2"> <p> 忽略空格量的變更。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -B </span> </p> </td> 
      <td colname="col2"> <p> 忽略插入或刪除空行的更改。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -c </span> </p> </td> 
      <td colname="col2"> <p> 使用上下文輸出格式，顯示三行上下文。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -C行 </span> </p> </td> 
      <td colname="col2"> <p> 使用上下文輸出格式，顯示上下文的行（整數），如果未指定行，則使用三行。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -i </span> </p> </td> 
      <td colname="col2"> <p> 忽略大小寫更改；請考慮等同大寫和小寫字母。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -f </span> </p> </td> 
      <td colname="col2"> <p> 使輸出看起來類似於編輯指令碼，但更改了它們在檔案中的顯示順序。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -n </span> </p> </td> 
      <td colname="col2"> <p> 輸出RCS格式差；例 <span class="codeph"> 如-f </span> ，但每個命令都指定受影響的行數。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>-u </p> </td> 
      <td colname="col2"> <p> 使用統一的輸出格式，顯示三行上下文。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -U線 </span> </p> </td> 
      <td colname="col2"> <p> 使用統一的輸出格式，顯示上下文的行（整數），如果未指定行，則使用三行。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 按一 **[!UICONTROL Test]** 下以測試篩選指令碼和URL遮色片。

   按一 **[!UICONTROL Test]** 下不會更新並儲存您的篩選指令檔。
1. 在欄位 [!DNL Filtering Script] 中，貼上您的指令碼。
1. （可選）按一 **[!UICONTROL Check Syntax]** 下，執行篩選、初始化和終止指令碼，以快速檢查指令碼的語法。

   **[!UICONTROL Check Syntax]** 不會更新並儲存您的指令碼。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參 [閱配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可選）在頁 [!DNL Filtering Script] 面上，執行下列任一項作業：

   * 按一 **[!UICONTROL History]** 下以回復您所做的任何變更。

      請參 [閱使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。

## 關於初始化指令碼 {#concept_048B4C8BC9F74BE8BB6162C490C201A3}

您可以使 [!DNL Initialization Script] 用更改Web文檔的內容，然後對其進行索引。

您可以插入HTML標籤、移除不相關的內容，甚至根據檔案的URL、MIME類型和現有內容建立新的HTML中繼資料。 初始化指令碼是Perl指令碼，它提供了強大的字串處理和規則運算式匹配的靈活性。 您可將初始化指令碼與篩選指令碼、終止指令碼、URL遮色片指令碼和測試URL搭配使用。

初始化指令碼在索引開始之前運行一次。 使用此指令碼可初始化篩選指令碼使用的所有全局變數和子常式。 您可以使用初始化指令碼將狀態消息從篩選指令碼打印到索引日誌。 您可以將消息打印到STDERR，也可以通過子常式 `_search_debug_log()` 打印。

在「分段初始化指令碼」頁的模 **[!UICONTROL Expert (diff)]** 式下可使用的某些GNU比較選項包括：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>GNUdiff選項 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -b </span> </p> </td> 
   <td colname="col2"> <p> 忽略空格量的變更。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -B </span> </p> </td> 
   <td colname="col2"> <p> 忽略插入或刪除空行的更改。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -c </span> </p> </td> 
   <td colname="col2"> <p> 使用上下文輸出格式，顯示三行上下文。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -C行 </span> </p> </td> 
   <td colname="col2"> <p> 使用上下文輸出格式，顯示上下文的行（整數），如果未指定行，則使用三行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -i </span> </p> </td> 
   <td colname="col2"> <p> 忽略大小寫更改；請考慮等同大寫和小寫字母。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -f </span> </p> </td> 
   <td colname="col2"> <p> 使輸出看起來類似於編輯指令碼，但更改了它們在檔案中的顯示順序。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -n </span> </p> </td> 
   <td colname="col2"> <p> 輸出RCS格式差；例 <span class="codeph"> 如-f </span> ，但每個命令都指定受影響的行數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>-u </p> </td> 
   <td colname="col2"> <p> 使用統一的輸出格式，顯示三行上下文。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -U線 </span> </p> </td> 
   <td colname="col2"> <p> 使用統一的輸出格式，顯示上下文的行（整數），如果未指定行，則使用三行。 </p> </td> 
  </tr> 
 </tbody> 
</table>

您可以在這些指令碼中使用局部變數、全域變數或兩者。 所有全域變數都會以命名空間&quot;main::&quot;為前置詞。 啟動初始化指令碼時，其環境包含以下標準檔案句柄：

* STDIN —— 無（讀取時立即返回EOF）
* STDOUT —— 無值（如果資料打印到STDOUT，則會被丟棄）
* STDERR —— 打印到STDERR的資料打印到索引日誌中是錯誤

此外，您還可以使用子常式將自定義消息寫入 `_search_debug_log()` 索引日誌，如下例所示：

```
# Log information to the Index Log 
_search_debug_log("Done processing document: " . $main::search_url);
```

這些消息以前面的單 `DEBUG` 字顯示，不會記錄為錯誤。

初始化指令碼的示例如下：

```
# My subroutine to do something. 
sub my_sub_for_the_filtering_script { 
    my ($param1, $param2) = @_; 
    ... 
} 
 
# Initialize the document counter. 
$main::doc_count = 0;
```

請參閱 [全域變數](#global-variables)

### 快速提示 {#section_A2CC0302CAF14135BF8EF6171FB184F1}

* 所有全域變數都會以命名空間&quot;main::&quot;為前置詞： `$main::doc_count = 0;`
* 所有局部變數都以&quot;my&quot;宣告： `my $i = 0;`
* 子常式在初始化指令碼中定義。 他們不需要明確的「main::」命名空間： `sub my_sub {`  `...`

   `}`

* 在對文 `$main::search_content_type` 件進行更改之前測試。 測試可協助您避免對二進位檔案（例如SWF檔案或PDF檔案）進行粗心變更：

   `if ($main::search_content_type =~ /^text\/html/) { ...`

* 您 `$main::search_content_type` 的伺服器傳送的完整內容類型標題。 它有時可包含簡單的MIME類型，例如&quot;text/html&quot;。 或者，它可以包含MIME類型，後面跟有其他資訊，如文檔的字元集編碼，如「text/html;charset=iso-8859-1」。
* 對於每種非HTML檔案類型，都可 `$main::search_content_type` 以使用各種值。 測試指令碼中的每個值會變得麻煩。 例如，某些Word檔案的內容類型值為&quot;application/msword&quot;、&quot;application/vnd.ms-word&quot;或&quot;application/x-msword&quot;。 在這種情況下， `$main::search_content_class` 可以採用下列值：

   * html
   * pdf
   * 詞
   * excel
   * powerpoint
   * mp3
   * text

* 在範例中，測 `$main::search_content_class` 試&quot;word&quot;會比對三種可能的內容類型值。
* 如果從篩選指令碼中沒有列印到STDOUT，則檔案會與下載的檔案完全相同。 也就是說，如果您不需要變更檔案中的任何項目，則不需要將該檔案的STDIN複製至STDOUT。
* 如果要從文檔中刪除所有文本，請打印有效的檔案STDOUT。 例如，要完全刪除HTML文檔中的所有文本，請執行以下操作： `print "<html></html>";`

## 添加初始化指令碼 {#task_5A03B8D0C46E4674B7CE88203515803B}

初始化指令碼是Perl指令碼，在對任何文檔編製索引之前運行一次。

您可將初始化指令碼與篩選指令碼、終止指令碼和URL遮色片指令碼搭配使用。

請確定您重建網站索引，以便客戶能夠看到初始化指令碼的結果。

請參 [閱配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**添加初始化指令碼**

1. 在產品功能表上，按一下 **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Initialization Script]**。
1. （可選）在頁 [!DNL Initialization Script] 面的欄位 [!DNL Test URL] 中，輸入網站上檔案的URL。

   按一下測試選項，查看原始HTML文字的變更。

   請參閱「新增篩選指令碼」 **下方的篩選選項表格**。

   按一 **[!UICONTROL Test]** 下以測試篩選指令碼和URL遮色片。

   按一下 **[!UICONTROL Test]** 不更新並保存初始化指令碼。
1. 在欄位 [!DNL Initialization Script] 中，貼上您的指令碼。
1. （可選）按一 **[!UICONTROL Check Syntax]** 下，執行篩選、初始化和終止指令碼，以快速檢查指令碼的語法。

   **[!UICONTROL Check Syntax]** 不會更新並儲存您的指令碼。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參 [閱配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可選）在頁 [!DNL Initialization Script] 面上，執行下列任一項作業：

   * 按一 **[!UICONTROL History]** 下以回復您所做的任何變更。

      請參 [閱使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。

## 關於終止指令碼 {#concept_AAD6B3B0E7124874AD0947096FC42F47}

您可以使 [!DNL Termination Script] 用更改Web文檔的內容，然後對其進行索引。

您可以插入HTML標籤、移除不相關的內容，甚至根據檔案的URL、MIME類型和現有內容建立新的HTML中繼資料。 初始化指令碼是Perl指令碼，它提供了強大的字串處理和規則運算式匹配的靈活性。 您可將終止指令碼與初始化指令碼、篩選指令碼、終止指令碼、URL掩碼指令碼和測試URL一起使用。

在所有文檔編製索引後，終止指令碼將運行一次。 您可以使用終止指令碼將狀態消息從過濾指令碼打印到索引日誌。 您可以將消息打印到STDERR，也可以通過子常式 `_search_debug_log()` 打印。

在「分段終止指令碼」頁的模式下可 **[!UICONTROL Expert (diff)]** 以使用的某些GNU diff命令行選項包括：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>GNU diff命令行選項 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -b </span> </p> </td> 
   <td colname="col2"> <p> 忽略空格量的變更。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -B </span> </p> </td> 
   <td colname="col2"> <p> 忽略插入或刪除空行的更改。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -c </span> </p> </td> 
   <td colname="col2"> <p> 使用上下文輸出格式，顯示三行上下文。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -C行 </span> </p> </td> 
   <td colname="col2"> <p> 使用上下文輸出格式，顯示上下文的行（整數），如果未指定行，則使用三行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -i </span> </p> </td> 
   <td colname="col2"> <p> 忽略大小寫更改；請考慮等同大寫和小寫字母。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -f </span> </p> </td> 
   <td colname="col2"> <p> 使輸出看起來類似於編輯指令碼，但更改了它們在檔案中的顯示順序。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -n </span> </p> </td> 
   <td colname="col2"> <p> 輸出RCS格式差；例 <span class="codeph"> 如-f </span> ，但每個命令都指定受影響的行數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>-u </p> </td> 
   <td colname="col2"> <p> 使用統一的輸出格式，顯示三行上下文。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -U線 </span> </p> </td> 
   <td colname="col2"> <p> 使用統一的輸出格式，顯示上下文的行（整數），如果未指定行，則使用三行。 </p> </td> 
  </tr> 
 </tbody> 
</table>

您可以在這些指令碼中使用局部變數、全域變數或兩者。 所有全域變數都會以命名空間&quot;main::&quot;為前置詞。 啟動終止指令碼時，其環境包含以下標準檔案句柄：

* STDIN —— 無（讀取時立即返回EOF）
* STDOUT —— 無值（如果資料打印到STDOUT，則會被丟棄）
* STDERR —— 打印到STDERR的資料打印到索引日誌中是錯誤

此外，您還可以使用子常式將自定義消息寫入 `_search_debug_log()` 索引日誌，如下例所示：

```
# Log information to the Index Log 
_search_debug_log("Done processing document: " . $main::search_url);
```

這些消息以前面的單 `DEBUG` 字顯示，不會記錄為錯誤。

要在索引日誌中將過濾指令碼處理的文檔數顯示為錯誤行，可以使用以下終止指令碼：

```
# Print the value of the document counter. 
print STDERR "Total docs: $main::doc_count\n"; 
# Or, using the log subroutine: 
_search_debug_log("Total docs: " . $main::doc_count);
```

請參閱 [全域變數](#global-variables)

### 快速提示 {#section_5790EA7ACAC046CBA01F759F88E2460F}

* 所有全域變數都會以命名空間&quot;main::&quot;為前置詞： `$main::doc_count = 0;`
* 所有局部變數都以&quot;my&quot;宣告： `my $i = 0;`
* 子常式在初始化指令碼中定義。 他們不需要明確的「main::」命名空間： `sub my_sub {`  `...`

   `}`

* 在對文 `$main::search_content_type` 件進行更改之前測試。 測試可協助您避免對二進位檔案（例如SWF檔案或PDF檔案）進行粗心變更：

   `if ($main::search_content_type =~ /^text\/html/) { ...`

* 您 `$main::search_content_type` 的伺服器傳送的完整內容類型標題。 它有時可包含簡單的MIME類型，例如&quot;text/html&quot;。 或者，它可以包含MIME類型，後面跟有其他資訊，如文檔的字元集編碼，如「text/html;charset=iso-8859-1」。
* 對於每種非HTML檔案類型，都可 `$main::search_content_type` 以使用各種值。 測試指令碼中的每個值會變得麻煩。 例如，某些Word檔案的內容類型值為&quot;application/msword&quot;、&quot;application/vnd.ms-word&quot;或&quot;application/x-msword&quot;。 在這種情況下， `$main::search_content_class` 可以採用下列值：

   * html
   * pdf
   * 詞
   * excel
   * powerpoint
   * mp3
   * text

* 在範例中，測 `$main::search_content_class` 試&quot;word&quot;會比對三種可能的內容類型值。
* 如果從篩選指令碼中沒有列印到STDOUT，則檔案會與下載的檔案完全相同。 也就是說，如果您不需要變更檔案中的任何項目，則不需要將該檔案的STDIN複製至STDOUT。
* 如果要從文檔中刪除所有文本，請打印有效的檔案STDOUT。 例如，要完全刪除HTML文檔中的所有文本，請執行以下操作： `print "<html></html>";`

## 添加終止指令碼 {#task_F0CFB412871642CFBC88132889C5B6F9}

終止指令碼是Perl指令碼，在所有文檔編製索引後運行一次。

您可將終止指令碼與篩選指令碼、終止指令碼和URL遮色片指令碼搭配使用。

請確定您重建網站索引，以便客戶能夠看到初始化指令碼的結果。

請參 [閱配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**添加終止指令碼**

1. 在產品功能表上，按一下 **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Termination Script]**。
1. （可選）在頁 [!DNL Termination Script] 面的欄位 [!DNL Test URL] 中，輸入網站上檔案的URL。

   按一下測試選項，查看原始HTML文字的變更。

   請參閱「新增篩選指令碼」下 **的篩選選項表格**。

   按一 **[!UICONTROL Test]** 下以測試篩選指令碼和URL遮色片。

   按一下 **[!UICONTROL Test]** 不更新並保存終止指令碼。
1. 在欄位 [!DNL Termination Script] 中，貼上您的指令碼。
1. （可選）按一 **[!UICONTROL Check Syntax]** 下，執行初始化、篩選和終止指令碼，以快速檢查指令碼的語法。

   **[!UICONTROL Check Syntax]** 不會更新並儲存您的指令碼。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參 [閱配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可選）在頁 [!DNL Termination Script] 面上，執行下列任一項作業：

   * 按一 **[!UICONTROL History]** 下以回復您所做的任何變更。

      請參 [閱使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。

## 關於URL遮色片指令碼 {#concept_384F32EA18F84853A7BA99A04009330B}

通過篩選，您可以在對Web文檔編製索引之前更改其內容。 您可以插入HTML標籤、移除不相關的內容，甚至根據檔案的URL、MIME類型和現有內容建立新的HTML中繼資料。 URL遮色片指令碼是Perl指令碼，可提供強大的字串處理功能以及規則運算式比對的彈性。

若要變更僅存在於網站特定部分的檔案內容，您可以指定包含URL遮色片、排除URL遮色片或兩者，以定義適當的頁面。

如果只想更改下面的文檔， `"https://www.mysite.com/faqs/"`則可使用以下一組遮罩：

```
include https://www.mysite.com/faqs/ 
exclude *
```

您也可以在URL遮色片指令碼中使用規則運算式，如下列範例所示：

```
include regexp ^https://www\.mysite\.com.*/faqs/.*$ 
exclude *
```

請參閱 [規則運算式](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A)。

原稿URL遮色片會依您在欄位中輸入的順序加以 [!DNL URL Masks] 考慮。 當檔案URL與遮色片相符時，會根據遮色片類型，包含或排除該檔案。 如果文檔的URL與任何URL掩碼不匹配，則僅當其MIME類型為&quot;text/html&quot;時才包括該文檔。 所有其他MIME類型都被排除。

## 新增URL遮色片指令碼 {#task_D18F2A496C1C45C997B5DA650AAF5D59}

指定URL包含遮色片和排除遮色片，以變更僅存在於網站特定部分的檔案內容。

在訪客看到「URL遮色片」設定的效果之前，請重建您的網站索引。

**若要新增URL遮色片指令碼**

1. 在產品功能表上，按一下 **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL URL Masks]**。
1. （可選）在頁 [!DNL URL Masks] 面的欄位中 [!DNL Test URL] ，輸入網站上檔案的URL，然後按一下 **[!UICONTROL Test]** ，以篩選指令碼和遮色片來測試URL。

   測試URL檔案會下載，並用作篩選指令碼的STDIN輸入。 然後運行篩選、初始化和終止指令碼。 如果過濾指令碼中有任何STDOUT輸出，則輸出將顯示在新的瀏覽器窗口中。

   按一 **[!UICONTROL Test]** 下不會更新並儲存您的指令碼。
1. 在欄位 [!DNL URL Masks] 中，每行輸入一個URL遮色片。
1. （可選）按一 **[!UICONTROL Check Syntax]** 下，執行篩選、初始化和終止指令碼，以快速檢查URL遮色片的語法。

   **[!UICONTROL Check Syntax]** 不會更新並儲存您的指令碼。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參 [閱配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可選）在頁 [!DNL URL Masks] 面上，執行下列任一項作業：

   * 按一 **[!UICONTROL History]** 下以回復您所做的任何變更。

      請參 [閱使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。

## 關於篩選中的內容類型 {#concept_E3EFF4A148EA4D21AFD0A5453A00427E}

可讓您選取要為此帳戶篩選的內容類型。

在選取的內容類型中找到的文字會轉換為HTML，然後使用篩選指令碼中指定的指令碼進行處理。

請參閱 [關於篩選指令碼](../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47)。

您可從中選取的內容類型包括：

* PDF檔案
* 文字檔案
* Adobe Flash影片
* Microsoft Word檔案
* Microsoft Office檔案(OpenXML)
* Microsoft Excel檔案
* Microsoft Powerpoint檔案
* MP3音樂檔案中的文字

客戶必須先重建網站索引，才能看到「內容類型」設定的效果或對設定所做的變更。

## 選取篩選的內容類型 {#task_C46081FA425A43EC8FDE6EA4A52A170A}

選擇您要傳遞至篩選指令碼中指定之指令碼的內容類型。

請參閱 [關於篩選指令碼](../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47)。

**若要選取篩選的內容類型**

1. 在產品功能表上，按一下 **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Content Types]**。
1. 在頁面 [!DNL Content Types] 上，檢查您要傳遞至篩選指令碼的內容類型。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）如果要預覽結果，請重建分段網站索引。

   請參 [閱配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。
1. （可選）在頁 [!DNL Content Types] 面上，執行下列任一項作業：

   * 按一 **[!UICONTROL History]** 下以回復您所做的任何變更。

      請參 [閱使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參 [閱檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參 [閱「即時推送舞台設定](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)」。
