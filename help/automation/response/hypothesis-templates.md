---
product: campaign
title: 假設範本
description: 瞭解如何在Campaign回應管理員中建立假設範本
feature: Campaigns, Templates
version: Campaign v8, Campaign Classic v7
audience: campaign
content-type: reference
topic-tags: response-manager
exl-id: 428c7677-454b-4618-bae7-0be7df6dfcaa
TQID: 'https://experienceleague.adobe.com/FKf9pDlOZI1NEhwmdSpcpvEbNsT28wEvgy81TBEQQgo'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: baf8e746-117b-5e73-b179-0a83edc0295f
    internal-label: Templates
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: d72afaa0-c842-48c8-9a3c-51b7911edc1b
    internal-label: Response Management
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 8839c1717cb026a38987a745ffc080a79f344bce
workflow-type: tm+mt
source-wordcount: '1828'
ht-degree: 1%
---
# 假設範本{#hypothesis-templates}



## 建立假設模型 {#creating-a-hypothesis-model}

設定假設範本可讓您定義測量回應的內容，無論是傳送或選件。 這是參照各種測量表格的位置，包括定義個人、假設和交易表之間關係的測量表格。

若要建立假設範本，請套用下列步驟：

1. 在Adobe Campaign總管中，按一下&#x200B;**[!UICONTROL Resources>Templates>Hypothesis templates]**。

   ![總管已選取資源>範本>假設範本，且假設範本在[一般]索引標籤上開啟。](assets/response_hypothesis_model_creation_001.png)

