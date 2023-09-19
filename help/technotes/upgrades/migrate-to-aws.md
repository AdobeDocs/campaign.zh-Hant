---
title: 將Campaign傳送基礎架構移轉至Amazon Web Services (AWS)
description: 將Campaign傳送基礎架構移轉至Amazon Web Services (AWS)
hide: true
hidefromtoc: true
source-git-commit: 557d61e0e015fa955b70858d614e476febd467cb
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 2%

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

## 何時進行此移轉？{#aws-timeline}

開發和預備環境移轉作業將發生在 **2023年10**.

生產環境移轉已排程在中開始 **2024年1月**. 隨著日期臨近，我們將提供更多詳細資訊。

作為Campaign客戶，當移轉波段已排程時，您將收到其他通知。 中繼環境至少在移轉前7天會傳送通知，生產環境則至少在移轉前30天傳送。

## 會有什麼影響？{#impact}

此步驟對客戶而言將是透明的：

* 移轉時間預計在30分鐘到60分鐘之間

* Campaign執行個體在移轉期間將無法傳送郵件。 其他Campaign功能不受影響。


## 常見問題集 {#aws-faq}

* **為什麼這是強制升級？**

  由Adobe Web Services (AWS)代管的全新Campaign傳送基礎建設，可為客戶提供更優異的品質和可靠性。 它還提供強大且現代的基礎架構，確保更優異的可用性和最佳傳輸量。

* **此移轉鎖定哪些客戶？**

  所有Campaign v8客戶和Campaign Classic v7混合、託管和Campaign Managed Services都將移轉其環境。

* **預期的停機時間是多少？**

  預計停機時間為30到60分鐘。

* **客戶移轉時是否需要任何動作？**

  移轉將會由Adobe自動執行，因此不需要採取任何動作。

* **客戶需要執行哪些驗證？**

  此安全性升級不需要任何特定測試。 如果發現任何問題，請聯絡 [Adobe客戶服務](https://experienceleague.adobe.com/?support-solution=Campaign#support)


* **我可以要求變更排程安全性升級位置的日期/時間嗎？**

  由於這是強制移轉，強烈建議您調整現有排程。


如有任何其他問題，您可以聯絡 [Adobe客戶服務](https://experienceleague.adobe.com/?support-solution=Campaign#support).
