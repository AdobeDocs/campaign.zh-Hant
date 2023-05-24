---
product: campaign
title: 訊息中心（控制）
description: 訊息中心（控制）
feature: Workflows
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 10%

---


# 訊息中心（控制）{#message-center-control}

以下詳細的工作流程已排程每小時執行一次。 它隨附於 **訊息中心 — 控制項** 模組（預設）。


<table> 
 <tbody> 
  <tr> 
   <td> <strong>標籤</strong><br /> </td> 
   <td> <strong>內部名稱</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 訊息中心 &lt;external_account_name&gt;<br /> </td> 
   <td> mcSynch_&lt;external_account_name&gt;<br /> </td> 
   <td> 此工作流程：<br /> 
    <ul> 
     <li> <p>恢復作業處理的事件清單。</p> </li> 
     <li> <p>與NmsBroadLogMsg表格同步，以復原傳遞訊息資格。</p> </li> 
     <li> <p>與NmsBroadLogMsg表同步完成後，立即復原事件傳送記錄檔。</p> </li> 
     <li> <p>與NmsTrackingUrl表格同步，以復原傳遞URL的追蹤。</p> </li> 
     <li> <p>與NmsTrackingUrl表同步完成後，立即復原事件追蹤URL。</p> </li> 
     <li> <p>可讓您在傳送後，每三小時復原一次所有置於隔離的電子郵件地址。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

