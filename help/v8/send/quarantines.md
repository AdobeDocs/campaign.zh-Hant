---
title: Campaign中的隔離管理
description: 瞭解Adobe Campaign中的隔離管理
feature: Profiles, Monitoring
role: User, Developer
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: c4d3a5d3cf89f2d342c661e54b5192d84ceb3a75
workflow-type: tm+mt
source-wordcount: '1317'
ht-degree: 5%

---

# 隔離 {#quarantine-management}

Adobe Campaign會管理線上頻道（電子郵件、簡訊、推播通知）的隔離地址清單。 如果無效地址的比率過高，某些網際網路存取提供者會自動將電子郵件視為垃圾郵件。 因此，隔離可讓您避免被這些提供者新增到封鎖清單中。 此外，隔離有助於減少簡訊傳送成本，因為將錯誤的電話號碼排除在遞送服務之外。

隔離收件者的地址或電話號碼時，會在傳遞分析期間將收件者從目標中排除：您將無法傳送行銷訊息（包括自動化工作流程電子郵件）給這些連絡人。 如果這些隔離地址也出現在清單中，那麼在傳送給這些清單時將排除這些地址。 舉例來說，信箱已滿、地址不存在或電子郵件伺服器無法使用時，可以隔離電子郵件地址。

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

## 隔離與封鎖清單

**隔離**&#x200B;只適用於&#x200B;**位址**、**電話號碼**&#x200B;或&#x200B;**裝置權杖**，不適用於設定檔本身。 例如，被隔離的電子郵件地址的設定檔可以更新其設定檔並輸入新地址，然後再次被傳送動作設為目標。 同樣地，如果兩個設定檔碰巧擁有相同的電話號碼，則兩個設定檔在隔離該號碼時都會受到影響。 隔離的地址或電話號碼會顯示在[排除記錄](#delivery-quarantines) （針對傳遞）或[隔離清單](#non-deliverable-bounces) （針對整個平台）中。

>[!NOTE]
>
>當收件者將您的訊息回報為垃圾訊息，或使用「STOP」等關鍵字回覆簡訊時，其地址或電話號碼將被隔離為&#x200B;**[!UICONTROL Denylisted]**。 他們的設定檔會據此更新。

另一方面，對於指定頻道，**設定檔**&#x200B;可以在取消訂閱（選擇退出）後位於&#x200B;**封鎖清單**&#x200B;上：這表示它們不再成為任何傳送的目標。 因此，如果電子郵件通道封鎖清單上的設定檔有兩個電子郵件地址，則兩個地址都會從傳送中排除。 您可以在設定檔的&#x200B;**[!UICONTROL No longer contact]**&#x200B;索引標籤的&#x200B;**[!UICONTROL General]**&#x200B;區段中，檢查設定檔是否位於一或多個頻道的封鎖清單中。 [了解更多](../audiences/view-profiles.md)

