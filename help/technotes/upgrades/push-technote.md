---
product: campaign
title: 推播通知頻道近期變更
description: 推播通知頻道近期變更
hide: true
hidefromtoc: true
source-git-commit: 70d1e7336cce7660890b13def5efcb614c0dc12e
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# 推播通知頻道近期變更 {#push-upgrade}

Firebase Cloud Messaging (FCM)服務有重大變更，可能會影響您的Adobe Campaign Classic實施。

為Google持續改善服務，舊版FCM API將於2024年6月終止服務([Firebase雲端通訊HTTP通訊協定](https://firebase.google.com/docs/cloud-messaging/http-server-ref))

這些API目前與Adobe Campaign Classic整合，可傳送推播通知訊息。 我們瞭解許多客戶（例如您）仰賴這些服務來行銷活動和通訊需求，尤其是Android裝置。

## 您有受到影響嗎？

* **HTTP （舊版） API使用者**：如果您的任何作用中推播通知行銷活動使用HTTP （舊版） API，此變更將直接影響您的設定。 我們強烈建議您檢閱目前的設定，並為移轉至較新API做準備。

* **HTTP v1 API使用者的好消息**：如果您的設定專門針對Android推播通知使用HTTP v1 API，則您已符合規範，不需要採取任何進一步動作。

## 我們在做什麼？

* **轉換計畫**：我們的團隊正積極致力於開發全方位的轉換計畫。 這將確保您可視需要將實作更新為較新的FCM API (已在最新版本的Adobe Campaign中提供)，並將對行銷活動造成的影響降至最低。

* **詳細指示**：我們將提供逐步指南和其他資源，以利順暢的轉換流程。

* **支援**：我們的客戶支援團隊將全程協助您進行轉換。 我們可能也會舉辦網路研討會及賦權研討會，以涵蓋轉換的技術層面及最佳實務。

## 我們希望您能提供什麼？

* **隨時掌握最新資訊**：留意您的收件匣，以便與我們進一步通訊，包括詳細的轉換計畫。

* **檢閱目前的設定**：請檢閱您目前的Adobe Campaign Classic設定和自訂，以準備視需要進行任何必要的變更。

* **聯絡我們**：如果您有任何急迫的疑慮或問題，請隨時聯絡我們的支援團隊。

## 實施步驟

未來幾週，我們將分享舊版FCM API之轉換計畫的更多詳細資訊，包括時間表和動作專案。 放心，我們的主要目標是讓您和您的團隊儘可能順暢地完成轉換。

我們感謝您的業務，感謝您對我們這些變更的理解。 您的成功是我們的首要任務，我們致力於為您提供每一步的支援。

為了讓您能夠預見變更，以下是將推送設定從HTTP （舊版）移轉至FCM HTTPv1 API所需的一般步驟。

### 版本編號升級

* Campaign Classic： 20.3.1版本已新增支援HTTPv1。 如果您使用舊版，必須先升級至最新的Campaign Classic版本編號。

* Campaign v8：所有Campaign v8版本都支援HTTPv1。 不需要升級。

### 行銷伺服器

客戶/合作夥伴可執行設定變更。

1. 首先，您需要擷取JSON檔案。 需要Firebase Admin SDK服務的帳戶JSON檔案，才能將行動應用程式移至HTTPv1。 請參閱此 [頁面](https://firebase.google.com/docs/admin/setup#initialize-sdk).

1. 導覽至您的清單 **服務與訂閱**.

1. 使用HTTP （舊版） API版本找出所有行動應用程式。

1. 針對這些行動應用程式，設定 **API版本** 至HTTPv1，並遵循 [檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html).

>[!NOTE]
>
>新傳遞時將考慮切換至HTTPv1 API。 重試、進行中及使用中的傳遞仍會使用HTTP （舊版） API。

### 中間來源伺服器

不需要變更。

### 即時執行伺服器

您需要聯絡Adobe Campaign支援以取得此資訊。 移轉程式與行銷伺服器的相同。

### Android作業系統和Android行動應用程式

Android行動應用程式的程式碼不需要特定變更，且通知行為不應變更。

不過，HTTPv1也推出了三個新的裝載元素：

| 名稱 | 預設值 |
|---|---|
| 粘性 | 假 |
| 優先順序 | 預設 |
| 可見度 | 假 |
| 粘性 | 私人 |
