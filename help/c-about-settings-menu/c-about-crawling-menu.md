---
description: 使用「編目」功能表設定日期和URL遮罩、密碼、內容類型、連線、表單定義和URL入口點。
solution: Target
subtopic: Crawling
title: 關於編目功能表
topic-legacy: Settings,Site search and merchandising
uuid: a58c03bf-90f7-4b5b-91ff-988b95c246b0
exl-id: 22dbbc30-bf1c-4d51-8fb0-708115ba844b
source-git-commit: 95bf92df17d7832df72e8d883a22f9063e53a18d
workflow-type: tm+mt
source-wordcount: '11015'
ht-degree: 0%

---

# 關於編目功能表{#about-the-crawling-menu}

使用「編目」功能表設定日期和URL遮罩、密碼、內容類型、連線、表單定義和URL入口點。

## 關於URL入口點 {#concept_5D857E3B5C124E85BC0B5AE77A509573}

大部分網站都有一個主要進入點或首頁，供客戶最初造訪。 此主要入口點是URL地址，搜索自動機從中開始索引搜索。 不過，如果您的網站有多個網域或子網域，或網站的部分並未從主要進入點連結，您可以使用URL進入點來新增更多登入點。

每個指定URL入口點下的所有網站頁面都會編製索引。 您可以結合URL入口點與遮罩，以精確控制您要為網站的哪些部分建立索引。 您必須先重建網站索引，客戶才能看到URL進入點設定的影響。

主要入口點通常是您要索引和搜尋之網站的URL。 您可在「帳戶設定」中設定此主要進入點。

請參閱[配置帳戶設定](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

指定主要URL入口點後，您可以選擇指定要依序編目的其他入口點。 通常，您會為未從主要登入點下的頁面連結的網頁指定其他登入點。 如下列範例所示，當您的網站涵蓋多個網域時，請指定其他登入點：

`https://www.domain.com/`

`https://www.domain.com/not_linked/but_search_me_too/`

`https://more.domain.com/`

在下表中，您可以使用下列一個或多個以空格分隔的關鍵字來限定每個入口點。 這些關鍵字會影響頁面的索引方式。

**重要**:請務必將指定關鍵字與入口點分開，並以空格分隔；逗號不是有效的分隔符號。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>關鍵字 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>noindex </p> </td> 
   <td colname="col2"> <p> 如果您不想為登入點頁面上的文字建立索引，但想要遵循頁面的連結，請新增 
     <code>
       noindex 
     </code>。 </p> <p>將關鍵字與入口點分隔，並加上空格，如下列範例所示： </p> <p> <code> https://www.my-additional-domain.com/more_pages/main.html&amp;nbsp;noindex </code> </p> <p>此關鍵字等同於具有的機器人元標籤 
     <code>
       content="noindex" 
     </code>) 
     <code>
       &lt;head&gt; 
     </code>.. 
     登入點頁面的<code>
       &lt;/head&gt; 
     </code>標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>no追隨 </p> </td> 
   <td colname="col2"> <p> 如果要為登入點頁面中的文字建立索引，但不想遵循頁面的任何連結，請新增 
     <code>
       nofollow 
     </code>。 </p> <p>將關鍵字與入口點分隔，並加上空格，如下列範例所示： </p> <p> <code> https://www.domain.com/not_linked/directory_listing&amp;nbsp;nofollow </code> </p> <p>此關鍵字等同於具有的機器人元標籤 
     <code>
       content="nofollow" 
     </code> 
     <code>
       &lt;head&gt; 
     </code>.. 
     登入點頁面的<code>
       &lt;/head&gt; 
     </code>標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>表單 </p> </td> 
   <td colname="col2"> <p> 當登入點為登入頁面時， 
     <code>
       form 
     </code>通常使用，以便搜尋機器人在對網站進行編目之前，能提交登入表單並接收適當的cookie。 使用"form"關鍵字時，入口點頁面沒有索引，而搜尋機器人不會將入口點頁面標示為已編目。 使用 
     <code>
       nofollow 
     </code>如果您不希望搜尋機器人遵循頁面的連結。 </p> </td> 
  </tr> 
 </tbody> 
</table>

另請參閱[關於內容類型](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07)。

