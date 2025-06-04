---
product: campaign
title: 內容管理
description: 內容管理
feature: Workflows, Data Management
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 9b225f78-1959-4e4f-aa4e-ff8a63051154
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 2%

---

# 內容管理{#content-management}

**內容管理**&#x200B;活動可讓您建立和操作內容，並根據此內容產生檔案。 然後可以透過「傳送」活動傳遞此內容。

>[!CAUTION]
>
>內容管理是選用的Adobe Campaign模組。 請檢查您的授權合約。

>[!NOTE]
>
>Adobe Campaign Web使用者介面可讓您將內容片段用於內容。 它可讓行銷使用者預先建立多個自訂內容區塊，這要歸功於可在一或多個訊息中參考的可重複使用元件，好讓您在改良的設計程式中快速組合訊息內容。 若要深入瞭解內容片段，請參閱[Adobe Campaign Web UI檔案。](https://experienceleague.adobe.com/en/docs/campaign-web/v8/content/manage-reusable-content/fragments/fragments){target=_blank}

活動的屬性分為三個步驟：

* **內容選擇**：內容可以先前建立，也可以透過活動建立。
* **內容更新**：工作可以修改內容的主體或匯入所有XML內容。
* **動作**：可以儲存或產生產生的內容。

  ![](assets/content_mgmt_edit.png)

1. **內容**

   * **[!UICONTROL Specified in the transition]**

     此選項可讓您使用轉變中指定的內容，即啟用內容管理的事件必須包含&#x200B;**[!UICONTROL contentId]**&#x200B;變數。 此變數可由先前的內容管理或任何指令碼設定。

   * **[!UICONTROL Explicit]**

     此選項可讓您透過&#x200B;**[!UICONTROL Content]**&#x200B;欄位選取已建立的內容。 只有在選取&#x200B;**[!UICONTROL Explicit]**&#x200B;選項時，才會顯示此欄位。

     ![](assets/content_mgmt_explicit.png)

   * **[!UICONTROL Calculated by a script]**

     內容識別碼由指令碼計算。 **[!UICONTROL Script]**&#x200B;欄位可讓您定義評估內容識別碼（主索引鍵）的JavaScript範本。 只有在選取&#x200B;**[!UICONTROL Calculated by a script]**&#x200B;選項時，才會顯示此欄位。

     ![](assets/content_mgmt_script.png)

   * **[!UICONTROL New, created from a publication template]**

     從出版物範本建立新內容。 此新內容將儲存在&#x200B;**[!UICONTROL String]**&#x200B;欄位中指定的檔案中。 **[!UICONTROL Template]**&#x200B;欄位指定要用來建立內容的發佈範本。

     ![](assets/content_mgmt_new.png)

1. **更新內容**

   * **[!UICONTROL Subject]**

     此欄位可讓您修改內容的主旨。

   * **[!UICONTROL Access to data from an XML feed]**

     此選項可讓您從透過XSL樣式表下載的XML檔案建構內容。 選取此選項時，**[!UICONTROL URL]**&#x200B;欄位會指定XML內容下載URL。 **[!UICONTROL XSL stylesheet]**&#x200B;可讓您指定要用來轉換下載的XML檔案的樣式表。 此屬性是選用的。

     ![](assets/content_mgmt_xmlcontent.png)

1. **要執行的動作**

   * **[!UICONTROL Save]**

     此選項會儲存已建立或已修改的內容。

     出站轉變只會啟動一次，而且內容會儲存到&#x200B;**[!UICONTROL contentId]**&#x200B;變數中作為引數。

   * **[!UICONTROL Generate]**

     此選項會儲存內容，然後為具有「檔案」型別發佈的每個轉換範本產生輸出檔案。

     ![](assets/content_mgmt_generate.png)

     已針對每個以儲存於&#x200B;**[!UICONTROL contentId]**&#x200B;變數中的內容識別碼作為其引數以及&#x200B;**[!UICONTROL filename]**&#x200B;變數中的檔案名稱所產生的檔案啟動出站轉變。

## 輸入引數 {#input-parameters}

* contentId

**[!UICONTROL Specified in the transition]**&#x200B;選項啟用時要使用的內容識別碼。

## 輸出引數 {#output-parameters}

* contentId

  內容識別碼。

* 檔案名稱

  如果選取的動作是&#x200B;**[!UICONTROL Generate]**，則為產生檔案的完整名稱。
