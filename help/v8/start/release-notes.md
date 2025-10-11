---
title: Campaign v8 發行說明
description: 最新的 Campaign v8 版本
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 3bc247ba81de3de56c26bdf8fa9b8aa5ea91fb2a
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 23%

---

# 最新版本 {#latest-release}

本頁面列出 Campaign v8 (主控台) **最新版本**&#x200B;中的新功能、改善和修正。在[此頁面](upgrades.md)進一步了解 Campaign 行銷活動發布、版本和更新。本文件的先前版本區段將列出其他版本。

## 版本 8.8.2 {#release-8-8-2}

_2025年10月9日_

>[!AVAILABILITY]
>
>此版本為&#x200B;**有限可用性** (LA)。

### 新功能 {#features-8-8-2}

**新的SMS傳送聯結器**&#x200B;現在可用於[Campaign FFDA部署](../architecture/enterprise-deployment.md)。 請參閱[詳細檔案](../send/sms/sms.md)。

此版本也隨附Campaign Web使用者介面提供的一組功能：

* [交易式訊息中的設定檔擴充](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html?lang=zh-Hant){target="_blank"}
* [異動訊息、推播通知和簡訊的多語言功能](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html?lang=zh-Hant){target="_blank"}

請參閱Campaign Web UI [發行說明](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=zh-hant){target="_blank"}

### 修正 {#fixes-8-8-2}

<!--
* Fixed an issue which prevented dynamic reporting from being available for transactional messages.
-->
* 修正可能導致資料庫清理工作流程失敗的問題。 (NEO-87949)
* 修正分散式行銷中，未針對合作行銷活動傳遞記錄追蹤資料的問題。 (NEO-86836)
<!--
* Issue SMS2.0 with FFDA Continuous Deliveries (NEO-88785)
-->
* 修正片段中個人化無法正常運作的問題。 (NEO-88161)
* 修正移轉至新Redshift ODBC聯結器後，可能導致分割工作流程活動因SQL錯誤而失敗的問題。 (NEO-87466)
* 修正工作流程中可能導致排除計數不正確的問題。 (NEO-89207)
* 修正可能導致推播通知的點按指標不正確的問題。 (NEO-89503)
* 修正SMS傳送記錄檔未正確更新，導致Adobe Campaign無法正確報告狀態的問題。 (NEO-88479)
* 修正傳送內容中，法文引號錯誤轉換為英文引號的問題。 (NEO-89631)
* 修正Real-Time Server針對無效的IMS權杖傳回錯誤回應代碼的問題。 (NEO-87428)
* 修正電子郵件和簡訊的傳遞統計資料未完全重新計算，導致成功指標不準確的問題。 (NEO-88106)
* 修正新SMS傳送聯結器的問題，該問題導致傳送記錄錯誤指派一小部分訊息的傳送狀態。 (NEO-89581)
* 修正新SMS傳送聯結器的問題，該問題導致T-Mobile傳遞的成功量度未在行銷和中間伺服器上正確更新。 (NEO-89850)
* 修正即時和行銷執行個體之間的同步問題，此問題會導致遺失追蹤記錄及不正確的報表。 (NEO-90247)
* 修正在自訂結構中選擇兩個連續1-N連結的欄位時，可能會導致錯誤的工作流程擴充問題。 (NEO-87682)

