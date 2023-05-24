---
title: 使用Campaign和Adobe Experience Platform
description: 瞭解如何使用Campaign和Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
exl-id: 21cf5611-ccaa-4e83-8891-a1a2353515aa
source-git-commit: 3c7455f348468a8f00fb853a3269a1d63b81e7b8
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---

# 使用Campaign和Adobe Experience Platform

Adobe Campaign受管理的Cloud Service目標和來源聯結器可讓Adobe Campaign與Adobe Experience Platform之間無縫整合。

* 使用 **Adobe Campaign Managed Cloud Services目的地** 將Experience Platform區段傳送至Adobe Campaign以進行啟用的連線

   ![](assets/aep-destination.png)

* 使用 **Adobe Campaign Managed Cloud Services來源** 將Adobe Campaign傳遞和追蹤記錄傳送至Adobe Experience Platform的連線

   ![](assets/aep-logs.png)

在Adobe Experience Platform中設定這項整合的步驟如下：

1. 設定新的Adobe Campaign Managed Cloud Services目的地連線，以啟用區段/對象，並將資料傳送至Adobe Campaign。

   提供要使用的Campaign執行個體的詳細資訊，選取要為目的地啟用的區段，然後設定您要匯出至Campaign的屬性。

   [瞭解如何建立Adobe Campaign Managed Cloud Services目的地連線](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

1. 設定新的Adobe Campaign Managed Cloud Services來源連線，將Campaign事件擷取到Adobe Experience Platform。

   提供要使用的Campaign執行個體和結構描述的詳細資訊、選取應擷取資料的資料集，然後設定要擷取的欄位。

   [瞭解如何建立Adobe Campaign Managed Cloud Services來源連線](https://www.adobe.com/go/sources-campaign-ui-en)
