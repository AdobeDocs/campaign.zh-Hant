---
title: 電子郵件追蹤畫素和CNIL指引
description: 瞭解CNIL更新的電子郵件追蹤畫素指南，以及可支援法規遵循工作的Adobe Campaign功能。
feature: Overview
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7, Campaign Standard
hide: true
source-git-commit: d30c11b245b8ad7735a8e45efb2c5fdbe936a97b
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 1%

---


# 瞭解CNIL更新的電子郵件追蹤畫素指南

這篇文章僅供參考。 這不是法律建議，也不保證您遵守適用法律。 底下所述的Adobe Campaign產品功能是建置區塊，若妥善設定和運作，可支援相容的實作。 每位客戶都有責任決定及遵守其適用法律義務。

## 概觀

在2026年4月14日，法國資料保護機構&#x200B;_全國資訊與自由委員會_ (CNIL)發佈了一項關於在電子郵件中使用追蹤畫素的[建議](https://www.cnil.fr/sites/default/files/2026-04/recommandation-pixels_de_suivi.pdf)。 此指引澄清何時需要同意，並強調正確同意實務對於電子郵件畫素追蹤的重要性。 此政策可能會影響任何實體傳送電子郵件給法國訂閱者的傳送實務。

CNIL從建議之日起提供三個月的時間，讓公司通知其電子郵件收件者（「使用者」）追蹤畫素的存在、其目的和使用者選擇退出的權利。 在此轉換期間，客戶應通知使用者畫素追蹤的相關資訊，並視需要提供選擇退出。 預計CNIL將在2026年7月14日之後開始執行活動。

隨著CNIL和其他監管機構釐清追蹤畫素和相關問題的指引，Adobe將繼續監控更新，並通知客戶支援Adobe Campaign等電子郵件行銷的Adobe產品的技術功能。

Adobe電子郵件行銷執行應用程式，包括Adobe Journey Optimizer、Journey Optimizer B2B、Adobe Campaign和Marketo Engage，可提供可協助客戶在傳送或電子郵件層級管理開啟追蹤的控制項。 根據適用的CNIL指引和其他法律，客戶有責任決定自己的合規義務，但這些功能可能會支援客戶合規工作。

## 什麼是電子郵件追蹤畫素

電子郵件追蹤畫素是內嵌在電子郵件HTML中的1x1透明影像。 收件者的電子郵件使用者端載入該影像時，畫素會偵測伺服器並記錄時間戳記、裝置型別、電子郵件使用者端等資料，有時還會偵測大致位置的IP位址。 然後，該記錄會繫結至收件者的記錄，讓行銷人員檢視電子郵件是否已開啟。

## 客戶支援

尋求協助實作上述變更的客戶可與其現有的Adobe生態系統互動。 如有關於所引用Adobe功能的技術問題，請聯絡您的客戶成功經理或技術客戶經理。

## 與電子郵件追蹤相關的Adobe Campaign功能

客戶在設定架構以處理CNIL指引時，可以使用Adobe Campaign的原生追蹤、結構和個人化機制來處理某些元素：

* **傳遞的分類。** 使用`emailType`屬性（驗證、僅傳遞能力、異動、行銷、公共服務、B2B潛在客戶）延伸`nms:delivery`。 分類會未經同意而允許使用哪些畫素。

* **同意擷取。** 以各用途同意結構延伸`nms:recipient`，其中包含措辭版本、時間戳記、擷取來源及有效期。 擴充登錄檔單和偏好設定中心，以便與電子郵件選擇加入分開收集畫素同意。

* **畫素發射。** 為每個畫素定義一個`NmsTracking_OpenFormula`用途（驗證、傳遞能力、效能、設定檔分析、詐騙偵測）。 傳遞型別規則會根據emailType和收件者的各用途同意，選取要發出的公式。 個人化區塊會封裝邏輯，使邏輯不會存在於個別創意中。

* **撤回。** 將&#x200B;**管理追蹤器偏好設定**&#x200B;連結新增至每個電子郵件頁尾，區別於取消訂閱連結。 連結指向透過`idTracking`驗證的`nms:webApp`登陸頁面；收件者只要按一下即可撤銷同意，無需重新輸入其電子郵件地址。 新增至標準&#x200B;**追蹤**&#x200B;工作流程的篩選步驟可防止在撤回後重新開啟先前傳遞的電子郵件。

* **同意證明。** 擷取每個同意事件在僅附加的記錄中（例如`pix:consentLog`擴充功能名稱空間），並個別儲存字詞版本以便在字詞變更後可擷取。 透過Adobe Campaign Explorer呈現記錄檔，並作為定期匯出。
* **重新請求治理。** `lastPixelRefusalDate`欄位和篩選型別規則可防止在拒絕後至少六個月重新請求。 定期工作流程有助於管理同意過期。

* **報告。** 現有的Adobe Campaign報告會繼續針對新欄位（urlCategory、emailType、同意標幟）運作，而不會變更程式碼。

如需Adobe電子郵件行銷執行應用程式中電子郵件追蹤的詳細資訊，請參閱此處的檔案：

| 產品 | 檔案參考 |
|---|---|
| Campaign v8 | [郵件追蹤](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/tracking/url-tracking){target="_blank"} |
| Campaign Classic | [開始使用訊息追蹤](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-message-tracking){target="_blank"} |
| Campaign Standard | [設定電子郵件通道](https://experienceleague.adobe.com/en/docs/campaign-standard/using/administrating/configuring-channels/configuring-email-channel){target="_blank"} |
| Journey Optimizer | [訊息追蹤檔案](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/email/design-email/add-content/message-tracking){target="_blank"} |
| Marketo Engage | [停用電子郵件連結的追蹤](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/email-marketing/general/functions-in-the-editor/disable-tracking-for-an-email-link){target="_blank"} |
| Journey Optimizer B2B | [電子郵件設定檔案](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/journey-content/email-channel/add-email){target="_blank"} |


