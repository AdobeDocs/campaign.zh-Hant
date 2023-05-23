---
title: 開始使用個人化
description: 瞭解如何個性化消息內容
feature: Personalization
role: User
level: Beginner
exl-id: 1da45746-4d69-415b-a793-9a08ce80091d
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 36%

---

# 開始使用個人化 {#personalize-content}

為了充分利用每一次營銷活動，Adobe Campaign為您提供了一種方法，讓您能夠在客戶級別上向客戶提供定制內容。 基於配置檔案資料，個性化功能可為不同的組和個人建立定制體驗：您可以利用您擁有的有關郵件的資料和資訊，將郵件調整為每個特定收件人。 它可以是他們的名字，興趣，住在哪裡，他們買了什麼，等等。

Adobe Campaign簡化了個性化：您可以使用單個收件人顯示為每個收件人定製的不同類型的內容 [電子郵件模板](create-templates.md)。 在事務性消息（如購買確認或購物車放棄電子郵件）中，在單個電子郵件模板中包括每個個人的產品清單資訊。


## 個性化策略 {#personalization-strategy}

使用「市場活動」可建立動態內容併發送個性化消息。 可以合併個性化功能來改進您的消息並建立自定義用戶體驗。

您可以透過以下方式個人化訊息內容：

* 插入動態&#x200B;**個人化欄位**

   個人化欄位用於訊息的第一層個人化。您可以從個人化編輯器選取資料庫中的任何欄位。對於傳遞，您可以選取與收件者、訊息或傳遞相關的任何欄位。這些個人化屬性可以插入訊息的主旨行或內文中。[了解更多](personalization-fields.md)。

   以下語法將收件者城市插入您的內容：&lt;%= recipient.location.city %>。

* 插入預先定義的&#x200B;**內容區塊**

   Campaign 隨附一組個人化區塊，其中包含您可以插入到傳遞中的特定轉譯。例如，您可以新增標誌、問候訊息或訊息鏡像頁面的連結。內容區塊可從個人化編輯器的專屬項目取得。[了解更多](personalization-blocks.md)。

* 建立 **條件內容**

   配置條件內容以添加基於收件人配置檔案的動態個性化設定。 當特定條件為true時插入文本塊和/或影像。 [了解更多](conditions.md)。

<!--* Add **personalized offers**
    
    Insert personalized offers in your message content, depending on the recipient location, the current weather, or the last purchase order.
-->


## 護欄和建議{#perso-guardrails}

### 個性化超時{#perso-timeout}

要改進交付保護，您可以設定個性化階段的超時時間。

在 **[!UICONTROL Delivery]** 頁籤 **[!UICONTROL Delivery properties]**，為 **[!UICONTROL Maximum personalization run time]** 的雙曲餘切值。

在預覽或發送期間，如果個性化階段超過您在此欄位中設定的最長時間，則進程將中止，並顯示錯誤消息，傳遞將失敗。

預設值為5秒。

如果將此選項設定為0，則個性化階段將沒有時間限制。


### 內部變數{#internal-variables}

以下變數是可用於個性化設定但不能修改的內部變數： **交貨**。 **消息**。 **資料源**。 **目標資料**。 **提供程式**。 **優惠**。 **優惠券值**。 **命題**。


## 教程視頻 {#personalization-video}

瞭解不同類型的動態內容，並瞭解如何建立個人化區塊和條件陳述式並套用至傳遞。


>[!VIDEO](https://video.tv.adobe.com/v/335734?quality=12)
