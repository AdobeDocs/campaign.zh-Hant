---
product: campaign
title: 合併連結
description: 合併連結
feature: Workflows
role: User
exl-id: c70a106d-3518-4eac-9944-6f7c93d85bac
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 21%

---

# 合併連結{#and-join}



只有當所有入站轉變啟動時（即所有先前的活動都完成時），聯結才會觸發其出站轉變。 這讓您可以在確保特定活動已完成後再繼續執行工作流程。

例如，您可以在內容建立和傳遞傳送自動化的內容中使用AND-join活動，以確保只有在完成目標查詢和內容更新步驟後才會開始傳遞。 以下位置提供了專屬的使用案例：

![](assets/and-join-usage.png)

>[!NOTE]
>
>請注意，使用不同目標維度設定的入站轉變，不能使用 **[!UICONTROL AND-join]** 活動。

活動的傳出已傳送母體是透過在活動的入站轉變中選擇主集來決定。

傳出轉變只能包含其中一個傳入轉變母體。如果未設定活動，出站轉變將會隨機選取其中一個入站母體。

>[!CAUTION]
>
>若為 **合併連結** 輸入活動，事件變數會合併，但如果相同的變數定義兩次，則會發生衝突，且值維持未定。 如需詳細資訊，請參閱[本章節](javascript-scripts-and-templates.md#event-variables)。
