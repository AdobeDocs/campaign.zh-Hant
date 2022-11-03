---
title: 與 Adobe Experience Cloud 解決方案共用對象
description: 了解如何與 Adobe Experience Cloud 解決方案共用對象
feature: Audiences, Profiles
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: 9bea7904ea4507083d2cf45193877e7a2539d0c7
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 81%

---

# 與 Adobe Experience Cloud 解決方案共用對象{#shared-audiences}

選項 1：AEP 來源和目的地

選項 2：Adobe 人員/AAM

您可以整合 **Adobe Campaign** 與&#x200B;**人員核心服務**&#x200B;或 Adobe Audience Manager。 之後，您將能夠：

* 從不同的 Adobe Experience Cloud 解決方案匯入共用的對象/區段至 Adobe Campaign。 您可以透過 Adobe Campaign 中的清單匯入對象。

* 以 Adobe Experience Cloud 共用對象的形式匯出清單。 這些對象可用於您所使用的不同 Adobe Experience Cloud 解決方案。 在工作流程中目標定位後，可使用專用的 **[!UICONTROL Update shared audience]** 活動匯出對象。

此整合支援兩種類型的 Adobe Experience Cloud ID：

* **訪客ID**:此識別碼可協調Adobe Experience Cloud訪客與Adobe Campaign收件者。
* **宣告ID**:此識別碼可與Adobe Campaign資料庫的元素協調所有類型的資料。 這是Adobe Campaign中預先定義的調解金鑰。

   >[!NOTE]
   >
   > 宣告ID資料來源也可與People核心服務整合搭配使用。
   >
   >如果您使用 People 核心服務整合，且想要新增 Audience Manager 整合，則需要 Adobe Audience Manager 顧問的協助，以避免在 Adobe Audience Manager 內容中轉換為使用此宣告 ID 資料來源時，所收集的 ID 同步全部遺失。

查看：

[https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=zh-Hant](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=zh-Hant)

[https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=zh-Hant](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=zh-Hant)