1. 按一下&#x200B;**[!UICONTROL New]**&#x200B;或在範本清單中按一下滑鼠右鍵，然後在下拉式清單中選擇&#x200B;**[!UICONTROL New]**。
1. 輸入假設標籤。
1. 指定範本是預期要透過&#x200B;**[!UICONTROL Hypothesis type]**&#x200B;用於優惠或傳遞的假設。
1. 針對&#x200B;**[!UICONTROL Delivery]**&#x200B;型別範本，指定是否應在控制組內進行測量。 [了解更多](#properties-of-a-hypothesis-template)
1. 對於&#x200B;**[!UICONTROL Delivery]**&#x200B;型別範本，您可以使用&#x200B;**[!UICONTROL Channel]**&#x200B;下拉式清單來選擇特定管道，或決定將該範本套用至Adobe Campaign中的所有可用管道。 [了解更多](#properties-of-a-hypothesis-template)
1. Select您要在其中建立的&#x200B;**[!UICONTROL Execution folder]**，並自動執行將從此範本建立的假設。
1. 選擇執行設定。 [了解更多](#hypothesis-template-execution-settings)
1. 指定假設計算期間。 [了解更多](#hypothesis-template-execution-settings)

   >[!CAUTION]
   >
   >此期間由聯絡日期決定。

1. 在&#x200B;**[!UICONTROL Transactions]**&#x200B;索引標籤中，指定假設計算所需的資料表和欄位。 [了解更多](#transactions)
1. 如果您的範本設定為&#x200B;**[!UICONTROL Offer]**&#x200B;型別假設，您可以啟用&#x200B;**[!UICONTROL Update offer proposition status]**&#x200B;選項：在此情況下，請選取您要變更之優惠方案主張的狀態。
1. 指定假設應用程式的範圍。 [了解更多](#hypothesis-perimeter)
1. 如有必要，請使用指令碼完成篩選。 [了解更多](#hypothesis-perimeter)

### 假設範本的屬性 {#properties-of-a-hypothesis-template}

範本的&#x200B;**[!UICONTROL General]**&#x200B;標籤可讓您指定一般範本選項。 可用的欄位包括：

* **[!UICONTROL Hypothesis type]**：可讓您判斷範本是否應該預定給傳遞或優惠方案的假設。

  您也可以選擇建立將同時套用至傳送和優惠方案的假設。

  >[!NOTE]
  >
  >如果範本套用至選件，**[!UICONTROL Transactions]**&#x200B;索引標籤中會提供&#x200B;**[!UICONTROL Update offer proposition status]**&#x200B;選項。

* **[!UICONTROL Measurement with control group]**：可讓您指出是否已為傳遞或行銷活動定義控制組，並將其納入測量指標中。 控制組不會接收傳遞，可讓您透過比較行銷活動與收到傳遞的目標母體，來測量傳遞後行銷活動的影響。

  >[!NOTE]
  >
  >如果範本設定為將控制組列入考量，但在假設相關的傳送中未定義任何組，則結果將僅以目標收件者為基礎。

  有關定義和設定控制組的詳細資訊，請參閱[Campaign v8檔案](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=zh-Hant#add-a-control-group){target=_blank}。

* **[!UICONTROL Channel]**：您可以在下拉式清單中選取&#x200B;**[!UICONTROL All channels]**，以選擇特定管道或讓假設範本可供Adobe Campaign主控台中的所有管道使用。 如果您設定特定頻道的範本，這可讓您在建立假設時自動篩選每個頻道的傳送。 [了解更多](creating-hypotheses.md)

  ![假設範本的「一般」標籤，其中的「管道」下拉式清單已開啟，「所有管道」已反白顯示。](assets/response_properties_001.png)

* **[!UICONTROL Execution folder]**：可讓您指定假設的執行資料夾。
* **[!UICONTROL Taken into account in campaign ROI calculation]**：在相關行銷活動的ROI計算中，將假設結果納入考量。

### 假設範本執行設定 {#hypothesis-template-execution-settings}

範本的&#x200B;**[!UICONTROL General]**&#x200B;標籤也可讓您指定假設執行引數。 可用的選項如下：

* **[!UICONTROL Schedule execution for a time of low activity]**：可讓您排程假設啟動，以最佳化Adobe Campaign效能。 核取此選項時，行銷活動的處理工作流程會在停機期間執行假設計算。

  ![假設範本執行設定已檢查低活動時間的排程執行。](assets/response_exec_settings_002.png)

* **[!UICONTROL Priority]**：套用至假設的層級，在有同時執行的情況下將假設計算順序隔開。

  ![假設範本優先順序下拉式清單「低」、「平均」和「高」。](assets/response_exec_settings_003.png)

* **[!UICONTROL Automatic execution]**：如有必要，可讓您排程假設重新計算（例如，如果您要定期更新指標直到傳送結束）。

  ![已使用執行連結的頻率檢查自動執行，並使用「變更」按鈕檢查其假設對話方塊。](assets/response_exec_settings_001.png)

  若要指定排程，請套用下列程式：

  1. 按一下&#x200B;**[!UICONTROL Frequency of execution...]**&#x200B;連結，然後按&#x200B;**[!UICONTROL Change...]**&#x200B;按鈕。

     ![說明未定義任務排程的假設對話方塊，使用[變更]按鈕來定義頻率。](assets/response_frequency_execution_001.png)

  1. 設定頻率、相關事件和有效期。

     ![排程編輯精靈：每週頻率、選取星期三和星期五，以及有效期限。](assets/response_frequency_execution_002.png)

  1. 按一下&#x200B;**[!UICONTROL Finish]**&#x200B;以儲存排程。

     ![使用[完成]按鈕排程編輯精靈摘要步驟列出啟動時間。](assets/response_frequency_execution_003.png)

* **[!UICONTROL Log SQL queries in journal]**：此函式已保留給專家使用者。 它可讓您在測量假設稽核中新增索引標籤，以顯示SQL查詢。 如此一來，在模擬完成時若發生錯誤，即可偵測可能的故障。
* **[!UICONTROL Keep execution workflow]**：可讓您保留假設計算開始時自動產生的工作流程。 在從已核取此選項的範本建立的假設中，產生的工作流程可用於遵循該流程。

  >[!CAUTION]
  >
  >此選項僅能用於偵錯，以防執行假設時發生錯誤。\
  >此外，不得修改自動產生的工作流程。 在之後的計算中，任何最終修改都不會在其他地方被考慮。\
  >如果您已核取此選項，請在工作流程執行後將其刪除。

### 交易數 {#transactions}

此索引標籤包含各種欄位和表格，可讓您根據交易儲存收件者回應的歷史記錄。 請參閱此[區段](https://experienceleague.adobe.com/zh-hant/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/about-schema-reference){target="_blank"}，以取得回應管理專用表格的詳細資訊。

* **[!UICONTROL Schema (reaction log storage)]**：選取收件者回應表格。 Adobe Campaign中的現成表格是&#x200B;**NmsRemaMatchRcp**。
* **[!UICONTROL Transaction schema]**：選擇假設所關注的資料表，即交易或購買資料表。
* **[!UICONTROL Querying schema]**：選擇篩選假設的條件。
* **[!UICONTROL Link to individuals]**：選擇個人與做為交易結構描述之資料表之間的連結。
* **[!UICONTROL Link to the household]**：如果您想要在假設中納入某個家庭的所有成員，請選取交易結構描述中該家庭的連結。 此欄位為選用。
* **[!UICONTROL Transaction date]**：此欄位是選用欄位，但建議使用，因為它可讓您定義假設計算的範圍。
* **[!UICONTROL Measurement period]**：可讓您設定執行假設與復原購買明細行的開始與結束日期。

  當假設連結至傳遞時，對於直接郵件傳遞，測量會在聯絡日期後數天自動觸發，對於電子郵件或簡訊傳遞，則會在傳遞日期後自動觸發。

  ![具有交易日期欄位、計算開始與計算期間結束的交易標籤。](assets/response_measurement_001.png)

  如果立即啟動假設，且想要立即觸發，則可強制啟動。 否則，會根據設定的計算結束日期（以假設建立日期為基礎）自動觸發。 [深入瞭解](creating-hypotheses.md#creating-a-hypothesis-on-the-fly-on-a-delivery))。

* **[!UICONTROL Transaction/Margin amount]**：這些欄位是選用欄位，可讓您自動計算人員調整指標。 [了解更多](hypothesis-tracking.md#indicators)
* **[!UICONTROL Unit amount]**：可讓您設定計算收入的金額。 [了解更多](hypothesis-tracking.md#indicators)

  ![交易索引標籤，其[交易金額]設定為@amount，且箭頭指向[單位金額]欄位。](assets/response_transactions_001.png)

* **[!UICONTROL Additional measures and data]**：可讓您從不同表格中的欄位指定其他報表測量或軸。
* **[!UICONTROL Update offer proposition status]**：可讓您變更優惠方案主張的狀態（如果假設已識別優惠方案收件者）。

  ![已勾選「更新優惠方案主張」狀態且「狀態」下拉式清單開啟的「交易」索引標籤的「主張」區段。](assets/response_offer_status_001.png)

### 假設周邊 {#hypothesis-perimeter}

定義交易表格和假設將關注的欄位後，您可以使用篩選器指定目標交易和傳送，以縮小假設的範圍。 您也可以使用JavaScript指令碼，明確指向交易表格中所參照的產品。

* **篩選交易**：在&#x200B;**[!UICONTROL Scope]**&#x200B;索引標籤中，您可以設定假設的篩選器。 操作步驟：

  1. 按一下&#x200B;**[!UICONTROL Edit query]**&#x200B;連結。

     ![範圍索引標籤，在[篩選連結至回應的交易]下有[編輯查詢]連結。](assets/response_scope_filtering_001.png)

  1. 指定您的篩選條件。

     ![編輯查詢精靈：篩選選取的條件，然後按一下[編輯運算式]按鈕與欄位選取樹狀結構。](assets/response_scope_filtering_002.png)

  1. Select假設將關注的交易。

     ![編輯查詢篩選條件：存在購買明細行，例如，購買等於值清單已開啟。](assets/response_scope_filtering_003.png)

* **篩選收件者**：在&#x200B;**[!UICONTROL Scope]**&#x200B;索引標籤中，您可以將假設限製為連結至郵件的任何資訊（傳遞、收件者、電子郵件地址、服務等）：

  1. 按一下&#x200B;**[!UICONTROL Add a filter]**&#x200B;連結，然後按&#x200B;**[!UICONTROL Edit query]**。

     ![範圍索引標籤，其中的[新增篩選器]連結與[編輯查詢]連結位於[篩選傳遞訊息]下。](assets/response_scope_filtering_004.png)

  1. 指定您的篩選條件。

     ![在電子郵件收件者傳遞記錄結構描述上編輯查詢精靈，包含篩選條件。](assets/response_scope_filtering_005.png)

  1. 按一下&#x200B;**[!UICONTROL Finish]**&#x200B;以儲存查詢。

     ![顯示已儲存傳遞訊息篩選器的範圍標籤，查詢：電子郵件包含，反白顯示。](assets/response_scope_filtering_006.png)

* **指令碼**：您可以使用JavaScript指令碼，在執行期間動態多載假設設定。

  若要這麼做，請按一下&#x200B;**[!UICONTROL Advanced settings]**&#x200B;連結，然後輸入所需的指令碼。

  >[!NOTE]
  >
  >此選項適用於專家使用者。

  ![進階設定對話方塊，已輸入初始化指令碼，從[範圍]索引標籤上的[進階設定]連結開啟。](assets/response_hypothesis_model_creation_011.png)

## 範例：在傳遞上建立假設範本 {#example--creating-a-hypothesis-template-on-a-delivery}

在此範例中，我們將針對直接郵件型別傳遞建立假設範本。 假設所依據的交易表（**購買**）包含連結至文章或產品的購買明細行。 我們想要設定模型，以建立購買表格中文章或產品的假設。

1. 在Adobe Campaign總管中，前往&#x200B;**[!UICONTROL Resources > Templates > Hypothesis templates]**&#x200B;節點。
1. 按一下&#x200B;**[!UICONTROL New]**&#x200B;以建立範本。

   ![假設範本清單中反白顯示「新增」按鈕，並在「一般」標籤上開啟新範本。](assets/response_hypothesis_model_example_001.png)

1. 變更範本標籤。

   ![範本一般索引標籤，其標籤已變更為購買和傳遞的假設型別。](assets/response_hypothesis_model_example_002.png)

1. Select **[!UICONTROL Deliveries]**&#x200B;為假設型別。
1. 核取相關方塊，指定傳遞可包含控制組。
1. 選擇&#x200B;**[!UICONTROL Direct mail]**&#x200B;管道。

   >[!NOTE]
   >
   >由於範本是直接郵件傳遞所專屬，因此使用此模型建立的假設可能不會連結至任何其他傳遞型別。

1. 在&#x200B;**[!UICONTROL Transactions]**&#x200B;索引標籤中，選取收件者回應表格。

   ![使用Select的[結構描述]對話方塊的[交易]索引標籤，以及選取的收件者結構描述回應。](assets/response_hypothesis_model_example_006.png)

1. 在&#x200B;**[!UICONTROL Transactions schema]**&#x200B;欄位中，選擇您的購買表格。

   ![使用Select的[交易]索引標籤為檔案對話方塊，已針對選取的購買和購買進行篩選。](assets/response_hypothesis_model_example_007.png)

1. **[!UICONTROL Querying schema]**&#x200B;欄位中的Select購買明細行。

   ![查詢結構描述下拉式清單，列出收件者的購買行、購買和回應。](assets/response_hypothesis_model_example_008.png)

1. 選擇連結至購買表格的收件者。

   ![Select運算式對話方塊，用於連結至在「購買」下選取收件者連結的個人。](assets/response_hypothesis_model_example_009.png)

1. Select連結至購買日期的欄位。

   這可讓您定義假設的時間範圍。 此階段並非強制性，但建議使用。

   ![針對已選取「購買日期」欄位的「交易日期」Select運算式對話方塊。](assets/response_hypothesis_model_example_010.png)

1. 設定計算期間5至25天。

   ![計算開始設為5d且計算結束設為25d的[交易]索引標籤。](assets/response_hypothesis_model_example_005.png)

1. 在&#x200B;**[!UICONTROL Scope]**&#x200B;索引標籤中，按一下&#x200B;**[!UICONTROL Edit query]**&#x200B;以建立假設的篩選器。

   ![已按一下[編輯查詢]的[範圍]索引標籤，且[編輯查詢]精靈列出篩選型別，依選取的產品篩選。](assets/response_hypothesis_model_example_011.png)

   因此建立的範本可讓您對購買表格中的產品或文章執行假設。

1. 按一下&#x200B;**[!UICONTROL Save]**&#x200B;以錄製您的範本。
