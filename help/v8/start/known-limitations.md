---
product: Adobe Campaign
title: Campaign v8已知限制
description: 已知限制
feature: 概覽
role: Data Engineer
level: Beginner
hidefromtoc: true
source-git-commit: 08c1f2fbe79845fe54670e25ac4a63ab65517513
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 3%

---

# 已知限制

已知限制可識別此版本的產品不支援的功能、架構或程式，或無法正確與其互操作的功能、架構或程式。 請仔細檢閱這些限制。

若為Adobe Campaign v8，則有下列限制：

* Adobe Campaign v8不適用於內部部署/混合部署 — 僅以「Adobe管理」Cloud Service發行。
* 現有客戶無法從現有的Adobe Campaign環境移轉至Adobe Campaign v8
* 無雙向資料複製：復寫只會從Campaign本機資料庫執行至雲端資料庫
* 此區段](capability-matrix.md#gs-unavailable-features)中列出的功能，不適用於目前的Campaign v8組建[
* 使用者介面中仍會顯示某些無法使用或已移除的功能
* 訂閱（選擇加入）和取消訂閱（選擇退出）機制，以及行動註冊為非同步程式。 系統會透過特定的技術工作流程，每小時處理要求。 [瞭解更多](../config/replication.md#tech-wf)
* 重複項目需要由使用者手動處理。 [瞭解更多](../dev/keys.md)
* LINE — 確認+詳細資訊
* 延遲 — 確認+詳細資訊
