---
product: campaign
title: 篩選重複的收件者
description: 瞭解如何篩選重複的收件者
feature: Workflows
exl-id: cfa1f45c-e1ac-4055-996c-6e8d041889bb
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 4%

---

# 篩選重複的收件者 {#filtering-duplicated-recipients}



在此範例中，我們要篩選在傳送中出現兩次或更多次的收件者，以復原重複的設定檔。

若要建立此範例，請套用下列步驟：

1. 拖放 **[!UICONTROL Query]** 活動並開啟活動。
1. 按一下 **[!UICONTROL Edit query]** 並將目標和篩選維度設為 **[!UICONTROL Recipients]**.

   ![](assets/query_recipients_1.png)

1. 定義下列篩選條件，以定位存在於傳遞記錄的收件者。 選擇 **收件者傳遞記錄(broadlog)** 在 **運算式** 欄，選擇 **存在，例如** 在 **運運算元** 欄。

   ![](assets/query_recipients_2.png)

1. 定義下列篩選條件來鎖定您的傳送。 選擇 **[!UICONTROL Internal name]** 在「運算式」欄與 **[!UICONTROL equal to]** （在運運算元欄中）。
1. 在值欄中，新增目標傳送的內部名稱。

   ![](assets/query_recipients_3.png)

1. 使用 **[!UICONTROL AND]** 運運算元，重複相同的作業來鎖定其他傳送。

   ![](assets/query_recipients_4.png)

您的出站轉變包含傳遞中鎖定的重複收件者。
