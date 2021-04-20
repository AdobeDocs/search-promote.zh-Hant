---
description: 您可以設定「您的意思是」，讓客戶在嘗試失敗的搜尋時獲得有效搜尋詞的建議。 建議是透過尋找拼字並輸入導致有效搜尋之搜尋詞的修正來形成。
solution: Target
title: 你是說
topic: Linguistics,Site search and merchandising
uuid: c5973541-3d6b-4fc9-bad4-66d4d3559fe8
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 2%

---


# 關於你是說{#about-did-you-mean}

您可以設定「您的意思是」，讓客戶在嘗試失敗的搜尋時獲得有效搜尋詞的建議。 建議是透過尋找拼字並輸入導致有效搜尋之搜尋詞的修正來形成。

## 設定您是指{#task_B539D6A0043547EFB1CA19B67E762371}

當客戶的查詢傳回無或最小搜尋結果時，您可以量身打造[!DNL site search/merchandising]的搜尋建議方式。

<!-- 

t_configuring_did_you_mean.xml

 -->

**若要設定您是指**

1. 在產品功能表上，按一下「**[!UICONTROL Linguistics]** > **[!UICONTROL Did You Mean]**」。
1. 在[!DNL Did You Mean]頁面的&#x200B;**「從建議中移除這些字詞」文字欄位中，輸入空格或行分隔字詞以篩選不想要的建議。**

   這些是您的搜尋索引中不顯示為建議替代搜尋詞的字詞。 您可以透過使用規則運算式來排除任何與模式相符的字詞。 否則，只會移除確切的字詞。

1. 設定您想要的&#x200B;**Did You Mean**&#x200B;選項。

   <!-- 
   
   r_did_you_mean_options.xml
   
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
      <td colname="col1"> <p>建議演算法 </p> </td> 
      <td colname="col2"> <p>調整軟體找到建議的距離。 如果使用者犯了一個字母錯誤，所有演算法都會提出相同的建議。 原因是只要進行一次編輯，就能得到有效的建議，而所有演算法都會尋找接近原始的字詞。 但當原始搜尋詞與索引中的現有詞語不類似時，<b>Deep</b>和<b>Bad Spellers</b>建議演算法會繼續搜尋可能的建議。 如果客戶嘗試難以輸入的正確名稱，而且他們發出聲音，則此方案很實用。 但是，如果您只想顯示類似的建議，則可以選擇<b>Quick</b>演算法。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>要顯示的建議預設計數 </p> </td> 
      <td colname="col2"> <p>指定當客戶的搜尋未傳回結果時，您要顯示的「您平均」詞語建議(0-20)數目。 預設值為 3。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>建議字詞長度最小 </p> </td> 
      <td colname="col2"> <p>Prunes Did You Mean詞語，指定建議字詞的最少字母數。 </p> <p>例如，如果您將值設為4，軟體不會建議使用長度為1、2或3個字元的字詞。 如果您指定值0，則不會從詞語建議中移除任何短字。 如果您指定高值，通常不會產生任何詞語建議。 預設值為 3。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>最小索引頻率 </p> </td> 
      <td colname="col2"> <p> 指定單字在納入「您的意思」字典之前，必須出現在索引中的最小次數。 </p> <p>您無法在欄位中指定負數。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>如果沒有結果，請搜尋建議詞 </p> </td> 
      <td colname="col2"> <p>當客戶的搜尋未產生任何結果且至少有一個「您是指」詞語建議時，自動重新搜尋第一個建議詞語。 </p> <p>您可以在簡報範本中使用下列標籤，指出網站搜尋／銷售會自動搜尋不同的詞語： </p> <p> <code>&nbsp;&lt;guided-if-suggestion-autosearch&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Search&nbsp;for&nbsp;&lt;guided-param&nbsp;gsname="q"&nbsp;/&gt;&nbsp;instead&nbsp;of&nbsp;guided-suggestion-original-query&nbsp;/&gt;&nbsp;&lt;/guided-if-suggestion-autosearch&gt;</code> </p> <p>您也可以在此顯示其他建議。 </p> <p> <code>&nbsp;&lt;guided-if-suggestion-autosearch&gt;&nbsp;&nbsp;There&nbsp;was&nbsp;0&nbsp;matches&nbsp;for&nbsp;&lt;guided-suggestion-original-query&nbsp;/&gt;&nbsp;&nbsp;&nbsp;Did&nbsp;You&nbsp;Mean&nbsp;&lt;guided-param&nbsp;gsname="q"&gt;?&nbsp;Here&nbsp;are&nbsp;the&nbsp;results&nbsp;for&nbsp;that&nbsp;search.&nbsp;&nbsp;&nbsp;Or&nbsp;Did&nbsp;You&nbsp;Mean&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestions&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestion-link&gt;&lt;guided-suggestion&nbsp;/&gt;&lt;/guided-suggestion-link&gt;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-suggestions&gt;&nbsp;&lt;/guided-if-suggestion-autosearch&gt;</code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>因結果不佳而建議 </p> </td> 
      <td colname="col2"> <p>如果客戶搜尋的詞語產生少於10個結果，搜尋引擎會檢查其是否有可產生超過100個結果的建議。 如果有，您可以使用下列標籤向使用者指出，雖然使用者有結果，但他們可能想要搜尋其他項目： </p> <p> <code>&nbsp;&lt;guided-if-suggestion-low-results&gt; &nbsp;&nbsp;You&nbsp;have&nbsp;a&nbsp;low&nbsp;result&nbsp;count&nbsp;for&nbsp;&lt;Search&nbsp;for&nbsp;guided-param&nbsp;gsname="q"&gt;.&nbsp;&nbsp;Did&nbsp;you&nbsp;mean:&nbsp;&lt;guided-suggestion&gt;&lt;guided-suggestion-link&gt;&lt;guided-suggestion&nbsp;/&gt;&lt;/guided-suggestion-link&gt;&lt;guided-if-not-last&gt;,&nbsp;&lt;/guided-if-not-last&gt;&lt;/guided-suggestions&gt;&nbsp;&lt;/guided-if-suggestion-low-results&gt;</code> </p> <p> 在上述案例中，建議數量由<span class="uicontrol">預設建議計數中指定的值控制，以顯示</span>。 低和高閾值可由以下選項進行配置。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>在初始結果少於 </p> </td> 
      <td colname="col2"> <p>控制系統開始提供建議時的結果數。 </p> <p>只有當您勾選<span class="uicontrol"> 「由於結果低而建議」時，才會顯示此選項。</span> </p> <p>預設值為 10。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>建議至少必須產生這麼多結果 </p> </td> 
      <td colname="col2"> <p>依據主要搜尋結果計數篩選因結果低而提出的建議。 </p> <p>只有當您勾選<span class="uicontrol"> 「由於結果低而建議」時，才會顯示此選項。</span> </p> <p>預設值為 100。 </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. 按一下&#x200B;**「儲存變更」**。
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

