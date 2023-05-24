---
product: campaign
title: 訊息中心（執行）
description: 訊息中心（執行）
feature: Workflows
source-git-commit: 8d9b8d3e31362c2d69ec0fc6f16ab375538d7f10
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 8%

---


# 訊息中心（執行）{#message-center-execution}

以下詳述的工作流程會隨 **訊息中心 — 執行** 預設為附加元件。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>標籤</strong><br /> </td> 
   <td> <strong>內部名稱</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">更新事件狀態</span> <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span> <br /> </td> 
   <td> 此工作流程可讓您為事件指派狀態。 事件狀態如下：<br /> 
    <ul> 
     <li> <p><strong>擱置中</strong>：事件位於佇列中。 尚未為其建立任何訊息範本的關聯。</p> </li> 
     <li> <p><strong>待處理的傳遞</strong>：事件位於佇列中，訊息範本已與其建立關聯，且傳遞目前正在處理中。</p> </li> 
     <li> <p><strong>已傳送</strong>：此狀態是從傳送記錄檔複製而來。 這表示傳遞已傳送。</p> </li> 
     <li> <p><strong>已被傳遞忽略</strong>：此狀態是從傳送記錄檔複製而來。 這表示已忽略傳遞。</p> </li> 
     <li> <p><strong>傳遞錯誤</strong>：此狀態是從傳送記錄檔複製而來。 這表示傳送失敗。</p> </li> 
     <li> <p><strong>未涵蓋的事件</strong>：此事件無法與訊息範本建立關聯。 將不會重新處理事件。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">處理批次事件</span> <br /> </td> 
   <td> <span class="uicontrol">batchEventsProcessing</span> <br /> </td> 
   <td> 此工作流程可讓您在將批次事件與訊息範本產生關聯之前，先將批次事件放入佇列中。 <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">處理即時事件</span> <br /> </td> 
   <td> <span class="uicontrol">rtEventsProcessing</span> <br /> </td> 
   <td> 此工作流程可讓您在將即時事件與訊息範本產生關聯之前，先將其放入佇列中。 <br /> </td> 
  </tr> 
 </tbody> 
</table>

