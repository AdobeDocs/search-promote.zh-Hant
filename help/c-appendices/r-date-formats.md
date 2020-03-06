---
description: 您可以定義當日期格式解析任何具有「日期」資料類型的欄位並索引時所使用的日期格式。
seo-description: 您可以定義當日期格式解析任何具有「日期」資料類型的欄位並索引時所使用的日期格式。
seo-title: 日期格式
solution: Target
title: 日期格式
topic: Appendices,Site search and merchandising
uuid: 148914b5-33ef-41db-8404-67c03f6f0832
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# 日期格式{#date-formats}

您可以定義當日期格式解析任何具有「日期」資料類型的欄位並索引時所使用的日期格式。

日期和時間的格式以格式字串指定。 格式字串由零個或多個轉換規範（轉換規範由百分比符號和一個其它字元組成）和普通字元組成。 每個日期欄位會提供日期格式字串的預設清單。

您可完全控制此清單，並可依您網站的需求新增或修改清單。 頂層格式字串優先，而後續格式字串只有在剖析特定中繼資料標籤的內容產生錯誤時才使用。

例如，假設您已指定下列日期格式：

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%B %d,%Y %T %Z </p> <p>%b %d,%Y %T %Z </p> <p>%A %B %d, %Y %T %Z </p> <p>%A %b %d,%Y %T %Z </p> <p>%a %B %d, %Y %T %Z </p> <p>%a %b %d, %Y %T %Z </p> <p>%d %b %Y %T %Z </p> </td> 
  </tr> 
 </tbody> 
</table>

第一個格式「%B %d, %Y %T %Z」與下列「2014年9月20日13:12:00 PDT」之類的日期相符。 如果無法使用此格式字串解析元資料標籤內容，則嘗試下一個可用格式&quot;%b %d, %Y %T %Z&quot;。 此格式符合下列日期：「2014年9月20日3:12:00 PDT」。 如果無法使用此格式字串剖析中繼資料標籤內容，網站搜尋／銷售會下移格式字串清單，直到找到有效的格式字串為止。

下表說明可用的日期格式字串：

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>資料格式 </p> </th> 
   <th colname="col2" class="entry"> <p>說明 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%A </p> </td> 
   <td colname="col2"> <p>相符項目：完整工作日名稱的國家代表，例如「星期一」。 國家代表性是根據"字詞和語言"選項上的"語言"設定確定的 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a </p> </td> 
   <td colname="col2"> <p> 相符項目：縮寫工作日名稱的國家代表，其中縮寫為前三個字元，例如"Mon." 國家代表性是根據"字詞和語言"選項上的"語言"設定確定的 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%B </p> </td> 
   <td colname="col2"> <p> 相符項目：全月名稱的國家代表，例如「6月」。 國家代表性是根據"字詞和語言"選項上的"語言"設定確定的 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%b </p> </td> 
   <td colname="col2"> <p> 相符項目：縮寫月份名稱的國家代表，其中縮寫是前三個字元，例如「6月」。 國家代表性是根據"字詞和語言"選項上的"語言"設定確定的 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%D </p> </td> 
   <td colname="col2"> <p> 等效於"%m/%d/%y"，例如"06/06/01" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%d </p> </td> 
   <td colname="col2"> <p> 與當月的某天相符，為小數(01-31) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%e </p> </td> 
   <td colname="col2"> <p> 將月中的某天與小數數相符(1-31);位數前面有空白 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%H </p> </td> 
   <td colname="col2"> <p> 與小時（24小時時鐘）相符，為小數(00-23) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%h </p> </td> 
   <td colname="col2"> <p> 相符項目：縮寫月份名稱的國家代表，其中縮寫是前三個字元，例如"Jun"（與%b相同） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%I </p> </td> 
   <td colname="col2"> <p> 與小時（12小時時鐘）相符，為小數(01-12) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%j </p> </td> 
   <td colname="col2"> <p> 與年中的某天相匹配，作為小數數(001-366) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%k </p> </td> 
   <td colname="col2"> <p> 將小時（24小時時鐘）與小數(0-23)相匹配；位數前面有空白 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%l </p> </td> 
   <td colname="col2"> <p> 將小時（12小時時鐘）與小數(1-12)相匹配；位數前面有空白 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%M </p> </td> 
   <td colname="col2"> <p> 與分鐘比對為小數(00-59) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%m </p> </td> 
   <td colname="col2"> <p> 與月份相符，為小數(01-12) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%p </p> </td> 
   <td colname="col2"> <p> 符合"ante meridiem"或"post meridiem"的國家代表，例如"PM." 國家代表性是根據"字詞和語言"選項上的"語言"設定確定的 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%R </p> </td> 
   <td colname="col2"> <p> 等效於"%H:%M"，例如"13:23" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%r </p> </td> 
   <td colname="col2"> <p> 等效於"%I:%M:%S %p"，例如。"01:23:45 PM" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%S </p> </td> 
   <td colname="col2"> <p> 將第二個數字與十進位數字匹配(00-60) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%T </p> </td> 
   <td colname="col2"> <p> 等效於"%H:%M:%S"，例如"13:26:47" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%U </p> </td> 
   <td colname="col2"> <p> 與年份的周數（星期日為一週的第一天）相符，並以小數數(00-53)表示 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%v </p> </td> 
   <td colname="col2"> <p> 等效於"%e-%b-%Y"，例如"2001年6月6日" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Y </p> </td> 
   <td colname="col2"> <p> 與以十進位數字表示的世紀相符，例如《2001年》 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%y </p> </td> 
   <td colname="col2"> <p> 與沒有世紀的年份相匹配，作為小數(00-99) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Z </p> </td> 
   <td colname="col2"> <p> 與時區名稱相符 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%% </p> </td> 
   <td colname="col2"> <p> matches "%" </p> </td> 
  </tr> 
 </tbody> 
</table>

**預設格式字串**

範本使用下列預設格式字串。 您可以新增至此清單，或視需要加以編輯。

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>預設格式字串 </p> </th> 
   <th colname="col2" class="entry"> <p>產生的範例 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%B %d,%Y %T %Z </p> </td> 
   <td colname="col2"> <p> 1999年9月5日13點12分0秒 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%b %d,%Y %T %Z </p> </td> 
   <td colname="col2"> <p> 1999年9月5日13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%A %B %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> 星期日1999年9月5日13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%A %b %d,%Y %T %Z </p> </td> 
   <td colname="col2"> <p> 星期日1999年9月5日13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a %B %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> 1999年9月5日13時12分00秒(PDT) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a %b %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> 1999年9月5日13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%d %b %Y %T %Z </p> </td> 
   <td colname="col2"> <p> 1999年9月5日13:12:00 PDT </p> </td> 
  </tr> 
 </tbody> 
</table>

