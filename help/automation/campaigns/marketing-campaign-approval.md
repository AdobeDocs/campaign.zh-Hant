---
product: campaign
title: 設定及管理核准流程
description: 瞭解如何管理行銷活動的核准
feature: Approvals, Campaigns
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 03be5058-436e-4de9-99a7-91d799aa17f6
source-git-commit: 24ecf598d3d01f7fb59c70e1c8c81e9c086e653e
workflow-type: tm+mt
source-wordcount: '2279'
ht-degree: 1%

---

# 設定及管理核准流程 {#approval-marketing-campaigns}

每個組織都必須有專屬的行銷活動建立與核准方法與人員。 行銷活動核准流程涉及協調多個利害關係人：數位行銷人員、傳遞經理、內容經理以及外部擁有者，例如合作夥伴或供應商。

透過Adobe Campaign，您可以設定行銷活動的核准流程，並在需要動作時通知操作者。 您可以為傳送的每個步驟定義核准：目標定位、內容、預算、摘取和證明傳送。 當您的行銷活動傳遞通過各種驗證步驟時，Adobe Campaigns會編譯修改和簽出的歷史記錄，包括意見回饋、評論、變更請求和評論。

通知訊息會傳送給指定為稽核者的Adobe Campaign操作者，以通知他們核准請求。


操作員可透過數種方式核准：

* 來自通知訊息。 電子郵件中的連結會透過網頁瀏覽器將運運算元傳送至Campaign。 連線之後，檢閱者可以選擇核准或不核准內容。
  ![](assets/approval-content-email.png)

* 從行銷活動控制面板。
  ![](assets/approval-from-dashboard.png)

* 從傳遞控制面板。
  ![](assets/approval-from-delivery-dashboard.png)

操作員可以從核准視窗存取行銷活動和傳遞。 他們也可以輸入註解。

![](assets/approval-target-confirm.png)

操作員驗證後，資訊會顯示在行銷活動和傳遞控制面板以及記錄中。

![](assets/approvals-from-delivery.png)

此資訊也可在傳送的核准記錄檔和行銷活動的核准日誌中取得。 這些記錄檔是透過&#x200B;**[!UICONTROL Edit > Audit > Approvals]**&#x200B;索引標籤進行存取。

![](assets/approval-logs.png)


## 啟用核准{#enable-approvals}

核准通知會傳送給每個已啟用核准之處理作業受影響的操作者。

它們可以在行銷活動範本、每個行銷活動個別或傳送時啟用。

所有需要核准的工作都會透過&#x200B;**[!UICONTROL Properties]** > **[!UICONTROL Advanced campaign parameters...]** > **[!UICONTROL Approvals]**&#x200B;索引標籤在行銷活動範本中選取。 會從此標籤中選取稽核者或稽核者群組。 他們會收到通知，除非未啟用此選項。 [了解更多](#approving-processes)。

您可以為使用此範本建立的每個行銷活動覆寫這些設定，也可以為每個傳遞個別覆寫。 瀏覽傳遞的&#x200B;**[!UICONTROL Properties]**&#x200B;按鈕，然後瀏覽&#x200B;**[!UICONTROL Approvals]**&#x200B;索引標籤。

在下列範例中，傳遞內容不需要核准：

![](assets/approval-not-enabled.png)


>[!CAUTION]
>
>檢查檢閱者是否具有核准的&#x200B;**適當許可權**，以及其安全區域是否已正確定義。 [了解更多](#selecting-reviewers)。

