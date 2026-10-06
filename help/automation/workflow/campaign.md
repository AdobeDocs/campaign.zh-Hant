---
product: campaign
title: Campaign
description: Campaign
feature: Workflows
role: User, Admin
version: Campaign v8, Campaign Classic v7
topic-tags: technical-workflows
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
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
source-wordcount: '157'
ht-degree: 3%
---

# Campaign{#campaign}

依預設，以下詳細的工作流程會與&#x200B;**Campaign**&#x200B;模組一起安裝。

>[!CAUTION]
>
>為了在行銷活動層級執行行銷活動程式，必須啟動這些工作流程。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>標籤</strong><br /> </td> 
   <td> <strong>內部名稱</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">成本計算</span> <br /> </td> 
   <td> <span class="uicontrol">budgetMgt</span> <br /> </td> 
   <td> 此工作流程會開始計算預算、計畫、方案、行銷活動、傳遞和任務的費用與成本行。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">庫存：訂單與警示</span> <br /> </td> 
   <td> <span class="uicontrol">stockMgt</span> <br /> </td> 
   <td> 此工作流程會啟動訂單明細行的庫存計算，並管理警告警示臨界值。<br /> </td> 
  </tr> 
  <tr> 
   <td> 行銷活動中的傳遞<span class="uicontrol">工作</span> <br /> </td> 
   <td> <span class="uicontrol">deliveryMgt</span> <br /> </td> 
   <td> 此工作流程會觸發已核准的傳送，並開始為外部傳送對服務提供者進行後續處理。 它也會傳送核准通知與提醒。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">行銷活動工作</span> <br /> </td> 
   <td> <span class="uicontrol">operationMgt</span> <br /> </td> 
   <td> 此工作流程管理行銷活動的工作（啟動目標定位、檔案擷取等）。 也會建立與循環和週期性行銷活動相關的工作流程。<br /> </td> 
  </tr> 
  <tr> 
   <td> 服務提供者上的<span class="uicontrol">工作</span> <br /> </td> 
   <td> <span class="uicontrol">supplierMgt</span> <br /> </td> 
   <td> 在核准傳遞後，此工作流程會開始處理提供者（傳送至路由器的電子郵件並進行後續處理）。<br /> </td> 
  </tr> 
 </tbody> 
</table>

