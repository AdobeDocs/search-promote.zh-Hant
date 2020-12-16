---
description: 直接點擊可讓您在客戶搜尋相符詞語時，將客戶重新導向至指定的URL。 這類功能可讓您改善網站搜尋的導覽。
seo-description: 直接點擊可讓您在客戶搜尋相符詞語時，將客戶重新導向至指定的URL。 這類功能可讓您改善網站搜尋的導覽。
seo-title: 關於直接點擊
solution: Target
title: 關於直接點擊
topic: Rules,Site search and merchandising
uuid: 374d63c8-2b82-4165-b543-05b587757baa
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 1%

---


# 關於直接點擊{#about-direct-hits}

直接點擊可讓您在客戶搜尋相符詞語時，將客戶重新導向至指定的URL。 這類功能可讓您改善網站搜尋的導覽。

## 使用直接點擊{#concept_C5EE074A19FD4D5B8DD21DB575E35565}

直接點擊由兩個主要元素組成：網站的URL，以及一或多個逗號分隔搜尋詞。 直接點擊的指定方式如下：

```
    website_URL: term
    website_URL: term, term, term
```

例如，假設您的公司網站包含指定您所有條款及條件的頁面。 當客戶搜尋您的條款與條件，而非顯示結果時，您可以將客戶重新導向至您的條款與條件頁面。

```
    https://www.mycompany.com/policies.asp?article=terms: terms and conditions, terms, conditions, security
    https://www.mycompany.com/press/news.asp: press releases, press
```

如果查詢詞語不符合任何直接點擊，則會以一般方式傳回搜尋結果。

## 設定直接點擊{#task_64DFB8C554874C699FCC0C2F26C3669F}

您可以指定將網頁瀏覽器重新導向至URI的搜尋詞，而不是傳回搜尋結果。

<!-- 

t_configuring_direct_hits.xml

 -->

允許以「#」（雜湊）字元開頭的空白行和註解行。

**若要設定直接點擊**

1. 在產品功能表上，按一下「**[!UICONTROL Rules]** > **[!UICONTROL Direct Hits]**」。
1. 在[!DNL Direct Hits]欄位中，輸入您網站的URL，以及一或多個逗號分隔的搜尋詞。
1. 按一下 **[!UICONTROL Save Changes]**.
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

## 測試直接點擊{#task_1E2EA833BF90423AA0DD8C5BBFE77445}

在即時推播直接點擊規則之前，您可以輸入詞語來測試直接點擊。

<!-- 

t_testing_direct_hits.xml

 -->

如果您測試直接點擊規則未涵蓋的詞語，會顯示訊息，告知您。 在這種情況下，如果直接點擊規則在您的網站上即時顯示，搜尋結果會照常傳回。 如果您測試直接點擊規則涵蓋的詞語，會顯示訊息，告知您已發生重新導向至指定URL。

**若要測試直接點擊**

1. 在產品功能表上，按一下「**[!UICONTROL Rules]** > **[!UICONTROL Direct Hits]**」。
1. 在[!DNL Test Direct Hits]欄位中輸入搜尋詞，然後按一下&#x200B;**[!UICONTROL Test]**。
1. （可選）執行下列任一項作業：

   * 按一下&#x200B;**[!UICONTROL History]**&#x200B;以回復您所做的任何變更。

      請參閱[使用歷史記錄選項](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)。

   * 按一下 **[!UICONTROL Live]**.

      請參閱[檢視即時設定](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)。

   * 按一下 **[!UICONTROL Push Live]**.

      請參閱[推送舞台設定live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)。

