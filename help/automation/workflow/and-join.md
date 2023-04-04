---
product: campaign
title: AND-join
description: AND-join
feature: Workflows
exl-id: c70a106d-3518-4eac-9944-6f7c93d85bac
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 5%

---

# AND-join{#and-join}



只有在啟動所有入站轉變（即完成所有先前的活動）時，連接才會觸發其出站轉變。 這可讓您在繼續執行工作流程之前，確定某些活動已完成。

例如，您可以在內容建立和傳送傳送自動化的內容中使用AND-join活動，以確保只有在目標查詢和內容更新步驟完成後，才會啟動傳送。 有專屬的使用案例可在

![](assets/and-join-usage.png)

>[!NOTE]
>
>請注意，使用不同目標維度設定的入站轉變無法使用 **[!UICONTROL AND-join]** 活動。

活動的出站已傳送母體，是透過在活動的入站轉變中選擇主要集來決定。

出站轉變只能包含入站轉變母體之一。 如果未設定活動，出站轉變將隨機選取入站母體之一。

>[!CAUTION]
>
>若 **合併連結** 類型活動時，會合併事件變數，但如果同一個變數定義兩次，則會發生衝突，且值仍未確定。 如需詳細資訊，請參閱[本章節](javascript-scripts-and-templates.md#event-variables)。
