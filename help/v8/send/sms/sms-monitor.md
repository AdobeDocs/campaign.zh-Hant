---
title: 監視和追蹤簡訊
description: 關於SMS傳送的監控和追蹤
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: 42be45db-3a90-4ad0-896d-f082afff1f8e
TQID: 'https://experienceleague.adobe.com/wETwv6lIEctnfT54WQjulzGxeCPo6lZDF-rxlwBtF4I'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: c4f3ffbf421621fa15b1b4d56480bd0ff9304254
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%
---
# 監視和追蹤簡訊

請務必監視您的SMS傳送，以確保您的行銷活動有效率。

以下是您必須知道傳送傳遞後會發生什麼情形的可能性

## 瞭解SMS傳送控制面板

傳送控制面板會提供您SMS的詳細資訊。

若要存取儀表板，請連按兩下傳送清單中的傳送。

在&#x200B;**[!UICONTROL Summary]**&#x200B;索引標籤中，您有主要資料，例如已處理的訊息數和成功數。

![簡訊傳遞儀表板摘要索引標籤，包含要傳送的訊息、已處理及成功率，以及傳遞狀態](assets/sms_summary.png){zoomable="yes"}

傳送SMS後，無法再存取與傳送內容有關的&#x200B;**[!UICONTROL SMS]**&#x200B;標籤以進行變更。

在&#x200B;**[!UICONTROL Delivery]**&#x200B;標籤中，您擁有傳遞記錄的資訊。 對於每個聯絡的地址，您可以檢視簡訊是否已傳送

![傳遞索引標籤記錄檔清單，針對每個聯絡的地址，顯示是否傳送簡訊，以及狀態和原因](assets/sms_deliverylogs.png){zoomable="yes"}

您可以在&#x200B;**[!UICONTROL Exclusions]**&#x200B;索引標籤中檢視有關為何將某些地址從目標中排除的詳細資料。

![傳遞索引標籤排除專案索引標籤會以原因列出被忽略的地址，例如已加入封鎖清單的地址或雙精度浮點數](assets/sms_exclusions.png){zoomable="yes"}

**[!UICONTROL Tracking]**&#x200B;索引標籤與追蹤有關。 以下是在SMS內容中追蹤的URL範例。

![追蹤標籤URL清單顯示來自SMS內容的追蹤URL及其標籤、型別和來源URL](assets/sms_trackinglogs.png){zoomable="yes"}

最後，在傳遞啟動期間包含所有詳細資料的&#x200B;**[!UICONTROL Audit]**&#x200B;標籤：

![稽核索引標籤記錄檔列出傳遞啟動期間記錄的訊息，包含日期和訊息欄](assets/sms_audit.png){zoomable="yes"}

## 瞭解簡訊失敗

簡訊的失敗型別和失敗原因與電子郵件的相同。

深入瞭解[傳送失敗](../delivery-failures.md)，尤其是關於[SMS隔離](../delivery-failures.md#sms-quarantines)。
