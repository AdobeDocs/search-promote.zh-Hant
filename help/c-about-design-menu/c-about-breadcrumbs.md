---
description: Breadcrumbs是您可新增至網站的導覽控制項。 網站導覽路徑標示可提供客戶在搜尋結果集中的意見回應。 此外，它還可協助他們快速返回上一步。
solution: Target
subtopic: Navigation
title: 關於Breadcrumbs
topic: Design,Site search and merchandising
uuid: 3e630a72-a631-4f4f-8aa5-adf2882cdf1c
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 1%

---


# 關於Breadcrumbs{#about-breadcrumbs}

Breadcrumbs是您可新增至網站的導覽控制項。 網站導覽路徑標示可提供客戶在搜尋結果集中的意見回應。 此外，它還可協助他們快速返回上一步。

## 使用Breadcrumbs {#concept_FB8A943C594A4A1593B118141DA61F03}

階層連結會追蹤搜尋的詞語以及選取以縮小結果集的後續刻面。

使用階層連結設定來自訂搜尋表現層的階層連結控制。 如果您的表現層有多組搜尋結果，則網路導覽路徑標示控制項會作用於頁面上的主要搜尋。

您可以編輯階層連結以變更預設行為、最大值寬度和值延伸值，並選取是否要包含查詢詞語。

## 新增階層連結{#task_2FFA94F82AE74F10BDDE7367CDCEAE8B}

您可以新增網站導覽路徑標示列，讓客戶可以追蹤他們在您網站上的位置。

<!-- 

t_adding_a_new_breadcrumb.xml

 -->

>[!NOTE]
>
>請確定您參考簡報範本中的階層連結，以便在網站上顯示。

**若要新增階層連結**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**」。
1. 在[!DNL Breadcrumbs]頁面上，按一下&#x200B;**[!UICONTROL Add Breadcrumb]**。
1. 在[!DNL Add Breadcrumb]頁面上，設定您想要的選項。

   這些設定會同時影響階層連結的行為和預設呈現方式。 您可以透過簡報範本的設定，覆寫其中一些設定。

   <!-- 
   
   r_breadcrumb_options.xml
    
    -->

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>選項 </p> </th> 
      <th colname="col2" class="entry"> <p>說明 </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>階層連結名稱 </p> </td> 
      <td colname="col2"> <p>階層連結的名稱。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>行為 </p> </td> 
      <td colname="col2"> <p>設定下列三種階層連結行為之一： </p> <p> 
      <ul id="ul_7E66ACC1DA494B20BEC3B0B2CCAB103A"> 
        <li id="li_D81876660A8B48AFB70D3317063FBF6F"> <span class="uicontrol"> Goto  </span> <p>Goto會移除點按後的所有網站導覽路徑標示，並在該點開始新搜尋。 </p> </li> 
        <li id="li_63AE06B544B64DCAA8C55031B3DFFFF7"> <span class="uicontrol"> 移除 </span> <p>從客戶點按的網站導覽路徑標示路徑中移除刪除，然後開始新搜尋。 當您想要讓客戶還原在搜尋中向下鑽取的步驟時，此行為很有用。 </p> </li> 
        <li id="li_EEC810D420FF41498ECE49EBAAB33BE5"> <span class="uicontrol"> 刪除  </span> <p>Drop會移除所有的網站導覽路徑。 </p> </li> 
      </ul> </p> <p> 例如，假設您的網站導覽路徑標示為1 &gt; 2 &gt; 3 &gt; 4。 當客戶點按「2」時，會根據您選擇的行為產生下列結果： </p> <p> 
      <ul id="ul_96FCD8E4C3704B45B59BC18A7A1AC52A"> 
        <li id="li_B880037088DF426F880788EAA3072180">移至- 1 &gt; 2 </li> 
        <li id="li_D0F07A15DCD043EFA4563632ED33A9E2">刪除- 1 &gt; 3 &gt; 4 </li> 
        <li id="li_D848ED44B4E44538AA92010F9F186224"> 刪除——整個網站導覽路徑標示被刪除，讓客戶在開始下鑽之前回到原點。 </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最大值寬度 </p> </td> 
      <td colname="col2"> <p>指定階層連結追蹤中每個值的長度。 您可將設定指定為數個字元。 </p> <p>例如，6的設定表示階層連結追蹤最長可有6個字元，包括空格。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>值延伸功能 </p> </td> 
      <td colname="col2"> <p>指定當網路導覽路徑標示被截斷時要使用的省略號。 </p> <p>預設為"。.." （橢圓）。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>包含查詢詞 </p> </td> 
      <td colname="col2"> <p>控制階層連結中查詢詞語的存在。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>啟用用戶定義的Crumbs </p> </td> 
      <td colname="col2"> <p>勾選可讓您使用URL中的<span class="codeph"> uX=[name]&amp;[name]=[value] </span>參數，在階層連結中使用使用者定義的項目。 您可以使用處理規則以您想要的方式處理此參數。 </p> <p>例如，若您已啟用此功能，而且您有URL <code> https://search.host.com/?1=category&amp;q1=Clothes&amp;u2= 
          type&amp;type=Men&amp;x3=kind&amp;q3=Sweater </code>（若您有Facet <span class="codeph"> <span class="varname">類別</span> </span>和<span class="codeph">類別</span> </span>），則您的導覽路徑標示看起來會像<span class="codeph">服裝&gt;男士&gt;毛衣</span>...<span class="varname"> </span></p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>使用者定義的Crumb名稱 </p> </td> 
      <td colname="col2"> <p>以逗號分隔，列出使用者定義之階層連結項目的所有可能名稱。 </p> <p>僅當選中<span class="uicontrol">啟用用戶定義的路徑包</span>時，此選項才可用。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 按一下 **[!UICONTROL Add]**.
1. （可選）在[!DNL Breadcrumbs]頁面上，執行下列其中一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 編輯階層連結{#task_583481D9A23E4E0F97AEB18E72CBE13F}

您可以編輯已新增之任何網路導覽路徑標示的設定。

<!-- 

t_editing_a_breadcrumb.xml

 -->

>[!NOTE]
>
>請確定您參考簡報範本中的階層連結，以便在網站上顯示。

**若要編輯階層連結**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**」。
1. 在[!DNL Breadcrumbs]頁面上，按一下階層連結名稱最右側的&#x200B;**[!UICONTROL Edit]**。
1. 在[!DNL Edit Breadcrumb]頁面上，設定您想要的選項。

   請參閱[新增階層連結](../c-about-design-menu/c-about-breadcrumbs.md#task_2FFA94F82AE74F10BDDE7367CDCEAE8B)下的選項表。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）在&#x200B;**[!UICONTROL Breadcrumb]**&#x200B;頁面上，執行下列其中一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 刪除導覽路徑標示{#task_401C6E481A744284906E15A29E04F757}

您可以刪除已新增的任何網路導覽路徑標示。

<!-- 

t_deleting_a_breadcrumb.xml

 -->

**若要刪除階層連結**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**」。
1. 在[!DNL Breadcrumbs]頁面上，按一下階層連結名稱最右側的&#x200B;**[!UICONTROL Delete]**。
1. 在[!DNL Confirmation]對話框中，按一下&#x200B;**[!UICONTROL OK]**。
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

