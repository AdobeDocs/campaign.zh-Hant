---
title: 授予市場活動v8的權限
description: 瞭解如何向Campaign v8用戶授予權限
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

## 添加用戶 {#add-users}

作為產品管理員，您可以添加用戶並授予市場活動訪問權限。

要添加用戶，請執行以下步驟：

1. 在 [Admin Console](https://adminconsole.adobe.com/enterprise){target="_blank"} 首頁，選擇 **添加用戶**。

   ![](assets/add-a-user.png)

1. 輸入用戶的電子郵件地址。
1. 使用「+」符號選擇要分配給用戶的產品配置檔案或用戶組。

   ![](assets/add-a-product-profile.png)

   市場活動內置產品配置檔案列於 [此部分](#ootb-productprofiles)。

   瞭解如何在 [此部分](#user-groups)

1. 按一下「**儲存**」。用戶即被添加，並顯示在「用戶」清單中。 如果將管理員角色或產品配置檔案分配給用戶，則用戶將收到電子郵件通知。 用戶必須遵循該連結才能完成其配置檔案。

瞭解有關在Admin Console中建立用戶的詳細資訊 [此頁](https://helpx.adobe.com/ie/enterprise/using/manage-users-individually.html){target="_blank"}。

當新用戶 [登錄市場活動](connect.md) 通過他們的Adobe ID，他們將被添加到客戶機控制台的Campaigon操作員清單中。 市場活動運算子儲存在 **[!UICONTROL Administration > Access management > Operators]** 市場活動瀏覽器的資料夾。

## 使用產品配置檔案{#product-profiles}

使用產品配置檔案來賦予用戶產品中包含的功能。

* 對於Admin Console上的每個產品，您可以建立一個或多個產品配置檔案。
* 在每個產品配置檔案中，您分配用戶和用戶組（在組織中）。
* 當用戶使用在產品配置檔案中指定的憑據登錄時，授予他們對產品配置檔案所基於的產品的應用和服務的訪問權限。

這些產品配置檔案與儲存在 **[!UICONTROL Administration > Access management > Operator groups]** 市場活動瀏覽器的資料夾。

在Admin Console中，產品配置檔案使用以下語法：

活動 —  `<your instance>`  — 操作員組的內部名稱

例如， **交貨操作員** test實例中的組，Admin Console中的產品配置檔案是：

市場活動 — test — 交付

可以使用預設產品配置檔案或建立新配置檔案。

### 建立產品配置檔案{#create-product-profile}

要將新產品配置檔案添加到Adobe中，必須先在市場活動客戶端控制台中建立它，然後在Admin Console中添加它。

例如，要建立「審閱者」產品配置檔案，請執行以下步驟。

#### 在市場活動中建立操作員組{#create-op-group}

1. 連接到市場活動，開啟瀏覽器，瀏覽到 **[!UICONTROL Administration > Access management > Operator groups]**。
1. 按一下 **[!UICONTROL New]**，並定義運算子組的名稱並設定其內部名稱(&#39;reivers&#39;)。
   ![](assets/new-op-group.png)
1. 通過選擇命名權限定義關聯權限。 命名權限詳見 [此部分](#use-named-rights)
1. 保存新運算子組。

#### 在Admin Console中建立產品配置檔案{#create-profile-in-admin-console}

1. 連接到 [Admin Console](https://adminconsole.adobe.com/enterprise){target="_blank"}。
1. 從 **產品和服務** 開啟市場活動產品。
1. 按一下 **新建配置檔案** 並輸入要建立的產品配置檔案的名稱，其語法完全正確 [這裡](#product-profiles)。 例如，我們輸入：活動 —  `<your-instance-name>`  — 審閱者

   ![](assets/new-product-profile-ui.png)

1. 儲存您的變更。

您現在可以將用戶添加到此新產品配置檔案中，如中所述 [此部分](#add-users)。

最佳做法是將產品配置檔案分配給用戶組。 按用戶管理權限不是一種可持續的模型。


### 預設產品配置檔案和操作員組 {#ootb-productprofiles}

Adobe Campaign內置 **產品配置檔案** 在Adobe啟用環境時定義。

![](assets/ootb-product-profiles.png)

這些產品配置檔案與市場活動匹配 **運算子組**。 預設運算子組及其 [命名權限](#use-named-rights) 下面列出：

1. **[!UICONTROL Administrator]** （管理員）

   此組中的運算子對實例具有完全訪問權限。 管理員是可以訪問用戶介面中技術最為完善部分的用戶。

   此組包含以下命名權限：

   * **[!UICONTROL ADMINISTRATION]**:執行/建立/編輯/刪除任何對象（如工作流、交付、指令碼等）的權限。

1. **[!UICONTROL Delivery operators]** (配送)

   此組中的操作員負責管理交貨：它們允許訪問建立和準備交貨所需的主要資源（市場活動類型、交貨映射、預設模板、個性化塊等）。

   此組包含以下命名權限：

   * **[!UICONTROL PREPARE DELIVERIES]**:建立、編輯和啟動交付分析，
   * **[!UICONTROL START DELIVERIES]**:批准先前分析的交貨的權利。

1. **[!UICONTROL Campaign managers]** （操作）

   此組中的操作員可以管理市場營銷活動：它允許您訪問連結到市場活動（計畫、計畫、工作流、預算等）的對象。 在 **[!UICONTROL Campaign]** (可選的Adobe Campaign模組)。

   此組包含以下命名權限：

   * **[!UICONTROL INSERT FOLDERS]**:將資料夾插入Adobe Campaign樹（前提是您對相關分支具有編輯權限）,
   * **[!UICONTROL WORKFLOW]**:有權使用工作流。

   >[!NOTE]
   >
   >此組不允許操作員開始交貨。

1. **[!UICONTROL Content contributors]** （內容）

   此組中的用戶可以在 **[!UICONTROL Content management]** 附件。 此組不授予任何其他權限。

1. **[!UICONTROL Access to reports]** （報告）

   此組保留給外部操作員，以便通過 [Web訪問](../start/campaign-ui.md#web-browser)。

1. **[!UICONTROL Workflow execution]** （工作流）

   的 **[!UICONTROL Workflow execution]** 組用於控制目標工作流的執行和批准：名為right的工作流已映射到此組的運算子。 除了對資料檔案的訪問權限之外，工作流上的所有操作都需要此選項。 預設情況下， **[!UICONTROL Workflow execution]** 組具有對標準目標工作流檔案和工作流模板的只讀訪問權限。 此組中的操作員也具有對待處理批准檔案的讀寫權限。

1. **[!UICONTROL Workflow supervisors]** （工作流主管）

   此組中的用戶管理工作流批准，並在出現有關市場活動工作流的警報時接收電子郵件通知。

1. **本地/中央管理** （中央/本地）

   此組中的用戶可以使用 **[!UICONTROL Distributed marketing]** 附件。

1. **[!UICONTROL Offer managers]** (優惠)

   使用「交互」(Interaction)載入項時，該組中的運算子可以建立和維護聘用。 [了解更多](../interaction/interaction-operators.md)。

   此組包含以下命名權限：

   * **[!UICONTROL INSERT FOLDERS]**:將資料夾插入Adobe Campaign樹（前提是您對相關分支具有編輯權限）,
   * **[!UICONTROL EDIT FOLDERS]**:更改資料夾屬性（如內部名稱、標籤、關聯影像、子資料夾順序等）的權限。

   分配給聘用經理的權限使他們能夠執行以下任務：

   * 修改 **[!UICONTROL Design]** 環境。
   * 視圖 **[!UICONTROL Live]** 環境。
   * 配置管理函式（預定義的空格和篩選器）。
   * 建立和更新類別。
   * 建立優惠.
   * 配置優惠資格。
   * 批准聘用。

   >[!NOTE]
   >
   >**提供經理** 僅當未指定審閱者或在聘用模板中將其設定為審閱者時，才能批准聘用。

   在中提供了每個環境的服務經理權限清單 [此頁](../interaction/interaction-operators.md#recap-of-rights-according-to-operator)。

## 使用用戶組{#user-groups}

您可以使用Admin Console建立用戶組並將用戶分配給它們。

用戶組是不同用戶的集合，這些用戶必須獲得一組共用權限。 瞭解如何在 [此部分](https://helpx.adobe.com/ie/enterprise/using/user-groups.html){target="_blank"}。

您可以將產品配置檔案分配給用戶組。 因此，該組中的所有用戶都要接收相同的產品權限集。

## 已命名的權限{#use-named-rights}

Adobe Campaign提供了一組命名權限，您可以定義分配給用戶和組的權限。 可從 **[!UICONTROL Administration > Access management > Named rights]** 市場活動瀏覽器的資料夾。

命名權限授予：

* 執行操作例如， **分析** 按鈕 **交貨操作員** 具有 **準備交付** 右命名

* 訪問資料夾操作員組的成員資格可以通過更改資料夾的安全設定來授予或限制對資料夾的訪問權限。 [了解更多](folder-permissions.md#restrict-access-to-a-folder)。

   例如，它可能會影響： **寫入訪問** 建立新實體（如交貨、配置檔案等）, **讀取訪問** 使用實體， **刪除訪問權限** 的子菜單。

Adobe Campaign中的預設命名權限為：

* **[!UICONTROL ADMINISTRATION]**:具有 **[!UICONTROL ADMINISTRATION]** right對實例具有完全訪問權限。 管理員用戶可以執行/建立/編輯/刪除任何對象，如工作流、交付、指令碼等。

* **[!UICONTROL APPROVAL ADMINISTRATION]**:您可以在工作流和交貨中設定多個審批步驟，以確保當前狀態已經由分配的操作員或組審批。 具有 **[!UICONTROL APPROVAL ADMINISTRATION]** right可以設定批准步驟，還可以分配應批准這些步驟的操作員或操作員組。

* **[!UICONTROL CENTRAL]**:中央管理權限（分佈式營銷）。

* **[!UICONTROL DELETE FOLDER]**:刪除資料夾的權限。 通過此權限，用戶可以從瀏覽器視圖中刪除資料夾。

* **[!UICONTROL EDIT FOLDERS]**:更改資料夾屬性（如內部名稱、標籤、關聯影像、子資料夾順序等）的權限。

* **[!UICONTROL EXPORT]**:用戶可以使用以下命令將資料從其Adobe Campaign實例導出到伺服器或本地電腦上的檔案 **[!UICONTROL EXPORT]** 工作流活動。

* **[!UICONTROL FILES ACCESS]**:通過指令碼對檔案進行讀寫訪問的權限，該指令碼可以寫入 **[!UICONTROL JavaScript]** 用於讀取/寫入伺服器上的檔案的工作流活動。

* **[!UICONTROL IMPORT]**:用於通用資料導入的權限。 **[!UICONTROL IMPORT]** 允許將資料導入任何其它表，而 **[!UICONTROL RECIPIENT IMPORT]** 僅允許導入到收件人表。

* **[!UICONTROL INSERT FOLDERS]**:插入資料夾的權限。 具有 **[!UICONTROL INSERT FOLDERS]** 在「資源管理器」視圖的資料夾樹中，「權限」可以建立新資料夾。

* **[!UICONTROL LOCAL]**:本地管理權（分佈式營銷）。

* **[!UICONTROL MERGE]**:將選定記錄合併到一個記錄中的權限。 如果收件人作為重複項存在， **[!UICONTROL MERGE]** 右側允許用戶選擇重複項並將它們合併到主收件人中。

* **[!UICONTROL PREPARE DELIVERIES]**:建立、編輯和保存交貨的權限。 具有 **[!UICONTROL PREPARE DELIVERIES]** right也可以啟動交貨分析流程。

* **[!UICONTROL PRIVACY DATA RIGHT]**:收集和刪除隱私資料的權利。 [了解更多](privacy.md)。

* **[!UICONTROL PROGRAM EXECUTION]**:以各種寫程式語言執行命令的權利。

* **[!UICONTROL RECIPIENT IMPORT]**:導入收件人的權限。 具有 **[!UICONTROL RECIPIENT IMPORT]** 權限可以將本地檔案導入收件人表中。

* **[!UICONTROL SQL SCRIPT EXECUTION]** 有權直接在資料庫上執行任何SQL命令。

* **[!UICONTROL START DELIVERIES]**:批准先前分析的交貨的權利。 在交付分析後，交付將在各個審批步驟中暫停，並需要獲得批准才能恢復。 具有 **[!UICONTROL START DELIVERIES]** 允許批准交貨。

* **[!UICONTROL USE SQL DATA MANAGEMENT ACTIVITY]**:使用SQL資料管理活動編寫自己的SQL指令碼以建立和填充工作表。 [了解更多](../../automation/workflow/sql-data-management.md)。

* **[!UICONTROL WORKFLOW]**:此命名權限特定於工作流：它允許您建立、啟動和停止工作流。 要適用命名權限，需要對工作流檔案進行讀取權限。 對於目標工作流， **[!UICONTROL Profiles and Targets]** 資料夾。


* **[!UICONTROL WEBAPP]**:有權使用Web應用程式。

>[!NOTE]
>
>此清單可能因環境中安裝的載入項而異。



## 額外資源{#additional-res}

* [管理工作流的權限](../../automation/workflow/managing-rights.md)
* [管理分佈式市場營銷的權限](../../automation/distributed-marketing/about-distributed-marketing.md#operators)
* [管理交互模組的權限](../interaction/interaction-operators.md)
* [篩選對架構的訪問](../dev/filter-schema.md)
* [限制 PI 檢視](../dev/restrict-pi-view.md)
