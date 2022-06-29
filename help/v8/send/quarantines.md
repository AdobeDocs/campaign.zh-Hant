---
title: 市場活動中的隔離管理
description: 瞭解Adobe Campaign的檢疫管理
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 220b7a88-bd42-494b-b55b-b827b4971c9e
source-git-commit: 5c1ced7972295e79418ac7ff14a6f0888e5ed39a
workflow-type: tm+mt
source-wordcount: '1097'
ht-degree: 5%

---

# 隔離 {#quarantine-management}

Adobe Campaign管理線上渠道（電子郵件、簡訊、推送通知）的隔離地址清單。 如果無效地址的速率過高，一些網際網路訪問提供商會自動將電子郵件視為垃圾郵件。 因此，隔離允許您避免被這些提供程式添加到denylist中。 此外，隔離有助於減少簡訊傳送成本，因為將錯誤的電話號碼排除在遞送服務之外。

隔離其地址或電話號碼時，在傳遞分析期間將收件人從目標中排除：您將無法向這些聯繫人發送營銷消息，包括自動工作流電子郵件。 如果這些隔離地址也出現在清單中，則在發送到這些清單時將排除它們。 可以隔離電子郵件地址，例如，當郵箱已滿時，如果地址不存在，或者電子郵件伺服器不可用。

<!--For more on best practices to secure and optimize your deliveries, refer to [this page](delivery-best-practices.md).-->

**隔離** 僅適用於 **地址**&#x200B;的 **電話號碼**&#x200B;或 **設備令牌**，但不是檔案本身。 例如，其電子郵件地址被隔離的配置檔案可以更新其配置檔案並輸入新地址，然後可以再次通過傳遞操作鎖定。 同樣，如果兩個配置檔案的電話號碼相同，則如果隔離該號碼，則兩個配置檔案都會受到影響。 隔離的地址或電話號碼顯示在 [排除日誌](#delivery-quarantines) （交貨）或 [隔離清單](#non-deliverable-bounces) （適用於整個平台）。

另一方面，配置檔案可以位於 **密度** 在取消訂閱（選擇退出）後，對於給定頻道：這意味著它們不再成為任何目標。 因此，如果電子郵件渠道的denylist上的配置檔案有兩個電子郵件地址，則兩個地址都將被排除在傳遞之外。 您可以檢查配置檔案是否位於密鑰清單中，以查看 **[!UICONTROL No longer contact]** 的 **[!UICONTROL General]** 頁籤。 [了解更多](../audiences/view-profiles.md)

>[!NOTE]
>
>當收件人將您的郵件報告為垃圾郵件或用關鍵字（如「STOP」）回復SMS郵件時，其地址或電話號碼將被隔離為 **[!UICONTROL Denylisted]**。 相應地更新其簡介。

<!--For the email channel, email addresses are quarantined. For the mobile app channel, device tokens are quarantined. For the SMS channel, phone numbers are quarantined.?-->

## 為什麼電子郵件、電話或設備被發送到隔離區 {#quarantine-reason}

Adobe Campaign根據交貨失敗的類型及其原因管理檢疫。 在錯誤消息限定期間分配這些資訊。 瞭解有關交付失敗管理的更多資訊 [此頁](delivery-failures.md)。

可以捕獲兩種類型或錯誤：

