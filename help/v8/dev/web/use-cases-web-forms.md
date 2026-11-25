---
product: campaign
title: 使用實例：網路表單
description: 使用實例：網路表單
feature: Web Forms
version: Campaign v8, Campaign Classic v7
exl-id: 7aa4646d-1325-47c2-b553-6fe375c48973
TQID: 'https://experienceleague.adobe.com/Zw-cfoQrq1PAe-swZ7gvMNyTb4ciCMF2kdT7fN2zLsg'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: f391046b-0cf3-4e76-bd3b-97fe06654506
    internal-label: Web Apps
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
  - id: e739ee2b-6228-412e-878f-45de0791417d
    internal-label: Use cases
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '1451'
ht-degree: 1%
---
# 使用實例：網路表單{#use-cases-web-forms}



## 建立包含雙重選擇加入的訂閱表單 {#create-a-subscription--form-with-double-opt-in}

提供資訊服務時，收件者必須訂閱才能接收所有連結的通訊。 為避免通訊不當並確保收件者刻意訂閱，建議您傳送訂閱確認請求以建立雙重選擇加入。 只有當使用者按一下確認訊息中包含的連結時，訂閱才會生效。

此範例根據下列情境而定：

1. 在包含訂閱暫時服務核取方塊的網站上建立電子報訂閱表單。 此服務可讓您傳遞訂閱確認訊息。
1. 使用連結至網頁表單的傳遞範本建立訂閱確認傳遞。 其中包含確認連結，可呼叫電子報訂閱的表單，並顯示訂閱核准訊息。

### 步驟1 — 建立資訊服務 {#step-1---creating-information-services}

1. 建立要提供給收件者的電子報訂閱服務。 如需如何建立Newsletter的詳細資訊，請參閱[本節](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/subscriptions-and-referrals/about-services-and-subscriptions){target="_blank"}。

   ![每週新聞稿服務的服務對話方塊，包含標籤、內部名稱、輸入電子郵件和模式新聞稿欄位。](assets/s_ncs_admin_survey_double-opt-in_sample_1.png)

1. 建立第二個資訊服務，此服務是連結至傳遞範本的暫時服務，用於傳送訂閱確認訊息。

   ![臨時服務(temp_service)儀表板，顯示型別電子郵件、模式新聞稿及其資料夾。](assets/s_ncs_admin_survey_double-opt-in_sample_1c.png)

### 步驟2 — 建立確認訊息 {#step-2---creating-confirmation-messages}

確認訊息會透過在臨時服務層級參考的專用傳遞範本傳送。

1. 在&#x200B;**[!UICONTROL Explorer]**&#x200B;中，選取&#x200B;**[!UICONTROL Resources > Templates > Delivery templates]**。
1. 建立傳送訂閱確認訊息的傳遞範本。
1. 按一下&#x200B;**[!UICONTROL Email parameters]**&#x200B;中的&#x200B;**[!UICONTROL To]**&#x200B;按鈕，將傳遞範本與訂閱目標對應而非收件者建立關聯。

   已選取訂閱(nms:subscription)目標對應的傳遞範本上的![Select目標對話方塊。](assets/s_ncs_admin_survey_double-opt-in_sample_1d.png)

1. 由於此傳遞的收件者尚未確認其核准，因此他們仍位於資料庫封鎖清單中。 為了讓收件者接收此通訊，您必須根據此範本授權傳遞，以鎖定封鎖清單上的收件者。

   若要這麼做，請按一下&#x200B;**[!UICONTROL Exclusions]**&#x200B;標籤。

1. 按一下&#x200B;**[!UICONTROL Edit...]**&#x200B;連結，並取消勾選&#x200B;**[!UICONTROL Exclude recipients who no longer want to be contacted]**&#x200B;選項。

   <!-- ![](assets/s_ncs_admin_survey_double-opt-in_sample_4d.png)-->

   >[!IMPORTANT]
   >
   >此選項只能在此型別的內容中停用。

1. 個人化您的傳遞，並將確認連結插入訊息內容。 此連結可讓您存取網路表單，以記錄訂閱確認。

   ![傳遞編輯器中含有名字個人化欄位和[按一下這裡]連結的確認電子郵件。](assets/s_ncs_admin_survey_double-opt-in_sample_1b.png)

1. 使用DCE，將您的URL連結至網頁表單。 由於尚未建立網頁表單，請在建立後立即取代值。

   ![含有網頁應用程式欄位的超文字連結窗格，該欄位仍為空白，用於確認電子郵件中的[按一下這裡]連結。](assets/s_ncs_admin_survey_double-opt-in_sample_3.png)

