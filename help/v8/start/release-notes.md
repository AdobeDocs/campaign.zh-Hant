---
product: Adobe Campaign
title: Campaign v8 發行說明
description: 最新的 Campaign v8 版本
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: false
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471,a9d18e75-18e7-491e-bfc4-671c3600396e
source-git-commit: 5b81c8e9e391ea1a9ad1825e5102b66c7926c204
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 43%

---

# 最新發行版本{#latest-release}

本頁面列出&#x200B;**最新 Campaign v8 版本**&#x200B;的新功能、改善和修正。

## 第 8.1.20 發行版本 {#release-8-1-20}

_2021年9月7日_

**安全性增強功能**

* 修正了安全性問題，以針對目錄周遊攻擊加強保護。 (NEO-28547)

**功能改善**

* 生命週期結束後，Flash已從所有相關的Campaign功能和元件中移除，並更換為HTML5。 已移除圖表的&#x200B;**儀表**&#x200B;類型。 (NEO-30330)[了解詳情](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/creating-a-chart.html)
* 在Windows上安裝客戶端控制台時，安裝程式現在會檢查是否有父註冊表節點，如果缺少，則會建立一個。 這可防止啟動主控台時發生潛在問題。 (NEO-34854)
* 追蹤簽章功能已經過改良，以防止連結至協力廠商工具（電子郵件用戶端、網際網路瀏覽器等）的錯誤 處理特殊字元。 URL參數現在已編碼。

**其他變更**

* 先前已棄用的Microsoft CRM連接器（Office 365和內部部署）已從介面中移除。 [顯示全文](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html#configure-acc-for-microsoft)
* 遷移到Tomcat 8後，已更新IIS安裝指令碼，以修正IIS整合問題。 (NEO-31019)
* 已新增護欄，僅允許[帳單技術工作流程](https://experienceleague.adobe.com/docs/campaign-classic/using/monitoring-campaign-classic/production-procedures/monitoring-processes.html#billing-report)在行銷執行個體上執行。
* 已在工作流程轉變「 **檢視母體**」視窗的資料和架構標籤中改善資料來源識別。
* 已將缺少的資料庫索引添加到以下架構中，以防止出現資料庫更新問題：xtk:rights, nms:dlvExclusion, nms:seedMember, nms:trackingUrl

**修補程式**

* 修正當選件連結至傳送時，**熱點點按**&#x200B;報表無法運作的問題。 (NEO-26295)
* 修正了&#x200B;**Sub-worklow**&#x200B;活動執行未產生輸出表格時的問題。 (NEO-36242)
* 修正將&#x200B;**描述性分析**&#x200B;報表匯出為PDF時的各種問題。 (NEO-25847)
* 修正使用外部郵件傳送時，可能導致傳送失敗的問題。 (NEO-37435)
* 修正使用Web API連線至Microsoft CRM時的錯誤。 由於功能未受影響，因此錯誤訊息已移除。
* 修正了當mid伺服器設為追蹤和行銷伺服器之間的中繼時，追蹤記錄重複資料刪除的問題。 (NEO-36285)
* 修正了無法將Vault用作特定代碼儲存區的回歸。
* 修正當傳入轉變來自FDA資料來源時，無法在&#x200B;**Excrent**&#x200B;工作流程活動中使用變數的問題。
* 修正FFDA無法正確復寫運算子群組和權限的問題。
* 修正了可能導致透過傳送傳送錯誤取消訂閱連結的問題。
* 修正復寫管理中影響升級後期間的問題。
* 修正了無法顯示&#x200B;**熱點點按**&#x200B;的問題。
* 修正可能導致電子郵件訊息中URL損毀的問題。

## 第 8.1.14 發行版本 {#release-8-1-14}

_2021 年 7 月 23 日_

**有哪些新增功能？**

<table>
<thead>
<tr>
<th><strong>新工作流程活動：變更資料來源</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新的<b>變更資料來源</b>工作流程活動可讓您變更工作流程工作表格的資料來源。 這為管理不同資料來源 (FDA、FFDA &amp; 本機資料庫) 的資料提供更強大的彈性。</p>
<p>在 Adobe Campaign 工作流程中，使用工作 (或暫時) 表格來管理資料。 工作流程執行時，工作表格會在各工作流程活動中共用資料。 在預設情況下，工作表格與我們查詢的資料來源建立在同一資料庫上。</p>
<p>使用 Campaign v8 時，主要設定檔表格會直接儲存在雲端資料庫中。 因此，查詢設定檔表格也會在雲端資料庫上建立工作表格。 在某些情況下，將工作表格移動到其他資料來源以執行特定操作是很合理的。</p>
<p>如需詳細資訊，請參閱<a href="../config/workflows.md#change-data-source-activity">詳細文件</a>，以瞭解詳情。</p>
</td>
</tr>
</tbody>
</table>

<table> 
<thead>
<tr> 
<th> <strong>LINE 頻道可用性</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p><a href="../send/line.md">LINE 頻道</a>現在可與 Campaign v8 搭配使用，包括與<a href="../send/transactional.md">異動訊息</a>模組結合時的下列增強功能：
<ul> 
<li><p>修正無法在 LINE 傳遞中鎖定訪客的問題。 
</p></li>
<li><p>修正從執行實例擷取訪客至行銷執行個體時，可能會導致錯誤的問題。
</p></li>
<li><p>修正處理即時事件期間的問題。</p></li>
</ul>
</td> 
</tr> 
</tbody> 
</table>

**其他改善項目**

* 修正了無法針對特定傳遞顯示&#x200B;**熱點點選**&#x200B;報告的問題。
* 修正&#x200B;**重複資料刪除**&#x200B;工作流程活動可能導致錯誤重複計數的問題。
* 修正搭配「ID不是空白」篩選使用工作流程查詢時，可能導致轉變母體中顯示空白項目的問題。
* 修正無法在新目標對應中建立其他欄位的問題。
