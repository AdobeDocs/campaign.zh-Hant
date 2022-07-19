---
product: campaign
title: 訊息中心（控制）
description: 訊息中心（控制）
feature: Workflows
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 8%

---


# 訊息中心（控制）{#message-center-control}

下面詳述的工作流計畫每小時運行一次。 它隨 **消息中心 — 控制項** 預設情況下為模組。


<table> 
 <tbody> 
  <tr> 
   <td> <strong>標籤</strong><br /> </td> 
   <td> <strong>內部名稱</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> 消息中心 &lt;external_account_name&gt;<br /> </td> 
   <td> mcSynch_&lt;external_account_name&gt;<br /> </td> 
   <td> 此工作流：<br /> 
    <ul> 
     <li> <p>恢復由操作處理的事件清單。</p> </li> 
     <li> <p>與NmsBroadLogMsg表同步以恢復傳遞消息資格。</p> </li> 
     <li> <p>與NmsBroadLogMsg表的同步完成後，立即恢復事件傳遞日誌。</p> </li> 
     <li> <p>與NmsTrackingUrl表同步以恢復傳遞URL的跟蹤。</p> </li> 
     <li> <p>在完成與NmsTrackingUrl表的同步後，立即恢復事件跟蹤URL。</p> </li> 
     <li> <p>允許您在發送交貨後每三小時恢復隔離的所有電子郵件地址。</p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

