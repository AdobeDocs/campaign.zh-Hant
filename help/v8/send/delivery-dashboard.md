---
title: 在Campaign UI中監視您的傳遞
description: 瞭解如何存取傳遞清單，並使用傳遞儀表板來監視您的傳遞
feature: Monitoring
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 3%

---

# 在Campaign UI中監視您的傳遞 {#delivery-dashboard}

監控您的傳送至關重要，以確保您的行銷活動有效並觸及客戶。 Adobe Campaign提供您存取傳遞的工具，並透過傳遞清單和傳遞控制面板監控其效能。

## 存取傳遞清單 {#list-of-deliveries}

您可以透過樹狀結構的&#x200B;**[!UICONTROL Campaign Management > Deliveries]**&#x200B;節點，從傳遞清單存取傳遞。

![](assets/deliveries-list.png)

依預設，傳遞清單包含在所選節點中建立的傳遞的名稱和狀態。 它也會顯示成功傳送、處理和傳送的訊息數。

* **[!UICONTROL Messages to send]**&#x200B;的數目對應於分析之後和傳遞之前的目標收件者數目。
* **[!UICONTROL Success]**&#x200B;欄中的訊息數目與伺服器所傳送及收件者所接收的訊息數目相對應。
* **[!UICONTROL Processed]**&#x200B;個訊息的數目對應於已接收的訊息數目加上發生錯誤的訊息數目。

>[!NOTE]
>
>對於大型傳送，您可以更新這些值。 若要這麼做，請選取有問題的傳送，然後在其上按一下滑鼠右鍵。 選取&#x200B;**[!UICONTROL Action > Recompute delivery and tracking indicators...]**，然後使用該助理來更新此資訊。

## 傳遞控制面板總覽 {#delivery-dashboard-overview}

**傳遞儀表板**&#x200B;是監視您的傳遞以及在傳送訊息期間遇到的最終問題的關鍵。

它可讓您擷取傳送的相關資訊，並在必要時加以編輯。 請注意，傳送後，索引標籤內容可能不會再變更。

以下是使用控制面板中提供的數個標籤來監視的資訊：

