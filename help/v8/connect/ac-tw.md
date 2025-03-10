---
title: 使用Campaign和X (Twitter)
description: 瞭解如何將您的Campaign環境與X （先前稱為Twitter）整合
role: User, Admin
feature: Social Marketing
level: Beginner, Intermediate
exl-id: 5523217a-b95f-4639-b941-52eb7d5a0203
source-git-commit: 42241364c1a23ae75d8f0aaf18a2cb1c04ce5b0c
workflow-type: tm+mt
source-wordcount: '1066'
ht-degree: 3%

---

# 使用Campaign和X (Twitter) {#tw-ac-ovv}

**管理社交網路（社交行銷）**&#x200B;模組可讓您透過X （先前稱為Twitter）與客戶互動。 此功能可用於：

* 張貼訊息並傳送DM — 使用Adobe Campaign社交行銷在X上張貼訊息。您也可以傳送直接訊息給所有追隨者。

* 收集新連絡人 — Adobe Campaign社交行銷也可讓您輕鬆取得新連絡人：聯絡使用者並詢問他們是否要分享其設定檔資訊。 如果他們接受，Adobe Campaign會自動復原資料，讓您能夠執行目標定位行銷活動，並儘可能實施跨管道策略。


>[!NOTE]
>
>作為Managed Cloud Services使用者，[請連絡Adobe](../start/campaign-faq.md#support)以連線Campaign與X。**管理社交網路（社交行銷）**&#x200B;附加元件必須透過專用套件安裝在您的環境中，且必須設定Twitter外部帳戶。


若要設定Adobe Campaign將推文張貼至您的X帳戶，請委派這些帳戶的Adobe Campaign寫入許可權。 若要這麼做，您必須：

1. 建立X帳戶並註冊開發人員帳戶。 [了解更多](#dev-account)
1. （選用）建立測試X帳戶以傳送校樣。 [了解更多](#tw-test-account)
1. 建立X應用程式（每個X帳戶一個應用程式）。 [了解更多](#create-an-app-on-twitter)
1. 為&#x200B;**[!UICONTROL Twitter]**&#x200B;建立新服務（每個X帳戶一個服務）。 [了解更多](#create-tw-service)
1. 將您的X帳戶與Campaign同步。 [了解更多](#synchro-tw-accounts)

## X開發人員帳戶 {#dev-account}

若要開始進行這項整合，您必須註冊[X開發人員帳戶](https://developer.twitter.com){target="_blank"}。

Campaign使用X API 1.1版。 若要使用它，您必須透過開發人員入口網站套用提升的存取權。 在此頁面](https://developer.twitter.com/en/portal/products/elevated){target="_blank"}中進一步瞭解X提升存取權[。

## 在X上建立應用程式 {#create-an-app-on-twitter}

核准您的「提升存取權」後，請建立X應用程式，讓Adobe Campaign能在您的X帳戶上建立貼文。 要執行此操作，請遵循下列步驟：

1. 登入您的X帳戶。
1. 連線至[X開發人員入口網站](https://developer.twitter.com/en/apps){target="_blank"}。
1. 選取&#x200B;**建立應用程式**。
1. 讓X助理引導您完成程式。
1. 若要允許Adobe Campaign在您的帳戶上建立貼文，請從應用程式的[使用者驗證設定]區段編輯至&#x200B;**應用程式許可權**。 選取&#x200B;**讀取、寫入和直接訊息**。

   ![](assets/tw-permissions.png)

1. 在&#x200B;**應用程式型別**&#x200B;區段中，選取&#x200B;**網頁應用程式、自動應用程式或機器人**。 您可以將&#x200B;**回撥URL**&#x200B;欄位保留空白，然後儲存您的設定。

   ![](assets/tw-app-type.png)

1. 回到您的應用程式儀表板，選取您的應用程式並瀏覽至&#x200B;**金鑰和代號**&#x200B;索引標籤。 在&#x200B;**存取Token和密碼**&#x200B;底下，如果未提及&#x200B;**讀取、寫入和直接訊息**&#x200B;許可權，您必須重新產生應用程式的權杖和密碼。 請注意，所有金鑰和權杖在建立後即必須儲存。 您需要他們來設定您的Campaign Twitter服務。

   ![](assets/tw-permissions-check.png)


>[!NOTE]
>
>每個X帳戶需要一個應用程式。 因此，您必須建立另一個測試應用程式，以將校樣傳送至您的測試帳戶。
>

## 在Campaign中建立Twitter服務 {#create-tw-service}

若要將您的Campaign執行個體與您的X帳戶連結，請建立&#x200B;**Twitter**&#x200B;服務並委派對Campaign的寫入許可權。

>[!CAUTION]
>
>為每個X帳戶建立一個&#x200B;**Twitter**&#x200B;服務。 因此，您必須建立另一個測試服務，以將校樣傳送至您的[測試帳戶](#tw-test-account)。
>
>每個&#x200B;**Twitter**&#x200B;服務也必須由Adobe在中間來源(MID)執行個體上建立。 請聯絡您的Adobe代表來設定您的環境。
>

若要輸入設定，您必須同時存取Adobe Campaign使用者端主控台和X應用程式許可權。

1. 在&#x200B;**Adobe Campaign**&#x200B;中，瀏覽至&#x200B;**[!UICONTROL Profiles and targets]**&#x200B;標籤，並選取&#x200B;**[!UICONTROL Services and Subscriptions]**&#x200B;連結
1. 建立新的服務。
1. 選取&#x200B;**[!UICONTROL Twitter]**&#x200B;型別。
1. 輸入服務的標籤和內部名稱。

   >[!CAUTION]
   >
   >服務的&#x200B;**[!UICONTROL Internal name]**&#x200B;名稱必須與您的X帳戶名稱完全相同。
   >

1. 依預設，追隨者會儲存在&#x200B;**[!UICONTROL Visitors]**&#x200B;資料夾中。 您可以從&#x200B;**[!UICONTROL Visitor folder]**&#x200B;欄位中選取其他位置。 [了解更多](../send/twitter.md#direct-tw-messages)

   ![](assets/tw-service-in-ac.png)

   >[!NOTE]
   >
   >**[!UICONTROL Synchronize subscriptions]**&#x200B;選項預設為啟用：此選項會自動復原您的X關注者清單，因此您可以[傳送直接訊息給他們](../send/twitter.md#direct-tw-messages)。 同步處理是由[專屬的技術工作流程](#synchro-tw-accounts)執行。

1. 從您的X應用程式中，複製&#x200B;**API金鑰**&#x200B;和&#x200B;**[API金鑰機密]**&#x200B;欄位的內容，並將其貼到您的行銷活動&#x200B;**Twitter**&#x200B;服務的&#x200B;**[!UICONTROL Consumer key]**&#x200B;和&#x200B;**[!UICONTROL Consumer secret]**&#x200B;欄位中。

1. 從您的X應用程式中，複製&#x200B;**存取權杖**&#x200B;和&#x200B;**存取權杖密碼**&#x200B;欄位的內容，並將其貼到您的行銷活動&#x200B;**Twitter**&#x200B;服務的&#x200B;**[!UICONTROL Access token]**&#x200B;和&#x200B;**[!UICONTROL Access token secret]**&#x200B;欄位中。

1. 在Campaign使用者端主控台中，按一下&#x200B;**[!UICONTROL Save]**。 您現在已委派Adobe Campaign的寫入許可權。

若要檢查您的設定，您可以：

* 編輯您剛建立的&#x200B;**Twitter**&#x200B;服務。
* 瀏覽&#x200B;**[!UICONTROL Twitter page]**標籤：應該會顯示您的Twitter帳戶。
  ![](assets/tw-page.png)

## 同步您的X帳戶 {#synchro-tw-accounts}

Campaign與X之間的同步作業是透過專屬的技術工作流程來管理。 這些工作流程儲存在&#x200B;**[!UICONTROL Administration > Production > Technical workflows > Managing social networks]**&#x200B;資料夾中。

預設會停止：當您開始使用&#x200B;**社交行銷**&#x200B;模組時，必須手動啟動這些專案。

**[!UICONTROL Synchronization of Twitter accounts]**&#x200B;技術工作流程會在Adobe Campaign中同步X帳戶。 此工作流程會復原X位追隨者的清單，因此您可以傳送直接訊息給他們。 [了解更多](../send/twitter.md#direct-tw-messages)

預設會每星期四早上7:30觸發此工作流程。 您可在實作此整合時隨時使用&#x200B;**[!UICONTROL Execute pending task(s) now]**&#x200B;選項啟動工作流程。  您也可以編輯排程器以變更工作流程觸發頻率。 在[本頁](../../automation/workflow/scheduler.md)中瞭解更多。

>[!CAUTION]
>
>若要復原X訂閱者清單，必須針對連結至帳戶的服務核取&#x200B;**[!UICONTROL Twitter account synchronization]**&#x200B;選項。 [了解更多](#create-tw-service)

跟隨者儲存在特定表格中：訪客表格。 若要顯示X追蹤者清單，請瀏覽至&#x200B;**[!UICONTROL Profiles and Targets > Visitors]**。

Adobe Campaign會針對每位追隨者儲存下列資訊：

* **[!UICONTROL Origin]**： Twitter
* **[!UICONTROL External ID]**：使用者識別碼
* **[!UICONTROL Username]**：使用者的帳戶名稱
* **[!UICONTROL Full name]**：使用者的名稱
* **[!UICONTROL Number of friends]**：關注者數
* **[!UICONTROL Checked]**：此欄位指出使用者是否擁有已驗證的Twitter帳戶

完成此設定後，您可以在X帳戶上建立貼文，並傳送直接訊息給追隨者。 [了解更多](../send/twitter.md)

## 在X上建立測試帳戶 {#tw-test-account}

除了X帳戶，請建立私人X帳戶，用來傳送[推文校樣](../send/twitter.md#send-tw-proofs)。 要執行此操作，請遵循下列步驟：

1. 建立新的X帳戶。
1. 存取帳戶&#x200B;**設定**。
1. 瀏覽至&#x200B;**隱私權與安全**&#x200B;和&#x200B;**對象與標籤**，並勾選&#x200B;**保護您的貼文**&#x200B;選項。 您的貼文和其他帳戶資訊只會顯示給關注您的人。

![](assets/do-not-localize/social_tw_test_page.png)

如上所述，設定您的X應用程式和Campaign服務以搭配此測試帳戶使用。
