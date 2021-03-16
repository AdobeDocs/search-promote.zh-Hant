---
description: 您可以使用功能表來自訂您的表現層。
solution: Target
subtopic: Navigation
title: 關於功能表
topic: 設計、網站搜尋與銷售
uuid: 011050cd-21b6-4150-9503-18fa3f771626
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 1%

---


# 關於菜單{#about-menus}

您可以使用功能表來自訂您的表現層。

## 使用菜單{#concept_68123CE5CF4447B59217B5D721424E32}

新增對應至搜尋內設定的功能表。 功能表內的每個項目都指定功能表設定的值。 您也可以自訂功能表標籤。

在簡報範本中，您可以參考已定義的功能表。 然後，您可將它們放入任何您想要的HTML元件中，例如選取控制項。 此組合可讓使用者自訂其搜尋結果。 支援三種功能表類型：排序、計數和導覽。

## 添加新菜單{#task_EE171532D3AE477FAFE8C2F4077A6D73}

您可以新增功能表，以對應至搜尋結果中的設定。

<!-- 

t_adding_a_new_menu.xml

 -->

>[!NOTE]
>
>請確定您參考簡報範本中的功能表，以便在網站上顯示。

**若要新增功能表**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Menus]**」。
1. 在[!DNL Menus]頁面上，按一下&#x200B;**[!UICONTROL Add New Menu]**。
1. 在[!DNL Add Menu]頁面上，設定您想要的選項。

   這些設定會同時影響階層連結的行為和預設呈現方式。 您可以透過簡報範本的設定，覆寫其中一些設定。

   請參閱[關於菜單](../c-about-design-menu/c-about-menus.md#concept_68123CE5CF4447B59217B5D721424E32)。

   <!-- 
   r_add_menu_options.xml
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
      <td colname="col1"> <p>功能表名稱 </p> </td> 
      <td colname="col2"> <p>功能表名稱。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>功能表類型 </p> </td> 
      <td colname="col2"> <p>設定以下三種菜單類型之一： </p> <p> 
      <ul id="ul_7E66ACC1DA494B20BEC3B0B2CCAB103A"> 
      <li id="li_D81876660A8B48AFB70D3317063FBF6F"> <span class="uicontrol"> 排序  </span> <p>依您定義的中繼資料類型來組織您的搜尋。 </p> <p>例如，您可以定義具有下列中繼資料類型的排序功能表：三項關聯性；自訂的中繼資料欄位，例如可用性代碼；和價格。 這三個項目可分別標示為「依關聯性排序」、「依可用性排序」和「依價格排序」。 當您將此項目加入簡報範本中時，客戶可以使用此控制項來排序其搜尋結果。 </p> </li> 
      <li id="li_63AE06B544B64DCAA8C55031B3DFFFF7"> <span class="uicontrol"> 計數 </span> <p>定義要顯示的搜尋結果數。 此菜單類型映射到cgi參數<span class="varname"> sp_c </span>。 </p> <p>請參閱<a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" format="dita" scope="local">後端搜尋CGI參數</a>。 </p> </li> 
      <li id="li_EEC810D420FF41498ECE49EBAAB33BE5"> <span class="uicontrol"> 導覽 </span> <p>指定一組與功能表項目關聯的靜態URL。 通常，導覽功能表用於在搜尋結果頁面上建立頂層導覽列。 </p> <p>例如，您可以建立包含女性、男性、男孩和女孩的選單，其中選單項目會類似下列： 
      <code>
        /?q1=womens;x1=gender 
      </code>, 
      <code>
        /?q1=mens;x1=gender 
      </code> </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>銷售 </p> 
        <!--DONT' KNOW WHAT THIS DOES--> </td> 
      <td colname="col2"> <p>只有在選擇菜單類型<span class="uicontrol">排序時，此選項才可用。</span> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>功能表中的項目數 </p> </td> 
      <td colname="col2"> <p>指定功能表中的項目數。 變更此設定會新增或刪除表單中的欄位。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>預設項目 </p> </td> 
      <td colname="col2"> <p>可讓您選取預設顯示的功能表項目。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>項目值 </p> </td> 
      <td colname="col2"> <p>項目值取決於您所設定的功能表類型。 </p> 
        <ul id="ul_2F14E6AA673640578A2D5161FD9D13EF"> 
        <li id="li_5017EC6E4ACB4B8E99E0AA61CBAAFFAE"> 排序菜單類型 <p>識別選單中選取的項目應依哪些項目排序。 選取的項目會填入可排序的中繼資料欄位。 </p> <p>對於單一項目，您可以依三個中繼資料欄位排序。 排序依指定順序進行。 </p> </li> 
        <li id="li_CC6BAFBF969C4367A71B55F08E0758D1"> 計數功能表類型 <p>可讓您指定客戶選擇此功能表項目時要傳回的結果數。 </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>項目標籤 </p> </td> 
      <td colname="col2"> <p>項目標籤取決於您所設定的菜單類型。 </p> 
        <ul id="ul_957BF01235F84748B5EB7062D6AEAC41"> 
        <li id="li_03FB2E2C96134A2B8E08154F87F0CD55"> 排序菜單類型 <p>識別您希望客戶在功能表中檢視此項目時看到的自訂標籤。 </p> </li> 
        <li id="li_C9FE2BC46D9443FB85FEB837C7CA45E1"> 計數功能表類型 <p>標識要為此菜單項顯示的自定義標籤。 </p> </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

1. 按一下 **[!UICONTROL Add]**.
1. （可選）在[!DNL Menus]頁面上，執行下列其中一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 編輯菜單{#task_0770DBFD0C7046169097FB6F771B9114}

您可以編輯已新增功能表的設定。

<!-- 

t_editing_a_menu.xml

 -->

>[!NOTE]
>
>請確定您參考簡報範本中的功能表，以便在網站上顯示。

**若要編輯功能表**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Menus]**」。
1. 在[!DNL Menus]頁面上，按一下功能表名稱最右側的&#x200B;**[!UICONTROL Edit]**。
1. 在[!DNL Edit Menu]頁面上，設定您想要的選項。

   請參閱[新增功能表](../c-about-design-menu/c-about-menus.md#task_EE171532D3AE477FAFE8C2F4077A6D73)下的選項表。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）在[!DNL Menus]頁面上，執行下列其中一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 刪除菜單{#task_645E212311A045CD8D9D906878165F47}

您可以刪除任何已新增的功能表。

<!-- 

t_deleting_a_menu.xml

 -->

**刪除菜單**

1. 在產品功能表上，按一下「**[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Menus]**」
1. 在[!DNL Menus]頁面上，按一下功能表名稱最右側的&#x200B;**[!UICONTROL Delete]**。
1. 在[!DNL Confirmation]對話框中，按一下&#x200B;**[!UICONTROL OK]**。
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

