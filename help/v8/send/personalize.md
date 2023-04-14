---
title: 開始使用個人化
description: 了解如何個人化訊息內容
feature: Personalization
role: User
level: Beginner
exl-id: 1da45746-4d69-415b-a793-9a08ce80091d
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 7%

---

# 開始使用個人化 {#personalize-content}

為了充分運用每個行銷活動，Adobe Campaign提供您一種方式，可提供對客戶層級的客戶講話的自訂內容。 根據設定檔資料，為不同群組和個人建立自訂體驗的個人化功能：您可以運用您擁有的相關資料和資訊，調整訊息以適應每個特定收件者。 這可以是他們的名字，興趣，住的地方，他們買的東西，等等。

Adobe Campaign簡化個人化：您可以使用單一 [電子郵件範本](create-templates.md). 在您的交易式訊息（例如購買確認或購物車放棄電子郵件）中，將每個個人的產品清單資訊納入單一電子郵件範本中。


## 個人化策略 {#personalization-strategy}

使用Campaign建立動態內容並傳送個人化訊息。 可結合個人化功能，以改善訊息並建立自訂使用者體驗。

您可以透過以下方式個人化訊息內容：

* 插入動態 **個人化欄位**

   個人化欄位是用於訊息的第一層級個人化。 您可以從個人化編輯器中選取資料庫中可用的任何欄位。 對於傳遞，您可以選取與收件者、訊息或傳遞相關的任何欄位。 這些個人化屬性可插入主旨行或訊息內文中。 [了解更多資訊](personalization-fields.md)。

   下列語法會將收件者的城市插入內容中：&lt;%= recipient.location.city %>。

* 插入預定義 **內容區塊**

   Campaign隨附一組個人化區塊，其中包含您可插入至傳送的特定轉譯。 例如，您可以新增標誌、問候訊息或訊息鏡像頁面的連結。 內容區塊可從個人化編輯器中的專用項目使用。 [了解更多資訊](personalization-blocks.md)。

* 建立 **條件內容**

   例如，設定條件式內容以根據收件者的設定檔新增動態個人化。 當特定條件為true時，會插入文字區塊和/或影像。 [了解更多資訊](conditions.md)。

<!--* Add **personalized offers**
    
    Insert personalized offers in your message content, depending on the recipient location, the current weather, or the last purchase order.
-->


## 護欄和建議{#perso-guardrails}

### 個人化逾時{#perso-timeout}

若要改善傳送保護，您可以為個人化階段設定逾時期間。

在 **[!UICONTROL Delivery]** 的 **[!UICONTROL Delivery properties]**，請為 **[!UICONTROL Maximum personalization run time]** 選項。

在預覽或傳送期間，如果個人化階段超過您在此欄位中設定的時間上限，程式會因錯誤訊息而中止，且傳送會失敗。

預設值為5秒。

如果將此選項設為0，則個人化階段不會有時間限制。


### 內部變數{#internal-variables}

下列變數是可用於個人化但不可修改的內部變數： **傳遞**, **訊息**, **dataSource**, **targetData**, **提供者**, **抵用券**, **couponValue**, **命題**.


## 教學課程影片 {#personalization-video}

瞭解不同類型的動態內容，並瞭解如何建立個人化區塊和條件陳述式並套用至傳遞。


>[!VIDEO](https://video.tv.adobe.com/v/335734?quality=12)
