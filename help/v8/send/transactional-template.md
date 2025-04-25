---
title: 建立並發佈您的異動訊息範本
description: 瞭解如何建立和發佈異動訊息範本
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 858c9216-c5a0-4bf9-b4b0-91e403293f73
source-git-commit: 8272550faefece753636418bcb748b36f989fcb5
workflow-type: tm+mt
source-wordcount: '1177'
ht-degree: 1%

---

# 建立並發佈您的異動訊息範本{#template-transactional-messages}

每個事件都可以觸發個人化訊息。 為了做到這點，您需要建立符合每個事件型別的訊息範本。 範本包含個人化交易式訊息的必要資訊。 您也可以使用範本來測試訊息預覽，並在傳送給最終目標之前使用種子地址傳送校樣。

## 建立範本{#create-message-template}

若要建立訊息範本，請遵循下列步驟：

1. 前往Adobe Campaign樹狀結構中的&#x200B;**[!UICONTROL Message Center >Transactional message templates]**&#x200B;資料夾。
1. 在交易式訊息範本清單中，按一下滑鼠右鍵並在下拉式功能表中選取&#x200B;**[!UICONTROL New]**，或按一下交易式訊息範本清單上方的&#x200B;**[!UICONTROL New]**&#x200B;按鈕。

   ![](assets/messagecenter_create_model_001.png)

1. 在傳送視窗中，選取適合您要使用之管道的傳送範本。

   ![](assets/messagecenter_create_model_002.png)

