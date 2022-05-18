---
title: 與運動和Adobe Target合作
description: 瞭解如何與Campaign和Adobe Target合作
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 891a9a87-f3a4-405a-87ed-a7703be90a67
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 1%

---

# 與運動和Adobe Target合作

連接活動和目標，將Adobe Target的優惠包括在Adobe Campaign電子郵件中。

此整合可幫助您實施以下使用案例：當收件人開啟通過Adobe Campaign發送的電子郵件時，通過呼叫Adobe Target，您可以顯示內容的動態版本。 根據建立電子郵件時預先指定的規則計算此動態版本。

>[!NOTE]
>整合僅支援靜態映像。 其他類型的內容無法個性化。

![](../assets/do-not-localize/speech.png)  作為托管Cloud Services用戶， [聯繫人Adobe](../start/campaign-faq.md#support) 使用市場活動實施Experience Cloud觸發器。

以下資料類型可供Adobe Target使用：

* Adobe Campaign資料庫的資料
* 連結到Adobe Target的訪問者ID的段，僅當使用的資料不受法律限制時
* Adobe Target資料：用戶代理、 IP地址、地理定位資料

## 插入動態內容

在下面的示例中，您將學習如何整合 **動態報價** 從Adobe Target轉到Adobe Campaign。

我們希望建立一個消息，其影像將根據接收國動態更改。 資料隨每個郵箱請求一起發送，並取決於訪問者的IP地址。

在此電子郵件中，我們希望其中一個映像根據以下用戶體驗動態變化：

* 電子郵件在法國開啟。
* 電子郵件在美國開啟。
* 如果這些條件均不適用，則顯示預設影像。

![](assets/target_4.png)

Adobe Campaign和Adobe Target需要採取以下步驟：

1. [在電子郵件中插入動態優惠](#inserting-dynamic-offer)
1. [建立重定向服務](#create-redirect-offers)
1. [建立對象](#audiences-target)
1. [建立針對活動的體驗](#creating-targeting-activity)
1. [預覽併發送消息](#preview-send-email)

### 在電子郵件中插入動態優惠 {#inserting-dynamic-offer}

在Adobe Campaign，定義您的電子郵件的目標和內容。 可以插入來自Adobe Target的動態影像。

為此，請指定預設影像的URL、位置名稱以及要傳輸到Adobe Target的欄位。

在Adobe Campaign，有兩種方法可將動態映像從Target插入電子郵件：

* 如果使用數字內容編輯器，請選擇現有影像並選擇 **[!UICONTROL Insert]** > **[!UICONTROL Dynamic image served by Adobe Target]** 的子菜單。

   ![](assets/target_5.png)

* 如果使用標準編輯器，請將游標置於要插入影像的位置，然後選擇 **[!UICONTROL Include]** > **[!UICONTROL Dynamic image served by Adobe Target...]** 按鈕。

   ![](assets/target_12.png)

然後，可以定義影像參數：

* 的 **[!UICONTROL Default image]**&#39;s URL是當未滿足任何條件時將顯示的影像。 也可以從「資產」庫中選擇影像。
* 的 **[!UICONTROL Target location]** 是您動態報價位置的名稱。 您必須在Adobe Target活動中選擇此位置。
* 的 **[!UICONTROL Landing Page]** 允許您將預設影像重定向到預設登錄頁。 此URL僅在最終電子郵件中顯示預設影像時才適用。 這是可選的。
* 的 **[!UICONTROL Additional decision parameters]**  定義在Adobe Target段中定義的欄位和Adobe Campaign欄位之間的映射。 使用的Adobe Campaign欄位必須已在原框中指定。 在我們的示例中，我們添加了Country欄位。

如果在Adobe Target的設定中使用企業權限，請在此欄位中添加相應的屬性。 瞭解有關中目標企業權限的詳細資訊 [此頁](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html?lang=en#administer)。

![](assets/target_13.png)

### 建立重定向服務 {#create-redirect-offers}

在Adobe Target，您可以建立不同版本的產品。 根據每個用戶體驗，可以建立重定向服務，並指定將顯示的影像。

在我們的情況下，我們需要兩個重定向優惠，第三個（預設）優惠將在Adobe Campaign定義。

1. 要在目標標準中建立新重定向服務，請從 **[!UICONTROL Content]** 按鈕 **[!UICONTROL Code offers]**。

1. 按一下 **[!UICONTROL Create]**，之後 **[!UICONTROL Redirect Offer]**。

   ![](assets/target_9.png)

1. 輸入聘用的名稱和影像的URL。

   ![](assets/target_6.png)

1. 對於剩餘的重定向服務，請遵循相同的步驟。 如需關於此項目的詳細資訊，請參閱此[頁面](https://experienceleague.adobe.com/docs/target/using/experiences/offers/offer-redirect.html?lang=en#experiences)。

### 建立對象 {#audiences-target}

在Adobe Target，您需要建立兩個受眾，訪問您產品的人員將根據要交付的不同內容進行分類。 對於每個受眾，添加一個規則以定義誰將能夠查看此優惠。

1. 要在「目標」中建立新受眾，請從 **[!UICONTROL Audiences]** 按鈕 **[!UICONTROL Create Audience]**。

   ![](assets/audiences_1.png)

1. 將名稱添加到您的受眾。

   ![](assets/audiences_2.png)

1. 按一下 **[!UICONTROL Add a rule]** 選擇一個類別。 規則使用特定標準來針對訪問者。 可以通過添加條件或在其他類別中建立新規則來細化規則。

1. 對其餘觀眾執行相同的步驟。

### 建立針對活動的體驗 {#creating-targeting-activity}

在Adobe Target，我們需要建立「體驗目標」活動，定義不同的體驗，並將它們與相應的優惠關聯起來。

首先，您需要定義受眾：

1. 要建立「體驗目標」活動，請從 **[!UICONTROL Activities]** 按鈕 **[!UICONTROL Create Activity]** 然後 **[!UICONTROL Experience Targeting]**。

   ![](assets/target_10.png)

1. 選擇 **[!UICONTROL Form]** 如 **[!UICONTROL Experience Composer]**。

1. 通過按一下 **[!UICONTROL Change audience]** 按鈕

   ![](assets/target_10_2.png)

1. 選擇在前面的步驟中建立的受眾。

   ![](assets/target_10_3.png)

1. 通過按一下 **[!UICONTROL Add Experience Targeting]**。

然後為每個受眾添加內容：

1. 選擇在Adobe Campaign插入動態優惠時選擇的位置名稱。

   ![](assets/target_15.png)

1. 按一下下拉按鈕並選擇 **[!UICONTROL Change Redirect Offer]**。

   ![](assets/target_content.png)

1. 選擇您以前建立的重定向服務。

   ![](assets/target_content_2.png)

1. 按照同樣的步驟進行第二次體驗。

的 **[!UICONTROL Target]** 窗口匯總了您的活動。 如有必要，可添加其他體驗。

![](assets/target_experience.png)

的 **[!UICONTROL Goal & Settings]** 窗口允許您通過設定優先順序、目標或持續時間來個性化活動。

的 **[!UICONTROL Reporting Settings]** 部分，用於選擇操作並編輯將確定何時實現目標的參數。

![](assets/target_experience_2.png)

## 預覽併發送消息 {#preview-send-email}

在Adobe Campaign，您現在可以預覽電子郵件並在不同收件人上test其呈現。

您會注意到影像會根據建立的不同體驗而改變。

您現在已準備好發送電子郵件，包括來自目標的動態優惠。

![](assets/target_20.png)
