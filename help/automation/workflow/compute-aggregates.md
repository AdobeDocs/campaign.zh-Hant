---
product: campaign
title: 執行彙總計算
description: 瞭解如何在查詢中執行彙總計算
feature: Workflows
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 00e564b5-3c8e-45d4-b240-c872a8b8ccb6
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 0%

---

# 執行彙總計算 {#performing-aggregate-computing}

在此範例中，我們要根據性別計算生活在倫敦的收件者人數。

* 需要選取哪個表格？

  收件者資料表(**nms：recipient**)

* 在輸出欄中應該選取哪些欄位？

  主索引鍵（含計數）和性別

* 篩選資訊所根據的條件為何？

  根據居住在倫敦的收件者

若要建立此範例，請套用下列步驟：

1. 在&#x200B;**[!UICONTROL Data to extract]**&#x200B;中，定義主索引鍵的計數（如上一個範例所示）。 在輸出欄中新增&#x200B;**[!UICONTROL Gender]**&#x200B;欄位。 檢查&#x200B;**[!UICONTROL Gender]**&#x200B;欄中的&#x200B;**[!UICONTROL Group]**&#x200B;選項。 如此一來，收件者就會依性別分組。

   ![](assets/query_editor_nveau_27.png)

1. 在&#x200B;**[!UICONTROL Sorting]**&#x200B;視窗中，按一下&#x200B;**[!UICONTROL Next]**：這裡不需要排序。
1. 設定資料篩選。 在此，您要將選取範圍限製為住在倫敦的聯絡人。

   ![](assets/query_editor_22.png)

   >[!NOTE]
   >
   >值區分大小寫。 如果&#39;London&#39;值是在沒有大寫字母的條件中輸入，且收件者清單包含單字「London」及大寫字母，則查詢將會失敗。

1. 在&#x200B;**[!UICONTROL Data formatting]**&#x200B;視窗中，按一下&#x200B;**[!UICONTROL Next]**：此範例不需要格式化。
1. 在預覽視窗中，按一下&#x200B;**[!UICONTROL Launch data preview]**。

   依性別區分的每種排序有三個不同的值：女性為&#x200B;**2**，男性為&#x200B;**1**，性別不明時為&#x200B;**0**。 在此範例中，該清單包含10名女性、16名男性和2名性別不明的個人。

   ![](assets/query_editor_agregat_04.png)
