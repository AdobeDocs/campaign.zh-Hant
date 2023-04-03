---
title: Campaign v8 發行說明
description: 最新的 Campaign v8 版本
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 44743e585119e8cd81a8fcc9b4d667c25c0d438e
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 79%

---

# 最新發行版本{#latest-release}

本頁面列出&#x200B;**最新 Campaign v8 版本**&#x200B;的新功能、改善和修正。

## 發行版本 8.4.5 {#release-8-4-5}

_2023年4月3日_

**修補程式**

* 修正若將數個核准工作流程設為相同排程時，可能導致重複金鑰限制錯誤的問題。 (NEO-48968)
* 修正NEO-54474(8.4.4)所導致在數位內容編輯器(DCE)中上傳影像時，內文標籤的樣式屬性有所變更的回歸問題。 (NEO-57697)
* 修正了使用CRM連接器匯出資料時，如果臨時表格的主索引鍵定義為long而非uuid，則可能導致錯誤的問題。 (NEO-54153)
* 修正8.4.1版中導入的回歸問題，此問題可能導致套件匯出、FDA over HTTP和報表出錯。 (NEO-57731)
* 修正8.3.8版中導入的回歸問題，此問題會導致無法針對ID為負的傳送正確更新傳送狀態。 (NEO-54675)
* 修正使用Big Query connector匯入資料時布林欄位的問題(NEO-49181)

>[!CAUTION]
>
> 用戶端主控台升級為強制。 透過本[頁面](../start/connect.md#upgrade-ac-console)了解如何升級您的用戶端主控台。

## 發行版本 8.4.4 {#release-8-4-4}

_2023 年 3 月 8 日_

**安全性增強功能**

* 為了改善安全性，已將 Tomcat 從 8.5.81 版更新至 8.5.85 版。 (NEO-50530)

**修補程式**

* 修正了無法在數位內容編輯器 (DCE) 捲動&#x200B;**編輯**&#x200B;索引標籤的問題。 (NEO-54474)
* 修正可能於複製期間導致 Web 伺服器當機的問題。 (NEO-53670)


>[!CAUTION]
>
> 用戶端主控台升級為強制。 透過本[頁面](../start/connect.md#upgrade-ac-console)了解如何升級您的用戶端主控台。


## 發行版本 8.4.3 {#release-8-4-3}


_2023 年 1 月 27 日_

**功能改進**

* 修正行銷伺服器與中間來源伺服器之間的傳送指標同步問題。(NEO-50724) <!--OKKKK-->
* 修正匯出工作流程時可能導致錯誤的問題。(NEO-50555) <!--OKKKK-->
* 修正延伸以前延伸之架構時出現的問題。(NEO-49118) <!--OKKKK-->
* 修正在連結定義中使用兩個具有相同識別碼的擴充活動時出現的問題。(NEO-48851)
* 修正兩個傳送準備失敗問題。當操作的潛在優惠方案數量太多時，傳送準備可能會失敗。 當影像 URL 定義為要在文字格式傳送中追蹤的 URL 時，會出現第二個問題。(NEO-48807) <!--OKKKK-->
* 修正可能導致工作流程失敗的問題，即工作流程會覆寫非 FFDA 帳戶外部帳戶中定義的倉儲名稱。(NEO-43209) <!--OKKKK-->
* 改善網站應用程式的安全性，以防止 DDoS 攻擊。 (NEO-50757) <!--OKKKK-->
* **[!UICONTROL Consolidated tracking]**(nms:trackingStats) FFDA 表中對合併追蹤資料的管理已得到改善，以避免重複。(NEO-46409)
* 修正在邏輯運算子條件下使用`enableIf`時工作流程查詢中的邏輯運算問題。已覆寫先前的邏輯條件。 (NEO-45815)  <!--OKKKK-->
* 帳單工作流程中已最佳化作用中設定檔的產生，以改善效能。(NEO-47658) <!--OKKKK-->
* 修正當影像節點 (img) 包含具有個人化欄位的 URL 時，HTML 檔案匯入的問題。 (NEO-48396)
* 修正在&#x200B;**分割**&#x200B;工作流程活動中使用排序參數時 Snowflake (所有部署) 的問題。(NEO-45899) <!--OKKKK-->
* 修正了當 nmsDeliveryMapping 資料夾上具有讀取存取權限的使用者嘗試執行行銷活動或工作流程時，導致錯誤的問題。 (NEO-48230)
* 修正傳送 HTML 標籤中，大型 HTML 程式碼可能發生的效能問題。 (NEO-47440)
<!-- * Fixed an issue which could lead to a "Character set mismatch" error when using certain functions such as `to_nclob` with an Oracle unicode database where NChar was not enabled. (NEO-49361)
* Fixed an issue which prevented users from inserting a Time datatype in a **Data Update** workflow activity on MSSQL. (NEO-47763)-->
* 修正阻止使用者使用&#x200B;**合併所選列**&#x200B;工作流程選項的問題。(NEO-48488)
* 修正 Snowflake FDA 連接器所引入的問題，此問題在擴充期間使用「0 或 1 基數簡單加入」選項時，會導致記錄遭到捨棄。 (NEO-48737)
* 對 log4j 程式庫的其餘參考已從 Windows 上安裝的 Campaign 中移除。 (NEO-44851)
* 修正在&#x200B;**查詢** 工作流程活動的其他資料中新增&#x200B;**已開啟的收件者**  (estimatedRecipientOpen) 指標導致錯誤的問題。(NEO-46665)
* 透過多次傳送來改善工作流程中追蹤 URL 的管理，以提升效能。(NEO-50894) <!--OKKKK-->
* 修正可能導致使用 Xtkfolder 的結構複寫失敗的問題。(NEO-46787) <!--OKKKK-->
* 修正可能導致「lastModified」自訂欄在 NmsSubscription 表格中被刪除的問題。(NEO-48402)


>[!CAUTION]
>
> 用戶端主控台升級為強制。 透過本[頁面](../start/connect.md#upgrade-ac-console)了解如何升級您的用戶端主控台。
