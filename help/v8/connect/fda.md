---
title: 使用Campaign和外部資料庫(FDA)
description: 了解如何使用Campaign和外部資料庫
feature: Federated Data Access
role: Data Engineer
level: Beginner
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: bb03c804c1c65322d275d0a2ca1db0bfe974636d
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 1%

---

# 同盟資料存取 (FDA){#gs-fda}

使用FDA連接器（同盟資料存取）將Campaign連線至一或多個 **外部資料庫** 和處理儲存在其中的資訊，而不會影響您的Campaign Cloud資料庫資料。 接著，您就可以存取外部資料，而不需變更Adobe Campaign資料的結構。

![](../assets/do-not-localize/speech.png)   作為托管Cloud Services用戶， [連絡Adobe](../start/campaign-faq.md#support) 使用Campaign實作Experience Cloud觸發程式。


>[!NOTE]
>
>* Federated Data Access的相容資料庫列於 [相容性矩陣](../start/compatibility-matrix.md).
>
>* 在 [企業(FFDA)部署](../architecture/enterprise-deployment.md)，特定外部帳戶可用於管理Campaign本機資料庫和Snowflake雲端資料庫之間的通訊。 此外部帳戶是依Adobe和 **不能** 修改。
>



## 最佳實務和限制

FDA選項受您所使用第三方資料庫系統的限制。

此外，請注意下列限制和最佳實務：

* FDA選項是用來在工作流程中以批次模式處理外部資料庫中的資料。 為避免效能問題，不建議在單一操作的情境下使用FDA模組，例如：個人化、互動、即時訊息傳送等。

* 請盡量避免同時使用Adobe Campaign和外部資料庫的操作。 若要這麼做，您可以：

   * 將Adobe Campaign資料庫匯出至外部資料庫，並在將結果重新匯入Adobe Campaign之前，僅從外部資料庫執行操作。

   * 從外部Adobe Campaign資料庫收集資料，並在本機執行操作。
   如果您想要使用外部資料庫的資料在傳送中進行個人化，請收集要在工作流程中使用的資料，以便在暫時表格中使用。 然後使用臨時表格中的資料來個人化您的傳送。 若要執行此作業，請使用 **[!UICONTROL Prepare the personalization data with a workflow]** 選項，可在 **[!UICONTROL Analysis]** 標籤。 在傳遞分析期間，此選項會自動建立並執行工作流程，該工作流程會將連結到目標的所有資料儲存在臨時表中，包括來自連結到外部資料庫的表的資料。

   >[!CAUTION]
   >
   >此選項可大幅改善執行個人化步驟時的效能。


## 在工作流程中使用外部資料

Campaign隨附數個工作流程活動，您可使用這些活動與來自外部資料庫的資料互動：

* **篩選外部資料**  — 使用 **[!UICONTROL Query]** 活動來新增外部資料，並在定義的篩選設定中使用它。

* **建立子集**  — 使用 **[!UICONTROL Split]** 建立子集的活動。 您可以使用外部資料來定義要使用的篩選條件。

* **載入外部資料庫**  — 在 **[!UICONTROL Data loading (RDBMS)]** 活動。

* **新增資訊和連結**  — 使用 **[!UICONTROL Enrichment]** 活動，將其他資料新增至工作流程的工作表，並連結至外部表格。 在此內容中，它可使用外部資料庫的資料。

您也可以針對暫時用途，從上列的所有工作流程活動直接定義外部資料庫的連線。 在此情況下，它將位於本機外部資料庫上，僅用於目前的工作流程。

>[!CAUTION]
>
>此類型的設定只能暫時用於收集資料。 任何其他用途均應偏好使用外部帳戶設定。

例如，在 **[!UICONTROL Query]** 活動，您可以定義外部資料庫的臨時連線，如下所示：

1. 開啟活動，然後按一下 **[!UICONTROL Add data...]**
1. 選取 **[!UICONTROL External data]** 選項
1. 選取 **[!UICONTROL Locally defining the data source]** 選項
1. 在下拉式清單中選取目標資料庫引擎。 輸入伺服器的名稱並提供驗證參數。 也指定外部資料庫的名稱。
1. 選擇資料儲存所在的表。 您可以直接在相應欄位中輸入表的名稱，或按一下編輯表徵圖以訪問資料庫表的清單。
1. 按一下 **[!UICONTROL Add]** 按鈕，在外部資料庫資料和Adobe Campaign資料庫中的資料之間定義一個或多個調解欄位。 此 **[!UICONTROL Edit expression]** 表徵圖 **[!UICONTROL Remote field]** 和 **[!UICONTROL Local field]** 可讓您存取每個表格的欄位清單。
1. 如有必要，請指定篩選條件和資料排序模式。
1. 選取要在外部資料庫中收集的其他資料。 若要這麼做，請連按兩下您要新增的欄位，以在 **[!UICONTROL Output columns]**.
1. 按一下 **[!UICONTROL Finish]** 確認此設定。
