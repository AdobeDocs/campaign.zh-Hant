---
product: campaign
title: 互動
description: 互動
feature: Workflows, Interaction
role: User, Admin
version: Campaign v8, Campaign Classic v7
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 3%

---


# 互動{#interaction}

依預設，下面詳細描述的工作流程會與&#x200B;**優惠方案引擎（互動）**&#x200B;附加元件一起安裝。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>標籤</strong><br /> </td> 
   <td> <strong>內部名稱</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">完整彙總計算(propositionrcp cube)</span> <br /> </td> 
   <td> <span class="uicontrol">agg_nmspropositionrcp_full</span> <br /> </td> 
   <td> 此工作流程會更新<strong>優惠方案主張</strong> Cube的<strong>完整</strong>彙總。 預設會每天早上6:00觸發。 此彙總會擷取下列維度：管道、傳送、行銷優惠和日期。<br /> <strong>優惠方案主張</strong> Cube隨後用於根據優惠方案產生報告。<br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">MessageCenter完整彙總計算</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> 此工作流程會更新<strong>訊息中心</strong> Cube的<strong>完整</strong>彙總。 預設會每天凌晨3:00觸發。 此彙總會擷取下列維度：管道、日期、狀態和事件型別。<br /> <strong>訊息中心</strong> Cube隨後用於根據事件產生報告。<br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

在[本節](../../v8/reporting/gs-cubes.md)中進一步瞭解多維度資料集與彙總。

