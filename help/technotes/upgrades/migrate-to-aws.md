---
title: 將Campaign傳送基礎架構移轉至Amazon Web Services (AWS)
description: 將Campaign傳送基礎架構移轉至Amazon Web Services (AWS)
hide: true
hidefromtoc: true
source-git-commit: 53080e3641e0070b0b6e47d1ec8b55b4c7aa2b1a
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 5%

---


# 行銷活動傳送基礎架構移轉至Amazon Web Services (AWS) {#migrate-infra-to-aws}

## 哪些部分有所變更？{#aws-changes}

我們一直努力提供最高品質的電子郵件傳遞服務，其中一環，就是將Campaign電子郵件傳送基礎建設從Adobe代管資料中心移至Amazon Web Services (AWS)。

此舉將確保高可用性、最佳輸送量，以及擴充能力，以符合客戶的需求。

## 您有受到影響嗎？{#aws-impact}

如果您是v8客戶或v7託管、混合或Managed Services Campaign客戶，即會受到影響。

## 何時進行此移轉？{#aws-timeline}

開發和預備環境移轉作業將發生在 **2023年10**.

生產環境移轉已排程在中開始 **2024年1月**. 隨著日期臨近，我們將提供更多詳細資訊。

作為Campaign客戶，當移轉波段已排程時，您將收到其他通知。 移轉前至少七天會傳送通知。

## 會有什麼影響？{#impact}

此步驟對客戶而言將是透明的：

* 傳送IP和Campaign版本編號將維持與移動前相同的狀態。

* 在移轉期間，Campaign執行個體將無法傳送郵件。 其他Campaign功能不受影響。

* 在維護期間之前排入傳遞佇列的任何郵件都必須重新傳送。

>[!NOTE]
>
>如對此移轉有任何疑問，請聯絡您的Adobe代表或聯絡 [Adobe客戶服務](https://helpx.adobe.com/tw/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).
>


