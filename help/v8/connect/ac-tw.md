---
title: 使用Campaign和Twitter
description: 了解如何整合您的Campaign環境與Twitter
role: User, Admin
level: Beginner, Intermediate
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 1baeb8827a0eab4f9487bb5e5afe4d779e00efe4
workflow-type: tm+mt
source-wordcount: '1061'
ht-degree: 4%

---

# 使用Campaign和Twitter{#tw-ac-ovv}

此 **管理社交網路（社交行銷）** 模組可讓您透過Twitter與客戶互動。 使用此功能可：

* 張貼訊息並傳送DM — 使用Adobe Campaign Social Marketing在Twitter上張貼訊息。 您也可以傳送直接訊息給所有追隨者。

* 收集新的聯絡人 — Adobe Campaign Social Marketing也可讓您輕鬆取得新的聯絡人：聯絡使用者，詢問他們是否要共用其設定檔資訊。 如果他們接受，Adobe Campaign會自動恢復資料，這可讓您執行定位促銷活動，並在可能時實施跨管道策略。

![](../assets/do-not-localize/speech.png) 作為托管Cloud Services用戶， [連絡Adobe](../start/campaign-faq.md#support) 將Campaign與Twitter連線。 此  **管理社交網路（社交行銷）** 必須透過專用套件在您的環境中安裝附加元件，且必須設定Twitter外部帳戶。


若要設定Adobe Campaign以張貼推文至您的Twitter帳戶，請為這些帳戶委派對Adobe Campaign的寫入存取權。 要執行此操作，您必須：

1. 建立Twitter帳戶並註冊開發人員帳戶。 [了解更多](#dev-account)
1. （選用）建立用於傳送校樣的測試Twitter帳戶。 [了解更多](#tw-test-account)
1. 建立Twitter應用程式(每個Twitter帳戶一個應用程式)。 [了解更多](#create-an-app-on-twitter)
1. 為 **[!UICONTROL Twitter]** (每個Twitter帳戶一項服務)。 [了解更多](#create-tw-service)
1. 將您的Twitter帳戶與Campaign同步。 [了解更多](#synchro-tw-accounts)

## Twitter開發人員帳戶 {#dev-account}

若要開始進行這項整合，您必須註冊 [Twitter開發人員帳戶](https://developer.twitter.com){target="_blank"}.

Campaign使用1.1版的Twitter API。 若要使用此功能，您需要透過開發人員入口網站申請提升存取權。 進一步了解Twitter Elighed Access [在本頁](https://developer.twitter.com/en/portal/products/elevated){target="_blank"}.

## 在Twitter上建立應用程式 {#create-an-app-on-twitter}

在您以提升的存取權獲得核准後，請建立Twitter應用程式，讓Adobe Campaign將推文張貼至您的Twitter帳戶。 要執行此操作，請遵循下列步驟：

1. 登入您的Twitter帳戶。
1. 連線至 [Twitter開發人員入口網站](https://developer.twitter.com/en/apps).
1. 選擇 **建立應用程式**.
1. 讓Twitter助理引導您完成程式。
1. 若要允許Adobe Campaign將推文張貼至您的帳戶，請編輯至 **應用程式權限** （位於應用程式的「使用者驗證設定」區段）。 選擇 **讀、寫和直接消息**.

   ![](assets/tw-permissions.png)

1. 在 **應用程式類型** 部分，選擇 **網頁應用程式、自動化應用程式或機器人**. 您可以將 **回呼URL** 欄位空白，並儲存您的設定。

   ![](assets/tw-app-type.png)

1. 返回應用程式控制面板，選取您的應用程式並瀏覽至 **金鑰和代號** 標籤。 在 **存取權杖與密碼**，若 **讀、寫和直接消息** 權限未提及，您必須重新產生應用程式的代號和密碼。 請注意，所有金鑰和代號都必須在建立時儲存。 您需要他們來設定您的Campaign Twitter服務。

   ![](assets/tw-permissions-check.png)


>[!NOTE]
>
>每個Twitter帳戶需要一個應用程式。 因此，您必須建立其他測試應用程式，以傳送校樣至您的測試帳戶。

## 在Campaign中建立Twitter服務 {#create-tw-service}

若要將您的Campaign執行個體與Twitter帳戶連結，請建立 **Twitter** 服務及委派對Campaign的寫入存取權。

>[!CAUTION]
>
>建立 **Twitter** 每個Twitter帳戶的服務。 因此，您必須建立其他測試服務，將校樣傳送至您的 [測試帳戶](#tw-test-account).
>
>每個 **Twitter** 服務也必須由Adobe在您的MID執行個體上建立。 請連絡您的Adobe代表以設定您的環境。

若要輸入設定，您必須同時存取Adobe Campaign主控台和Twitter應用程式權限。

1. 在 **Adobe Campaign**，瀏覽至 **[!UICONTROL Profiles and targets]** ，然後選取 **[!UICONTROL Services and Subscriptions]** 連結
1. 建立新服務。
1. 選取 **[!UICONTROL Twitter]** 類型。
1. 輸入服務的標籤和內部名稱。

   >[!CAUTION]
   >
   >此 **[!UICONTROL Internal name]** 服務的名稱必須與您的Twitter帳戶的名稱完全相同。

1. 依預設，追隨者會儲存在 **[!UICONTROL Visitors]** 檔案夾。 您可以從 **[!UICONTROL Visitor folder]** 欄位。 [了解更多](../send/twitter.md#direct-tw-messages)

   ![](assets/tw-service-in-ac.png)

   >[!NOTE]
   >
   >此 **[!UICONTROL Synchronize subscriptions]** 選項預設為啟用：此選項會自動復原您的Twitter追隨者清單，以便您 [傳送直接訊息](../send/twitter.md#direct-tw-messages). 同步由 [專屬技術工作流程](#synchro-tw-accounts).

1. 從您的Twitter應用程式，複製 **API金鑰** 和 **[API金鑰密碼]** 欄位並貼入 **[!UICONTROL Consumer key]** 和 **[!UICONTROL Consumer secret]** 行銷活動欄位 **Twitter** 服務。

1. 從您的Twitter應用程式，複製 **存取權杖** 和 **存取權杖密碼** 欄位並貼入 **[!UICONTROL Access token]** 和 **[!UICONTROL Access token secret]** 行銷活動欄位 **Twitter** 服務。

1. 在Campaign用戶端主控台中，按一下 **[!UICONTROL Save]**. 您現在已委派寫入存取權給Adobe Campaign。

若要檢查您的設定，您可以：

* 編輯 **Twitter** 服務。
* 瀏覽 **[!UICONTROL Twitter page]** 標籤：您的Twitter帳戶。
   ![](assets/tw-page.png)


## 同步您的Twitter帳戶 {#synchro-tw-accounts}

Campaign與Twitter之間的同步是透過專屬的技術工作流程來管理。 這些工作流程會儲存在 **[!UICONTROL Administration > Production > Technical workflows > Managing social networks]** 檔案夾。

預設會停止它們：您必須在開始使用時手動啟動 **社交行銷** 模組。

此 **[!UICONTROL Synchronization of Twitter accounts]** 技術工作流程會同步Adobe Campaign中的Twitter帳戶。 此工作流程會復原Twitter追隨者的清單，以便您傳送直接訊息。 [了解更多](../send/twitter.md#direct-tw-messages)

依預設，此工作流程會在每星期四早上7:30觸發。 您可以使用 **[!UICONTROL Execute pending task(s) now]** 選項，在您實作此整合時隨時啟動工作流程。  您也可以編輯排程器以變更工作流程觸發頻率。 在[本頁](../../automation/workflow/scheduler.md)中瞭解更多。

>[!CAUTION]
>
>若要復原Twitter訂閱者清單，請 **[!UICONTROL Twitter account synchronization]** 必須針對連結至帳戶的服務檢查選項。 [了解更多](#create-tw-service)

追隨者會儲存在特定表格中：訪客表格。 若要顯示Twitter追隨者清單，請瀏覽至 **[!UICONTROL Profiles and Targets > Visitors]**.

Adobe Campaign會針對每個追隨者儲存下列資訊：

* **[!UICONTROL Origin]**: Twitter
* **[!UICONTROL External ID]**:使用者識別碼
* **[!UICONTROL Username]**:使用者的帳戶名稱
* **[!UICONTROL Full name]**:用戶名
* **[!UICONTROL Number of friends]**:跟隨者數
* **[!UICONTROL Checked]**:此欄位指出使用者是否擁有已驗證的Twitter帳戶

完成此設定後，您就可以張貼推文至您的Twitter帳戶，並傳送直接訊息給您的追隨者。 [了解更多](../send/twitter.md)

## 在Twitter上建立測試帳戶 {#tw-test-account}

除了Twitter帳戶外，請建立可用於傳送的私人Twitter帳戶 [推文校樣](../send/twitter.md#send-tw-proofs). 要執行此操作，請遵循下列步驟：

1. 建立新的Twitter帳戶。
1. 存取帳戶  **設定**.
1. 瀏覽至 **隱私與安全** 和 **對象和標籤** 並檢查 **Protect您的推文** 選項。 您的推文和其他帳戶資訊只會顯示給追隨您的人。

![](assets/social_tw_test_page.png)

如上所述，設定您的Twitter應用程式和Campaign服務以搭配此測試帳戶運作。