1. 最後，將此範本連結至先前建立的臨時服務。

   ![在[訂閱]欄位中選取確認傳遞的[暫時服務編輯]索引標籤。](assets/s_ncs_admin_survey_double-opt-in_sample_3c.png)

### 步驟3 — 建立訂閱表單 {#step-3---creating-the-subscription-form}

網頁表單會同時啟用收件者訂閱和訂閱確認。

網路表單工作流程將包含下列活動：

![網頁表單工作流程：預先載入、測試，然後以電子郵件空白銷售機會進入指令碼封鎖清單、訂閱、儲存、結束。](assets/s_ncs_admin_survey_double-opt-in_sample_4c.png)

要執行此操作，請遵循下列步驟：

1. 建立網路表單並選擇範本&#x200B;**[!UICONTROL Newsletter subscription (subNewsletter)]**。

   ![新增Web應用程式對話方塊，其中已選取電子報訂閱(subNewsletter)範本。](assets/s_ncs_admin_survey_double-opt-in_sample_5a.png)

1. 在&#x200B;**[!UICONTROL Edit]**&#x200B;索引標籤中，我們需要設定現有的工作流程，因為我們要新增確認訊息給要訂閱的收件者。

   若要這麼做，請連按兩下&#x200B;**[!UICONTROL Preloading]**&#x200B;方塊並按如下方式設定。

   ![使用表單中參考的自動載入資料預先載入活動對話方塊，且若未選取任何ID，則略過預先載入。](assets/s_ncs_admin_survey_double-opt-in_sample_5b.png)

   這表示如果使用者透過確認訊息中的連結存取此表單，則會載入其設定檔資訊。 如果他們透過網站的頁面存取網頁表單，則不會載入任何資訊。

1. 將&#x200B;**[!UICONTROL Test]**&#x200B;活動新增至工作流程。

   ![網頁表單工作流程，其測試活動在電子郵件上以空白分支至訂閱、儲存和結束。](assets/s_ncs_admin_survey_double-opt-in_sample_6e.png)

   **[!UICONTROL Test]**&#x200B;活動可能涉及收件者電子郵件。 在此情況下，請依照以下方式設定：

   ![條件@email非空白的測試活動分支編輯器。](assets/s_ncs_admin_survey_double-opt-in_sample_6d.png)

1. 新增兩個&#x200B;**[!UICONTROL Script]**&#x200B;活動至您的工作流程。

   ![網頁表單工作流程，在測試活動的每個分支上都有指令碼活動。](assets/s_ncs_admin_survey_double-opt-in_sample_6f.png)

   前&#x200B;**[!UICONTROL Script]**&#x200B;個活動會在封鎖清單中新增收件者，直到他們確認訂閱電子報為止。 其內容必須如下：

   ```javascript
   ctx.recipient.@blackList=1
   ```

   ![包含指令碼ctx.recipient.@blackList=1的指令碼封鎖清單活動。](assets/s_ncs_admin_survey_double-opt-in_sample_6bbis.png)

   第二個&#x200B;**[!UICONTROL Script]**&#x200B;活動會授權要傳送給使用者的傳送，並訂閱電子報。 指令碼的最後兩行將可讓您將收件者從暫存資料夾轉移至另一個資料夾，並在他們確認訂閱後立即與現有設定檔進行調解。

   ```javascript
   ctx.recipient.@blackList=0
   nms.subscription.Subscribe("INTERNAL_NAME_OF_THE_NEWSLETTER", ctx.recipient, false)
   ctx.recipient.folder = <folder name="nmsRootRecipient"/>
   nms.subscription.Unsubscribe("TEMP", ctx.recipient)
   ```

   >[!NOTE]
   >
   >也可以使用工作流程定期清除&#x200B;**[!UICONTROL Temp]**&#x200B;資料分割。

   ![第二個指令碼活動，包含取消封鎖清單、訂閱、資料夾和取消訂閱指令碼行。](assets/s_ncs_admin_survey_double-opt-in_sample_6b.png)

1. 連按兩下&#x200B;**[!UICONTROL Subscription]**&#x200B;活動以個人化訂閱表單，並將核取方塊與先前建立的臨時服務連結。

   ![頁面編輯器，其同意核取方塊連結至[服務]欄位中的[暫存服務]。](assets/s_ncs_admin_survey_double-opt-in_sample_5c.png)

1. 設定&#x200B;**[!UICONTROL Storage]**&#x200B;活動以儲存表單頁面中輸入的資訊。

   此活動可讓您在專用的臨時資料夾中建立收件者設定檔，將它們與資料庫中可傳送通訊的設定檔區分開。

   ![儲存活動對話方塊，將Temp資料夾設定為建立資料夾。](assets/s_ncs_admin_survey_double-opt-in_sample_5g.png)

   >[!NOTE]
   >
   >您不得定義任何調解選項。

