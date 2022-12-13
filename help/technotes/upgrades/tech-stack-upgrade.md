---
product: campaign
title: 技術 — Adobe Campaign系統升級
description: Adobe Campaign系統升級
hide: true
hidefromtoc: true
exl-id: 78949d94-60b3-44f1-8e5a-d61b5b723e87
source-git-commit: 3535e1e4fcd326412b6378253e5dde1249bce1f2
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 11%

---

# Adobe Campaign 2023環境升級 {#ac-system-upgrade}

Campaign基礎架構依賴協力廠商系統，必須定期更新最新版本和修正。 這些更新是強制性的，以確保服務的連續性，並保護Campaign環境免受安全風險的影響。 此外，還需要Campaign升級，以確保與協力廠商系統變更相容。

As a **托管Cloud Services客戶**,Adobe會在需要時通知您這些升級。 您的環境需要根據建議進行升級，以確保符合規範。

出於安全原因，Adobe必須 [安裝最新的Campaign版本編號](#ac-upgrade)，然後升級您的 [作業系統](#os-upgrade) 和/或 [關係資料庫管理系統(RDBMS)](#pg-upgrade).

>[!NOTE]
>
>如對這些變更有任何疑問，請聯絡 [Adobe 客戶服務](https://helpx.adobe.com/tw/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html)。

## Campaign版本編號升級 {#ac-upgrade}

**您有受到影響嗎？**

如果您受 [作業系統升級](#os-upgrade) 和/或 [資料庫系統升級](#pg-upgrade) 下文詳細說明，Adobe必須將您的Campaign環境升級至 [最新8.4.3版](../../v8/start/release-notes.md)，與這些系統相容。

**如何更新？**

身為受管Cloud Services客戶，Adobe會與您連絡，並升級您的Campaign版本。

## 作業系統升級 {#os-upgrade}

**您有受到影響嗎？**

如果您在Debian作業系統上執行Campaign，為了從最新的Debian安全性更新中受益，Adobe需要將您的Campaign基礎架構移至 **Debian 11**. 請注意，Debian 9的安全性支援將提供至2023年6月30日。

**如何更新？**

作為受管Cloud Services客戶，Adobe將與您聯繫並升級您的環境。

## 資料庫系統升級 {#pg-upgrade}

**您有受到影響嗎？**

如果您的Campaign資料庫系統是PostgreSQL，為了從最新的PostgreSQL創新和安全更新中受益，Adobe需要升級到 **PostgreSQL 14**. 請注意，PostgreSQL 11將於2023年11月9日終止服務。

**如何更新？**

* 作為托管Cloud Services客戶，Adobe將與您聯繫，並將資料庫系統從PostgreSQL 11升級到PostgreSQL 14。
