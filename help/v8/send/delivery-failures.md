---
title: Campaign中的傳送失敗
description: 瞭解使用Adobe Campaign傳送訊息時可能發生的失敗
feature: Profiles, Monitoring
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: 9c83ebeb-e923-4d09-9d95-0e86e0b80dcc
source-git-commit: 57e177dc6c30502f2ed3bb08b18586fa5399e89c
workflow-type: tm+mt
source-wordcount: '3410'
ht-degree: 5%

---

# 瞭解傳遞失敗 {#delivery-failures}

跳出是ISP提供返回失敗通知的傳送嘗試和失敗的結果。 跳出處理是清單衛生的重要部分。 在指定的電子郵件連續多次跳出後，此程式會將其標示為需要抑制。

此程式會防止系統繼續傳送無效的電子郵件地址。 跳出是ISP用來判斷IP信譽的關鍵資料之一。 留意此量度非常重要。 「已傳遞」與「已跳出」可能是衡量行銷訊息傳遞方式最常見的方式：傳遞百分比越高越好。

如果無法將訊息發送到輪廓，遠端伺服器會自動向 Adobe Campaign 發送錯誤消息。此錯誤適用於判斷應隔離電子郵件地址、電話號碼或裝置。 請參閱[退回郵件管理](#bounce-mail-qualification)。

傳送訊息後，您可以在傳送記錄檔中檢視每個設定檔的傳送狀態，以及相關失敗的型別和原因。

隔離電子郵件地址時，或設定檔位於封鎖清單時，收件者會在傳送準備步驟中排除。 已排除的訊息會列在傳送控制面板中。

## 為什麼訊息傳遞失敗 {#delivery-failure-reasons}

訊息失敗時有兩種型別的錯誤。 每個傳送失敗型別都會判斷地址是否傳送至[隔離](quarantines.md#quarantine-reason)。

* **硬退信**
硬跳出是當ISP將寄送訂閱者位址的嘗試判斷為無法傳送後，產生的永久性失敗。 在Adobe Campaign中，分類為無法傳送的硬跳出會新增至隔離清單，這表示不會重新嘗試這些跳出。 在某些情況下，如果失敗的原因不明，則會忽略硬退信。

  以下是一些常見的硬跳出範例：地址不存在、帳戶已停用、語法錯誤、網域錯誤

* **軟退信**
軟跳出是ISP在難以傳遞郵件時產生的暫時性失敗。 軟性失敗將[重試](#retries)多次（如有差異，取決於使用自訂或現成可用的傳送設定），以嘗試成功傳送。 在嘗試重試次數上限之前（依設定而異），不會將持續軟跳出的位址新增至隔離。

  軟跳出的常見原因包括：信箱已滿、接收電子郵件伺服器關閉、寄件者信譽問題

**Ignored**&#x200B;錯誤型別已知為暫時，例如「不在辦公室」，或技術錯誤，例如，如果寄件者型別為「郵遞員」。

回饋回圈的運作方式與退回電子郵件類似：當使用者將電子郵件歸類為垃圾郵件時，您可以在Adobe Campaign中設定電子郵件規則，以封鎖傳送給該使用者的所有內容。 即使這些使用者未按一下取消訂閱連結，其位址仍會列入封鎖清單。 位址已新增至(**NmsAddress**)隔離資料表，而非以&#x200B;**狀態新增至(** NmsRecipient **[!UICONTROL Denylisted]**)收件者資料表。 在[Adobe傳遞能力最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=zh-Hant#feedback-loops){target="_blank"}中進一步瞭解回饋回圈機制。

## 同步與非同步錯誤 {#synchronous-and-asynchronous-errors}

訊息傳送可能會立即失敗，在此情況下，我們限定為同步錯誤。 如果訊息傳送失敗或稍後再傳送，則在傳送後錯誤為非同步。

這些型別的錯誤可管理如下：

* **同步錯誤**：由Adobe Campaign傳遞伺服器連絡的遠端伺服器會立即傳回錯誤訊息。 不允許將傳遞傳送至設定檔的伺服器。 郵件傳輸代理程式(MTA)會判斷退信型別並限定錯誤，然後將該資訊傳回至Campaign，以判斷是否應隔離相關電子郵件地址。 請參閱[退回電子郵件鑑定](#bounce-mail-qualification)。

* **非同步錯誤**：接收伺服器稍後會重新傳送退回郵件或SR。 此錯誤以與錯誤相關的標籤限定。 傳送後一週內，可能會發生非同步錯誤。

>[!NOTE]
>
>作為「受管理的Cloud Services」使用者，跳出信箱的設定是由Adobe執行。

## 退回郵件資格 {#bounce-mail-qualification}

<!--NO LONGER WITH MOMENTUM - Rules used by Campaign to qualify delivery failures are listed in the **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Delivery log qualification]** node. It is non-exhaustive, and is regularly updated by Adobe Campaign and can also be managed by the user.

![](assets/delivery-log-qualification.png)-->

在Adobe Campaign中處理退信限定的方式取決於錯誤型別：

* **同步錯誤**： MTA會決定退信型別和資格，並將該資訊傳回至Campaign。 **[!UICONTROL Delivery log qualification]**&#x200B;資料表中的退信限定不用於&#x200B;**同步**&#x200B;傳遞失敗錯誤訊息。

* **非同步錯誤**： Campaign用來限定非同步傳送失敗的規則列在&#x200B;**[!UICONTROL Administration > Campaign Management > Non deliverables Management > Delivery log qualification]**&#x200B;節點中。 inMail處理序會透過&#x200B;**[!UICONTROL Inbound email]**&#x200B;規則來限定非同步退信。

<!--NO LONGER WITH MOMENTUM - The message returned by the remote server on the first occurrence of this error type is displayed in the **[!UICONTROL First text]** column of the **[!UICONTROL Audit]** tab.

![](assets/delivery-log-first-txt.png)

Adobe Campaign filters this message to delete the variable content (such as IDs, dates, email addresses, phone numbers, etc.) and displays the filtered result in the **[!UICONTROL Text]** column. The variables are replaced with **`#xxx#`**, except addresses that are replaced with **`*`**.

This process allows to bring together all failures of the same type and avoid multiple entries for similar errors in the Delivery log qualification table.
  
>[!NOTE]
>
>The **[!UICONTROL Number of occurrences]** field displays the number of occurrences of the message in the list. It is limited to 100 000 occurrences. You can edit the field, if you want, for example, to reset it.

Bounce mails can have the following qualification status:

* **[!UICONTROL To qualify]**: the bounce mail could not be qualified. Qualification must be assigned to the Deliverability team to guarantee efficient platform deliverability. As long as it is not qualified, the bounce mail is not used to enrich the list of email management rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Refresh for deliverability** workflow to be compared to existing email management rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail is ignored, meaning that this bounce will never cause the recipient's address to be quarantined. It will not be used by the **Refresh for deliverability** workflow and it will not be sent to client instances.

![](assets/delivery-log-status.png)

>[!NOTE]
>
>In case of an outage of an ISP, emails sent through Campaign will be wrongly marked as bounces. To correct this, you need to update bounce qualification.-->


## 重試管理 {#retries}

如果訊息傳遞因暫時錯誤（**Soft**&#x200B;或&#x200B;**Ignored**）而失敗，Campaign會重試傳送。 可以執行這些重試，直到傳送持續時間結束。

軟退信重試次數和兩次之間的時間長度由MTA根據從訊息的電子郵件網域傳回的退信回應的型別和嚴重性決定。

>[!NOTE]
>
>Campaign不會使用傳遞屬性中的重試設定。

## 有效期限 {#valid-period}

Campaign傳遞中的有效期間設定限製為&#x200B;**3.5天或更少**。 對於傳送，如果您在Campaign中定義的值超過3.5天，則不會將其列入考量。

例如，如果有效期間在Campaign中設定為預設值5天，則軟退信訊息會進入MTA重試佇列，並從該訊息達到MTA時起最多只重試3.5天。 在此情況下，將不會使用Campaign中設定的值。

訊息在MTA佇列中停留3.5天且無法傳送後，訊息會逾時，其狀態會從傳送記錄檔中的&#x200B;**[!UICONTROL Sent]**&#x200B;更新為&#x200B;**[!UICONTROL Failed]**。

<!--For more on the validity period, see the [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html?lang=zh-Hant#defining-validity-period){target="_blank"}.-->


## 電子郵件錯誤型別 {#email-error-types}

針對電子郵件頻道，傳送失敗的可能原因列於下方。

+++ 按一下以檢視電子郵件錯誤型別的完整清單

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
   <td> 連結至該地址的帳戶已失效。 當網際網路存取提供者(IAP)偵測到長時間的不活動時，它可以關閉使用者的帳戶。 之後將無法傳遞至使用者的位址。 如果帳戶因為6個月的閒置而暫時停用，而且仍然可以啟動，則會指派狀態「發生錯誤」並再次嘗試帳戶，直到錯誤計數器達到5。 如果錯誤訊號表示帳戶已永久停用，則會直接將其設定為隔離。<br /> </td> 
  </tr> 
  <tr> 
   <td> 被隔離的地址 </td> 
   <td> 強烈 </td> 
   <td> 9 </td> 
   <td> 地址已放入隔離區。<br /> </td> 
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
   <td> 地址在允許清單上。 因此會忽略錯誤，並會傳送電子郵件。<br /> </td> 
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
   <td> 電子郵件地址的網域不正確或已不存在。 此輪廓將再次定位，直到錯誤計數達到5。之後，記錄將設定為隔離狀態，不會再重試。<br /> </td> 
  </tr> 
  <tr> 
   <td> 郵箱已滿 </td> 
   <td> 柔光 </td> 
   <td> 5 </td> 
   <td> 此使用者的信箱已滿，無法接受更多郵件。 此輪廓將再次定位，直到錯誤計數達到5。之後，記錄將設定為「隔離」狀態，不會再重試。<br />此型別的錯誤是由清理程式管理，地址在30天後會設定為有效狀態。<br />警告：若要從隔離位址清單自動移除位址，必須啟動資料庫清理技術工作流程。<br /> </td> 
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
   <td> 此位址正在限定中，因為錯誤尚未增加。 當伺服器傳送新錯誤訊息時，會發生此類錯誤：它可能是孤立的錯誤，但如果再次發生，錯誤計數器會增加，這會提醒技術團隊。 接著，他們可以透過樹狀結構中的<span class="uicontrol">管理</span> / <span class="uicontrol">行銷活動管理</span> / <span class="uicontrol">無法傳遞的專案管理</span>節點，執行訊息分析並限定此錯誤。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不符合產品建議條件 </td> 
   <td> 已忽略 </td> 
   <td> 16 </td> 
   <td> 收件者不符合傳遞中的優惠方案條件。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已拒絕 </td> 
   <td> 軟/硬 </td> 
   <td> 20 </td> 
   <td> 由於安全反饋為垃圾郵件報告，該地址已被置於隔離狀態。 根據錯誤，將再次嘗試此位址，直到錯誤計數器達到5，或直接傳送給隔離。<br /> </td> 
  </tr> 
  <tr> 
   <td> 目標大小受限 </td> 
   <td> 已忽略 </td> 
   <td> 17 </td> 
   <td> 已達到收件者的傳遞大小上限。<br /> </td> 
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
   <td> 訊息傳遞鏈結中發生錯誤。 可能是SMTP轉送上的事件、暫時無法連線的網域等。 根據錯誤，將再次嘗試該位址，直到錯誤計數器達到5，或直接將該位址傳送到隔離區。<br /> </td> 
  </tr> 
  <tr> 
   <td> 使用者不明 </td> 
   <td> 強烈 </td> 
   <td> 1 </td> 
   <td> 地址不存在。 此設定檔不會再嘗試傳送。<br /> </td> 
  </tr> 
 </tbody> 
</table>

+++

## 推播通知錯誤型別 {#push-error-types}

針對行動應用程式頻道，傳送失敗的可能原因列於下方。

### iOS隔離 {#ios-quarantine}

HTTP/V2通訊協定允許每個推播傳遞有直接的回饋和狀態。 如果使用HTTP/V2通訊協定聯結器，**[!UICONTROL mobileAppOptOutMgt]**&#x200B;工作流程將不再呼叫意見回饋服務。 解除安裝或重新安裝行動應用程式時，Token會視為已解除註冊。

同步時，如果APN針對訊息傳回「未註冊」狀態，則目標Token會立即置於隔離中。

+++ 按一下以檢視iOS隔離案例

<table> 
 <tbody> 
  <tr> 
   <td> <strong>案例</strong><br /> </td> 
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
   <td> 目標裝置已關閉<br /> </td> 
   <td> 確定<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 使用者停用應用程式<br />的通知 </td> 
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
   <td> 軟式<br /> </td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 訊息建立/分析階段 — 非預期的內容格式問題<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 根據錯誤<br />的各種錯誤訊息 </td> 
   <td> 軟式<br /> </td> 
   <td> 未定義<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 憑證問題（密碼、損毀等）和測試與APNs的連線問題<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 根據錯誤<br />的各種錯誤訊息 </td> 
   <td> 軟式<br /> </td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送期間網路連線中斷<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 連線錯誤<br /> </td> 
   <td> 未定義<br /> </td> 
   <td> 無法連線<br /> </td> 
   <td> 是<br /> </td> 
  </tr> 
  <tr> 
   <td> APN訊息拒絕：取消註冊<br />使用者已移除應用程式或權杖已過期<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 已取消登入<br /> </td> 
   <td> 硬式<br /> </td> 
   <td> 使用者不明<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> APNs訊息拒絕：所有其他錯誤<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 錯誤訊息<br />中出現錯誤拒絕原因 </td> 
   <td> 軟式<br /> </td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
 </tbody> 
</table>

+++

### Android隔離 {#android-quarantine}

適用於Android V1 **的**

對於每個通知，Adobe Campaign會直接從FCM伺服器接收同步錯誤。 Adobe Campaign會即時處理這些錯誤，並根據錯誤的嚴重性產生硬錯誤或軟錯誤，且可執行重試：

* 已超過承載長度、連線問題、服務可用性問題：已執行重試、軟錯誤、失敗原因為&#x200B;**[!UICONTROL Refused]**。
* 超過裝置配額：沒有重試、軟錯誤、失敗原因為&#x200B;**[!UICONTROL Refused]**。
* 無效的或未登入權杖、未預期的錯誤、寄件者帳戶問題：無重試、硬錯誤、失敗原因為&#x200B;**[!UICONTROL Refused]**。

**[!UICONTROL mobileAppOptOutMgt]**&#x200B;工作流程每6小時執行一次，以更新&#x200B;**AppSubscriptionRcp**&#x200B;資料表。 對於宣告為未登入或不再有效的權杖，**Disabled**&#x200B;欄位設為&#x200B;**True**，而且連結至該裝置權杖的訂閱將會自動從未來的傳遞中排除。

在傳遞分析期間，所有從目標排除的裝置都會自動新增至&#x200B;**excludeLogAppSubRcp**&#x200B;表格。

>[!NOTE]
>
>對於使用百度聯結器的客戶，以下是不同型別的錯誤：
>
>* 傳遞開始時的連線問題：失敗型別&#x200B;**[!UICONTROL Undefined]**，失敗原因&#x200B;**[!UICONTROL Unreachable]**，已執行重試。
>* 傳遞期間連線中斷：軟錯誤，失敗原因&#x200B;**[!UICONTROL Refused]**，已執行重試。
>* 百度在傳送期間傳回同步錯誤：硬錯誤，失敗原因&#x200B;**[!UICONTROL Refused]**，不執行重試。
>
>Adobe Campaign每10分鐘會連絡百度伺服器以擷取已傳送訊息的狀態，並更新broadlog。 如果訊息宣告為已傳送，broadlogs中訊息的狀態會設為&#x200B;**[!UICONTROL Received]**。 如果百度宣告錯誤，狀態會設為&#x200B;**[!UICONTROL Failed]**。

適用於Android V2 **的**

Android V2隔離機制使用與Android V1相同的流程，同樣適用於訂閱和排除更新。 如需詳細資訊，請參閱[Android V1](#android-quarantine)區段。

+++ 按一下以檢視Android V2隔離案例

<table> 
 <tbody> 
  <tr> 
   <td> <strong>案例</strong><br /> </td> 
   <td> <strong>狀態</strong><br /> </td> 
   <td> <strong>錯誤訊息</strong><br /> </td> 
   <td> <strong>失敗型別</strong><br /> </td> 
   <td> <strong>失敗原因</strong><br /> </td> 
   <td> <strong>重試</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 訊息建立/分析階段：在自訂欄位<br />中使用的關鍵字不合法 </td> 
   <td> 失敗<br /> </td> 
   <td> 無法使用下列關鍵字： {1}<br /> </td> 
   <td> 軟式<br /> </td> 
   <td> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 訊息建立/分析階段：承載太大<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 通知太重： {1}位元，而只有{2}是授權的<br /> </td> 
   <td> 軟式<br /> </td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送期間網路連線中斷<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 沒有來自位址{1}<br />上Firebase Cloud Messaging服務的回應 </td> 
   <td> 軟式<br /> </td> 
   <td> 無法連線<br /> </td> 
   <td> 是<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM訊息拒絕： FCM伺服器暫時無法使用（例如逾時）。<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> Firebase Cloud Messaging服務暫時無法使用<br /> </td> 
   <td> 軟式<br /> </td> 
   <td> 無法連線<br /> </td> 
   <td> 是<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM郵件拒絕：驗證寄件者帳戶<br />時發生錯誤 </td> 
   <td> 失敗<br /> </td> 
   <td> 無法識別開發人員帳戶，請檢查您的識別碼和密碼<br /> </td> 
   <td> 軟式<br /> </td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM訊息拒絕：超過裝置配額<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> </td> 
   <td> 軟式<br /> </td> 
   <td> 已拒絕<br /> </td> 
   <td> 是<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM訊息拒絕：註冊無效/未註冊<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> </td> 
   <td> 硬式<br /> </td> 
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
   <td> FCM訊息拒絕：寄件者識別碼不符<br /> </td> 
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
   <td> 驗證：要求中有未經授權的使用者端或範圍。<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> unauthorized_client </td> 
   <td> 已忽略</td>
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 驗證：使用者端未獲授權，無法使用此方法擷取存取權杖，或是使用者端未獲授權使用任何要求的範圍。<br /> </td> 
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
   <td> 驗證：無效的JWT簽章<br /> </td> 
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

+++

## SMS隔離 {#sms-quarantines}

**適用於標準聯結器**

簡訊通道的特定性列於下方。

>[!NOTE]
>
>**[!UICONTROL Delivery log qualification]**&#x200B;資料表不適用於&#x200B;**Extended generic SMPP**&#x200B;聯結器。

+++ 按一下以檢視標準聯結器的簡訊錯誤型別

<table> 
 <tbody> 
  <tr> 
   <td> <strong>案例</strong><br /> </td> 
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
   <td> 已在行動裝置<br />上收到 </td> 
   <td> 已接收<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 提供者傳回的錯誤<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 接收資料（SR或MO）時發生錯誤<br /> </td> 
   <td> 軟式<br /> </td> 
   <td> 無法連線<br /> </td> 
  </tr> 
  <tr> 
   <td> 無效的MT通知<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 處理傳送查詢<br />的認可框架時發生錯誤'{1}' </td> 
   <td> 軟式<br /> </td> 
   <td> 無法連線<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送MT<br />時發生錯誤 </td> 
   <td> 失敗<br /> </td> 
   <td> 傳送訊息時發生錯誤<br /> </td> 
   <td> 軟式<br /> </td> 
   <td> 無法連線<br /> </td> 
  </tr> 
 </tbody> 
</table>

+++

延伸通用SMPP聯結器的&#x200B;**&#x200B;**

使用SMPP通訊協定傳送SMS訊息時，錯誤管理的處理方式不同。

SMPP聯結器會擷取使用規則運算式（規則運算式）傳回之SR （狀態報告）訊息的資料，以篩選其內容。 然後，此資料會與&#x200B;**[!UICONTROL Delivery log qualification]**&#x200B;資料表中的資訊進行比對（可透過&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Campaign Management]** > **[!UICONTROL Non deliverables Management]**&#x200B;功能表取得）。

在限定新型別的錯誤之前，失敗原因預設一律設為&#x200B;**已拒絕**。

>[!NOTE]
>
>失敗型別和失敗原因與電子郵件相同。
>
>請要求您的提供者提供狀態和錯誤碼的清單，以便在傳遞記錄資格表中設定適當的失敗型別和失敗原因。

產生的訊息範例：

```
SR Generic DELIVRD 000|#MESSAGE#
```

* 所有錯誤訊息都以&#x200B;**SR**&#x200B;開頭，以區分SMS錯誤碼與電子郵件錯誤碼。
* 錯誤訊息的第二部分（**Generic**，在此範例中）參考SMSC實作的名稱，例如SMS外部帳戶的&#x200B;**[!UICONTROL SMSC implementation name]**&#x200B;欄位中定義的名稱。

  由於對於每個提供者，相同的錯誤碼可能有不同的含義，因此此欄位可讓您知道產生錯誤碼的提供者。 然後您可以在相關提供者的檔案中找到錯誤。

* 錯誤訊息的第三部分（此範例中為&#x200B;**DELIVRD**）對應於使用SMS外部帳戶中定義的狀態擷取規則運算式從SR擷取的狀態代碼。

  此規則運算式指定於外部帳戶的&#x200B;**[!UICONTROL SMSC specificities]**&#x200B;索引標籤中。
依預設，規則運算式會擷取&#x200B;**SMPP 3.4規格**&#x200B;的&#x200B;**附錄B**&#x200B;區段所定義的&#x200B;**stat：**&#x200B;欄位。

* 錯誤訊息的第四部分(**000**)對應於使用SMS外部帳戶中定義的錯誤碼擷取規則運算式從SR擷取的錯誤碼。

  此規則運算式指定於外部帳戶的&#x200B;**[!UICONTROL SMSC specificities]**&#x200B;索引標籤中。

  依預設，規則運算式會擷取&#x200B;**SMPP 3.4規格**&#x200B;的&#x200B;**附錄B**&#x200B;區段所定義的&#x200B;**err：**&#x200B;欄位。

* 直立線符號(|)後面的所有專案只會顯示在&#x200B;**[!UICONTROL First text]**&#x200B;表格的&#x200B;**[!UICONTROL Delivery log qualification]**&#x200B;欄中。 訊息標準化之後，此內容一律會由&#x200B;**#MESSAGE#**&#x200B;取代。 此程式會避免因類似錯誤而出現多個專案，與電子郵件的情況相同。

Extended generic SMPP聯結器會套用啟發式來尋找合理的預設值：如果狀態以&#x200B;**DELIV**&#x200B;開頭，則會被視為成功，因為它符合大多數提供者使用的一般狀態&#x200B;**DELIVRD**&#x200B;或&#x200B;**DELIVERED**。 任何其他狀態都會導致硬失敗。

## 疑難排解傳送失敗 {#troubleshooting}

本節提供診斷和解決常見傳遞失敗問題的指引。

### 具有個人化錯誤的失敗狀態 {#personalization-errors}

如果電子郵件傳遞的狀態為&#x200B;**[!UICONTROL Failed]**，則它可以連結至個人化區塊的問題。 當結構描述不符合傳遞對應時，傳遞中的個人化區塊可能會產生錯誤。

傳遞記錄是瞭解傳遞失敗原因的關鍵。 以下是您可能會遇到的常見錯誤：

收件者訊息失敗並出現「無法聯絡」錯誤，指出：

```
Error while compiling script 'content htmlContent' line X: `[table]` is not defined. JavaScript: error while evaluating script 'content htmlContent
```

**原因**： HTML中的個人化正在嘗試呼叫尚未定義或對應到上游目標定位或傳遞目標對應的資料表或欄位。

**解決方法**：檢閱工作流程和傳遞內容，以明確判斷哪些個人化嘗試呼叫相關資料表。 然後，在HTML中移除對此表格的呼叫，或修正傳遞的對應。

在[本節](personalize.md)中進一步瞭解個人化。

### 多個個人化值錯誤 {#multiple-values-error}

傳送失敗時，傳送記錄檔中可能會出現下列錯誤：

```
DLV-XXXX The count of message prepared (123) is greater than the number of messages to send (111). Please contact support.
```

**原因**：電子郵件中有收件者的多個值之個人化欄位或區塊。 個人化區塊正在使用中，且正在為特定收件者擷取多個記錄。

**解決方法**：檢查使用的個人化資料，然後檢查目標中是否有收件者有多個專案。 您也可以在傳遞活動之前，於目標工作流程中使用&#x200B;**[!UICONTROL Deduplication]**&#x200B;活動，以確保一次只有一個個人化欄位。 如需重複資料刪除的詳細資訊，請參閱[工作流程檔案](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/deduplication.html?lang=zh-Hant){target="_blank"}。

### 自動回覆處理 {#auto-reply-handling}

部分傳送可能會因為「無法聯絡」錯誤而失敗，並指出：

```
Inbound email bounce (rule 'Auto_replies' has matched this bounce).
```

**說明**：這表示傳送成功，但Adobe Campaign收到來自收件者的自動回覆（例如「不在辦公室」回覆），符合「Auto_replies」傳入電子郵件規則。

Adobe Campaign會忽略自動回覆電子郵件，收件者的地址不會傳送給隔離區。 這是預期行為，並不表示傳送失敗。

## 相關主題

[傳遞狀態](delivery-statuses.md)說明傳遞在其生命週期中可以具有的不同狀態。

[在Campaign UI中監視傳遞](delivery-dashboard.md)提供使用傳遞儀表板追蹤傳遞效能和診斷問題的指南。

[隔離管理](quarantines.md)說明Campaign如何管理隔離地址，以保護您的傳送信譽。

[監視您的傳遞能力](monitoring-deliverability.md)提供維持良好的傳遞能力和寄件者信譽的指引。

[傳遞最佳實務](../start/delivery-best-practices.md)涵蓋在Campaign中建立和傳送傳遞的最佳實務。
