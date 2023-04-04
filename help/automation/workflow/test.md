---
product: campaign
title: 測試
description: 進一步了解測試工作流程活動
feature: Workflows
exl-id: 0d4d13f6-7128-44d3-ad5c-4ed02257ee64
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 4%

---

# 測試{#test}



A **測試** 類型活動會啟動滿足與其相關的條件的第一個轉變。 若未滿足任何條件，且 **[!UICONTROL Use the default fork]** 選項，則會啟動預設轉變。

條件是必須評估為「true」或「false」的JavaScript運算式。 若要輸入運算式，請按一下條件名稱右側的圖示，然後選取 **[!UICONTROL Edit...]**.

![](assets/edit_test.png)

如需可透過工作流程JavaScript存取之應用程式伺服器的所有其他JavaScript函式和SOAP方法的詳細資訊，請參閱 [JSAPI檔案](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=zh-Hant).

您也可以直接從此編輯器插入變數。 如需如何使用變數的詳細資訊，請參閱 [本節](javascript-scripts-and-templates.md#variables).

您可以從活動屬性編輯視窗新增、刪除或排序條件，也可以從轉變中修改條件。

如果計算結果要被不同條件重複使用，則可以在活動的初始化指令碼中計算它。 結果必須儲存在要由條件指令碼(task.vars.xxx)存取之任務的變數中。
