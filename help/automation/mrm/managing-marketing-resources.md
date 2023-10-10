---
product: campaign
title: 管理行銷資源
description: 瞭解如何管理行銷資源
role: User
exl-id: 4d91fb7d-f846-4644-b83d-5a6a988ae297
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '1111'
ht-degree: 1%

---

# 管理行銷資源{#managing-marketing-resources}

使用Adobe Campaign管理和追蹤行銷活動生命週期中涉及的行銷資源。 這些行銷資源可以是白皮書、資料檔案、標誌或與行銷活動相關的任何其他資產。

對於透過Adobe Campaign管理的每個行銷資源，您可以隨時追蹤其狀態和歷史記錄，並檢視目前版本。

根據預設，行銷資源儲存在 **[!UICONTROL MRM > Marketing resources]** Campaign檔案總管的資料夾。

## 新增行銷資源 {#adding-a-marketing-resource}

若要新增行銷資源，請遵循下列步驟：

1. 瀏覽至 **[!UICONTROL Campaigns]** 標籤，然後選取 **[!UICONTROL Marketing resouces]**.

1. 按一下 **[!UICONTROL Create]** 按鈕。
   ![](assets/add-a-mkt-resource.png)
1. 在「行銷資源」視窗中拖放檔案，將其上傳至Campaign伺服器。 您也可以使用 **[!UICONTROL Upload file to server...]** 連結。
   ![](assets/mkt-resource-creation.png)

上傳完成後，資源會新增至可用資源清單中。

## 管理行銷資源 {#manage-marketing-resources}

上傳後，所有Adobe Campaign操作員都可使用行銷資源。 他們可以檢視、製作復本以修改檔案，或更新伺服器上的檔案。

![](assets/open-a-marketing-resource.png)

使用 **[!UICONTROL Assigned to]** 中的下拉式清單 **[!UICONTROL Edit]** 定位字元以選取負責資源的運運算元。

![](assets/assign-a-mkt-resource.png)

您也可以選取負責資源驗證和資源發佈的運運算元或運運算元群組。 若要存取這些選項，請按一下  **[!UICONTROL Advanced parameters]** 連結。

啟動資源驗證程式時，會以電子郵件通知這些操作者。

如果未選取稽核者，則資源 **[!UICONTROL cannot be]** 待核准。

使用 **[!UICONTROL Audit]** 按Tab鍵以新增校訂閱讀器並定義資源的可用日期。 在此日期之後，它會顯示為 **[!UICONTROL Late]** 狀態。

>[!NOTE]
>
>此 **[!UICONTROL History]** 索引標籤包含資源的下載和更新記錄。 此 **[!UICONTROL Details]** 按鈕可讓您檢視選取的版本。
>
>此 **[!UICONTROL Audit]** 索引標籤可讓您監視對資源執行的任何動作：核准、拒絕核准、相關註解或出版物。

### 鎖定/解除鎖定資源 {#locking-unlocking-a-resource}

建立之後，行銷資源儀表板中就會提供資源，操作員可以編輯和修改資源。

當運運算元開始處理資源時，最佳實務是鎖定該資源，以防止其他運運算元同時修改資源。 接著會保留資源：它仍可存取，但無法由其他運運算元在伺服器上發佈或更新。

只有當行銷資源未核準時，才能鎖定該資源。

若要鎖定資源，您必須按一下 **[!UICONTROL Lock]** 按鈕。

![](assets/lock-a-resource.png)


更新資源後，按一下 **[!UICONTROL Lock]** 按鈕可供所有操作者再次使用。

特殊訊息會通知任何嘗試存取該訊息的操作者：

![](assets/mkt-resource-locked.png)

此 **[!UICONTROL Tracking]** 定位字元表示鎖定資源的操作員名稱。

![](assets/mkt-resource-audit-tab.png)


>[!NOTE]
>
>只有鎖定資源的操作員與具有管理員許可權的操作員才有權解鎖資源。

### 論壇 {#discussion-forums}

對於每個資源， **[!UICONTROL Forum]** 索引標籤可讓參與者共用資訊。

![](assets/mkt-resource-forum.png)

進一步瞭解 [論壇](discussion-forums.md) 區段。

### 核准流程 {#approval-process}

