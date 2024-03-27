---
product: campaign
title: 傳送報吿至清單
description: 瞭解如何使用工作流程將報告傳送至清單
feature: Workflows
exl-id: 5bc576d0-cab7-4d26-a3a5-91982a00e356
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 3%

---

# 傳送報吿至清單{#send-a-report-to-a-list}

此使用案例詳細說明如何產生立即可用的每月帳單 **[!UICONTROL Tracking indicators]** 以PDF格式報告，以及如何將其傳送給收件者清單。

![](assets/use_case_report_intro.png)

此使用案例的主要實施步驟為：

* 建立此報告的收件者清單。 [了解更多](#step-1--create-the-recipient-list)。
* 建立傳遞範本，每次執行工作流程時都會建立新的傳遞。 [了解更多](#step-2--create-the-delivery-template)。
* 建立工作流程，以PDF格式產生報表並傳送至收件者清單。 [瞭解更多](#step-3--create-the-workflow))。

## 步驟1：建立收件者清單 {#step-1--create-the-recipient-list}

若要建立目標收件者清單，請遵循下列步驟：

1. 瀏覽至 **[!UICONTROL Profiles and targets]** 索引標籤，按一下 **[!UICONTROL Lists]** 連結。
1. 按一下 **[!UICONTROL Create]** 按鈕。
1. 選取 **[!UICONTROL New list]** 並為要接收的報告建立新的收件者清單。

有關建立清單的詳細資訊，請參閱 [本節](../../v8/audiences/create-audiences.md).

## 步驟2：建立傳遞範本 {#step-2--create-the-delivery-template}

若要建立傳遞範本，請遵循下列步驟：

1. 瀏覽至 **[!UICONTROL Resources > Templates > Delivery templates]** Adobe Campaign explorer的節點，並複製 **[!UICONTROL Email delivery]** 內建範本。

   有關建立傳遞範本的詳細資訊，請參閱 [本節](../../v8/send/create-templates.md).

1. 輸入範本引數：標籤、目標（先前建立的收件者清單）、主旨與內容。

   每次執行工作流程時， **[!UICONTROL Tracking indicators]** 報告已更新，如中所述： [步驟3：建立工作流程](#step-3--creating-the-workflow))。

1. 若要在傳送中包含最新版本的報告，您必須新增 **[!UICONTROL Calculated attachment]**：

   * 按一下 **[!UICONTROL Attachments]** 連結，並按一下 **[!UICONTROL Add]** 按鈕。 選取 **[!UICONTROL Calculated attachment...]**。

     ![](assets/use_case_report_4.png)

   * 在 **[!UICONTROL Type]** 從下拉式清單中選取最新的選項： **[!UICONTROL File name is computed during delivery of each message (it may then depend on the recipient profile)]**.

     ![](assets/use_case_report_5.png)

     輸入的值 **[!UICONTROL Label]** 欄位不會出現在最終傳送中。

   * 在文字區域中，輸入檔案的存取路徑和名稱。

     ![](assets/use_case_report_6.png)

     >[!CAUTION]
     >
     >路徑和名稱必須與 **[!UICONTROL JavaScript code]** 輸入工作流程的活動，如中所述 [步驟3：建立工作流程](#step-3--creating-the-workflow).

   * 選取 **[!UICONTROL Advanced]** 標籤並核取 **[!UICONTROL Script the name of the file name displayed in the mails sent]**. 在文字區域中，輸入最終傳遞中的附件名稱。

     ![](assets/use_case_report_6b.png)

## 步驟3：建立工作流程 {#step-3--creating-the-workflow}

針對此使用案例建立下列工作流程。

![](assets/use_case_report_8.png)

它會使用三個活動：

* A **[!UICONTROL Scheduler]** 每月執行一次工作流程的活動，
* A **[!UICONTROL JavaScript code]** 會以PDF格式產生報表的活動，
* A **[!UICONTROL Delivery]** 活動，此活動會參考先前建立的傳遞範本。

若要建置此工作流程，請遵循下列步驟：

1. 瀏覽至 **[!UICONTROL Administration > Production > Technical workflows]** 節點，並建立新資料夾以儲存您的工作流程。
1. 建立新的工作流程。

   ![](assets/use_case_report_7.png)

1. 從新增 **[!UICONTROL Scheduler]** 輸入活動並進行設定，讓工作流程在當月第一個星期一執行。

   ![](assets/use_case_report_9.png)

   有關設定排程器的詳細資訊，請參閱 [排程器](scheduler.md).

1. 然後新增 **[!UICONTROL JavaScript code]** 輸入活動。

   ![](assets/use_case_report_10.png)

   在編輯區域中輸入下列程式碼：

   ```sql
   var reportName = "indicators";
   var path = "/tmp/indicators.pdf";
   var exportFormat = "PDF";
   var reportURL = "<PUT THE URL OF THE REPORT HERE>";
   var _ctx = <ctx _context="global" _reportContext="deliveryFeedback" />
   var isAdhoc = 0;
   
   xtk.report.export(reportName, _ctx, exportFormat, path, isAdhoc);
   ```


   ，並使用下列變數：

   * **var reportName**：以雙引號輸入報表的內部名稱。 在此案例中， **追蹤指標** 報表為「deliveryFeedback」。
   * **變數路徑**：輸入檔案的儲存路徑(「tmp」)、您要提供檔案的名稱(「deliveryFeedback」)和副檔名(「.pdf」)。 在此案例中，我們使用內部名稱作為檔案名稱。 值必須位於雙引號之間，並以「+」字元分隔。

     >[!CAUTION]
     >
     >檔案必須儲存在伺服器上。 您必須輸入與中的相同的路徑和相同的名稱 **[!UICONTROL General]** 已計算附件之編輯視窗的標籤（如詳細） [此處](#step-2--create-the-delivery-template))。

   * **var exportFormat**：輸入檔案的匯出格式(「PDF」)。
   * **var _ctx** （上下文）：在此案例中，我們使用 **[!UICONTROL Tracking indicators]** 在其全域內容中報告。

1. 完成方式是新增 **[!UICONTROL Delivery]** 活動，包含下列選項：

   ![](assets/use_case_report_11.png)

   * **[!UICONTROL Delivery]**：選取 **[!UICONTROL New, created from a template]**，並選取先前建立的傳送範本。
   * 對於 **[!UICONTROL Recipients]** 和 **[!UICONTROL Content]** 欄位，選取 **[!UICONTROL Specified in the delivery]**.
   * **[!UICONTROL Action to perform]**：選取 **[!UICONTROL Prepare and start]**.
   * 取消勾選 **[!UICONTROL Generate an outbound transition]** 和 **[!UICONTROL Process errors]** 選項。

1. 儲存變更並啟動工作流程。 該訊息會在該月的第一個星期一傳送至收件者清單，並附上報告。