>[!NOTE]
>
>透過[&quot;mailto&quot; List-Unsubscribe方法](https://experienceleague.adobe.com/zh-hant/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations#mailto-list-unsubscribe){target="_blank"}取消訂閱的收件者不會傳送到隔離區。 他們或是從與傳遞相關聯的[服務](../start/subscriptions.md)取消訂閱，或是傳送到封鎖清單（顯示在設定檔的&#x200B;**[!UICONTROL No longer contact]**&#x200B;區段中） （如果未定義傳遞的服務）。

<!--For the mobile app channel, device tokens are quarantined.-->

## 電子郵件、電話或裝置為何要傳送到隔離區 {#quarantine-reason}

Adobe Campaign會根據傳送失敗的型別及其原因管理隔離。 這些會在錯誤訊息限定期間指派。 在此頁面[上進一步瞭解傳遞失敗管理](delivery-failures.md)。

可擷取兩種型別或錯誤：

* **硬錯誤**：會立即將電子郵件地址、電話號碼或裝置傳送到隔離區。
* **軟錯誤**：軟錯誤會增加錯誤計數器，並可能隔離電子郵件、電話號碼或裝置權杖。 Campaign執行[重試](delivery-failures.md#retries)：當錯誤計數器達到限制臨界值時，將會隔離地址、電話號碼或裝置Token。 [了解更多](delivery-failures.md#retries)。

在隔離地址清單中，**[!UICONTROL Error reason]**&#x200B;欄位會指出所選地址被置於隔離狀態的原因。 [了解更多](#non-deliverable-bounces)。


如果使用者將電子郵件歸類為垃圾訊息，該訊息會自動重新導向至Adobe管理的技術信箱。 之後，系統會自動將使用者的電子郵件地址傳送到狀態為　**[!UICONTROL Denylisted]**　的隔離區。此狀態僅適用於地址，而且設定檔不在封鎖清單中，因此使用者會繼續收到SMS訊息和推播通知。 進一步瞭解[傳遞最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=zh-Hant#feedback-loops){target="_blank"}中的意見回圈。

>[!NOTE]
>
>Adobe Campaign　中的隔離區會區分大小寫。請務必以小寫匯入電子郵件地址，如此一來，稍後就不會將它們重新設為目標。

## 軟性錯誤管理 {#soft-error-management}

與硬錯誤相反，軟錯誤不會立即傳送要隔離的地址，而是會增加錯誤計數器。 當錯誤計數器達到限制臨界值時，則會隔離該地址。 在[瞭解傳遞失敗](delivery-failures.md)中進一步瞭解重試和錯誤型別。

如果最後一次重大錯誤發生在10天以前，則會重新初始化錯誤計數器。 然後，地址狀態變更為&#x200B;**[!UICONTROL Valid]**，並由&#x200B;**[!UICONTROL Database cleanup]**&#x200B;工作流程從隔離清單中刪除該地址。 [進一步瞭解技術工作流程](../config/workflows.md#technical-workflows)。

## 存取隔離的地址 {#access-quarantined-addresses}

可以為特定傳送或整個平台顯示隔離的地址。

### 傳送的隔離{#delivery-quarantines}

隔離地址會列在傳送準備階段期間，並列在傳送控制面板的傳送記錄中。

對於每個傳遞，您也可以檢查&#x200B;**[!UICONTROL Delivery summary]**&#x200B;報告：它顯示傳遞目標中隔離的地址數量，並顯示：

* 傳遞分析期間被置於隔離的地址數量；
* 進行傳送動作後置於隔離區的地址數。

若要了解傳遞報告的詳細資訊，請參閱[本章節](../reporting/gs-reporting.md)。

### 無法傳遞和退回的地址{#non-deliverable-bounces}

若要檢視整個平台&#x200B;**的隔離地址清單**，Campaign管理員可以瀏覽至&#x200B;**[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**。 本節列出&#x200B;**電子郵件**、**簡訊**&#x200B;及&#x200B;**推播通知**&#x200B;管道的隔離元素。

![](assets/tech-quarantine.png)

>[!NOTE]
>
>隔離區數量會隨時間增加。 例如，如果電子郵件地址的存留期被視為三年，而收件者表格每年增加50%，則隔離區數量的增加計算如下：
>
>年度結束1：(1&#42;0.33)/(1+0.5)=22%。
>
>年度結束2：((1.22&#42;0.33)+0.33)/(1.5+0.75)=32.5%。

此外，此首頁的&#x200B;**[!UICONTROL Non-deliverables and bounces]**&#x200B;報告&#x200B;**區段提供的**&#x200B;內建報告會顯示隔離地址、遇到的錯誤型別，以及依網域劃分的失敗等相關資訊。 您可以篩選特定傳送的資料，或視需要自訂此報表。

在[傳遞能力最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html?lang=zh-Hant){target="_blank"}中進一步瞭解退信地址。

### 隔離的電子郵件地址 {#quarantined-recipient}

您可以查詢任何收件者之電子郵件地址的狀態。

若要這麼做，請選取收件者設定檔，然後按一下&#x200B;**[!UICONTROL Deliveries]**&#x200B;標籤。 對於傳送給該收件者的所有郵件，您可以檢視該地址是否失敗、在分析期間是否被隔離等。

對於每個資料夾，您都可以使用&#x200B;**[!UICONTROL Quarantined email address]**&#x200B;內建篩選條件，僅顯示其電子郵件地址處於隔離狀態的收件者，如下所示：

![](assets/quarantine-filter.png)


## 移除隔離的地址 {#remove-a-quarantined-address}

### 自動更新 {#unquarantine-auto}

符合特定條件的地址會由&#x200B;**[!UICONTROL Database cleanup]**&#x200B;內建工作流程自動從隔離清單中刪除。

在下列情況下，地址會自動從隔離清單中移除：

* 成功傳送後，會從隔離清單中移除&#x200B;**[!UICONTROL With errors]**&#x200B;狀態的地址。
* 如果最後一次軟退信發生於10天以前，則會從隔離清單中移除&#x200B;**[!UICONTROL With errors]**&#x200B;狀態的地址。 如需軟性錯誤管理的詳細資訊，請參閱[本節](#soft-error-management)。
* 狀態為&#x200B;**[!UICONTROL With errors]**&#x200B;且出現&#x200B;**[!UICONTROL Mailbox full]**&#x200B;錯誤退信的地址將在30天後從隔離清單中移除。

其狀態然後變更為&#x200B;**[!UICONTROL Valid]**。

>[!CAUTION]
>
>位址處於&#x200B;**[!UICONTROL Quarantine]**&#x200B;或&#x200B;**[!UICONTROL Denylisted]**&#x200B;狀態的收件者，即使收到電子郵件，也不會被移除。

### 手動更新 {#unquarantine-manual}

您也可以從隔離清單手動移除地址。 若要從隔離區手動移除地址，您可以將其狀態從&#x200B;**[!UICONTROL Valid]**&#x200B;節點變更為&#x200B;**[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**。

![](assets/tech-quarantine-status.png)

### 大量更新 {#unquarantine-bulk}

在特定情況下，您可能會需要對隔離清單執行大量更新，例如ISP中斷期間，由於電子郵件無法成功傳遞給收件者，導致電子郵件被錯誤標籤為跳出。

若要執行大量更新，請執行下列動作：

1. 建立工作流程並在隔離表格(**[!UICONTROL nms:address]**)上新增查詢，以篩選受影響的收件者
2. 使用查詢條件來識別應取消隔離的地址，例如：
   * **電子郵件網域(@domain)**&#x200B;等於受影響的ISP網域
   * 在中斷時間範圍內&#x200B;**更新狀態(@lastModified)**
   * **狀態(@status)**&#x200B;等於隔離狀態
3. 新增&#x200B;**[!UICONTROL Update data]**&#x200B;活動以將地址狀態設定為&#x200B;**[!UICONTROL Valid]**

接著，**[!UICONTROL Database cleanup]**&#x200B;工作流程會自動從隔離清單中移除這些地址，這些地址可包含在未來的傳送中。

## 相關主題

* [瞭解傳送失敗](delivery-failures.md) — 瞭解不同型別的傳送失敗以及Campaign如何處理退信
* [監視傳遞](delivery-dashboard.md) — 存取傳遞記錄檔並監視傳遞效能
* [傳遞最佳實務](../start/delivery-best-practices.md) — 維持良好傳遞能力並避免隔離的最佳實務

