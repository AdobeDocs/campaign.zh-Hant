---
product: campaign
title: 中間來源平台
description: 中間來源平台
feature: Workflows
role: User
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
source-git-commit: 8a7bf8408d15e0bd9e1c3e72f7846bf9a79c6885
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 1%
---

# 中間來源平台{#mid-sourcing-platform}



依預設，以下詳細描述的工作流程會與&#x200B;**中間來源平台**&#x200B;模組一起安裝。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>標籤</strong><br /> </td> 
   <td> <strong>內部名稱</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">傳遞指標</span> <br /> </td> 
   <td> <span class="uicontrol">deliveryIndicator</span> <br /> </td> 
   <td> 此工作流程會更新傳送的傳送追蹤指標。 此工作流程預設每小時觸發一次。<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>中間來源伺服器上的記錄保留期間必須長於傳遞有效期間加上&#x200B;**indicatorsDuration**&#x200B;值。 否則，在清除舊記錄檔時，傳送指標會降低，而較低的值會同步至行銷執行個體。 例如，如果有效期間為5天，而&#x200B;**indicatorsDuration**&#x200B;為30天，請將保留期間設定為至少36天。
