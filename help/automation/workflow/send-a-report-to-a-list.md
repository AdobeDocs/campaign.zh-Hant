---
product: campaign
title: 傳送報吿至清單
description: 瞭解如何使用工作流將報告發送到清單
feature: Workflows
exl-id: 5bc576d0-cab7-4d26-a3a5-91982a00e356
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 3%

---

# 傳送報吿至清單{#send-a-report-to-a-list}

此使用案例詳細說明了如何生成每月開箱即用 **[!UICONTROL Tracking indicators]** 以PDF格式報告，以及如何將其發送到收件人清單。

![](assets/use_case_report_intro.png)

此使用案例的主要實施步驟是：

* 為此報告建立收件人清單。 [了解更多](#step-1--create-the-recipient-list)。
* 建立每次執行工作流時都會建立新交貨的交貨模板。 [了解更多](#step-2--create-the-delivery-template)。
* 建立工作流，該工作流以PDF格式生成報表，並將其發送到收件人清單。 [了解更多](#step-3--create-the-workflow)).

## 步驟1:建立收件人清單 {#step-1--create-the-recipient-list}

要建立目標收件人清單，請執行以下步驟：

1. 瀏覽到 **[!UICONTROL Profiles and targets]** 頁籤 **[!UICONTROL Lists]** 的子菜單。
1. 按一下 **[!UICONTROL Create]** 按鈕。
1. 選擇 **[!UICONTROL New list]** 並為要發送到的報告建立新收件人清單。

有關建立清單的詳細資訊，請參閱 [此部分](../../v8/audiences/create-audiences.md)。

## 步驟2:建立交貨模板 {#step-2--create-the-delivery-template}

要建立交貨模板，請執行以下步驟：

1. 瀏覽到 **[!UICONTROL Resources > Templates > Delivery templates]** 的子目錄，並複製 **[!UICONTROL Email delivery]** 內置模板。

   有關建立交貨模板的詳細資訊，請參閱 [此部分](../../v8/send/create-templates.md)。

1. 輸入模板參數：標籤、目標（先前建立的收件人清單）、主題和內容。

   每次執行工作流時， **[!UICONTROL Tracking indicators]** 報告已更新，如中所述 [第3步：建立工作流](#step-3--creating-the-workflow))。

1. 要在交貨中包括報表的最新版本，您需要添加 **[!UICONTROL Calculated attachment]**:

   * 按一下 **[!UICONTROL Attachments]** 連結，然後按一下 **[!UICONTROL Add]** 按鈕 選取 **[!UICONTROL Calculated attachment...]**。

      ![](assets/use_case_report_4.png)

   * 在 **[!UICONTROL Type]** 下拉清單中，選擇最新選項： **[!UICONTROL File name is computed during delivery of each message (it may then depend on the recipient profile)]**。

      ![](assets/use_case_report_5.png)

      在 **[!UICONTROL Label]** 欄位將不顯示在最終交貨中。

   * 在文本區域中，輸入檔案的訪問路徑和名稱。

      ![](assets/use_case_report_6.png)

      >[!CAUTION]
      >
      >路徑和名稱必須與在 **[!UICONTROL JavaScript code]** 工作流的類型活動，如中所述 [第3步：建立工作流](#step-3--creating-the-workflow)。

   * 選擇 **[!UICONTROL Advanced]** 頁籤 **[!UICONTROL Script the name of the file name displayed in the mails sent]**。 在文本區域中，在最終交貨中輸入附件的名稱。

      ![](assets/use_case_report_6b.png)

## 第3步：建立工作流 {#step-3--creating-the-workflow}

為此用例建立以下工作流。

![](assets/use_case_report_8.png)

它使用三種活動：

* A **[!UICONTROL Scheduler]** 執行工作流的活動，
* A **[!UICONTROL JavaScript code]** 以PDF格式生成報表的活動，
* A **[!UICONTROL Delivery]** 引用先前建立的交貨模板的活動。

要構建此工作流，請執行以下步驟：

1. 瀏覽到 **[!UICONTROL Administration > Production > Technical workflows]** 「市場活動」瀏覽器的節點，並建立一個新資料夾以儲存您的工作流。
1. 建立新工作流。

   ![](assets/use_case_report_7.png)

1. 開始添加 **[!UICONTROL Scheduler]** 鍵入activity並配置它，以便工作流在當月的第一個星期一執行。

   ![](assets/use_case_report_9.png)

   有關配置調度程式的詳細資訊，請參閱 [調度程式](scheduler.md)。

1. 然後添加 **[!UICONTROL JavaScript code]** 鍵入活動。

   ![](assets/use_case_report_10.png)

   在編輯區域中輸入以下代碼：

   ```sql
   var reportName = "indicators";
   var path = "/tmp/indicators.pdf";
   var exportFormat = "PDF";
   var reportURL = "<PUT THE URL OF THE REPORT HERE>";
   var _ctx = <ctx _context="global" _reportContext="deliveryFeedback" />
   var isAdhoc = 0;
   
   xtk.report.export(reportName, _ctx, exportFormat, path, isAdhoc);
   ```


   具有以下變數：

   * **var reportName**:以雙引號輸入報表的內部名稱。 在本例中， **跟蹤指示器** 報告為「deliveryFeedback」。
   * **var路徑**:輸入檔案的保存路徑(&quot;tmp&quot;)、要給該檔案的名稱(&quot;deliveryFeedback&quot;)和檔案副檔名(&quot;。pdf&quot;)。 在本例中，我們使用內部名稱作為檔案名。 值必須介於雙引號之間，並由&quot;+&quot;字元分隔。

      >[!CAUTION]
      >
      >檔案必須保存在伺服器上。 必須輸入與中相同的路徑和名稱 **[!UICONTROL General]** 的子菜單。 [這裡](#step-2--create-the-delivery-template))。

   * **var導出格式**:輸入檔案的導出格式(「PDF」)。
   * **var_ctx** （上下文）:在這個例子中，我們使用 **[!UICONTROL Tracking indicators]** 報告。

1. 通過添加 **[!UICONTROL Delivery]** 活動，具有以下選項：

   ![](assets/use_case_report_11.png)

   * **[!UICONTROL Delivery]**:選擇 **[!UICONTROL New, created from a template]**，然後選擇以前建立的交貨模板。
   * 對於 **[!UICONTROL Recipients]** 和 **[!UICONTROL Content]** 欄位，選擇 **[!UICONTROL Specified in the delivery]**。
   * **[!UICONTROL Action to perform]**:選擇 **[!UICONTROL Prepare and start]**。
   * 取消檢查 **[!UICONTROL Generate an outbound transition]** 和 **[!UICONTROL Process errors]** 頁籤

1. 保存更改並啟動工作流。 每月的第一個星期一，該郵件會連同附帶的報告發送到收件人清單。
