---
title: 個人化欄位
description: 了解如何在訊息內容中插入個人化資料
feature: Personalization
role: User
level: Beginner
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 3%

---


# 個人化欄位{#personalization-fields}

根據您為每個收件者設定的規則，使用個人化欄位以一對一方式提供個人化內容。

個人化欄位是個人化特定收件者傳送時所使用的單一資料欄位參考。 實際資料值會在傳遞分析階段插入。

![訊息個人化範例](assets/perso-name-sample.png)

## 語法

個人化標籤一律使用下列語法： `<%=table.field%>`.

例如，若要插入儲存在收件者表格中的收件者名稱，個人化欄位會使用 `<%= recipient.lastName %>` 語法。

>[!CAUTION]
>
>個人化欄位內容不能超過1024個字元。

## 插入個人化欄位 {#insert-a-personalization-field}

若要插入個人化欄位，請按一下可從任何標題、主旨或訊息內文欄位存取的下拉式圖示。

![插入個人化欄位](assets/perso-field-insert.png)

個人化欄位會插入，且可供Adobe Campaign解讀：在訊息準備期間，欄位會取代為指定收件者的值。

![電子郵件中的個人化欄位](assets/perso-fields-in-msg.png)

接著，您可在 **[!UICONTROL Preview]** 標籤。

<!--Learn more about message preview in [this page]().-->

## 使用案例：個人化電子郵件主旨 {#personalization-fields-uc}

在以下使用案例中，了解如何使用收件者資料個人化電子郵件主旨和內文：

1. 建立新傳送或開啟現有的電子郵件傳送。
1. 瀏覽至 **[!UICONTROL Subject]** 連結以編輯訊息的主旨。
1. 輸入&quot; **特別優惠** 「 」，並使用工具列中的按鈕來插入個人化欄位。 選取 **[!UICONTROL Recipients>Title]**。
1. 重複此操作以插入收件者的名稱。 在所有個人化欄位之間插入空格。
1. 按一下 **[!UICONTROL OK]** 以驗證。
1. 在訊息內文中插入個人化。 要執行此操作，請按一下訊息內容中的，然後按一下欄位插入按鈕。
1. 選取 **[!UICONTROL Recipient>Other...]**。
1. 選取包含要顯示之資訊的欄位，然後按一下 **[!UICONTROL OK]**.
1. 按一下 **[!UICONTROL Preview]** 標籤來檢視個人化結果。 您必須選取收件者才能顯示該收件者的訊息。



## 教學課程影片 {#personalization-field-video}

透過下列影片，了解如何將個人化欄位新增至主旨行，以及電子郵件傳送的內容。

>[!VIDEO](https://video.tv.adobe.com/v/24925?quality=12)

