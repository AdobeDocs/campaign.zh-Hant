---
title: 向鏡像頁面添加連結
description: 了解如何新增和管理鏡像頁面的連結
feature: Email
role: User
level: Beginner
source-git-commit: d8ceefe1dd56aecb810878d99395ac900f889c2e
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# 連結到鏡像頁{#mirror-page}

## 關於鏡像頁面{#about-mirror-page}

鏡像頁面是您電子郵件的線上版本。

雖然大部分的電子郵件用戶端都可以順利轉譯影像，但有些預設集可以避免因安全原因顯示影像。 使用者可以瀏覽至電子郵件的鏡像頁面，例如，當他們嘗試在收件匣中檢視時遇到轉譯問題或影像損毀時。 建議您基於協助工具原因提供線上版本，或鼓勵社交分享。

Adobe Campaign產生的鏡像頁面包含所有個人化資料。

![](assets/mirror-page-link.png)


## 向鏡像頁面添加連結{#link-to-mirror-page}

插入鏡像頁面的連結是一種好做法。 例如，此連結可以是「在瀏覽器中檢視此電子郵件」或「線上閱讀此內容」。 它通常位於電子郵件的標題或注腳。

在Adobe Campaign中，您可以使用專用 **個人化區塊**. 內建 **鏡像頁面的連結** 個人化區塊會在您的電子郵件內容中插入下列程式碼： `<%@ include view='MirrorPage' %>`.

<!--For more on personalization blocks insertion, refer to [Personalization blocks](personalization-blocks.md).-->

## 鏡像頁面生成{#mirror-page-generation}

依預設，如果電子郵件內容不為空，且包含鏡像頁面的連結（亦稱為鏡像連結），則Adobe Campaign會自動產生鏡像頁面。

您可以控制電子郵件鏡像頁面的產生模式。 傳遞屬性中提供選項。 若要存取這些選項：

1. 瀏覽至 **[!UICONTROL Validity]** 標籤。
1. 在 **鏡像頁面管理** 部分，檢查 **[!UICONTROL Mode]** 下拉式清單。

![](assets/mirror-page-generation.png)

除了預設模式外，還提供下列選項：

* **[!UICONTROL Force the generation of the mirror page]**:即使傳送中未插入鏡像頁面的連結，仍使用此模式來產生鏡像頁面。
* **[!UICONTROL Do not generate the mirror page]**:使用此模式可避免產生鏡像頁面，即使傳送中有連結亦然。
* **[!UICONTROL Generates a mirror page accessible using only the message identifier]**:使用此選項可在傳送記錄視窗中啟用對鏡像頁面內容及個人化資料的存取。 要訪問此鏡像頁面：傳送後，請開啟傳送並瀏覽至其 **[!UICONTROL Delivery]** 標籤。 選取收件者，然後按一下 **[!UICONTROL Display the mirror page for this message...]** 連結。 鏡像頁面會顯示在新索引標籤中。

