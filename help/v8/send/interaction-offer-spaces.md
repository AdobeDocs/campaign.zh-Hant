---
title: 行銷活動互動優惠方案空間
description: 了解如何建立優惠方案空間
feature: Overview
role: Data Engineer
level: Beginner
exl-id: c116d86a-d3e2-47e3-a641-e2d7c8cc575c
source-git-commit: 889400a238f32968464f1425bb7d6c2dc3ff3cd0
workflow-type: tm+mt
source-wordcount: '840'
ht-degree: 3%

---

# 建立優惠方案空間{#creating-offer-spaces}

優惠方案目錄的內容是在優惠方案空間中設定。 依預設，內容可包含下列欄位： **[!UICONTROL Title]**, **[!UICONTROL Destination URL]**, **[!UICONTROL Image URL]**, **[!UICONTROL HTML content]** 和 **[!UICONTROL Text content]**. 欄位序列是在選件空間中設定。

As a **技術管理員**，您可以在設計環境中建立優惠方案空間。 您必須擁有優惠方案空間子資料夾的存取權。 建立後，這些優惠方案空間會在優惠方案核准期間自動複製到即時環境中。

HTML呈現是透過呈現函式建立。 呈現函式中定義的欄位順序必須與內容中設定的序列相同。

![](assets/offer_space_create_009.png)

若要建立新優惠方案空間，請遵循下列步驟：

1. 在優惠方案空間清單中，按一下 **[!UICONTROL New]**.

   ![](assets/offer_space_create_001.png)

1. 選取您要使用的管道，並變更優惠方案空間的標籤。

   ![](assets/offer_space_create_002.png)

1. 檢查 **[!UICONTROL Enable unitary mode]** 選項

1. 前往 **[!UICONTROL Content field]** 按一下 **[!UICONTROL Add]**.

   ![](assets/offer_space_create_003.png)

1. 前往 **[!UICONTROL Content]** 節點，然後依下列順序選取欄位： **[!UICONTROL Title]**，然後 **[!UICONTROL Image URL]**，然後 **[!UICONTROL HTML content]**，然後 **[!UICONTROL Destination URL]**.

   ![](assets/offer_space_create_004.png)

1. 檢查 **[!UICONTROL Required]** 選項，將每個欄位設為必填。

   >[!NOTE]
   >
   >預覽時會使用此選項，如果選件中缺少其中一個必填欄位，則發佈時會使選件空間無效。 不過，如果優惠方案已在優惠方案空間上線，則不會考慮這些條件。

   ![](assets/offer_space_create_005.png)

