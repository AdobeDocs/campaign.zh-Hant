---
product: campaign
title: LINE 頻道
description: LINE 頻道
feature: Workflows
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '95'
ht-degree: 13%

---


# LINE 頻道{#line-channel}

以下詳細說明的工作流程會與 **LINE頻道** 模組。 有關此模組的詳細資訊，請參閱 [本頁](../../v8/send/line.md).

<table> 
 <tbody> 
  <tr> 
   <td> <strong>標籤</strong><br /> </td> 
   <td> <strong>內部名稱</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">LINE V2存取權杖更新</span> <br /> </td> 
   <td> <span class="uicontrol">updateLineV2AccessToken</span> <br /> </td> 
   <td> 此工作流程會將存取權杖重新整理為LINE V2。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">刪除阻止的LINE用戶</span> <br /> </td> 
   <td> <span class="uicontrol">deleteBlockedLineUsersV2</span> <br /> </td> 
   <td> 此工作流確保在LINE V2用戶180天內阻止LINE官方帳戶後刪除其資料。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">MID到LineUserID移轉</span> <br /> </td> 
   <td> <span class="uicontrol">MIDoUserIDMigration</span> <br /> </td> 
   <td> 此工作流將生成LINE V2用戶的ID，以便從LINE V1遷移到LINE V2。<br /> </td> 
  </tr> 
 </tbody> 
</table>

