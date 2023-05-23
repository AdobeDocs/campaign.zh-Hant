---
title: 市場活動事務性消息
description: 開始事務性消息傳遞
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 06fdb279-3776-433f-8d27-33d016473dee
source-git-commit: 3c7455f348468a8f00fb853a3269a1d63b81e7b8
workflow-type: tm+mt
source-wordcount: '1491'
ht-degree: 1%

---

# 開始事務性消息傳遞{#send-transactional-messages}

事務性消息傳遞（消息中心）是一個市場活動模組，用於管理觸發消息。 這些通知是從資訊系統觸發的事件生成的，可以是：發票、訂單確認、發運確認、密碼更改、產品不可用通知、帳戶對帳單、網站帳戶建立等。

![](../assets/do-not-localize/speech.png)  作為托管Cloud Services用戶， [聯繫人Adobe](../start/campaign-faq.md#support){target="_blank"} 在您的環境中配置市場活動事務性消息傳遞。

事務性消息用於發送：

* 通知，例如訂單確認或密碼重置
* 對客戶行為的單獨即時響應
* 非促銷內容

事務性消息傳送設定在 [此部分](../config/transactional-msg-settings.md)。

瞭解事務性消息傳遞體系結構 [此頁](../architecture/architecture.md#transac-msg-archi)。

## 交易式訊息傳遞操作原則 {#transactional-messaging-operating-principle}

Adobe Campaign事務性消息傳遞模組整合到資訊系統中，該資訊系統將要被更改的事件返回到個性化事務性消息。 這些消息可以單獨或通過電子郵件、簡訊或推式通知批量發送。

例如，假設您是一家擁有網站的公司，客戶可以在該網站上購買產品。

Adobe Campaign允許您向已將產品添加到購物車的客戶發送通知電子郵件。 當其中一個人離開您的網站而未完成其購買（觸發市場活動事件的外部事件）時，將自動向他們發送購物車放棄電子郵件（事務性消息傳遞）。

實施此項措施的主要步驟如下：

1. [建立事件類型](#create-event-types)。
1. [建立和設計消息模板](#create-message-template)。 在此步驟中，必須將事件連結到您的消息。
1. [Test消息](#test-message-template)。
1. [發佈消息模板](#publish-message-template)。

設計並發佈事務性消息模板後，如果觸發了相應的事件，則相關資料將通過PushEvent和PushEvents發送到Campaign [SOAP方法](../send/event-description.md)，並將傳遞發送到目標收件人。

## 建立事件類型 {#create-event-types}

要確保每個事件都可以更改為個性化郵件，您首先需要建立 **事件類型**。

當 [建立消息模板](#create-message-template)，您將選擇與要發送的消息匹配的事件類型。

>[!CAUTION]
>
>必須先建立事件類型，然後才能在消息模板中使用它們。

要建立將由Adobe Campaign處理的事件類型，請執行以下步驟：

1. 瀏覽到 **[!UICONTROL Administration > Platform > Enumerations]** 市場活動瀏覽器的資料夾。
1. 選擇 **[!UICONTROL Event type]** 清單中的枚舉。
1. 按一下 **[!UICONTROL Add]** 建立枚舉值。 這可以是訂單確認、密碼更改、訂單交貨更改等。

   ![](assets/messagecenter_eventtype_enum_001.png)

   >[!CAUTION]
   >
   >每個事件類型都必須與 **[!UICONTROL Event type]** 枚舉。

1. 建立明細化清單值後，註銷並返回實例以使建立生效。

>[!NOTE]
>
>瞭解有關中枚舉的詳細資訊 [此頁](../../v8/config/ui-settings.md#enumerations)。


## 定義事務性消息模板 {#create-message-template}

每個事件都可觸發個性化消息。 為了實現此目的，您需要建立一個消息模板以匹配每個事件類型。 模板包含個性化事務性消息的必要資訊。 您還可以使用模板test消息預覽，並在傳送到最終目標之前使用種子地址發送校樣。

### 建立模板

要建立消息模板，請執行以下步驟：

1. 轉到 **[!UICONTROL Message Center >Transactional message templates]** 資料夾。
1. 在事務性消息模板清單中，按一下右鍵並選擇 **[!UICONTROL New]** 或按一下 **[!UICONTROL New]** 按鈕。

   ![](assets/messagecenter_create_model_001.png)

1. 在交貨窗口中，選擇適合要使用的渠道的交貨模板。

   ![](assets/messagecenter_create_model_002.png)

1. 如有必要，請更改其標籤。
1. 選擇與您要發送的消息匹配的事件類型。 必須事先建立要由Adobe Campaign處理的事件類型。 [了解更多](#create-event-types)

   ![](assets/messagecenter_create_model_003.png)

   >[!CAUTION]
   >
   >事件類型永遠不應連結到多個模板。

1. 輸入屬性和說明，然後按一下 **[!UICONTROL Continue]** 的子菜單。

### 建立內容{#create-message-content}

事務性消息內容的定義與Adobe Campaign所有遞送的定義相同。 例如，對於電子郵件傳遞，您可以以HTML或文本格式建立內容、添加附件或個性化傳遞對象。 [了解更多](../start/create-message.md)。

>[!CAUTION]
>
>郵件中包含的影像必須可以公開訪問。 Adobe Campaign沒有為事務性消息提供任何映像上載機制。\
>與JSSP或WebApp不同， `<%=` 沒有任何預設轉義符。
>
>必須正確地從事件中轉移每個資料。 此轉義取決於此欄位的使用方式。 例如，在URL中，請使用encodeURIComponent。 要在HTML中顯示，可以使用escapeXMLString。

定義消息內容後，可以將事件資訊整合到消息正文中並對其進行個性化設定。 由於個性化標籤，事件資訊被插入文本正文中。

![](assets/messagecenter_create_content.png)

* 所有個性化欄位都來自負載。
* 在事務性消息中可以引用一個或多個個性化塊。 <!--The block content will be added to the delivery content during the publication to the execution instance.-->

要將個性化標籤插入電子郵件的正文中，請應用以下步驟：

1. 在消息模板中，按一下與電子郵件格式(HTML或文本)匹配的頁籤。
1. 輸入消息的正文。
1. 在文本正文中，使用 **[!UICONTROL Real time events>Event XML]** 菜單開啟它。

   ![](assets/messagecenter_create_custo_1.png)

1. 使用以下語法填充標籤： **元素名稱**。@**屬性名稱** 如下所示。

   ![](assets/messagecenter_create_custo_2.png)

## Test事務性消息模板 {#test-message-template}

### 新增種子地址{#add-seeds}

種子地址允許您在發送消息之前顯示消息的預覽、發送證明和test消息個性化。 種子地址連結到交貨，不能用於其他交貨。

1. 在事務性消息模板中，按一下 **[!UICONTROL Seed addresses]** ，然後按一下 **[!UICONTROL Add]** 按鈕

   ![](assets/messagecenter_create_seed_1.png)

1. 為標籤分配標籤，以便以後進行輕鬆選擇，然後輸入種子地址（根據通信通道的不同，電子郵件或行動電話）。

1. 輸入外部標識符：此可選欄位允許您輸入業務密鑰（唯一ID、名稱+電子郵件等） 用於標識您的配置檔案的所有應用程式所共有的。 如果此欄位也存在於Adobe Campaign市場營銷資料庫中，則可以將事件與資料庫中的配置檔案協調起來。

   ![](assets/messagecenter_create_seed_2.png)

1. 插入test資料。 請參閱[本節](#personalization-data)。

   ![](assets/messagecenter_create_custo_3.png)

1. 按一下 **[!UICONTROL Ok]** 確認種子地址的建立。

1. 重複該過程，以根據需要建立盡可能多的地址。

   ![](assets/messagecenter_create_seed_6.png)

建立地址後，您可以訪問其預覽和個性化。

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

### 預覽事務性消息{#transactional-message-preview}

建立一個或多個種子地址和消息正文後，可以預覽消息並檢查其個性化設定。

1. 在消息模板中，按一下 **[!UICONTROL Preview]** ，然後選擇 **[!UICONTROL A seed address]** 的下界。

   ![](assets/messagecenter_preview_1.png)

1. 選擇以前建立的種子地址以顯示個性化消息。

   ![](assets/messagecenter_create_seed_7.png)

### 傳送證明

您可以通過向先前建立的種子地址發送證明來test消息傳遞。

發送證據涉及與任何交貨相同的流程。 瞭解有關中的校樣的詳細資訊 [此部分](../send/preview-and-proof.md)。

但是，要發送事務性消息的證明，您需要執行以下操作：

* 建立一個或多個 [種子地址](#add-seeds) 具有個性化test資料
* 建立郵件內容

要發送證明：

1. 按一下 **[!UICONTROL Send a proof]** 按鈕。
1. 分析交貨。
1. 更正所有錯誤並確認交貨。

   ![](assets/messagecenter_send_proof_001.png)

1. 檢查郵件是否已發送到種子地址，其內容是否符合您的配置。

   ![](assets/messagecenter_send_proof_002.png)

可通過 **[!UICONTROL Audit]** 頁籤。

![](assets/messagecenter_send_proof_003.png)

## 發佈模板 {#publish-message-template}

建立消息模板時<!-- on the control instance--> 完成後，您可以發佈它，這將允許您發送連結到即時事件和批處理事件的消息。

<!--This process will also publish it on all execution instances.

NOTE: When publishing transactional message templates, typology rules are also automatically published on the execution instances.

Publication lets you automatically create two message templates on the execution instances, which will allow you to send messages linked to real-time and batch events.-->

>[!CAUTION]
>
>無論何時對模板進行任何更改，請確保再次發佈該模板以使這些更改在事務性消息傳遞期間有效。

1. 轉到 **[!UICONTROL Message Center > Transactional message templates]** 資料夾。
1. 選擇要發佈的模板<!--on your execution instances-->。
1. 按一下&#x200B;**[!UICONTROL Publish]**。

   ![](assets/messagecenter_publish_template.png)

發佈完成後，將在中建立要應用於批處理和即時類型事件的消息模板 **[!UICONTROL Administration > Production > Message Center Execution> Default > Transactional message templates]** 的子菜單。

![](assets/messagecenter_deployed_model.png)

模板發佈後，如果觸發了相應事件，Adobe Campaign<!--execution instance--> 將接收事件，將其連結到事務模板，並將相應的事務消息發送給每個收件人。

<!--
>[!NOTE]
>
>If you replace an existing field of the transactional message template, such as the sender address, with an empty value, the corresponding field on the execution instance(s) will not be updated once the transactional message is published again. It will still contain the previous value.
>
>However, if you add a non-empty value, the corresponding field will be updated as usual after the next publication.
-->

## 取消發佈模板

發佈消息模板後 <!--on the execution instances-->可以取消發佈。

* 事實上，如果觸發了相應事件，仍可調用已發佈模板：如果您不再使用消息模板，建議取消發佈該模板。 這樣可以避免錯誤地發送不需要的事務性消息。

   例如，您發佈了一個僅用於聖誕節市場活動的消息模板。 你可能想在聖誕節期間結束後取消發佈，並在明年再次發佈。

* 此外，您不能刪除具有 **[!UICONTROL Published]** 狀態。 必須先取消發佈它。

要取消發佈事務性消息模板，請執行以下步驟。

1. 瀏覽到 **[!UICONTROL Message Center > Transactional message templates]** 的子菜單。
1. 選擇要取消發佈的模板。
1. 按一下&#x200B;**[!UICONTROL Unpublish]**。
1. 按一下&#x200B;**[!UICONTROL Start]**。

![](assets/message-center-unpublish.png)

事務性消息模板狀態從 **[!UICONTROL Published]** 至 **[!UICONTROL Being edited]**。

一旦取消發佈完成：

* 將刪除兩個消息模板（應用於批處理和即時類型事件）<!-- from each execution instance-->。

   它們不再出現在 **[!UICONTROL Administration > Production > Message Center Execution > Default > Transactional message templates]** 的子菜單。

* 取消發佈模板後，您可以將其刪除<!-- from the control instance-->。

   為此，請從清單中選擇它，然後按一下 **[!UICONTROL Delete]** 按鈕。
