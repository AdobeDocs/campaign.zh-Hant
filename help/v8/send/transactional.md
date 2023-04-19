---
title: Campaign交易式訊息
description: 開始使用異動訊息
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 06fdb279-3776-433f-8d27-33d016473dee
source-git-commit: 1c879c7803c346d4b602089a22c2639eb83e82be
workflow-type: tm+mt
source-wordcount: '1510'
ht-degree: 1%

---

# 開始使用異動訊息{#send-transactional-messages}

交易式訊息（訊息中心）是專為管理觸發訊息而設計的Campaign模組。 這些通知是從資訊系統觸發的事件中產生的，可以是：發票、訂單確認、發運確認、密碼更改、產品不可用通知、帳戶對帳單、網站帳戶建立等。

![](../assets/do-not-localize/speech.png)  作為托管Cloud Services用戶， [連絡Adobe](../start/campaign-faq.md#support){target="_blank"} 在您的環境中設定Campaign交易式訊息。

交易式訊息用於傳送：

* 通知，例如訂單確認或密碼重設
* 客戶動作的個別即時回應
* 非促銷內容

交易式訊息設定在 [本節](../config/transactional-msg-settings.md).

了解交易式訊息架構，位於 [本頁](../architecture/architecture.md#transac-msg-archi).

## 交易式訊息傳遞操作原則 {#transactional-messaging-operating-principle}

Adobe Campaign交易式訊息模組整合至資訊系統，該資訊系統會傳回要變更為個人化交易式訊息的事件。 這些訊息可以個別傳送，或透過電子郵件、簡訊或推播通知分批傳送。

例如，假設您是一家有網站的公司，客戶可在此購買產品。

Adobe Campaign可讓您傳送通知電子郵件給已將產品新增至購物車的客戶。 當其中一個使用者離開您的網站而未進行購買時（觸發促銷活動事件的外部事件），購物車放棄率電子郵件會自動傳送給他們（交易式訊息傳送）。

實施此程式的主要步驟如下：

1. [建立事件類型](#create-event-types).
1. [建立和設計訊息範本](#create-message-template). 在此步驟中，您必須將事件連結至訊息。
1. [測試訊息](#test-message-template).
1. [發佈訊息範本](#publish-message-template).

在您設計並發佈交易式訊息範本後，如果觸發對應事件，則相關資料會透過PushEvent和PushEvents傳送至Campaign [SOAP方法](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/processing/event-description.html){target="_blank"}，則會傳送給目標收件者。

## 建立事件類型 {#create-event-types}

若要確保每個事件都可變更為個人化訊息，您必須先建立 **事件類型**.

當 [建立訊息範本](#create-message-template)，您將選取符合您要傳送之訊息的事件類型。

>[!CAUTION]
>
>您必須先建立事件類型，才能在訊息範本中使用它們。

若要建立Adobe Campaign將處理的事件類型，請遵循下列步驟：

1. 瀏覽至 **[!UICONTROL Administration > Platform > Enumerations]** Campaign檔案總管的資料夾。
1. 選取 **[!UICONTROL Event type]** 清單中的分項清單。
1. 按一下 **[!UICONTROL Add]** 來建立分項清單。 這可以是訂單確認、密碼變更、訂單傳送變更等。

   ![](assets/messagecenter_eventtype_enum_001.png)

   >[!CAUTION]
   >
   >每個事件類型都必須符合 **[!UICONTROL Event type]** 枚舉。

1. 建立分項清單值後，請登出再重新登入您的例項，讓建立生效。

>[!NOTE]
>
>進一步了解 [本頁](../../v8/config/ui-settings.md#enumerations).


## 定義交易式訊息範本 {#create-message-template}

每個事件都可觸發個人化訊息。 為了讓此情況發生，您需要建立訊息範本以符合每個事件類型。 範本包含個人化交易式訊息的必要資訊。 您也可以使用範本來測試訊息預覽，並在傳送至最終目標之前使用種子地址傳送校樣。

### 建立範本

若要建立訊息範本，請遵循下列步驟：

1. 前往 **[!UICONTROL Message Center >Transactional message templates]** 檔案夾中。
1. 在交易式訊息範本清單中，按一下滑鼠右鍵並選取 **[!UICONTROL New]** 或按一下 **[!UICONTROL New]** 按鈕。

   ![](assets/messagecenter_create_model_001.png)

1. 在傳送視窗中，選取適合您要使用之通道的傳送範本。

   ![](assets/messagecenter_create_model_002.png)

1. 視需要變更其標籤。
1. 選取符合您要傳送之訊息的事件類型。 必須預先建立Adobe Campaign要處理的事件類型。 [了解更多](#create-event-types)

   ![](assets/messagecenter_create_model_003.png)

   >[!CAUTION]
   >
   >事件類型絕不應連結至多個範本。

1. 輸入性質和說明，然後按一下 **[!UICONTROL Continue]** 以建立訊息內文。

### 建立內容{#create-message-content}

交易式訊息內容的定義與Adobe Campaign中所有傳送的定義相同。 例如，對於電子郵件傳送，您可以建立HTML或文字格式的內容、新增附件或個人化傳送物件。 [了解更多資訊](../start/create-message.md)。

>[!CAUTION]
>
>訊息中包含的影像必須可公開存取。 Adobe Campaign不提供任何交易式訊息的影像上傳機制。\
>與JSSP或webApp不同， `<%=` 沒有任何預設逸出。
>
>您必須正確逸出來自事件的每個資料。 此逸出取決於此欄位的使用方式。 例如，在URL中，請使用encodeURIComponent。 要在HTML中顯示，可以使用escapeXMLString。

定義訊息內容後，您可以將事件資訊整合至訊息內文，並加以個人化。 由於個人化標籤，事件資訊會插入文字內文。

![](assets/messagecenter_create_content.png)

* 所有個人化欄位皆來自有效負載。
* 可以在交易式訊息中參考一或多個個人化區塊。 <!--The block content will be added to the delivery content during the publication to the execution instance.-->

若要將個人化標籤插入電子郵件訊息的內文，請套用下列步驟：

1. 在訊息範本中，按一下符合電子郵件格式(HTML或文字)的索引標籤。
1. 輸入訊息的內文。
1. 在文字內文中，使用 **[!UICONTROL Real time events>Event XML]** 功能表。

   ![](assets/messagecenter_create_custo_1.png)

1. 使用下列語法填入標籤： **元素名稱**.@**屬性名稱** 如下所示。

   ![](assets/messagecenter_create_custo_2.png)

## 測試交易式訊息範本 {#test-message-template}

### 新增種子地址{#add-seeds}

種子地址可讓您顯示訊息的預覽、傳送校樣，以及在傳送訊息之前測試訊息個人化。 種子地址連結至傳送，無法用於其他傳送。

1. 在交易式訊息範本中，按一下 **[!UICONTROL Seed addresses]** ，然後按一下 **[!UICONTROL Add]** 按鈕。

   ![](assets/messagecenter_create_seed_1.png)

1. 為標籤指派標籤以方便日後選取，然後輸入種子地址（根據通訊通道，電子郵件或行動電話）。

1. 輸入外部標識符：此選用欄位可讓您輸入商業金鑰（唯一ID、名稱+電子郵件等） 網站上所有應用程式都通用的識別碼，用於識別您的設定檔。 如果此欄位也存在於Adobe Campaign行銷資料庫中，您就可以使用資料庫中的設定檔調解事件。

   ![](assets/messagecenter_create_seed_2.png)

1. 插入測試資料。 請參閱[本節](#personalization-data)。

   ![](assets/messagecenter_create_custo_3.png)

1. 按一下 **[!UICONTROL Ok]** 確認種子地址的建立。

1. 重複此過程以建立所需的地址數。

   ![](assets/messagecenter_create_seed_6.png)

建立地址後，您就可以存取其預覽和個人化。

<!--

### Add personalization data{#personalization-data}

You can add data in the message template to test transactional message personalization. This will allow you to generate a preview or send a proof. If you install the **Deliverability** module, this data allows you to display a rendering of the messages for various desktop, web or mobile clients.

The purpose of this data is to test your messages before their final delivery. These messages do not coincide with actual data to be processed by Message Center.

However, the XML structure must be identical to that of the event stored in the execution instance, as shown below. 

![](assets/messagecenter_create_custo_4.png)

This information enables you to personalize message content using personalization tags.

1. In the message template, click the **[!UICONTROL Seed addresses]** tab.
1. In the event content, enter the test information in XML format.

   ![](assets/messagecenter_create_custo_3.png)
-->

### 預覽交易式訊息{#transactional-message-preview}

建立一或多個種子地址和訊息內文後，您可以預覽訊息並檢查其個人化。

1. 在訊息範本中，按一下 **[!UICONTROL Preview]** ，然後選取 **[!UICONTROL A seed address]** 中。

   ![](assets/messagecenter_preview_1.png)

1. 選取先前建立的種子地址以顯示個人化訊息。

   ![](assets/messagecenter_create_seed_7.png)

### 傳送證明

您可以傳送校樣至先前建立的種子地址，以測試訊息傳送。

傳送校樣的程式與任何傳送的程式相同。

![](../assets/do-not-localize/book.png) 進一步了解校樣，於 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html#sending-a-proof){target="_blank"}

不過，若要傳送交易式訊息的證明，您必須執行下列操作：

* 建立一或多個 [種子地址](#add-seeds) 使用個人化測試資料
* 建立訊息內容

若要傳送校樣：

1. 按一下 **[!UICONTROL Send a proof]** 按鈕。
1. 分析傳送。
1. 更正任何錯誤並確認傳送。

   ![](assets/messagecenter_send_proof_001.png)

1. 檢查訊息是否已傳送至種子地址，且其內容是否符合您的設定。

   ![](assets/messagecenter_send_proof_002.png)

校樣可透過 **[!UICONTROL Audit]** 標籤。

![](assets/messagecenter_send_proof_003.png)

## 發佈範本 {#publish-message-template}

建立訊息範本時<!-- on the control instance--> 完成後，您就可以發佈它，這可讓您傳送連結至即時和批次事件的訊息。

<!--This process will also publish it on all execution instances.

NOTE: When publishing transactional message templates, typology rules are also automatically published on the execution instances.

Publication lets you automatically create two message templates on the execution instances, which will allow you to send messages linked to real-time and batch events.-->

>[!CAUTION]
>
>每當您對範本進行任何變更時，請務必再次發佈，讓這些變更在交易式訊息傳送期間生效。

1. 前往 **[!UICONTROL Message Center > Transactional message templates]** 樹的資料夾。
1. 選取要發佈的範本<!--on your execution instances-->.
1. 按一下&#x200B;**[!UICONTROL Publish]**。

   ![](assets/messagecenter_publish_template.png)

發佈完成後，要套用至批次和即時類型事件的訊息範本，都會在 **[!UICONTROL Administration > Production > Message Center Execution> Default > Transactional message templates]** 檔案夾。

![](assets/messagecenter_deployed_model.png)

範本發佈後，若觸發對應事件，則Adobe Campaign<!--execution instance--> 會收到事件，將其連結至交易式範本，並傳送對應的交易式訊息給每個收件者。

<!--
>[!NOTE]
>
>If you replace an existing field of the transactional message template, such as the sender address, with an empty value, the corresponding field on the execution instance(s) will not be updated once the transactional message is published again. It will still contain the previous value.
>
>However, if you add a non-empty value, the corresponding field will be updated as usual after the next publication.
-->

## 取消發佈範本

發佈訊息範本後 <!--on the execution instances-->，則可取消發佈。

* 事實上，如果觸發對應事件，仍可呼叫已發佈的範本：如果您不再使用訊息範本，建議取消發佈訊息範本。 這是為了避免錯誤傳送不需要的交易式訊息。

   例如，您發佈了訊息範本，而您只能用於聖誕促銷活動。 在聖誕節期間結束後，您可能會想要取消發佈，並在明年再次發佈。

* 此外，您無法刪除具有 **[!UICONTROL Published]** 狀態。 您必須先取消發佈。

若要取消發佈交易式訊息範本，請遵循下列步驟。

1. 瀏覽至 **[!UICONTROL Message Center > Transactional message templates]** 檔案夾。
1. 選取要取消發佈的範本。
1. 按一下&#x200B;**[!UICONTROL Unpublish]**。
1. 按一下&#x200B;**[!UICONTROL Start]**。

![](assets/message-center-unpublish.png)

交易式訊息範本狀態會從 **[!UICONTROL Published]** to **[!UICONTROL Being edited]**.

完成取消發佈後：

* 會刪除兩個訊息範本（套用至批次和即時類型事件）<!-- from each execution instance-->.

   它們不再出現在 **[!UICONTROL Administration > Production > Message Center Execution > Default > Transactional message templates]** 檔案夾。

* 取消發佈範本後，您就可以將其刪除<!-- from the control instance-->.

   若要這麼做，請從清單中選取它，然後按一下 **[!UICONTROL Delete]** 按鈕。
