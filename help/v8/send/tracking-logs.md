---
title: 存取追蹤記錄
description: 瞭解如何存取及解讀追蹤記錄
feature: Monitoring
role: User
level: Beginner
exl-id: df494786-5950-4646-aa9c-4dde45845057
source-git-commit: 5b23be4cb8f0896d2482e525e416713b1a6c4514
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---

# 存取追蹤記錄 {#accessing-the-tracking-logs}

傳送傳遞並啟用追蹤後，**[!UICONTROL Tracking]**&#x200B;技術工作流程會負責擷取追蹤資料。 預設會每小時執行。

## 在收件者設定檔中檢視追蹤 {#recipient-tracking}

此資訊會顯示在傳遞所目標定位之收件者設定檔的&#x200B;**[!UICONTROL Tracking]**&#x200B;標籤中，如下列範例所示：

![](assets/s_ncs_user_select_tracking_tab_from_recipient.png)

此索引標籤會顯示收件者追蹤及點按的所有URL，包括：

* 點選的URL
* 點按的日期和時間
* 找到URL的傳遞
* 任何其他相關追蹤資訊

您可以篩選和排序此資訊，以分析收件者行為並識別參與模式。

## 在傳遞中檢視追蹤 {#delivery-tracking}

追蹤資訊也可透過傳遞的&#x200B;**[!UICONTROL Tracking]**&#x200B;索引標籤存取。

![](assets/s_ncs_user_select_tracking_tab_from_del.png)

在此標籤中，您可以檢視：

* **[!UICONTROL Tracking statistics]**：提供開啟、點按及其他追蹤事件的概觀
* **[!UICONTROL URLs and click streams]**：顯示點選了哪些連結及其點選次數
* **[!UICONTROL Hot clicks]**：顯示收件者點按您郵件位置的視覺化表示
* **[!UICONTROL Tracking logs]**：提供詳細的個別追蹤記錄

## 疑難排解追蹤 {#troubleshooting}

>[!NOTE]
>
>如果您看不到傳遞的&#x200B;**[!UICONTROL Tracking]**&#x200B;索引標籤，表示尚未啟用追蹤。 請參閱[本節](tracked-links.md)以瞭解如何設定追蹤。

### 檢查追蹤技術工作流程 {#check-tracking-workflow}

追蹤技術工作流程必須執行中，才能收集追蹤資料。 您可以在&#x200B;**[!UICONTROL Administration > Production > Technical workflows]**&#x200B;資料夾中找到「追蹤」技術工作流程。

若要驗證工作流程：

1. 開啟&#x200B;**[!UICONTROL Tracking]**&#x200B;工作流程
1. 檢查上一個執行日期
1. 確認工作流程記錄檔中沒有錯誤

如果工作流程未執行或有錯誤，請聯絡您的系統管理員。

## 驗證追蹤資料收集

傳送已啟用追蹤的傳遞後：

1. 等待追蹤工作流程執行（預設為每小時）
1. 開啟傳遞，然後前往&#x200B;**[!UICONTROL Tracking]**&#x200B;標籤
1. 檢查是否有追蹤資料出現
1. 如果未顯示任何資料，請檢查：
   * 已在傳遞設定中啟用追蹤
   * 追蹤技術工作流程正在執行中
   * 收件者已開啟電子郵件並按一下連結

## 相關主題 {#related-topics}

* [瞭解如何設定追蹤的連結](tracked-links.md)
* [瞭解如何測試追蹤](testing-tracking.md)
* [瞭解追蹤報表](../reporting/delivery-reports.md#tracking-indicators)

