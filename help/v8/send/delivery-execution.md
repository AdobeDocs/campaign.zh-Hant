---
title: 交易式訊息傳送執行
description: 進一步了解交易式訊息傳送執行和監控
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
source-git-commit: c61f03252c7cae72ba0426d6edcb839950267c0a
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 1%

---


# 傳遞執行 {#delivery-execution}

完成擴充並將傳送範本連結至事件後，即會從執行例項傳送傳送。

>[!NOTE]
>
>交易式訊息的優先順序高於任何其他傳送。

所有傳送都會分組於 **[!UICONTROL Administration > Production > Message Center > Default > Deliveries]** 檔案夾。

依預設，會依傳送月份排序為子資料夾。 可在訊息範本屬性中變更此排序。

## 交易式訊息監控 {#transactional-message-monitoring}

若要監視交易式訊息，請檢查 [傳遞記錄](send.md).

從執行例項傳送的交易式傳送會透過技術工作流程同步回控制例項(**[!UICONTROL Message Center execution instance]**)，每小時執行一次。

>[!NOTE]
>
>每週傳送會根據最新事件更新累積事件，而非根據事件建立日期。 因此，從控制例項擷取交易式訊息傳送記錄時，與每個傳送記錄ID相關聯的傳送ID可能會隨著記錄更新而隨時間變更（例如，當收到事件的入站退信時）。

<!--
To monitor the activity and running of the execution instance(s), see [Transactional messaging reports](transactional-messaging-reports.md).-->