資源詳細資料中會顯示預期的可用日期(若已在 **[!UICONTROL Tracking]** 標籤。 一旦達到此日期，您就可以使用 **[!UICONTROL Submit for approval]** 按鈕。 然後，資源狀態會變更為 **[!UICONTROL Approval in progress]**.

若要核准資源，請按一下 **[!UICONTROL Approve the resource]** 按鈕。

![](assets/mkt-resouce-approve.png)

然後，授權的操作員可以接受或拒絕核准。 這個動作是可能的：透過傳送的電子郵件訊息（按一下通知訊息中的連結），或透過使用者端主控台(按一下 **[!UICONTROL Approve]** )按鈕。

核准視窗可讓您輸入註解。

![](assets/mkt-resource-approval-confirmation.png)

瀏覽至 **[!UICONTROL Tracking]** 索引標籤以檢查核准。

>[!NOTE]
>
>除了為每個行銷資源指定的檢閱者之外，具有管理員許可權的操作者和資源管理員也被授權核准行銷資源。

### 發佈資源 {#publishing-a-resource}

核准後，必須發佈行銷資源。 發佈程式必須根據公司需求進行特定實施。 這表示資源可發佈至外部網路或任何其他伺服器，特定資訊可傳送至外部服務提供者等。

若要發佈資源，請按一下 **[!UICONTROL Publish]** 按鈕（在行銷資源控制面板的編輯區域中）。

![](assets/mkt-resource-publish.png)

您也可以透過工作流程自動發佈資源。

發佈資源即表示該資源可供使用（例如供其他任務使用）。 視您資源的性質而定，發佈內容可能會有所不同：對於傳單，發佈可能表示將檔案傳送到印表機；對於網站代理商，發佈可能表示將檔案發佈到網站等。

為了讓Adobe Campaign能夠發佈，您需要建立足夠的工作流程並將其連結至資源。 若要這麼做，請開啟 **[!UICONTROL Advanced settings...]** 方塊中，然後在中選擇所需的工作流程 **[!UICONTROL Post-processing]** 欄位。

![](assets/mkt-resource-post-processing-wf.png)

工作流程會執行：

* 當檢閱者按一下 **[!UICONTROL Publish resource]** 連結（如果未定義稽核者，則為資源負責人）。
* 如果資源是透過行銷資源建立任務進行管理，則會在任務設定為時執行 **[!UICONTROL Finished]**，只要 **[!UICONTROL Publish the marketing resource]** 方塊。 [了解更多](creating-and-managing-tasks.md#marketing-resource-creation-task))

如果未立即啟動工作流程（例如工作流程已停止），資源的狀態會變更為 **[!UICONTROL Pending publication]**. 工作流程啟動後，資源的狀態會變更為 **[!UICONTROL Published]**. 此狀態未考慮發佈程式中可能出現的錯誤。 檢查工作流程的狀態，確認工作流程已正確執行。

## 將資源連結至行銷活動 {#linking-a-resource-to-a-campaign}

### 參考行銷資源 {#referencing-a-marketing-resource}

行銷資源可與行銷活動相關聯，前提是已在以下專案中選擇此功能： [行銷活動範本](../campaigns/marketing-campaign-templates.md).

瀏覽至 **[!UICONTROL Edit > Documents > Resources]** 標籤，然後按一下 **[!UICONTROL Add]** 以選取相關資源。

![](assets/link-a-mkt-resource-to-a-campaign.png)

您可以依狀態、性質或型別篩選資源，或套用個人化篩選。

使用 **[!UICONTROL Details]** 按鈕以編輯和預覽資源。

### 將行銷資源新增至傳遞大網 {#adding-a-marketing-resource-to-a-delivery-outline}

行銷資源可以透過傳遞大網與傳遞建立關聯。

瞭解更多關於傳遞大綱，請參閱 [本節](../campaigns/marketing-campaign-deliveries.md).

若要這麼做，請以滑鼠右鍵按一下傳遞大網，然後選取 **新增>資源**.

![](assets/mkt-resource-add-in-del-outline.png)

輸入資產名稱，然後從 **行銷資源** 下拉式清單。

![](assets/mkt-resource-select-in-del-outline.png)


## 庫存管理 {#stock-management}

您可以將行銷資源與一或多個庫存建立關聯，以便管理您的供給，並在庫存不足時在控制面板上顯示警告。


若要將行銷資源與股票建立關聯，請遵循下列步驟：

1. 編輯庫存或建立新庫存。 進一步瞭解中的庫存 [本節](../campaigns/providers--stocks-and-budgets.md#stock-management).

1. 新增庫存行，並選取對應的行銷資源。

   ![](assets/mkt-resource-in-a-stock-line.png)

   您可以透過以下方式編輯所選資源： **[!UICONTROL Edit the link]** 圖示位於選取資源右側。

1. 指定初始庫存和警示庫存，然後儲存。

庫存在行銷資源中指明 **庫存** 標籤。