* [傳遞摘要](#delivery-summary)
* [傳遞報告](#delivery-reports)
* [傳遞記錄、映象頁面、排除專案](#delivery-logs-and-history)
* [傳遞追蹤記錄和歷史記錄](#tracking-logs)
* [傳遞呈現](#delivery-rendering)
* [傳遞稽核](#delivery-audit-)

![](assets/s_ncs_user_del_details.png)

**相關主題：**

* [瞭解傳遞失敗](delivery-failures.md)
* [隔離管理](quarantines.md)
* [關於傳遞的最佳實務](../start/delivery-best-practices.md)
* [管理傳遞能力](about-deliverability.md)

## 傳遞摘要 {#delivery-summary}

**[!UICONTROL Summary]**&#x200B;索引標籤包含傳遞的特性：傳遞狀態、使用的管道、寄件者的相關資訊、主旨、執行的相關資訊。

## 傳遞報告 {#delivery-reports}

可從&#x200B;**[!UICONTROL Reports]**&#x200B;標籤存取的&#x200B;**[!UICONTROL Summary]**&#x200B;連結可讓您檢視與傳遞動作相關的一組報告：一般傳遞報告、詳細報告、傳遞報告、失敗訊息的分發、年初匯率、點按和交易等。

您可以根據自己的需求設定此標籤的內容。 如需傳遞報告的詳細資訊，請參閱[本節](../reporting/delivery-reports.md)。

![](assets/delivery-report.png)

## 傳遞記錄、記錄和排除 {#delivery-logs-and-history}

**[!UICONTROL Delivery]**&#x200B;索引標籤會提供此傳遞中發生的記錄。 它包含傳遞記錄，即已傳送的訊息清單及其狀態和相關聯的訊息。

對於傳遞，您可以（例如）僅顯示傳送失敗或在隔離中的地址的收件者。 若要這麼做，請按一下&#x200B;**[!UICONTROL Filters]**&#x200B;按鈕並選取&#x200B;**[!UICONTROL By state]**。 然後在下拉式清單中選取狀態。 各種狀態列於[傳遞狀態頁面](delivery-statuses.md)。

>[!NOTE]
>
>顯示傳送記錄的清單可與Campaign中的任何清單一樣自訂。 例如，您可以新增欄，以瞭解在傳送中每封電子郵件傳送了哪個IP位址。 如需設定清單顯示的詳細資訊，請參閱[本節](../config/ui-settings.md#customize-lists)。

![](assets/s_ncs_user_delivery_delivery_tab.png)

**[!UICONTROL Display the mirror page for this message...]**&#x200B;連結可讓您在新視窗中檢視從清單選取之傳遞內容的映象頁面。

映象頁面僅適用於已定義HTML內容的傳送。 如需詳細資訊，請參閱[映象頁面的連結](mirror-page.md)。

![](assets/s_ncs_user_wizard_miror_page_link.png)

## 傳遞追蹤記錄和歷史記錄 {#tracking-logs}

**[!UICONTROL Tracking]**&#x200B;索引標籤會列出此傳遞的追蹤記錄。 此標籤會顯示已傳送訊息的追蹤資料，例如，所有受Adobe Campaign追蹤的URL。 追蹤資料會每小時更新。

>[!NOTE]
>
>如果未啟用傳遞追蹤，則不會顯示此索引標籤。

追蹤設定會在傳遞助理的適當階段執行。 請參閱[如何設定追蹤的連結](tracking.md)。

在傳遞報告中解譯&#x200B;**[!UICONTROL Tracking]**&#x200B;資料。 請參閱[本節](../reporting/delivery-reports.md)。

![](assets/s_ncs_user_delivery_tracking_tab.png)

## 收件匣轉譯 {#delivery-rendering}

**[!UICONTROL Inbox rendering]**&#x200B;索引標籤可讓您在可能接收訊息的不同內容中預覽訊息，並檢查主要案頭和應用程式中的相容性。

如此一來，您就可以確保以最佳方式在各種Web使用者端、網頁郵件與裝置上向收件者顯示您的訊息。

如需收件匣轉譯的詳細資訊，請參閱[此頁面](inbox-rendering.md)


## 傳遞稽核 {#delivery-audit-}

**[!UICONTROL Audit]**&#x200B;索引標籤包含傳遞記錄檔及與校樣相關的所有訊息。

**[!UICONTROL Refresh]**&#x200B;按鈕可讓您更新資料。 使用&#x200B;**[!UICONTROL Filters]**&#x200B;按鈕來定義資料的篩選器。

特殊圖示可讓您識別錯誤或警告。 請參閱[傳遞分析](delivery-analysis.md)。

**[!UICONTROL Proofs]**&#x200B;子索引標籤可讓您檢視已傳送的校樣清單。

![](assets/s_ncs_user_delivery_log_tab.png)

您可以修改此視窗中顯示的資訊（以及&#x200B;**[!UICONTROL Delivery]**&#x200B;和&#x200B;**[!UICONTROL Tracking]**&#x200B;索引標籤的資訊），方法是選取要顯示的欄。 若要這麼做，請按一下右下角的&#x200B;**[!UICONTROL Configure list]**&#x200B;圖示。 如需設定清單顯示的詳細資訊，請參閱[本節](../config/ui-settings.md#customize-lists)。

## 傳遞控制面板同步 {#delivery-dashboard-synchronization}

從您的傳送控制面板，檢查已處理的訊息和傳送記錄檔，確定傳送成功。

有些指標或狀態可能錯誤或不是最新的，此問題可能由下列解決方案解決：

* 如果您的傳遞狀態不正確，請檢查此傳遞的所有必要核准是否已完成，或&#x200B;**[!UICONTROL operationMgt]**&#x200B;和&#x200B;**[!UICONTROL deliveryMgt]**&#x200B;技術工作流程是否正在執行中且沒有錯誤。

* 如果您的傳遞計數器不符合您的傳遞，請在Adobe Campaign總管中的相關傳遞上按一下滑鼠右鍵，並選取&#x200B;**[!UICONTROL Actions]** > **[!UICONTROL Recompute delivery and tracking indicators]**&#x200B;以重新同步處理，藉此嘗試重新計算指標。 如需追蹤指標的詳細資訊，請參閱此[區段](../reporting/delivery-reports.md#tracking-indicators)。

您也可以透過傳送控制面板，使用不同的報告追蹤您的傳送內容。 如需詳細資訊，請參閱本[區段](../reporting/delivery-reports.md)。

>[!NOTE]
>
>身為Campaign v8受管理的Cloud Services使用者，基礎架構會由Adobe監控和管理。 如果您遇到傳送指標或控制面板同步化的持續問題，請聯絡Adobe客戶服務。

## 疑難排解緩慢的傳送 {#troubleshooting-slow-deliveries}

如果按一下&#x200B;**[!UICONTROL Send]**&#x200B;按鈕後，您的傳送似乎比平常需要更長的時間，請檢查下列可能的原因：

### IP位址信譽問題

有些電子郵件提供者可能會將您的IP位址新增至封鎖清單。 檢查&#x200B;**[!UICONTROL Delivery]**&#x200B;索引標籤中的傳遞記錄(broadlogs)，找出指出信譽問題的退信訊息。 請參閱[傳遞能力監視](monitoring-deliverability.md)區段，以取得信譽管理的指引。

### 傳遞規模和複雜性

您的傳送可能太大，無法快速處理。 這可能發生在以下情況中：

繁重的JavaScript個人化需要為每個收件者執行大量資料處理。

由於HTML內容龐大、內嵌影像或廣泛的個人化，重量超過60 KB的傳遞。

請參閱[傳遞最佳實務](../start/delivery-best-practices.md)，瞭解內容准則和個人化最佳實務。 為獲得最佳效能，建議的最大大小約為35KB。

### 系統效能

系統問題可能會讓伺服器無法有效處理傳遞。 如果您懷疑效能有問題，請檢查傳送記錄檔是否有逾時錯誤或通訊問題。

>[!NOTE]
>
>身為Campaign v8受管理的Cloud Services使用者，伺服器基礎架構監控由Adobe管理。 如果您在傳送傳遞時遇到持續的效能問題，請聯絡Adobe客戶服務，並提供您的傳送記錄檔。

