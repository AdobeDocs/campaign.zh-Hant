---
solution: Campaign v8
product: Adobe Campaign
title: 使用Campaign和Adobe Analytics
description: 了解如何使用Campaign和Adobe Analytics
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
source-git-commit: 556cd7727c7c2bf0158d59d71ae0131b4c1013ee
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 2%

---

# 使用Campaign和Adobe Analytics


## Adobe Analytics Connector

您可以設定Adobe Analytics連接器以整合Campaign與Analytics。

Adobe Analytics連接器可讓Adobe Campaign和Adobe Analytics透過&#x200B;**Web Analytics連接器**&#x200B;附加元件互動。 此整合會以與電子郵件後使用者行為相關的區段形式，與Analytics和Campaign共用資料。 相反地，它會將Adobe Campaign傳送之電子郵件促銷活動的指標和屬性傳送至Adobe Analytics - Data connector。

Adobe Campaign使用Adobe Analytics Connector可測量網際網路受眾(Web Analytics)。 有了這些整合，Adobe Campaign便能復原行銷活動後一或多個網站的訪客行為資料，並（分析後）執行再行銷活動，以便將其轉換為購買者。 反之，Adobe Campaign的網頁分析工具可將指標和行銷活動屬性轉送至其平台。

每個工具的動作欄位如下：

* **Adobe Analytics**

   * 會標籤透過Adobe Campaign啟動的電子郵件行銷活動
   * 以區段的形式，儲存收件者在按一下促銷活動電子郵件後所瀏覽的網站上的行為。 區段與放棄的產品（已檢視但未新增至購物車或已購買）、購買或購物車放棄有關。

* **Adobe Campaign**

   * 會將指標和促銷活動屬性傳送至連接器，連接器會將它們轉送至Web分析工具
   * 恢復和分析區段
   * 觸發再行銷活動

請前往[本頁面](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/adobe-analytics-data-connector.html)，深入了解Adobe Campaign和Adobe Analytics

:speech_balloon: 以「受管理Cloud Services」使用者的身分，[聯絡Adobe](../start/campaign-faq.md#support)以整合Adobe Analytics Data Connector與Campaign。


## Experience Cloud Triggers

您可以使用Experience Cloud觸發器，使用管道在Adobe Campaign和Adobe Analytics之間連線資料。 管道會從您的網站擷取使用者的動作或觸發器。 放棄購買是觸發的範例。 觸發器會在Adobe Campaign中處理，以近乎即時傳送電子郵件。

深入了解[本頁面](https://experienceleague.adobe.com/docs/campaign-classic/using/integrating-with-adobe-experience-cloud/experience-triggers/about-triggers.html?lang=en)上的Adobe Campaign和Experience Cloud觸發器。

:speech_balloon: 以「受管理的Cloud Services」使用者身分，[聯絡Adobe](../start/campaign-faq.md#support)以使用Campaign實作Experience Cloud觸發器。
