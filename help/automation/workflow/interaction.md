---
product: campaign
title: 互動
description: 互動
feature: Workflows, Interaction
role: User, Admin
version: Campaign v8, Campaign Classic v7
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '132'
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
   <td> 此工作流程會更新<strong>優惠方案主張</strong> Cube的<strong>完整</strong>彙總。 預設會每天早上6:00觸發。 此彙總會擷取下列維度：管道、傳遞、行銷優惠和日期。<br /> 接著會使用<strong>優惠方案主張</strong> Cube來根據優惠方案產生報表。<br /> </td> 
  </tr> 
   <tr> 
   <td> <span class="uicontrol">MessageCenter完整彙總計算</span> <br /> </td> 
   <td> <span class="uicontrol">agg_messageCenter_full</span> <br /> </td> 
   <td> 此工作流程會更新<strong>訊息中心</strong> Cube的<strong>完整</strong>彙總。 預設會每天凌晨3:00觸發。 此彙總會擷取下列維度：管道、日期、狀態和事件型別。<br /> 接著會使用<strong>訊息中心</strong> Cube來根據事件產生報表。<br /> </td> 
   <td> <br /> </td> 
  </tr> 
 </tbody> 
</table>

在[本節](../../v8/reporting/gs-cubes.md)中進一步瞭解多維度資料集與彙總。

