---
title: 與 Adobe Experience Cloud 解決方案共用對象
description: 了解如何與 Adobe Experience Cloud 解決方案共用對象
feature: Subscriptions
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: c4d30771-db5e-40be-8af6-50f0fab9f9af
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 100%

---

# 與 Adobe Experience Cloud 解決方案共用對象{#shared-audiences}


選項 1：AEP 來源和目的地

選項 2：Adobe 人員/AAM

您可以整合 **Adobe Campaign** 與&#x200B;**人員核心服務**&#x200B;或 Adobe Audience Manager。 之後，您將能夠：

* 從不同的 Adobe Experience Cloud 解決方案匯入共用的對象/區段至 Adobe Campaign。 您可以透過 Adobe Campaign 中的清單匯入對象。

* 以 Adobe Experience Cloud 共用對象的形式匯出清單。 這些對象可用於您所使用的不同 Adobe Experience Cloud 解決方案。 在工作流程中目標定位後，可使用專用的 **[!UICONTROL Update shared audience]** 活動匯出對象。

此整合支援兩種類型的 Adobe Experience Cloud ID：

* **訪客 ID**：此類型的識別碼可協調 Adobe Experience Cloud 訪客與 Adobe Campaign 收件者。
* **宣告 ID**：此類型的識別碼可協調所有類型的資料與 Adobe Campaign 資料庫中的元素。 在 Adobe Campaign 中以預先定義的調解金鑰呈現。

  >[!NOTE]
  >
  > 已宣告的 ID 資料來源現在也可搭配 People 核心服務整合使用。
  >
  >如果您使用 People 核心服務整合，且想要新增 Audience Manager 整合，則需要 Adobe Audience Manager 顧問的協助，以避免在 Adobe Audience Manager 內容中轉換為使用此宣告 ID 資料來源時，所收集的 ID 同步全部遺失。

查看：

[https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=zh-Hant)

[https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=zh-Hant)
