---
title: 使用Campaign和外部資料庫(FDA)
description: 瞭解如何使用Campaign和外部資料庫
feature: Federated Data Access
role: Admin
level: Beginner
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 1%

---

# 同盟資料存取 (FDA){#gs-fda}

使用FDA聯結器（同盟資料存取）將Campaign連線至一或多個&#x200B;**外部資料庫**，並處理儲存在這些資料庫中的資訊，而不會影響您的Campaign雲端資料庫資料。 之後，您就可以存取外部資料，而不需變更Adobe Campaign資料的結構。

>[!NOTE]
>
>* 同盟資料存取的相容資料庫列於[相容性矩陣](../start/compatibility-matrix.md)。
>
>* 在[企業(FFDA)部署](../architecture/enterprise-deployment.md)的內容中，有特定的外部帳戶可用來管理Campaign本機資料庫與Snowflake雲端資料庫之間的通訊。 此外部帳戶是依Adobe為您設定的，**不得**&#x200B;修改。
>
>* 作為Managed Cloud Service使用者，[請連絡Adobe](../start/campaign-faq.md#support)以連線外部資料庫與Campaign。


## 最佳實務和限制

FDA選項受您使用的協力廠商資料庫系統限制。

此外，請注意下列限制和最佳作法：

* FDA選項可用於在工作流程中以批次模式操控外部資料庫中的資料。 為了避免效能問題，不建議在單一操作的內容中使用FDA模組，例如：個人化、互動、即時傳訊等。

* 儘可能避免需要使用Adobe Campaign和外部資料庫的操作。 若要這麼做，您可以：

   * 將Adobe Campaign資料庫匯出至外部資料庫，並僅從外部資料庫執行操作，然後再將結果重新匯入Adobe Campaign。

   * 從外部Adobe Campaign資料庫收集資料，並在本機執行操作。

  如果您想使用外部資料庫中的資料在傳遞中執行個人化，請收集要在工作流程中使用的資料，以便在臨時表格中提供。 然後，使用臨時表格中的資料來個人化您的傳遞。 若要執行此動作，請使用傳遞屬性的&#x200B;**[!UICONTROL Analysis]**&#x200B;索引標籤中的&#x200B;**[!UICONTROL Prepare the personalization data with a workflow]**&#x200B;選項，在專屬工作流程中預先處理訊息個人化。 在傳遞分析期間，此選項會自動建立並執行工作流程，將所有連結至目標的資料儲存在暫存表格中，包括連結至外部資料庫之表格的資料。

  >[!CAUTION]
  >
  >此選項可大幅改善執行個人化步驟時的效能。


## 在工作流程中使用外部資料

Campaign提供幾個工作流程活動，可用來與來自外部資料庫的資料互動：

* **篩選外部資料** — 使用&#x200B;**[!UICONTROL Query]**&#x200B;活動新增外部資料，並在定義的篩選設定中使用它。

* **建立子集** — 使用&#x200B;**[!UICONTROL Split]**&#x200B;活動建立子集。 您可以使用外部資料來定義要使用的篩選條件。

* **載入外部資料庫** — 在&#x200B;**[!UICONTROL Data loading (RDBMS)]**&#x200B;活動中使用外部資料。

* **新增資訊和連結** — 使用&#x200B;**[!UICONTROL Enrichment]**&#x200B;活動將其他資料新增至工作流程的工作表，以及外部表格的連結。 在這種情況下，它可以使用來自外部資料庫的資料。

您也可以從上面列出的所有工作流程活動中直接定義外部資料庫的連線，以供暫時使用。 在這種情況下，它將在本機外部資料庫上，僅用於目前工作流程中。

>[!CAUTION]
>
>此型別的設定只能暫時用於收集資料。 外部帳戶設定應首選用於任何其他用途。

例如，在&#x200B;**[!UICONTROL Query]**&#x200B;活動中，您可以定義與外部資料庫的暫時連線，如下所示：

1. 開啟活動並按一下&#x200B;**[!UICONTROL Add data...]**
1. 選取&#x200B;**[!UICONTROL External data]**&#x200B;選項
1. 選取&#x200B;**[!UICONTROL Locally defining the data source]**&#x200B;選項
1. 在下拉式清單中選取目標資料庫引擎。 輸入伺服器的名稱並提供驗證引數。 同時指定外部資料庫的名稱。
1. 選取儲存資料的表格。 您可以直接在對應欄位中輸入表格的名稱，或按一下編輯圖示來存取資料庫表格的清單。
1. 按一下&#x200B;**[!UICONTROL Add]**&#x200B;按鈕，以定義外部資料庫資料與Adobe Campaign資料庫資料之間的一或多個調解欄位。 **[!UICONTROL Remote field]**&#x200B;和&#x200B;**[!UICONTROL Local field]**&#x200B;的&#x200B;**[!UICONTROL Edit expression]**&#x200B;圖示可讓您存取每個表格的欄位清單。
1. 如有需要，請指定篩選條件和資料排序模式。
1. 選取要在外部資料庫中收集的其他資料。 若要這麼做，請連按兩下要新增的欄位，以便在&#x200B;**[!UICONTROL Output columns]**&#x200B;中顯示。
1. 按一下&#x200B;**[!UICONTROL Finish]**&#x200B;以確認此組態。
