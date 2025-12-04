---
title: 追蹤個人化連結
description: 瞭解如何在電子郵件中追蹤個人化連結
feature: Personalization
role: User
level: Beginner
exl-id: d0e00b40-e7dd-4484-b37c-fd3f3ac70fda
source-git-commit: 6e465ec24f72d0b30c4fc287da5d4c4bcaeda05b
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 2%

---

# 追蹤個人化連結 {#tracking-personalized-links}

電子郵件內容中包含個人化的連結需要追蹤特定語法。

在電子郵件內容(HTML或文字)中使用JavaScript，可讓您產生動態內容並傳送給收件者，但有兩個限制：

* 指令碼無法直接存取資料庫（無法使用SQL函式和API函式），
* Adobe Campaign必須能夠偵測URL，以便追蹤連結。

## 前置處理指示 {#pre-processing-instructions}

您可以新增特定的前置處理指示，以便為URL編寫指令碼並加以追蹤。 這些指示必須以JavaScript撰寫並以`<%@`開頭。

例如：

```
<%@ value object="myObject" xpath="@myField" %>
```

此指示會從`myField`物件擷取`myObject`欄位的值。

## url偵測 {#url-detection}

為了追蹤偵測，Adobe Campaign會嵌入[Tidy](https://www.html-tidy.org/)以剖析HTML來源並偵測模式。 它會列出內容的所有URL，以便可以個別追蹤。 Adobe Campaign再次使用Tidy，將URL (`http://myurl.com`)取代為指向Adobe Campaign重新導向伺服器的URL。

例如，在初始內容中： `http://myurl.com/a.php?name=<%=escapeUrl(recipient.lastName)%>`會取代為下列特定收件者： `http://emailing.customer.com/r/?id=h617791,71ffa3,71ffa8&p1=CustomerName`

其中：

* 「h」表示HTML內容（或「t」表示文字內容）。
* 617791是訊息ID / broadLog ID （十六進位）。
* 71ffa3是NmsDelivery ID （十六進位）。
* 71ffa8是NmsTrackingUrl ID （十六進位）。
* p1、p2等都是URL中要取代的引數。

### 非偵測範例 {#non-detection-example}

`<%= getURL("http://mynewsletter.com") %>`運作並透過電子郵件傳送網頁的實際內容給收件者。 但系統不會追蹤任何連結。 原因在於MTA在傳送前會針對每封電子郵件執行`"<%=getURL(..."`。 每個收件者的URL可能不同，因此Adobe Campaign無法得知要追蹤的URL，也無法為其指派標籤ID。

當所有收件者的下載頁面均相同時，最佳實務為使用：

```
<%@ include url="http://mynewsletter.com" %>
```

在此情況下，頁面會在分析期間、追蹤偵測之前下載。 它可讓Adobe Campaign探索連結、指派標籤ID及追蹤連結。

### 建議的模式 {#recommended-pattern}

在處理`<%@`指示後，要追蹤的URL應具有下列語法：

```
<a href="http://myurl.com/a.php?param1=aaa&param2=<%=escapeUrl(recipient.xxx)%>&param3=<%=escapeUrl(recipient.xxx)%>">
```

>[!IMPORTANT]
>
>Adobe不支援所有其他模式，應避免使用，以防止潛在的安全性缺口。

## URL 參數 {#url-parameters}

為確保正確追蹤個人化URL，您必須對URL中的引數使用`escapeUrl()`函式或適當的編碼方法。

**範例：**

```
<a href="http://myurl.com/a.php?name=<%=escapeUrl(recipient.lastName)%>">Click here</a>
```

這可確保Adobe Campaign正確編碼及追蹤個人化引數。

## 與`<%@ foreach %>`循環 {#foreach}

`<%@ foreach %>`指示可讓您反複處理載入傳遞中的物件陣列，以追蹤與物件相關的個別連結。

### 語法

```
<%@ foreach object="myObject" xpath="myLink" index="3" item="myItem" %>
  <!-- Content to repeat -->
<%@ end %>
```

**引數：**

* **`object`**：要開始的物件名稱（通常是額外的指令碼物件，但可以是傳遞）
* **`xpath`** （選用）：要回圈的集合的XPath。 預設值為「。」，表示物件是要重複播放的陣列
* **`index`** （選用）：如果xpath不是&quot;。&quot; 而且物件本身是陣列，物件的專案索引（從0開始）
* **`item`** （選用）：可在foreach回圈內使用`<%@ value %>`存取的新物件名稱。 預設為綱要中的連結名稱

### 範例

在傳遞屬性/個人化中，載入一系列文章以及收件者和文章之間的關係表。

您可以顯示這些文章的連結以及個別追蹤：

```
<%@ foreach object="articleList" item="article" %>
  <a href="http://example.com/article.jsp?id=<%@ value object="article" xpath="@id" %>">
    <%@ value object="article" xpath="@title" %>
  </a>
<%@ end %>
```

這可讓Adobe Campaign追蹤每個收件者點按了哪些特定文章，而非僅追蹤是否點按了文章連結。

## 最佳實務 {#best-practices}

* 一律使用`escapeUrl()`函式處理動態URL引數
* 當您需要追蹤集合中的個別專案時使用`<%@ foreach %>`
* 傳送傳遞前請先測試追蹤，確保所有連結正常運作
* 驗證個人化連結在傳遞內容中的格式是否正確
* 檢查追蹤記錄，確認可正確擷取個人化引數

## 相關主題 {#related-topics}

* [瞭解如何設定追蹤的連結](tracked-links.md)
* [瞭解如何設定URL追蹤選項](url-tracking.md)
* [瞭解如何新增個人化欄位](personalization-fields.md)

