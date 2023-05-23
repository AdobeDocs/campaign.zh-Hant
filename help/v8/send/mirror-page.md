---
title: 新增鏡像頁面連結
description: 了解如何新增和管理鏡像頁面連結
feature: Email
role: User
level: Beginner
exl-id: 7bf3937c-484d-4404-8a9b-de7a10f5455a
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 57%

---

# 連結至鏡像頁面{#mirror-page}

## 關於鏡像頁{#about-mirror-page}

鏡像頁面是您電子郵件的線上版本。

雖然大部分電子郵件用戶端可以正確轉譯影像，但是某些預設集可以基於安全原因避免顯示影像。使用者可以瀏覽到電子郵件的鏡像頁面，例如他們在嘗試在收件匣中檢視郵件時遇到轉譯問題或影像毀損。我們建議基於存取性原因或鼓勵社交共享，提供線上版本。

Adobe Campaign 產生的鏡像頁面包含所有個人化資料。

![鏡像連結範例](assets/mirror-page-link.png){width="600" align="left"}

## 新增鏡像頁面連結{#link-to-mirror-page}

插入鏡像頁面連結是很好的做法。例如，此連結可以是「在瀏覽器中檢視此電子郵件」或「線上閱讀」。它通常位於電子郵件的頁首或頁尾。

在 Adobe Campaign 中，您可以使用專屬 **個人化區塊**，將鏡像頁面連結插入電子郵件中。內建的&#x200B;**鏡像頁面連結**&#x200B;個人化區塊會將以下程式碼插入電子郵件內容中：`<%@ include view='MirrorPage' %>`。

![](assets/mirror-page-insert.png){width="800" align="left"}


有關自定義內容塊插入的詳細資訊，請參閱 [個性化塊](personalization-blocks.md)。

## 鏡像頁面產生{#mirror-page-generation}

依預設，如果電子郵件內容不是空的且包含鏡像頁面連結 (也稱為鏡像連結)，Adobe Campaign 會自動產生鏡像頁面。

您可以控制電子郵件鏡像頁面的產生模式。傳遞屬性中有提供相關選項。要訪問這些選項：

1. 瀏覽到 **[!UICONTROL Validity]** 頁籤。
1. 在 **鏡像頁面管理** 的 **[!UICONTROL Mode]** 的下界。

![](assets/mirror-page-generation.png){width="800" align="left"}

除了預設模式，還提供以下選項：

* **[!UICONTROL Force the generation of the mirror page]**:即使在傳遞中未插入到鏡像頁的連結，也使用此模式來生成鏡像頁。
* **[!UICONTROL Do not generate the mirror page]**:使用此模式可避免生成鏡像頁，即使該連結在傳遞中存在。
* **[!UICONTROL Generates a mirror page accessible using only the message identifier]**:如果電子郵件內容中不存在鏡像頁面連結，則使用此選項可以在傳遞日誌窗口中啟用對鏡像頁面內容的訪問，如下所述。

## 檢查收件人的鏡像頁面{#mirror-page-access}

您可以使用個性化資料存取傳送的特定收件人的鏡像頁的內容。

要訪問此鏡像頁：

1. 發送交貨後，開啟它並瀏覽到其 **[!UICONTROL Delivery]** 頁籤。

1. 選擇收件人，然後按一下 **[!UICONTROL Display the mirror page for this message...]** 的子菜單。

   ![](assets/mirror-page-display.png){width="800" align="left"}

   鏡像頁顯示在專用螢幕中，其中包含所選收件人的個性化資料。
