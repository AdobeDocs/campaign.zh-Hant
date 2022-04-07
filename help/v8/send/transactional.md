---
title: 市場活動事務性消息
description: 開始事務性消息傳遞
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 06fdb279-3776-433f-8d27-33d016473dee
source-git-commit: 63b53fb6a7c6ecbfc981c93a723b6758b5736acf
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 2%

---

# 開始事務性消息傳遞{#send-transactional-messages}

事務性消息傳遞（消息中心）是一個市場活動模組，用於管理觸發消息。 這些消息是從資訊系統觸發的事件生成的，可以是：例如，發票、訂單確認、發運確認、密碼更改、產品不可用性通知、帳戶對帳單或網站帳戶建立。

![](../assets/do-not-localize/speech.png)  作為托管Cloud Services用戶， [聯繫人Adobe](../start/campaign-faq.md#support) 在您的環境中安裝和配置市場活動事務性消息傳遞。

事務性消息用於發送：

* 通知，例如訂單確認或密碼重置
* 對客戶行為的單獨即時響應
* 非促銷內容

![](../assets/do-not-localize/glass.png) 事務性消息傳送設定在 [此部分](../config/transactional-msg-settings.md)。

![](../assets/do-not-localize/glass.png) 瞭解中的事務性消息傳遞體系結構 [此頁](../dev/architecture.md)。

>[!CAUTION]
>
>事務性消息傳遞需要特定的許可證。 請檢查您的授權合約。

## 定義事務性消息模板

每個事件都可觸發個性化消息。 為了實現此目的，您需要建立一個消息模板以匹配每個事件類型。 模板包含個性化事務性消息的必要資訊。 您還可以使用模板test消息預覽，並在傳送到最終目標之前使用種子地址發送校樣。

### 建立模板

要建立消息模板，請執行以下步驟：

1. 轉到 **[!UICONTROL Message Center >Transactional message templates]** 資料夾。
1. 在事務性消息模板清單中，按一下右鍵並選擇 **[!UICONTROL New]** 或按一下 **[!UICONTROL New]** 按鈕。

   ![](assets/messagecenter_create_model_001.png)

1. 在交貨窗口中，選擇適合要使用的渠道的交貨模板。

   ![](assets/messagecenter_create_model_002.png)

1. 如有必要，請更改其標籤。
1. 選擇與您要發送的消息匹配的事件類型。

   ![](assets/messagecenter_create_model_003.png)

   必須通過Adobe在控制實例上建立目標為Adobe Campaign處理的事件類型。

   >[!NOTE]
   >
   >事件類型永遠不應連結到多個模板。

1. 輸入屬性和說明，然後按一下 **[!UICONTROL Continue]** 的子菜單。 請參閱 [建立郵件內容](#create-message-content)。

### 建立內容{#create-message-content}

事務性消息內容的定義與Adobe Campaign所有遞送的定義相同。 例如，對於電子郵件傳遞，您可以以HTML或文本格式建立內容、添加附件或個性化傳遞對象。 如需詳細資訊，請參閱[本章節](../start/create-message.md)。

>[!CAUTION]
>
>郵件中包含的影像必須可以公開訪問。 Adobe Campaign沒有為事務性消息提供任何映像上載機制。\
>與JSSP或WebApp不同， `<%=` 沒有任何預設轉義符。
>
>必須正確地從事件中轉移每個資料。 此轉義取決於此欄位的使用方式。 例如，在URL中，請使用encodeURIComponent。 要在HTML中顯示，可以使用escapeXMLString。

定義消息內容後，可以將事件資訊整合到消息正文中並對其進行個性化設定。 由於個性化標籤，事件資訊被插入文本正文中。

![](assets/messagecenter_create_content.png)

* 所有個性化欄位都來自負載。
* 在事務性消息中可以引用一個或多個個性化塊。 塊內容將在發佈到執行實例期間添加到傳遞內容。

要將個性化標籤插入電子郵件的正文中，請應用以下步驟：

1. 在消息模板中，按一下與電子郵件格式(HTML或文本)匹配的頁籤。
1. 輸入消息的正文。
1. 在文本正文中，使用 **[!UICONTROL Real time events>Event XML]** 菜單開啟它。

   ![](assets/messagecenter_create_custo_1.png)

1. 使用以下語法填充標籤： **元素名稱**。@**屬性名稱** 如下所示。

   ![](assets/messagecenter_create_custo_2.png)

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

### 添加個性化資料{#personalization-data}

您可以在消息模板中添加資料以test事務性消息個性化。 這將允許您生成預覽或發送證明。 如果安裝 **可交付性** 模組，此資料允許您為各種案頭、web或移動客戶端顯示消息的呈現。

此資料的目的是在郵件最終送達之前test郵件。 這些消息與消息中心要處理的實際資料不一致。 但是，XML結構必須與儲存在執行實例中的事件結構相同，如下所示。

![](assets/messagecenter_create_custo_4.png)

此資訊使您能夠使用個性化標籤對消息內容進行個性化。

1. 在消息模板中，按一下 **[!UICONTROL Seed addresses]** 頁籤。
1. 在事件內容中，以XML格式輸入test資訊。

   ![](assets/messagecenter_create_custo_3.png)

### 預覽事務性消息{#transactional-message-preview}

建立一個或多個種子地址和消息正文後，可以預覽消息並檢查其個性化設定。

1. 在消息模板中，按一下 **[!UICONTROL Preview]** ，然後選擇 **[!UICONTROL A seed address]** 的下界。

   ![](assets/messagecenter_preview_1.png)

1. 選擇以前建立的種子地址以顯示個性化消息。

   ![](assets/messagecenter_create_seed_7.png)

### 傳送證明

您可以通過向先前建立的種子地址發送證明來test消息傳遞。

發送證據涉及與任何交貨相同的流程。

![](../assets/do-not-localize/book.png) 瞭解有關中的校樣的詳細資訊 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html?lang=zh-Hant){target=&quot;_blank&quot;

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

### 發佈模板

在控制項實例上建立的消息模板完成後，可以發佈它。 此進程還將在所有執行實例上發佈它。

>[!NOTE]
>
>在發佈事務性消息模板時，類型規則也會自動發佈在執行實例上。

發佈允許您在執行實例上自動建立兩個消息模板，這樣您就可以發送連結到即時和批處理事件的消息。

>[!CAUTION]
>
>無論何時對模板進行任何更改，請確保再次發佈該模板以使這些更改在事務性消息傳遞期間有效。

1. 在控制實例上，轉到 **[!UICONTROL Message Center > Transactional message templates]** 資料夾。
1. 選擇要在執行實例上發佈的模板。
1. 按一下&#x200B;**[!UICONTROL Publish]**。

   ![](assets/messagecenter_publish_template.png)

發佈完成後，將在生產實例的樹中建立要應用於批處理和即時類型事件的消息模板 **[!UICONTROL Administration > Production > Message Center Execution> Default > Transactional message templates]** 的子菜單。

![](assets/messagecenter_deployed_model.png)

一旦發佈了模板，如果觸發了相應的事件，則執行實例將接收該事件，將其連結到事務模板，並將相應的事務消息發送到每個接收者。

>[!NOTE]
>
>如果用空值替換事務性消息模板的現有欄位，則一旦再次發佈事務性消息，將不會更新執行實例上的相應欄位。 它仍將包含上一個值。
>
>但是，如果添加非空值，則在下次發佈後，相應欄位將照常更新。


### 取消發佈模板

在執行實例上發佈消息模板後，可以取消發佈該消息模板。

* 事實上，如果觸發了相應事件，仍可調用已發佈模板：如果您不再使用消息模板，建議取消發佈該模板。 這樣可以避免錯誤地發送不需要的事務性消息。

   例如，您發佈了一個僅用於聖誕節市場活動的消息模板。 你可能想在聖誕節期間結束後取消發佈，並在明年再次發佈。

* 此外，您不能刪除具有 **[!UICONTROL Published]** 狀態。 必須先取消發佈它。

要取消發佈事務性消息模板，請執行以下步驟。

1. 在控制實例上，瀏覽到 **[!UICONTROL Message Center > Transactional message templates]** 的子菜單。
1. 選擇要取消發佈的模板。
1. 按一下&#x200B;**[!UICONTROL Unpublish]**。
1. 按一下&#x200B;**[!UICONTROL Start]**。

![](assets/message-center-unpublish.png)

事務性消息模板狀態從 **[!UICONTROL Published]** 至 **[!UICONTROL Being edited]**。

一旦取消發佈完成：

* 從每個執行實例中刪除兩個消息模板（應用於批處理和即時類型事件）。

   它們不再出現在 **[!UICONTROL Administration > Production > Message Center Execution > Default > Transactional message templates]** 的子菜單。

* 取消發佈模板後，可以從控制項實例中刪除它。

   為此，請從清單中選擇它，然後按一下 **[!UICONTROL Delete]** 按鈕。
