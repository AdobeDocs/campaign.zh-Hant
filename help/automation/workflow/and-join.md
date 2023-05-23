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



僅當激活所有入站轉換（即當完成所有先前活動時）時，連接才會觸發其出站轉換。 這允許您確保在繼續執行工作流之前已完成某些活動。

例如，您可以在內容建立和傳遞發送自動化的上下文中使用與聯接活動，以確保只有目標查詢和內容更新步驟完成後才啟動傳遞。 在中提供了專用的使用案例

![](assets/and-join-usage.png)

>[!NOTE]
>
>請注意，配置了不同目標維的入站過渡無法使用 **[!UICONTROL AND-join]** 的子菜單。

通過在活動的入站轉換中選擇主集來確定活動的出站已發送人口。

出站轉換只能包含入站轉換總體之一。 如果未配置該活動，則出站轉換將隨機選擇一個入站總體。

>[!CAUTION]
>
>在 **與連接** 類型活動，將合併事件變數，但如果定義了兩次相同變數，則存在衝突，且值仍未確定。 如需詳細資訊，請參閱[本章節](javascript-scripts-and-templates.md#event-variables)。
