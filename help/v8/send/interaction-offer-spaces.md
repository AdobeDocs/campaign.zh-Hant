---
solution: Campaign v8
product: Adobe Campaign
title: 行銷活動互動優惠方案空間
description: 了解如何建立優惠方案空間
feature: 概覽
role: Data Engineer
level: Beginner
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 3%

---

# 建立優惠方案空間{#creating-offer-spaces}

優惠方案目錄的內容是在優惠方案空間中設定。 依預設，內容可包含下列欄位：**[!UICONTROL Title]**、**[!UICONTROL Destination URL]**、**[!UICONTROL Image URL]**、**[!UICONTROL HTML content]**&#x200B;和&#x200B;**[!UICONTROL Text content]**。 欄位序列是在選件空間中設定。

身為&#x200B;**技術管理員**，您可以在設計環境中建立優惠方案空間。 您必須擁有優惠方案空間子資料夾的存取權。 建立後，這些優惠方案空間會在優惠方案核准期間自動複製到即時環境中。

HTML呈現是透過呈現函式建立。 呈現函式中定義的欄位順序必須與內容中設定的序列相同。

![](assets/offer_space_create_009.png)

若要建立新優惠方案空間，請遵循下列步驟：

1. 從選件空間清單中，按一下&#x200B;**[!UICONTROL New]**。

   ![](assets/offer_space_create_001.png)

1. 選取您要使用的管道，並變更優惠方案空間的標籤。

   ![](assets/offer_space_create_002.png)

1. 檢查&#x200B;**[!UICONTROL Enable unitary mode]**&#x200B;選項

1. 前往&#x200B;**[!UICONTROL Content field]**&#x200B;視窗，然後按一下&#x200B;**[!UICONTROL Add]**。

   ![](assets/offer_space_create_003.png)

1. 轉至&#x200B;**[!UICONTROL Content]**&#x200B;節點，然後按以下順序選擇欄位：**[!UICONTROL Title]**，然後是&#x200B;**[!UICONTROL Image URL]**，然後是&#x200B;**[!UICONTROL HTML content]**，然後是&#x200B;**[!UICONTROL Destination URL]**。

   ![](assets/offer_space_create_004.png)

1. 核取&#x200B;**[!UICONTROL Required]**&#x200B;選項，將每個欄位設為必填欄位。

   >[!NOTE]
   >
   >預覽時會使用此選項，如果選件中缺少其中一個必填欄位，則發佈時會使選件空間無效。 不過，如果優惠方案已在優惠方案空間上線，則不會考慮這些條件。

   ![](assets/offer_space_create_005.png)

1. 按一下&#x200B;**[!UICONTROL Edit functions]**&#x200B;以建立呈現函式。

   這些函式可用來在優惠方案空間中產生優惠方案表示法。 有幾種可能的格式：HTML或文字。

   **注意**  - XML格式僅限於暫時無法使用的入站互動。[了解更多](../start/capability-matrix.md#gs-unavailable-features)

   ![](assets/offer_space_create_006.png)_

1. 前往&#x200B;**[!UICONTROL HTML rendering]**&#x200B;標籤，然後選取&#x200B;**[!UICONTROL Overload the HTML rendering function]**。
1. 插入您的呈現函式。

   ![](assets/offer_space_create_007.png)

## 優惠方案主張狀態{#offer-proposition-statuses}

優惠方案主張狀態會依與目標人口的互動而有所不同。 「促銷活動互動」模組隨附一組值，可在優惠方案主張的整個生命週期中套用。 您需要設定平台，以便在建立並接受優惠方案主張時變更狀態。

>[!NOTE]
>
>狀態更新是非同步進程。 這會由每小時觸發的追蹤工作流程執行。

### 選件狀態清單{#status-list}

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

### 建立主張時的選件狀態{#configuring-the-status-when-the-proposition-is-created}

當優惠方案主張為&#x200B;**created**&#x200B;時，其狀態會更新。

在&#x200B;**[!UICONTROL Design]**&#x200B;環境中，根據您要在優惠方案報表中顯示的資訊，針對每個優惠方案空間，設定建立主張時要套用的狀態。

要執行此操作，請遵循下列步驟：

1. 前往所需空間的&#x200B;**[!UICONTROL Storage]**&#x200B;標籤。
1. 選擇要在建立命題時應用到命題的狀態。

   ![](assets/offer_update_status_001.png)

### 接受主張時的選件狀態{#configuring-the-status-when-the-proposition-is-accepted}

一旦優惠方案主張已&#x200B;**接受**，請使用預設提供的其中一個值來設定該主張的新狀態。 當收件者點按選件中的連結時，就會套用更新。

要執行此操作，請遵循下列步驟：

1. 前往所需空間的&#x200B;**[!UICONTROL Storage]**&#x200B;標籤。
1. 選擇在接受主張時要應用於該主張的狀態。

   ![](assets/offer_update_status_002.png)

<!--
**Inbound interaction**

The **[!UICONTROL Storage]** tab lets you define statuses for **proposed** and **accepted** offer propositions only. For inbound interaction, the status of offer propositions should be specified directly in the URL for calling the offer engine, rather than through the interface. This way, you will be able to specify which status to apply in other cases, for example if an offer proposition is rejected.

```
<BASE_URL>?a=UpdateStatus&p=<PRIMARY_KEY_OF_THE_PROPOSITION>&st=<NEW_STATUS_OF_THE_PROPOSITION>&r=<REDIRECT_URL>
```

For instance, the proposition (identifier **40004**) that matches the **Home insurance** offer displayed on the **Neobank** site contains the following URL:

```
<BASE_URL>?a=UpdateStatus&p=<40004>&st=<3>&r=<"http://www.neobank.com/insurance/subscribe.html">
```

As soon as a visitor clicks the offer, and therefore the URL, the **[!UICONTROL Accepted]** status (value **3**) is applied to the proposition and the visitor is redirected to a new page of the **Neobank** site to take out the insurance contract.

>[!NOTE]
>
>If you want to specify another status in the url (for example if an offer proposition is rejected), use the value corresponding to the desired status. Example: **[!UICONTROL Rejected]** = "5", **[!UICONTROL Presented]** = "1" and so on.
>
>Statuses and their values can be retrieved in the **[!UICONTROL Offer propositions (nms)]** data schema. For more on this, refer to [this page](../../configuration/using/data-schemas.md).

**Outbound interaction**
-->

當傳送包含連結時，您可以自動將&#x200B;**[!UICONTROL Interested]**&#x200B;狀態套用至優惠方案主張。 只需將&#x200B;**_urlType=&quot;11&quot;**&#x200B;值新增至連結即可：

```
<a _urlType="11" href="<DEST_URL>">Link inserted into the delivery</a>
```

## 每個空間的選件預覽{#offer-preview-per-space}

在&#x200B;**[!UICONTROL Preview]**&#x200B;標籤中，您可以透過所選方法檢視收件者符合資格的選件。 在以下範例中，收件者可透過郵件取得三份優惠方案。

![](assets/offer_space_overview_002.png)

如果收件者不符合任何優惠方案的資格，這會顯示在預覽中。

![](assets/offer_space_overview_001.png)

<!--
The preview can ignore contexts when they are restricted to a space. This is the case when the interaction schema has been extended to add fields referenced in a space using an inbound channel (for more on this, refer to Extension example.
-->
