---
title: Campaign中的傳送失敗
description: 了解使用Adobe Campaign傳送訊息時可能發生的故障
feature: Profiles, Monitoring
role: User
level: Beginner, Intermediate
exl-id: 9c83ebeb-e923-4d09-9d95-0e86e0b80dcc
source-git-commit: 46be0379610a6a4a3491d49ce096c64270ed8016
workflow-type: tm+mt
source-wordcount: '3005'
ht-degree: 12%

---

# 瞭解傳遞失敗 {#delivery-failures}

退信是傳送嘗試和失敗的結果，ISP會提供回傳失敗通知。 退信處理是清單衛生的關鍵部分。 指定的電子郵件已連續反彈數次後，此程式會將其標示為隱藏。

此程式會防止系統繼續傳送無效的電子郵件地址。 退信是ISP用來判斷IP信譽的關鍵資料之一。 請務必留意此量度。 「已傳送」或「已退信」可能是衡量行銷訊息傳送最常見的方式：交付百分比越高，就越好。

如果訊息無法傳送至設定檔，遠端伺服器會自動傳送錯誤訊息至Adobe Campaign。 此錯誤符合條件，可判斷是否應隔離電子郵件地址、電話號碼或裝置。 請參閱 [退回郵件管理](#bounce-mail-qualification).

傳送訊息後，您可以在傳送記錄檔中檢視每個設定檔的傳送狀態，以及相關的失敗類型和原因。

隔離電子郵件地址或封鎖清單上的設定檔時，收件者會在傳送準備步驟中排除。 已排除的訊息會列在傳送控制面板中。

## 訊息傳送為何失敗 {#delivery-failure-reasons}

訊息失敗時有兩種錯誤。 每個傳送失敗類型都決定地址是否傳送至 [隔離](quarantines.md#quarantine-reason) 或否。

* **硬跳出數**
硬退信是在ISP判定寄送嘗試寄送訂閱者地址為無法傳送後，所產生的永久失敗。 在Adobe Campaign中，分類為無法傳送的硬退信會新增至隔離清單，表示不會重新嘗試退信。 在某些情況下，如果失敗的原因未知，則會忽略硬跳出。

   以下是一些常見的硬跳出範例：地址不存在、帳戶已禁用、語法錯誤、域錯誤

* **軟跳出數**
軟跳出是ISP在無法傳送郵件時產生的暫時故障。 軟故障將 [重試](#retries) 嘗試成功傳送多次（差異取決於使用自訂或現成可用的傳送設定）。 在嘗試最大重試次數（根據設定而再次有所不同）之前，不會將持續軟退信的地址添加到隔離區。

   軟退信的一些常見原因包括：郵箱已滿，正在接收電子郵件伺服器關閉，發件人信譽問題

此  **已忽略** 錯誤類型已知為暫時錯誤，例如「不在辦公室」或技術錯誤，例如，如果傳送者類型為「postmaster」。

反饋回圈的運作方式就像退信電子郵件：當使用者將電子郵件歸類為垃圾訊息時，您可以在Adobe Campaign中設定電子郵件規則，以封鎖傳送給此使用者的所有內容。 即使未點按取消訂閱連結，這些使用者的地址仍會遭封鎖。 地址會新增至&#x200B;**NmsAddress**)隔離表，而不是(**NmsRecipient**)收件者表格(包含 **[!UICONTROL Denylisted]** 狀態。 進一步了解中的反饋回圈機制 [Adobe傳遞能力最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops).

## 同步與非同步錯誤 {#synchronous-and-asynchronous-errors}

訊息傳送可能會立即失敗，在此情況下，我們會將此錯誤歸類為同步錯誤。 如果訊息傳送失敗或稍後發生，則在傳送後，錯誤為非同步。

以下是這些錯誤類型的管理方式：

* **同步錯誤**:由Adobe Campaign傳送伺服器連絡的遠端伺服器會立即傳回錯誤訊息。 不可將傳送傳送至設定檔的伺服器。 郵件傳輸代理(MTA)會判斷退信類型並限定錯誤，並將該資訊傳回Campaign，以判斷是否應隔離相關電子郵件地址。 請參閱[退信資格](#bounce-mail-qualification)。

* **非同步錯誤**:接收伺服器稍後會重新發送退回郵件或SR。 此錯誤已以與錯誤相關的標籤限定。 傳送後一週內，可能會發生非同步錯誤。

>[!NOTE]
>
>作為「受管Cloud Services」用戶，退信郵箱的配置由Adobe執行。

## 退回郵件資格 {#bounce-mail-qualification}

<!--NO LONGER WITH MOMENTUM - Rules used by Campaign to qualify delivery failures are listed in the **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Delivery log qualification]** node. It is non-exhaustive, and is regularly updated by Adobe Campaign and can also be managed by the user.

![](assets/delivery-log-qualification.png)-->

在Adobe Campaign中處理退信限定的方式取決於錯誤類型：

* **同步錯誤**:MTA會決定退信類型和資格，並將該資訊傳回至Campaign。 中的退信資格 **[!UICONTROL Delivery log qualification]** 表不用於 **同步** 傳遞失敗錯誤訊息。

* **非同步錯誤**:Campaign用來限定非同步傳送失敗的規則列於 **[!UICONTROL Administration > Campaign Management > Non deliverables Management > Delivery log qualification]** 節點。 inMail程式會透過 **[!UICONTROL Inbound email]** 規則。 有關詳細資訊，請參閱 [Adobe Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html#bounce-mail-qualification){target="_blank"}.

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

如果訊息傳送因暫時錯誤而失敗(**軟** 或 **已忽略**)，促銷活動重試次數傳送。 可以執行這些重試，直到傳送持續期間結束為止。

軟退信重試次數及兩者之間的時間長度，由MTA根據來自訊息電子郵件網域傳回之退信的類型和嚴重性決定。

>[!NOTE]
>
>Campaign不會使用傳送屬性中的重試設定。

## 有效期限

您的Campaign傳送中的有效期設定限制為 **3.5天或更少**. 對於傳送，如果您在Campaign中定義的值超過3.5天，則不會考慮該值。

例如，如果有效期在Campaign中設為5天的預設值，則軟跳出訊息會進入MTA重試佇列，並在訊息到達MTA後，僅重試最多3.5天。 在此情況下，將不會使用Campaign中設定的值。

當訊息在 MTA 佇列中停留 3.5 天且無法傳送時，訊息會逾時，其狀態會從傳送記錄檔中的 **[!UICONTROL Sent]** 更新為 **[!UICONTROL Failed]**。

如需有效期的詳細資訊，請參閱 [Adobe Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-sending-the-delivery.html#defining-validity-period){target="_blank"}.


## 電子郵件錯誤類型 {#email-error-types}

對於電子郵件通道，傳送失敗的可能原因列於下方。

<table> 
 <tbody> 
  <tr> 
   <td> 錯誤標籤 </td> 
   <td> 錯誤類型 </td> 
   <td> 技術價值 </td> 
   <td> 說明 </td> 
  </tr> 
  <tr> 
   <td> 帳戶已停用 </td> 
   <td> 軟/硬 </td> 
   <td> 4 </td> 
   <td> 連結至該地址的帳戶已不再有效。 當Internet訪問提供程式(IAP)檢測到長時間的不活動時，它可以關閉用戶的帳戶。 之後無法傳送至使用者位址。 如果帳戶因為6個月的閒置而暫時停用，而且仍可啟動，則會指派狀態「有錯誤」，並再次嘗試帳戶，直到錯誤計數器達到5。 如果錯誤訊號表示帳戶已永久停用，則會直接將其設為隔離。<br /> </td> 
  </tr> 
  <tr> 
   <td> 被隔離的地址 </td> 
   <td> 硬 </td> 
   <td> 9 </td> 
   <td> 地址被置於隔離區。<br /> </td> 
  </tr> 
  <tr> 
   <td> 未指定地址 </td> 
   <td> 硬 </td> 
   <td> 7 </td> 
   <td> 未為收件人指定地址。<br /> </td> 
  </tr> 
  <tr> 
   <td> 品質不良的地址 </td> 
   <td> 已忽略 </td> 
   <td> 14 </td> 
   <td> 此地址的質量評級太低。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已加入封鎖清單的地址 </td> 
   <td> 硬 </td> 
   <td> 8 </td> 
   <td> 地址已在發送時添加到封鎖清單中。 此狀態用於將外部清單和外部系統的資料匯入Adobe Campaign隔離清單。<br /> </td> 
  </tr> 
  <tr> 
   <td> 控制地址 </td> 
   <td> 已忽略 </td> 
   <td> 127 </td> 
   <td> 收件者的地址是控制組的一部分。<br /> </td> 
  </tr> 
  <tr> 
   <td> 雙精度浮點數 </td> 
   <td> 已忽略 </td> 
   <td> 10 </td> 
   <td> 收件者的地址已在此傳遞中。<br /> </td> 
  </tr> 
  <tr> 
   <td> 忽略的錯誤 </td> 
   <td> 已忽略 </td> 
   <td> 25 </td> 
   <td> 地址在允許清單中。 因此，會忽略錯誤，並傳送電子郵件。<br /> </td> 
  </tr> 
  <tr> 
   <td> 仲裁後排除 </td> 
   <td> 已忽略 </td> 
   <td> 12 </td> 
   <td> 收件者被「仲裁」類型的促銷活動類型規則排除。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已由 SQL 規則排除 </td> 
   <td> 已忽略 </td> 
   <td> 11 </td> 
   <td> 收件者被「SQL」類型的促銷活動類型規則排除。<br /> </td> 
  </tr> 
  <tr> 
   <td> 無效的網域 </td> 
   <td> 軟 </td> 
   <td> 2 </td> 
   <td> 電子郵件地址的網域不正確或已不存在。 此設定檔將再次定位，直到錯誤計數達到5。之後，記錄將設定為「隔離」狀態，不會再重試。<br /> </td> 
  </tr> 
  <tr> 
   <td> 郵箱已滿 </td> 
   <td> 軟 </td> 
   <td> 5 </td> 
   <td> 此用戶的郵箱已滿，無法接受更多郵件。 此設定檔將再次定位，直到錯誤計數達到5。之後，記錄將設定為「隔離」狀態，不會再重試。<br /> 此類錯誤由清理進程管理，地址在30天後設為有效狀態。<br /> 警告：若要從隔離位址清單自動移除位址，必須啟動「資料庫清理」技術工作流程。<br /> </td> 
  </tr> 
  <tr> 
   <td> 未連線 </td> 
   <td> 已忽略 </td> 
   <td> 6 </td> 
   <td> 當發送消息時，收件人的行動電話被關閉或未連接到網路。<br /> </td> 
  </tr> 
  <tr> 
   <td> 未定義 </td> 
   <td> 未定義 </td> 
   <td> 0 </td> 
   <td> 該地址正在限定中，因為錯誤尚未增加。 當伺服器傳送新錯誤訊息時，會發生此類錯誤：它可能是孤立的錯誤，但如果再次發生，錯誤計數器會增加，這會提醒技術團隊。然後，他們可以執行訊息分析，並透過 <span class="uicontrol">管理</span> / <span class="uicontrol">Campaign Management</span> / <span class="uicontrol">無法交付的管理</span> 樹結構中的節點。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不符合優惠方案條件 </td> 
   <td> 已忽略 </td> 
   <td> 16 </td> 
   <td> 收件者不符合傳送中優惠方案的資格。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已拒絕 </td> 
   <td> 軟/硬 </td> 
   <td> 20 </td> 
   <td> 由於安全反饋是垃圾郵件報告，該地址已被置於隔離狀態。 根據錯誤，將再次嘗試該地址，直到錯誤計數器達到5，或直接將其傳送至隔離區。<br /> </td> 
  </tr> 
  <tr> 
   <td> 目標大小受限 </td> 
   <td> 已忽略 </td> 
   <td> 17 </td> 
   <td> 已達到收件者的最大傳送大小。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不合格的地址 </td> 
   <td> 已忽略 </td> 
   <td> 15 </td> 
   <td> 郵寄地址不合格.<br /> </td> 
  </tr> 
  <tr> 
   <td> 無法聯繫 </td> 
   <td> 軟/硬 </td> 
   <td> 3 </td> 
   <td> 郵件傳送鏈中出錯。 可能是SMTP中繼的事件、暫時無法存取的網域等。 根據錯誤，將再次嘗試該地址，直到錯誤計數器達到5，或直接將其傳送至隔離區。<br /> </td> 
  </tr> 
  <tr> 
   <td> 使用者不明 </td> 
   <td> 硬 </td> 
   <td> 1 </td> 
   <td> 地址不存在。 此設定檔不會再嘗試傳送。<br /> </td> 
  </tr> 
 </tbody> 
</table>



## 推播通知錯誤類型 {#push-error-types}

針對行動應用程式通道，傳送失敗的可能原因列於下方。

### iOS隔離 {#ios-quarantine}

HTTP/V2通訊協定可針對每個推送傳送提供直接意見和狀態。 若使用HTTP/V2通訊協定連接器，則不再呼叫反饋服務 **[!UICONTROL mobileAppOptOutMgt]** 工作流程。 在卸載或重新安裝移動應用程式時，將令牌視為未註冊。

同步地，如果APN返回消息的「未註冊」狀態，則目標令牌將立即被置於隔離狀態。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>藍本</strong><br /> </td> 
   <td> <strong>狀態</strong><br /> </td> 
   <td> <strong>錯誤訊息</strong><br /> </td> 
   <td> <strong>失敗類型</strong><br /> </td> 
   <td> <strong>失敗原因</strong><br /> </td> 
   <td> <strong>重試</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 已開啟的目標設備<br /> </td> 
   <td> 確定<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 已關閉目標設備<br /> </td> 
   <td> 確定<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 用戶禁用應用程式的通知<br /> </td> 
   <td> 確定<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 消息建立/分析階段 — 負載太大<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 裝載過長<br /> </td> 
   <td> 軟<br /> </td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 訊息建立/分析階段 — 未預期的內容格式問題<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 根據錯誤產生的各種錯誤訊息<br /> </td> 
   <td> 軟<br /> </td> 
   <td> 未定義<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 憑證問題（密碼、損毀等） 和測試與APN的連接問題<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 根據錯誤產生的各種錯誤訊息<br /> </td> 
   <td> 軟<br /> </td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 發送期間網路連接丟失<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 連接錯誤<br /> </td> 
   <td> 未定義<br /> </td> 
   <td> 無法聯繫<br /> </td> 
   <td> 是<br /> </td> 
  </tr> 
  <tr> 
   <td> APN消息拒絕：取消註冊<br /> 用戶已刪除應用程式或令牌已過期<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 未註冊<br /> </td> 
   <td> 硬<br /> </td> 
   <td> 使用者不明<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> APN消息拒絕：所有其他錯誤<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 錯誤消息中將存在錯誤拒絕原因<br /> </td> 
   <td> 軟<br /> </td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Android隔離 {#android-quarantine}

**針對Android V1**

對於每個通知，Adobe Campaign會直接從FCM伺服器接收同步錯誤。 Adobe Campaign會即時處理錯誤，並根據錯誤的嚴重性產生硬錯誤或軟錯誤，並可執行重試：

* 超出裝載長度、連線問題、服務可用性問題：重試已執行，軟錯誤，失敗原因 **[!UICONTROL Refused]**.
* 超出設備配額：無重試，軟錯誤，失敗原因 **[!UICONTROL Refused]**.
* 無效或未註冊的令牌，意外錯誤，發件人帳戶問題：無重試，硬錯誤，失敗原因 **[!UICONTROL Refused]**.

此 **[!UICONTROL mobileAppOptOutMgt]** 工作流程每6小時執行一次以更新 **AppSubscriptionRcp** 表格。 對於已宣告未註冊或不再有效的代號，欄位為 **已停用** 設為 **True** 而連結至該裝置代號的訂閱將會從未來傳送中自動排除。

在傳送分析期間，從目標中排除的所有裝置都會自動新增至 **excludeLogAppSubRcp** 表格。

>[!NOTE]
>
>對於使用Baidu連接器的客戶，以下是不同類型的錯誤：
>
>* 傳送開始時發生連線問題：失敗類型 **[!UICONTROL Undefined]**，失敗原因 **[!UICONTROL Unreachable]**，則會執行重試。
>* 傳送期間連線遺失：軟錯誤，失敗原因 **[!UICONTROL Refused]**，則會執行重試。
>* Baidu在傳送期間傳回的同步錯誤：硬錯誤，失敗原因 **[!UICONTROL Refused]**，則不執行重試。
>
>Adobe Campaign每10分鐘連絡Baidu伺服器以擷取已傳送訊息的狀態，並更新broadlog。 如果訊息宣告為已傳送，則broadlogs中的訊息狀態會設為 **[!UICONTROL Received]**. 如果Baidu宣告錯誤，狀態會設為 **[!UICONTROL Failed]**.

**針對Android V2**

Android V2隔離機制使用的程式與Android V1相同，也同樣適用於訂閱和排除更新。 有關詳細資訊，請參閱 [Android V1](#android-quarantine) 區段。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>藍本</strong><br /> </td> 
   <td> <strong>狀態</strong><br /> </td> 
   <td> <strong>錯誤訊息</strong><br /> </td> 
   <td> <strong>失敗類型</strong><br /> </td> 
   <td> <strong>失敗原因</strong><br /> </td> 
   <td> <strong>重試</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 消息建立/分析階段：自訂欄位中使用的非法關鍵字<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 下列關鍵字無法使用：{1}<br /> </td> 
   <td> 軟<br /> </td> 
   <td> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 消息建立/分析階段：裝載過大<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 通知過重：{1}位，而僅授權{2}<br /> </td> 
   <td> 軟<br /> </td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> 發送期間網路連接丟失<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 地址上沒有來自Firebase雲端訊息服務的回應：{1}<br /> </td> 
   <td> 軟<br /> </td> 
   <td> 無法聯繫<br /> </td> 
   <td> 是<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM報文拒絕：FCM伺服器暫時無法使用（例如逾時）。 <br /> </td> 
   <td> 失敗<br /> </td> 
   <td> Firebase雲端訊息服務暫時無法使用<br /> </td> 
   <td> 軟<br /> </td> 
   <td> 無法聯繫<br /> </td> 
   <td> 是<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM報文拒絕：驗證發件人帳戶時出錯<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 無法識別開發人員帳戶，請檢查您的ID和密碼<br /> </td> 
   <td> 軟<br /> </td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM報文拒絕：已超出設備配額<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> </td> 
   <td> 軟<br /> </td> 
   <td> 已拒絕<br /> </td> 
   <td> 是<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM報文拒絕：註冊無效/未註冊<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> </td> 
   <td> 硬<br /> </td> 
   <td> 使用者不明<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
  <tr> 
   <td> FCM報文拒絕：所有其他錯誤<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> Firebase雲端訊息伺服器傳回未預期的錯誤碼：{1} </td> 
   <td> </td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr> 
    <tr> 
   <td> FCM報文拒絕：參數無效<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> INVALID_ARGUMENT </td> 
   <td> 已忽略</td> 
   <td> 未定義<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> FCM報文拒絕：第三方身份驗證錯誤<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> THIRD_PARTY_AUTH_ERROR </td> 
   <td> 已忽略</td>
   <td> 已拒絕<br /> </td> 
   <td> 是<br /> </td> 
  </tr>
    <tr> 
   <td> FCM報文拒絕：發件人ID不匹配<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> SENDER_ID_MISMATCH </td> 
   <td> 軟</td>
   <td> 使用者不明<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> FCM報文拒絕：未註冊<br /> </td> 
   <td> 失敗<br /> </td>
   <td> 未註冊 </td> 
   <td> 硬</td> 
   <td> 使用者不明<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> FCM報文拒絕：內部<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 內部 </td> 
   <td> 已忽略</td> 
   <td> 已拒絕<br /> </td> 
   <td> 是<br /> </td> 
  </tr>
    <tr> 
   <td> FCM報文拒絕：不可用<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 不可用</td> 
   <td> 已忽略</td> 
   <td> 已拒絕<br /> </td> 
   <td> 是<br /> </td> 
  </tr>
    <tr> 
   <td> FCM報文拒絕：意外錯誤代碼<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 意外錯誤代碼</td> 
   <td> 已忽略</td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
  <tr> 
   <td> 驗證：連線問題<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 無法連接到身份驗證伺服器 </td> 
   <td> 已忽略</td>
   <td> 已拒絕<br /> </td> 
   <td> 是<br /> </td> 
  </tr>
    <tr> 
   <td> 驗證：請求中的未授權客戶端或作用域。<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> unauthorized_client </td> 
   <td> 已忽略</td>
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 驗證：客戶端未授權使用此方法檢索訪問令牌，或客戶端未授權任何請求的作用域。<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> unauthorized_client </td> 
   <td> 已忽略</td>
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 驗證：拒絕訪問<br /> </td> 
   <td> 失敗<br /> </td>
   <td> access_denied</td> 
   <td> 已忽略</td>
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 驗證：無效電子郵件<br /> </td> 
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
   <td> 驗證：JWT簽名無效<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> invalid_grant </td> 
   <td> 已忽略</td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 驗證：提供的OAuth範圍或ID代號對象無效<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> unauthorized_client</td> 
   <td> 已忽略</td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
    <tr> 
   <td> 驗證：OAuth用戶端已停用<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> disabled_client</td> 
   <td> 已忽略</td> 
   <td> 已拒絕<br /> </td> 
   <td> 否<br /> </td> 
  </tr>
 </tbody> 
</table>

## SMS隔離 {#sms-quarantines}

**標準連接器**

SMS通道的特異性列於下方。

>[!NOTE]
>
>此 **[!UICONTROL Delivery log qualification]** 表不適用於 **擴展通用SMPP** 連接器。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>藍本</strong><br /> </td> 
   <td> <strong>狀態</strong><br /> </td> 
   <td> <strong>錯誤訊息</strong><br /> </td> 
   <td> <strong>失敗類型</strong><br /> </td> 
   <td> <strong>失敗原因</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送至提供者<br /> </td> 
   <td> 已傳送<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 在行動裝置上接收<br /> </td> 
   <td> 已收到<br /> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 提供程式返回的錯誤<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 接收資料時出錯（SR或MO）<br /> </td> 
   <td> 軟<br /> </td> 
   <td> 無法聯繫<br /> </td> 
  </tr> 
  <tr> 
   <td> MT確認無效<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 處理髮送查詢的確認幀時出錯「{1}」<br /> </td> 
   <td> 軟<br /> </td> 
   <td> 無法聯繫<br /> </td> 
  </tr> 
  <tr> 
   <td> 發送MT時出錯<br /> </td> 
   <td> 失敗<br /> </td> 
   <td> 傳送訊息時出錯<br /> </td> 
   <td> 軟<br /> </td> 
   <td> 無法聯繫<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Extended generic SMPP連接器**

使用SMPP通訊協定傳送SMS訊息時，錯誤管理的處理方式不同。

SMPP連接器會從SR（狀態報表）訊息中擷取資料，該訊息使用規則運算式(regexes)傳回以篩選其內容。 然後，此資料會與 **[!UICONTROL Delivery log qualification]** 表格(可透過 **[!UICONTROL Administration]** > **[!UICONTROL Campaign Management]** > **[!UICONTROL Non deliverables Management]** 功能表)。

在限定新類型的錯誤之前，失敗原因始終設定為 **已拒絕** 依預設。

>[!NOTE]
>
>失敗類型和原因與電子郵件的相同。
>
>請向提供者索取狀態和錯誤代碼清單，以便在「傳送記錄檔資格」表格中設定正確的失敗類型和失敗原因。

產生的訊息範例：

```
SR Generic DELIVRD 000|#MESSAGE#
```

* 所有錯誤訊息的開頭皆為 **SR** 區分SMS錯誤碼和電子郵件錯誤碼。
* 第二部分(**一般** 在此範例中)，錯誤訊息會參照SMSC實作的名稱，如 **[!UICONTROL SMSC implementation name]** SMS外部帳戶的欄位。

   因為相同的錯誤代碼可能對每個提供程式具有不同的含義，所以此欄位允許您了解生成錯誤代碼的提供程式。 然後，您可以在相關提供者的檔案中找到錯誤。

* 第三部分(**DELIVRD** 在此範例中)，錯誤訊息對應至使用SMS外部帳戶中定義的狀態擷取規則運算式從SR擷取的狀態代碼。

   此規則運算式在 **[!UICONTROL SMSC specificities]** 外部帳戶的索引標籤。
依預設，規則運算式會擷取 **stat:** 欄位，由定義 **附錄B** 區段 **SMPP 3.4規範**.

* 第四部分(**000** 在此範例中)，錯誤訊息對應於使用SMS外部帳戶中定義的錯誤碼擷取regex，從SR擷取的錯誤碼。

   此規則運算式在 **[!UICONTROL SMSC specificities]** 外部帳戶的索引標籤。

   依預設，規則運算式會擷取 **錯誤：** 欄位，由定義 **附錄B** 區段 **SMPP 3.4規範**.

* 垂直號(|)之後的所有內容只會顯示在 **[!UICONTROL First text]** 欄 **[!UICONTROL Delivery log qualification]** 表格。 此內容一律會取代為 **#MESSAGE#** 標準化後。 此程式可避免因類似錯誤而有多個項目，且與電子郵件的項目相同。

Extended generic SMPP連接器應用啟發式來查找明顯預設值：如果狀態開頭為 **DELIV**，則會視為成功，因為它符合常見狀態 **DELIVRD** 或 **傳遞** 供大部分提供者使用。 任何其他狀態都會導致硬性失敗。
