---
title: Adobe Campaign內建報表
description: 內建報表
feature: Reporting
source-git-commit: 9bea7904ea4507083d2cf45193877e7a2539d0c7
workflow-type: tm+mt
source-wordcount: '1111'
ht-degree: 1%

---

# Adobe Campaign內建報表{#ootb-reports}

此頁面提供Adobe Campaign內建報表的清單、其內容及其內容。 Adobe Campaign提供一系列內建報表，可透過用戶端主控台或網際網路瀏覽器存取。

可使用下列類型的報表：

* 整個平台的報表。 [了解更多資訊](global-reports.md)。
* 傳遞報告. [了解更多資訊](delivery-reports.md)。

您可以從Campaign首頁、專用報表控制面板或傳送清單存取內建報表。 報表在UI中的顯示方式取決於其內容。

首頁上提供重要報表清單，可讓您快速存取傳送資料。 您可以變更此清單以符合您的需求。 您也可以了解如何將自己的報表新增至 **[!UICONTROL Reports]** 標籤。

如需這些自訂設定的詳細資訊，請參閱 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/reporting/creating-new-reports/configuring-access-to-the-report.html).


## 存取內建報吿 {#access-ootb-reports}

若要存取Campaign內建報表：

1. 選取 **[!UICONTROL Reports]** 頁簽。

   ![](assets/reporting-access-from-home.png)

1. 使用搜尋欄位來篩選顯示的報表。

1. 然後按一下您要顯示的報表。

   ![](assets/edit-a-report.png)

1. 按一下 **[!UICONTROL Back]** 螢幕頂端的連結會帶您回到報表清單。

   ![](assets/back-button.png)

行銷活動或傳送的特定報表可透過其各自的控制面板存取。

![](assets/reporting-on-delivery.png)

清單、服務、優惠方案等原則相同。 如下所示：

![](assets/reporting-on-offer.png)


## 傳遞報表 {#reports-on-deliveries}

Adobe Campaign提供的內建報表位於下表。

如需這些報表內容的詳細資訊，請參閱 [本節](delivery-reports.md).