1. 必要時變更其標籤。
1. 選取符合您要傳送之訊息的事件型別。 必須預先建立預定由Adobe Campaign處理的事件型別。 [了解更多](../send/transactional.md#create-event-types)

   ![](assets/messagecenter_create_model_003.png)

   >[!CAUTION]
   >
   >事件型別絕不可連結至多個範本。

1. 輸入性質和說明，然後按一下&#x200B;**[!UICONTROL Continue]**&#x200B;以建立郵件內文。

## 建立內容{#create-message-content}

交易式訊息內容的定義與Adobe Campaign中所有傳送的定義相同。 例如，針對電子郵件傳遞，您可以建立HTML或文字格式的內容、新增附件或個人化傳遞物件。 [了解更多](../start/create-message.md)。

>[!CAUTION]
>
>訊息中包含的影像必須可公開存取。 Adobe Campaign不提供任何異動訊息的影像上傳機制。\
>不同於JSSP或webApp，`<%=`沒有任何預設逸出。
>
>您必須正確逸出來自事件的每個資料。 此逸出取決於此欄位的使用方式。 例如，在URL中，請使用encodeURIComponent。 若要在HTML中顯示，您可以使用escapeXMLString。

定義訊息內容後，您就可以將事件資訊整合至訊息內文，並加以個人化。 由於個人化標籤，事件資訊會插入文字內文中。

![](assets/messagecenter_create_content.png)

* 所有個人化欄位都來自裝載。
* 可以在交易式訊息中參考一或多個個人化區塊。<!--The block content will be added to the delivery content during the publication to the execution instance.-->

若要將個人化標籤插入電子郵件內文，請套用下列步驟：

1. 在訊息範本中，按一下符合電子郵件格式(HTML或文字)的索引標籤。
1. 輸入訊息內文。
1. 在文字內文中，使用&#x200B;**[!UICONTROL Real time events>Event XML]**&#x200B;功能表插入標籤。

   ![](assets/messagecenter_create_custo_1.png)

1. 使用下列語法填入標籤： **元素名稱**。@**屬性名稱**，如下所示。

   ![](assets/messagecenter_create_custo_2.png)

## 測試異動訊息範本 {#test-message-template}

### 新增種子地址{#add-seeds}

種子地址可讓您在傳送訊息之前，顯示訊息預覽、傳送校樣並測試訊息個人化。 種子地址會連結至傳遞，且無法用於其他傳遞。

1. 在交易式訊息範本中，按一下&#x200B;**[!UICONTROL Seed addresses]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL Add]**&#x200B;按鈕。

   ![](assets/messagecenter_create_seed_1.png)

1. 指派標籤給它以便稍後輕鬆選取，然後輸入種子地址（電子郵件或行動電話，視通訊通道而定）。

1. 輸入外部識別碼：此選擇性欄位可讓您輸入網站上的所有應用程式通用的商業金鑰（唯一ID、名稱+電子郵件等），用於識別您的設定檔。 如果此欄位也出現在Adobe Campaign行銷資料庫中，您可以接著將事件與資料庫中的設定檔進行調解。

   ![](assets/messagecenter_create_seed_2.png)

1. 插入測試資料。 [在Campaign Classic v7檔案中進一步瞭解個人化資料](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/message-templates/testing-message-templates#personalization-data.html){target="_blank"}

   ![](assets/messagecenter_create_custo_3.png)

1. 按一下&#x200B;**[!UICONTROL Ok]**&#x200B;以確認建立種子地址。

1. 重複此程式，視需要儘量建立地址。

   ![](assets/messagecenter_create_seed_6.png)

地址建立後，您就可以存取其預覽和個人化。

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

建立一或多個種子地址和訊息本文後，您可以預覽訊息並檢查其個人化。

1. 在訊息範本中，按一下&#x200B;**[!UICONTROL Preview]**&#x200B;標籤，然後在下拉式清單中選取&#x200B;**[!UICONTROL A seed address]**。

   ![](assets/messagecenter_preview_1.png)

1. 選取先前建立的種子地址，以顯示個人化訊息。

   ![](assets/messagecenter_create_seed_7.png)

### 傳送校樣 {#send-proof}

您可以傳送證明至先前建立的種子地址，以測試訊息傳送。

傳送證明的過程與傳送證明的過程相同。

在[本節](../send/preview-and-proof.md#proofs-send)中進一步瞭解校訂。

但是，若要傳送交易式訊息的證明，您必須執行下列操作：

* 使用個人化測試資料建立一或多個[種子地址](#add-seeds)
* 建立訊息內容

若要傳送證明：

1. 按一下傳遞視窗中的&#x200B;**[!UICONTROL Send a proof]**&#x200B;按鈕。
1. 分析傳遞。
1. 更正任何錯誤並確認傳遞。

   ![](assets/messagecenter_send_proof_001.png)

1. 檢查訊息是否已送達種子地址，其內容是否符合您的設定。

   ![](assets/messagecenter_send_proof_002.png)

可透過&#x200B;**[!UICONTROL Audit]**&#x200B;索引標籤在每個範本中存取校樣。

![](assets/messagecenter_send_proof_003.png)

#### 從[!DNL Campaign Classic] v7轉換 {#transition-from-v7}

如果您[要從Campaign Classic v7](../start/v7-to-v8.md)進行轉換，所有傳遞都會通過中間來源(MID)伺服器。

但是，建立交易式訊息範本時，成功使用範本所需的路由是&#x200B;**內部電子郵件傳遞**。 此路由可防止您傳送校樣。

因此，若要傳送交易式訊息範本的校樣，您必須將路由從內部電子郵件傳送變更為&#x200B;**中間來源路由帳戶**。

![](assets/messagecenter_send_proof_004.png)

傳送校樣後，您必須先將路由變更為內部電子郵件傳送，然後再發佈異動訊息範本。

## 發佈範本 {#publish-message-template}

當建立的訊息範本<!-- on the control instance-->完成時，您可以發佈它，這可讓您傳送連結到即時和批次事件的訊息。

<!--This process will also publish it on all execution instances.

NOTE: When publishing transactional message templates, typology rules are also automatically published on the execution instances.

Publication lets you automatically create two message templates on the execution instances, which will allow you to send messages linked to real-time and batch events.-->

>[!CAUTION]
>
>無論何時對範本進行任何變更，請務必再次發佈該範本，使這些變更在交易式訊息傳遞期間生效。

1. 前往樹狀結構的&#x200B;**[!UICONTROL Message Center > Transactional message templates]**&#x200B;資料夾。
1. 選取您要發佈的範本<!--on your execution instances-->。
1. 按一下&#x200B;**[!UICONTROL Publish]**。

   ![](assets/messagecenter_publish_template.png)

發佈完成後，會在&#x200B;**[!UICONTROL Administration > Production > Message Center Execution> Default > Transactional message templates]**&#x200B;資料夾中建立要套用至批次和即時型別事件的訊息範本。

![](assets/messagecenter_deployed_model.png)

發佈範本後，若觸發對應的事件，Adobe Campaign<!--execution instance-->將會收到該事件、將其連結至交易式範本，並將對應的交易式訊息傳送給每個收件者。

<!--
>[!NOTE]
>
>If you replace an existing field of the transactional message template, such as the sender address, with an empty value, the corresponding field on the execution instance(s) will not be updated once the transactional message is published again. It will still contain the previous value.
>
>However, if you add a non-empty value, the corresponding field will be updated as usual after the next publication.
-->

## 取消發佈範本

訊息範本發佈後<!--on the execution instances-->，即可取消發佈。

* 事實上，如果觸發對應的事件，仍可呼叫已發佈的範本：如果您不再使用訊息範本，建議將其取消發佈。 這是為了避免誤傳不必要的交易式訊息。

  例如，您發佈了一個訊息範本，但僅用於聖誕節行銷活動。 您可能會想要在聖誕節期間結束後取消發佈，並在明年再次發佈。

* 此外，您無法刪除狀態為&#x200B;**[!UICONTROL Published]**&#x200B;的交易式訊息範本。 您必須先取消發佈。

若要取消發佈異動訊息範本，請遵循下列步驟。

1. 瀏覽至&#x200B;**[!UICONTROL Message Center > Transactional message templates]**&#x200B;資料夾。
1. 選取要取消發佈的範本。
1. 按一下&#x200B;**[!UICONTROL Unpublish]**。
1. 按一下&#x200B;**[!UICONTROL Start]**。

![](assets/message-center-unpublish.png)

異動訊息範本狀態從&#x200B;**[!UICONTROL Published]**&#x200B;變更回&#x200B;**[!UICONTROL Being edited]**。

取消發佈完成後：

* 訊息範本（套用至批次和即時型別事件）都會被刪除<!-- from each execution instance-->。

  它們不再出現在&#x200B;**[!UICONTROL Administration > Production > Message Center Execution > Default > Transactional message templates]**&#x200B;資料夾中。

* 範本取消發佈後，您就可以刪除它<!-- from the control instance-->。

  若要這麼做，請從清單中選取它，然後按一下畫面右上方的&#x200B;**[!UICONTROL Delete]**&#x200B;按鈕。
