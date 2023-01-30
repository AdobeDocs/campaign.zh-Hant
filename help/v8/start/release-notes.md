---
title: Campaign v8 發行說明
description: 最新的 Campaign v8 版本
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: e7f4982a9b13fe5413b6cce0a1cc58e2b3a6afa4
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 34%

---

# 最新發行版本{#latest-release}

本頁面列出&#x200B;**最新 Campaign v8 版本**&#x200B;的新功能、改善和修正。

## 發行版本 8.4.3 {#release-8-4-3}

>[!CAUTION]
>
> 用戶端主控台升級為強制。 透過本[頁面](../start/connect.md#download-ac-console)了解如何升級您的用戶端主控台。

_2023年1月27日_

**功能改進**

* 修正行銷伺服器與中間來源伺服器之間的傳送指標同步問題。 (NEO-50724) <!--OKKKK-->
* 修正匯出工作流程時可能導致錯誤的問題。 (NEO-50555) <!--OKKKK-->
* 修正擴充先前已擴充之架構時的問題。 (NEO-49118) <!--OKKKK-->
* 修正在連結定義中使用具有相同識別碼的兩個擴充活動時的問題。 (NEO-48851)
* 修正了兩個傳送準備失敗問題。 當操作的潛在選件數量太多時，傳送準備可能會失敗。 第二個問題是將影像URL定義為要在文字格式傳送中追蹤的URL時。 (NEO-48807) <!--OKKKK-->
* 修正了可能導致工作流程失敗的問題，亦即工作流程會覆寫非FFDA帳戶外部帳戶中定義的倉儲名稱。 (NEO-43209) <!--OKKKK-->
* 改善Web應用程式的安全性，以防止DDoS攻擊。 (NEO-50757) <!--OKKKK-->
* 已改善 **[!UICONTROL Consolidated tracking]** (nms:trackingStats)FFDA表格以避免重複。 (NEO-46409)
* 修正使用 `enableIf` 在邏輯運算子條件中。 已覆寫先前的邏輯條件。 (NEO-45815)  <!--OKKKK-->
* 帳單工作流程中已最佳化作用中設定檔的產生，以改善效能。 (NEO-47658) <!--OKKKK-->
* 修正當影像節點 (img) 包含具有個人化欄位的 URL 時，HTML 檔案匯入的問題。 (NEO-48396)
* 修正使用排序參數(位於 **分割** 工作流程活動。 (NEO-45899) <!--OKKKK-->
* 修正了當 nmsDeliveryMapping 資料夾上具有讀取存取權限的使用者嘗試執行行銷活動或工作流程時，導致錯誤的問題。 (NEO-48230)
* 修正傳送 HTML 標籤中，大型 HTML 程式碼可能發生的效能問題。 (NEO-47440)
<!-- * Fixed an issue which could lead to a "Character set mismatch" error when using certain functions such as `to_nclob` with an Oracle unicode database where NChar was not enabled. (NEO-49361)
* Fixed an issue which prevented users from inserting a Time datatype in a **Data Update** workflow activity on MSSQL. (NEO-47763)-->
* 修正使用者無法使用 **合併所選行** 工作流程選項。 (NEO-48488)
* 修正了在SnowflakeFDA連接器上，在擴充期間使用「0或1基數簡單加入」選項時，會捨棄記錄的問題。 (NEO-48737)
* 對 log4j 程式庫的其餘參考已從 Windows 上安裝的 Campaign 中移除。 (NEO-44851)
* 修正在&#x200B;**查詢** 工作流程活動的其他資料中新增&#x200B;**已開啟的收件者**  (estimatedRecipientOpen) 指標導致錯誤的問題。(NEO-46665)
* 透過多次傳送來改善工作流程中追蹤URL的管理，以提升效能。 (NEO-50894) <!--OKKKK-->
* 修正了可能導致使用Xtkfolder的結構復寫失敗的問題。 (NEO-46787) <!--OKKKK-->
* 修正了導致「lastModified」自訂欄被拖放到NmsSubscription表格的問題。 (NEO-48402)
