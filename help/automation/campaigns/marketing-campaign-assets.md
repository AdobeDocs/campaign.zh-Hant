---
product: campaign
title: 行銷活動資產、檔案和傳遞大網
description: 進一步瞭解行銷活動檔案和傳遞大網
feature: Campaigns
role: User
exl-id: 352f6cd5-777d-413d-af79-6f53444b336f
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 0%

---

# 管理資產和檔案 {#manage-assets-documents}

您可以將各種檔案與行銷活動建立關聯：報表、像片、網頁、圖表等。 這些檔案可以是任何格式。

在行銷活動中，您也可以參考其他專案，例如促銷優惠券、與特定品牌或商店相關的特殊優惠等。 當這些元素包含在大綱中時，它們可以與直接郵件傳遞相關聯。 [了解更多](#associating-and-structuring-resources-linked-via-a-delivery-outline)。


>[!CAUTION]
>
>此功能專為小型資產和檔案所設計。

<!--
>[!NOTE]
>
>If you are using Campaign Marketing Resource Management module, you can also manage a library of marketing resources that are available for several users for collaborative work. [Learn more](../../mrm/using/managing-marketing-resources.md).
-->

## 新增檔案 {#add-documents}

檔案可以在行銷活動層級（內容檔案）或方案層級（一般檔案）相關聯。

對於行銷活動， **[!UICONTROL Documents]** 索引標籤包含：

* 內容所需的所有檔案清單（範本、影像等） 這些軟體可由具有適當許可權的Adobe Campaign運運算元在本機下載，
* 包含路由器資訊的檔案（如果有的話）。

檔案透過連結至方案或行銷活動 **[!UICONTROL Edit > Documents]** 標籤。

![](assets/op_add_document.png)

您也可以從控制面板的專用連結，將檔案新增至行銷活動。

![](assets/add_a_document_in_op.png)

按一下 **[!UICONTROL Detail...]** 圖示可檢視檔案內容並新增資訊：

![](assets/add_document_details.png)

在控制面板中，與行銷活動相關聯的檔案會分組在 **[!UICONTROL Document(s)]** 區段，如下列範例所示：

![](assets/edit_documents.png)

您也可以從此檢視編輯及修改它們。

## 使用傳遞大網 {#delivery-outlines}

傳遞大網是結構化的元素集（檔案、商店、促銷優惠券等） 由公司針對特定行銷活動所建立。 它用於直接郵件傳遞的情境下。

這些元素會分組在傳遞大網中，而每個傳遞大網都會與一個傳遞相關聯；其將在傳送至的擷取檔案中參考 **服務提供者** 以便附加至傳遞。 例如，您可以建立參考單位及其使用之行銷手冊的傳遞大網。

對於行銷活動，傳遞概要可讓您根據特定條件來建構要與傳遞關聯的外部元素：相關單位、已授與的促銷優惠、本機活動的邀請等。

>[!CAUTION]
>
>傳遞大網僅限於直接郵件行銷活動。

### 建立傳遞大網 {#create-an-outline}

若要建立傳遞大網，請按一下 **[!UICONTROL Delivery outlines]** 中的子標籤 **[!UICONTROL Edit > Documents]** 相關行銷活動的標籤。

![](assets/add-a-delivery-outline.png)


>[!NOTE]
>
>如果您看不到此標籤，表示此功能無法用於此行銷活動，或您的執行個體中未啟用直接郵件傳送。 請參閱 [行銷活動範本設定](marketing-campaign-templates.md#campaign-templates) 或您的授權合約。

接下來，按一下 **[!UICONTROL Add a delivery outline]** 並為行銷活動建立大綱階層：

1. 以滑鼠右鍵按一下樹狀結構的根目錄，然後選取 **[!UICONTROL New > Delivery outlines]**.
1. 用滑鼠右鍵按一下您剛建立的大綱，然後選取 **[!UICONTROL New > Item]** 或 **[!UICONTROL New > Personalization fields]**.

![](assets/del-outline-add-new-item.png)

大綱可包含專案、個人化欄位和選件：

* 專案可以是實體檔案，例如，此處會參照和說明，且會附加至傳遞。
* 個人化欄位可讓您建立與傳送相關的個人化元素，而非收件者。 因此，您可以建立用於特定目標之傳送的值（歡迎優惠、折扣等） 它們是在Adobe Campaign中建立，並透過匯入大綱 **[!UICONTROL Import personalization fields...]** 連結。

  ![](assets/del-outline-perso-field.png)

  也可以直接在大綱中建立，方法是按一下 **[!UICONTROL Add]** 圖示加以顯示。

  ![](assets/add-del-outline-button.png)


### 選取大綱 {#select-an-outline}

對於每次傳遞，您可以從保留給擷取大綱的區段中選取要關聯的大綱，如下列範例所示：

![](assets/select-delivery-outline.png)

然後所選輪廓會顯示在視窗的下半部。 您可以使用欄位右側的圖示加以編輯，或使用下拉式清單加以變更：

![](assets/delivery-outline-selected.png)

此 **[!UICONTROL Summary]** 傳遞的索引標籤也會顯示此資訊：

![](assets/delivery-outline-in-dashboard.png)

### 擷取結果 {#extraction-result}

在擷取並傳送給服務提供者的檔案中，大綱的名稱以及適當時其特徵（成本、說明等） 會根據與服務提供者相關聯之匯出範本中的資訊來新增至內容。

在下列範例中，與傳遞相關的大綱的標籤、預估成本和說明將新增至摘取檔案。

![](assets/campaign-export-template.png)

匯出模型必須與為相關傳遞選取的服務提供者相關聯。 請參閱[本節](providers--stocks-and-budgets.md#creating-service-providers-and-their-cost-structures)。
