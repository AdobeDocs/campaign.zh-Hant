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

下面詳細介紹的工作流隨 **消息中心 — 執行** 預設情況下為載入項。

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
   <td> 此工作流允許您為事件分配狀態。 事件狀態如下：<br /> 
    <ul> 
     <li> <p><strong>待定</strong>:事件在隊列中。 尚未將郵件模板與其關聯。</p> </li> 
     <li> <p><strong>等待交貨</strong>:該事件在隊列中，消息模板已與其關聯，並且當前正由傳遞處理。</p> </li> 
     <li> <p><strong>已發送</strong>:此狀態從交貨日誌中複製。 這意味著送貨已經寄出。</p> </li> 
     <li> <p><strong>被傳遞忽略</strong>:此狀態從交貨日誌中複製。 這意味著傳遞被忽略。</p> </li> 
     <li> <p><strong>傳遞錯誤</strong>:此狀態從交貨日誌中複製。 這意味著交貨失敗。</p> </li> 
     <li> <p><strong>未涵蓋的事件</strong>:事件未能與消息模板關聯。 將不再處理該事件。</p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">處理批處理事件</span> <br /> </td> 
   <td> <span class="uicontrol">batchEventsProcessing</span> <br /> </td> 
   <td> 通過此工作流，您可以在將批處理事件與消息模板關聯之前，將它們放入隊列。 <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">處理即時事件</span> <br /> </td> 
   <td> <span class="uicontrol">rtEventsProcessing</span> <br /> </td> 
   <td> 通過此工作流，您可以在將即時事件與消息模板關聯之前，將它們放入隊列。 <br /> </td> 
  </tr> 
 </tbody> 
</table>

