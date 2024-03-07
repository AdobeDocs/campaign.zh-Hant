---
title: Campaign中的隔離管理
description: 瞭解Adobe Campaign中的隔離管理
feature: Profiles, Monitoring
role: User, Data Engineer
level: Beginner
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: e45799f0f3849d53d2c5f593bc02954b3a55fc28
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 4%

---

# 隔離 {#quarantine-management}

Adobe Campaign會管理線上頻道（電子郵件、簡訊、推播通知）的隔離地址清單。 如果無效地址的比率過高，某些網際網路存取提供者會自動將電子郵件視為垃圾郵件。 因此，隔離可讓您避免被這些提供者新增到封鎖清單中。 此外，隔離有助於減少簡訊傳送成本，因為將錯誤的電話號碼排除在遞送服務之外。

隔離收件者的地址或電話號碼時，會在傳遞分析期間將收件者從目標中排除：您將無法傳送行銷訊息（包括自動化工作流程電子郵件）給這些連絡人。 如果這些隔離地址也出現在清單中，那麼在傳送給這些清單時將排除這些地址。 舉例來說，信箱已滿、地址不存在或電子郵件伺服器無法使用時，可以隔離電子郵件地址。

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

**隔離** 僅適用於 **地址**， a **電話號碼**，或 **裝置Token**，但不適用於設定檔本身。 例如，被隔離的電子郵件地址的設定檔可以更新其設定檔並輸入新地址，然後再次被傳送動作設為目標。 同樣地，如果兩個設定檔碰巧擁有相同的電話號碼，則兩個設定檔在隔離該號碼時都會受到影響。 隔離的地址或電話號碼會顯示在 [排除記錄檔](#delivery-quarantines) （針對傳遞）或在 [隔離清單](#non-deliverable-bounces) （適用於整個平台）。

另一方面，設定檔可以位於 **封鎖清單** 和取消訂閱（選擇退出）後一樣，對於指定頻道：這表示他們不再被任何頻道設為目標。 因此，如果電子郵件通道封鎖清單上的設定檔有兩個電子郵件地址，則兩個地址都會從傳送中排除。 您可以檢查設定檔是否位於一或多個頻道的封鎖清單中 **[!UICONTROL No longer contact]** 設定檔的區段 **[!UICONTROL General]** 標籤。 [了解更多](../audiences/view-profiles.md)

>[!NOTE]
>
>當收件者將您的訊息回報為垃圾訊息，或使用「STOP」等關鍵字回覆簡訊訊息時，其地址或電話號碼將被隔離為 **[!UICONTROL Denylisted]**. 他們的設定檔會據此更新。

<!--For the email channel, email addresses are quarantined. For the mobile app channel, device tokens are quarantined. For the SMS channel, phone numbers are quarantined.?-->

## 電子郵件、電話或裝置為何要傳送到隔離區 {#quarantine-reason}

Adobe Campaign會根據傳送失敗的型別及其原因管理隔離。 這些會在錯誤訊息限定期間指派。 深入瞭解傳遞失敗管理 [在此頁面上](delivery-failures.md).

可擷取兩種型別或錯誤：

* **硬錯誤**：會立即將電子郵件地址、電話號碼或裝置傳送至隔離區。
* **軟錯誤**：軟錯誤會增加錯誤計數器，並可能隔離電子郵件、電話號碼或裝置Token。 行銷活動執行 [重試](delivery-failures.md#retries)：當錯誤計數器達到限制臨界值時，將會隔離地址、電話號碼或裝置Token。 [了解更多](delivery-failures.md#retries)。

在隔離地址清單中， **[!UICONTROL Error reason]** 欄位指出所選地址被置於隔離區的原因。 [了解更多](#identifying-quarantined-addresses-for-the-entire-platform)。


如果使用者將電子郵件歸類為垃圾訊息，則訊息會自動重新導向至由Adobe管理的技術信箱。 之後，系統會自動將使用者的電子郵件地址傳送到狀態為　**[!UICONTROL Denylisted]**　的隔離區。此狀態僅適用於地址，而且設定檔不在封鎖清單中，因此使用者會繼續收到SMS訊息和推播通知。 進一步瞭解中的意見回圈 [傳遞最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops){target="_blank"}.

>[!NOTE]
>
>Adobe Campaign　中的隔離區會區分大小寫。請務必以小寫匯入電子郵件地址，如此一來，稍後就不會將它們重新設為目標。

## 存取隔離的地址 {#access-quarantined-addresses}

可以為特定傳送或整個平台顯示隔離的地址。

### 傳送的隔離{#delivery-quarantines}

隔離地址會列在傳送準備階段期間，並列在傳送控制面板的傳送記錄中。

對於每次傳遞，您也可以檢查 **[!UICONTROL Delivery summary]** 報告：顯示傳送目標中隔離的地址數量，並顯示：

* 傳遞分析期間被置於隔離的地址數量；
* 進行傳送動作後置於隔離區的地址數。

### 無法傳遞和退回的地址{#non-deliverable-bounces}

若要檢視隔離地址清單 **適用於整個平台**，Campaign管理員可瀏覽至  **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**. 本節列出以下專案的隔離元素： **電子郵件**， **簡訊** 和 **推播通知** 管道。

![](assets/tech-quarantine.png)

>[!NOTE]
>
>隔離區數量會隨時間增加。 例如，如果電子郵件地址的存留期被視為三年，而收件者表格每年增加50%，則隔離區數量的增加計算如下：
>
>第1年年末： (1&#42;0.33)/(1+0.5)=22%。
>
年度結束2：((1.22)&#42;0.33)+0.33)/(1.5+0.75)=32.5%。

此外， **[!UICONTROL Non-deliverables and bounces]** 內建報告，可從 **報表** 首頁的區段，顯示隔離地址、遇到的錯誤型別以及依網域劃分的失敗等相關資訊。 您可以篩選特定傳送的資料，或視需要自訂此報表。

進一步瞭解 [傳遞性最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html){target="_blank"}.

### 隔離的電子郵件地址 {#quarantined-recipient}

您可以查詢任何收件者之電子郵件地址的狀態。

若要這麼做，請選取收件者設定檔，然後按一下 **[!UICONTROL Deliveries]** 標籤。 對於傳送給該收件者的所有郵件，您可以檢視該地址是否失敗、在分析期間是否被隔離等。

對於每個資料夾，您只能顯示其電子郵件地址處於隔離狀態的收件者，並使用 **[!UICONTROL Quarantined email address]** 內建篩選器，如下所示：

![](assets/quarantine-filter.png)


## 移除隔離的地址 {#remove-a-quarantined-address}

符合特定條件的地址會由自動從隔離清單中刪除 **資料庫清理** 內建工作流程。

在下列情況下，地址會自動從隔離清單中移除：

* 中的地址 **[!UICONTROL With errors]** 成功傳送後，狀態會從隔離清單中移除。
* 中的地址 **[!UICONTROL With errors]** 如果最後一次軟退信發生在10天以前，則會從隔離清單中移除狀態。 如需軟性錯誤管理的詳細資訊，請參閱 [本節](#soft-error-management).
* 中的地址 **[!UICONTROL With errors]** 已退回的狀態 **[!UICONTROL Mailbox full]** 錯誤將在30天後從隔離清單中移除。

其狀態然後變更為 **[!UICONTROL Valid]**.

>[!CAUTION]
>
地址在中的收件者 **[!UICONTROL Quarantine]** 或 **[!UICONTROL Denylisted]** 即使他們收到電子郵件，狀態也不會被移除。

您也可以從隔離清單手動移除地址。 若要從隔離中移除地址，您可以：

* 將其狀態變更為 **[!UICONTROL Valid]** 從 **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]** 節點。

  ![](assets/tech-quarantine-status.png)

您可能需要對隔離清單執行大量更新，例如在ISP中斷期間，由於電子郵件無法成功傳遞給收件者，導致電子郵件被錯誤標籤為退回時。

若要執行此動作，請建立工作流程，並在隔離表格上新增查詢，以篩選出所有受影響的收件者，以便從隔離清單中將其移除，並納入未來的Campaign電子郵件傳送。

以下是此查詢的建議准則：

* **錯誤文字（隔離文字）** 包含「Momen_Code10_InvalidRecipient」
* **電子郵件網域(@domain)** 等於domain1.com或 **電子郵件網域(@domain)** 等於domain2.com或 **電子郵件網域(@domain)** 等於domain3.com
* **更新狀態(@lastModified)** 在或晚於 `MM/DD/YYYY HH:MM:SS AM`
* **更新狀態(@lastModified)** 在或早於 `MM/DD/YYYY HH:MM:SS PM`

取得受影響的收件者清單後，請新增 **[!UICONTROL Update data]** 活動以將其狀態設為 **[!UICONTROL Valid]** 因此它們會由從隔離清單中移除 **[!UICONTROL Database cleanup]** 工作流程，. 您也可以從隔離表中刪除它們。

