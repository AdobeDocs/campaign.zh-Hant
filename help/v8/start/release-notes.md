---
title: Campaign v8 發行說明
description: 最新的 Campaign v8 版本
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: d4b172bc6b874d542dc9f2725e3bc35679fc7635
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 28%

---

# 最新版本 {#latest-release}

本頁面列出 Campaign v8 (主控台) 最新版本中的新功能、改善和修正。在[此頁面](upgrades.md)進一步了解 Campaign 行銷活動發布、版本和更新。

## 發行版本 8.6.4 {#release-8-6-4}

_2025年1月15日_


### 一般改善 {#improvements-8-6-4}

* 在[企業(FFDA)部署](../../v8/architecture/enterprise-deployment.md)內容中的傳遞分析期間，已改善行銷活動應用程式穩定性。
* 此版本隨附改善及增強的FFDA架構機制，包括金鑰管理、測試和資料複製。
* 已為[企業(FFDA)部署](../../v8/architecture/enterprise-deployment.md)引入新的技術工作流程。 這些工作流程會集中對應表格上的平行復寫請求，以復寫傳遞和相關資料。 這些工作流程以`Replicate nms`開始。
* 新的&#x200B;**啟用監督員以保持工作流程永久執行**&#x200B;選項現在可在工作流程屬性中使用。 啟用此選項後，工作流程會在發生錯誤時自動重新啟動。 根據預設，每30秒會重新啟動一次。 若要調整此間隔，您可以建立新的`XtkWorkflow_WatchdogTimerTimeout`選項，並設定Integer資料型別以指定新的延遲。 此選項只應在技術工作流程中啟用。

### 安全性改善 {#security-8-6-4}

已更新透過&#x200B;**[!UICONTROL Adobe Experience Cloud]**&#x200B;外部帳戶與Adobe解決方案和應用程式的連線，以強化安全性。

<!--
### Connection to Campaign {#ims-8-6-4}

**(Limited availability)** For a restricted list of customers, Campaign v8.6.4 can allow native authentication mode instead of Adobe Identity Management System (IMS). Note that if you are using Campaign native authentication, you cannot access to [Campaign Web User Interface](../start/campaign-ui.md#campaign-web-user-interface).-->

### 相容性更新 {#comp-8-6-4}

現可支援 Databricks 作為外部資料庫，與 Adobe Campaign 同盟資料存取 (FDA) 搭配使用。 在[本頁](compatibility-matrix.md#FederatedDataAccessFDA)中深入瞭解。

### 修正 {#fixes-8-6-4}

此版本已修正下列問題：

NEO-77452、NEO-81127、NEO-81209、NEO-80243、NEO-80314、NEO-81223、NEO-81287、NEO-81290、NEO-81312、NEO-81512、NEO-81520、NEO-81566、NEO-81704、NEO-83096 83081。