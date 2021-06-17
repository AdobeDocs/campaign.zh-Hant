---
product: Adobe Campaign
title: Campaign v8 已知限制
description: 已知限制
feature: 概覽
role: Data Engineer
level: Beginner
hidefromtoc: true
source-git-commit: cf00895f988514fc029d0060d7404bdef0c8b30e
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 87%

---

# 已知限制

已知限制可識別此版本的產品不支援的功能、架構或流程，或無法正確與其相互操作的功能、架構或流程。 請仔細檢閱這些限制。

若為 Adobe Campaign v8，則有下列限制：

* Adobe Campaign v8 不適用於內部部署/混合部署，僅以 Adobe 管理的 Cloud Service 發行。
* 現有客戶無法從現有的 Adobe Campaign 環境移轉至 Adobe Campaign v8
* 無雙向資料複製：複製只會從 Campaign 本機資料庫執行至雲端資料庫
* 此區段](capability-matrix.md#gs-unavailable-features)中列出的功能，不適用於目前的 Campaign v8 版本編號[
* 使用者介面中仍會顯示某些無法使用或已移除的功能
* 訂閱 (選擇加入) 和取消訂閱 (選擇退出) 機制，以及行動註冊為非同步流程。 每小時都會透過特定的技術工作流程處理請求。 [深入瞭解](../config/replication.md#tech-wf)
* 重複項目需要由終端使用者手動處理。 [深入瞭解](../dev/keys.md)
* Adobe Campaign v8不支援API和Web應用程式的延長吞吐量。 若有特定需求，請聯絡Adobe以取得指引。


