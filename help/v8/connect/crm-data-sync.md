---
title: CRM連接器資料同步
description: 在Campaign和您的CRM之間管理資料
feature: Salesforce Integration, Microsoft CRM Integration
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 2a7ae88e-d47f-416b-84cd-986ab9be6aef
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 1%

---

# 在Campaign和您的CRM之間同步資料 {#data-synchronization}

Adobe Campaign與CRM之間的資料同步由 **CRM Connector** 工作流程活動。

例如，若要將Microsoft Dynamics資料匯入Adobe Campaign，請建立下列類型的工作流程：

![](assets/ms-dyn-wf.png)

此工作流程會透過Microsoft Dynamics匯入聯絡人、將其與現有Adobe Campaign資料同步、刪除重複的聯絡人，以及更新Adobe Campaign資料庫。

此 **[!UICONTROL CRM Connector]** 活動必須設定為同步資料。

![](assets/crm-connector-ms-dyn.png)

透過此活動，您可以：

* 從CRM匯入 —  [深入了解](#importing-from-the-crm)
* 匯出至CRM - [深入了解](#exporting-to-the-crm)
* 導入在CRM中刪除的對象 —  [深入了解](#importing-objects-deleted-in-the-crm)
* 刪除CRM中的對象 —  [深入了解](#deleting-objects-in-the-crm)

![](assets/crm-remote-op.png)

選擇與要配置同步的CRM匹配的外部帳戶，然後選擇要同步的對象：帳戶、機會、銷售機會、聯繫人等

![](assets/crm-remote-obj.png)

此活動的設定取決於要執行的程式。 以下詳細說明各種配置。

## 從CRM匯入 {#importing-from-the-crm}

若要透過Adobe Campaign中的CRM匯入資料，您需要建立下列類型的工作流程：

![](assets/crm-wf-import.png)

1. 選取 **[!UICONTROL Import from the CRM]** 操作。
1. 在 **[!UICONTROL Remote object]** 下拉式清單中，選取要匯入的物件。 此物件與連接器配置期間在Adobe Campaign中建立的其中一個表格相符。
1. 在 **[!UICONTROL Remote fields]** 部分，輸入要導入的欄位。

   若要新增欄位，請按一下 **[!UICONTROL Add]** 按鈕，然後按一下 **[!UICONTROL Edit expression]** 表徵圖。

   如有必要，請使用 **[!UICONTROL Conversion]** 欄。 可能的轉換類型在 [本節](#data-format).

   >[!CAUTION]
   >
   >在CRM和Adobe Campaign中，連結物件時，CRM中記錄的識別碼是必填的。 當核准方塊時，就會自動新增。
   >
   >對於增量資料匯入，CRM端的上次修改日期也是必要項目。

1. 您可以根據需求篩選要匯入的資料。 若要這麼做，請按一下 **[!UICONTROL Edit the filter...]** 連結。

   在下列範例中，Adobe Campaign只會匯入自2021年11月1日以來已記錄某些活動的連絡人。

   ![](assets/crm-task-import-filter.png)

   >[!CAUTION]
   >
   >如需資料篩選模式的相關限制，請參閱 [本節](#filtering-data).

1. 選取 **[!UICONTROL Use automatic index...]** 選項，根據CRM和Adobe Campaign的上次修改日期，自動管理其間的增量物件同步。

   如需詳細資訊，請參閱[本章節](#variable-management)。

### 管理變數 {#variable-management}

啟動 **[!UICONTROL Automatic index]** 選項，僅收集自上次導入後修改的對象。

![](assets/use-auto-index.png)

預設情況下，上次同步的日期將儲存在配置窗口中指定的選項中： **LASTIMPORT_&lt;%=instance.internalName%>_&lt;%=activityName%>**.

>[!NOTE]
>
>此注釋僅適用於通用 **[!UICONTROL CRM Connector]** 活動。 對於其他CRM活動，程式會自動執行。
>
>此選項必須手動建立，並填入 **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**. 它必須是文字選項，其值必須符合下列格式： **yyyy/MM/dd hh:mm:ss**.
> 
>您需要手動更新此選項，才能進行任何進一步匯入。

您可以指定要考慮的遠端CRM欄位，以識別最近的變更。

預設會使用下列欄位（依指定順序）:

* 若為Microsoft Dynamics: **修改日期**,
* 對於Salesforce.com: **LastModifiedDate**, **SystemModstamp**.

啟動 **[!UICONTROL Automatic index]** 選項會產生三個變數，這些變數可透過 **[!UICONTROL JavaScript code]** 類型活動。 這些活動包括：

* **vars.crmOptionName**:包含上次匯入日期的選項名稱。
* **vars.crmStartImport**:上次資料匯入的開始日期（已包含）。
* **vars.crmEndDate**:上次資料匯入的結束日期（已排除）。

   >[!NOTE]
   >
   >這些日期會以下列格式顯示： **yyyy/MM/dd hh:mm:ss**.

### 篩選資料 {#filtering-data}

為了確保對各種CRM進行有效操作，需使用以下規則建立篩選器：

* 每個篩選層級只能使用一種運算子。
* 不支援AND NOT運算子。
* 比較可能只涉及空值（「為空」/「非空」類型）或數字。 這表示會評估值（右側欄），此評估的結果必須為數字。 因此不支援JOIN類型比較。
* 右側欄中的值會以JavaScript評估。
* 不支援連接比較。
* 左欄中的運算式必須是欄位。 它不能是數個運算式、數字等的組合。

### 訂購依據 {#order-by}

在Microsoft Dynamics和Salesforce.com中，您可以依遞增或遞減順序排序要匯入的遠端欄位。

若要這麼做，請按一下 **[!UICONTROL Order by]** 連結，並將欄新增至清單。

清單中的欄順序是排序順序：

![](assets/crm-import-order.png)

### 記錄標識 {#record-identification}

與其匯入CRM中包含的元素（且可能經過篩選），您可以使用工作流程中預先計算的母體。

若要這麼做，請選取 **[!UICONTROL Use the population calculated upstream]** 選項，並指定包含遠端識別碼的欄位。

然後選取您要匯入的入站母體欄位，如下所示：

![](assets/use-population-calc-upstream.png)

## 匯出至CRM {#exporting-to-the-crm}

將Adobe Campaign資料匯出至您的CRM，以將其整個內容複製至您的CRM資料庫。

若要將資料匯出至您的CRM，請建立下列類型的工作流程：

![](assets/crm-export-diagram.png)

1. 選取 **[!UICONTROL Export to CRM]** 操作。
1. 前往 **[!UICONTROL Remote object]** 下拉式清單中，並選取要匯出的物件。 此物件與連接器配置期間在Adobe Campaign中建立的其中一個表格相符。

   >[!CAUTION]
   >
   >的匯出功能 **[!UICONTROL CRM Connector]** 活動可在您的CRM上插入或更新欄位。 要啟用CRM中的欄位更新，請指定遠程表的主鍵。 如果缺少金鑰，則會插入資料，而非更新。

1. 如果您需要執行更快的匯出作業，請檢查  **[!UICONTROL Export in Batches]** 選項。

   ![](assets/crm-export-batch.png)

1. 在 **[!UICONTROL Mapping]** ，按一下 **[!UICONTROL New]** 指定要匯出的欄位及其在CRM中的對應。

   若要新增欄位，請按一下 **[!UICONTROL Add]** 按鈕，然後按一下 **[!UICONTROL Edit expression]** 表徵圖。

   >[!NOTE]
   >
   >如果未為欄位定義相符項目，則無法更新值：會直接插入您的CRM中。

   如有必要，請使用 **[!UICONTROL Conversion]** 欄。 可能的轉換類型在 [本節](#data-format).

   >[!NOTE]
   >
   >要導出的記錄清單和導出結果將保存在臨時檔案中，該檔案在工作流完成或重新啟動之前始終可訪問。 這可讓您在發生錯誤時安全地啟動程式。

## 其他設定 {#additional-configurations}

### 資料格式 {#data-format}

將資料格式匯入CRM時或從CRM匯入時，您可以即時轉換資料格式。

若要這麼做，請選取要在相符欄中套用的轉換。

![](assets/crm-task-import.png)

此 **[!UICONTROL Default]** 模式會套用自動資料轉換，在大多數情況下，這等於資料的複製/貼上。 但是會套用時區管理。

其他可能的轉換包括：

* **[!UICONTROL Date only]**:刪除日期+時間類型欄位。
* **[!UICONTROL Without time offset]**:取消在預設模式中應用的時區管理。
* **[!UICONTROL Copy/Paste]**:使用字串等原始資料（無轉換）。

### 錯誤處理 {#error-processing}

在資料匯入或匯出的架構中，您可以將特定程式套用至錯誤和拒絕。 若要這麼做，請選取 **[!UICONTROL Keep the rejections in a file]** 和 **[!UICONTROL Process errors]** 選項 **[!UICONTROL Behavior]** 標籤。

![](assets/crm-export-options.png)

這些選項會新增相關的輸出轉變。

![](assets/crm-export-transitions.png)

然後插入相關活動以處理資料。 例如，新增 **等待** 活動和排程重試錯誤。

此 **[!UICONTROL Reject]** 輸出轉變可讓您存取包含與錯誤訊息和程式碼相關的特定欄的輸出架構。 對於Salesforce.com，此欄為 **errorSymbol** （錯誤符號，與錯誤代碼不同）, **errorMessage** （錯誤內容的說明）。

## 導入在CRM中刪除的對象 {#importing-objects-deleted-in-the-crm}

您可以將CRM中刪除的物件匯入Adobe Campaign。

1. 選取 **[!UICONTROL Import objects deleted in the CRM]** 操作。
1. 前往 **[!UICONTROL Remote object]** 下拉式清單中，並選取程式所關注的物件。 此物件與連接器配置期間在Adobe Campaign中建立的其中一個表格相符。
1. 指定要在 **[!UICONTROL Start date]** 和 **[!UICONTROL End date]** 欄位（包含日期）。

   >[!CAUTION]
   >
   >刪除期間必須符合您的CRM特定限制。 例如，對於Salesforce.com,30天前刪除的元素無法復原。

## 刪除 CRM 中的物件 {#deleting-objects-in-the-crm}

要刪除CRM上的對象，請指定要刪除的遠程元素的主鍵。

此 **[!UICONTROL Behavior]** 索引標籤可讓您啟用拒絕的處理。 此選項會為 **[!UICONTROL CRM connector]** 活動。 有關詳細資訊，請參閱 [錯誤處理](#error-processing).
