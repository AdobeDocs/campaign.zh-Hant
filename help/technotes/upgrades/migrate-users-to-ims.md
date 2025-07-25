---
title: 將Campaign運運算元移轉至Adobe Identity Management系統(IMS)
description: 瞭解如何將Campaign運運算元移轉至Adobe Identity Management系統(IMS)
exl-id: 58c130d8-8ba8-42ce-9ab4-a697125d3f85
source-git-commit: e0dbeb7402a46f76a26c28dd226bc069d52f2609
workflow-type: tm+mt
source-wordcount: '1343'
ht-degree: 1%

---

# 將Campaign運運算元移轉至Adobe Identity Management系統(IMS) {#migrate-users-to-ims}

自Campaign v8.6開始，改善對Campaign v8的驗證流程。 所有操作員都將使用[Adobe Identity Management System (IMS)](https://helpx.adobe.com/tw/enterprise/using/identity.html){target="_blank"} **only**&#x200B;連線至Campaign。 不再允許以使用者/密碼（亦稱為原生驗證）連線。 Adobe建議您在Campaign v8.5.2中執行此移轉，以便能夠順利移轉至Campaign v8.6。

身為Campaign Classic v7 Managed Services客戶，如果您要移轉至Campaign v8，則此程式也適用於您。

本文詳細說明將技術運運算元移轉至Adobe Developer主控台上的技術帳戶所需的步驟。

## 哪些部分有所變更？{#move-to-ims-changes}

透過Campaign v8，所有一般使用者應該已透過Adobe Campaign Identity Management System (IMS)，使用其Adobe ID連線至Adobe使用者端主控台。 但是，使用某些舊版設定時，使用者/密碼連線仍然可用。 **從Campaign v8.6開始不再允許此專案。**

此外，為了強化安全性和驗證程式，Adobe Campaign使用者端應用程式現在直接使用IMS技術帳戶權杖呼叫Campaign API。 技術運運算元的移轉作業在專用文章中有詳細說明，可在[此頁面](ims-migration.md)取得。

此變更適用於Campaign v8.5.2開始，且為Campaign v8.6開始的&#x200B;**強制性**。

## 您有受到影響嗎？{#migrate-ims-impacts}

如果貴組織中的操作員使用其登入/密碼（亦即）連線至Campaign使用者端主控台， 原生驗證)，您會受到影響，且必須將這些運運算元移轉至Adobe IMS，如下所述。

