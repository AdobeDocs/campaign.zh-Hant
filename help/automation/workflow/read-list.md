---
product: campaign
title: 讀取清單
description: 進一步了解讀取清單工作流程活動
feature: Workflows, Targeting Activity
role: User, Data Engineer
version: Campaign v8, Campaign Classic v7
exl-id: 91c87f8f-bdd2-4ca1-94c2-ec9e7affc1a0
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 0%

---

# 讀取清單{#read-list}

在工作流程中處理的資料可能來自已預先準備資料或將其結構化的清單（在先前的細分或檔案上傳後）。

**[!UICONTROL Read list]**&#x200B;活動可讓您從工作流程工作表格的清單複製資料，例如來自查詢的資料。 然後即可在整個工作流程中存取。

要處理的清單可依據選取的選項和&#x200B;**[!UICONTROL Read list]**&#x200B;活動中定義的引數，明確指定、由指令碼計算或動態本地化。

![](assets/list_edit_select_option_01.png)

如果未明確指定清單，您必須提供清單作為範本，以找出其結構。

![](assets/s_advuser_list_template_select.png)

設定清單選擇後，您可以使用&#x200B;**[!UICONTROL Edit query]**&#x200B;選項新增篩選器，以保留母體的一部分，以供下一個工作流程使用。

![](assets/wf_readlist_1.png)

>[!CAUTION]
>
>若要在讀取清單活動中建立篩選器，相關清單必須是「檔案」型別。

您可以透過首頁的&#x200B;**[!UICONTROL Profiles and Targets > Lists]**&#x200B;連結，直接在Adobe Campaign中建立清單。 您也可以在工作流程中使用&#x200B;**[!UICONTROL List update]**&#x200B;活動來建立它們。

**範例：排除傳送位址清單**

下列範例可讓您使用要排除在電子郵件傳遞目標之外的電子郵件地址清單。

![](assets/s_advuser_list_read_sample_1.png)

**新連絡人**&#x200B;資料夾中包含的設定檔必須透過傳遞動作定位。 要從目標中排除的電子郵件地址會儲存在外部清單中。 在我們的範例中，排除只需要電子郵件地址的資訊。

1. **新連絡人**&#x200B;資料夾選擇查詢必須讓您載入選取的設定檔電子郵件地址，才能與清單中的資訊對齊。

   ![](assets/s_advuser_list_read_sample_0.png)

1. 在此處，清單儲存在&#x200B;**清單**&#x200B;資料夾中，並計算其標籤。

   ![](assets/s_advuser_list_read_sample_2.png)

1. 為了從主要目標排除外部清單的電子郵件地址，您必須設定排除活動，並指定&#x200B;**新連絡人**&#x200B;資料夾包含要保留的資料。 此集和排除活動之任何其他入站集之間的聯合資料將從目標中刪除。

   ![](assets/s_advuser_list_read_sample_3.png)

   排除規則是在編輯工具的中央區段中設定。 按一下&#x200B;**[!UICONTROL Add]**&#x200B;按鈕以定義要套用的排除型別。

   您可以根據活動的傳入轉變數來定義數個排除專案。

1. 在&#x200B;**[!UICONTROL Exclusion set]**&#x200B;欄位中，選取&#x200B;**[!UICONTROL Read list]**&#x200B;活動：此活動中的資料將從主要集中排除。

   在我們的範例中，聯結上有排除專案：清單中包含的資料將透過包含電子郵件地址的欄位，與主要集的資料進行調解。 若要設定加入，請在&#x200B;**[!UICONTROL Change dimension]**&#x200B;欄位中選取&#x200B;**[!UICONTROL Joins]**。

   ![](assets/s_advuser_list_read_sample_4.png)

1. 然後選取與兩組中(Source和目的地)的電子郵件地址相對應的欄位。 然後會連結欄，而且其電子郵件地址在匯入地址清單中的收件者將從目標中排除。