1. 新增兩個&#x200B;**[!UICONTROL End]**&#x200B;活動來為使用者顯示訊息。

   訂閱完成後，第二個&#x200B;**[!UICONTROL End]**&#x200B;方塊將顯示確認訊息。

   ![結束活動對話方塊，其中訊息您的訂閱已完成。 您很快就會收到我們的電子報。](assets/s_ncs_admin_survey_double-opt-in_sample_5h.png)

1. 建立及設定網頁表單後，您現在可以在傳送範本中參考該表單，以傳送確認訊息。

   ![使用Click here連結的確認傳遞，指向電子報訂閱雙重選擇加入Web應用程式。](assets/s_ncs_admin_survey_double-opt-in_sample_7b.png)

### 步驟4 — 發佈和測試表單 {#step-4---publishing-and-testing-the-form}

您現在可以發佈表單，讓使用者能夠存取。

![具有[發佈]按鈕的Web應用程式儀表板，以及必須發佈才能線上存取的訊息。](assets/s_ncs_admin_survey_double-opt-in_sample_8b.png)

訂閱電子報涉及以下步驟：

1. 網站使用者登入訂閱頁面並核准表單。

   ![瀏覽器中的Newsletter訂閱表單，已填入名稱及電子郵件、已核取同意方塊及我訂閱按鈕。](assets/s_ncs_admin_survey_double-opt-in_sample_8c.png)

   使用者會透過瀏覽器中的訊息收到通知，告知其請求已納入考量。

   ![瀏覽器結束頁面顯示要求已註冊，之後將會顯示訊息。](assets/s_ncs_admin_survey_double-opt-in_sample_8d.png)

   使用者已新增至&#x200B;**[!UICONTROL Temp]**&#x200B;資料夾中的Adobe Campaign資料庫，且他們的設定檔已加入封鎖清單，直到他們透過電子郵件確認訂閱為止。

   ![已選取新設定檔的臨時收件者資料夾，且已勾選「不再連絡（透過任何管道）」。](assets/s_ncs_admin_survey_double-opt-in_sample_8f.png)

1. 系統會將確認訊息（包含核准其訂閱的連結）傳送給他們。

   ![訂閱確認電子郵件，內含Click here連結，以確認Newsletter訂閱。](assets/s_ncs_admin_survey_double-opt-in_sample_8e.png)

1. 當使用者按一下此連結時，其瀏覽器中會顯示核准頁面。

   ![標題為恭喜的瀏覽器頁面！ 確認訂閱目前作用中。](assets/s_ncs_admin_survey_double-opt-in_sample_8.png)

   在Adobe Campaign中，使用者設定檔已更新：

   * 他們不再位於封鎖清單中，
   * 他們訂閱了資訊服務。

     ![已更新收件者設定檔，其中不再連絡人已清除，且列出了Newsletter影片訂閱。](assets/s_ncs_admin_survey_double-opt-in_sample_9.png)

## 根據選取的值顯示不同的選項 {#displaying-different-options-depending-on-the-selected-values}

在下列範例中，系統會要求使用者選取車輛型別。 您可以根據選取的型別顯示可用的車輛類別。 這表示右側欄中顯示的專案取決於使用者的選擇：

![汽車選擇頁面，其[汽車型別]下拉式清單設定為Select。](assets/s_ncs_admin_survey_condition_sample0.png)

* 當使用者選擇「私家車」時，可選擇「緊密」和「小貨車」。

  ![已選取「個人汽車」的「汽車選擇」頁面，顯示「標準」和「緊密」選項。](assets/s_ncs_admin_survey_condition_sample2.png)

* 當使用者選擇「商用車輛」時，選擇專案會顯示在下拉式清單中：

  ![已選取「搬運卡車」的車輛選擇頁面，以及車輛型別的「類別」下拉式清單。](assets/s_ncs_admin_survey_condition_sample1.png)

在此範例中，車輛型別不會儲存在資料庫中。 下拉式清單的設定如下：

![具有Select、Personal car和Moving truck值的汽車下拉式方塊屬性型別。](assets/s_ncs_admin_survey_condition_config1.png)

此資訊儲存在區域變數中。

在容器中設定右側欄的條件式顯示：

![為car欄位型別選取[變數]選項的[儲存]對話方塊。](assets/s_ncs_admin_survey_condition_config1bis.png)

* 適用於私人車輛的條件式欄位可見性：

  ![個人汽車容器的可見性條件：汽車型別等於個人汽車。](assets/s_ncs_admin_survey_condition_config2.png)

* 商用車輛的條件式欄位可見性：

  ![卡車/貨車貨櫃的可見度狀況：汽車型別等於搬運卡車。](assets/s_ncs_admin_survey_condition_config3.png)
