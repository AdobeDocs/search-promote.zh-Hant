---
description: 關於構造規則運算式的語法和規則的更新。
solution: Target
title: 規則運算式
topic: Appendices,Site search and merchandising
uuid: 369b54f6-372a-41de-bb5d-3ae0bd640199
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 1%

---


# 規則運算式{#regular-expressions}

關於構造規則運算式的語法和規則的更新。

另請參閱[配置分段網站的增量索引](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0)。

**規則運算式的語法**

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>文字</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>任何單一字元 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> [字元] </p> </td> 
   <td colname="col3"> <p> 字元類別：字元之一 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> [^chars] </p> </td> 
   <td colname="col3"> <p>字元類別：無字元 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> text1|text2 </p> </td> 
   <td colname="col3"> <p> 替代方案：text1或text2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>量詞</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> ? </p> </td> 
   <td colname="col3"> <p> 前文的0或1 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> * </p> </td> 
   <td colname="col3"> <p> 0或N(N &gt; 1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> + </p> </td> 
   <td colname="col3"> <p>1或N(N &gt; 1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>分組</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> (text) </p> </td> 
   <td colname="col3"> <p> 對文本進行分組，以設定替代項的邊框，或在RewriteRule的RHS上使用N組且為$N的位置返回引用) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>錨點</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> ^ </p> </td> 
   <td colname="col3"> <p> 行錨點的開始。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> $ </p> </td> 
   <td colname="col3"> <p> 行尾錨點。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>逃跑</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> </p> </td> 
   <td colname="col2"> <p>\char </p> </td> 
   <td colname="col3"> <p>請逸出特定字元。 例如，要指定字元''。[]()"等。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**規則運算式規則**

* 普通字元（不是下文所述之特殊字元之一）是與自身相符的單字元規則運算式。
* 反斜線(\)後面跟任何特殊字元是符合特殊字元本身的單字元規則運算式。 特殊字元包括：

   * `.` （句點）、 `*` （星號）、 `?` （問號）、 `+` （加號）、 `[` （左方括弧）、 `|` （垂直管道）和 `\` （反斜線）都是特殊字元，除非它們出現在方括弧內。
   * `^` （脫字元號或抑揚符號）在規則運算式的開頭或緊接在一對方括弧的左側時特別。
   * `$` （美元符號）在規則運算式結尾處是特別的。
   * `.` (period)是一個單字元的規則運算式，可比對任何字元，包括新行除外的輔助程式碼集字元。
   * `[ ]`（左方括弧和右方括弧）中包含的非空字串是一個單字元規則運算式，它與該字串中的一個字元（包括補充代碼集字元）匹配。

      但是，如果字串的第一個字元是`^`（抑揚符號），則單字元規則運算式會比對任何字元，包括輔助程式碼集字元，但字串中的新行和其餘字元除外。

      `^`只有在字串中出現時，才會有此特殊含義。 您可以使用`-`（減號）來指出連續的字元範圍，包括輔助程式碼集字元。 例如，[0-9]等於[0123456789]。

      指定範圍的字元必須來自相同的程式碼集。 當字元來自不同的程式碼集時，會比對指定範圍的其中一個字元。 如果`-`是在字串中出現的第一個（在初始`^`之後，如果有的話）或最後一個，則會遺失此特殊含義。 當`]`（右方括弧）是字串中的第一個字元時，若有，`^`初始字元後不會終止此字串。 例如，`[]a-f]`與`]`（右方括弧）或其中一個ASCII字母a到f（含）匹配。 上面列為特殊字元的四個字元，代表在這樣一串字元中。

**從單字規則表達式構造規則表達式的規則**

您可以使用下列規則，從單字元規則運算式建構規則運算式：

* 單字元規則運算式是與單字元規則運算式相符的規則運算式。
* 一字元規則運算式，後跟`*`（星號）是一個規則運算式，可比對零或多個單字元規則運算式，該運算式可以是輔助程式碼集字元。 如果有任何選擇，則會選擇允許相符項目的最左側最長字串。
* 一字元規則運算式，後面接著`?`（問號）是一個規則運算式，可比對單字元規則運算式的零或一次，該運算式可以是輔助程式碼集字元。 如果有任何選擇，則會選擇允許相符項目的最左側最長字串。
* 一字元規則運算式，後跟`+`（加號）是一個規則運算式，可比對一或多個單字元規則運算式，該運算式可為補充程式碼集字元。 如果有任何選擇，則會選擇允許相符項目的最左側最長字串。
* 一字元規則運算式，後面接著`{m}`、`{m,}`或`{m,n}`，是符合單字元規則運算式發生範圍的規則運算式。 m和n的值必須是小於256的非負整數；`{m}`與m個匹配；`{m,}`至少符合m次；`{m,n}`符合m和n（含）之間的任意次數。 每當有選項存在時，規則運算式會盡可能多地匹配。
* 規則運算式的串連是規則運算式，與規則運算式中每個元件所匹配之字串的串連相符。
* 字元序列（和）之間包含的規則運算式是與任何樸素規則運算式匹配的規則運算式。
* 後跟`|`（垂直管道）的規則運算式是與第一個規則運算式（垂直管道之前）或第二個規則運算式（垂直管道之後）匹配的規則運算式。

您也可以限制規則運算式，使其僅匹配線的初始段或最終段，或兩者皆匹配。

* 規則運算式開頭的`^`（抑揚符號）會限制該規則運算式以符合行的初始區段。
* 整個規則運算式結尾的`$`（貨幣符號）會限制該規則運算式以符合行的最後一段。
* 構造^規則運算式$會限制規則運算式以符合整行。

有些預先定義的字元類別名稱，可用來取代複雜括弧的規則運算式。 例如，一個數字可以由單字元規則運算式[0-9]或由字元類單字元規則運算式[[:digit:]]表示。

預定義字元類及其含義如下：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>字元類別 </p> </th> 
   <th colname="col2" class="entry"> <p>含義 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> [[:alnum:]] </p> </td> 
   <td colname="col2"> <p> 字母字元或數字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:alpha:]] </p> </td> 
   <td colname="col2"> <p>字母字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:空白:]] </p> </td> 
   <td colname="col2"> <p>空格或標籤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:cntrl:]] </p> </td> 
   <td colname="col2"> <p> 控制碼；非列印字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:dig:]] </p> </td> 
   <td colname="col2"> <p>數字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[：圖：]] </p> </td> 
   <td colname="col2"> <p> 任何列印字元（空格除外）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:lower:]] </p> </td> 
   <td colname="col2"> <p>小寫字母字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[：打印：]] </p> </td> 
   <td colname="col2"> <p> 任何列印字元，包括空格。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:punct:]] </p> </td> 
   <td colname="col2"> <p> 標點符號。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:空格:]] </p> </td> 
   <td colname="col2"> <p> 空格，例如空格、標籤或行尾。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[：上：]] </p> </td> 
   <td colname="col2"> <p> 大寫字母字元。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:xdig:]] </p> </td> 
   <td colname="col2"> <p> 十六進位數字，大寫或小寫。 </p> </td> 
  </tr> 
 </tbody> 
</table>

兩個特殊字元類名稱與單字開頭和結尾處的空值空格相匹配。 換言之，它們不符合實際字元。 單字被視為字母字元、數字或下划線(_)的任意序列。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>字元類別 </p> </th> 
   <th colname="col2" class="entry"> <p>含義 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> [[:&lt;:]] </p> </td> 
   <td colname="col2"> <p> 一字開頭 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:&gt;:]] </p> </td> 
   <td colname="col2"> <p>結尾 </p> </td> 
  </tr> 
 </tbody> 
</table>

