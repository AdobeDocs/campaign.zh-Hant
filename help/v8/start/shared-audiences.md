---
title: 與 Adobe Experience Cloud 解決方案共用客群
description: 了解如何與 Adobe Experience Cloud 解決方案共用客群
feature: Audiences
role: User
level: Beginner
hide: true
exl-id: c4d30771-db5e-40be-8af6-50f0fab9f9af
TQID: https://experienceleague.adobe.com/Q7eY7lPXlHWEcaj-Hx4Bbqj-hwzMvrlxGGYeN5AxzRE
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 267
ht-degree: 76%

---

# 與 Adobe Experience Cloud 解決方案共用客群{#shared-audiences}


選項 1：AEP 來源和目的地

選項 2：Adobe 人員/AAM

您可以整合 **Adobe Campaign** 與&#x200B;**人員核心服務**&#x200B;或 Adobe Audience Manager。 之後，您將能夠：

* 從不同的 Adobe Experience Cloud 解決方案匯入共用的客群/區段至 Adobe Campaign。 您可以透過 Adobe Campaign 中的清單匯入客群。

* 以 Adobe Experience Cloud 共用客群的形式匯出清單。 這些客群可用於您所使用的不同 Adobe Experience Cloud 解決方案。 在工作流程中目標定位後，可使用專用的 **[!UICONTROL Update shared audience]** 活動匯出客群。

此整合支援兩種類型的 Adobe Experience Cloud ID：

* **訪客 ID**：此類型的識別碼可協調 Adobe Experience Cloud 訪客與 Adobe Campaign 收件者。
* **宣告 ID**：此類型的識別碼可協調所有類型的資料與 Adobe Campaign 資料庫中的元素。 在 Adobe Campaign 中以預先定義的調解金鑰呈現。

  >[!NOTE]
  >
  > 已宣告的 ID 資料來源現在也可搭配 People 核心服務整合使用。
  >
  >如果您使用People核心服務整合，且想要新增Audience Manager整合，則需要Adobe Audience Manager顧問的協助，以避免在Adobe Audience Manager內容中轉換為使用此宣告ID資料來源時，所收集的ID同步全部遺失。

查看：

[Adobe Audience Manager檔案](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=zh-Hant){target="_blank"}

[Adobe Experience Cloud中央介面元件指南](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=zh-Hant){target="_blank"}
