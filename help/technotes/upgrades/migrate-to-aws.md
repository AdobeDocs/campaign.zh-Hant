---
title: 將Campaign傳送基礎架構移轉至Amazon Web Services (AWS)
description: 將Campaign傳送基礎架構移轉至Amazon Web Services (AWS)
hide: true
hidefromtoc: true
exl-id: 50279a2f-0296-43f5-8967-16cc6a0c88f6
source-git-commit: 3e95a56825a143a4457ab7ee242208d7daaeb414
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 0%

---

# 行銷活動傳送基礎架構移轉至Amazon Web Services (AWS) {#migrate-infra-to-aws}

## 哪些部分有所變更？{#aws-changes}

我們一直努力提供最高品質的電子郵件傳遞服務，其中一環，就是將Campaign電子郵件傳送基礎建設從Adobe代管資料中心移至Amazon Web Services (AWS)。

此舉將確保高可用性、最佳輸送量，以及擴充能力，以符合客戶的需求。

## 您有受到影響嗎？{#aws-impact}

此變更會影響：

* Campaign Classicv7託管和混合型客戶
* Campaign Managed Services客戶
* 所有Campaign v8客戶
* Campaign Standard客戶

## 何時進行此移轉？{#aws-timeline}

開發和預備環境移轉將於&#x200B;**2023年10月**&#x200B;進行。

生產環境移轉已排程在&#x200B;**2024年1月**&#x200B;開始。 隨著日期臨近，我們將提供更多詳細資訊。

作為Campaign客戶，當移轉波段已排程時，您將收到其他通知。 中繼環境至少在移轉前7天會傳送通知，生產環境則至少在移轉前30天傳送。

## 會有什麼影響？{#impact}

此步驟對客戶而言將是透明的：

* 每個移轉波次的長度可能會因受影響的Campaign執行個體數目而異。 排程移轉波段時，通知將包含預期的持續時間。

* Campaign執行個體在移轉期間將無法傳送郵件。 其他Campaign功能不受影響。


## 常見問題集 {#aws-faq}

* **為什麼這是強制升級？**

  Adobe計畫淘汰舊版資料中心，在該處執行的Adobe Campaign執行個體必須轉移到新的參考資料中心Amazon Web Services (AWS)。

  AdobeManaged Services雲端託管於Amazon Web Services (AWS)上，這是一個現代、安全且最佳化的環境。 [進一步瞭解Amazon Web Services](https://aws.amazon.com/application-hosting/benefits/){target="_blank"}。

* **此移轉的目標客戶為哪些客戶？**

  所有Campaign v8客戶和Campaign Classic v7混合、託管和Campaign Managed Services都將移轉其環境。 Campaign Standard客戶也會受到影響。

* **預期的停機時間是多少？**

  移轉應在30分鐘到60分鐘之間，但每個移轉波動的長度可能會因受影響的Campaign執行個體數量而異。 排程移轉波段時，通知將包含預期的持續時間。

* **客戶移轉是否需要任何動作？**

  不需要採取任何動作，因為Adobe會自動執行移轉。

* **客戶需要執行哪些驗證？**

  此移轉不需要任何特定測試。 如果發現任何問題，請聯絡[Adobe客戶服務](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}。


* **我可以要求變更排定的安全性升級位置的日期/時間嗎？**

  由於這是強制移轉，我們無法因應現有排程的修改。

如有任何其他問題，請連絡[Adobe客戶服務](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}。
