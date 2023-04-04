---
title: 將權限授予Campaign v8
description: 了解如何將權限授予Campaign v8使用者
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 90154f84-b6a7-407c-93b7-9731dc94d9de
source-git-commit: b96ac3bd2365c548d071e626721d606dd33200b5
workflow-type: tm+mt
source-wordcount: '1632'
ht-degree: 1%

---

# 管理使用者權限{#manage-permissions}

## 新增使用者 {#add-users}

身為產品管理員，您可以新增使用者並授與Campaign的存取權。

若要新增使用者，請遵循下列步驟：

1. 在 [Admin Console](https://adminconsole.adobe.com/enterprise){target="_blank"} 首頁，選擇 **新增使用者**.

   ![](assets/add-a-user.png)

1. 輸入使用者的電子郵件地址。
1. 使用「+」符號來選取要指派給使用者的產品設定檔或使用者群組。

   ![](assets/add-a-product-profile.png)

   Campaign內建的產品設定檔列於 [本節](#ootb-productprofiles).

   了解如何在 [本節](#user-groups)

1. 按一下 **儲存**. 使用者隨即新增，並顯示在「使用者」清單中。 如果您指派管理員角色或產品設定檔給使用者，使用者會收到電子郵件通知。 使用者必須依循連結才能完成其設定檔。

進一步了解在Admin Console中建立使用者的方式： [本頁](https://helpx.adobe.com/ie/enterprise/using/manage-users-individually.html){target="_blank"}.

新使用者時 [登入Campaign](connect.md) 透過其Adobe ID，這些使用者會新增至用戶端主控台的Campaign運算子清單。 促銷活動運算子儲存在 **[!UICONTROL Administration > Access management > Operators]** Campaign檔案總管的資料夾。

## 使用產品設定檔{#product-profiles}

使用產品設定檔來授予使用者權益，使用產品中包含的功能。

* 您可以針對Admin Console上的每個產品建立一或多個產品設定檔。
* 在每個產品設定檔中，您會指派使用者和使用者群組（在您的組織中）。
* 當使用者依產品設定檔中指定的認證登入時，即可存取產品設定檔所依據之產品的應用程式和服務。

這些產品設定檔會與儲存在 **[!UICONTROL Administration > Access management > Operator groups]** Campaign檔案總管的資料夾。

在Admin Console中，產品設定檔使用下列語法：

行銷活動 —  `<your instance>`  — 操作員組的內部名稱

例如，對於 **傳送運算子** 群組，Admin Console中的產品設定檔為：

行銷活動 — 測試 — 傳遞

您可以使用預設的產品設定檔或建立新的產品設定檔。

### 建立產品設定檔{#create-product-profile}

若要新增產品設定檔至Adobe，您必須先在Campaign用戶端主控台中建立，然後將其新增至Admin Console。

例如，若要建立「審核者」產品設定檔，請遵循下列步驟。

#### 在Campaign中建立運算子群組{#create-op-group}

1. 連線至Campaign，開啟Explorer，然後瀏覽至 **[!UICONTROL Administration > Access management > Operator groups]**.
1. 按一下 **[!UICONTROL New]**，並定義運算子群組的名稱，並設定其內部名稱(「reviewers」)。
   ![](assets/new-op-group.png)
1. 選取命名的權限，以定義相關的權限。 命名權限在 [本節](#use-named-rights)
1. 儲存新運算子群組。

#### 在Admin Console中建立產品設定檔{#create-profile-in-admin-console}

1. 連線至 [Admin Console](https://adminconsole.adobe.com/enterprise){target="_blank"}.
1. 從 **產品與服務** 在首頁的區段中，開啟Campaign產品。
1. 按一下 **新設定檔** 並輸入要建立的產品設定檔名稱，且語法完全正確，如所說明 [此處](#product-profiles). 例如，我們輸入：行銷活動 —  `<your-instance-name>`  — 審核者

   ![](assets/new-product-profile-ui.png)

1. 儲存您的變更。

您現在可以將使用者新增至此新產品設定檔，如 [本節](#add-users).

最佳實務是將產品設定檔指派給使用者群組。 依使用者管理權限並非可持續的模式。


### 預設產品設定檔和運算子群組 {#ootb-productprofiles}

Adobe Campaign內建 **產品設定檔** 當Adobe啟用您的環境時定義。

![](assets/ootb-product-profiles.png)

這些產品設定檔與Campaign相符 **運算元組**. 預設運算子群組及其 [已命名的權限](#use-named-rights) 列於下方：

1. **[!UICONTROL Administrator]** （管理員）

   此群組中的運算子可完整存取執行個體。 管理員是可存取使用者介面中技術最全的使用者。

   此群組包含下列命名權限：

   * **[!UICONTROL ADMINISTRATION]**:執行/建立/編輯/刪除任何物件（例如工作流程、傳送、指令碼等）的權限。

1. **[!UICONTROL Delivery operators]** (配送)

   此群組中的運算子負責管理傳送：它們可讓您存取建立和準備傳送所需的主要資源（行銷活動類型、傳送對應、預設範本、個人化區塊等）。

   此組包含以下命名權限：

   * **[!UICONTROL PREPARE DELIVERIES]**:建立、編輯和開始傳遞分析，
   * **[!UICONTROL START DELIVERIES]**:核准先前分析的傳送的權限。

1. **[!UICONTROL Campaign managers]** （操作）

   此群組中的運算子可以管理行銷活動：它可讓您存取連結至促銷活動（計畫、方案、工作流程、預算等）的物件 在 **[!UICONTROL Campaign]** (選用的Adobe Campaign模組)。

   此組包含以下命名權限：

   * **[!UICONTROL INSERT FOLDERS]**:將資料夾插入Adobe Campaign樹的權利（前提是您擁有相關分支的編輯權利）,
   * **[!UICONTROL WORKFLOW]**:使用工作流程的權限。

   >[!NOTE]
   >
   >此群組不會讓運算子開始傳送。

1. **[!UICONTROL Content contributors]** （內容）

   此群組中的使用者可以在 **[!UICONTROL Content management]** 附加元件。 此組不授予任何附加權限。

1. **[!UICONTROL Access to reports]** （報告）

   此群組保留給外部運算子，以透過 [網路存取](../start/campaign-ui.md#web-browser).

1. **[!UICONTROL Workflow execution]** （工作流程）

   此 **[!UICONTROL Workflow execution]** 群組可讓您控制目標工作流程的執行和核准：名為「權限」的工作流將映射到此組的運算子。 除了存取資料檔案的權限外，工作流程上的所有動作都需要此功能。 依預設， **[!UICONTROL Workflow execution]** 群組對標準目標工作流程檔案和工作流程範本具有唯讀存取權。 此組中的操作員也具有對待批准檔案的讀寫權限。

1. **[!UICONTROL Workflow supervisors]** (workflowSupervisor)

   此群組中的使用者會管理工作流程核准，並在出現與行銷活動工作流程相關的警報時收到電子郵件通知。

1. **本地/中央管理** （中央/地方）

   此群組中的使用者可使用 **[!UICONTROL Distributed marketing]** 附加元件。

1. **[!UICONTROL Offer managers]** (優惠)

   使用「互動」附加元件時，此群組中的運算子可以建立和維護優惠方案。 [了解更多資訊](../interaction/interaction-operators.md)。

   此組包含以下命名權限：

   * **[!UICONTROL INSERT FOLDERS]**:將資料夾插入Adobe Campaign樹的權利（前提是您擁有相關分支的編輯權利）,
   * **[!UICONTROL EDIT FOLDERS]**:更改資料夾屬性的權限，如內部名稱、標籤、關聯影像、子資料夾順序等。

   指派給優惠方案管理員的權限可讓他們執行下列工作：

   * 修改 **[!UICONTROL Design]** 環境。
   * 檢視 **[!UICONTROL Live]** 環境。
   * 配置管理函式（預定義空格和篩選器）。
   * 建立和更新類別。
   * 建立優惠.
   * 設定優惠方案資格。
   * 核准優惠方案。

   >[!NOTE]
   >
   >**優惠方案經理** 只有在未指定審核者，或在優惠方案範本中已設定為審核者時，才能核准優惠方案。

   中提供每個環境的Offer Manager權限矩陣 [本頁](../interaction/interaction-operators.md#recap-of-rights-according-to-operator).

## 使用使用者群組{#user-groups}

您可以使用Admin Console來建立使用者群組，並將使用者指派給他們。

使用者群組是不同使用者的集合，這些使用者必須獲得一組共用權限。 了解如何在 [本節](https://helpx.adobe.com/ie/enterprise/using/user-groups.html){target="_blank"}.

您可以將產品設定檔指派給使用者群組。 因此，該群組中的所有使用者都會收到相同的產品權限集。

## 已命名的權限{#use-named-rights}

Adobe Campaign隨附一組命名權限，可讓您定義指派給使用者和使用者群組的權限。 您可以從 **[!UICONTROL Administration > Access management > Named rights]** Campaign檔案總管的資料夾。

指定權限授予：

* 執行操作例如 **分析** 按鈕（在「傳送」編輯器中） **傳送運算子** 具有 **準備傳送** 已命名權限

* 對資料夾的訪問操作員組的成員資格可以通過更改資料夾的安全設定來授予或限制對資料夾的訪問權限。 [了解更多資訊](folder-permissions.md#restrict-access-to-a-folder)。

   例如，它可能會影響： **寫入訪問** 建立新實體（例如傳送、設定檔等）, **讀取存取** 要使用實體， **刪除存取權** 刪除實體。

Adobe Campaign中的預設命名權限為：

* **[!UICONTROL ADMINISTRATION]**:運算子 **[!UICONTROL ADMINISTRATION]** right對執行個體具有完整存取權。 管理員使用者可以執行/建立/編輯/刪除任何物件，例如工作流程、傳送、指令碼等。

* **[!UICONTROL APPROVAL ADMINISTRATION]**:您可以在工作流程和傳送中設定多個核准步驟，以確保目前狀態已由指派的運算子或群組核准。 具有 **[!UICONTROL APPROVAL ADMINISTRATION]** 權利可以設定批准步驟，也可以分配應批准這些步驟的操作員或操作員組。

* **[!UICONTROL CENTRAL]**:集中管理權（分散式行銷）。

* **[!UICONTROL DELETE FOLDER]**:刪除資料夾的權限。 通過此權限，用戶可以從瀏覽器視圖中刪除資料夾。

* **[!UICONTROL EDIT FOLDERS]**:更改資料夾屬性的權限，如內部名稱、標籤、關聯影像、子資料夾順序等。

* **[!UICONTROL EXPORT]**:使用者可使用，將資料從其Adobe Campaign執行個體匯出至伺服器或本機電腦上的檔案 **[!UICONTROL EXPORT]** 工作流程活動。

* **[!UICONTROL FILES ACCESS]**:通過指令碼讀取和寫入檔案的權限，該指令碼可寫入 **[!UICONTROL JavaScript]** 在伺服器上讀取/寫入檔案的工作流活動。

* **[!UICONTROL IMPORT]**:一般資料匯入的權限。 **[!UICONTROL IMPORT]** 可讓您將資料匯入任何其他表格，而 **[!UICONTROL RECIPIENT IMPORT]** right僅允許匯入收件者表格。

* **[!UICONTROL INSERT FOLDERS]**:插入資料夾的權限。 具有 **[!UICONTROL INSERT FOLDERS]** 右鍵可以在資源管理器視圖的資料夾樹中建立新資料夾。

* **[!UICONTROL LOCAL]**:當地管理權（分佈式行銷）。

* **[!UICONTROL MERGE]**:將所選記錄合併為一個記錄的權限。 如果收件者存在為重複項目，則 **[!UICONTROL MERGE]** 右側允許用戶選擇重複項，並將它們合併到主要收件人中。

* **[!UICONTROL PREPARE DELIVERIES]**:建立、編輯和儲存傳遞的權限。 具有 **[!UICONTROL PREPARE DELIVERIES]** 右側也可以啟動傳遞分析程式。

* **[!UICONTROL PRIVACY DATA RIGHT]**:收集和刪除隱私權資料的權限。 [了解更多資訊](privacy.md)。

* **[!UICONTROL PROGRAM EXECUTION]**:用各種寫程式語言執行命令的權利。

* **[!UICONTROL RECIPIENT IMPORT]**:匯入收件者的權限。 具有 **[!UICONTROL RECIPIENT IMPORT]** 右側可將本機檔案匯入收件者表格。

* **[!UICONTROL SQL SCRIPT EXECUTION]** 直接在資料庫上執行任何SQL命令的權限。

* **[!UICONTROL START DELIVERIES]**:核准先前分析的傳送的權限。 傳送分析後，傳送會在各種核准步驟暫停，且需要獲得核准才能繼續。 具有 **[!UICONTROL START DELIVERIES]** 允許核准傳遞的權限。

* **[!UICONTROL USE SQL DATA MANAGEMENT ACTIVITY]**:使用SQL資料管理活動編寫您自己的SQL指令碼，以便建立和填充工作表。 [了解更多資訊](../../automation/workflow/sql-data-management.md)。

* **[!UICONTROL WORKFLOW]**:此命名權限專供工作流程使用：它可讓您建立、開始和停止工作流程。 需要有工作流檔案的讀取權限才能適用已命名的權限。 針對目標工作流程，請直接閱讀 **[!UICONTROL Profiles and Targets]** 資料夾。


* **[!UICONTROL WEBAPP]**:使用Web應用程式的權限。

>[!NOTE]
>
>此清單會因環境上安裝的附加元件而異。



## 額外資源{#additional-res}

* [管理工作流程的權限](../../automation/workflow/managing-rights.md)
* [管理分散式行銷的權限](../../automation/distributed-marketing/about-distributed-marketing.md#operators)
* [管理互動模組的權限](../interaction/interaction-operators.md)
* [篩選結構存取權](../dev/filter-schema.md)
* [限制 PI 檢視](../dev/restrict-pi-view.md)
