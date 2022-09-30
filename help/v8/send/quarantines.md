---
title: Campaign中的隔離管理
description: 了解Adobe Campaign中的隔離管理
feature: Profiles, Monitoring
role: User, Developer
level: Beginner, Intermediate
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '1097'
ht-degree: 5%

---

# 隔離 {#quarantine-management}

Adobe Campaign會管理線上通道的隔離地址清單（電子郵件、簡訊、推播通知）。 如果無效地址的比率太高，某些網際網路存取提供者會自動將電子郵件視為垃圾郵件。 因此，隔離可讓您避免被這些提供者新增至封鎖清單。 此外，隔離有助於減少簡訊傳送成本，因為將錯誤的電話號碼排除在遞送服務之外。

隔離其地址或電話號碼時，在傳送分析期間，收件者會從目標中排除：您將無法將行銷訊息（包括自動化工作流程電子郵件）傳送給這些聯絡人。 如果這些隔離地址也存在於清單中，則在傳送至這些清單時，這些地址將被排除。 例如，信箱容量已滿、地址不存在或電子郵件伺服器無法使用時，可以隔離電子郵件地址。

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

**隔離** 僅適用於 **地址**, **電話號碼**，或 **裝置代號**，但對設定檔本身則不會。 例如，被隔離的電子郵件地址的設定檔可以更新其設定檔並輸入新地址，然後再次被傳送動作定位。 同樣地，如果兩個設定檔的電話號碼恰好相同，則兩者在隔離號碼時都會受到影響。 隔離的地址或電話號碼顯示在 [排除記錄](#delivery-quarantines) （用於傳遞）或 [隔離清單](#non-deliverable-bounces) （適用於整個平台）。

另一方面，設定檔可以位於 **封鎖清單** 針對特定管道，在取消訂閱（選擇退出）後：這表示他們不再被任何目標鎖定。 因此，如果電子郵件通道封鎖清單上的設定檔有兩個電子郵件地址，則兩個地址都將從傳送中排除。 您可以檢查設定檔是否位於封鎖清單中，以取得 **[!UICONTROL No longer contact]** 設定檔的區段 **[!UICONTROL General]** 標籤。 [了解更多](../audiences/view-profiles.md)

>[!NOTE]
>
>當收件者回報您的訊息為垃圾訊息或回覆SMS訊息時，其地址或電話號碼會被隔離為 **[!UICONTROL Denylisted]**. 其設定檔會隨之更新。

<!--For the email channel, email addresses are quarantined. For the mobile app channel, device tokens are quarantined. For the SMS channel, phone numbers are quarantined.?-->

## 為什麼將電子郵件、電話或設備發送到隔離區 {#quarantine-reason}

Adobe Campaign會根據傳送失敗的類型及其原因來管理隔離區。 在錯誤訊息限定期間會指派這些訊息。 深入了解傳遞失敗管理 [本頁](delivery-failures.md).

可擷取兩種類型或錯誤：

* **硬錯誤**:會立即將電子郵件地址、電話號碼或裝置傳送至隔離區。
* **軟錯誤**:軟錯誤會增加錯誤計數器，且可能會隔離電子郵件、電話號碼或裝置代號。 行銷活動執行 [重試](delivery-failures.md#retries):當錯誤計數器達到限制臨界值時，會隔離地址、電話號碼或裝置代號。 [了解更多資訊](delivery-failures.md#retries)。

在隔離地址清單中， **[!UICONTROL Error reason]** 欄位指示所選地址被置於隔離區的原因。 [了解更多資訊](#identifying-quarantined-addresses-for-the-entire-platform)。


如果使用者將電子郵件歸類為垃圾訊息，則訊息會自動重新導向至由Adobe管理的技術信箱。 之後，系統會自動將使用者的電子郵件地址傳送到狀態為　**[!UICONTROL Denylisted]**　的隔離區。此狀態僅指位址，而設定檔不在封鎖清單上，因此使用者會繼續收到SMS訊息和推播通知。 進一步了解 [傳遞最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops){target=&quot;_blank&quot;}。

>[!NOTE]
>
>Adobe Campaign　中的隔離區會區分大小寫。請務必以小寫匯入電子郵件地址，如此一來，稍後就不會將它們重新設為目標。

## 訪問隔離地址 {#access-quarantined-addresses}

可針對特定傳送或整個平台顯示隔離的地址。

### 傳送的隔離{#delivery-quarantines}

隔離地址會在傳送準備階段期間列於傳送控制面板的傳送記錄中。

對於每個傳送，您也可以檢查 **[!UICONTROL Delivery summary]** 報告：它會顯示傳送目標中隔離區中的地址數，並顯示：

* 在傳送分析期間放在隔離區中的地址數，
* 傳送動作後置於隔離區中的地址數。

### 無法傳送和退信地址{#non-deliverable-bounces}

檢視隔離地址清單 **適用於整個平台**, Campaign管理員可瀏覽至  **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**. 此部分列出 **電子郵件**, **簡訊** 和 **推播通知** 管道。

![](assets/tech-quarantine.png)

>[!NOTE]
>
>隔離數量會隨時間增加。 例如，如果電子郵件地址的存留期被視為三年，而收件者表格每年增加50%，則隔離區數量的增加計算如下：
>
>年底1:(1)&#42;0.33)/(1+0.5)=22%。
>
>2年末：(1.22&#42;0.33)+0.33)/(1.5+0.75)=32.5%。

此外， **[!UICONTROL Non-deliverables and bounces]** 內建報表，可從 **報表** 區段中，顯示隔離中地址、遇到的錯誤類型以及按域劃分的故障資訊。 您可以篩選特定傳送的資料，或視需要自訂此報表。

進一步了解 [傳遞能力最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html){target=&quot;_blank&quot;}。

### 隔離的電子郵件地址 {#quarantined-recipient}

您可以查詢任何收件者之電子郵件地址的狀態。

若要這麼做，請選取收件者設定檔，然後按一下 **[!UICONTROL Deliveries]** 標籤。 對於傳送給該收件者的所有傳送，您可以找出地址是否失敗、在分析期間是否被隔離等。

對於每個資料夾，您只能顯示其電子郵件地址處於隔離狀態的收件者，其 **[!UICONTROL Quarantined email address]** 內建篩選器，如下所示：

![](assets/quarantine-filter.png)


## 移除隔離的地址 {#remove-a-quarantined-address}

符合特定條件的地址會由 **資料庫清理** 內建的工作流程。

在下列情況下，地址會自動從隔離清單中刪除：

* 中的地址 **[!UICONTROL With errors]** 成功傳送後，狀態將從隔離清單中移除。
* 中的地址 **[!UICONTROL With errors]** 如果上次軟退信發生在10天前，則狀態將從隔離清單中移除。 有關軟錯誤管理的詳細資訊，請參見 [本節](#soft-error-management).
* 中的地址 **[!UICONTROL With errors]** 與 **[!UICONTROL Mailbox full]** 30天後，錯誤將從隔離清單中移除。

其狀態接著會變更為 **[!UICONTROL Valid]**.

>[!CAUTION]
>
>地址位於 **[!UICONTROL Quarantine]** 或 **[!UICONTROL Denylisted]** 即使收到電子郵件，狀態也不會遭到移除。

您也可以手動從隔離清單中移除地址。 要從隔離中刪除地址，可以：

* 將其狀態變更為 **[!UICONTROL Valid]** 從 **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]** 節點。

   ![](assets/tech-quarantine-status.png)

* 將其狀態變更為 **[!UICONTROL Allowlisted]**:在此情況下，地址仍保留在隔離清單中，但將系統地定位該地址，即使遇到錯誤亦然。

>[!CAUTION]
>
>如果從隔離清單中刪除地址，則將重新開始向此地址發送。 這可能會對您的傳遞能力和IP信譽造成嚴重影響，最終可能導致您的IP位址或傳送網域遭到封鎖。 考慮從隔離區中移除任何地址時，請格外小心。 如果您需要協助，請聯絡Adobe支援。
