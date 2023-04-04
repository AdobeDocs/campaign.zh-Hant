---
title: Campaign v8 早期發行說明
description: 早期 Campaign v8 版本
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 100%

---

# 早期發行說明 {#e-new-release}

本頁介紹了下一個 Campaign v8 版本中包含的改善及修正。在發行日期前，此內容可能會有所變更，恕不另行通知。 本[頁面](../start/release-notes.md)提供正式發行說明。

## 發行版本 8.3.9 {#release-8-3-9}

>[!CAUTION]
>
> 用戶端主控台升級為強制。 透過本[頁面](../start/connect.md#download-ac-console)了解如何升級您的用戶端主控台。

_2022 年 10 月 7 日_

**功能改進**

* 修正啟用 FeatureFlag_GZIP_Compression 選項時，影響 MID 執行個體上傳送記錄狀態更新的問題。 (NEO-49183)
* 此 **資料庫清理** 技術工作流程現在也可處理自訂的準備結構。 (NEO-48974)
* 修正了可能導致傳遞持續存在&#x200B;**待定**&#x200B;狀態的問題，即使已達到聯絡日期亦然。 (NEO-48079、NEO-48251)
* 改善在 SOAP 呼叫期間處理無效 XML 字串時的穩定性。 (NEO-48027)
* 修正在排除已列入封鎖名單的收件者步驟期間，鎖定大量收件者時，可能會拖慢傳送分析的速度的問題。 (NEO-48019)
* 為了防止向種子地址傳送證明時速度變慢，現在種子成員的所有連續複製都分組到一個複製請求中。 (NEO-44844)
* 修正使用外部傳送模式傳送 SMS 訊息時，導致個人化問題的問題。 (NEO-46415)
* 修正嘗試在任何「訊息中心」封存事件中預覽傳遞時，顯示錯誤的問題。 (NEO-43620)
* 修正工作流程中，使用&#x200B;**資料載入 (檔案)** 活動可能阻止檔案更新的問題。 流程 100% 停止，但從未結束。 (NEO-47269)
* 修正了當傳送使用日曆和分割模式時，導致建立不必要 DeliveryPart 的問題。 (NEO-48634)
* 修正使用日曆波段時的效能問題。 (NEO-48451)
* 修正在自訂架構上建立新目標對應後，傳送清單畫面中可能顯示錯誤訊息的問題。 (NEO-49237)
* 修正了在 MTA 流程期間，如果傳送達到精確大小時可能發生的問題。 (NEO-46097)
* 修正追蹤記錄無法傳回與收件者瀏覽器相關資料的問題。 (NEO-46612)
* 修正日文環境升級後期間的問題。 (NEO-46640)
* 修正使用&#x200B;**查詢**&#x200B;活動和篩選表格時的問題。 當欄名稱包含「更新」一詞時，出現編譯錯誤，且識別碼無效，並出現以下訊息：「更新的列數」。(NEO-46485)
* 修正即使在執行期間發生錯誤，仍然阻止 **[!UICONTROL Replicate Staging data]** (ffdaReplicateStagingData) 技術工作流程停止的問題。 (NEO-46280)
* 修正了在測試工作流程錯誤且保留期已完全通過時，可能導致資料遺失的問題。 (NEO-48975)
* 修正使用 Campaign 將資料插入 Snowflake 雲端資料庫的問題&#x200B;**查詢**&#x200B;活動與&#x200B;**變更資料來源**&#x200B;活動：資料中出現反斜線字元時，流程會失敗。 來源字串未逸出，且資料在 Snowflake 時未正確處理。 (NEO-45549)