移轉至[Adobe Identity Management System (IMS)](https://helpx.adobe.com/tw/enterprise/using/identity.html){target="_blank"}是安全性必要條件，可讓您的環境安全且標準化，因為大部分其他Adobe Experience Cloud解決方案和應用程式已位於IMS上。

## 如何移轉？{#ims-migration-procedure}

### 先決條件{#ims-migration-prerequisites}

在開始移轉程式之前，您必須聯絡您的Adobe代表（轉換經理），以便Adobe技術團隊能夠將您現有的操作員群組和已命名的許可權移轉到Adobe Identity Management System (IMS)。

### 主要步驟 {#ims-migration-steps}

以下列出此移轉的關鍵步驟：

1. Adobe會將您的環境升級至Campaign v8.5.2。
1. 升級後，您仍然可以透過兩種方法建立新使用者，以原生使用者身分或透過IMS。
1. 您的內部Campaign管理員必須向Campaign使用者端主控台上的所有原生使用者新增唯一電子郵件，並在完成後向您的Adobe轉變管理員確認。 此步驟在[此區段](#ims-migration-id)中有詳細說明。
1. 請與Adobe合作，為Adobe確定一個日期，讓非技術使用者（操作員）和產品設定檔執行自動移轉。 此步驟需要一小時的時段，您的任何執行個體都沒有停機時間。
1. 您的內部Campaign管理員會驗證這些變更，並提供簽核服務。 移轉後，您再也不能建立任何以他的登入和密碼進行驗證的進一步運運算元。

您現在可以將技術操作員移轉至Adobe Developer Console，如[此技術檔案](ims-migration.md)所詳述。 如果您使用Campaign API，則此步驟為必要步驟。

此移轉一旦完成，請向您的Adobe轉換管理員確認： Adobe然後將移轉標示為完成，並封鎖建立新的原生使用者和原生使用者登入。 接著您的環境就會受到保護並標準化。

## 常見問題集 {#ims-migration-faq}

### 何時可以開始移轉？ {#ims-migration-start}

移轉至[Adobe Identity Management System (IMS)](https://helpx.adobe.com/tw/enterprise/using/identity.html){target="_blank"}的必要條件是將您的環境升級至Campaign v8.5.2。

升級到Campaign v8.5.2後，您可以在中繼環境中開始IMS移轉，並據此規劃生產環境。

### 組建版本升級至Campaign v8.5.2後會發生什麼事？ {#ims-migration-after-upgrade}

環境升級至Campaign v8.5.2後，您就可以開始轉變至[Adobe Identity Management System (IMS)](https://helpx.adobe.com/tw/enterprise/using/identity.html){target="_blank"}。

在IMS移轉完成之前，仍允許建立新的原生使用者。

### 移轉何時完成？ {#ims-migration-end}

使用者移轉及技術使用者移轉至Adobe Identity Management System (IMS)後，請務必聯絡Adobe轉換經理，以便Adobe將移轉標示為完成、阻止從使用者端主控台建立使用者，並停用原生使用者登入。


### 如何在移轉後建立使用者？ {#ims-migration-native}

完整IMS移轉完成後，Adobe將套用會封鎖新原生使用者建立的限制。 在IMS移轉完成之前，不會套用這些限制。

對於新客戶 — 不允許從頭開始建立新的原生使用者。

身為Campaign管理員，您可以透過Adobe Admin Console和Campaign使用者端主控台將許可權授與組織的使用者。 使用者使用其Adobe ID登入Adobe Campaign。 深入瞭解[此檔案](../../v8/start/gs-permissions.md)。

### 如何為目前原生使用者新增電子郵件？ {#ims-migration-id}

身為Campaign管理員，您必須從使用者端主控台新增電子郵件ID至所有原生使用者。 若要執行此作業，請依照下列步驟操作：

1. 連線到使用者端主控台，並瀏覽至&#x200B;**管理>存取管理>操作員**。
1. 在運運算元清單中選取要更新的運運算元。
1. 在操作員表單的&#x200B;**聯絡點**&#x200B;區段中，輸入操作員的電子郵件。
1. 儲存您的變更。

身為工作流程主管或Campaign管理員，您也可以使用工作流程對操作員執行大量更新。

+++使用工作流程更新運運算元的關鍵步驟

若要對原生運運算元執行大量更新，請遵循下列步驟：

1. 建立工作流程，將您連線至具有原生驗證模式Campaign的所有運運算元擷取到CSV檔案。 使用&#x200B;**查詢**&#x200B;活動和&#x200B;**資料擷取（檔案）**&#x200B;活動來建立CSV檔案。 對於每個運運算元，根據它們的設定檔資料，您可以匯出下列資料行： `Name, Label`。

   在[此頁面](../../automation/workflow/query.md)中進一步瞭解&#x200B;**查詢**&#x200B;活動

   深入瞭解[此頁面](../../automation/workflow/extraction-file.md)中的&#x200B;**資料擷取（檔案）**&#x200B;活動

1. 以包含您操作員電子郵件的新欄更新CSV檔案。

1. 建立工作流程以匯入更新的資料，在工作流程中有&#x200B;**資料載入（檔案）**&#x200B;活動和&#x200B;**更新資料**&#x200B;活動。

   ![](assets/update-operators-wf.png){width="70%"}

1. 編輯&#x200B;**資料載入（檔案）**&#x200B;活動，並定義設定以載入更新的CSV檔案，如以下範例所示。

   ![](assets/data-loading-activity.png){width="70%"}

   深入瞭解[此頁面](../../automation/workflow/data-loading-file.md)中的&#x200B;**資料載入（檔案）**&#x200B;活動

1. 編輯&#x200B;**更新資料**&#x200B;活動，並根據下列範例定義設定。 請注意，**已更新的維度**&#x200B;已變更為`Operators (xtk)`。

   ![](assets/update-data-activity.png){width="70%"}

   在[此頁面](../../automation/workflow/update-data.md)中進一步瞭解&#x200B;**更新資料**&#x200B;活動

1. 執行工作流程並檢查結果。 電子郵件地址已新增到操作員的設定檔。

   ![](assets/updated-operator.png){width="70%"}

+++


### 如何透過IMS登入Campaign？ {#ims-migration-log}

在[本節](../../v8/start/connect.md)中瞭解如何使用您的Adobe ID連線至Campaign。

### 此移轉期間是否會有停機時間？ {#ims-migration-downtime}

為了完成移轉（移轉使用者和產品設定檔），Adobe需要一小時的時段，您的任何執行個體（工作流程等）都不會出現停機時間。

在這段時間內，所有Campaign使用者都必須登出，並在完成移轉至IMS後使用Adobe ID登回。

### 在IMS使用者移轉期間登入的使用者會發生什麼事？ {#ims-migration-log-off}

Adobe強烈建議所有使用者在移轉期間登出。

### 我組織中的使用者已在使用IMS，我仍需要執行IMS移轉嗎？{#ims-migration-needed}

此移轉包括兩個方面：一般使用者移轉和技術使用者移轉（用於自訂程式碼的API）。

如果您的所有使用者（Campaign運運算元）都在IMS上，則不需要執行此移轉。 不過，您仍需要移轉可能已用於自訂程式碼中的技術使用者。 在[本頁](ims-migration.md)中瞭解更多。

移轉一旦完成，您必須聯絡Adobe轉換經理，Adobe才能完成移轉。

### 如何檢視您的操作員的驗證型別？

瞭解如何在Campaign中檢視您的操作員驗證型別：

1. 從&#x200B;**總管**，存取&#x200B;**管理** `>` **存取管理** `>` **操作員**。

1. 以滑鼠右鍵按一下標題列，並選取&#x200B;**設定清單**&#x200B;功能表。

   ![](assets/ims_2.png)

1. 將&#x200B;**已停用的帳戶**&#x200B;和&#x200B;**驗證型別**&#x200B;新增為&#x200B;**輸出資料行**。

   ![](assets/ims_1.png)

您現在可以看到&#x200B;**操作員**&#x200B;及其&#x200B;**驗證型別**&#x200B;的清單。

![](assets/ims_3.png)

## 有用的連結 {#ims-useful-links}

* [將技術使用者移轉至Adobe Developer主控台](ims-migration.md)
* [如何連線至Adobe Campaign v8](../../v8/start/connect.md)
* [Adobe Campaign v8中的存取和許可權](../../v8/start/gs-permissions.md)
* [Adobe Campaign v8發行說明](../../v8/start/release-notes.md)
* [什麼是Adobe Identity Management System (IMS)](https://helpx.adobe.com/tw/enterprise/using/identity.html){target="_blank"}