<table> 
 <tbody> 
  <tr> 
   <td> <strong>標籤和內部名稱</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
   <td> <strong>結構描述</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 使用者活動(recipientActivity)<br /> </td> 
   <td> 依時段劃分開啟、點按和交易。<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送總處理量（輸送量）<br /> </td> 
   <td> 傳送吞吐量圖表，以報文/小時和Mbit/s為單位。<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 失敗和退信（錯誤）<br /> </td> 
   <td> 退信和不可交付項（按原因和域）。<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 追蹤指標(deliveryFeedback)<br /> </td> 
   <td> 追蹤收件者行為的關鍵指標摘要。<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 追蹤指標(mobileAppDeliveryFeedback)<br /> </td> 
   <td> 追蹤傳送至行動應用程式的指標。<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 瀏覽器(browserStatistics)<br /> </td> 
   <td> 按一下訊息之收件者所使用之瀏覽器的統計資料。<br /> </td> 
   <td> xtk:none<br /> </td> 
  </tr> 
  <tr> 
   <td> 分享至社交網路(deliveryForward)<br /> </td> 
   <td> 共用活動和郵件開啟統計資訊。<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 熱點點按（捲動）<br /> </td> 
   <td> 顯示疊加的消息和點按率。<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 假設報表(deliveryHexposition)<br /> </td> 
   <td> 顯示有關交付假設的測量摘要。<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送統計資料(statisticsPerDelivery)<br /> </td> 
   <td> 每個電子郵件網域的統計資料（已處理的訊息、已傳送的訊息、硬退信、軟退信、點按、取消訂閱）。<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 共用活動統計資料(forwardActivities)<br /> </td> 
   <td> 分析每個時段的共用活動、開啟和訂閱。<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 追蹤統計資料(trackingStatistics)<br /> </td> 
   <td> 開啟，按一下「和」交易率報表。<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送摘要(deliverySending)<br /> </td> 
   <td> 交付指標摘要：目標、排除和已傳送的訊息。<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送摘要(deliveryStatistics)<br /> </td> 
   <td> 所選傳送的摘要表格：已傳送目標、排除和訊息。<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> 作業系統(osStatistics)<br /> </td> 
   <td> 按一下訊息的收件者所使用作業系統的統計資料。<br /> </td> 
   <td> xtk:none<br /> </td> 
  </tr> 
  <tr> 
   <td> 反應率(deliveryFeedbackSocial)<br /> </td> 
   <td> 輸送反應率和反應分解。<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> URL和點按輸送量(topUrlDelivery)<br /> </td> 
   <td> 反應性最強的URL和相關的點按資料流。<br /> </td> 
   <td> nms:delivery<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 行銷活動報表 {#reports-on-campaigns}

行銷活動報表與 **nms:operation** 表格。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>標籤和內部名稱</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 使用者活動(operationRecipientActivity)<br /> </td> 
   <td> 依時段劃分的開啟、點按和交易次數，取決於促銷活動。<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送總處理能力(operationThroughput)<br /> </td> 
   <td> 以郵件/小時和Mbit/s為單位的傳送吞吐量圖表取決於Campaign。<br /> </td> 
  </tr> 
  <tr> 
   <td> 促銷活動費用(budgetOperationExpenses)<br /> </td> 
   <td> 根據促銷活動顯示詳細的促銷活動明細項目。<br /> </td> 
  </tr> 
  <tr> 
   <td> 失敗和退信(operationErrors)<br /> </td> 
   <td> 退信和不可交付項目（依原因和網域）取決於Campaign。<br /> </td> 
  </tr> 
  <tr> 
   <td> 探索成本行(budgetExplorerOperation)<br /> </td> 
   <td> 成本行的描述性分析取決於MRM。<br /> </td> 
  </tr> 
  <tr> 
   <td> 追蹤指標(operationFeedback)<br /> </td> 
   <td> 關鍵追蹤指標的概觀：開啟、點按和交易，取決於促銷活動。<br /> </td> 
  </tr> 
  <tr> 
   <td> 共用至社交網路(operationForward)<br /> </td> 
   <td> 共用活動和郵件開啟統計資料，取決於促銷活動。<br /> </td> 
  </tr> 
  <tr> 
   <td> 假設報表(operationHexposition)<br /> </td> 
   <td> 根據促銷活動顯示促銷活動傳送的假設測量摘要。<br /> </td> 
  </tr> 
  <tr> 
   <td> 共用活動統計資料(forwardActivityOpt)<br /> </td> 
   <td> 依據Campaign分析每個時段的共用活動、開啟次數和訂閱次數。<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳送摘要(operationStatistics)<br /> </td> 
   <td> 促銷活動傳送的摘要圖表：已傳送目標、排除和訊息。<br /> </td> 
  </tr> 
  <tr> 
   <td> URL和點按輸送量(operationTopUrlDelivery)<br /> </td> 
   <td> 大部分的反應式URL和相關的點按資料流取決於Campaign。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 服務報告 {#reports-on-services}

有關服務的報告涉及 **nms:service** 表格。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>標籤和內部名稱</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 粉絲贏取(socialUbcripationsByWebapp)<br /> </td> 
   <td> 哪些Web應用程式使潛在客戶獲得成功？ 取決於社交行銷附加元件。<br /> </td> 
  </tr> 
  <tr> 
   <td> 訂閱劃分(mobileAppDistribution)<br /> </td> 
   <td> 依行動應用程式頻道附加元件，劃分每個行動應用程式的作用中訂閱。<br /> </td> 
  </tr> 
  <tr> 
   <td> 訂閱追蹤(subscriptionsProgress)<br /> </td> 
   <td> 資訊服務訂閱的演變<br /> </td> 
  </tr> 
  <tr> 
   <td> 反應率(socialReactionRate)<br /> </td> 
   <td> 最新傳送的再活動率為何？ 取決於社交行銷附加元件。<br /> </td> 
  </tr> 
  <tr> 
   <td> 反應率(mobileAppReciblyRate)<br /> </td> 
   <td> 最新傳送的再活動率取決於行動應用程式通道附加元件。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 預算報表 {#budget-reports}

Adobe Campaign提供的內建報表位於下表。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>標籤和內部名稱</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
   <td> <strong>結構描述</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 與方案有關的費用（預算方案費用）<br /> </td> 
   <td> 方案費用細目。<br /> </td> 
   <td> nms:program<br /> </td> 
  </tr> 
  <tr> 
   <td> 預算演變(budgetEvolution)<br /> </td> 
   <td> 按承諾水準開列的預算費用演變。<br /> </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
  <tr> 
   <td> 預算的累積演變(budgetCumulativeEvolution)<br /> </td> 
   <td> 按預算細分的累積預算費用的演變<br /> 部門級別。 </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
  <tr> 
   <td> 探索成本行(budgetExplorerBudget)<br /> </td> 
   <td> 成本行的描述性分析。<br /> </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
  <tr> 
   <td> 探索成本行(budgetExplorer)<br /> </td> 
   <td> 成本行的描述性分析。<br /> </td> 
   <td> nms:costLine<br /> </td> 
  </tr> 
  <tr> 
   <td> 探索成本行(budgetExplorerPlan)<br /> </td> 
   <td> 成本行的描述性分析。<br /> </td> 
   <td> nms:plan<br /> </td> 
  </tr> 
  <tr> 
   <td> 探索成本行(budgetExplorerProgram)<br /> </td> 
   <td> 成本行的描述性分析。<br /> </td> 
   <td> nms:program<br /> </td> 
  </tr> 
  <tr> 
   <td> 預算（預算）匯總<br /> </td> 
   <td> 主要成本、支出類別和預算的快照。<br /> </td> 
   <td> nms:budget<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 模擬報告 {#reports-on-simulations}

模擬報表與 **nms：模擬** 表格。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>標籤和內部名稱</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 模擬排除的詳細資訊(dlvSimuLossDetail)<br /> </td> 
   <td> 排除所有原因的詳細表格。<br /> </td> 
  </tr> 
  <tr> 
   <td> 依排名劃分優惠方案(offerSimulationRanking)<br /> </td> 
   <td> 模擬中選件的劃分（依排名）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 模擬摘要(dlvSimuLossSummary)<br /> </td> 
   <td> 模擬卷和排除的摘要。<br /> </td> 
  </tr> 
  <tr> 
   <td> 重疊統計(dlvSimuOverplaing)<br /> </td> 
   <td> 傳遞目標重疊卷。<br /> </td> 
  </tr> 
  <tr> 
   <td> 因模擬而排除的摘要(dlvSimuLossSimu)<br /> </td> 
   <td> 因模擬而排除的表格。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 網路應用程式報告 {#reports-on-web-applications}

Web應用程式報告與 **nms:WebApp** 表格。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>標籤和內部名稱</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 檔案(surveyDictionary)<br /> </td> 
   <td> 調查結構的說明取決於「調查管理員」附加元件。<br /> </td> 
  </tr> 
  <tr> 
   <td> 主要(surveyProperties)<br /> </td> 
   <td> 調查屬性<br /> </td> 
  </tr> 
  <tr> 
   <td> 回應的劃分(surveyDistribution)<br /> </td> 
   <td> 問題回應的劃分。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 其他ootb報告 {#other-ootb-reports}

也提供下列內建報表。 有關詳細資訊，請參閱相關功能的文檔。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>標籤和內部名稱</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
   <td> <strong>結構描述</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 優惠方案分析(offerAnalysis)<br /> </td> 
   <td> 根據日期和管道進行選件分析，取決於互動附加元件。<br /> </td> 
   <td> nms:offer<br /> </td> 
  </tr> 
  <tr> 
   <td> 再行銷效率（再行銷效果）<br /> </td> 
   <td> 再行銷效率的測量<br /> </td> 
   <td> nms:webEvent<br /> </td> 
  </tr> 
  <tr> 
   <td> 社交潛在客戶贏取歷史記錄(socialVisitorStatistics)<br /> </td> 
   <td> twitter和Facebook潛在客戶贏取的歷史，取決於Social行銷附加元件。<br /> </td> 
   <td> nms:visitor<br /> </td> 
  </tr> 
  <tr> 
   <td> 最近的主張跟蹤（最近的主張）<br /> </td> 
   <td> 即時主張追蹤<br /> </td> 
   <td> nms:positionRcp<br /> </td> 
  </tr> 
 </tbody> 
</table>
