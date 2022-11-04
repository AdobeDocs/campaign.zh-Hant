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

以下詳細說明的工作流程會與 **優惠方案引擎（互動）** 預設為附加元件。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>標籤</strong><br /> </td> 
   <td> <strong>內部名稱</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">完整聚合計算（propositircp多維資料集）</span> <br /> </td> 
   <td> <span class="uicontrol">agg_nmspropositrcp_full</span> <br /> </td> 
   <td> 此工作流程會更新 <strong>完整</strong> 匯總 <strong>優惠方案主張</strong> 立方體。 預設會每天早上6點觸發。 此匯總會擷取下列維度：管道、傳送、行銷活動和日期。<br /> 此 <strong>優惠方案主張</strong> 然後，多維度資料集可用來根據選件產生報表。<br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">MessageCenter完整聚合計算</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> 此工作流程會更新 <strong>完整</strong> 匯總 <strong>訊息中心</strong> 立方體。 預設會每天凌晨3:00觸發。 此匯總會擷取下列維度：管道、日期、狀態和事件類型。<br /> 此 <strong>訊息中心</strong> 然後，多維資料集可用來根據事件產生報表。 <br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

進一步了解中的立方體和匯總 [本節](../../v8/reporting/gs-cubes.md).

