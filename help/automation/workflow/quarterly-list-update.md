---
product: campaign
title: 使用增量查詢更新每季清單
description: 在此使用案例中，增量查詢用於自動更新收件者清單。
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: eedc796a-865f-47a8-8807-5980546b8adf
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 5%

---

# 使用增量查詢更新每季清單 {#quarterly-list-update}



在下列範例中，[增量查詢](incremental-query.md)用於自動更新收件者清單。 這些收件者是季節性行銷活動中的目標收件者。

由於這些行銷活動會在每個季初啟動，以提供相關的體育活動，因此這些清單會每季更新。 不過，此行銷活動僅能每9個月將收件者鎖定於此。 這可讓您找出收件者的資格頻率，並逐年提供不同季節的活動。

![](assets/incremental_query_example.png)

1. 將增量查詢和清單更新活動新增到新工作流程中。
1. 依照[建立查詢](query.md#creating-a-query)中指定的方式設定活動的&#x200B;**[!UICONTROL Incremental query]**&#x200B;索引標籤。
1. 選取「**[!UICONTROL Scheduling & History]**」標籤，然後指定270天的歷程記錄。 已設定目標的收件者在270天或大約9個月的期間內將不再設定目標。

   然後按一下&#x200B;**[!UICONTROL Change...]**&#x200B;按鈕。

1. 若要確保清單在每個季節開始之前更新，請選取&#x200B;**[!UICONTROL Monthly]**。
1. 在下一個畫面，選取3月、6月、9月和12月。 選擇當月20日，並選擇要啟動工作流程的時間。
1. 接著，選取查詢的有效期。 例如，如果您希望此活動永久啟用，請選取&#x200B;**[!UICONTROL Permanent validity]**。

1. 在核准增量查詢後，請依照[清單更新](list-update.md)中的說明來設定清單更新活動。

因此，工作流程將在每個季節開始前自動啟動。 清單會更新為符合資格的新收件者，以接收優惠。
