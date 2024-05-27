---
title: Campaign中的傳送失敗
description: 瞭解使用Adobe Campaign傳送訊息時可能發生的失敗
feature: Profiles, Monitoring
role: User
level: Beginner, Intermediate
exl-id: 9c83ebeb-e923-4d09-9d95-0e86e0b80dcc
source-git-commit: 7f6c394f56d517c0a675e0fd2341bb6ef98044f0
workflow-type: tm+mt
source-wordcount: '2990'
ht-degree: 5%

---

# 瞭解傳遞失敗 {#delivery-failures}

跳出是ISP提供返回失敗通知的傳送嘗試和失敗的結果。 跳出處理是清單衛生的重要部分。 在指定的電子郵件連續多次跳出後，此程式會將其標示為需要抑制。

此程式會防止系統繼續傳送無效的電子郵件地址。 跳出是ISP用來判斷IP信譽的關鍵資料之一。 留意此量度非常重要。 「已傳遞」與「已跳出」可能是衡量行銷訊息傳遞方式最常見的方式：傳遞百分比越高越好。

如果無法將訊息發送到設定檔，遠端伺服器會自動向Adobe Campaign 發送錯誤消息。此錯誤適用於判斷應隔離電子郵件地址、電話號碼或裝置。 另請參閱 [退回郵件管理](#bounce-mail-qualification).

傳送訊息後，您可以在傳送記錄檔中檢視每個設定檔的傳送狀態，以及相關失敗的型別和原因。

隔離電子郵件地址時，或設定檔位於封鎖清單時，收件者會在傳送準備步驟中排除。 已排除的訊息會列在傳送控制面板中。

## 為什麼訊息傳遞失敗 {#delivery-failure-reasons}

訊息失敗時有兩種型別的錯誤。 每個傳送失敗型別都會判斷地址是否傳送至 [隔離](quarantines.md#quarantine-reason) 也可能不會。

* **硬跳出**
硬跳出是當ISP將寄送訂閱者位址的嘗試判斷為無法傳送後，產生的永久性失敗。 在Adobe Campaign中，分類為無法傳送的硬跳出會新增至隔離清單，這表示不會重新嘗試這些跳出。 在某些情況下，如果失敗的原因不明，則會忽略硬退信。

  以下是一些常見的硬跳出範例：地址不存在、帳戶已停用、語法錯誤、網域錯誤

* **軟退信**
軟跳出是ISP在難以傳遞郵件時產生的暫時性失敗。 軟性失敗會 [重試](#retries) 多次（如有差異，取決於使用自訂或現成可用的傳送設定），以嘗試成功傳送。 在嘗試重試次數上限之前（依設定而異），不會將持續軟跳出的位址新增至隔離。

  軟跳出的常見原因包括：信箱已滿、接收電子郵件伺服器關閉、寄件者信譽問題

此  **已忽略** 已知的錯誤型別是暫時性的，例如「不在辦公室」，或技術錯誤，例如，如果傳送者型別是&quot;postmaster&quot;。

回饋回圈的運作方式與退回電子郵件類似：當使用者將電子郵件歸類為垃圾郵件時，您可以在Adobe Campaign中設定電子郵件規則，以封鎖傳送給該使用者的所有內容。 即使這些使用者未按一下取消訂閱連結，其位址仍會列入封鎖清單。 位址會新增至(**NmsAddress**)隔離表格而非(**NmsRecipient**)收件者表格，包含 **[!UICONTROL Denylisted]** 狀態。 進一步瞭解中的意見回圈機制 [Adobe傳遞性最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops){target="_blank"}.

## 同步與非同步錯誤 {#synchronous-and-asynchronous-errors}

訊息傳送可能會立即失敗，在此情況下，我們限定為同步錯誤。 如果訊息傳送失敗或稍後再傳送，則在傳送後錯誤為非同步。

這些型別的錯誤可管理如下：

* **同步錯誤**：Adobe Campaign傳送伺服器連絡的遠端伺服器會立即傳回錯誤訊息。 不允許將傳遞傳送至設定檔的伺服器。 郵件傳輸代理程式(MTA)會判斷退信型別並限定錯誤，然後將該資訊傳回至Campaign，以判斷是否應隔離相關電子郵件地址。 請參閱[退信資格](#bounce-mail-qualification)。

* **非同步錯誤**：接收伺服器稍後會重新傳送退回郵件或SR。 此錯誤以與錯誤相關的標籤限定。 傳送後一週內，可能會發生非同步錯誤。

>[!NOTE]
>
>作為「受管理的Cloud Service」使用者，Adobe會執行退回信箱的設定。

## 退回郵件資格 {#bounce-mail-qualification}

<!--NO LONGER WITH MOMENTUM - Rules used by Campaign to qualify delivery failures are listed in the **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Delivery log qualification]** node. It is non-exhaustive, and is regularly updated by Adobe Campaign and can also be managed by the user.

![](assets/delivery-log-qualification.png)-->

在Adobe Campaign中處理退信限定的方式取決於錯誤型別：

* **同步錯誤**：MTA會判斷跳出型別和資格，並將該資訊傳回至Campaign。 中的退信資格 **[!UICONTROL Delivery log qualification]** 表格不用於 **同步** 傳遞失敗錯誤訊息。

* **非同步錯誤**：Campaign用來限定非同步傳送失敗的規則列於 **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Delivery log qualification]** 節點。 inMail程式會透過 **[!UICONTROL Inbound email]** 規則。 有關詳細資訊，請參閱 [Adobe Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target="_blank"}.

<!--NO LONGER WITH MOMENTUM - The message returned by the remote server on the first occurrence of this error type is displayed in the **[!UICONTROL First text]** column of the **[!UICONTROL Audit]** tab.

![](assets/delivery-log-first-txt.png)

Adobe Campaign filters this message to delete the variable content (such as IDs, dates, email addresses, phone numbers, etc.) and displays the filtered result in the **[!UICONTROL Text]** column. The variables are replaced with **`#xxx#`**, except addresses that are replaced with **`*`**.

This process allows to bring together all failures of the same type and avoid multiple entries for similar errors in the Delivery log qualification table.
  
>[!NOTE]
>
>The **[!UICONTROL Number of occurrences]** field displays the number of occurrences of the message in the list. It is limited to 100 000 occurrences. You can edit the field, if you want, for example, to reset it.

Bounce mails can have the following qualification status:

* **[!UICONTROL To qualify]** : the bounce mail could not be qualified. Qualification must be assigned to the Deliverability team to guarantee efficient platform deliverability. As long as it is not qualified, the bounce mail is not used to enrich the list of email management rules.
* **[!UICONTROL Keep]** : the bounce mail was qualified and will be used by the **Refresh for deliverability** workflow to be compared to existing email management rules and enrich the list.
* **[!UICONTROL Ignore]** : the bounce mail is ignored, meaning that this bounce will never cause the recipient's address to be quarantined. It will not be used by the **Refresh for deliverability** workflow and it will not be sent to client instances.

![](assets/delivery-log-status.png)

>[!NOTE]
>
>In case of an outage of an ISP, emails sent through Campaign will be wrongly marked as bounces. To correct this, you need to update bounce qualification.-->


## 重試管理 {#retries}

如果訊息傳送因暫時錯誤而失敗(**柔光** 或 **已忽略**)，Campaign會重試傳送。 可以執行這些重試，直到傳送持續時間結束。

軟退信重試次數和兩次之間的時間長度由MTA根據從訊息的電子郵件網域傳回的退信回應的型別和嚴重性決定。

>[!NOTE]
>
>Campaign不會使用傳遞屬性中的重試設定。

## 有效期限 {#valid-period}

Campaign傳送中的有效期間設定限製為 **3.5天或以下**. 對於傳送，如果您在Campaign中定義的值超過3.5天，則不會將其列入考量。

例如，如果有效期間在Campaign中設定為預設值5天，則軟退信訊息會進入MTA重試佇列，並從該訊息達到MTA時起最多只重試3.5天。 在此情況下，將不會使用Campaign中設定的值。

當訊息在MTA佇列中停留3.5天且無法傳送時，訊息會逾時，其狀態會從更新 **[!UICONTROL Sent]** 至 **[!UICONTROL Failed]** 傳送記錄檔中。

如需有效期的詳細資訊，請參閱 [Adobe Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target="_blank"}.


## 電子郵件錯誤型別 {#email-error-types}

針對電子郵件頻道，傳送失敗的可能原因列於下方。

<table> 
 <tbody> 
  <tr> 
   <td> 錯誤標籤 </td> 
   <td> 錯誤型別 </td> 
   <td> 技術價值 </td> 
   <td> 說明 </td> 
  </tr> 
  <tr> 
   <td> 帳戶已停用 </td> 
   <td> 軟/硬 </td> 
   <td> 4 </td> 
   <td> 連結至該地址的帳戶已失效。 當網際網路存取提供者(IAP)偵測到長時間的不活動時，它可以關閉使用者的帳戶。 之後將無法傳遞至使用者的位址。 如果帳戶因為6個月的閒置而暫時停用，而且仍然可以啟動，則會指派狀態「發生錯誤」並再次嘗試帳戶，直到錯誤計數器達到5。 如果錯誤訊號指出帳戶已永久停用，則會直接將其設定為隔離。<br /> </td> 
  </tr> 
  <tr> 
   <td> 被隔離的地址 </td> 
   <td> 強烈 </td> 
   <td> 9 </td> 
   <td> 地址被放入隔離區。<br /> </td> 
  </tr> 
  <tr> 
   <td> 未指定地址 </td> 
   <td> 強烈 </td> 
   <td> 7 </td> 
   <td> 未提供收件者的地址。<br /> </td> 
  </tr> 
  <tr> 
   <td> 品質不良的地址 </td> 
   <td> 已忽略 </td> 
   <td> 14 </td> 
   <td> 此地址的品質評等太低。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已加入封鎖清單的地址 </td> 
   <td> 強烈 </td> 
   <td> 8 </td> 
   <td> 地址已在傳送時新增到封鎖清單中。 此狀態用於將外部清單和外部系統的資料匯入Adobe Campaign隔離清單。<br /> </td> 
  </tr> 
  <tr> 
   <td> 控制地址 </td> 
   <td> 已忽略 </td> 
   <td> 127 </td> 
   <td> 收件者的地址是控制組的一部分。<br /> </td> 
  </tr> 
  <tr> 
   <td> 雙精度 </td> 
   <td> 已忽略 </td> 
   <td> 10 </td> 
   <td> 收件者的地址已在此傳遞中。<br /> </td> 
  </tr> 
  <tr> 
   <td> 忽略的錯誤 </td> 
   <td> 已忽略 </td> 
   <td> 25 </td> 
   <td> 地址在允許清單上。 因此，錯誤會被忽略，並會傳送電子郵件。<br /> </td> 
  </tr> 
  <tr> 
   <td> 仲裁後排除 </td> 
   <td> 已忽略 </td> 
   <td> 12 </td> 
   <td> 收件者已由「仲裁」型別的行銷活動型別規則排除。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已由 SQL 規則排除 </td> 
   <td> 已忽略 </td> 
   <td> 11 </td> 
   <td> 收件者已由「SQL」型別行銷活動型別規則排除。<br /> </td> 
  </tr> 
  <tr> 
   <td> 無效的網域 </td> 
   <td> 柔光 </td> 
   <td> 2 </td> 
   <td> 電子郵件地址的網域不正確或已不存在。 此設定檔將再次定位，直到錯誤計數達到5。之後，記錄將設定為隔離狀態，不會再重試。<br /> </td> 
  </tr> 
  <tr> 
   <td> 郵箱已滿 </td> 
   <td> 柔光 </td> 
   <td> 5 </td> 
   <td> 此使用者的信箱已滿，無法接受更多郵件。 此設定檔將再次定位，直到錯誤計數達到5。之後，記錄將設定為「隔離」狀態，不會再重試。<br /> 此類錯誤是由清理程式管理，地址會在30天後設為有效狀態。<br /> 警告：若要從隔離位址清單自動移除位址，必須啟動資料庫清理技術工作流程。<br /> </td> 
  </tr> 
  <tr> 
   <td> 未連線 </td> 
   <td> 已忽略 </td> 
   <td> 6 </td> 
   <td> 傳送訊息時，收件者的行動電話已關閉或未連線至網路。<br /> </td> 
  </tr> 
  <tr> 
   <td> 未定義 </td> 
   <td> 未定義 </td> 
   <td> 0 </td> 
   <td> 此位址正在限定中，因為錯誤尚未增加。 當伺服器傳送新錯誤訊息時，會發生此類錯誤：它可能是孤立的錯誤，但如果再次發生，錯誤計數器會增加，這會提醒技術團隊。 然後他們可以透過進行訊息分析，並確認此錯誤 <span class="uicontrol">管理</span> / <span class="uicontrol">Campaign Management</span> / <span class="uicontrol">無法傳遞的專案管理</span> 樹狀結構中的節點。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不符合優惠方案條件 </td> 
   <td> 已忽略 </td> 
   <td> 16 </td> 
   <td> 收件者不符合傳遞中的優惠方案條件。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已拒絕 </td> 
   <td> 軟/硬 </td> 
   <td> 20 </td> 
   <td> 由於安全反饋為垃圾郵件報告，該地址已被置於隔離狀態。 根據錯誤，將再次嘗試該位址，直到錯誤計數器達到5，或直接將其傳送給隔離。<br /> </td> 
  </tr> 
  <tr> 
   <td> 目標大小受限 </td> 
   <td> 已忽略 </td> 
   <td> 17 </td> 
   <td> 已達收件者的傳遞大小上限。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不合格的地址 </td> 
   <td> 已忽略 </td> 
   <td> 15 </td> 
   <td> 郵寄地址不合格。<br /> </td> 
  </tr> 
  <tr> 
   <td> 無法聯繫 </td> 
   <td> 軟/硬 </td> 
   <td> 3 </td> 
   <td> 訊息傳遞鏈結中發生錯誤。 可能是SMTP轉送上的事件、暫時無法連線的網域等。 根據錯誤，將再次嘗試該位址，直到錯誤計數器達到5，或直接將其傳送給隔離。<br /> </td> 
  </tr> 
  <tr> 
   <td> 使用者不明 </td> 
   <td> 強烈 </td> 
   <td> 1 </td> 
   <td> 地址不存在。 此設定檔不會再嘗試傳送。<br /> </td> 
  </tr> 
 </tbody> 
</table>



## 推播通知錯誤型別 {#push-error-types}

針對行動應用程式頻道，傳送失敗的可能原因列於下方。

### iOS隔離 {#ios-quarantine}

HTTP/V2通訊協定允許每個推播傳遞有直接的回饋和狀態。 如果使用HTTP/V2通訊協定聯結器，則不再由呼叫回饋服務。 **[!UICONTROL mobileAppOptOutMgt]** 工作流程。 解除安裝或重新安裝行動應用程式時，Token會視為已解除註冊。

同步時，如果APN針對訊息傳回「未註冊」狀態，則目標Token會立即置於隔離中。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>情境</strong><br /> </td> 
   <td> <strong>狀態</strong><br /> </td> 
   <td> <strong>錯誤訊息</strong><br /> </td> 
   <td> <strong>失敗型別</strong><br /> </td> 
   <td> <strong>失敗原因</strong><br /> </td> 
   <td> <strong>重試</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 目標裝置已開啟<br /> </td> 
   <td> 確定<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 目標裝置電源已關閉<br /> </td> 
   <td> 確定<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 使用者停用應用程式的通知<br /> </td> 
   <td> 確定<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 訊息建立/分析階段 — 承載太大<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 承載太長<br /> </td> 
   <td> 柔光<br /> </td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 訊息建立/分析階段 — 非預期的內容格式問題<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 根據錯誤的各種錯誤訊息<br /> </td> 
   <td> 柔光<br /> </td> 
   <td> 未定義<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 憑證問題（密碼、損毀等） 並測試與APNs問題的連線<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 根據錯誤的各種錯誤訊息<br /> </td> 
   <td> 柔光<br /> </td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送期間網路連線中斷<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 連線錯誤<br /> </td> 
   <td> 未定義<br /> </td> 
   <td> 無法聯絡<br /> </td> 
   <td> 是<br /> </td> 
  </tr> 
  <tr> 
   <td> APNs訊息拒絕：取消註冊<br /> 使用者已移除應用程式或權杖已過期<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 已取消註冊<br /> </td> 
   <td> 強烈<br /> </td> 
   <td> 使用者不明<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> APNs訊息拒絕：所有其他錯誤<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 錯誤訊息中會出現錯誤拒絕原因<br /> </td> 
   <td> 柔光<br /> </td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Android隔離 {#android-quarantine}

**適用於Android V1**

對於每個通知，Adobe Campaign會直接從FCM伺服器接收同步錯誤。 Adobe Campaign會即時處理這些錯誤，並根據錯誤的嚴重性產生硬錯誤或軟錯誤，且可執行重試：

* 已超過承載長度，連線問題，服務可用性問題：已執行重試，軟錯誤，失敗原因為 **[!UICONTROL Refused]**.
* 超過裝置配額：沒有重試、軟錯誤、失敗原因為 **[!UICONTROL Refused]**.
* 無效或未登入的權杖、未預期的錯誤、寄件者帳戶問題：無重試、硬錯誤、失敗原因為 **[!UICONTROL Refused]**.

此 **[!UICONTROL mobileAppOptOutMgt]** 工作流程每6小時執行一次，以更新 **AppSubscriptionRcp** 表格。 對於已宣告未註冊或不再有效的權杖，欄位 **已停用** 設為 **真** 而連結至該裝置Token的訂閱會自動從未來的傳送中排除。

在傳遞分析期間，所有從目標中排除的裝置都會自動新增至 **excludeLogAppSubRcp** 表格。

>[!NOTE]
>
>對於使用百度聯結器的客戶，以下是不同型別的錯誤：
>
>* 傳送開始時的連線問題：失敗型別 **[!UICONTROL Undefined]**，失敗原因 **[!UICONTROL Unreachable]**，會執行重試。
>* 傳遞期間連線中斷：軟錯誤、失敗原因 **[!UICONTROL Refused]**，會執行重試。
>* 百度在傳送期間傳回同步錯誤：硬錯誤、失敗原因 **[!UICONTROL Refused]**，不會執行重試。
>
>Adobe Campaign每10分鐘會連絡百度伺服器以擷取已傳送訊息的狀態，並更新broadlog。 如果訊息宣告為已傳送，則broadlogs中訊息的狀態會設為 **[!UICONTROL Received]**. 如果百度宣告錯誤，則狀態會設為 **[!UICONTROL Failed]**.

**適用於Android V2**

Android V2隔離機制使用與Android V1相同的程式，同樣適用於訂閱和排除專案更新。 如需詳細資訊，請參閱 [Android V1](#android-quarantine) 區段。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>情境</strong><br /> </td> 
   <td> <strong>狀態</strong><br /> </td> 
   <td> <strong>錯誤訊息</strong><br /> </td> 
   <td> <strong>失敗型別</strong><br /> </td> 
   <td> <strong>失敗原因</strong><br /> </td> 
   <td> <strong>重試</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 訊息建立/分析階段：自訂欄位中使用的關鍵字不合法<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 無法使用下列關鍵字： {1}<br /> </td> 
   <td> 柔光<br /> </td> 
   <td> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 訊息建立/分析階段：承載太大<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 通知太重： {1}位元，而只有{2}位元獲得授權<br /> </td> 
   <td> 柔光<br /> </td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送期間網路連線中斷<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 沒有來自Firebase Cloud Messaging服務對以下位址的回應： {1}<br /> </td> 
   <td> 柔光<br /> </td> 
   <td> 無法聯絡<br /> </td> 
   <td> 是<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM訊息拒絕： FCM伺服器暫時無法使用（例如逾時）。 <br /> </td> 
   <td> 失敗<br /> </td> 
   <td> Firebase雲端傳訊服務暫時無法使用<br /> </td> 
   <td> 柔光<br /> </td> 
   <td> 無法聯絡<br /> </td> 
   <td> 是<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM訊息拒絕：驗證寄件者帳戶時發生錯誤<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 無法識別開發人員帳戶，請檢查您的ID和密碼<br /> </td> 
   <td> 柔光<br /> </td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM訊息拒絕：超過裝置配額<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> </td> 
   <td> 柔光<br /> </td> 
   <td> 已拒絕<br /> </td> 
   <td> 是<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM訊息拒絕：註冊無效/未註冊<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> </td> 
   <td> 強烈<br /> </td> 
   <td> 使用者不明<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM訊息拒絕：所有其他錯誤<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> Firebase Cloud Messaging伺服器傳回未預期的錯誤碼： {1} </td> 
   <td> </td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
    <tr> 
   <td> FCM訊息拒絕：無效的引數<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> INVALID_ARGUMENT </td> 
   <td> 已忽略</td> 
   <td> 未定義<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> FCM訊息拒絕：協力廠商驗證錯誤<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> THIRD_PARTY_AUTH_ERROR </td> 
   <td> 已忽略</td>
   <td> 已拒絕<br /> </td> 
   <td> 是<br /> </td> 
  </tr>
    <tr> 
   <td> FCM訊息拒絕：寄件者識別碼不相符<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> SENDER_ID_MISMATCH </td> 
   <td> 柔光</td>
   <td> 使用者不明<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> FCM訊息拒絕：已取消註冊<br /> </td> 
   <td> 失敗<br /> </td>
   <td> 未註冊 </td> 
   <td> 強烈</td> 
   <td> 使用者不明<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> FCM訊息拒絕：內部<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 內部 </td> 
   <td> 已忽略</td> 
   <td> 已拒絕<br /> </td> 
   <td> 是<br /> </td> 
  </tr>
    <tr> 
   <td> FCM訊息拒絕：無法使用<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 無法使用</td> 
   <td> 已忽略</td> 
   <td> 已拒絕<br /> </td> 
   <td> 是<br /> </td> 
  </tr>
    <tr> 
   <td> FCM訊息拒絕：未預期的錯誤碼<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 未預期的錯誤碼</td> 
   <td> 已忽略</td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
  <tr> 
   <td> 驗證：連線問題<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 無法連線到驗證伺服器 </td> 
   <td> 已忽略</td>
   <td> 已拒絕<br /> </td> 
   <td> 是<br /> </td> 
  </tr>
    <tr> 
   <td> 驗證：要求中未獲授權的使用者端或範圍。<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> unauthorized_client </td> 
   <td> 已忽略</td>
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 驗證：使用者端未獲授權使用此方法擷取存取權杖，或未獲授權使用任何請求範圍的使用者端。<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> unauthorized_client </td> 
   <td> 已忽略</td>
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 驗證：存取遭拒<br /> </td> 
   <td> 失敗<br /> </td>
   <td> access_denied</td> 
   <td> 已忽略</td>
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 驗證：無效的電子郵件<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> invalid_grant </td> 
   <td> 已忽略</td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 驗證：無效的JWT<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> invalid_grant </td> 
   <td> 已忽略</td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 驗證：無效的JWT簽名<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> invalid_grant </td> 
   <td> 已忽略</td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 驗證：提供的OAuth範圍或ID權杖對象無效<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> unauthorized_client</td> 
   <td> 已忽略</td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 驗證： OAuth使用者端已停用<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> disabled_client</td> 
   <td> 已忽略</td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
 </tbody> 
</table>

## SMS隔離 {#sms-quarantines}

**適用於標準聯結器**

簡訊通道的特定性列於下方。

>[!NOTE]
>
>此 **[!UICONTROL Delivery log qualification]** 表格不適用於 **擴充通用SMPP** 聯結器。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>情境</strong><br /> </td> 
   <td> <strong>狀態</strong><br /> </td> 
   <td> <strong>錯誤訊息</strong><br /> </td> 
   <td> <strong>失敗型別</strong><br /> </td> 
   <td> <strong>失敗原因</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 已傳送給提供者<br /> </td> 
   <td> 已傳送<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 已在行動裝置上接收<br /> </td> 
   <td> 已接收<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 提供者傳回的錯誤<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 接收資料時發生錯誤（SR或MO）<br /> </td> 
   <td> 柔光<br /> </td> 
   <td> 無法聯絡<br /> </td> 
  </tr> 
  <tr> 
   <td> 無效的MT通知<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 處理傳送查詢的認可框架時發生錯誤'{1}'<br /> </td> 
   <td> 柔光<br /> </td> 
   <td> 無法聯絡<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送MT時發生錯誤<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 傳送訊息時發生錯誤<br /> </td> 
   <td> 柔光<br /> </td> 
   <td> 無法聯絡<br /> </td> 
  </tr> 
 </tbody> 
</table>

**用於擴充通用SMPP聯結器**

使用SMPP通訊協定傳送SMS訊息時，錯誤管理的處理方式不同。

SMPP聯結器會擷取使用規則運算式（規則運算式）傳回之SR （狀態報告）訊息的資料，以篩選其內容。 然後，此資料會與中的資訊進行比對 **[!UICONTROL Delivery log qualification]** 表格(可透過 **[!UICONTROL Administration]** > **[!UICONTROL Campaign Management]** > **[!UICONTROL Non deliverables Management]** 功能表)。

在限定新型別的錯誤之前，失敗原因一律設為 **已拒絕** 依預設。

>[!NOTE]
>
>失敗型別和失敗原因與電子郵件相同。
>
>請要求您的提供者提供狀態和錯誤碼的清單，以便在傳遞記錄資格表中設定適當的失敗型別和失敗原因。

產生的訊息範例：

```
SR Generic DELIVRD 000|#MESSAGE#
```

* 所有錯誤訊息的開頭為 **SR** 以區分SMS錯誤碼與電子郵件錯誤碼。
* 第二部分(**通用** 在此範例中，錯誤訊息會參照SMSC實作的名稱，例如 **[!UICONTROL SMSC implementation name]** 簡訊外部帳戶的欄位。

  由於對於每個提供者，相同的錯誤碼可能有不同的含義，因此此欄位可讓您知道產生錯誤碼的提供者。 然後您可以在相關提供者的檔案中找到錯誤。

* 第三部分(**傳遞** 在此範例中)的錯誤訊息會與使用SMS外部帳戶中定義的狀態擷取規則運算式從SR擷取到的狀態代碼相對應。

  此規則運算式指定於 **[!UICONTROL SMSC specificities]** 外部帳戶的索引標籤。
依預設，規則運算式會提取 **stat：** 由定義的欄位 **附錄B** 的區段 **SMPP 3.4規格**.

* 第四部分(**000** 在此範例中)的錯誤訊息會對應到使用SMS外部帳戶中定義的錯誤代碼擷取規則運算式從SR擷取的錯誤代碼。

  此規則運算式指定於 **[!UICONTROL SMSC specificities]** 外部帳戶的索引標籤。

  依預設，規則運算式會提取 **錯誤：** 由定義的欄位 **附錄B** 的區段 **SMPP 3.4規格**.

* 管路符號(|)後面的所有專案只會顯示在 **[!UICONTROL First text]** 的欄 **[!UICONTROL Delivery log qualification]** 表格。 此內容一律會取代為 **#MESSAGE#** 在訊息標準化之後。 此程式會避免因類似錯誤而出現多個專案，與電子郵件的情況相同。

Extended generic SMPP聯結器會套用啟發式來尋找合理的預設值：如果狀態開頭為 **傳遞**，則視為成功，因為它符合常見狀態 **傳遞** 或 **已傳遞** 供大部分提供者使用。 任何其他狀態都會導致硬失敗。
