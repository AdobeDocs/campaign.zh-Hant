---
title: 新增個人化欄位
description: 瞭解如何在郵件內容中插入個性化資料
feature: Personalization
role: User
level: Beginner
exl-id: 14a741dd-794e-4760-bfa3-bafbe993a3f7
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 4%

---

# 新增個人化欄位{#personalization-fields}

根據為每個收件人設定的規則，使用個性化欄位以一對一的方式傳遞個性化內容。

個性化欄位是在個性化特定收件人的遞送時使用的單個資料欄位引用。 在傳遞分析階段插入實際資料值。

![消息個性化示例](assets/perso-name-sample.png)

## 語法

個性化標籤始終使用以下語法： `<%=table.field%>`。

例如，要插入儲存在收件人表中的收件人名稱，個性化欄位使用 `<%= recipient.lastName %>` 語法。

>[!CAUTION]
>
>個性化欄位內容不能超過1024個字元。

## 插入個人化欄位 {#insert-a-personalization-field}

要插入個性化欄位，請按一下可從任何標題、主題或消息正文欄位訪問的下拉表徵圖。

![插入個性化欄位](assets/perso-field-insert.png)

個性化欄位被插入，並準備由Adobe Campaign解釋：在消息準備期間，欄位將替換為給定收件人的值。

![電子郵件中的個性化欄位](assets/perso-fields-in-msg.png)

然後，可以在 **[!UICONTROL Preview]** 頁籤。

<!--Learn more about message preview in [this page]().-->

## 用例：個性化電子郵件 {#personalization-fields-uc}

在下面的使用案例中，瞭解如何使用收件人資料個性化電子郵件主題和正文：

1. 建立新的傳遞或開啟現有電子郵件傳遞。
1. 瀏覽到 **[!UICONTROL Subject]** 連結以編輯消息的主題。
1. 輸入「」 **特別優惠** 」，然後使用工具欄中的按鈕插入個性化欄位。 選取 **[!UICONTROL Recipients>Title]**。
1. 重複此操作以插入收件人的名稱。 在所有個性化欄位之間插入空格。
1. 按一下 **[!UICONTROL OK]** 驗證。
1. 在消息正文中插入個性化設定。 為此，請按一下消息內容，然後按一下欄位插入按鈕。
1. 選取 **[!UICONTROL Recipient>Other...]**。
1. 選擇要顯示的資訊的欄位，然後按一下 **[!UICONTROL OK]**。
1. 按一下 **[!UICONTROL Preview]** 頁籤。 必須選擇一個收件人以顯示該收件人的郵件。



## 教程視頻 {#personalization-field-video}

瞭解如何將個性化欄位添加到主題行以及以下視頻中電子郵件傳遞的內容。

>[!VIDEO](https://video.tv.adobe.com/v/24925?quality=12)
