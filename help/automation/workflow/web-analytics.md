---
product: campaign
title: 網站分析
description: 進一步瞭解網站分析套件
feature: Workflows, Analytics Integration
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 13%

---


# 網站分析{#web-analytics}



以下詳述的工作流程會隨 **網站分析聯結器** 模組（預設）。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>標籤</strong><br /> </td> 
   <td> <strong>內部名稱</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">指標和行銷活動屬性的傳送</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsSendMetrics</span> <br /> </td> 
   <td> 此工作流程可讓您透過Adobe® Analytics聯結器，從Adobe Campaign傳送電子郵件行銷活動指標至Adobe Experience Cloud套裝。 相關指標如下： <strong>已傳送</strong> （已傳送）， <strong>開啟次數總計</strong> (iTotalRecipientOpen)， <strong>已點按的收件者總數</strong> (iTotalRecipientClick)， <strong>錯誤</strong> (iError)， <strong>選擇退出</strong> （選擇退出） (iOptOut)。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">已轉換聯絡人的識別</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsFindConverted</span> <br /> </td> 
   <td> 此工作流程會針對在再次行銷活動後完成購買的網站訪客建立索引。 此工作流程復原的資料可在以下位置存取： <span class="uicontrol">再行銷效率報表</span> （請參閱此）。 <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">事件清除</span><br /> </td> 
   <td> <span class="uicontrol">webAnalyticsPurgeWebEvents</span> <br /> </td> 
   <td> 此工作流程可讓您根據中設定的期間，從資料庫欄位中刪除每個事件 <span class="uicontrol">有效期限</span> 欄位。 <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">網頁事件的復原</span> <br /> </td> 
   <td> <span class="uicontrol">webAnalyticsGetWebEvents</span> <br /> </td> 
   <td> 每小時，此工作流程會下載指定網站之網際網路使用者行為的區段，將其放入Adobe Campaign資料庫並啟動再次行銷工作流程。 <br /> </td> 
  </tr> 
 </tbody> 
</table>

