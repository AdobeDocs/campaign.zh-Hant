---
product: campaign
title: 收件匣轉譯技術工作流程
description: 本節說明隨收件匣轉譯套件安裝的技術工作流程
feature: Workflows, Inbox Rendering
role: User, Admin
version: Campaign v8, Campaign Classic v7
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: c858a28b-ea19-49b0-8d48-828717fad89c
    internal-label: Prepare and test messages
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: 2317b1ea-6db4-58c7-851f-717a69c0f5c0
    internal-label: Inbox Rendering
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 3%
---

# 收件匣轉譯(IR){#inbox-rendering}



依預設，以下詳細的工作流程會與&#x200B;**收件匣轉譯(IR)**&#x200B;模組一併安裝。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>標籤</strong><br /> </td> 
   <td> <strong>內部名稱</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>更新收件匣轉譯的種子網路</strong><br /> </td> 
   <td> <span class="uicontrol">updateRenderingSeeds</span> <br /> </td> 
   <td> 此工作流程會更新用於收件匣轉譯的電子郵件地址，而且只有在<strong>deliverability.neolane.net</strong>.<br />的HTTPS連線埠開啟時才有效 </td> 
  </tr> 
 </tbody> 
</table>