傳遞的核准程式在[本節](#review-and-approve-deliveries)中有詳細說明。

## 選取檢閱者 {#select-reviewers}

對於每種核准型別，會從傳送的下拉式清單中選取負責核准的運運算元或運運算元群組。 可使用&#x200B;**[!UICONTROL Edit...]**&#x200B;連結新增更多運運算元。 此視窗也可讓您編輯核准期限。 依預設，稽核者從提交日期起有三天可核准程式。 若要新增自動提醒，請使用&#x200B;**[!UICONTROL Add a reminder]**&#x200B;連結。

![](assets/add-reviewers.png)

如果未指定稽核者，則行銷活動擁有者會負責核准並接收通知。 行銷活動擁有者在行銷活動的&#x200B;**[!UICONTROL Edit > Properties]**&#x200B;索引標籤中指定：

![](assets/campaign-owner.png)

其他所有具有&#x200B;**[!UICONTROL Administrator]**&#x200B;許可權的Adobe Campaign運運算元也可以核准工作，但他們不會收到通知。

>[!NOTE]
>
>依預設，如果已定義核准操作員，行銷活動擁有者無法執行核准或開始傳送。 作為Adobe Campaign管理員，您可以建立設定為&#x200B;**1**&#x200B;的&#x200B;**NmsCampaign_Activate_OwnerConfirmation**&#x200B;選項，修改此行為並允許行銷活動擁有者核准/開始傳遞。


如果已定義稽核者清單，當稽核者核准某個工作時，就會核准該工作。 行銷活動和傳遞控制面板中不再提供核准連結。 啟用通知傳送後，如果其他複查者按一下通知訊息中的核准連結，就會通知他們其他操作員已核准該工作。

![](assets/delivery-target-already-approved.png)


## 檢閱及核准傳遞 {#review-and-approve-deliveries}

您可以針對每個行銷活動，核准傳遞目標、[傳遞內容](#approving-content)和成本。 可以透過電子郵件形式通知負責核准的Adobe Campaign操作者，然後他們可透過使用者端主控台或網路連線核准或拒絕核准。 [了解更多](#approving-processes)。

如果是直接郵件傳送，Adobe Campaign操作員可在解壓縮檔案傳送給路由器之前檢視解壓縮檔案，並可視需要變更格式及重新啟動解壓縮。 [了解更多](#approve-an-extraction-file)。

完成這些驗證階段後，即可啟動傳遞。 [了解更多](marketing-campaign-deliveries.md#starting-a-delivery)。

>[!NOTE]
>
>在行銷活動範本中選取需要核准的程式。 [了解更多](marketing-campaign-templates.md)。
>

### 核准傳遞的步驟 {#approving-processes}

需要核准的階段會出現在行銷活動控制面板上（透過使用者端主控台或網頁介面）。 它們也會出現在傳送追蹤表格和傳送控制面板上。

![](assets/delivery-approval-actions.png)

對於行銷活動中的每個傳遞，您可以核准下列流程：

* **目標定位、內容和預算**

  在核准設定視窗中選取&#x200B;**[!UICONTROL Enable target approval]**、**[!UICONTROL Enable content approval]**&#x200B;或&#x200B;**[!UICONTROL Enable budget approval]**&#x200B;選項時，相關連結會顯示在行銷活動和傳遞控制面板中。

  ![](assets/template-activate-6.png)

  >[!NOTE]
  >
  >只有在核准設定視窗中啟用目標核準時，才能使用預算核准。 只有在分析目標之後，才會顯示預算核准連結。

  如果在核准設定視窗中選取&#x200B;**[!UICONTROL Assign content editing]**&#x200B;或&#x200B;**[!UICONTROL External content approval]**&#x200B;選項，儀表板將會顯示&#x200B;**[!UICONTROL Available content]**&#x200B;和&#x200B;**[!UICONTROL External content approval]**&#x200B;連結。

  內容核准可讓您存取已傳送的校樣。

* **摘取核准（直接郵件傳遞）**

  在核准設定視窗中選取&#x200B;**[!UICONTROL Enable extraction approval]**&#x200B;時，擷取的檔案必須先核准，才能通知路由器。

  **[!UICONTROL Approve file]**&#x200B;選項適用於行銷活動和傳遞控制面板。

  ![](assets/approve-file-preview.png)

  您可以在驗證之前預覽輸出檔案。 擷取檔案預覽只會顯示資料範例。 未載入整個檔案。

* **核准關聯的傳遞**

  **[!UICONTROL Enable individual approval of each associated delivery]**&#x200B;選項用於與次要傳遞相關的主要傳遞。 依預設，不會選取此選項，因此可以執行主要傳送的整體核准。 如果選取此選項，則必須個別核准每個傳遞。

  ![](assets/enable-ind-approval.png)


>[!NOTE]
>
>在目標定位工作流程中，如果訊息準備期間發生連結至設定問題的錯誤，控制面板上會顯示&#x200B;**[!UICONTROL Restart message preparation]**&#x200B;連結。 修正錯誤，並使用此連結在略過目標階段時重新啟動訊息準備。


### 核准內容 {#approve-content}

>[!CAUTION]
>
>若要核准內容，校訂週期是強制性的。 校樣可讓您核准資訊顯示、個人化資料並檢查連結是否正常運作。
>
>下文詳述的內容核准功能與證明傳送有關。

您可以設定內容核准週期。 若要這麼做，請在核准設定視窗中選取&#x200B;**[!UICONTROL Enable content approval]**&#x200B;選項。 內容核准週期的主要步驟如下：

1. 建立新傳遞後，行銷活動經理按一下行銷活動控制面板上的&#x200B;**[!UICONTROL Submit content]**&#x200B;連結，以開始內容核准週期。

   >[!NOTE]
   >
   >如果在核准設定視窗中選取&#x200B;**[!UICONTROL Enable the sending of proofs]**&#x200B;選項（用於電子郵件傳遞）或&#x200B;**[!UICONTROL Enable the sending and approval of proofs]**&#x200B;選項（用於直接郵件傳遞），則會自動傳送校樣。

1. 系統會傳送通知電子郵件給負責內容的人員，由其選擇是否核准：

   * 透過通知電子郵件：通知電子郵件包含已傳送證明的連結，而且如果針對此執行個體啟用&#x200B;**傳遞能力**&#x200B;附加元件，則可能會包含各種網頁郵件的郵件轉譯連結。

   * 透過使用者端主控台或網頁介面、傳遞追蹤、傳遞控制面板或行銷活動控制面板。 此行銷活動儀表板可讓您按一下&#x200B;**[!UICONTROL Inbox rendering...]**&#x200B;連結，以檢視已傳送的校樣清單。 若要檢視其內容，請按一下清單右側的&#x200B;**[!UICONTROL Detail]**&#x200B;圖示。

1. 系統會傳送通知電子郵件給行銷活動的負責人，通知其內容是否已核准。 行銷活動的負責人可以隨時重新開始內容核准週期。 若要這麼做，請按一下行銷活動控制面板&#x200B;**[!UICONTROL Content status]**&#x200B;行上的連結（在傳遞層級），然後按一下&#x200B;**[!UICONTROL Reset content approval to submit it again]**。

#### 指派內容編輯 {#assign-content-editing}

此選項可讓您定義負責內容編輯的人員，例如網站管理員。 如果在核准設定視窗中選取&#x200B;**[!UICONTROL Assign content editing]**&#x200B;選項，則在傳遞建立與將通知電子郵件傳送給內容負責人之間會新增幾個核准步驟：

1. 建立新傳遞後，行銷活動負責人按一下行銷活動控制面板中的&#x200B;**[!UICONTROL Submit content editing]**&#x200B;連結，以開始內容編輯週期。

1. 負責內容編輯的人員會收到電子郵件，通知他們內容可用。

1. 接著，他們可以登入Client Console、開啟傳遞，並使用簡化的精靈進行編輯，以變更主題、HTML和文字內容，以及傳送校樣。

   >[!NOTE]
   >
   >如果在核准設定視窗中選取&#x200B;**[!UICONTROL Enable the sending of proofs]**&#x200B;選項（用於電子郵件傳遞）或&#x200B;**[!UICONTROL Enable the sending and approval of proofs]**&#x200B;選項（用於直接郵件傳遞），則會自動傳送校樣。

1. 當負責內容編輯的人員完成傳送內容的任何變更後，他們就可以提供內容。

   為此，他們可以使用：

   * Adobe Campaign使用者端主控台中的&#x200B;**[!UICONTROL Available content]**&#x200B;連結。
   * 通知訊息中的連結。
操作員可在將內容提交至行銷活動負責人之前新增評論。
通知訊息可讓稽核者核准或拒絕內容。

#### 外部內容核准 {#external-content-approval}

此選項可讓您定義負責核准傳遞呈現（例如品牌通訊一致性、費率等）的外部運運算元。 在核准設定視窗中選取&#x200B;**[!UICONTROL External content approval]**&#x200B;選項時，在內容核准與將通知傳送給行銷活動負責人之間會新增數個核准步驟：

1. 外部內容管理員會收到通知電子郵件，告知他們內容已核准並請求外部核准。
1. 通知電子郵件包含已傳送校樣的連結（可讓您檢視傳遞呈現），以及核准或拒絕傳遞內容的按鈕。

只有在已傳送一或多個校樣時，才可使用這些連結。 否則，傳遞呈現只能透過使用者端主控台或網頁介面使用。

### 核准擷取檔案 {#approve-an-extraction-file}

對於離線傳遞，Adobe Campaign會產生擷取檔案，並依據其設定方式傳送至路由器。 其內容取決於所使用的匯出範本。

核准內容、目標定位和預算後，傳遞會變更為&#x200B;**[!UICONTROL Extraction pending]**，直到啟動行銷活動的擷取工作流程為止。

在擷取請求日期建立擷取檔案，且傳遞狀態變更為&#x200B;**[!UICONTROL File to approve]**。

您可以檢視擷取檔案的內容（按一下其名稱）、核准該檔案，或視需要變更格式，然後使用控制面板上的連結來重新啟動擷取。

一旦檔案獲得核准，您就可以將通知電子郵件傳送給路由器。 [了解更多](marketing-campaign-deliveries.md#start-an-offline-delivery)。

## 核准模式 {#approval-modes}

可以在行銷活動控制面板、傳遞追蹤標籤、傳遞控制面板或傳送給稽核者的電子郵件通知中核准工作。

### 在儀表板中核准 {#approval-via-the-dashboard}

若要透過使用者端主控台或網頁介面核准工作，請按一下行銷活動控制面板上的適當連結。

例如，執行傳遞分析後：

1. 選取 **[!UICONTROL Approve targeting]**。

![](assets/target-validation-from-console.png)

1. 在快顯視窗中，檢查要核准的資訊。
1. 選取&#x200B;**[!UICONTROL Accept]**&#x200B;或&#x200B;**[!UICONTROL Reject]**，並視需要輸入註解。 此註解會顯示在驗證記錄檔中。
1. 使用&#x200B;**[!UICONTROL Target approval]**&#x200B;按鈕確認您的選擇。

![](assets/confirm-validation-from-console.png)


如果某個程式已由另一個操作員核准，則無法使用核准連結。

如果處理遭到拒絕，則會在傳遞控制面板中顯示資訊，如下所示：

![](assets/target-approval-rejected.png)


### 從通知訊息核准 {#approval-via-notification-messages}

若要核准來自[通知訊息](#notifications)的工作：

1. 按一下通知中的連結。
1. 登入Adobe Campaign。
1. 檢查要核准的資訊
1. 選取&#x200B;**[!UICONTROL Accept]**&#x200B;或&#x200B;**[!UICONTROL Reject]**，並視需要輸入註解。
1. 驗證。 您的選擇和註解會顯示在驗證記錄中。

>[!NOTE]
>
>如果處理期間出現警告，通知中會顯示警告。

### 追蹤核准{#approval-tracking}

使用者介面中提供核准記錄：

* 在行銷活動核准記錄中，**[!UICONTROL Edit > Audit]**&#x200B;索引標籤的&#x200B;**[!UICONTROL Approvals]**&#x200B;子索引標籤：

  ![](assets/approval-tracking-from-campaign.png)

* 在行銷活動傳遞記錄中，**[!UICONTROL Edit > Audit]**&#x200B;索引標籤的&#x200B;**[!UICONTROL Deliveries]**&#x200B;子索引標籤：

  ![](assets/approval-tracking-from-campaign-deliveries.png)

* 按一下&#x200B;**[!UICONTROL Summary]**&#x200B;索引標籤的&#x200B;**[!UICONTROL Hide/display logs]**&#x200B;選項，即可檢視每個傳遞的核准狀態。

  ![](assets/approval-tracking-delivery-dashboard.png)

* 也可以透過每個傳遞的&#x200B;**[!UICONTROL Audit > Approvals]**&#x200B;索引標籤存取此資訊：

  ![](assets/approval-tracking-delivery-tab.png)

>[!NOTE]
>
>操作員核准或拒絕工作後，其他稽核者就無法再變更它。

### 自動/手動核准 {#automatic-and-manual-approval}

建立目標定位工作流程時，如果核准是自動的（預設模式），Adobe Campaign會顯示核准連結，或在需要核準時立即傳送通知。

若要選擇核准模式（手動或自動），請按一下行銷活動或行銷活動範本的&#x200B;**[!UICONTROL Edit > Properties]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL Advanced campaign parameters...]**，最後按一下&#x200B;**[!UICONTROL Approvals]**&#x200B;標籤。
par
![](assets/approval-mode.png)

>[!NOTE]
>
>核准模式會套用至行銷活動的所有傳送。

建立目標工作流程時，手動核准可讓您避免建立核准連結或自動傳送通知。 行銷活動儀表板接著會提供&#x200B;**[!UICONTROL Submit targeting for approval]**&#x200B;連結，以手動啟動核准程式。

確認訊息可讓您針對針對針對此傳遞選取的工作，授權核准。

核准按鈕接著會顯示在行銷活動控制面板（適用於此傳遞）、傳遞控制面板以及傳遞追蹤中。 如果已啟用通知，則會同時傳送通知。

這種啟用核准的方法可讓您進行目標定位，而不會向稽核者傳送虛假通知。

## 通知 {#notifications}

通知是傳送給稽核者的特定電子郵件訊息，通知他們流程正在等待核准。 當操作員按一下訊息中的連結時，驗證頁面就會顯示，在登入之後，操作員就可以檢視資訊，並核准或拒絕工作。 您也可以在核准視窗中輸入註解。

通知電子郵件的內容可以是個人化的。 檢視[通知內容](#notification-content)。

### 啟用/停用通知 {#enabling-disabling-notification}

依預設，如果在行銷活動範本、行銷活動或傳遞中啟用相關工作的核准，則會傳送通知訊息。 但是，可以停用通知，以僅授權來自使用者端主控台的核准。

若要這麼做，請編輯行銷活動或行銷活動範本的核准期間（ **[!UICONTROL Edit > Properties]** > **[!UICONTROL Advanced campaign parameters...]** > **[!UICONTROL Approvals]**&#x200B;標籤）並選取&#x200B;**[!UICONTROL Do not enable notification sending]**。

![](assets/enable-disable-notifications.png)

### 通知內容 {#notification-content}

通知內容已在特定範本中定義： **[!UICONTROL Notification of validations for the marketing campaign]**。 此範本儲存在Adobe Campaign樹狀結構的&#x200B;**[!UICONTROL Administration > Campaign management > Technical delivery templates]**&#x200B;資料夾中。
