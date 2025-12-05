---
title: 移至新的SMS聯結器v2
description: 瞭解如何改用新的簡訊聯結器v2
feature: Technote
role: Admin
exl-id: 61a5a3e8-59f8-47ea-afc9-66ec243b8265
source-git-commit: 30ab5a10f17baddfc455dc406a4f31f058ea05ba
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# 移至新的SMS聯結器v2

Adobe Campaign v8推出全新的&#x200B;**專用SMS流程聯結器** (v2)，相較於舊版MTA型SMS聯結器，此聯結器提供更優異的效能和可靠性。

## 為何切換至v2聯結器

專用的SMS流程引入對SMPP收發器模式的支援，減少連線計數並提高資源效率，同時仍然在需要時支援傳送器/接收器設定。 它提供大幅提升的穩定性，可更快速地從錯誤中復原、持續連線，並且不依賴本機檔案或處理序間通訊。 效能也得到改善，延遲時間更短，吞吐量更高，智慧型微批次處理可平衡速度和可靠性。 此外，SMS程式的隔離可簡化疑難排解，並將跨頻道影響降至最低。 這些增強功能讓專用聯結器成為SMS傳送的更強大且可擴展的解決方案。

## 設定

透過Adobe Campaign Managed Cloud Services，伺服器設定和SMS聯結器移轉由Adobe管理。 此技術程式需要直接存取伺服器組態檔和資料庫作業。

如果您需要移轉至新的SMS聯結器v2，請聯絡您的Adobe代表或Adobe客戶服務。 他們將會排程並執行您執行個體的必要更新。

如需Campaign v8簡訊頻道的詳細資訊，請參閱[簡訊檔案](../../v8/send/sms/sms.md)。
