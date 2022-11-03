---
title: 使用Campaign和Adobe Experience Platform
description: 了解如何使用Campaign和Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
source-git-commit: 9bea7904ea4507083d2cf45193877e7a2539d0c7
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---

# 使用Campaign和Adobe Experience Platform

Adobe Campaign受管Cloud Service目的地和來源連接器可順暢地整合Adobe Campaign和Adobe Experience Platform。

* 使用 **Adobe Campaign Managed Cloud Services** 要將Experience Platform區段傳送至Adobe Campaign以進行啟用的目的地連線，

   ![](assets/aep-destination.png)

* 使用 **Adobe Campaign Managed Cloud Services** 來源連線，將Adobe Campaign傳送和追蹤記錄檔傳送至Adobe Experience Platform。

   ![](assets/aep-logs.png)

在Adobe Experience Platform中設定此整合的步驟如下：

1. 設定新的Adobe Campaign Managed Cloud Services目的地連線以啟用區段/對象，並將該資料傳送至Adobe Campaign。

   提供要使用的促銷活動例項的詳細資訊，選取要針對目的地啟用的區段，然後設定您要匯出至促銷活動的屬性。

   [了解如何建立Adobe Campaign Managed Cloud Services目的地連線](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

1. 設定新的Adobe Campaign Managed Cloud Services來源連線，將促銷活動事件內嵌至Adobe體驗平台。

   提供Campaign執行個體和要使用的結構的詳細資訊，選取應匯入資料的資料集，然後設定要擷取的欄位。

   [了解如何建立Adobe Campaign Managed Cloud Services來源連線](https://www.adobe.com/go/sources-campaign-ui-en)
