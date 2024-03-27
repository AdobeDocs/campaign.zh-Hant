---
title: 新增個人化欄位
description: 瞭解如何在訊息內容中插入個人化資料
feature: Personalization
role: User
level: Beginner
exl-id: 14a741dd-794e-4760-bfa3-bafbe993a3f7
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 4%

---

# 新增個人化欄位{#personalization-fields}

使用個人化欄位，根據您為每個收件者設定的規則，以一對一的方式提供個人化內容。

個人化欄位是將特定收件者的傳遞個人化時使用的單一資料欄位參考。 實際資料值會在傳遞分析階段插入。

![訊息個人化範例](assets/perso-name-sample.png)

## 語法

個人化標籤一律會使用以下語法： `<%=table.field%>`.

例如，若要插入儲存在收件者表格中的收件者名稱，個人化欄位會使用 `<%= recipient.lastName %>` 語法。

>[!CAUTION]
>
>個人化欄位內容不可超過1024個字元。

## 插入個人化欄位 {#insert-a-personalization-field}

若要插入個人化欄位，請按一下可從任何標題、主旨或郵件內文欄位存取的下拉式圖示。

![插入個人化欄位](assets/perso-field-insert.png)

已插入個人化欄位，並準備好由Adobe Campaign進行解譯：在訊息準備期間，欄位將取代為指定收件者的值。

![電子郵件中的個人化欄位](assets/perso-fields-in-msg.png)

然後可以在以下位置測試此替代方案： **[!UICONTROL Preview]** 標籤。

<!--Learn more about message preview in [this page]().-->

## 使用案例：個人化電子郵件主旨 {#personalization-fields-uc}

在下列使用案例中，瞭解如何使用收件者資料個人化電子郵件主旨與內文：

1. 建立新傳遞或開啟現有的電子郵件傳遞。
1. 瀏覽至 **[!UICONTROL Subject]** 編輯訊息主旨的連結。
1. 輸入&quot; **特別優惠** 」並使用工具列中的按鈕插入個人化欄位。 選取 **[!UICONTROL Recipients>Title]**。
1. 重複操作以插入收件者的名稱。 在所有個人化欄位之間插入空格。
1. 按一下 **[!UICONTROL OK]** 以進行驗證。
1. 在訊息本文中插入個人化。 若要這麼做，請按一下訊息內容中的，然後按一下欄位插入按鈕。
1. 選取 **[!UICONTROL Recipient>Other...]**。
1. 選取包含要顯示的資訊的欄位，然後按一下 **[!UICONTROL OK]**.
1. 按一下 **[!UICONTROL Preview]** 標籤以檢視個人化結果。 您必須選取收件者以顯示該收件者的訊息。



## 教學課程影片 {#personalization-field-video}

在下列影片中瞭解如何將個人化欄位新增至主旨行，以及電子郵件傳送的內容。

>[!VIDEO](https://video.tv.adobe.com/v/24925?quality=12)
