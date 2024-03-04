---
product: campaign
title: 技術檔案 — Adobe Campaign系統升級
description: Adobe Campaign系統升級
hide: true
hidefromtoc: true
source-git-commit: c362e6ff932f5017530434c4b458070ec1a97abc
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 9%

---

# Adobe Campaign 2023環境升級 {#ac-system-upgrade}

Campaign基礎架構仰賴協力廠商系統，且必須定期以最新版本和修正更新。 這些更新是強制性的，可確保服務的連續性，並確保Campaign環境的安全不會受到安全風險的影響。 此外，需要升級Campaign，以確保與協力廠商系統變更相容。

作為 **Managed Cloud Service客戶**，Adobe會在需要這些升級時通知您。 您的環境將需要根據建議進行升級，以確保法規遵循。

基於安全理由，Adobe必須 [安裝最新的Campaign版本編號](#ac-upgrade)，然後升級您的 [作業系統](#os-upgrade) 和/或您的 [關係資料庫管理系統(RDBMS)](#pg-upgrade).

>[!NOTE]
>
>如對這些變更有任何疑問，請聯絡 [Adobe 客戶服務](https://helpx.adobe.com/tw/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html)。
>

## Campaign版本編號升級 {#ac-upgrade}

**您有受到影響嗎？**

如果您受 [作業系統升級](#os-upgrade) 和/或 [資料庫系統升級](#pg-upgrade) 如下所述，Adobe必須將您的Campaign環境升級至 [最新8.4.3版本](../../v8/start/release-notes.md)，這些系統相容。

**如何更新？**

Adobe作為「受管理的Cloud Service」客戶，將會連絡您並升級您的Campaign版本。

## 作業系統升級 {#os-upgrade}

**您有受到影響嗎？**

如果您在Debian作業系統上執行Campaign，若要受益於最新的Debian安全性更新，Adobe需要將您的Campaign基礎架構移至 **Debian 11**. 請注意，Debian 9的安全性支援將持續提供至2023年6月30日。

**如何更新？**

Adobe作為「受管理的Cloud Service」客戶，將會與您連絡並升級您的環境。

## 資料庫系統升級 {#pg-upgrade}

**您有受到影響嗎？**

如果您的Campaign資料庫系統是PostgreSQL，若要受益於最新的PostgreSQL創新和安全性更新，Adobe需要升級至 **PostgreSQL 14**. 請注意，PostgreSQL 11將於2023年11月9日結束生命週期。

**如何更新？**

作為「受管理的Cloud Service」客戶，Adobe將會與您聯絡，並將您的資料庫系統從PostgreSQL 11升級至PostgreSQL 14。
