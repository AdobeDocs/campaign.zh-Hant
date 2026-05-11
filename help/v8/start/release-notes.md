---
title: Campaign v8 發行說明
description: 最新的 Campaign v8 版本
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 4a3e6cf15b1877e6eb4e13fdee056356eab267c5
workflow-type: tm+mt
source-wordcount: '1747'
ht-degree: 6%

---

# 最新版本 {#latest-release}

本頁面列出 Campaign v8 (主控台) **最新版本**&#x200B;中的新功能、改善和修正。 在[此頁面](upgrades.md)進一步了解 Campaign 行銷活動發布、版本和更新。 本文件的先前版本區段將列出其他版本。

## 發行版本8.9.2 {#release-8-9-2}

>[!CAUTION]
>
> 用戶端主控台升級為強制。 透過本[頁面](../start/connect.md#upgrade-ac-console)了解如何升級您的用戶端主控台。

_2026年5月3日_

### 安全性改善 {#security-8-9-2}

* 為了維持最佳的安全性、穩定性和法規遵循，所有執行個體都已升級至Debian 13和PostgreSQL 17。

### 修正 {#fixes-8-9-2}

>[!NOTE]
>
> 下列修正專案已逐步在後續的8.9.2版本編號中推出。 導覽至&#x200B;**[!UICONTROL Help > About...]** [功能表](upgrades.md#version)，檢查您是否有最新的8.9.2 (11d1c68)版本。 如需詳細資訊，請聯絡您的Adobe代表。

* 修正由於資料型別轉換問題而導致交易事件中的事件日期設定不正確，造成動態報告中的日期不正確的問題。 (NEO-93923)
* 修正標題和內文欄位空白時，Android和iOS無訊息推播通知在傳送準備期間失敗的問題。 (NEO-93739)
* 修正因調解金鑰不正確而無法為Android應用程式註冊權杖擷取語言欄位的問題。 (NEO-93100)
* 修正透過壓力規則套用自訂型別規則時，傳送準備失敗的問題。 (NEO-94457)
* 修正使用者端主控台可能發生HTTP要求處理失敗的問題。 (NEO-94071)

<!-- BUILD 8.9.2.9829.9669833 -->

* FDA監視現在預設為停用，以防止連線記錄插入錯誤。 (NEO-94841)
* 修正用於優惠兌換的互動SOAP呼叫可能因名稱空間解析錯誤而失敗的問題。 (NEO-94787)
<!-- infra * Fixed an issue where Snowflake connections using private key authentication could fail on ARM64 architectures. (NEO-94350) -->
* 修正長度為1的字串欄位可能導致PostgreSQL 17上的工作流程臨時表格發生SQL錯誤的問題。 (NEO-94487)
<!-- linked to previous build * Fixed an issue where the server could fail to restart after a Debian 13 build upgrade due to a missing dependency. (NEO-94598) -->

<!-- BUILD 8.9.2.9829.c90aa36 -->

* 修正使用者端主控台和Web UI中的&#x200B;**顯示映象頁面**&#x200B;選項可能傳回「錯誤的映象頁面」錯誤的問題。 (NEO-93303)

<!-- BUILD 8.9.2.9830.4a6f868 -->

* 修正在FFDA部署中安裝多變數套件後，現成可用的&#x200B;**追蹤**&#x200B;技術工作流程可能失敗的問題。 (NEO-94972)
* 修正當傳遞範本使用參考目前傳遞的權重公式時，傳遞準備無法將任何收件者新增至目標的問題。 (NEO-94892)
<!-- hotfix -->
* 修正了在升級後，使用兩個連續1-N連結的聯結來擴充工作流程時，可能會因SQL錯誤而失敗的問題。 (NEO-94893)

<!-- BUILD 8.9.2.9831.f53d3d2 -->

* 修正電子郵件管道中可能導致一段時間後記憶體過度消耗的問題。 (NEO-95088)
* 修正當使用種子或校樣地址時，衝突的電子郵件型別規則可能錯誤地將非重複收件者從傳遞目標中排除的問題。 (NEO-95026)
* 已修正升級後現成可用的&#x200B;**優惠通知**&#x200B;技術工作流程可能失敗的問題。 (NEO-95064)
* 多變數套件安裝程式已經過改善，以防止在建置升級期間追蹤工作流程失敗。 (NEO-95018)

<!-- BUILD 8.9.2.9831.11d1c68 -->

* 修正可能導致伺服器重複當機，導致執行個體中斷的問題。 (NEO-95304)
* 修正追蹤和映象頁面連結無法載入傳遞的問題。 (NEO-95239)
* 修正了登入受IMS單一登入保護的Campaign Web應用程式時，可能會導致重新導向回圈的問題。 (NEO-95188)
* 修正儲存傳遞後，傳遞擷取檔案中缺少傳遞建立日期的問題。 (NEO-95010)
* 修正大量產生的子工作流程可能卡在&#x200B;**正在編輯**&#x200B;狀態的問題，減少異動工作流程容量。 (NEO-95131)
* 修正&#x200B;**讀取清單**&#x200B;活動可能會以工作流程產生的清單結構覆寫預先定義的清單範本，導致下游工作流程失敗的問題。 (NEO-95103)
* 修正推播通知回饋處理在處理大量傳遞時，可能導致伺服器當機的問題。 (NEO-95150)
* 修正在結構描述總管中開啟`xtk:workflow`結構描述上的&#x200B;**資料**&#x200B;索引標籤可能會觸發錯誤訊息的問題。 (NEO-94923)
<!-- hotfixes -->
* 修正&#x200B;**擴充**&#x200B;活動無法再從上游&#x200B;**子工作流程**&#x200B;活動中擷取輸出屬性，導致工作流程失敗的問題。 (NEO-95151)
* 修正了追蹤資料擷取的問題，此問題可能會阻止傳遞狀態更新並封鎖下游訊息處理。 (NEO-94666)
* 修正與優惠方案主張相關的某些使用者端主控台動作可能會在Snowflake資料庫上觸發長期執行查詢，導致鎖定和速度緩慢的問題。 (NEO-92936)
* 修正無法在Snowflake外部帳戶上設定儲存加密金鑰的自訂選項的問題。 (NEO-93302)

<!-- 
Internal/non-customer-facing:
* Internal test automation task added to cover NEO-94893. (NEO-94990) — autotest only
Customer-specific hotfixes:
* Fixed an issue affecting WhatsApp delivery preparation. (NEO-92480) — HeroMotoCorp only
* Added a feature-flagged optimization to use dynamic shared memory in Customer Targeting Audience (CTA) processing. (NEO-93542) — DerTour only
* Fixed an issue where the delivery alerting workflow could fire incorrect "long start pending" notifications even when deliveries were sent within the configured threshold. (NEO-93434) — non-ZDT hotfix, NORC only
* Added a new parameter in the mobile SDK to allow identification of the source instance for push notifications. (NEO-94650) — ICICI only
* Fixed an issue with the custom send time feature on the Web UI where deliveries waited until the contact date and time to execute instead of executing at the equivalent local time per recipient timezone, breaking parity with Campaign Standard behavior. (NEO-94762) — H&M only (in progress at time of writing)
-->

## 發行版本8.9.1 {#release-8-9-1}

_2026 年 1 月 27 日_

>[!CAUTION]
>
> 用戶端主控台升級為強制。 透過本[頁面](../start/connect.md#upgrade-ac-console)了解如何升級您的用戶端主控台。

### 新功能 {#new-8-9-1}

**新SMS傳送聯結器**&#x200B;現在可供所有客戶使用(GA)。 請參閱[詳細檔案](../send/sms/sms.md)。

此版本隨附Campaign Web使用者介面提供的一組功能：

* [多語言傳送功能 (正式推出)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html){target="_blank"}
* [異動訊息(GA)中的設定檔擴充](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html){target="_blank"}
* [Adobe Experience Manager即時和語言副本](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html){target="_blank"}
* [內容實驗 — A/B測試](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html){target="_blank"}
* [持續傳遞活動](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html){target="_blank"}
* [行銷活動核准管理](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html){target="_blank"}

請參閱Campaign Web UI [發行說明](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=zh-hant){target="_blank"}

### 安全性改善 {#security-8-9-1}

* Snowflake外部帳戶現在支援OAuth2驗證，為同盟資料存取連線提供現代且安全的驗證方法。 (NEO-87013) [瞭解詳情](../config/external-accounts.md#snowflake-external-accounts)
* Databricks外部帳戶現在支援透過服務主體（非互動式使用者端憑證流程）的OAuth2驗證，為同盟資料存取連線提供安全的驗證方法。 互動式OAuth2驗證將在未來版本中提供。 (NEO-87422) [瞭解詳情](../config/external-accounts.md#databricks-external-accounts)
* 修正工作流程檔案存取漏洞，限制對授權目錄的操作，防止未經授權的存取和可能的遠端程式碼執行。 (NEO-88460)
* 新增FTP URL允許清單控制項至工作流程JavaScript程式碼活動，限制只有授權位址的輸出FTP連線。 (NEO-89083)

### 其他變更 {#changes-8-9-1}

* 透過在高記憶體狀況期間實施自動工作流程節流，以及針對非關鍵性程式的智慧型工作流程重新啟動功能和記憶體護欄，改善容器記憶體管理。 (NEO-89041)
* 新增對Campaign工作流程中非對稱加密和解密功能的支援。 (NEO-80257)
* 針對FFDA部署中的大型資料上傳，增強復寫代理程式效能和記憶體彈性。 (NEO-88430)
* 已改善&#x200B;**[!UICONTROL SQL code]**&#x200B;和&#x200B;**[!UICONTROL SQL Data Management]**&#x200B;工作流程活動，以便在從Campaign執行自訂SQL時，更能保護PostgreSQL資料庫，並保持工作流程順暢執行。 如需詳細資訊和最佳實務，請參考[SQL資料管理](../../automation/workflow/sql-data-management.md#important-notes)和[SQL程式碼](../../automation/workflow/sql-code-and-javascript-code.md#important-notes)。 (NEO-86540)


### 修正 {#fixes-8-9-1}

* 修正sysFilter變更後無法更新資料庫結構的問題。 (NEO-93306)
* 修正移轉後遺失動態報表資料的問題。 (NEO-92962)
* 修正傳送狀態未正確更新的問題。 (NEO-92908)
* 修正了與Databricks FDA使用目錄限制相關的問題。 (NEO-92900)
* 修正可能導致Outlook Windows案頭發生HTML配置錯誤的問題。 (NEO-92611)
* 修正升級後傳遞主要金鑰在中間執行個體上重複的資料完整性問題。 (NEO-92424)
* 修正無法在傳遞的「追蹤與影像」對話方塊中停用連結的問題。 (NEO-92381)
* 修正nms.subscribtion.RecipientSubscribe()函式無法用於大量訂閱的問題。 (NEO-92308)
* 修正升級後因缺少傳遞部分而導致傳遞失敗的問題。 (NEO-92278)
* 修正追蹤工作流程中，重複狀態錯誤和SQL語法錯誤無法更新追蹤指標的問題。 (NEO-92239)
* 修正使用dbEnum欄位時，透過工作流程建立的清單遺失或不正確顯示列舉欄位標籤的問題。 (NEO-91158)
* 修正RT發佈/取消發佈對話方塊未關閉及凍結的問題。 (NEO-91038)
* 修正收件者發生「服務提供者已考慮」狀態的問題。 (NEO-90927)
* 修正選擇退出連結缺少（取消）訂閱來源的問題。 (NEO-90714)
* 修正傳送準備失敗時新增優惠券的問題。 (NEO-90547)
* 修正「稽核」索引標籤未正確反映「插入拒絕計數」的問題。 (NEO-90318)
* 修正可能導致應用程式拒絕服務的安全性問題。 (NEO-89984)
* 修正Hotclick報表中，已下載的PDF發生中斷的問題。 (NEO-89954)
* 解決升級後發生的SSL錯誤，在讀取錯誤時造成未預期的EOF。 (NEO-89108)
* 修正升級後無法在資料結構描述中查詢資料的問題。 (NEO-88663)
* 修正PostgreSQL 15中串連「char」欄位時發生的錯誤。 (NEO-88028)
* 修正儲存或複製範本時傳遞範本變數順序已變更的問題。 (NEO-87845)
* 修正建立新資料庫結構描述導致Web介面當機的問題。 (NEO-87816)
* 修正重複資料刪除活動中具有補充集的問題。 (NEO-87711)
* 修正無X11相依性的安裝套件要求。 (NEO-87471)
* 修正無法在動態報告中使用區段代碼的問題。 (NEO-87276)
* 修正工作流程卡在更新資料活動中的問題。 (NEO-87252)
* 修正BigQuery使用錯誤時區的問題。 (NEO-86622)
* 修正評估「mcSynch_mcExec1/jsReplicateUrl」指令碼時發生的JavaScript錯誤。 (NEO-86553)
* 修正由於識別碼計算方法不正確而導致重複事件出現在eventHisto表格的問題。 (NEO-86544)
* 修正複製時無法針對iOS推送顯示進階標籤的問題。 (NEO-86231)
* 修正復寫參考表格工作流程在復寫nms:delivery結構描述時失敗的問題。 (NEO-85884)
* 修正傳送傳遞時，錯誤記錄中出現與MXIP位址相對應的Null網域錯誤的問題。 (NEO-85238)
* 修正變更選項後未重新整理技術傳遞範本的問題。 (NEO-84149)
* 修正現成可用的帳單工作流程中的錯誤。 (NEO-83624)
* 修正僅根據目標籤錄的主索引鍵排除重複專案的問題。 (NEO-82910)
* 修正Campaign Web UI報表中，追蹤統計資料顯示與控制檯不同值的差異。 (NEO-82339)
* 修正即使不應在「更新資料」活動中更新記錄，上次修改日期仍變更的問題。 (NEO-82002)
* 修正在清單中新增屬性導致工作流程讀取清單失敗的問題。 (NEO-80258)
* 修正追蹤指標報告針對不同開啟顯示錯誤值的問題。 (NEO-79466)