* **硬錯誤**:電子郵件地址、電話號碼或設備會立即發送到隔離區。
* **軟錯誤**:軟錯誤會增加錯誤計數器，並可能會隔離電子郵件、電話號碼或設備令牌。 市場活動執行 [重試](delivery-failures.md#retries):當錯誤計數器達到限制閾值時，將隔離地址、電話號碼或設備令牌。 [了解更多資訊](delivery-failures.md#retries)。

在隔離地址清單中， **[!UICONTROL Error reason]** 欄位指明將選定地址置於隔離區的原因。 [了解更多資訊](#identifying-quarantined-addresses-for-the-entire-platform)。


如果用戶將電子郵件定義為垃圾郵件，則該郵件將自動重定向到由Adobe管理的技術郵箱。 之後，系統會自動將使用者的電子郵件地址傳送到狀態為　**[!UICONTROL Denylisted]**　的隔離區。此狀態僅指地址，配置檔案不在密碼清單中，因此用戶繼續接收SMS消息和推送通知。 瞭解有關中反饋循環的詳細資訊 [交付最佳做法指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops){target=&quot;_blank&quot;}。

>[!NOTE]
>
>Adobe Campaign　中的隔離區會區分大小寫。請務必以小寫匯入電子郵件地址，如此一來，稍後就不會將它們重新設為目標。

## 訪問隔離地址 {#access-quarantined-addresses}

可以為特定傳送或整個平台顯示隔離地址。

### 隔離交貨{#delivery-quarantines}

隔離地址在交貨準備階段列在交貨儀表板的交貨日誌中。

對於每個交貨，您還可以檢查 **[!UICONTROL Delivery summary]** 報告：它顯示交貨目標中隔離的地址數，並顯示：

* 在交貨分析期間存放在隔離區中的地址數，
* 在傳遞操作後置於隔離中的地址數。

### 無法交付和彈出地址{#non-deliverable-bounces}

查看隔離地址清單 **整個平台**，市場活動管理員可瀏覽至  **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]**。 此部分列出的隔離元素 **電子郵件**。 **簡訊** 和 **推送通知** 頻道。

![](assets/tech-quarantine.png)

>[!NOTE]
>
>隔離次數隨時間而增加。 例如，如果電子郵件地址的生存期被認為是三年，而收件人表每年增加50%，則隔離增加的計算方法如下：
>
>年末1:(1)&#42;0.33)/(1+0.5)=22%。
>
>年末2:(1.22)&#42;0.33)+0.33)/(1.5+0.75)=32.5%。

另外， **[!UICONTROL Non-deliverables and bounces]** 內置報告，可從 **報告** 此首頁的「」部分，按域顯示有關隔離中的地址、遇到的錯誤類型和故障細分的資訊。 您可以篩選特定傳遞的資料，或根據需要自定義此報告。

瞭解有關中的彈出地址的詳細資訊 [交付能力最佳實踐指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html){target=&quot;_blank&quot;}。

### 隔離的電子郵件地址 {#quarantined-recipient}

您可以查找任何收件人的電子郵件地址的狀態。

為此，請選擇收件人配置檔案，然後按一下 **[!UICONTROL Deliveries]** 頁籤。 對於向該收件人發送的所有郵件，您可以查明地址是否失敗、是否在分析期間被隔離等。

對於每個資料夾，您只能顯示電子郵件地址處於隔離狀態的收件人， **[!UICONTROL Quarantined email address]** 內置篩選器，如下所示：

![](assets/quarantine-filter.png)


## 刪除隔離地址 {#remove-a-quarantined-address}

與特定條件匹配的地址將由 **資料庫清理** 內置工作流。

在以下情況下，這些地址將自動從隔離清單中刪除：

* 中的地址 **[!UICONTROL With errors]** 成功交貨後，狀態將從隔離清單中刪除。
* 中的地址 **[!UICONTROL With errors]** 如果上次軟反彈發生時間超過10天，則狀態將從隔離清單中刪除。 有關軟錯誤管理的詳細資訊，請參見 [此部分](#soft-error-management)。
* 中的地址 **[!UICONTROL With errors]** 與 **[!UICONTROL Mailbox full]** 30天後將從隔離清單中刪除錯誤。

其狀態隨後更改為 **[!UICONTROL Valid]**。

>[!CAUTION]
>
>地址位於 **[!UICONTROL Quarantine]** 或 **[!UICONTROL Denylisted]** 即使收到電子郵件，狀態也永遠不會被刪除。

您也可以手動從隔離清單中刪除地址。 要從隔離中刪除地址，您可以：

* 將其狀態更改為 **[!UICONTROL Valid]** 從 **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Non deliverables and addresses]** 的下界。

   ![](assets/tech-quarantine-status.png)

* 將其狀態更改為 **[!UICONTROL Allowlisted]**:在這種情況下，地址仍保留在隔離清單中，但是即使遇到錯誤，它也會被系統性地定向。

>[!CAUTION]
>
>如果從隔離清單中刪除地址，則將再次開始發送到此地址。 這可能會對您的可交付性和IP信譽造成嚴重影響，最終可能導致您的IP地址或發送域被阻止。 考慮從隔離區中刪除任何地址時，請格外小心。 如果需要幫助，請與Adobe支援聯繫。