1. 按一下 **[!UICONTROL Edit functions]** 來建立呈現函式。

   這些函式可用來在優惠方案空間中產生優惠方案表示法。 有幾種可能的格式：HTML或文字。

   **附註** - XML格式僅限於此版本產品中不可用的入站交互。 [了解更多](../start/capability-matrix.md#gs-unavailable-features)

   ![](assets/offer_space_create_006.png)_

1. 前往 **[!UICONTROL HTML rendering]** 索引標籤和選取 **[!UICONTROL Overload the HTML rendering function]**.
1. 插入您的呈現函式。

   ![](assets/offer_space_create_007.png)

## 優惠方案主張狀態 {#offer-proposition-statuses}

優惠方案主張狀態會依與目標人口的互動而有所不同。 「促銷活動互動」模組隨附一組值，可在優惠方案主張的整個生命週期中套用。 您需要設定平台，以便在建立並接受優惠方案主張時變更狀態。

>[!NOTE]
>
>狀態更新是 **非同步** 程式。 這會由每小時觸發的追蹤工作流程執行。

### 選件狀態清單 {#status-list}

可用的優惠方案狀態包括：

* **[!UICONTROL Accepted]**
* **[!UICONTROL Scheduled]**
* **[!UICONTROL Generated]**
* **[!UICONTROL Interested]**
* **[!UICONTROL Presented]**
* **[!UICONTROL Rejected]**

預設不會套用這些值：必須進行設定。

>[!NOTE]
>
>如果優惠方案連結至狀態為「已傳送」的傳送，優惠方案主張的狀態會自動變更為「已呈現」。

### 建立主張時的選件狀態 {#configuring-the-status-when-the-proposition-is-created}

優惠方案主張為 **已建立**，則其狀態會更新。

在 **[!UICONTROL Design]** 環境中，根據您要顯示在優惠方案報表中的資訊，針對每個優惠方案空間設定建立主張時要套用的狀態。

要執行此操作，請遵循下列步驟：

1. 前往 **[!UICONTROL Storage]** 頁簽。
1. 選擇要在建立命題時應用到命題的狀態。

   ![](assets/offer_update_status_001.png)

### 接受主張時的優惠方案狀態 {#configuring-the-status-when-the-proposition-is-accepted}

一旦優惠方案主張 **接受**，請使用預設提供的值之一來設定主張的新狀態。 當收件者點按選件中的連結時，就會套用更新。

要執行此操作，請遵循下列步驟：

1. 前往 **[!UICONTROL Storage]** 頁簽。
1. 選擇在接受主張時要應用於該主張的狀態。

   ![](assets/offer_update_status_002.png)


**入站互動**

此 **[!UICONTROL Storage]** 索引標籤可讓您定義 **提議** 和 **接受** 僅提供建議。 若是傳入互動，應直接在呼叫優惠方案引擎的URL中指定優惠方案狀態，而非透過介面。 如此一來，您就能指定在其他情況下（例如，如果優惠方案主張遭拒）要套用的狀態。

```
<BASE_URL>?a=UpdateStatus&p=<PRIMARY_KEY_OF_THE_PROPOSITION>&st=<NEW_STATUS_OF_THE_PROPOSITION>&r=<REDIRECT_URL>
```

例如，主張（識別碼） **40004**) **家庭保險** 顯示在 **尼奧班克** 網站包含下列URL:

```
<BASE_URL>?a=UpdateStatus&p=<40004>&st=<3>&r=<"http://www.neobank.com/insurance/subscribe.html">
```

當訪客點按選件，因此URL時， **[!UICONTROL Accepted]** 狀態（值） **3**)會套用至主張，而訪客會重新導向至的新頁面 **尼奧班克** 地點來簽保險合同。

>[!NOTE]
>
>如果您想在URL中指定其他狀態（例如，如果優惠方案主張遭拒），請使用與所需狀態對應的值。 範例： **[!UICONTROL Rejected]** = &quot;5&quot;, **[!UICONTROL Presented]** = &quot;1&quot;等。
>
>狀態及其值可在 **[!UICONTROL Offer propositions (nms)]** 資料結構。 如需詳細資訊，請參閱[此頁面](../dev/create-schema.md)。

**傳出互動**

您可以自動套用 **[!UICONTROL Interested]** 當傳送包含連結時，狀態為優惠方案主張。 只需新增 **_urlType=&quot;11&quot;** 連結的值：

```
<a _urlType="11" href="<DEST_URL>">Link inserted into the delivery</a>
```

## 每個空間的選件預覽 {#offer-preview-per-space}

在 **[!UICONTROL Preview]** 標籤，您可以透過選擇的方法來檢視收件者符合資格的選件。 在以下範例中，收件者可透過郵件取得三份優惠方案。

![](assets/offer_space_overview_002.png)

如果收件者不符合任何優惠方案的資格，這會顯示在預覽中。

![](assets/offer_space_overview_001.png)


當內容被限制為空格時，預覽可忽略這些內容。 互動架構已擴充至使用入站頻道新增空間中參考的欄位時，即為此情況。

![](../assets/do-not-localize/book.png)  如需詳細資訊，請參閱 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/advanced-parameters/extension-example.html){target=&quot;_blank&quot;}。