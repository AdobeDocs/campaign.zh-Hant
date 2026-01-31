---
title: Campaign v8 發行說明
description: 最新的 Campaign v8 版本
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: 6693bb8a62c0d126b871dc24a75b76de71b86f8d
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 21%

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
* [內容實驗 — A/B測試](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/email/ab-testing.html?lang=zh-Hant)
* [持續傳遞活動](https://experienceleague.adobe.com/docs/campaign-web/v8/wf/design-workflows/continuous-delivery.html?lang=zh-Hant)
* [行銷活動核准管理](https://experienceleague.adobe.com/docs/campaign-web/v8/campaigns/campaign-approvals.html?lang=zh-Hant)

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

* 修正依特定欄分組時，動態報告顯示錯誤計數的問題。 (NEO-86898)
* 解決動態報告與實際行銷活動資料之間的資料差異。 (NEO-88068)
* 修正PostgreSQL「char」欄位型別造成查詢意外結果的串連問題。 (NEO-87769)
* 修正JavaScript logInfo命令未正確處理某些引數的問題。 (NEO-88263)
* 解決訊息中心即時事件處理中的同步處理擱置問題。 (NEO-88330)
* 修正視覺編輯器自動重新格式化HTML內容，造成版面變更的問題。 (NEO-88409)
* 修正重複資料刪除活動無法正確使用臨時結構描述的問題。 (NEO-88577)
* 修正傳送校樣時無法產生種子地址的問題。 (NEO-88720)
* 透過最佳化資料分割資料行處理，改善PostgreSQL查詢效能。 (NEO-88771)
* 解決檔案傳輸活動未正確處理行接續字元的問題。 (NEO-88812)
* 增強的PostgreSQL查詢最佳化功能，可在大型資料集中提供更優異的效能。 (NEO-88885)
* 修正無法開啟混合式促銷活動的「許可權遭拒」錯誤。 (NEO-88955)
* 延伸條碼功能支援，可處理較長的文字字串。 (NEO-88958)
* 修正使用校樣與循環傳送時，行銷活動記錄中發生的錯誤。 (NEO-88976)
* 修正了在某些情況下影響電子郵件傳送作業的問題。 (NEO-89019)
* 解決工作流程開始模式意外地從立即變更為正常的問題。 (NEO-89025)
* 修正在特定條件下執行更新資料活動時發生的錯誤。 (NEO-89031)
* 修正更新資料活動遺失自訂結構描述中繼資料的問題。 (NEO-89056)
* 修正了傳遞準備期間發生的驗證錯誤。 (NEO-89063)
* 解決當查詢包含1-1連結關係的篩選器時產生無效的SQL。 (NEO-89065)
* 修正增量查詢活動未遵循設定大小限制的問題。 (NEO-89066)
* 改善FFDA部署中的工作流程效能，以進行大規模作業。 (NEO-89098)
* 增強工作流程記憶體管理和穩定性。 (NEO-89105)
* 為網路表單啟用嚴格的欄驗證，以防止資料不一致。 (NEO-89111)
* 解決造成處理延遲的訊息中心同步處理問題。 (NEO-89138)
* 修正「重新整理傳遞能力」工作流程中，無法正確執行的錯誤。 (NEO-89160)
* 修正了在工作流程中執行JavaScript程式碼活動時發生的錯誤。 (NEO-89169)
* 已移除硬式編碼Snowflake倉儲設定，以允許適當的外部帳戶設定。 (NEO-89201)
* 修正工作流程檔案傳輸作業期間發生的403個禁止錯誤。 (NEO-89226)
* 已在FFDA部署中的收件者表格上最佳化緩慢查詢。 (NEO-89268)
* 修正增量查詢活動忽略已設定排程的問題。 (NEO-89317)
* 解決在混合環境中開啟行銷活動時的存取錯誤。 (NEO-89320)
