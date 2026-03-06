---
title: 簡訊連接器
description: 瞭解Adobe Campaign中的SMS聯結器
feature: SMS
role: User, Admin
level: Intermediate
source-git-commit: e349e9f236c3eeb28ffe96bcc5ec72ab64c4c127
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 1%

---

# 關於SMS聯結器型別 {#sms-connectors}

Adobe Campaign支援兩個SMS聯結器，用於傳送簡訊給您的客戶：

* **舊版SMS聯結器**： Campaign v7及舊版Campaign v8中使用的聯結器第一版本。 [了解更多](#legacy-sms-connector)
* **SMS聯結器v2**：自Campaign v8.9.1開始於GA提供，此v2專用的SMS聯結器已現代化，以提供改良的效能和可靠性。 [了解更多](#sms-connector-v2)

## 舊版SMS聯結器 {#legacy-sms-connector}

舊版SMS聯結器是在舊版Adobe Campaign中使用的MTA型SMS聯結器。 現有實作仍支援此聯結器，但Adobe強烈建議升級至v8.9.1或更新版本，以從v2聯結器的改良效能和可靠性中獲益。

若要瞭解如何受益於v2聯結器，請參閱[啟用](#activation)區段。

如需舊版SMS聯結器設定和使用方式的詳細資訊，請參閱[Campaign Classic檔案](https://experienceleague.adobe.com/zh-hant/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}。

## SMS聯結器v2 {#sms-connector-v2}

從v8.9.1開始的GA中提供v2聯結器，可啟用收發器模式SMPP連線、持續的SMPP連線，並確保更好的相容性。 專用簡訊外部帳戶可用於使用v2聯結器的所有簡訊實施。

v2聯結器預設為針對新安裝啟用。 如果您使用舊版聯結器從舊版升級，則需要聯絡Adobe代表以切換至v2聯結器。 請參閱[啟用](#activation)區段。

若要瞭解如何在Campaign v8中使用SMS聯結器v2，請參閱[SMS檔案](sms.md)。

>[!NOTE]
>
>下列組建中也提供v2聯結器，但有一些限制：
>* 8.8.1：所有Campaign FDA環境的版本。 不適用於Campaign FFDA部署。
>* 8.8.2：所有部署型別（包括FFDA）的發行版本。 於Limited Availability (LA)發行。

## 啟用 {#activation}

### 為何切換至v2聯結器 {#why-switch-v2}

專用的SMS流程引入對SMPP收發器模式的支援，減少連線計數並提高資源效率，同時仍然在需要時支援傳送器/接收器設定。 它提供大幅提升的穩定性，可更快速地從錯誤中復原、持續連線，並且不依賴本機檔案或處理序間通訊。 效能也得到改善，延遲時間更短，吞吐量更高，智慧型微批次處理可平衡速度和可靠性。 此外，SMS程式的隔離可簡化疑難排解，並將跨頻道影響降至最低。 這些增強功能讓專用聯結器成為SMS傳送的更強大且可擴展的解決方案。

### 設定 {#configuration}

透過Adobe Campaign Managed Cloud Services，伺服器設定和SMS聯結器移轉由Adobe管理。 此技術程式需要直接存取伺服器組態檔和資料庫作業。

若要啟動並開始使用SMS聯結器v2，您首先需要升級到v8.9.1或更高版本。 請聯絡您的Adobe代表或Adobe客戶服務。 他們將會排程並執行您執行個體的必要更新。