---
title: 使用Campaign和Adobe Experience Platform
description: 瞭解如何使用Campaign和Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
exl-id: 21cf5611-ccaa-4e83-8891-a1a2353515aa
source-git-commit: f8c4e05ba2fc97d981fb31f9b11c5de1dcc1ff6e
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---

# 使用Campaign和Adobe Experience Platform

Adobe Campaign受管理的Cloud Service目標和來源聯結器可讓Adobe Campaign與Adobe Experience Platform之間無縫整合。

* 使用Adobe Campaign Managed Cloud Services **目的地連線** 若要將Experience Platform區段傳送至Adobe Campaign以進行啟用：

  若要這麼做，請設定新的Adobe Campaign Managed Cloud Services **目的地連線** 以啟用區段/對象，並將該資料傳送至Adobe Campaign。 提供要使用的Campaign執行個體的詳細資訊，選取要為目的地啟用的區段，然後設定您要匯出至Campaign的屬性。 [瞭解如何建立Adobe Campaign Managed Cloud Services目的地連線](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

  ![](assets/aep-destination.png){width="800" align="center"}

* 使用Adobe Campaign Managed Cloud Services **來源連線** 若要將Adobe Campaign傳送和追蹤記錄傳送至Adobe Experience Platform：

  若要這麼做，請設定新的Adobe Campaign Managed Cloud Services **來源連線** 將Campaign事件擷取至Adobe Experience Platform。 提供要使用的Campaign執行個體和結構描述的詳細資訊、選取應擷取資料的資料集，然後設定要擷取的欄位。 [瞭解如何建立Adobe Campaign Managed Cloud Services來源連線](https://www.adobe.com/go/sources-campaign-ui-en)

  ![](assets/aep-logs.png){width="800" align="center"}
