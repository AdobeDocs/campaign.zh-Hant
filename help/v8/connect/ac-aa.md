---
title: 合作使用Campaign與Adobe Analytics
description: 瞭解如何整合Campaign與Analytics
feature: Analytics Integration, Reporting
role: Admin, User
level: Beginner
exl-id: 11370fb6-e192-4626-944e-b80a7496e50d
source-git-commit: e465b846b3144a2138bb912b4baa09238f8c5b4c
workflow-type: tm+mt
source-wordcount: '1333'
ht-degree: 66%

---

# 合作使用Campaign與Adobe Analytics {#ac-aa}

您可以設定Adobe Analytics以整合Campaign和Analytics。

此整合可讓Adobe Campaign和Adobe Analytics透過&#x200B;**Web Analytics聯結器**&#x200B;附加元件互動。 此整合會將Adobe Campaign所傳送電子郵件行銷活動的指標和屬性傳送至Adobe Analytics。

>[!NOTE]
>
>作為「受管理的Cloud Services」使用者，[請聯絡Adobe](../start/campaign-faq.md#support)以將Campaign與Adobe Experience Cloud服務和解決方案連線。 必須透過專用套件將Web Analytics聯結器附加元件安裝在您的環境中。

Adobe Campaign 使用 Adobe Analytics 連接器可測量網際網路客群 (Web Analytics)。 網站分析工具可讓Adobe Campaign將指標和行銷活動屬性轉送至Analytics。

每個工具的動作周長如下：

* **Adobe Analytics**&#x200B;標籤使用Adobe Campaign啟動的電子郵件行銷活動

* **Adobe Campaign**&#x200B;將指標和行銷活動屬性傳送至聯結器，聯結器再將它們轉送至網頁分析工具


>[!CAUTION]
>
>Adobe Analytics 連接器與異動訊息 (訊息中心) 不相容。

若要設定Campaign-Analytics連線，您必須執行下列操作：

1. [在 Adobe Analytics 中建立報告套裝](#report-suite-analytics)
1. [設定轉換變數和成功事件](#configure-conversion-success)
1. [在Adobe Campaign中設定外部帳戶](#external-account-ac)

## 建立您的Analytics報表套裝 {#report-suite-analytics}

若要在[!DNL Adobe Analytics]中建立您的&#x200B;**[!UICONTROL Report suite]**，請遵循下列步驟：

1. 從 [!DNL Adobe Analytics] 中，選擇&#x200B;**[!UICONTROL Admin tab]**，然後按一下&#x200B;**[!UICONTROL All admin]**。

   ![](assets/analytics_connnector_1.png)

1. 按一下&#x200B;**[!UICONTROL Report suites]**。

   ![](assets/analytics_connnector_2.png)

1. 從&#x200B;**[!UICONTROL Report suite manager]**&#x200B;頁面，按一下&#x200B;**[!UICONTROL Create new]**，然後按一下&#x200B;**[!UICONTROL Report suite]**。

   如需建立&#x200B;**[!UICONTROL Report suite]**&#x200B;的詳細程式，請參閱[Adobe Analytics檔案](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/new-report-suite/t-create-a-report-suite.html#prerequisites){target="_blank"}。

   ![](assets/analytics_connnector_3.png)

1. 選取範本。

1. 使用下列資訊設定您的新報告套裝：

   * **[!UICONTROL Report Suite ID]**
   * **[!UICONTROL Site Title]**
   * **[!UICONTROL Time Zone]**
   * **[!UICONTROL Go Live Date]**
   * **[!UICONTROL Estimated Page Views Per Day]**

   ![](assets/analytics_connnector_4.png)

1. 設定後，按一下&#x200B;**[!UICONTROL Create report suite]**。

## 設定轉換變數和成功事件 {#configure-conversion-success}

建立&#x200B;**[!UICONTROL Report suite]**&#x200B;後，您需要依照以下方式設定&#x200B;**[!UICONTROL Conversion variables]**&#x200B;和&#x200B;**[!UICONTROL Success events]**:

1. 選取您先前設定的&#x200B;**[!UICONTROL Report suite]**。

1. 從&#x200B;**[!UICONTROL Edit settings]**&#x200B;按鈕中選取&#x200B;**[!UICONTROL Conversion]** >  **[!UICONTROL Conversion variables]**。

   ![](assets/analytics_connnector_5.png)

1. 按一下&#x200B;**[!UICONTROL Add new]**&#x200B;以建立測量電子郵件行銷活動影響所需的識別碼，即內部行銷活動名稱 (cid) 和 iNmsBroadlog (bid) 表格 ID。

   若要瞭解如何編輯&#x200B;**[!UICONTROL Conversion variables]**，請參閱此[Adobe Analytics檔案](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/t-conversion-variables-admin.html#admin-tools){target="_blank"}。

   ![](assets/analytics_connnector_6.png)

1. 完成時，按一下&#x200B;**[!UICONTROL Save]**。

1. 然後，要建立&#x200B;**[!UICONTROL Success events]**，請從&#x200B;**[!UICONTROL Edit settings]**&#x200B;按鈕中選擇&#x200B;**[!UICONTROL Conversion]** > **[!UICONTROL Success events]**。

   ![](assets/analytics_connnector_7.png)

1. 按一下&#x200B;**[!UICONTROL Add new]**&#x200B;以設定以下&#x200B;**[!UICONTROL Success events]**：

   * **[!UICONTROL Clicked]**
   * **[!UICONTROL Opened]**
   * **[!UICONTROL Person clicks]**
   * **[!UICONTROL Processed]**
   * **[!UICONTROL Scheduled]**
   * **[!UICONTROL Sent]**
   * **[!UICONTROL Total bounces]**
   * **[!UICONTROL Unique Clicks]**
   * **[!UICONTROL Unique Opens]**
   * **[!UICONTROL Unsubscribed]**

   若要瞭解如何設定&#x200B;**[!UICONTROL Success events]**，請參閱此[Adobe Analytics檔案](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/conversion-variables/success-event.html)

   ![](assets/analytics_connnector_8.png)

1. 完成時，按一下&#x200B;**[!UICONTROL Save]**。

設定報表套裝後，您需要在Adobe Campaign中設定&#x200B;**[!UICONTROL External accounts]**。

## 設定您的Campaign外部帳戶 {#external-account-ac}

您現在需要在 Adobe Campaign 中設定 **[!UICONTROL Web Analytics]** 外部帳戶，以啟用兩個解決方案之間的同步。

請注意，如果在設定外部帳戶時未顯示 **[!UICONTROL Report suite]**、**[!UICONTROL Conversion variables]** 或 **[!UICONTROL Success events]**&#x200B;之一，這表示您在與使用者相關聯的 **[!UICONTROL Product profile]** 中缺少此新建立元件的權限。

如需詳細資訊，請參閱 [Adobe Analytics 的產品設定檔](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html#product-profile-admins){target="_blank"}頁面。

1. 瀏覽至Adobe Campaign總管樹狀目錄的&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL External accounts]**&#x200B;資料夾，然後按一下&#x200B;**[!UICONTROL New]**。

   ![](assets/analytics_connnector_9.png)

1. 使用下拉式清單，從 **[!UICONTROL Integration]** 下拉式清單中選取 **[!UICONTROL Web Analytics]** 類型和 **[!UICONTROL Adobe Analytics]**。

   ![](assets/analytics_connnector_10.png)

1. 按一下 **[!UICONTROL Integration]** 下拉式清單旁的 **[!UICONTROL Configure]** 。

1. 從 **[!UICONTROL Configure Analytics integration]** 視窗，將外部帳戶與先前建立的報告套裝對應，並提供下列資訊：

   * **[!UICONTROL E-Mail]**
   * **[!UICONTROL IMS Org]**
   * **[!UICONTROL Analytics Company]**
   * **[!UICONTROL Report Suite]**


1. 從 **[!UICONTROL eVars]** 類別中，對應在 [!DNL Adobe Analytics] 中設定的兩個 **[!UICONTROL Conversion variables]**。

   >[!NOTE]
   >
   >促銷活動ID和Broadload ID欄位是透過登入頁面上的JavaScript或處理規則來收集。 [進一步瞭解處理規則](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/c-processing-rules/processing-rules)

   ![](assets/analytics_connnector_11.png)

1. 從 **[!UICONTROL Events]** 類別中，對應 [!DNL Adobe Analytics] 中設定的 10 個&#x200B;**[!UICONTROL Success events]**。

1. 完成時，按一下 **[!UICONTROL Submit]**。Adobe Campaign 會在對應的 Analytics **[!UICONTROL Report Suite]**&#x200B;中建立 **[!UICONTROL Data source]**、**[!UICONTROL Calculated metrics]**、**[!UICONTROL Remarketing segments]** 和 **[!UICONTROL Classifications]**。

   在 [!DNL Adobe Analytics] 和 Adobe Campaign 之間同步完成後，您可以關閉視窗。

1. 您可以從 **[!UICONTROL Configure Analytics integration]** 視窗的 **[!UICONTROL Data Settings]** 標籤檢視設定。

   使用 **[!UICONTROL Sync]** 按鈕， [!DNL Adobe Campaign] 將同步在 [!DNL Adobe Analytics] 中完成的名稱變更。 如果在 [!DNL Adobe Analytics] 中刪除元件，則將在 [!DNL Adobe Campaign] 中刪除該元件，或顯示為 **未找到**&#x200B;訊息。

   ![](assets/analytics_connnector_12.png)

   >[!NOTE]
   >
   > 您無法在此版本的Campaign v8中新增或移除區段。

1. 在 **[!UICONTROL External account]** 中，按一下 **[!UICONTROL Enrich the formula...]** 連結以變更 URL 計算公式，以指定網站分析工具整合資訊 (行銷活動 ID) 和必須追蹤其活動的網站網域。

   ![](assets/analytics_connnector_13.png)

1. 指定網站的網域名稱。

   ![](assets/analytics_connnector_14.png)

1. 按一下 **[!UICONTROL Next]** 並確保已儲存域名。

   ![](assets/analytics_connnector_15.png)

1. 如有必要，您可以多載計算公式。 要執行此操作，請核取方塊並直接在視窗中編輯公式。

   >[!IMPORTANT]
   >
   >此設定模式為專家使用者保留：此公式中的任何錯誤都可能導致電子郵件傳送停止。

1. **[!UICONTROL Advanced]**&#x200B;標籤可讓您設定或修改更多技術設定。

   * **[!UICONTROL Lifespan]**：可讓您指定延遲（以天為單位），之後技術工作流程便可在Adobe Campaign中復原Web事件。 預設值：180天。
   * **[!UICONTROL Persistence]**：可讓您將所有 Web 事件 (例如購買) 歸因於再次行銷活動的期間，預設值：7天。

>[!NOTE]
>
>如果您使用數個客群測量工具，可在建立外部帳戶時，於&#x200B;**[!UICONTROL Partners]**&#x200B;下拉式清單中選取&#x200B;**[!UICONTROL Other]**。 您只能在傳送屬性中參考一個外部帳戶：因此，您需要借由新增 Adobe 預期的參數以及所有其他測量工具，調整追蹤 URL 的公式。

## 網站分析流程的技術工作流程 {#technical-workflows-of-web-analytics-processes}

Adobe Campaign與Adobe Analytics之間的資料交換由技術工作流程處理，可作為背景工作執行。

此工作流程可從Campaign Explorer樹狀結構中的&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]** > **[!UICONTROL Web analytics process]**&#x200B;資料夾下使用。

![](assets/webanalytics_workflows.png)

**[!UICONTROL Sending of indicators and campaign attributes]**&#x200B;工作流程可讓您使用Adobe Analytics Connector，透過Adobe Campaign將電子郵件行銷活動指標傳送至Adobe Experience Cloud。 此工作流程每天凌晨 4:00 會觸發，且可能需要 24 小時才會將資料傳送至 Analytics。

請注意，不應重新啟動此工作流程，否則會重新傳送所有可能扭曲 Analytics 結果的先前資料。

相關指標包括：

* **[!UICONTROL Messages to deliver]** (@toDeliver)
* **[!UICONTROL Processed]** (@processed)
* **[!UICONTROL Success]** (@success)
* **[!UICONTROL Total count of opens]** (@totalRecipientOpen)
* **[!UICONTROL Recipients who have opened]** (@recipientOpen)
* **[!UICONTROL Total number of recipients who clicked]** (@totalRecipientClick)
* **[!UICONTROL People who clicked]** (@personClick)
* **[!UICONTROL Number of distinct clicks]** (@recipientClick)
* **[!UICONTROL Opt-Out]** (@optOut)
* **[!UICONTROL Errors]** (@error)

>[!NOTE]
>
>傳送的資料是根據上次快照的差值，可能導致量度資料中的負值。

傳送的屬性如下：

* **[!UICONTROL Internal name]** (@internalName)
* **[!UICONTROL Label]** (@label)
* **[!UICONTROL Label]** (operation/@label): 僅在安裝了 **&#x200B;**&#x200B;Campaign 套件時
* **[!UICONTROL Nature]** (operation/@nature): 僅在安裝了 **&#x200B;**&#x200B;Campaign 套件時
* **[!UICONTROL Tag 1]** (webAnalytics/@tag1)
* **[!UICONTROL Tag 2]** (webAnalytics/@tag2)
* **[!UICONTROL Tag 3]** (webAnalytics/@tag3)
* **[!UICONTROL Contact date]** (scheduling/@contactDate)

## 追蹤傳遞 {#tracking-deliveries-in-adobe-campaign}

為了讓 Adobe Experience Cloud 在 Adobe Campaign 傳送後能夠追蹤網站上的活動，您必須在傳送屬性中參考相符的連接器。 若要這麼做，請套用下列步驟：

1. 開啟要追蹤之行銷活動的傳送。

   ![](assets/webanalytics_delivery_properties_003.png)

1. 開啟傳送屬性。
1. 前往&#x200B;**[!UICONTROL Web Analytics]**&#x200B;標籤，並選取先前建立的外部帳戶。 請參閱[在Adobe Campaign中設定外部帳戶](#external-account-ac)。

   ![](assets/webanalytics_delivery_properties_002.png)

1. 您現在可以傳送傳遞內容，並在 Adobe Analytics 中存取報告。


## 建立再次行銷活動 {#create-a-re-marketing-campaign}

若要準備再次行銷活動，只需建立要用於再次行銷類型行銷活動的傳送範本。 然後設定再次行銷活動，並將其連結至區段。 每個區段必須有不同的再次行銷活動。

當 Adobe Campaign 完成分析初始行銷活動鎖定目標之人員的行為的區段後，就會自動開始再次行銷活動。 如果放棄購買或檢視產品而未進行購買，則會傳送傳遞內容給相關收件者，以供其網站瀏覽完成購買。

Adobe Campaign 提供個人化傳送範本，供您自行使用或建立資料庫，以準備行銷活動。

1. 從&#x200B;**[!UICONTROL Explorer]**，前往 Adobe Campaign 樹的&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**&#x200B;資料夾。
1. 複製 Adobe Campaign 提供的&#x200B;**[!UICONTROL Email delivery (re-marketing)]**&#x200B;範本或再次行銷範本範例。
1. 個人化範本以符合您的需求並加以儲存。
1. 建立新行銷活動，並從下拉式清單中選取&#x200B;**[!UICONTROL Re-marketing campaign]**&#x200B;範本。
1. 按一下&#x200B;**[!UICONTROL Configure...]**&#x200B;連結，以指定連結至行銷活動的區段和傳送範本。
1. 選取Analytics e[外部帳戶](#external-account-ac)及相關區段。
1. 選取要用於此再次行銷活動的傳送範本，然後按一下&#x200B;**[!UICONTROL Finish]**&#x200B;以關閉視窗。
1. 按一下&#x200B;**[!UICONTROL OK]**&#x200B;以關閉行銷活動視窗。

**[!UICONTROL Re-marketing efficiency]**&#x200B;報告可透過全域報告頁面存取。它可讓您檢視與 Adobe Campaign 再次行銷活動後購物車放棄次數相關的轉換聯絡人數 (亦即已購買商品)。 轉換率是每週、每月或自Adobe Campaign與Adobe Analytics開始同步後計算。

**相關主題**

* [Campaign - Experience Cloud Triggers整合](ac-triggers.md)
