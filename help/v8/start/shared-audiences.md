---
title: 與Adobe Experience Cloud解決方案共用受眾
description: 了解如何與Adobe Experience Cloud解決方案共用受眾
feature: Subscriptions
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: ec46a6f41d640b11306a88d6a966f81f8c2e43e0
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 5%

---

# 與Adobe Experience Cloud解決方案共用受眾{#shared-audiences}


選項1:AEP來源和目的地

選項2:Adobe人員/AAM

您可以整合 **Adobe Campaign** with **人員核心服務** 或Adobe Audience Manager。 之後，您將能夠：

* 從不同的Adobe Experience Cloud解決方案匯入共用的受眾/區段至Adobe Campaign。 您可以透過Adobe Campaign中的清單匯入對象。

* 以Adobe Experience Cloud共用對象的形式匯出清單。 這些對象可用於您所使用的不同Adobe Experience Cloud解決方案。 在工作流程中鎖定目標後，可使用專用的 **[!UICONTROL Update shared audience]** 活動。

此整合支援兩種類型的Adobe Experience Cloud ID:

* **訪客ID**:此類型的識別碼可協調Adobe Experience Cloud訪客與Adobe Campaign收件者。
* **宣告ID**:此類型的識別碼可協調所有類型的資料與Adobe Campaign資料庫中的元素。 在Adobe Campaign中以預先定義的調解金鑰呈現。

   >[!NOTE]
   >
   > 已宣告的 ID 資料來源現在也可搭配 People 核心服務整合使用。
   >
   >如果您使用People核心服務整合，且想要新增Audience Manager整合，則需要Adobe Audience Manager顧問的協助，以避免在Adobe Audience Manager內容中轉換為使用此宣告ID資料來源時，所收集的所有ID同步都遺失。

查看:

[https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=en](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=en)

[https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=en](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=en)
