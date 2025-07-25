---
title: 開始使用個人化
description: 瞭解如何個人化訊息內容
feature: Personalization
role: User
level: Beginner
exl-id: 1da45746-4d69-415b-a793-9a08ce80091d
source-git-commit: 3ac2976839f084761ba56647b282062d8d457ff2
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 48%

---

# 開始使用個人化 {#personalize-content}

為了充分運用每一次行銷活動，Adobe Campaign可讓您提供自訂內容，告訴客戶其層級的資訊。 根據設定檔資料、建立不同群組與個人自訂體驗的個人化功能：您可以運用您擁有的關於特定收件者的資料和資訊，根據每位收件者調整訊息。 這可以是他們的名字、興趣、居住地、購買內容等等。

Adobe Campaign簡化了個人化：您可以使用單一[訊息範本](create-templates.md)，顯示針對每個收件者自訂的不同內容型別。 在您的交易式訊息（例如購買確認或購物車放棄電子郵件）中，在單一電子郵件範本中包含每個人的產品清單資訊。


## Personalization策略 {#personalization-strategy}

使用 Campaign 建立動態內容並傳送個人化訊息。可合併個人化功能以改善您的訊息並建立自訂的使用者體驗。

您可以透過以下方式個人化訊息內容：

* 插入動態&#x200B;**個人化欄位**

  個人化欄位用於訊息的第一層個人化。您可以從個人化編輯器選取資料庫中的任何欄位。對於傳遞，您可以選取與收件者、訊息或傳遞相關的任何欄位。可將這些個人化屬性插入訊息的主旨行或內文中。[了解更多](personalization-fields.md)。

  以下語法將收件者城市插入您的內容：&lt;%= recipient.location.city %>。

* 插入預先定義的&#x200B;**內容區塊**

  Campaign 會隨附一組個人化區塊，其中包含您可以插入到傳遞中的特定呈現。例如，您可以新增標誌、問候訊息或訊息鏡像頁面的連結。內容區塊可從個人化編輯器的專屬項目取得。[了解更多](personalization-blocks.md)。

* 建立&#x200B;**條件式內容**

  例如，設定條件式內容以根據收件者的輪廓新增動態個人化。特定條件為真時，即可插入文字區塊及/或影像。[了解更多](conditions.md)。

<!--* Add **personalized offers**
    
    Insert personalized offers in your message content, depending on the recipient location, the current weather, or the last purchase order.
-->


## 護欄和建議{#perso-guardrails}

### Personalization逾時 {#perso-timeout}

若要改善傳送保護，您可以設定個人化階段的逾時期間。

在&#x200B;**[!UICONTROL Delivery properties]**&#x200B;的&#x200B;**[!UICONTROL Delivery]**&#x200B;索引標籤中，選取&#x200B;**[!UICONTROL Maximum personalization run time]**&#x200B;選項的最大值（以秒為單位）。

在預覽或傳送期間，如果個人化階段超過您在此欄位中設定的最大時間，則會中止程式並顯示錯誤訊息，且傳送失敗。

預設值為5秒。

如果您將此選項設為0，個人化階段將沒有時間限制。


### 內部變數{#internal-variables}

下列變數是可用於個人化的內部變數，但不可修改： **傳遞**、**訊息**、**資料來源**、**targetData**、**提供者**、**抵用券**、**抵用券值**、**主張**。


## 教學課程影片 {#personalization-video}

瞭解不同類型的動態內容，並瞭解如何建立個人化區塊和條件陳述式並套用至傳遞。


>[!VIDEO](https://video.tv.adobe.com/v/3452879?quality=12&captions=chi_hant)
