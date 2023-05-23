---
product: campaign
title: 互動
description: 互動
feature: Workflows, Interaction
source-git-commit: 8d9b8d3e31362c2d69ec0fc6f16ab375538d7f10
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 5%

---


# 互動{#interaction}

下面詳細介紹的工作流隨 **提供引擎（交互）** 預設情況下為載入項。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>標籤</strong><br /> </td> 
   <td> <strong>內部名稱</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">完全聚合計算（propositionrcp多維資料集）</span> <br /> </td> 
   <td> <span class="uicontrol">agg_nmspropositionrcp_full</span> <br /> </td> 
   <td> 此工作流更新 <strong>滿</strong> 聚合 <strong>提供建議</strong> 立方。 預設情況下，每天早上6點觸發。 此聚合捕獲以下維：渠道、交付、營銷優惠和日期。<br /> 的 <strong>提供建議</strong> 然後，使用cube根據優惠生成報告。<br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">MessageCenter完整聚合計算</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> 此工作流更新 <strong>滿</strong> 聚合 <strong>消息中心</strong> 立方。 預設情況下，每天凌晨3點觸發。 此聚合捕獲以下維：渠道、日期、狀態和事件類型。<br /> 的 <strong>消息中心</strong> 然後，使用cube根據事件生成報告。 <br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

瞭解有關中的立方和聚合的詳細資訊 [此部分](../../v8/reporting/gs-cubes.md)。

