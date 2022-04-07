---
title: 與運動和Adobe Analytics合作
description: 瞭解如何整合活動和分析
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 11370fb6-e192-4626-944e-b80a7496e50d
source-git-commit: 63b53fb6a7c6ecbfc981c93a723b6758b5736acf
workflow-type: tm+mt
source-wordcount: '1083'
ht-degree: 75%

---

# 與運動和Adobe Analytics合作

您可以配置Adobe Analytics以整合市場活動和分析。

這一整合使Adobe Campaign和Adobe Analytics通過 **Web Analytics連接器** 附件。 這一整合將Adobe Campaign向Adobe Analytics發送電子郵件活動的指標和屬性。

![](../assets/do-not-localize/speech.png)  作為托管Cloud Services用戶， [聯繫人Adobe](../start/campaign-faq.md#support) 將營銷活動與Adobe Experience Cloud的服務和解決方案聯繫起來。 必須通過專用軟體包在您的環境上安裝Web Analytics連接器載入項。

Adobe Campaign 使用 Adobe Analytics 連接器可測量網際網路對象 (Web Analytics)。 Web分析工具使Adobe Campaign能夠將指標和活動屬性轉發到分析。

每個工具的操作周界如下：

* **Adobe Analytics** 標誌著與Adobe Campaign一起發起的電子郵件活動

* **Adobe Campaign** 將指示符和市場活動屬性發送到連接器，然後連接器將它們轉發到Web分析工具


>[!CAUTION]
>
>Adobe Analytics 連接器與異動訊息 (訊息中心) 不相容。

要設定Campaign-Analytics連接，必須執行以下操作：

1. [在 Adobe Analytics 中建立報告套裝](#report-suite-analytics)
1. [設定轉換變數和成功事件](#configure-conversion-success)
1. [在 Adobe Campaign 中設定您的外部帳戶](#external-account-ac)

## 建立分析報告套件 {#report-suite-analytics}

建立 **[!UICONTROL Report suite]** 在 [!DNL Adobe Analytics]，請執行以下步驟：

1. 從 [!DNL Adobe Analytics] 中，選擇&#x200B;**[!UICONTROL Admin tab]**，然後按一下&#x200B;**[!UICONTROL All admin]**。

   ![](assets/analytics_connnector_1.png)

1. 按一下&#x200B;**[!UICONTROL Report suites]**。

   ![](assets/analytics_connnector_2.png)

1. 從&#x200B;**[!UICONTROL Report suite manager]**&#x200B;頁面，按一下&#x200B;**[!UICONTROL Create new]**，然後按一下&#x200B;**[!UICONTROL Report suite]**。

   有關建立&#x200B;**[!UICONTROL Report suite]**&#x200B;的詳細過程，請參閱本[節](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/new-report-suite/t-create-a-report-suite.html?lang=zh-Hant#prerequisites)。

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

   若要瞭解如何編輯&#x200B;**[!UICONTROL Conversion variables]**，請參閱本[節](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/t-conversion-variables-admin.html?lang=zh-Hant#admin-tools)。

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

   若要瞭解如何設定&#x200B;**[!UICONTROL Success events]**，請參閱本[節](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/t-success-events.html?lang=zh-Hant#admin-tools)

   ![](assets/analytics_connnector_8.png)

1. 完成時，按一下&#x200B;**[!UICONTROL Save]**。

配置報告套件後，您需要配置 **[!UICONTROL External accounts]** 在Adobe Campaign。

## 配置市場活動外部帳戶 {#external-account-ac}

您現在需要在 Adobe Campaign 中設定 **[!UICONTROL Web Analytics]** 外部帳戶，以啟用兩個解決方案之間的同步。

請注意，如果在設定外部帳戶時未顯示 **[!UICONTROL Report suite]**、**[!UICONTROL Conversion variables]** 或 **[!UICONTROL Success events]**&#x200B;之一，這表示您在與使用者相關聯的 **[!UICONTROL Product profile]** 中缺少此新建立元件的權限。

如需詳細資訊，請參閱 [Adobe Analytics 的產品設定檔](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=zh-Hant#product-profile-admins)頁面。

1. 前往 Adobe Campaign 樹的 **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL External accounts]** 資料夾，然後按一下 **[!UICONTROL New]**。

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

   ![](assets/analytics_connnector_11.png)

1. 從 **[!UICONTROL Events]** 類別中，對應 [!DNL Adobe Analytics] 中設定的 10 個&#x200B;**[!UICONTROL Success events]**。

1. 完成時，按一下 **[!UICONTROL Submit]**。Adobe Campaign 會在對應的 Analytics **[!UICONTROL Report Suite]**&#x200B;中建立 **[!UICONTROL Data source]**、**[!UICONTROL Calculated metrics]**、**[!UICONTROL Remarketing segments]** 和 **[!UICONTROL Classifications]**。

   在 [!DNL Adobe Analytics] 和 Adobe Campaign 之間同步完成後，您可以關閉視窗。

1. 您可以從 **[!UICONTROL Configure Analytics integration]** 視窗的 **[!UICONTROL Data Settings]** 標籤檢視設定。

   使用 **[!UICONTROL Sync]** 按鈕， [!DNL Adobe Campaign] 將同步在 [!DNL Adobe Analytics] 中完成的名稱變更。 如果在 [!DNL Adobe Analytics] 中刪除元件，則將在 [!DNL Adobe Campaign] 中刪除該元件，或顯示為 **未找到**&#x200B;訊息。

   ![](assets/analytics_connnector_12.png)

   >[!NOTE]
   >
   > 不能在此版本的市場活動v8中添加或刪除段。

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

   * **[!UICONTROL Lifespan]**：可讓您 (以天為單位) 指定延遲，之後技術工作流程便可在 Adobe Campaign 中復原 Web 事件。預設值：180天。
   * **[!UICONTROL Persistence]**：可讓您將所有 Web 事件 (例如購買) 歸因於再次行銷活動的期間，預設值：7天。

>[!NOTE]
>
>如果您使用數個對象測量工具，可在建立外部帳戶時，於&#x200B;**[!UICONTROL Partners]**&#x200B;下拉式清單中選取&#x200B;**[!UICONTROL Other]**。 您只能在傳送屬性中參考一個外部帳戶：因此，您需要借由新增 Adobe 預期的參數以及所有其他測量工具，調整追蹤 URL 的公式。

## Web分析進程的技術工作流 {#technical-workflows-of-web-analytics-processes}

Adobe Campaign和Adobe Analytics之間的資料交換由作為後台任務運行的技術工作流處理。

此工作流可從「市場活動瀏覽器」(Campaign Explorer)樹中的 **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]** > **[!UICONTROL Web analytics process]** 的子菜單。

![](assets/webanalytics_workflows.png)

的 **[!UICONTROL Sending of indicators and campaign attributes]** 工作流允許您使用Adobe Campaign連接器通過Adobe Analytics向Adobe Experience Cloud發送電子郵件活動指示符。 此工作流程每天凌晨 4:00 會觸發，且可能需要 24 小時才會將資料傳送至 Analytics。

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
* **[!UICONTROL Label]** (operation/@label): 僅在安裝了 **** Campaign 套件時
* **[!UICONTROL Nature]** (operation/@nature): 僅在安裝了 **** Campaign 套件時
* **[!UICONTROL Tag 1]** (webAnalytics/@tag1)
* **[!UICONTROL Tag 2]** (webAnalytics/@tag2)
* **[!UICONTROL Tag 3]** (webAnalytics/@tag3)
* **[!UICONTROL Contact date]** (scheduling/@contactDate)

## 跟蹤交貨 {#tracking-deliveries-in-adobe-campaign}

為了讓 Adobe Experience Cloud 在 Adobe Campaign 傳送後能夠追蹤網站上的活動，您必須在傳送屬性中參考相符的連接器。 若要這麼做，請套用下列步驟：

1. 開啟要追蹤之行銷活動的傳送。

   ![](assets/webanalytics_delivery_properties_003.png)

1. 開啟傳送屬性。
1. 前往&#x200B;**[!UICONTROL Web Analytics]**&#x200B;標籤，並選取先前建立的外部帳戶。 請參閱[在 Adobe Campaign 中設定外部帳戶](#external-account-ac)。

   ![](assets/webanalytics_delivery_properties_002.png)

1. 您現在可以傳送傳遞內容，並在 Adobe Analytics 中存取報告。


**相關主題**

* [市場活動 — Experience Cloud觸發器整合](ac-triggers.md)
