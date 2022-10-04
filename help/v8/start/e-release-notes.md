---
title: 搶先的Campaign v8發行說明
description: 搶先推出Campaign v8版本
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
source-git-commit: e873e945f7101c5c54b4b18a128951e08d329b87
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 早期發行說明 {#e-new-release}

本頁說明下一個Campaign v8版本包含的改善和修正。 在發行日期前，本內容可能會有所變更，恕不另行通知。 以下提供正式發行說明： [頁面](../start/release-notes.md).

## 發行版本 8.3.9 {#release-8-3-9}

>[!CAUTION]
>
> 用戶端主控台升級為強制。 透過此檔案了解如何升級您的用戶端主控台 [頁面](../start/connect.md#download-ac-console).

_2022年10月7日_

**功能改進**

* 修正啟用FeatureFlag_GZIP_Compression選項時，影響MID例項上傳送記錄狀態更新的問題。 (NEO-49183)
* 此 **資料庫清理** 技術工作流程現在也可處理自訂的測試結構。 (NEO-48974)
* 修正了可能導致傳遞持續存在的問題 **待定** 狀態，即使已達到聯絡日期亦然。 (NEO-48079、NEO-48251)
* 改善在SOAP呼叫期間處理無效XML字串時的穩定性。 (NEO-48027)
* 修正在排除已列入封鎖名單的收件者步驟期間，鎖定大量收件者時，可能會拖慢傳送分析的速度的問題。 (NEO-48019)
* 為了防止向種子地址發送校樣時速度變慢，現在種子成員的所有連續複製都分組為一個複製請求。 (NEO-44844)
* 修正使用外部傳送模式傳送SMS訊息時，導致個人化問題的問題。 (NEO-46415)
* 修正嘗試在任何「訊息中心」封存事件中預覽傳遞時，顯示錯誤的問題。 (NEO-43620)
* 修正工作流程中，使用 **資料載入（檔案）** 活動。 程式100%停止，但從未結束。 (NEO-47269)
* 修正了當傳送使用日曆和分割模式時，導致建立不必要DeliveryPart的問題。 (NEO-48634)
* 修正使用日曆波段時的效能問題。 (NEO-48451)
* 修正在自訂架構上建立新目標對應後，傳送清單畫面中可能顯示錯誤訊息的問題。 (NEO-49237)
* 修正了在MTA程式期間，傳送達到特定大小時可能發生的問題。 (NEO-46097)
* 修正追蹤記錄無法傳回與收件者瀏覽器相關資料的問題。 (NEO-46612)
* 修正日文環境升級後期間的問題。 (NEO-46640)
* 修正使用 **查詢** 活動和篩選表格。 列名包含&quot;Update&quot;一詞時，出現編譯錯誤，標識符無效，並出現以下消息：&quot;更新的行數&quot;。 (NEO-46485)
* 修正無法 **[!UICONTROL Replicate Staging data]** (fdaReplicateStagingData)技術工作流程即使在執行期間發生錯誤亦無法停止。 (NEO-46280)
* 修正了在測試工作流程錯誤且保留期已完全通過時，可能導致資料遺失的問題。 (NEO-48975)
* 修正使用Campaign將資料插入Snowflake雲端資料庫的問題 **查詢** 活動與 **變更資料來源** 活動：資料中出現反斜線字元時，程式會失敗。 來源字串未逸出，且資料在Snowflake時未正確處理。 (NEO-45549)
