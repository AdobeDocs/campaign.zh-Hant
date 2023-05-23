---
product: campaign
title: 技術 — Adobe Campaign系統升級
description: Adobe Campaign系統升級
hide: true
hidefromtoc: true
exl-id: 78949d94-60b3-44f1-8e5a-d61b5b723e87
source-git-commit: f1e963a880e8499dbbb16c44831a4ce1b537601f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 11%

---

# Adobe Campaign2023年環境升級 {#ac-system-upgrade}

市場活動基礎架構依賴第三方系統，這些系統必須定期更新最新版本和修復。 這些更新是必需的，以確保服務的連續性和針對安全風險保護市場活動環境。 此外，還需要進行市場活動升級，以確保與第三方系統更改相容。

作為 **托管Cloud Services客戶**，當需要升級時，Adobe會通知您。 您的環境需要根據建議進行升級，以確保法規遵從性。

出於安全原因，Adobe [安裝最新的市場活動構建](#ac-upgrade)，然後升級 [作業系統](#os-upgrade) 和 [關係資料庫管理系統(RDBMS)](#pg-upgrade)。

>[!NOTE]
>
>如對這些變更有任何疑問，請聯絡 [Adobe 客戶服務](https://helpx.adobe.com/tw/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html)。

## 市場活動構建升級 {#ac-upgrade}

**您有受到影響嗎？**

如果您受 [作業系統升級](#os-upgrade) 和/或 [資料庫系統升級](#pg-upgrade) 詳細說明，Adobe必須將促銷活動環境升級到 [最新8.4.3版](../../v8/start/release-notes.md)與這些系統相容。

**如何更新？**

作為受管Cloud Services客戶，Adobe將與您聯繫並升級促銷活動版本。

## 作業系統升級 {#os-upgrade}

**您有受到影響嗎？**

如果您在Debian作業系統上運行Camping ，以便從Debian最新的安全更新中獲益，則Adobe需要將您的Campaing基礎架構移動到 **德比11**。 請注意，對德比安9號的安全支援將提供到2023年6月30日。

**如何更新？**

作為受管Cloud Services客戶，Adobe將與您聯繫並升級您的環境。

## 資料庫系統升級 {#pg-upgrade}

**您有受到影響嗎？**

如果您的市場活動資料庫系統是PostgreSQL，要從最新的PostgreSQL創新和安全更新中獲益，Adobe需要升級到 **PostgreSQL 14**。 請注意，PostgreSQL 11將於2023年11月9日到期。

**如何更新？**

作為托管Cloud Services客戶，Adobe將與您聯繫，並將資料庫系統從PostgreSQL 11升級到PostgreSQL 14。
