---
title: Campaign v8 發行說明
description: 最新的 Campaign v8 版本
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 4fe8b8eaf88f763e796dbe06ef3c1477de12bad6
workflow-type: tm+mt
source-wordcount: '921'
ht-degree: 18%

---

# 最新版本 {#latest-release}

本頁面列出 Campaign v8 (主控台) **最新版本**&#x200B;中的新功能、改善和修正。在[此頁面](upgrades.md)進一步了解 Campaign 行銷活動發布、版本和更新。本文件的先前版本區段將列出其他版本。

## 發行版本 8.9.1 {#release-8-9-1}

_2026 年 1 月 27 日_

>[!CAUTION]
>
> 用戶端主控台升級為強制。 透過本[頁面](../start/connect.md#upgrade-ac-console)了解如何升級您的用戶端主控台。

### 新功能 {#new-8-9-1}

**新SMS傳送聯結器**&#x200B;現在可供所有客戶使用(GA)。 請參閱[詳細檔案](../send/sms/sms.md)。

此版本隨附Campaign Web使用者介面提供的一組功能：

* [多語言傳遞功能(GA)](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html?lang=zh-Hant){target="_blank"}
* [異動訊息(GA)中的設定檔擴充](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html?lang=zh-Hant){target="_blank"}
* [Adobe Experience Manager即時和語言副本](https://experienceleague.adobe.com/docs/campaign-web/v8/integrations/aem-multilingual.html?lang=zh-Hant){target="_blank"}
* [內容實驗 — A/B測試](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html?lang=zh-Hant){target="_blank"}
* [持續傳遞活動](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html?lang=zh-Hant){target="_blank"}
* [行銷活動核准管理](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html?lang=zh-Hant){target="_blank"}

請參閱Campaign Web UI [發行說明](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=zh-hant){target="_blank"}

### 安全性改善 {#security-8-9-1}

* Snowflake外部帳戶現在支援OAuth2驗證，為同盟資料存取連線提供現代且安全的驗證方法。 (NEO-87013)
* 修正工作流程檔案存取漏洞，限制對授權目錄的操作，防止未經授權的存取和可能的遠端程式碼執行。 (NEO-88460)
* 新增FTP URL允許清單控制項至工作流程JavaScript程式碼活動，限制只有授權位址的輸出FTP連線。 (NEO-89083)

### 其他變更 {#changes-8-9-1}

* 透過在高記憶體狀況期間實施自動工作流程節流，以及針對非關鍵性程式的智慧型工作流程重新啟動功能和記憶體護欄，改善容器記憶體管理。 (NEO-89041)
* 新增對Campaign工作流程中非對稱加密和解密功能的支援。 (NEO-80257)
* 針對FFDA部署中的大型資料上傳，增強復寫代理程式效能和記憶體彈性。 (NEO-88430)


### 修正 {#fixes-8-9-1}

* 修正sysFilter變更後無法更新資料庫結構的問題。 (NEO-93306)
* 解決移轉後遺失動態報表資料的問題。 (NEO-92962)
* 修正傳送狀態未正確更新的問題。 (NEO-92908)
* 新增Databricks FDA USE CATALOG限制的因應措施。 (NEO-92900)
* 修正視覺化編輯器在Outlook Windows案頭中破壞HTML版面的問題。 (NEO-92611)
* 解決在升級後傳遞主要金鑰在中間執行個體上重複的嚴重資料完整性問題。 (NEO-92424)
* 修正無法在傳遞的「追蹤與影像」對話方塊中停用連結的問題。 (NEO-92381)
* 修正nms.subscription.RecipientSubscribe()函式無法用於大量訂閱的問題。 (NEO-92308)
* 解決升級後因缺少傳遞部分而導致傳遞失敗的問題。 (NEO-92278)
* 修正追蹤工作流程中的問題。 (NEO-92239)
* 解決使用工作流程建立清單後，清單XML中遺失暫時列舉參考的問題。 (NEO-91158)
* 修正RT發佈/取消發佈對話方塊未關閉及凍結的問題。 (NEO-91038)
* 解決卡在「服務提供者考慮」狀態的收件者未達到Momentum的問題。 (NEO-90927)
* 修正選擇退出連結的v8中缺少（取消）訂閱來源的問題。 (NEO-90714)
* 修正傳送準備失敗時新增優惠券的問題。 (NEO-90547)
* 修正「稽核」索引標籤未正確反映「插入拒絕計數」的問題。 (NEO-90318)
* 解決可能導致應用程式拒絕服務的安全性問題。 (NEO-89984)
* 修正Hotclick報表中，已下載的PDF發生中斷的問題。 (NEO-89954)
* 解決升級後發生的SSL錯誤，在讀取錯誤時造成未預期的EOF。 (NEO-89108)
* 修正升級後無法在資料結構描述中查詢資料的問題。 (NEO-88663)
* 修正PostgreSQL 15中串連「char」欄位時發生的錯誤。 (NEO-88028)
* 修正儲存或複製範本時傳遞範本變數順序已變更的問題。 (NEO-87845)
* 解決建立新資料庫結構描述導致Web介面當機的問題。 (NEO-87816)
* 修正重複資料刪除活動的補充集區段代碼無法運作的問題。 (NEO-87711)
* 解決無X11相依性的安裝套件要求。 (NEO-87471)
* 修正無法在動態報告中使用區段代碼的問題。 (NEO-87276)
* 解決工作流程卡在更新資料活動中的問題。 (NEO-87252)
* 修正BigQuery使用錯誤時區的問題。 (NEO-86622)
* 修正評估指令碼「mcSynch_mcExec1/jsReplicateUrl」時所發生的JavaScript錯誤。 (NEO-86553)
* 解決因識別碼計算方法在eventHisto表格中出現重複事件的問題。 (NEO-86544)
* 修正複製時無法針對iOS推送顯示進階標籤的問題。 (NEO-86231)
* 解決復寫參考表格工作流程無法復寫nms:delivery結構描述的問題。 (NEO-85884)
* 修正傳送傳遞時，錯誤記錄中出現與MXIP位址相對應的Null網域錯誤的問題。 (NEO-85238)
* 新增對選項進行任何變更後，重新整理技術傳遞範本的方法。 (NEO-84149)
* 修正現成可用的帳單工作流程中的錯誤。 (NEO-83624)
* 解決僅根據目標籤錄的主索引鍵排除重複專案的問題。 (NEO-82910)
* 修正Campaign Web UI報表中，追蹤統計資料顯示與控制檯不同值的差異。 「追蹤指標」、「傳送摘要」和「URL點按資料流」報表現在會顯示兩個介面中一致的量度。 (NEO-82339)
* 修正即使不應在「更新資料」活動中更新記錄，上次修改日期仍變更的問題。 (NEO-82002)
* 修正在清單中新增屬性導致工作流程讀取清單失敗的問題。 (NEO-80258)
* 解決追蹤指標報表中的異常問題。 (NEO-79466)