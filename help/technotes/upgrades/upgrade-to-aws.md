---
title: Campaign電子郵件傳送基礎架構升級
description: Campaign電子郵件傳送基礎架構升級
source-git-commit: 4478c4b4b1eb3697ff03acfcd618ebfb1d875df9
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 2%

---


# Campaign電子郵件傳送基礎架構升級 {#migrate-infra-to-aws}

## 將升級哪些專案？{#aws-changes}

為了提供同級最佳的使用者體驗，我們不斷升級電子郵件傳送服務。

## 您有受到影響嗎？{#aws-impact}

此變更會影響：

* Adobe Campaign Classic Managed Services客戶
* Adobe Campaign Managed Cloud Services客戶
* Adobe Campaign Standard On-demand客戶

## 此升級將於何時進行？{#aws-timeline}

開發和測試環境升級預計會在以下時段進行： **2023年10**.

我們計畫於以下日期開始安排生產環境升級： **2024年1月**.

作為Campaign客戶，您至少將提前三十(30)天收到有關生產升級的額外通知。

## 有何期望？{#impact}

* 每個升級波次的長度，會因受影響的Campaign執行個體數量而異。 排程生產升級波段時，通知將包含估計持續時間。

* 在升級期間，中繼和生產環境中的Campaign執行個體將無法傳送郵件。 其他Campaign功能應該不會受到影響。

## 常見問題集 {#aws-faq}

* **這是強制升級嗎？**

  是. 身為Campaign客戶，您的電子郵件傳送功能需要使用電子郵件傳送基礎結構。

* **此升級鎖定哪些客戶？**

  以上提及的所有Campaign客戶都會升級其環境。

* **預期的停機時間是多少？**

  每個升級波次的長度可能會因受影響的Campaign執行個體數目而異。 排程生產升級波段時，通知將包含估計持續時間。

* **客戶升級是否需要任何動作？**

  不需要採取任何動作。 Adobe將管理升級流程，該流程會自動執行。

* **客戶需要哪些測試？**

  我們預計客戶不會針對此升級事件進行任何測試。 如果發現任何問題，請聯絡 [Adobe客戶服務](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.


* **我可以要求變更排程安全性升級位置的日期/時間嗎？**

  沒有。我們無法因應現有排程的任何修改請求，因為這可能會中斷為其他客戶指派的升級事件。

如有任何其他問題，您可以聯絡 [Adobe客戶服務](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.
