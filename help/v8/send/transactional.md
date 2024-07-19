---
title: Campaign交易訊息
description: 開始使用異動訊息
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 06fdb279-3776-433f-8d27-33d016473dee
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '1491'
ht-degree: 1%

---

# 開始使用異動訊息{#send-transactional-messages}

異動訊息（訊息中心）是專為管理觸發訊息而設計的Campaign模組。 這些通知是從資訊系統觸發的事件產生，可以是：發票、訂單確認、出貨確認、密碼變更、產品無法使用通知、帳戶對帳單、網站帳戶建立等。

>[!NOTE]
>
>作為Managed Cloud Service使用者，[請聯絡Adobe](../start/campaign-faq.md#support){target="_blank"}以在您的環境中設定Campaign異動訊息。

交易式訊息用於傳送：

* 通知，例如訂單確認或密碼重設
* 個人對客戶動作的即時回應
* 非促銷內容

交易式訊息設定在[本節](../config/transactional-msg-settings.md)中有詳細說明。

瞭解[此頁面](../architecture/architecture.md#transac-msg-archi)上的交易式傳訊架構。

## 異動訊息傳遞操作原則 {#transactional-messaging-operating-principle}

Adobe Campaign異動訊息模組整合至資訊系統，可傳回要變更為個人化異動訊息的事件。 這些訊息可透過電子郵件、簡訊或推播通知個別或批次傳送。

例如，假設您是一間擁有網站的公司，客戶可以在其中購買產品。

Adobe Campaign可讓您傳送通知電子郵件給已將產品新增至購物車的客戶。 當其中一人離開您的網站而未完成購買（觸發促銷活動事件的外部事件）時，就會自動傳送購物車放棄電子郵件給他們（交易式訊息傳送）。

設定此專案的主要步驟如下：

1. [建立事件型別](#create-event-types)。
1. [建立並設計訊息範本](#create-message-template)。 您必須在此步驟將事件連結至訊息。
1. [測試訊息](#test-message-template)。
1. [Publish訊息範本](#publish-message-template)。

設計和發佈異動訊息範本後，如果觸發了對應的事件，則會透過PushEvent和PushEvents [SOAP方法](../send/event-description.md)將相關資料傳送至Campaign，並將傳遞傳送至目標收件者。

## 建立事件類型 {#create-event-types}

為了確保每個事件都可以變更為個人化訊息，您必須先建立&#x200B;**事件型別**。

當[建立訊息範本](#create-message-template)時，您將選取符合您要傳送之訊息的事件型別。

>[!CAUTION]
>
>您必須先建立事件型別，才能在訊息範本中使用它們。

若要建立Adobe Campaign將處理的事件型別，請遵循下列步驟：

1. 瀏覽至Campaign檔案總管的&#x200B;**[!UICONTROL Administration > Platform > Enumerations]**&#x200B;資料夾。
1. 從清單中選取&#x200B;**[!UICONTROL Event type]**&#x200B;分項清單。
1. 按一下&#x200B;**[!UICONTROL Add]**&#x200B;以建立分項清單。 這可以是訂單確認、密碼變更、訂單傳遞變更等。

   ![](assets/messagecenter_eventtype_enum_001.png)

   >[!CAUTION]
   >
   >每個事件型別都必須符合&#x200B;**[!UICONTROL Event type]**&#x200B;列舉中的一個值。

1. 建立分項清單值後，請先登出再登入執行個體，才能讓建立生效。

>[!NOTE]
>
>在[此頁面](../../v8/config/ui-settings.md#enumerations)中進一步瞭解列舉。


## 定義異動訊息範本 {#create-message-template}

每個事件都可以觸發個人化訊息。 為了做到這點，您需要建立符合每個事件型別的訊息範本。 範本包含個人化交易式訊息的必要資訊。 您也可以使用範本來測試訊息預覽，並在傳送給最終目標之前使用種子地址傳送校樣。

### 建立範本

若要建立訊息範本，請遵循下列步驟：

1. 前往Adobe Campaign樹狀結構中的&#x200B;**[!UICONTROL Message Center >Transactional message templates]**&#x200B;資料夾。
1. 在交易式訊息範本清單中，按一下滑鼠右鍵並在下拉式功能表中選取&#x200B;**[!UICONTROL New]**，或按一下交易式訊息範本清單上方的&#x200B;**[!UICONTROL New]**&#x200B;按鈕。

   ![](assets/messagecenter_create_model_001.png)

1. 在傳送視窗中，選取適合您要使用之管道的傳送範本。

   ![](assets/messagecenter_create_model_002.png)

1. 必要時變更其標籤。
1. 選取符合您要傳送之訊息的事件型別。 必須預先建立預定由Adobe Campaign處理的事件型別。 [了解更多](#create-event-types)

   ![](assets/messagecenter_create_model_003.png)

   >[!CAUTION]
   >
   >事件型別絕不可連結至多個範本。

1. 輸入性質和說明，然後按一下&#x200B;**[!UICONTROL Continue]**&#x200B;以建立郵件內文。

### 建立內容{#create-message-content}

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

1. 輸入外部識別碼：此選擇性欄位可讓您輸入商業金鑰（唯一ID、名稱+電子郵件等） 這是您網站上所有應用程式通用的功能，用來識別您的設定檔。 如果此欄位也出現在Adobe Campaign行銷資料庫中，您可以接著將事件與資料庫中的設定檔進行調解。

   ![](assets/messagecenter_create_seed_2.png)

1. 插入測試資料。 請參閱[本節](#personalization-data)。

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

### 傳送證明

您可以傳送證明至先前建立的種子地址，以測試訊息傳送。

傳送證明的過程與傳送證明的過程相同。 在[本節](../send/preview-and-proof.md)中進一步瞭解校訂。

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

## Publish範本 {#publish-message-template}

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