另請參閱[關於索引連接器](../c-about-settings-menu/c-about-crawling-menu.md#concept_CA6921E2FBF641F9B4F60C92B32AFA84)。

## 新增多個要建立索引的URL登入點 {#task_2338A47387D74CFDAC4D4EF4A367ED45}

如果您的網站有多個網域或子網域，而您想要進行編目，則可使用URL進入點來新增更多URL。

若要設定網站的主要URL進入點，請使用「帳戶設定」。

請參閱[配置帳戶設定](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

**要添加要編製索引的多個URL入口點**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**」。
1. 在[!DNL URL Entrypoints]頁面的[!DNL Entrypoints]欄位中，每行輸入一個URL地址。
1. （可選）在&#x200B;**[!UICONTROL Add Index Connector Configurations]**&#x200B;下拉清單中，選擇要添加作為索引入口點的索引連接器。

   只有在您先前已新增一或多個索引連接器定義時，下拉式清單才可用。

   ![](assets/url_entrypoints_index_connector.png)

   請參閱[添加索引連接器定義](../c-about-settings-menu/c-about-crawling-menu.md#task_96779B651A654E1F871F55D6DBBC8886)。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （選用）執行下列任一操作：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以還原您所做的任何更改。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送階段設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 關於URL遮罩 {#concept_8039DFC53FF3410AA494D602F71BA164}

URL遮罩是決定哪些網站記錄搜尋自動機索引或非索引的模式。

請務必重建網站索引，讓客戶可看到URL遮罩的結果。

請參閱[配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

以下是您可使用的兩種URL遮罩：

* 包含URL遮罩
* 排除URL遮罩

包括URL掩碼指示搜索自動機為匹配掩碼模式的任何文檔建立索引。

排除URL遮罩會指示搜尋自動機為相符的檔案建立索引。

當搜尋機器人從連結經由您的網站連結時，它會遇到URL並尋找符合這些URL的遮罩。 第一個相符項目會決定要將該URL納入索引，還是從索引中排除。 如果沒有任何遮罩符合遇到的URL，則會從索引中捨棄該URL。

系統會自動產生入口點URL的包含URL遮罩。 此行為可確保對您網站上遇到的所有檔案建立索引。 此外，它還可方便地移除「離開」您網站的連結。 例如，如果索引頁面連結到https://www.yahoo.com，則搜索自動機不會為該URL建立索引，因為它與入口點URL自動生成的包含掩碼不匹配。

您指定的每個URL遮色片都必須位在一行上。

遮罩可指定下列任一項：

* `https://www.mydomain.com/products.html`中的完整路徑。
* `https://www.mydomain.com/products`中的部分路徑。
* 使用萬用字元的URL，如`https://www.mydomain.com/*.html`中。
* 規則運算式（適用於進階使用者）。

   要使掩碼成為規則表達式，請在掩碼類型（`exclude`或`include`）和URL掩碼之間插入關鍵字`regexp`。

以下是簡單的排除URL遮罩範例：

```
exclude https://www.mydomain.com/photos
```

由於此示例是排除URL掩碼，因此任何匹配該模式的文檔都不會編製索引。 此模式與遇到的任何項目（包括檔案和資料夾）相匹配，因此`https://www.mydomain.com/photos.html`和`https://www.mydomain.com/photos/index.html`（兩者均與排除URL相匹配）不會建立索引。 若要僅比對`/photos/`資料夾中的檔案，URL遮罩必須包含尾隨斜線，如下列範例所示：

```
exclude https://www.mydomain.com/photos/
```

下列排除遮罩範例使用萬用字元。 它會告訴搜尋自動機忽略副檔名為「.pdf」的檔案。 搜索自動機不會將這些檔案添加到索引中。

```
exclude *.pdf
```

簡單的包含URL遮罩如下：

```
include https://www.mydomain.com/news/
```

只有以URL入口點的一系列連結連結連結的檔案，或本身作為URL入口點使用的檔案，才會編製索引。 僅將文檔的URL列為包含URL掩碼時，不會為未連結的文檔建立索引。 若要將未連結的文檔添加到索引中，可以使用URL入口點功能。

請參閱[關於URL入口點](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

包含遮罩和排除遮罩可共同運作。 您可以建立排除URL遮罩，但同時包含一或多個具有包含URL遮罩的已排除頁面，以排除網站的大部分，使其無法建立索引。 例如，假設您的入口點URL如下：

```
https://www.mydomain.com/photos/
```

搜索自動機對`/photos/summer/`、`/photos/spring/`和`/photos/fall/`下的所有頁面進行編目和索引（假設每個目錄中的`photos`資料夾中至少有一個頁面的連結）。 發生此行為是因為連結路徑使搜索自動機能夠查找`/summer/`、`/spring/`和`/fall/`中的文檔、資料夾和資料夾URL與入口點URL自動生成的包含掩碼匹配。

您可以選擇排除`/fall/`資料夾中所有具有排除URL遮罩的頁面，如下列範例所示：

```
exclude https://www.mydomain.com/photos/fall/
```

或者，只選擇性地將`/photos/fall/redleaves4.html`包含在具有以下URL掩碼的索引中：

```
include https://www.mydomain.com/photos/fall/redleaves4.html
```

為了讓上述兩個遮色片範例如預期般運作，會先列出包含遮色片，如下所示：

```
include https://www.mydomain.com/photos/fall/redleaves4.html 
exclude https://www.mydomain.com/photos/fall/
```

由於搜索自動機按照它們所列的順序執行指令，因此搜索自動機首先包括`/photos/fall/redleaves4.html`，然後排除`/fall`資料夾中的其餘檔案。

如果以相反的方式指定指令，如下所示：

```
exclude https://www.mydomain.com/photos/fall/ 
include https://www.mydomain.com/photos/fall/redleaves4.html
```

然後不包括`/photos/fall/redleaves4.html`，即使掩碼指定包括它。

首先出現的URL遮色片一律優先於稍後出現在遮色片設定中的URL遮色片。 此外，如果搜索自動機遇到的頁面與包含URL掩碼和排除URL掩碼匹配，則首先列出的掩碼始終優先。

請參閱[配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

## 關於使用關鍵字與URL遮罩 {#section_7609A7A6D79B482ABCA8900886541AAB}

您可以使用一或多個空格分隔的關鍵字來限定每個包含掩碼，這些關鍵字會影響匹配頁面的索引方式。

逗號在遮罩和關鍵字之間作為分隔符無效；您只能使用空格。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>關鍵字 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>noindex </p> </td> 
   <td colname="col2"> <p> 如果您不想為符合URL遮色片的頁面上的文字建立索引，但想要遵循相符的頁面連結，請新增 
     <code>
       noindex 
     </code>。 請務必將關鍵字與遮色片分開，並加上空格，如下列範例所示： </p> <p> <code> include&amp;nbsp;*.swf&amp;nbsp;noindex </code> </p> <p>上例指定搜索自動機會遵循檔案中的所有連結，其中 
     <code>
       .swf 
     </code>擴充功能，但禁用對這些檔案中包含的所有文本的索引。 </p> <p>此 
     <code>
       noindex 
     </code>關鍵字等同於具有的機器人元標籤 
     <code>
       content="noindex" 
     </code> 
     <code>
       &lt;head&gt;...&lt;/head&gt; 
     </code>相符頁面的標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>no追隨 </p> </td> 
   <td colname="col2"> <p> 如果您想要為符合URL遮色片的頁面上的文字建立索引，但不想遵循相符頁面的連結，請新增 
     <code>
       nofollow 
     </code>。 請務必將關鍵字與遮色片分開，並加上空格，如下列範例所示： </p> <p> <code> include&amp;nbsp;https://www.mydomain.com/photos&amp;nbsp;nofollow </code> </p> <p>此 
     <code>
       nofollow 
     </code>關鍵字等同於具有的機器人元標籤 
     <code>
       content="nofollow" 
     </code> 
     <code>
       &lt;head&gt;...&lt;/head&gt; 
     </code>相符頁面的標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>regexp </p> </td> 
   <td colname="col2"> <p>用於包含和排除遮罩。 </p> <p>任何URL遮色片前面都有 
     <code>
       regexp 
     </code>被視為規則運算式。 如果搜索自動機遇到與排除規則表達式URL掩碼匹配的文檔，則這些文檔不會編入索引。 如果搜索自動機遇到的文檔與包含規則表達式URL掩碼匹配，則這些文檔將被編入索引。 例如，假設您有下列URL遮罩： </p> <p> <code> exclude&amp;nbsp;regexp&amp;nbsp;^.*/products/.*\.html$ </code> </p> <p>搜索自動機會排除匹配檔案，例如 
     <code>
       https://www.mydomain.com/products/page1.html 
     </code> </p> <p>如果您有下列排除規則運算式URL遮罩： </p> <p> <code> exclude&amp;nbsp;regexp&amp;nbsp;^.*\?..*$ </code> </p> <p>搜尋自動機不會包含任何包含CGI參數的URL，例如 
     <code>
       https://www.mydomain.com/cgi/prog/?arg1=val1&amp;arg2=val2 
     </code>。 </p> <p>如果您有下列包含規則運算式URL遮罩： </p> <p> <code> include&amp;nbsp;regexp&amp;nbsp;^.*\.swf$&amp;nbsp;noindex </code> </p> <p>搜索自動機將跟蹤副檔名為"。swf"的檔案中的所有連結。 此 
     <code>
       noindex 
     </code>關鍵字還指定匹配檔案的文本未編入索引。 </p> <p>請參閱<a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local">規則運算式</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 新增URL遮罩以索引或不是網站的索引部分 {#task_E1AFC17C746048B8843013D979E082C1}

您可以使用[!DNL URL Masks]來定義要或不要對網站的哪些部分進行編目和索引。

使用「測試URL掩碼」欄位來測試索引後是否包含文檔。

請務必重建網站索引，讓客戶可看到URL遮罩的結果。

請參閱[配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**若要新增URL遮罩至網站的索引部分或非索引部分**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]**」。
1. （可選）在[!DNL URL Masks]頁面的&#x200B;**[!UICONTROL Test URL Masks]**&#x200B;欄位中，輸入網站的測試URL遮罩，然後按一下&#x200B;**[!UICONTROL Test]**。
1. 在[!DNL URL Masks]欄位中，鍵入`include`（以添加要爬網和索引的網站），或鍵入`exclude`（以阻止網站被爬網和索引），然後鍵入URL掩碼地址。

   每行輸入一個URL掩碼地址。 範例:  

   ```
   include https://www.mycompany.com/summer 
   include https://www.mycompany.com/spring 
   exclude regexp .*\.xml 
   exclude https://www.mycompany.com/fall
   ```

1. 按一下 **[!UICONTROL Save Changes]**.
1. （選用）執行下列任一操作：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以還原您所做的任何更改。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送階段設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 關於日期遮色片 {#concept_F4F1F58A646F4A86B8650EC46FDCEF66}

您可以根據檔案的年齡，使用「日期遮罩」來包含或排除搜尋結果中的檔案。

請務必重建網站索引，讓客戶可看到URL遮罩的結果。

請參閱[配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

以下是兩種日期遮色片可供使用：

* 包含日期遮罩（「include-days」和「include-date」）

   包含日期在指定日期或之前的日期掩碼索引檔案。
* 排除日期遮罩（「exclude-days」和「exclude-date」）

   排除日期在指定日期或之前的日期遮罩索引檔案。

依預設，檔案日期是由中繼標籤資訊決定。 如果未找到元標籤，則從搜索自動機下載檔案時從伺服器接收的HTTP標頭確定檔案的日期。

您指定的每個日期遮色片都必須位於單獨的一行。

遮罩可指定下列任一項：

* `https://www.mydomain.com/products.html`中的完整路徑
* `https://www.mydomain.com/products`中的部分路徑
* 使用萬用字元`https://www.mydomain.com/*.html`的URL
* 規則運算式。 若要將遮罩設為規則運算式，請在URL前面插入關鍵字`regexp`。

包含和排除日期遮罩都可透過下列兩種方式之一指定日期。 僅當在指定日期或之前建立了匹配的檔案時，才應用掩碼：

1. 幾天。 例如，假設您的日期遮色片如下：

   ```
   exclude-days 30 https://www.mydomain.com/docs/archive/)
   ```

   返回指定天數。 如果檔案的日期是到達日期之前或之後，則會套用遮罩。

1. 使用YYYY-MM-DD格式的實際日期。 例如，假設您的日期遮色片如下：

   ```
   include-date 2011-02-15 https://www.mydomain.com/docs/archive/)
   ```

   如果匹配的文檔日期在指定日期或之前，則應用日期掩碼。

以下是簡單的排除日期遮罩範例：

```
exclude-days 90 https://www.mydomain.com/docs/archive
```

因為這是排除日期遮罩，任何符合模式的檔案都不會建立索引，且會保留90天或更舊。 排除文檔時，不會對任何文本編製索引，也不會從該檔案中跟隨任何連結。 會有效忽略檔案。 在此範例中，檔案和資料夾都可能符合指定的URL模式。 請注意，`https://www.mydomain.com/docs/archive.html`和`https://www.mydomain.com/docs/archive/index.html`都符合模式，且如果90天或更舊，則未編列索引。 若要僅比對`/docs/archive/`資料夾中的檔案，日期遮罩必須包含尾隨斜線，如下所示：

```
exclude-days 90 https://www.mydomain.com/docs/archive/
```

日期遮色片也可搭配萬用字元使用。 下列排除遮罩會告訴搜尋自動機忽略副檔名為&quot;。pdf&quot;的檔案，這些檔案日期為2011-02-15年或之前。 搜索自動機不會向索引添加任何匹配的檔案。

```
exclude-date 2011-02-15 *.pdf
```

包含日期遮罩看起來類似，只有相符的檔案會新增至索引。 以下包含日期掩碼示例告訴搜索自動機從網站`/docs/archive/manual/`區域中任何存在零天或更舊的檔案中索引文本。

```
include-days 0 https://www.mydomain.com/docs/archive/manual/
```

包含遮罩和排除遮罩可共同運作。 例如，您可以建立排除日期遮色片，但同時包含一或多個具有包含URL遮色片的已排除頁面，借此排除大部分網站的索引不。 如果您的入口點URL如下：

```
https://www.mydomain.com/archive/
```

搜索自動機對`/archive/summer/`、`/archive/spring/`和`/archive/fall/`下的所有頁面進行編目和索引（假設每個資料夾中的`archive`資料夾中至少有一個頁面的連結）。 發生此行為是因為連結路徑使搜索自動機能夠「查找」`/summer/`、`/spring/`和`/fall/`資料夾中的檔案，並且資料夾URL與入口點URL自動生成的包含掩碼匹配。

請參閱[關於URL入口點](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

請參閱[配置帳戶設定](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9)。

您可以選擇在`/fall/`資料夾中排除90天以上的所有頁面，並搭配排除日期遮罩，如下所示：

```
exclude-days 90 https://www.mydomain.com/archive/fall/
```

您可以選擇性地僅包含`/archive/fall/index.html`（無論其存在的時間 — 任何0天或更舊的檔案都匹配），作為具有以下日期掩碼的索引的一部分：

```
include-days 0 https://www.mydomain.com/archive/fall/index.html
```

為了讓上述兩個遮色片範例如預期般運作，您必須先將包含遮色片列在下列：

```
include-days 0 https://www.mydomain.com/archive/fall/index.html 
exclude-days 90 https://www.mydomain.com/archive/fall/
```

由於搜索自動機按照指定的順序執行指令，因此搜索自動機首先包括`/archive/fall/index.html`，然後排除`/fall`資料夾中的其餘檔案。

如果以相反的方式指定指令，如下所示：

```
exclude-days 90 https://www.mydomain.com/archive/fall/ 
include-days 0 https://www.mydomain.com/archive/fall/index.html 
```

然後不包含`/archive/fall/index.html`，即使掩碼指定它應該包含。 先出現的日期遮色片一律優先於稍後可能出現在遮色片設定中的日期遮色片。 此外，如果搜索自動機遇到的頁面既匹配了包含日期掩碼又匹配了排除日期掩碼，則首先列出的掩碼始終優先。

請參閱[配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

## 關於使用關鍵字與日期遮罩 {#section_CCBB3E3FDBDE4725B2B571FD6594470C}

您可以使用一或多個空格分隔的關鍵字來限定每個包含掩碼，這些關鍵字會影響匹配頁面的索引方式。

逗號在遮罩和關鍵字之間作為分隔符無效；您只能使用空格。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>關鍵字 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>noindex </p> </td> 
   <td colname="col2"> <p> 如果您不想在包含遮色片指定的日期或之前，為頁面上的文字建立索引，請新增 
     <code>
       noindex 
     </code>之後包含日期遮色片，如下所示： </p> <p> <code> include-days&amp;nbsp;10&amp;nbsp;*.swf&amp;nbsp;noindex </code> </p> <p>請務必將關鍵字與遮色片分開，並加上空格。 </p> <p>上例指定搜索自動機遵循副檔名為「.swf」（10天或更舊）的檔案中的所有連結。 但是，它禁用對這些檔案中包含的所有文本的索引。 </p> <p>您可能希望確保未對舊檔案的文本編製索引，但仍遵循這些檔案的所有連結。 在這種情況下，請使用包含日期遮色片搭配「noindex」關鍵字，而非使用排除日期遮色片。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>no追隨 </p> </td> 
   <td colname="col2"> <p> 如果要為日期在包含遮罩指定之日期或之前的頁面上的文字建立索引，但您不想遵循相符頁面的連結，請新增 
     <code>
       nofollow 
     </code>之後包含日期遮色片，如下所示： </p> <p> <code> include-days&amp;nbsp;8&amp;nbsp;https://www.mydomain.com/photos&amp;nbsp;nofollow </code> </p> <p>請務必將關鍵字與遮色片分開，並加上空格。 </p> <p>此 
     <code>
       nofollow 
     </code>關鍵字等同於具有的機器人元標籤 
     <code>
       content="nofollow" 
     </code> 
     <code>
       &lt;head&gt;...&lt;/head&gt; 
     </code>標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>server-date </p> </td> 
   <td colname="col2"> <p>用於包含和排除遮罩。 </p> <p>搜索自動機通常在檢查日期掩碼之前下載並分析每個檔案。 發生此行為是因為某些檔案類型可以在檔案本身內指定日期。 例如，HTML檔案可以包含設定檔案日期的中繼標籤。 </p> <p>如果您要根據檔案的日期排除許多檔案，而您不想在伺服器上造成不必要的負載，則可使用 
     <code>
       server-date 
     </code>。 </p> <p>此關鍵字指示搜索機器人信任伺服器返回的檔案的日期，而不是解析每個檔案。 例如，如果檔案是90天或更舊，則下列排除日期遮罩會根據伺服器在HTTP標題中傳回的日期，忽略與URL相符的頁面： </p> <p> <code> exclude-days&amp;nbsp;90&amp;nbsp;https://www.mydomain.com/docs/archive&amp;nbsp;server-date </code> </p> <p> 如果伺服器傳回的日期是90天或更久以前， 
     <code>
       server-date 
     </code>指定不從伺服器下載排除的文檔。 這意味著，您的文檔的索引時間會更快，伺服器上的負載也會降低。 若 
     未指定<code>
       server-date 
     </code>，搜索自動機將忽略伺服器在HTTP標題中返回的日期。 而是會下載並檢查每個檔案，以查看是否指定日期。 如果未在檔案中指定日期，則搜索自動機將使用伺服器返回的日期。 </p> <p>您不應使用 
     <code>
       server-date 
     </code>如果您的檔案包含覆蓋伺服器日期的命令。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>regexp </p> </td> 
   <td colname="col2"> <p> 同時用於包含和排除遮罩。 </p> <p>前面有的任何日期遮色片 
     <code>
       regexp 
     </code>被視為規則運算式。 </p> <p>如果搜索自動機遇到的檔案與排除規則運算式日期掩碼匹配，則不會為這些檔案建立索引。 </p> <p>如果搜索自動機遇到與包含規則表達式日期掩碼匹配的檔案，則會為這些文檔建立索引。 </p> <p>例如，假設您有下列日期遮色片： </p> <p> <code> exclude-days&amp;nbsp;180&amp;nbsp;regexp&amp;nbsp;.*archive.* </code> </p> <p>遮罩會告訴搜尋自動機排除180天或更舊的相符檔案。 即URL中包含「封存」一字的檔案。 </p> <p>請參閱<a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local">規則運算式</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 新增日期遮罩以索引或不為網站的某些部分建立索引 {#task_0010543C55F648D2B5DEFEFAD60FAF04}

您可以使用「日期遮罩」，根據檔案的年齡，在客戶搜尋結果中包含或排除檔案。

使用&#x200B;**[!UICONTROL Test Date]**&#x200B;和&#x200B;**[!UICONTROL Test URL]**&#x200B;欄位來測試索引後是否包含檔案。

請務必重建網站索引，讓客戶可看到URL遮罩的結果。

請參閱[配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**若要將日期遮罩新增至網站的索引，或不要為網站的索引部分新增**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Date Masks]**」。
1. （可選）在[!DNL Date Masks]頁面的&#x200B;**[!UICONTROL Test Date]**&#x200B;欄位中，輸入格式為YYYY-MM-DD的日期（例如`2011-07-25`）;在&#x200B;**[!UICONTROL Test URL]**&#x200B;欄位中，輸入網站的URL遮罩，然後按一下&#x200B;**[!UICONTROL Test]**。
1. 在[!DNL Date Masks]欄位中，為每行輸入一個日期掩碼地址。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （選用）執行下列任一操作：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以還原您所做的任何更改。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送階段設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 關於密碼 {#concept_3EDBD731725D46B891F834D4472774DC}

若要存取受HTTP基本驗證保護的網站部分，您可以新增一或多個密碼。

在客戶看到密碼設定的效果之前，您必須重建網站索引。

請參閱[配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

在[!DNL Passwords]頁面上，按一行鍵入每個密碼。 密碼由URL或領域、用戶名和密碼組成，如以下示例所示：

```
https://www.mydomain.com/ myname mypassword
```

您也可以指定領域，而不是使用URL路徑（如上所示）。

要確定要使用的正確領域，請使用瀏覽器開啟受密碼保護的網頁，然後查看「輸入網路密碼」對話框。

![](assets/realms.gif)

領域名稱，在此例中為「我的網站領域」。

使用上述領域名稱，您的密碼可能如下所示：

```
My Site Realm myusername mypassword
```

如果您的網站有多個領域，您可以像以下示例一樣，在單獨的一行中輸入每個領域的用戶名和密碼，以建立多個密碼：

```
Realm1 name1 password1 
Realm2 name2 password2 
Realm3 name3 password3
```

您可以混合包含URL或領域的密碼，使您的密碼清單看起來可能如下所示：

```
Realm1 name1 password1 
https://www.mysite.com/path1/path2 name2 password2 
Realm3 name3 password3 
Realm4 name4 password4 
https://www.mysite.com/path1/path5 name5 password5 
https://www.mysite.com/path6 name6 password6
```

在上面的清單中，使用的第一個密碼包含符合伺服器驗證請求的領域或URL。 即使`https://www.mysite.com/path1/path2/index.html`處的檔案位於`Realm3`中，例如`name2`和`password2`也被使用，因為與URL定義的密碼列在與領域定義的密碼的上方。

## 新增密碼以存取需要驗證的網站區域 {#task_DED19D476FF04B48BB6456D5ECB8628A}

您可以使用密碼來訪問網站中受密碼保護的區域，以便進行編目和建立索引。

在客戶看到密碼添加的效果之前，請務必重建網站索引

請參閱[配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**新增密碼以存取需要驗證的網站區域**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Passwords]**」。
1. 在[!DNL Passwords]頁的&#x200B;**[!UICONTROL Passwords]**&#x200B;欄位中，輸入領域或URL及其關聯的用戶名和密碼，用空格分隔。

   不同行上的領域密碼和URL密碼的示例：

   ```
   Realm1 name1 password1 
   https://www.mysite.com/path1/path2 name2 password2
   ```

   每行僅添加一個密碼。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （選用）執行下列任一操作：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以還原您所做的任何更改。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送階段設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 關於內容類型 {#concept_6FEA1355C0374500B4C53090C34A8A07}

可以使用[!DNL Content Types]選擇要對此帳戶進行編目和索引的檔案類型。

您可以選擇進行編目和索引的內容類型包括PDF文檔、文本文檔、AdobeFlash電影、來自Microsoft Office應用程式（如Word、Excel和Powerpoint）的檔案，以及MP3檔案中的文本。 在選取的內容類型中找到的文字會與您網站上的所有其他文字一起搜尋。

在客戶看到「內容類型」設定的效果之前，您必須重建網站索引。

請參閱[配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

## 關於索引MP3音樂檔案 {#section_AD2E28BEEE3E46629E2B05C34A963673}

如果在[!DNL Content Types]頁面上選擇選項&#x200B;**[!UICONTROL Text in MP3 Music Files]**，則會以兩種方式之一對MP3檔案進行爬網和索引。 第一種也是最常見的方式來自HTML檔案中的錨點href標籤，如下所示：

```
<a href="MP3-file-URL"></a>
```

第二種方式是輸入MP3檔案的URL作為URL入口點。

請參閱[關於URL入口點](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

MP3檔案的MIME類型為&quot;audio/mpeg&quot;。

請注意，MP3音樂檔案的大小可能非常大，即使它們通常只包含少量文本。 例如，MP3檔案可以選擇儲存相簿名稱、藝術家名稱、歌曲標題、歌曲類型、發行年份和注釋等。 此資訊會儲存在檔案的結尾處，即所謂的TAG。 包含TAG資訊的MP3檔案的索引方式如下：

* 歌曲標題視為HTML頁面的標題。
* 註解的處理方式與為HTML頁面定義的說明相同。
* 類型視為為HTML頁面定義的關鍵字。
* 藝人名稱、相簿名稱和發行年份視為HTML頁面的內文。

請注意，網站上所編目和編列索引的每個MP3檔案都計為一頁。

如果您的網站包含許多大型MP3檔案，則可能超過帳戶的索引位元組限制。 如果發生此情況，您可以取消選取[!DNL Content Types]頁面上的&#x200B;**[!UICONTROL Text in MP3 Music Files]**，以防止對網站上的所有MP3檔案進行索引。

如果您只想阻止網站上某些MP3檔案的索引，可以執行下列操作之一：

* 以`<nofollow>`和`</nofollow>`標籤環繞連結至MP3檔案的錨記。 搜尋自動機不會遵循這些標籤之間的連結。

* 將MP3檔案的URL新增為排除遮罩。

   請參閱[關於URL遮罩](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164)。

## 選擇要爬網和索引的內容類型 {#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8}

可以使用[!DNL Content Types]選擇要對此帳戶進行編目和索引的檔案類型。

您可以選擇進行編目和索引的內容類型包括PDF文檔、文本文檔、AdobeFlash電影、來自Microsoft Office應用程式（如Word、Excel和Powerpoint）的檔案，以及MP3檔案中的文本。 在選取的內容類型中找到的文字會與您網站上的所有其他文字一起搜尋。

在客戶看到「內容類型」設定的效果之前，您必須重建網站索引。

請參閱[配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

要對中文、日文或韓文MP3檔案進行爬網和索引，請完成以下步驟。 然後，在&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]**&#x200B;中，指定用於編碼MP3檔案的字元集。

請參閱[關於插入](../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5)。

**選擇要編目和索引的內容類型**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**」。
1. 在[!DNL Content Types]頁面上，檢查您要在網站上進行編目和索引的檔案類型。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （選用）執行下列任一操作：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以還原您所做的任何更改。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送階段設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 關於連線 {#concept_E2F3B7E7521147479E5948A94BB3A40B}

您可以使用「連線」來新增最多10個HTTP連線，搜尋機器人會使用這些連線來為您的網站建立索引。

增加連線數量可大幅減少完成編目和索引所需的時間。 不過，請注意，每增加一個連線都會增加伺服器的負載。

## 添加連接以提高索引速度 {#task_3E9B83E43C1842A19066355A15C4A6FB}

您可以使用「連線」來增加Crawler使用的同時HTTP連線數，以減少為網站建立索引所花的時間。 最多可以添加10個連接。

請注意，每增加一個連線，都會增加伺服器上的負載。

**添加連接以提高索引速度**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Connections]**」。
1. 在[!DNL Parallel Indexing Connections]頁的&#x200B;**[!UICONTROL Number of Connections]**&#x200B;欄位中，輸入要添加的連接數(1-10)。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （選用）執行下列任一操作：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以還原您所做的任何更改。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送階段設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 關於表單提交 {#concept_CADD5D7CF373497DAA6F8564D7BC8502}

您可以使用表單提交功能來協助您識別和處理網站上的表單。

在網站的編目和索引期間，遇到的每個表單都會與您新增的表單定義進行比較。 如果表單與表單定義相符，則會提交表單以進行索引。 如果表單符合多個定義，則會針對每個符合的定義提交表單一次。

## 新增在網站上建立表單索引的表單定義 {#task_62FBCE9E6DBE4BDA8D1249233ADFC00F}

您可以使用[!DNL Form Submission]來協助處理在您的網站上識別的表單，以便建立索引。

請務必重建網站索引，讓客戶可看到變更的結果。

請參閱[配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**為網站上的表單建立索引添加表單定義**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**」。
1. 在[!DNL Form Submission]頁面上，按一下&#x200B;**[!UICONTROL Add New Form]**。
1. 在[!DNL Add Form Definition]頁面上，設定[!DNL Form Recognition]和[!DNL Form Submission]選項。

   [!DNL Form Definition]頁面上[!DNL Form Recognition]區段中的五個選項可用來識別您的網頁中可處理的表單。

   [!DNL Form Submission]區段中的三個選項可用來指定隨表單提交至網站伺服器的參數和值。

   每行輸入一個識別或提交參數。 每個參數都必須包含名稱和值。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>選項 </p> </th> 
      <th colname="col2" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p> <b>表單識別</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>頁面URL遮色片 </p> </td> 
      <td colname="col2"> <p>識別包含表單的網頁。 若要識別出現在單一頁面上的表單，請輸入該頁面的URL，如下列範例所示： </p> <p> <code> https://www.mydomain.com/login.html </code> </p> <p>若要識別出現在多個頁面上的表單，請指定使用萬用字元來說明頁面的URL遮罩。 要識別在<code> https://www.mydomain.com/register/ </code>下的任何ASP頁面上遇到的表單，可以指定以下內容： </p> <p> <code> https://www.mydomain.com/register/*.asp&amp;nbsp; </code> </p> <p>您也可以使用規則運算式來識別多個頁面。 只需指定 
      <code>
        regexp 
      </code>關鍵字，如下列範例所示： </p> <p> <code> regexp&amp;nbsp;^https://www\.mydomain\.com/.*/login\.html$ </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>動作URL遮色片 </p> </td> 
      <td colname="col2"> <p>識別 
      <code>
        &lt;form&gt; 
      </code>標籤。 </p> <p>如同頁面URL遮罩，動作URL遮罩可採用單一URL、含萬用字元的URL或規則運算式的形式。 </p> <p>URL遮罩可以是下列任一項： 
      <ul id="ul_EDFE7688D3DD4C0BBACCE5D4648D8E44"> 
      <li id="li_77550A448D954EF29FF33EE5E8B5E0F5"> 完整路徑，如下所示：<code> https://www.mydomain.com/products.html </code> </li> 
      <li id="li_F84E25553BBA41419BE153DC0709E011"> 部分路徑，如下所示：<code> https://www.mydomain.com/products </code> </li> 
      <li id="li_8DADA1C8604740FCACBA30B4AAADB2A1"> 使用萬用字元的URL，如下所示：<code> https://www.mydomain.com/*.html </code> </li> 
      <li id="li_1EF637B450654B509AA4B618F7FD3C2B"> 規則運算式，如下所示：<code> regexp&amp;nbsp^https://www\.mydomain\.com/.*/login\.html$ </code> </li> 
      </ul> </p> <p>如果您不想為以URL遮色片或動作URL遮色片所識別之頁面上的文字建立索引，或如果您不想在這些頁面上追蹤連結，則可使用 
      <code>
        noindex 
      </code>和 
      <code>
        nofollow 
      </code>關鍵字。 您可以使用URL遮罩或入口點將這些關鍵字新增至遮罩。 </p> <p>請參閱<a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573" type="concept" format="dita" scope="local">關於URL入口點</a>。 </p> <p>請參閱<a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164" type="concept" format="dita" scope="local">關於URL遮罩</a>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>表單名稱遮色片 </p> </td> 
      <td colname="col2"> <p>識別表單(若 
      網頁中的<code>
        &lt;form&gt; 
      </code>標籤包含名稱屬性。 </p> <p>您可以使用簡單名稱( 
      <code>
        login_form 
      </code>)，帶有通配符的名稱( 
      )或規則運算式( 
      <code>
        regexp ^.*authorize.*$ 
      </code>)。<code>
        form* 
      </code> </p> <p>您通常可將此欄位保留為空白，因為表單通常沒有名稱屬性。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>表單ID遮色片 </p> </td> 
      <td colname="col2"> <p>識別表單(若 
      網頁中的<code>
        &lt;form&gt; 
      </code>標籤包含id屬性。 </p> <p>您可以使用簡單名稱( 
      <code>
        login_form 
      </code>)，帶有通配符的名稱( 
      )或規則運算式( 
      <code>
        regexp ^.*authorize.*$ 
      </code>)。<code>
        form* 
      </code> </p> <p>您通常可將此欄位保留為空白，因為表單通常沒有名稱屬性。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>參數 </p> </td> 
      <td colname="col2"> <p>識別包含或不包含已命名參數或具有特定值的已命名參數的表單。 </p> <p>例如，要標識包含預設為rick_brough@mydomain.com的電子郵件參數（密碼參數，但不是名字參數）的表單，可以指定以下參數設定，每行一個： </p> <p> <code> email=rick_brough@mydomain.com password  not&nbsp;first-name </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>表單提交</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>覆寫動作URL </p> </td> 
      <td colname="col2"> <p>指定表單提交的目標與表單的動作屬性中指定的目標不同。 </p> <p>例如，當透過JavaScript函式提交表單時，您可能會使用此選項，此函式會建構與表單中所含URL值不同的URL值。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>覆蓋方法 </p> </td> 
      <td colname="col2"> <p>指定表單提交的目標與表單的動作屬性中所使用的不同，以及提交JavaScript已變更方法的時間。 </p> <p>所有表單參數的預設值( 
      <code>
        &lt;input&gt; 
      </code>標籤，包括隱藏欄位)，預設值 
      <code>
        &lt;option&gt; 
      </code>來自 
      <code>
        &lt;select&gt; 
      </code>標籤，以及 
      <code>
        &lt;textarea&gt;...&lt;/textarea&gt; 
      </code>標籤)會從網頁讀取。 不過，在<span class="uicontrol">參數</span>欄位中，<span class="wintitle">表單提交</span>區段中列出的任何參數，都會以表單預設值取代。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>參數 </p> </td> 
      <td colname="col2"> <p>您可以在表單提交參數前置詞為 
      <code>
        not 
      </code>關鍵字。 </p> <p>為參數加上前置詞時 
      <code>
        not 
      </code>，表單提交時不會提交。 此行為適用於應取消選取的提交核取方塊。 </p> <p>例如，假設您要提交下列參數： </p> <p> 
      <ul id="ul_962D12BACF464FF189DB12BFAFCC93A6"> 
      <li id="li_830C6C3EC8D2448388A453BB8EDE5940"> 包含值的電子郵件參數 
      <code>
        nobody@mydomain.com 
      </code> </li> 
      <li id="li_905497E3FACE472DBDD49392D5B45E01"> 包含值的密碼參數 
      <code>
        tryme 
      </code> </li> 
      <li id="li_AAA411708ADC464793EADF0D821E282E"> 取消選取mycheckbox參數。 </li> 
      <li id="li_0D3DDE641E2B4BEF9F570C03FDB40ED2"> <p>其他 
      <code>
        &lt;form&gt; 
      </code>參數作為預設值 </p> </li> 
      </ul> </p> <p>您的表單提交參數如下所示： </p> <p> <code> email=nobody@mydomain.com 
        password=tryme 
        not&nbsp;mycheckbox </code> </p> <p>方法屬性 
      網頁上的<code>
        &lt;form&gt; 
      </code>標籤可用來決定是否使用GET方法或POST方法將資料傳送至您的伺服器。 </p> <p>若 
      <code>
        &lt;form&gt; 
      </code>標籤不包含方法屬性，則會使用GET方法提交表單。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 按一下 **[!UICONTROL Add]**.
1. （選用）執行下列任一操作：

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送階段設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 編輯表單定義 {#task_9FB34E9C8A814DFE9BF7F8F8F69BF314}

如果網站上的表單已變更，或您只需變更定義，即可編輯現有的表單定義。

請注意，[!DNL Form Submission]頁面上沒有[!DNL History]功能可還原您對表單定義所做的任何變更。

請務必重建網站索引，讓客戶可看到變更的結果。

請參閱[配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**要編輯表單定義**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**」。
1. 在[!DNL Form Submission]頁面上，按一下要更新的表單定義右側的&#x200B;**[!UICONTROL Edit]**。
1. 在[!DNL Edit Form Definition]頁面上，設定[!DNL Form Recognition]和[!DNL Form Submission]選項。

   請參閱[新增表單定義以在您的網站上建立表單索引下的選項表](../c-about-settings-menu/c-about-crawling-menu.md#task_62FBCE9E6DBE4BDA8D1249233ADFC00F)。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （選用）執行下列任一操作：

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送階段設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 刪除表單定義 {#task_C350FC0CDE344F2786215D544C048B5E}

如果您的網站上已不存在表單，或您不想再處理特定表單並為其建立索引，您可以刪除現有的表單定義。

請注意，[!DNL Form Submission]頁面上沒有[!DNL History]功能可還原您對表單定義所做的任何變更。

請務必重建網站索引，讓客戶可看到變更的結果。

請參閱[配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**刪除表單定義**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]**」。
1. 在[!DNL Form Submission]頁面上，按一下要刪除的表單定義右側的&#x200B;**[!UICONTROL Delete]**。

   請務必選擇要刪除的正確表單定義。 在下一步中按一下&#x200B;**[!UICONTROL Delete]**&#x200B;時，沒有刪除確認對話框。
1. 在[!DNL Delete Form Definition]頁面上，按一下&#x200B;**[!UICONTROL Delete]**。
1. （選用）執行下列任一操作：

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送階段設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 關於索引連接器 {#concept_CA6921E2FBF641F9B4F60C92B32AFA84}

使用[!DNL Index Connector]定義用於索引XML頁面或任何類型的摘要的其他輸入源。

您可以使用資料摘要輸入來源來存取儲存在不同表單中的內容，該表單使用其中一個可用的編目方法，通常會在網站上探索到。 每個已編目和編列索引的檔案，都直接對應至您網站上的內容頁面。 但是，資料摘要可能來自XML檔案，也可能來自逗號分隔或定位點分隔的文字檔，且包含要索引的內容資訊。

XML資料源由XML標籤或記錄組成，這些標籤或記錄包含與單個文檔對應的資訊。 這些單個文檔將添加到索引中。 文字資料摘要包含個別新行分隔記錄，這些記錄會對應至個別檔案。 這些單個文檔也添加到索引中。 無論是哪種情況，索引連接器組態都會說明如何解譯摘要。 每個配置都描述檔案的駐留位置以及伺服器訪問該檔案的方式。 設定也說明「對應」資訊。 也就是說，每個記錄的項目如何用來填入產生索引中的中繼資料欄位。

將「索引連接器」定義添加到[!DNL Staged Index Connector Definitions]頁後，可以更改「名稱」或「類型」值的任何配置設定&#x200B;*，但*&#x200B;除外。

[!DNL Index Connector]頁面會顯示下列資訊：

* 已配置和添加的已定義索引連接器的名稱。
* 已新增每個連接器的下列資料來源類型之一：

   * **文字**  — 簡單的「一般」檔案、逗號分隔、定位點分隔或其他一致分隔格式。
   * **摘要**  - XML摘要。
   * **XML**  - XML文檔的集合。

* 是否啟用連接器進行下一個爬網和索引完成。
* 資料源的地址。

另請參閱[關於索引連接器](../c-about-settings-menu/c-about-crawling-menu.md#concept_CA6921E2FBF641F9B4F60C92B32AFA84)

## 索引程式如何用於Index Connector中的文字和摘要組態 {#section_E059A33D61EE4DB0972A37B8A35E9E16}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>步驟 </p> </th> 
   <th colname="col2" class="entry"> <p>程序 </p> </th> 
   <th colname="col3" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>下載資料來源。 </p> </td> 
   <td colname="col3"> <p>對於文字和摘要設定，這是簡單的檔案下載。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>將下載的資料來源劃分為個別偽檔案。 </p> </td> 
   <td colname="col3"> <p>對於<span class="uicontrol">文本</span>，每行以新行分隔的文本都對應於單個文檔，並使用指定的分隔符（如逗號或制表符）進行分析。 </p> <p>對於<span class="uicontrol">摘要</span>，每個檔案的資料會使用下列格式的規則運算式模式擷取： </p> <p> <code> &lt;${Itemtag}&gt;(.*?)&lt;/${Itemtag}&gt; </code> </p> <p>使用<span class="uicontrol"> 「Index Connector Add </span>」頁上的<span class="wintitle">映射</span>，建立資料的快取副本，然後為Crawler建立連結清單。 資料儲存在本機快取中，並填入已設定的欄位。 </span></p> <p>將解析的資料寫入本地快取。 </p> <p>此快取稍後將被讀取，以建立Crawler需要的簡單HTML文檔。 例如， </p> <p> <code> &lt;html&gt;&lt;head&gt; 
      &lt;title&gt;{title}&lt;/title&gt; 
      &lt;meta&nbsp;name="{field}"&nbsp;content="{data}"&nbsp;/&gt; 
      ... 
      &lt;/head&gt;&lt;body&gt; 
      {body} 
      &lt;/body&gt;&lt;/html&gt; </code> </p> <p><span class="codeph"> &lt;title&gt; </span>元素只有在與「標題」元資料欄位有映射時才產生。 同樣地，<span class="codeph"> &lt;body&gt; </span>元素只有在與Body元資料欄位有映射時才產生。 </p> <p> <b>重要</b>:不支援將值指派給預先定義的URL中繼標籤。 </p> <p>對於所有其他映射，將為在原始文檔中找到資料的每個欄位生成<span class="codeph"> &lt;meta&gt; </span>標籤。 </p> <p>每個檔案的欄位會新增至快取。 對於寫入快取的每個文檔，也生成一個連結，如以下示例所示： </p> <p> <code> &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      .... </code> </p> <p>配置的映射必須有一個欄位標識為主鍵。 此對應會構成從快取擷取資料時所使用的金鑰。 </p> <p>Crawler可識別URL <span class="codeph">索引：</span>配置前置詞，可接著存取本機快取的資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>對快取的文檔集進行爬網。 </p> </td> 
   <td colname="col3"> <p><span class="codeph">索引：</span>連結將添加到爬網程式的待處理清單中，並以正常爬網順序進行處理。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>處理每個文檔。 </p> </td> 
   <td colname="col3"> <p>每個連結的索引鍵值對應於快取中的項目，因此對每個連結進行編目會導致從快取中擷取該檔案的資料。 然後，它會「組合」成HTML影像，並加以處理並新增至索引。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 索引過程如何在Index Connector中處理XML配置 {#section_7F1551EA51854C5C99F284CE260526EB}

XML配置的索引過程與文本和摘要配置的過程類似，但有以下小的更改和例外。

由於XML編目的文檔已分為單個檔案，因此上表中的步驟1和2不直接應用。 如果您在[!DNL Index Connector Add]頁面的&#x200B;**[!UICONTROL Host Address]**&#x200B;和&#x200B;**[!UICONTROL File Path]**&#x200B;欄位中指定URL，則會將其下載並作為一般HTML檔案處理。 期望是下載文檔包含`<a href="{url}"...`連結的集合，每個連結指向處理的XML文檔。 此類連結會轉換為下列格式：

```
<a href="index:<ic_config_name>?url="{url}">
```

例如，如果Adobe設定傳回下列連結：

```
<a href="https://www.adobe.com/somepath/doc1.xml">doc 1</a> 
<a href="https://www.adobe.com/otherpath/doc2.xml">doc 2</a>
```

在上表中，步驟3不適用，且在編目和索引時已完成步驟4。

或者，您也可以將XML文檔與通過爬網過程自然發現的其他文檔混合。 在這種情況下，您可以使用重寫規則(**[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Retrieve URL Rules]**)來更改XML文檔的URL，以將它們導向Index Connector。

請參閱[關於爬網清單檢索URL規則](../c-about-settings-menu/c-about-rewrite-rules-menu.md#concept_EC8E2E48B99A458D8567B526C9827CBA)。

例如，假設您有下列重寫規則：

```
RewriteRule (^http.*[.]xml$) index:Adobe?key=$1
```

此規則將任何結尾為`.xml`的URL轉譯為「索引連接器」連結。 Crawler識別並重寫`index:` URL配置。 下載過程將通過主伺服器上的Index Connector Apache伺服器重定向。 每個下載的檔案都會使用與摘要搭配使用的相同規則運算式模式來檢查。 但是，在這種情況下，製造的HTML文檔不會保存在快取中。 而是直接交給爬蟲來處理索引。

## 如何配置多個索引連接器 {#section_C2B14C0F06354A57AEF6238FF3814E5D}

您可以為任何帳戶定義多個索引連接器配置。 這些設定會自動新增至&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawl]** > **[!UICONTROL URL Entrypoints]**&#x200B;中的下拉式清單，如下圖所示：

![](assets/url_entrypoints_index_connector.png)

從下拉式清單中選取設定，會將值新增至URL登入點清單的結尾。

>[!NOTE]
>
>禁用的「索引連接器」配置將添加到下拉清單中，但您無法選擇它們。 如果您再次選擇同一個Index Connector配置，該配置將添加到清單的末尾，並刪除前一個實例。

要指定增量爬網的「索引連接器」入口點，可以使用以下格式添加條目：

```
index:<indexconnector_configuration_name>
```

如果在「索引連接器」頁上找到並啟用了每個添加的條目，則Crawler將處理這些條目。

注意：由於每個文檔的URL都是使用索引連接器配置名稱和文檔的主鍵構建的，因此在執行增量更新時，請確保使用相同的索引連接器配置名稱！ 這樣做允許[!DNL Adobe Search&Promote]正確更新先前已索引的文檔。

另請參閱[關於URL入口點](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。

**添加索引連接器時使用「設定映射」**

新增「索引連接器」時，您可以選擇使用功能&#x200B;**[!UICONTROL Setup Maps]**&#x200B;來下載資料來源的範例。 檢查資料以確定索引適用性。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>如果選擇「索引連接器」類型…… </p> </th> 
   <th colname="col2" class="entry"> <p>設定映射功能…… </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>文字 </p> </td> 
   <td colname="col2"> <p>先嘗試制表符，然後使用垂直條(<span class="codeph"> | </span>)，最後加上逗號(<span class="codeph"> 、 </span>)。 如果您在按一下「<span class="uicontrol">設定映射</span>」之前已指定分隔字元值，則會改用該值。 </p> <p>最佳配適方案會在地圖欄位中填入適當標籤和欄位值的猜測。 此外，顯示所分析資料的採樣。 如果您知道檔案包含標題列，請務必選取第一列</span>中的<span class="uicontrol">標題。 設定函式會使用此資訊來更好地識別產生的對應項目。 </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>資訊源 </p> </td> 
   <td colname="col2"> <p>下載資料源並執行簡單的XML解析。 </p> <p>生成的XPath標識符顯示在映射表的標籤行中，並且在欄位中顯示類似的值。 這些行僅標識可用資料，不會生成更複雜的XPath定義。 但是，它仍然很有幫助，因為它描述了XML資料並標識了Itemtag值。 </p> <p> <p>注意： 「設定映射」函式將下載整個XML源以執行其分析。 如果檔案很大，則此操作可能會超時。 </p> </p> <p>成功後，此函式將標識所有可能的XPath項，其中許多項不理想使用。 請務必檢查產生的地圖定義，並移除您不需要或想要的定義。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>XML </p> </td> 
   <td colname="col2"> <p>下載代表個別檔案的URL，而非主要連結清單。 此單一檔案會使用與摘要搭配使用的相同機制進行剖析，並顯示結果。 </p> <p>在按一下<span class="uicontrol">添加</span>以保存配置之前，請確保將URL更改回主連結清單文檔。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**重要**:「設定映射」功能可能不適用於大型XML資料集，因為其檔案解析器嘗試將整個檔案讀入記憶體。因此，您可能會遇到記憶體不足的情況。 但是，當在編製索引時處理同一文檔時，它不會讀入記憶體。 相反，大型文檔「在移動時」被處理，並且不會先完全讀入記憶體。

**添加索引連接器時使用預覽**

新增「索引連接器」時，您可以選擇使用功能&#x200B;**[!UICONTROL Preview]**&#x200B;來驗證資料，就像儲存資料一樣。 它會針對設定執行測試，但不會將設定儲存至帳戶。 測試存取已設定的資料來源。 但是，它將下載快取寫入臨時位置；它與索引編目器使用的主快取資料夾不衝突。

預覽僅處理由Acct:IndexConnector-Preview-Max-Documents控制的五個文檔的預設值。 預覽的文檔以源格式顯示，如向索引編目程式顯示。 顯示與Web瀏覽器中的「檢視來源」功能類似。 可以使用標準導航連結導航預覽集中的文檔。

預覽不支援XML配置，因為此類文檔是直接處理的，不會下載到快取中。

## 添加索引連接器定義 {#task_96779B651A654E1F871F55D6DBBC8886}

每個「索引連接器」配置都定義一個資料源和映射，以將為該源定義的資料項與索引中的元資料欄位相關。

在客戶看到新定義和已啟用定義的效果之前，請重建網站索引。

**添加索引連接器定義**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**」。
1. 在[!DNL Stage Index Connector Definitions]頁面上，按一下&#x200B;**[!UICONTROL Add New Index Connector]**。
1. 在[!DNL Index Connector Add]頁面上，設定您想要的連接器選項。 可用的選項取決於您選取的&#x200B;**[!UICONTROL Type]**。

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>選項 </p> </th> 
      <th colname="col2" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>名稱 </p> </td> 
      <td colname="col2"> <p>索引連接器配置的唯一名稱。 您可以使用英數字元。 也允許使用字元「_」和「 — 」。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>類型 </p> </td> 
      <td colname="col2"> <p>資料的來源。 您選擇的資料源類型會影響生成的<span class="wintitle">索引連接器添加</span>頁上可用的選項。 您可以選擇下列項目： </p> <p> 
      <ul id="ul_1ADC3DFBC929467385F7465BE8E13635"> 
      <li id="li_64FCD749F55442BAB316BD474128D4F9"> <span class="uicontrol"> 文字 </span> <p>簡單的平面文本檔案、逗號分隔、制表符分隔或其他一致的分隔格式。 每行以新行分隔的文本都對應於單個文檔，並使用指定的分隔符進行分析。 </p> <p>您可以從1(1)開始，將每個值或欄對應至由欄號參考的中繼資料欄位。 </p> </li> 
      <li id="li_2A4F16CE6DCE4114B7F8E4FE156252BB"> <span class="uicontrol"> 資訊源 </span> <p>下載包含多個「行」資訊的主XML文檔。 </p> </li> 
      <li id="li_5A61C53522D74D4C9A5F65989604BDEF"> <span class="uicontrol"> XML </span> <p>下載包含連結的主XML文檔( 
      <code>
        &lt;a&gt; 
      </code>)轉換為個別XML檔案。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>資料源類型：文字</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>已啟用 </p> </td> 
      <td colname="col2"> <p>將配置「開啟」以進行編目和索引。 或者，您可以關閉設定，以防止編目和建立索引。 </p> <p> <b>注意</b>:如果在入口點清單中找到索引連接器配置，則會忽略這些配置。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>主機地址 </p> </td> 
      <td colname="col2"> <p>指定資料所在的伺服器主機的地址。 </p> <p>如果需要，可以指定資料源文檔的完整URI（統一資源標識符）路徑，如以下示例所示： </p> <p> <code> https://www.somewhere.com/some_path/some_file.xml </code> </p> <p>或  </p> <p> <code> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.xml </code> </p> <p>URI被劃分為「主機地址」、「檔案路徑」、「協定」以及（可選）「用戶名」和「密碼」欄位的相應條目。 </p> <p>指定找到資料源檔案的主機系統的IP地址或URL地址。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>檔案路徑 </p> </td> 
      <td colname="col2"> <p>指定簡單普通文本檔案、逗號分隔、制表符分隔或其他一致分隔格式檔案的路徑。 </p> <p>路徑相對於主機地址的根。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>增量檔案路徑 </p> </td> 
      <td colname="col2"> <p>指定簡單普通文本檔案、逗號分隔、制表符分隔或其他一致分隔格式檔案的路徑。 </p> <p>路徑相對於主機地址的根。 </p> <p>如果指定，則在增量索引操作期間下載並處理此檔案。 如果未指定檔案，則會改用「檔案路徑」下列出的檔案。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>垂直檔案路徑 </p> </td> 
      <td colname="col2"> <p>指定在「垂直更新」期間使用的簡單普通文本檔案、逗號分隔、制表符分隔或其它一致分隔格式檔案的路徑。 </p> <p>路徑相對於主機地址的根。 </p> <p>如果指定，則在「垂直更新」操作期間下載並處理此檔案。 </p> <p> <b>注意</b>:此功能預設為未啟用。請連絡技術支援以啟用此功能以供您使用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>刪除檔案路徑 </p> </td> 
      <td colname="col2"> <p>指定簡單普通文本檔案的路徑，每行包含單個文檔標識符值。 </p> <p>路徑相對於主機地址的根。 </p> <p>如果指定，則在增量索引操作期間下載並處理此檔案。 此檔案中找到的值用於構造「刪除」請求，以刪除先前已索引的文檔。 此檔案中的值必須與「完整檔案路徑」或「增量檔案路徑」檔案中的值相對應，該檔案位於標識為<span class="uicontrol">主鍵</span>的列中。 </p> <p> <b>注意</b>:此功能預設為未啟用。請連絡技術支援以啟用此功能以供您使用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>通訊協定 </p> </td> 
      <td colname="col2"> <p>指定用於訪問檔案的協定。 您可以選擇下列項目： </p> <p> 
      <ul id="ul_F6BC10FD51CA4A1D855B2B3212838A9C"> 
      <li id="li_79FB7DC65E774ABBB23E57BF98AD9738"> HTTP <p>如有必要，您可以輸入正確的驗證憑據以訪問HTTP伺服器。 </p> </li> 
      <li id="li_BAA9AD5E4B014E09B3A66C94022B7225"> HTTPS <p>如有必要，您可以輸入正確的驗證憑據以訪問HTTPS伺服器。 </p> </li> 
      <li id="li_E716ABB169DD408BA91F1CA27F445A16"> FTP <p>您必須輸入正確的驗證憑證才能存取FTP伺服器。 </p> </li> 
      <li id="li_FD7143019C5244C3B8A5B1B5AA84859A"> SFTP <p>您必須輸入正確的驗證憑證才能存取SFTP伺服器。 </p> </li> 
      <li id="li_38E0036C1365419F9D00083CACA34AFB"> 檔案 </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>逾時 </p> </td> 
      <td colname="col2"> <p>指定FTP、SFTP、HTTP或HTTPS連線的逾時（秒）。 此值必須介於30和300之間。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>重試 </p> </td> 
      <td colname="col2"> <p>指定失敗FTP、SFTP、HTTP或HTTPS連線的重試次數上限。 此值必須介於0和10之間。 </p> <p>值為零(0)將阻止重試嘗試。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>編碼 </p> </td> 
      <td colname="col2"> <p>指定指定的資料源檔案中使用的字元編碼系統。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>分隔字元 </p> </td> 
      <td colname="col2"> <p>指定您要用來勾勒指定資料來源檔案中每個欄位的字元。 </p> <p>逗號字元(<span class="codeph"> 、 </span>)是分隔字元的範例。 逗號可做為欄位分隔字元，有助於分隔您指定之資料來源檔案中的資料欄位。 </p> <p>選擇<span class="uicontrol">頁簽？ </span> 使用水準定位字元作為分隔符。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>第一列的標題 </p> </td> 
      <td colname="col2"> <p>指示資料源檔案中的第一行僅包含標題資訊，而不包含資料。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>用於編製索引的最小文檔數 </p> </td> 
      <td colname="col2"> <p>如果設為正值，則指定下載的檔案中預期的最小記錄數。 如果收到的記錄較少，則索引操作將被中止。 </p> <p> <b>注意</b>:此功能預設為未啟用。請連絡技術支援以啟用此功能以供您使用。 </p> <p> <b>注意</b>:此功能僅在完整索引操作期間使用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>地圖 </p> </td> 
      <td colname="col2"> <p>使用列號指定列到元資料的映射。 </p> <p> 
      <ul id="ul_981AE2C6D30443BDBFC6575D413732A2"> 
      <li id="li_A42CB9DFFF8C45A7BAC2D471FE96CEBE"> <span class="uicontrol"> 欄 </span> <p> 指定列號，第一列為1(1)。 若要為每個欄新增對應列，請在「<span class="wintitle">動作</span>」下方按一下「<span class="uicontrol"> + </span>」。 </p> <p>您不需要參考資料來源中的每一欄。 反之，您可以選擇略過值。 </p> </li> 
      <li id="li_26E8C9554A5D4BC5A5073D6385E3626F"> <span class="uicontrol"> 欄位 </span> <p>定義用於每個生成的&lt;meta&gt;標籤的名稱屬性值。 </p> </li> 
      <li id="li_5DFA514B7F9549B98D6CBC095A66033C"> <span class="uicontrol"> 中繼資料? </span> <p>使<span class="uicontrol">欄位</span>成為下拉清單，您可從中為當前帳戶選擇定義的元資料欄位。 </p> <p>如果需要，<span class="uicontrol">欄位</span>值可以是未定義的元資料欄位。 未定義的元資料欄位有時對建立<span class="wintitle">篩選指令碼</span>使用的內容很有幫助。 </p> <p>請參閱<a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local">關於篩選指令碼</a>。 </p> <p>當Index Connector在任何映射欄位上處理具有多個點擊的XML文檔時，將多個值串連到生成的快取文檔中的單個值中。 依預設，這些值會使用逗號分隔字元結合。 但是，假設對應的<span class="wintitle">欄位</span>值是定義的中繼資料欄位。 此外，該欄位還設定了<span class="wintitle">允許清單</span>屬性。 在此情況下，在串連中使用欄位的「清單分隔符」值（定義的第一個分隔符）。 </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892C95"> <span class="uicontrol"> 主鍵？  </span> <p>只有一個映射定義被標識為主鍵。 此欄位將成為將此文檔添加到索引時顯示的唯一引用。 此值用於索引中文檔的URL中。 </p> <p><span class="uicontrol">主鍵</span>值在由Index Connector配置表示的所有文檔中都必須是唯一的 — 將忽略所遇到的任何重複項。 如果源文檔不包含用作<span class="uicontrol">主鍵</span>的單個唯一值，但將<i>組合在一起的兩個或多個欄位可以</i>形成唯一標識符，則可以通過將多個<span class="uicontrol">列</span>值與限定值的垂直條("|")組合來定義<span class="uicontrol">主鍵</span>。 </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892D96"> <span class="uicontrol"> 脫HTML?  </span> <p>核取此選項時，會移除在此欄位資料中找到的任何HTML標籤。 </p> </li> 
      <li id="li_359D2902859B4C5BADB0BA26F0BA4DC0"> <span class="uicontrol"> 動作 </span> <p>可讓您將列新增至地圖，或從地圖中移除列。 列的順序並不重要。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>資料源類型：摘要</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>已啟用 </p> </td> 
      <td colname="col2"> <p>將配置「開啟」以進行編目和索引。 或者，您可以關閉設定，以防止編目和建立索引。 </p> <p> <b>注意</b>:如果在入口點清單中找到索引連接器配置，則會忽略這些配置。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>主機地址 </p> </td> 
      <td colname="col2"> <p>指定找到資料源檔案的主機系統的IP地址或URL地址。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>檔案路徑 </p> </td> 
      <td colname="col2"> <p>指定包含多個「行」資訊的主XML文檔的路徑。 </p> <p>路徑相對於主機地址的根。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>增量檔案路徑 </p> </td> 
      <td colname="col2"> <p>指定包含多個「行」資訊的增量XML文檔的路徑。 </p> <p>路徑相對於主機地址的根。 </p> <p>如果指定，則在增量索引操作期間下載並處理此檔案。 如果未指定檔案，則會改用「檔案路徑」下列出的檔案。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>垂直檔案路徑 </p> </td> 
      <td colname="col2"> <p>指定XML文檔的路徑，該文檔包含多個要在垂直更新期間使用的稀疏「行」資訊。 </p> <p>路徑相對於主機地址的根。 </p> <p>如果指定，則在「垂直更新」操作期間下載並處理此檔案。 </p> <p> <b>注意</b>:此功能預設為未啟用。請連絡技術支援以啟用此功能以供您使用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>刪除檔案路徑 </p> </td> 
      <td colname="col2"> <p>指定簡單普通文本檔案的路徑，每行包含單個文檔標識符值。 </p> <p>路徑相對於主機地址的根。 </p> <p>如果指定，則在增量索引操作期間下載並處理此檔案。 此檔案中找到的值用於構造「刪除」請求，以刪除先前已索引的文檔。 此檔案中的值必須與「完整檔案路徑」或「增量檔案路徑」檔案中的值相對應，該檔案位於標識為<span class="uicontrol">主鍵</span>的列中。 </p> <p> <b>注意</b>:此功能預設為未啟用。請連絡技術支援以啟用此功能以供您使用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>通訊協定 </p> </td> 
      <td colname="col2"> <p>指定用於訪問檔案的協定。 您可以選擇下列項目： </p> <p> 
      <ul id="ul_976A34FD14A841F2B610C1C0CCBB82B9"> 
      <li id="li_05BBA0F670F14431A89AE4178F1A6F94"> HTTP <p>如有必要，您可以輸入正確的驗證憑據以訪問HTTP伺服器。 </p> </li> 
      <li id="li_100446691F304572B8FC3F083F86A2CB"> HTTPS <p>如有必要，您可以輸入正確的驗證憑據以訪問HTTPS伺服器。 </p> </li> 
      <li id="li_027088A8E30444DAA8CCCC5B0BAA74C1"> FTP <p>您必須輸入正確的驗證憑證才能存取FTP伺服器。 </p> </li> 
      <li id="li_DCEF9D5C99354990B03E29083C2ED8DC"> SFTP <p>您必須輸入正確的驗證憑證才能存取SFTP伺服器。 </p> </li> 
      <li id="li_44E34FF2AB0D429EB3408106E6FCF780"> 檔案 </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Itemtag </p> </td> 
      <td colname="col2"> <p>標識可用於標識指定資料源檔案中各個XML行的XML元素。 </p> <p>例如，在AdobeXML文檔的以下摘要片段中，Itemtag值為<span class="codeph">記錄</span>: </p> <p> <code> &lt;?xml&nbsp;version="1.0"&nbsp;encoding="utf-8"?&gt; 
        &lt;!DOCTYPE&nbsp;gsafeed&nbsp;PUBLIC&nbsp;"-//Google//DTD&nbsp;GSA&nbsp;Feeds//EN"&nbsp;""&gt; &lt;gsafeed&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;datasource&gt;marketplace&lt;/datasource&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;feedtype&gt;incremental&lt;/feedtype&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;group&nbsp;action="add"&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=1&nbsp;action="add"&nbsp;mimetype="text/html"displayurl="https://www.adobe.com/cfusion/marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=1"&gt;&lt;metadata&gt; 
        &lt;meta&nbsp;name="mp_mkt"&nbsp;content="1"/&gt; 
        &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
        dbreferenced/marketplaceicons/icn_air.png"/&gt; 
        &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;AIR&nbsp;Marketplace"/&gt; 
        &lt;meta&nbsp;name="description"&nbsp;content="Discover&nbsp;new&nbsp;applications&nbsp;..."/&gt; &lt;/metadata&gt; 
        &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;AIR&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Discover&nbsp;new&nbsp;applications&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;&lt;/cntent&gt; 
        &lt;/record&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa/
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=2&nbsp;action="add"&nbsp;mimetype="text/html"&nbsp;displayurl="https://www.adobe.com/cfusion/ 
        marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=2"&gt; 
        &lt;metadata&gt; 
        &lt;meta&nbsp;name="mp_mkt"&nbsp;content="2"/&gt; 
        &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
        dbreferenced/marketplaceicons/icn_photoshop.png"/&gt;         &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;Photoshop&nbsp;Marketplace"/&gt;         &lt;meta&nbsp;name="description"&nbsp;content="Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;..."/&gt; 
        &lt;/metadata&gt;         &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;Photoshop&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;/content&gt; 
        &lt;/record&gt; 
        ... 
        &lt;record&gt; 
        ... 
        &lt;/record&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/group&gt; 
        &lt;/gsafeed&gt; 
        </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>用於編製索引的最小文檔數 </p> </td> 
      <td colname="col2"> <p>如果設為正值，則指定下載的檔案中預期的最小記錄數。 如果收到的記錄較少，則索引操作將被中止。 </p> <p> <b>注意</b>:此功能預設為未啟用。請連絡技術支援以啟用此功能以供您使用。 </p> <p> <b>注意</b>:此功能僅在完整索引操作期間使用。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>地圖 </p> </td> 
      <td colname="col2"> <p>可讓您使用XPath運算式指定XML元素對中繼資料的對應。 </p> <p> 
      <ul id="ul_604108C0277C4892AE8A40CA39889ABD"> 
      <li id="li_0AF92270AE9F4BA8B2C7EE41FABC0F34"> <span class="uicontrol"> 標記 </span> <p>指定已解析XML資料的XPath表示。 使用上面的示例AdobeXML文檔，在選項Itemtag下，可以使用以下語法進行映射： </p> <p> <code> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
      /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
      /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
      /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>上述語法轉譯為： </p> <p> 
      <ul id="ul_6400EBD08D424EADA1612FE4F7EFB640"> 
      <li id="li_9958F9B40D42434195597DBA9F2AF28F"> <code> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p><span class="codeph">顯示<span class="codeph">記錄</span>元素的 </span>屬性映射到元資料欄位<span class="codeph"> page-url </span>。 </p> </li> 
      <li id="li_759013EA02CD48BE971A55B0A6A11424"> <code> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>包含在<span class="codeph">元資料</span>元素內的<span class="codeph">內容</span>元素的<span class="codeph">屬性，該元資料</span>元素包含在<span class="codeph">記錄</span>元素內，其名稱屬性為<span class="codeph">標題</span>，映射到元資料欄位<span class="codeph">標題</span>。 </p> </li> 
      <li id="li_E741CA59197D462EB2946EDE874AFDC8"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>包含在<span class="codeph">記錄</span>元素內的<span class="codeph">元資料</span>元素中的<span class="codeph">內容</span>屬性，其名稱屬性為<span class="codeph">說明</span>，映射到元資料欄位<span class="codeph"> desc </span>。</span><span class="codeph"> </span></p> </li> 
      <li id="li_E35EAE3D284D46D485D9064D7BB6AB13"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>包含在<span class="codeph">記錄</span>元素內的<span class="codeph">元資料</span>元素中的<span class="codeph">內容</span>屬性（其名稱屬性為<span class="codeph">說明</span>）映射到元資料欄位<span class="codeph"> body </span>。</span><span class="codeph"> </span></p> </li> 
      </ul> </p> <p>XPath是相對複雜的表示法。 如需詳細資訊，請前往下列位置： </p> <p>請參閱<a href="https://www.w3schools.com/xml/xpath_intro.asp" scope="external" format="html"> https://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_8147075D7ACD4811A7ED335F23FE62A6"> <span class="uicontrol"> 欄位 </span> <p>定義用於每個生成的<span class="codeph"> &lt;meta&gt; </span>標籤的名稱屬性值。 </p> </li> 
      <li id="li_2380199D63BF425A919606D8232FA6E2"> <span class="uicontrol"> 中繼資料? </span> <p>使<span class="uicontrol">欄位</span>成為下拉清單，您可從中為當前帳戶選擇定義的元資料欄位。 </p> <p>如果需要，<span class="uicontrol">欄位</span>值可以是未定義的元資料欄位。 未定義的元資料欄位有時對建立<span class="wintitle">篩選指令碼</span>使用的內容很有幫助。 </p> <p>請參閱<a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local">關於篩選指令碼</a>。 </p> <p>當Index Connector在任何映射欄位上處理具有多個點擊的XML文檔時，將多個值串連到生成的快取文檔中的單個值中。 依預設，這些值會使用逗號分隔字元結合。 但是，假設對應的<span class="wintitle">欄位</span>值是定義的中繼資料欄位。 此外，該欄位還設定了<span class="wintitle">允許清單</span>屬性。 在此情況下，在串連中使用欄位的「清單分隔符」值（定義的第一個分隔符）。 </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC70E"> <span class="uicontrol"> 主鍵？  </span> <p>只有一個映射定義被標識為主鍵。 此欄位將成為將此文檔添加到索引時顯示的唯一引用。 此值用於索引中文檔的URL中。 </p> <p><span class="uicontrol">主鍵</span>值在由Index Connector配置表示的所有文檔中都必須是唯一的 — 將忽略所遇到的任何重複項。 如果源文檔不包含用作<span class="uicontrol">主鍵</span>的單個唯一值，但將兩個或多個欄位合併在一起<i>可以</i>形成唯一標識符，則可以通過組合多個<span class="uicontrol">標籤</span>定義和限定值的垂直條("|")來定義<span class="uicontrol">主鍵</span>。 </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC81F"> <span class="uicontrol"> 脫HTML?  </span> <p>核取此選項時，會移除在此欄位資料中找到的任何HTML標籤。 </p> </li> 
      <li id="li_5E829D1D0DBD4BB7AAB5DB983053D248"> <span class="uicontrol"> 用於刪除？  </span> <p>僅在增量索引操作期間使用。 符合此XPath模式的記錄標識要刪除的項目。 每個此類記錄的<span class="uicontrol">主鍵</span>值用於構造"delete"請求，如刪除檔案路徑。 </p> <p> <b>注意</b>:此功能預設為未啟用。請連絡技術支援以啟用此功能以供您使用。 </p> </li> 
      <li id="li_D40E2F9AD8AD49FC9AC4B8C75BA31E28"> <span class="uicontrol"> 動作 </span> <p>可讓您將列新增至地圖，或從地圖中移除列。 列的順序並不重要。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>資料源類型：XML</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>已啟用 </p> </td> 
      <td colname="col2"> <p>將配置「開啟」以進行編目和索引。 或者，您可以關閉設定，以防止編目和建立索引。 </p> <p> <b>注意</b>:如果在入口點清單中找到索引連接器配置，則會忽略這些配置。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>主機地址 </p> </td> 
      <td colname="col2"> <p>指定找到資料源檔案的主機系統的URL地址。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>檔案路徑 </p> </td> 
      <td colname="col2"> <p>指定包含連結的主XML文檔的路徑( 
      <code>
        &lt;a&gt; 
      </code>)轉換為個別XML檔案。 </p> <p>路徑相對於主機地址的根。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>通訊協定 </p> </td> 
      <td colname="col2"> <p>指定用於訪問檔案的協定。 您可以選擇下列項目： </p> <p> 
      <ul id="ul_EA4EB7953D68483FAD75753B2EE70E74"> 
      <li id="li_537F24C6B2AB435CB7C14117663D7B3F"> HTTP <p>如有必要，您可以輸入正確的驗證憑據以訪問HTTP伺服器。 </p> </li> 
      <li id="li_8C13C93C52364FFA8B9B18830CDB223C"> HTTPS <p>如有必要，您可以輸入正確的驗證憑據以訪問HTTPS伺服器。 </p> </li> 
      <li id="li_2F967B5675254C949B31EAB19910751C"> FTP <p>您必須輸入正確的驗證憑證才能存取FTP伺服器。 </p> </li> 
      <li id="li_C24BE4C1DE79488AA64C7133D78CD3A6"> SFTP <p>您必須輸入正確的驗證憑證才能存取SFTP伺服器。 </p> </li> 
      <li id="li_7581C21CFC104986A361F62BD7A370C1"> 檔案 </li> 
      </ul> </p> <p> <b>注意</b>:只有在「主機地址」和/或「檔案路徑」欄位中指定了資訊時，才使用「協定」設定。根據URL規範，個別XML檔案會使用HTTP或HTTPS下載。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Itemtag </p> </td> 
      <td colname="col2"> <p>標識在指定的資料源檔案中定義「行」的XML元素。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>地圖 </p> </td> 
      <td colname="col2"> <p>可讓您使用欄數指定欄對中繼資料的對應。 </p> <p> 
      <ul id="ul_06F50CBA0AA64C7CB1AFAE076E629A64"> 
      <li id="li_0FA2502869BA40DC93D790B79E15A9D2"> <span class="uicontrol"> 標記 </span> <p>指定已解析XML資料的XPath表示。 使用上面的示例AdobeXML文檔，在選項Itemtag下，可以使用以下語法映射它： </p> <p> <code> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
        /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>上述語法轉譯為： </p> <p> 
      <ul id="ul_F8C536E6E54546D9AA5B22B879C0AF39"> 
      <li id="li_78A35DFFF1B4496CAC6EDC7B1E991F29"> <code> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p><span class="codeph">顯示<span class="codeph">記錄</span>元素的 </span>屬性映射到元資料欄位<span class="codeph"> page-url </span>。 </p> </li> 
      <li id="li_FA7DF3D1942248B98660F3D0C82F4563"> <code> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>包含在<span class="codeph">元資料</span>元素內的<span class="codeph">內容</span>元素的<span class="codeph">屬性，該元資料</span>元素包含在<span class="codeph">記錄</span>元素內，其名稱屬性為<span class="codeph">標題</span>，映射到元資料欄位<span class="codeph">標題</span>。 </p> </li> 
      <li id="li_D8000A116FF84DE59ED19C656DDD3BC1"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>包含在<span class="codeph">記錄</span>元素內的<span class="codeph">元資料</span>元素中的<span class="codeph">內容</span>屬性，其名稱屬性為<span class="codeph">說明</span>，映射到元資料欄位<span class="codeph"> desc </span>。</span><span class="codeph"> </span></p> </li> 
      <li id="li_7FA6A53DFD3D42A98B7BA17CC29DDB81"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>包含在<span class="codeph">記錄</span>元素內的<span class="codeph">元資料</span>元素中的<span class="codeph">內容</span>屬性（其名稱屬性為<span class="codeph">說明</span>）映射到元資料欄位<span class="codeph"> body </span>。</span><span class="codeph"> </span></p> </li> 
      </ul> </p> <p>XPath是相對複雜的表示法。 如需詳細資訊，請前往下列位置： </p> <p>請參閱<a href="https://www.w3schools.com/xml/xpath_intro.asp" scope="external" format="html"> https://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_84999D07E0AE4265BC7928BBB49957B9"> <span class="uicontrol"> 欄位 </span> <p>定義用於每個生成的&lt;meta&gt;標籤的名稱屬性值。 </p> </li> 
      <li id="li_E125788D0F5242958BD790E26A675C20"> <span class="uicontrol"> 中繼資料? </span> <p>使<span class="uicontrol">欄位</span>成為下拉清單，您可從中為當前帳戶選擇定義的元資料欄位。 </p> <p>如果需要，<span class="uicontrol">欄位</span>值可以是未定義的元資料欄位。 未定義的元資料欄位有時對建立<span class="wintitle">篩選指令碼</span>使用的內容很有幫助。 </p> <p>請參閱<a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local">關於篩選指令碼</a>。 </p> <p>當Index Connector在任何映射欄位上處理具有多個點擊的XML文檔時，將多個值串連到生成的快取文檔中的單個值中。 依預設，這些值會使用逗號分隔字元結合。 但是，假設對應的<span class="wintitle">欄位</span>值是定義的中繼資料欄位。 此外，該欄位還設定了<span class="wintitle">允許清單</span>屬性。 在此情況下，在串連中使用欄位的「清單分隔符」值（定義的第一個分隔符）。 </p> </li> 
      <li id="li_9F435EFB3EC74B409EC82A851824609F"> <span class="uicontrol"> 主鍵？  </span> <p>只有一個映射定義被標識為主鍵。 此欄位將成為將此文檔添加到索引時顯示的唯一引用。 此值用於索引中文檔的URL中。 </p> <p><span class="uicontrol">主鍵</span>值在由Index Connector配置表示的所有文檔中都必須是唯一的 — 將忽略所遇到的任何重複項。 如果源文檔不包含用作<span class="uicontrol">主鍵</span>的單個唯一值，但將兩個或多個欄位合併在一起<i>可以</i>形成唯一標識符，則可以通過組合多個<span class="uicontrol">標籤</span>定義和限定值的垂直條("|")來定義<span class="uicontrol">主鍵</span>。 </p> </li> 
      <li id="li_9F435EFB3EC74B409EC82A851824610G"> <span class="uicontrol"> 脫HTML?  </span> <p>核取此選項時，會移除在此欄位資料中找到的任何HTML標籤。 </p> </li> 
      <li id="li_6302D18971AD439FBECE27742649C56B"> <span class="uicontrol"> 動作 </span> <p>可讓您將列新增至地圖，或從地圖中移除列。 列的順序並不重要。 </p> </li> 
      </ul> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. （可選）按一下&#x200B;**[!UICONTROL Setup Maps]**&#x200B;下載資料來源的範例。 檢查資料以確定索引適用性。 此功能僅適用於文字和摘要類型。
1. （可選）按一下&#x200B;**[!UICONTROL Preview]**&#x200B;以測試配置的實際工作。 此功能僅適用於文字和摘要類型。
1. 按一下&#x200B;**[!UICONTROL Add]**&#x200B;將配置添加到[!DNL Index Connector Definitions]頁和[!DNL URL Entrypoints]頁上的[!DNL Index Connector Configurations]下拉清單中。

   請參閱[關於URL入口點](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573)。
1. 在[!DNL Index Connector Definitions]頁面上，按一下&#x200B;**[!UICONTROL rebuild your staged site index]**。
1. （選用）在[!DNL Index Connector Definitions]頁面上，執行下列任一操作：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以還原您所做的任何更改。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送階段設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 編輯索引連接器定義 {#task_DCFC9C6A9964421DB5AB6C25DEE98DE9}

您可以編輯已定義的現有「索引連接器」。

>[!NOTE]
>
>並非所有選項都可供您更改，例如[!DNL Type]下拉清單中的「索引連接器名稱」或「類型」。

**要編輯索引連接器定義**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**」。
1. 在[!DNL Index Connector]頁的[!DNL Actions]列標題下，按一下&#x200B;**[!UICONTROL Edit]**&#x200B;獲取要更改其設定的索引連接器定義名稱。
1. 在[!DNL Index Connector Edit]頁面上，設定您想要的選項。

   請參閱[添加索引連接器定義](../c-about-settings-menu/c-about-crawling-menu.md#task_96779B651A654E1F871F55D6DBBC8886)下的選項表。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）在[!DNL Index Connector Definitions]頁面上，按一下&#x200B;**[!UICONTROL rebuild your staged site index]**。
1. （選用）在[!DNL Index Connector Definitions]頁面上，執行下列任一操作：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以還原您所做的任何更改。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送階段設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 查看「索引連接器」定義的設定 {#task_D0B71A7426E54247BDB3468EC576D871}

您可以查看現有索引連接器定義的配置設定。

將「索引連接器」定義添加到[!DNL Index Connector Definitions]頁後，無法更改其「類型」設定。 請改為刪除定義，然後新增定義。

**查看「索引連接器」定義的設定**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**」。
1. 在[!DNL Index Connector]頁的[!DNL Actions]列標題下，按一下&#x200B;**[!UICONTROL Edit]**&#x200B;獲取要查看或編輯其設定的Index Connector定義名稱。

## 複製索引連接器定義 {#task_3AD55DF07FC44A748D0EFDAB7B35699B}

您可以複製現有的「索引連接器」定義，以用作要建立的新「索引連接器」的基礎。

複製Index Connector定義時，預設情況下會停用複製的定義。 若要啟用或「開啟」定義，必須從[!DNL Index Connector Edit]頁面編輯該定義，然後選取&#x200B;**[!UICONTROL Enable]**。

請參閱[編輯索引連接器定義](../c-about-settings-menu/c-about-crawling-menu.md#task_DCFC9C6A9964421DB5AB6C25DEE98DE9)。

**複製索引連接器定義**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**」。
1. 在[!DNL Index Connector]頁的[!DNL Actions]列標題下，按一下&#x200B;**[!UICONTROL Copy]**&#x200B;獲取要複製其設定的Index Connector定義名稱。
1. 在[!DNL Index Connector Copy]頁面上，輸入定義的新名稱。
1. 按一下 **[!UICONTROL Copy]**.
1. （選用）在[!DNL Index Connector Definitions]頁面上，執行下列任一操作：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以還原您所做的任何更改。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送階段設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 更名索引連接器定義 {#task_5132118FC21B47D99881E0ED425225D7}

可以更改現有「索引連接器」定義的名稱。

重新命名定義後，請檢查&#x200B;**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**。 要確保新定義名稱反映在[!DNL URL Entrypoints]頁面的下拉式清單中。

請參閱[新增多個要建立索引的URL入口點](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)。

**更名「索引連接器」定義**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**」。
1. 在[!DNL Index Connector]頁的[!DNL Actions]列標題下，按一下&#x200B;**[!UICONTROL Rename]**&#x200B;以獲取要更改的「索引連接器」定義名稱。
1. 在[!DNL Index Connector Rename]頁面的[!DNL Name]欄位中輸入定義的新名稱。
1. 按一下 **[!UICONTROL Rename]**.
1. 按一下「**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**」。 如果清單中存在以前的Index Connector名稱，請將其刪除，然後添加新更名的條目。

   請參閱[新增多個要建立索引的URL入口點](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45)。 1.（選用）在[!DNL Index Connector Definitions]頁面上，執行下列任一操作：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以還原您所做的任何更改。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送階段設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 刪除索引連接器定義 {#task_6B0BD5D0C09F4597A401B0F3AC7C7EA7}

您可以刪除不再需要或使用的現有「索引連接器」定義。

**刪除索引連接器定義**

1. 在產品功能表中，按一下「**[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]**」。
1. 在[!DNL Index Connector Definitions]頁的[!DNL Actions]列標題下，按一下&#x200B;**[!UICONTROL Delete]**&#x200B;以獲取要刪除的Index Connector定義名稱。
1. 在[!DNL Index Connector Delete]頁面上，按一下&#x200B;**[!UICONTROL Delete]**。
