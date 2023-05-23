---
title: 使用活動和外部資料庫(FDA)
description: 瞭解如何使用活動和外部資料庫
feature: Federated Data Access
role: Admin
level: Beginner, Intermediate
exl-id: 0259b3bd-9dc2-44f9-a426-c4af46b00a4e
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 1%

---

# 同盟資料存取 (FDA){#gs-fda}

使用FDA連接器（聯合資料存取）將市場活動連接到一個或多個 **外部資料庫** 並處理儲存在其中的資訊，而不影響您的市場活動雲資料庫資料。 然後，您可以訪問外部資料，而不更改Adobe Campaign資料的結構。

![](../assets/do-not-localize/speech.png)   作為托管Cloud Services用戶， [聯繫人Adobe](../start/campaign-faq.md#support) 將外部資料庫與市場活動連接。


>[!NOTE]
>
>* 聯合資料存取的相容資料庫列於 [相容性矩陣](../start/compatibility-matrix.md)。
>
>* 在 [企業(FDA)部署](../architecture/enterprise-deployment.md)，可使用特定外部帳戶管理市場活動本地資料庫和Snowflake雲資料庫之間的通信。 此外部帳戶通過Adobe和 **不能** 修改。
>



## 最佳實務和限制

FDA選項受您使用的第三方資料庫系統的限制。

此外，請注意以下限制和最佳做法：

* FDA選項用於在工作流中以批處理模式處理外部資料庫中的資料。 為避免業績問題，不建議在單一操作中使用FDA模組，例如：個性化、交互、即時消息等。

* 避免需要盡可能使用Adobe Campaign和外部資料庫的操作。 為此，您可以：

   * 將Adobe Campaign資料庫導出到外部資料庫，並僅在將結果重新導入Adobe Campaign之前從外部資料庫執行操作。

   * 從外部Adobe Campaign資料庫收集資料並在本地執行操作。
   如果您希望使用外部資料庫中的資料在交貨中執行個性化設定，請收集要在工作流中使用的資料，使其在臨時表中可用。 然後使用臨時表中的資料來個性化您的交付。 要執行此操作，請使用 **[!UICONTROL Prepare the personalization data with a workflow]** ，在 **[!UICONTROL Analysis]** 的子菜單。 在傳遞分析期間，此選項會自動建立並執行一個工作流，該工作流將連結到目標的所有資料儲存在臨時表中，包括來自外部資料庫中連結的表的資料。

   >[!CAUTION]
   >
   >此選項在執行個性化設定步驟時顯著提高效能。


## 在工作流中使用外部資料

市場活動附帶了幾個工作流活動，您可以使用這些活動與外部資料庫中的資料交互：

* **篩選外部資料**  — 使用 **[!UICONTROL Query]** 活動：添加外部資料並在定義的篩選器配置中使用它。

* **建立子集**  — 使用 **[!UICONTROL Split]** 建立子集。 可以使用外部資料來定義要使用的篩選條件。

* **載入外部資料庫**  — 使用 **[!UICONTROL Data loading (RDBMS)]** 的子菜單。

* **添加資訊和連結**  — 使用 **[!UICONTROL Enrichment]** 活動，將附加資料添加到工作流的工作表，並連結到外部表。 在此上下文中，它可以使用外部資料庫中的資料。

您也可以直接從上面列出的所有工作流活動定義到外部資料庫的連接，以便暫時使用。 在這種情況下，它將位於本地外部資料庫上，僅在當前工作流中使用。

>[!CAUTION]
>
>此類型的配置只能用於臨時收集資料。 對於任何其他用途，應首選外部帳戶配置。

例如，在 **[!UICONTROL Query]** 活動，可以定義到外部資料庫的臨時連接，如下所示：

1. 開啟活動，然後按一下 **[!UICONTROL Add data...]**
1. 選擇 **[!UICONTROL External data]** 選項
1. 選擇 **[!UICONTROL Locally defining the data source]** 選項
1. 在下拉清單中選擇目標資料庫引擎。 輸入伺服器名稱並提供驗證參數。 還指定外部資料庫的名稱。
1. 選擇儲存資料的表。 可以直接在相應欄位中輸入表的名稱，或按一下編輯表徵圖訪問資料庫表的清單。
1. 按一下 **[!UICONTROL Add]** 按鈕，定義外部資料庫資料與Adobe Campaign資料庫中資料之間的一個或多個協調欄位。 的 **[!UICONTROL Edit expression]** 表徵圖 **[!UICONTROL Remote field]** 和 **[!UICONTROL Local field]** 允許您訪問每個表的欄位清單。
1. 如有必要，請指定篩選條件和資料排序模式。
1. 選擇要在外部資料庫中收集的其他資料。 為此，請按兩下要添加的欄位，以在 **[!UICONTROL Output columns]**。
1. 按一下 **[!UICONTROL Finish]** 確認此配置。
