---
title: Campaign互動選件空間
description: 瞭解如何建立優惠方案空間
feature: Interaction, Offers
role: Data Engineer
level: Beginner
exl-id: c116d86a-d3e2-47e3-a641-e2d7c8cc575c
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 3%

---

# 建立優惠方案空間{#creating-offer-spaces}

優惠方案目錄的內容是在優惠方案空間中設定。 依預設，內容可包含以下欄位： **[!UICONTROL Title]**， **[!UICONTROL Destination URL]**， **[!UICONTROL Image URL]**， **[!UICONTROL HTML content]** 和 **[!UICONTROL Text content]**. 欄位序列是在選件空間中設定。

As a **技術管理員**，您可以在「設計」環境中建立優惠方案空間。 您需要具有優惠方案空間子資料夾的存取權。 建立後，這些優惠方案空間會在優惠方案核准期間自動複製到即時環境中。

HTML演算會透過演算函式建立。 轉譯函式中定義的欄位順序必須與內容中設定的順序相同。

![](assets/offer_space_create_009.png)

若要建立新的優惠方案空間，請遵循下列步驟：

1. 從優惠方案空間清單中，按一下 **[!UICONTROL New]**.

   ![](assets/offer_space_create_001.png)

1. 選取您要使用的頻道，並變更優惠方案空間的標籤。

   ![](assets/offer_space_create_002.png)

1. 檢查 **[!UICONTROL Enable unitary mode]** option

1. 前往 **[!UICONTROL Content field]** 視窗並按一下 **[!UICONTROL Add]**.

   ![](assets/offer_space_create_003.png)

1. 前往 **[!UICONTROL Content]** 節點並按下列順序選取欄位： **[!UICONTROL Title]**，則 **[!UICONTROL Image URL]**，則 **[!UICONTROL HTML content]**，則 **[!UICONTROL Destination URL]**.

   ![](assets/offer_space_create_004.png)

1. 檢查 **[!UICONTROL Required]** 讓每個欄位成為必要欄位的選項。

   >[!NOTE]
   >
   >預覽時會使用此選項，如果選件中缺少其中一個必要欄位，發佈時就會讓選件空格無效。 但是，如果優惠方案已在優惠方案空間上線，則不會考慮這些條件。

   ![](assets/offer_space_create_005.png)

1. 按一下 **[!UICONTROL Edit functions]** 以建立演算函式。

   這些函式用於在優惠方案空間上產生優惠方案宣告。 有幾種可能的格式：HTML或文字。

   **注意** - XML格式僅限於此版本產品中無法使用的輸入互動。 [了解更多](../start/v7-to-v8.md#gs-unavailable-features)

   ![](assets/offer_space_create_006.png)_

1. 前往 **[!UICONTROL HTML rendering]** 標籤並選取 **[!UICONTROL Overload the HTML rendering function]**.
1. 插入您的演算函式。

   ![](assets/offer_space_create_007.png)

## 優惠方案主張狀態 {#offer-proposition-statuses}

優惠方案主張狀態會依與目標群體的互動而有所不同。 「促銷活動互動」模組隨附一組值，可在優惠方案主張的整個生命週期中套用這些值。 您需要設定平台，以便在建立及接受優惠方案主張時變更狀態。

>[!NOTE]
>
>狀態更新為 **非同步** 程式。 追蹤工作流程會每小時觸發一次。

### 優惠狀態清單 {#status-list}

可用的優惠方案狀態為：

* **[!UICONTROL Accepted]**
* **[!UICONTROL Scheduled]**
* **[!UICONTROL Generated]**
* **[!UICONTROL Interested]**
* **[!UICONTROL Presented]**
* **[!UICONTROL Rejected]**

預設不會套用這些值：必須加以設定。

>[!NOTE]
>
>如果優惠連結到狀態為「已傳送」的傳遞，優惠方案主張的狀態會自動變更為「已呈現」。

### 建立主張時的優惠方案狀態 {#configuring-the-status-when-the-proposition-is-created}

當優惠方案主張為 **已建立**，其狀態會更新。

在 **[!UICONTROL Design]** 環境，請根據您要在優惠方案報表中顯示的資訊，為每個優惠方案空間設定建立主張時要套用的狀態。

要執行此操作，請遵循下列步驟：

1. 前往 **[!UICONTROL Storage]** 標籤中指定位置的頁首。
1. 選取建立時套用至主張的狀態。

   ![](assets/offer_update_status_001.png)

### 接受主張時的優惠狀態 {#configuring-the-status-when-the-proposition-is-accepted}

一旦優惠方案主張已 **已接受**，使用預設提供的值之一來設定主張的新狀態。 當收件者按一下優惠方案中的連結時，就會套用更新。

要執行此操作，請遵循下列步驟：

1. 前往 **[!UICONTROL Storage]** 標籤中指定位置的頁首。
1. 選取您要在主張被接受時套用的狀態。

   ![](assets/offer_update_status_002.png)


**傳入互動**

此 **[!UICONTROL Storage]** 索引標籤可讓您定義狀態 **已建議** 和 **已接受** 僅限優惠方案主張。 針對傳入互動，應直接在呼叫優惠方案引擎的URL中指定優惠方案主張的狀態，而非透過介面。 如此一來，您將能夠指定在其他情況下要套用的狀態，例如優惠方案主張被拒絕時。

```
<BASE_URL>?a=UpdateStatus&p=<PRIMARY_KEY_OF_THE_PROPOSITION>&st=<NEW_STATUS_OF_THE_PROPOSITION>&r=<REDIRECT_URL>
```

例如，主張（識別碼） **40004**)，此引數符合 **家庭保險** 優惠方案顯示在 **Neobank** 網站包含下列URL：

```
<BASE_URL>?a=UpdateStatus&p=<40004>&st=<3>&r=<"http://www.neobank.com/insurance/subscribe.html">
```

當訪客按一下選件，接著按一下URL，然後 **[!UICONTROL Accepted]** 狀態（值） **3**)套用至主張，而訪客會重新導向至的新頁面 **Neobank** 提出保險合約的網站。

>[!NOTE]
>
>如果您想在URL中指定其他狀態（例如，如果優惠方案主張被拒絕），請使用與所需狀態對應的值。 範例： **[!UICONTROL Rejected]** = &quot;5&quot;， **[!UICONTROL Presented]** = 「1」等。
>
>狀態及其值可在下列位置擷取： **[!UICONTROL Offer propositions (nms)]** 資料結構描述。 如需詳細資訊，請參閱[此頁面](../dev/create-schema.md)。

**傳出互動**

您可以自動套用 **[!UICONTROL Interested]** 當傳遞包含連結時，優惠方案主張的狀態。 只需新增 **_urlType=&quot;11&quot;** 連結的值：

```
<a _urlType="11" href="<DEST_URL>">Link inserted into the delivery</a>
```

## 每個空間的優惠預覽 {#offer-preview-per-space}

在 **[!UICONTROL Preview]** 索引標籤中，您可以透過選擇的方法檢視收件者符合資格的優惠方案。 在以下範例中，收件者有資格透過郵件獲得三個優惠方案書。

![](assets/offer_space_overview_002.png)

如果收件者不符合任何優惠方案的資格，便會在預覽中顯示。

![](assets/offer_space_overview_001.png)


當上下文限製為空格時，預覽可以忽略上下文。 當互動結構描述已擴展，以使用傳入頻道新增空間中參照的欄位時，就會發生這種情況。

![](../assets/do-not-localize/book.png)  如需詳細資訊，請參閱此範例，位置如下： [Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/advanced-parameters/extension-example.html){target="_blank"}.