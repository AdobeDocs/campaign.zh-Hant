---
product: campaign
title: 測試
description: 進一步瞭解測試工作流程活動
feature: Workflows
version: Campaign v8, Campaign Classic v7
exl-id: 0d4d13f6-7128-44d3-ad5c-4ed02257ee64
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 1%

---

# 測試{#test}



**Test**&#x200B;型別活動會啟動滿足與其相關的條件的第一個轉變。 如果未滿足任何條件，且已啟動&#x200B;**[!UICONTROL Use the default fork]**&#x200B;選項，則將啟動預設轉變。

條件是JavaScript運算式，必須評估為「true」或「false」。 若要輸入運算式，請按一下條件名稱右邊的圖示，然後選取&#x200B;**[!UICONTROL Edit...]**。

![](assets/edit_test.png)

如需透過工作流程JavaScript存取之應用程式伺服器的所有其他JavaScript函式和SOAP方法的詳細資訊，請參閱[JSAPI檔案](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=zh-Hant){target="_blank"}。

您也可以從此編輯器直接插入變數。 有關如何使用變數的詳細資訊，請參閱[本節](javascript-scripts-and-templates.md#variables)。

可以從活動屬性編輯視窗中新增、刪除或排序條件，也可以從轉變中修改條件。

如果計算的結果由不同的條件重複使用，則可以在活動的初始化指令碼中計算它。 結果必須儲存在任務的變數中，才能由條件指令碼(task.vars.xxx)存取。
