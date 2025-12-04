---
title: 測試訊息追蹤
description: 瞭解如何在傳送傳遞前測試訊息追蹤
feature: Monitoring
role: User
level: Beginner
exl-id: 16ad36b7-c13e-4b77-86ca-41c9ef174172
source-git-commit: edbe7ab49a628436dfb4d27ae17122917d7371e9
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 1%

---

# 測試訊息追蹤 {#testing-tracking}

在將您的傳送傳送傳送傳送給整個對象之前，必須測試追蹤功能，以確保所有連結正確運作且正確擷取追蹤資料。 此驗證程式可協助您在行銷活動開始前識別並修正任何追蹤問題，防止連結重新導向、追蹤畫素載入或資料收集的潛在問題。

測試追蹤可讓您：

* 確認訊息中的所有連結受到正確追蹤，且重新導向正確
* 確認映象頁面連結有效並被追蹤
* 請確定開啟追蹤的追蹤畫素載入正確
* 檢查是否已正確擷取URL中的個人化引數
* 驗證追蹤技術工作流程是否正確處理資料

您可以依照下列步驟，測試映象頁面、電子郵件記錄檔和連結上的追蹤：

## 步驟1：建立測試傳送 {#create-test-delivery}

1. 建立用於測試的新電子郵件傳遞。 [了解如何建立傳遞](../start/create-message.md)
1. 使用您要追蹤的連結設計您的電子郵件內容。 [瞭解電子郵件內容設計](defining-the-email-content.md)
1. 在電子郵件內容中新增映象頁面個人化區塊。 [瞭解個人化區塊](personalization-blocks.md)

   ![](assets/mirror-page-insert.png)

1. 指定將接收電子郵件的使用者。 由於此使用者必須開啟電子郵件並按一下其中包含的連結，因此請確定您選取您控制的測試收件者地址。 [瞭解測試設定檔](../audiences/test-profiles.md)

## 步驟2：傳送測試傳送 {#send-test}

1. 確認已在傳送設定中啟用追蹤：
   * 開啟您的傳遞的&#x200B;**[!UICONTROL Properties]**
   * 前往&#x200B;**[!UICONTROL Tracking & Images]**&#x200B;區段
   * 確定已核取&#x200B;**[!UICONTROL Activate tracking]**
   * 如果您要追蹤開啟專案，請確定已核取&#x200B;**[!UICONTROL Opens tracking]**

   ![](assets/s_ncs_user_email_del_tracking_param.png)

[深入瞭解URL追蹤選項](url-tracking.md)

1. 將傳遞傳送給測試收件者。 [瞭解傳送傳遞](configure-and-send.md)

## 步驟3：驗證追蹤功能 {#verify-tracking}

1. 收到電子郵件後，請開啟並按一下映象頁面連結。 [瞭解映象頁面](mirror-page.md)
1. 按一下電子郵件中的各種連結，以產生追蹤資料。
1. 在您正確重新導向至映象頁面後，請存取&#x200B;**[!UICONTROL Administration > Production > Technical workflows]**&#x200B;資料夾。 [瞭解工作流程](../config/workflows.md)
1. 開啟&#x200B;**[!UICONTROL Tracking]**&#x200B;工作流程。
1. 啟動工作流程，或用滑鼠右鍵按一下&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動並選取&#x200B;**[!UICONTROL Execute pending task now]**。
1. 等候約30秒讓工作流程處理追蹤記錄。
1. 選取工作流程的&#x200B;**[!UICONTROL Audit]**&#x200B;標籤。 請確定至少找到一個追蹤記錄記錄。 如果您沒有看到任何新記錄，請按一下&#x200B;**[!UICONTROL Refresh]**。

1. 驗證傳送中的追蹤記錄：
   * 返回您的傳遞
   * 選取&#x200B;**[!UICONTROL Tracking]**&#x200B;索引標籤
   * 檢查追蹤記錄清單是否隨已點按URL和其他追蹤事件而顯示

   ![](assets/s_ncs_user_delivery_tracking_tab.png)

## 步驟4：檢查收件者追蹤標籤 {#check-recipient-tracking}

1. 移至您用於測試的收件者之設定檔頁面。 [瞭解如何檢視設定檔](../audiences/view-profiles.md)
   * 收件者的設定檔頁面預設位於&#x200B;**[!UICONTROL Profiles and Targets > Recipients]**&#x200B;資料夾。

1. 選取 **[!UICONTROL Tracking]** 索引標籤。[進一步瞭解追蹤記錄](tracking-logs.md)

   ![](assets/s_ncs_user_select_tracking_tab_from_recipient.png)

1. 確認追蹤記錄的顯示方式：
   * **[!UICONTROL Mirror Page]**&#x200B;欄中的&#x200B;**[!UICONTROL Type]**&#x200B;值
   * 電子郵件開啟次數的&#x200B;**[!UICONTROL Open]**&#x200B;欄中的&#x200B;**[!UICONTROL Type]**&#x200B;個值
   * 在&#x200B;**[!UICONTROL Email click]**&#x200B;欄中有&#x200B;**[!UICONTROL Type]**&#x200B;個連結點選值

## 疑難排解追蹤測試 {#troubleshooting-tracking-test}

如果追蹤記錄未顯示：

1. **檢查傳遞設定**：移至傳遞並存取其&#x200B;**[!UICONTROL Properties]**，以確定已同時檢查&#x200B;**[!UICONTROL Activate tracking]**&#x200B;和&#x200B;**[!UICONTROL Opens tracking]**&#x200B;選項。 [進一步瞭解URL追蹤選項](url-tracking.md)

1. **驗證追蹤工作流程**：確定&#x200B;**[!UICONTROL Tracking]**&#x200B;技術工作流程正在執行且沒有錯誤。 [瞭解追蹤工作流程疑難排解](tracking-logs.md#check-tracking-workflow)

1. **檢查URL格式**：確認您的URL格式正確，並以分隔符號括住。 [進一步瞭解設定追蹤的連結](tracked-links.md)

1. **檢閱電子郵件使用者端行為**：某些電子郵件使用者端可能會封鎖追蹤畫素或修改連結。 嘗試使用不同的電子郵件使用者端進行測試。 [瞭解傳遞最佳實務](../start/delivery-best-practices.md)

1. **等待處理**：追蹤工作流程預設會每小時執行。 如果您手動觸發，請在檢查結果前留出足夠的處理時間。 [進一步瞭解追蹤記錄](tracking-logs.md)

## 相關主題 {#related-topics}

* [瞭解如何設定追蹤的連結](tracked-links.md)
* [瞭解如何存取追蹤記錄](tracking-logs.md)
* [瞭解追蹤報表](../reporting/delivery-reports.md#tracking-indicators)

