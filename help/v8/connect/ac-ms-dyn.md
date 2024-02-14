---
title: 使用 Campaign 及 Microsoft Dynamics
description: 瞭解如何使用Campaign和Microsoft Dynamics
feature: Microsoft CRM Integration
role: Admin, User
level: Beginner, Intermediate
exl-id: 4f9e8f74-27dc-482c-a83c-25623b53560f
source-git-commit: 09db0cc1a14bffefe8d1b8d0d5a06d5b6517a5bb
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 2%

---

# 合作使用Campaign與Microsoft Dynamics 365{#crm-ms-dynamics}

在跨頻道通訊上啟用您的CRM資料：瞭解如何傳遞聯絡人 **Microsoft Dynamics 365** 到Adobe Campaign，並從Adobe Campaign將行銷活動績效資料（傳送、開啟、點按和跳出）分享回Microsoft Dynamics 365。

完成設定後，會透過專用工作流程活動在系統之間執行資料同步。 [了解更多](crm-data-sync.md)。

>[!NOTE]
>
>受支援的Microsoft Dynamics版本在Campaign中有詳細說明 [相容性矩陣](../start/compatibility-matrix.md).

請依照下列步驟設定專用的外部帳戶，將Microsoft Dynamics 365資料匯入及匯出至Adobe Campaign。

對於每個系統，這些步驟需要由管理員執行。

>[!CAUTION]
> 本檔案中的步驟將指導您建立涉及指派許可權和/或管理員存取權的整合/註冊。 您有責任在執行前確保這些步驟符合貴公司的政策，並仔細執行。

## 設定 Microsoft Dynamics 365 {#config-crm-microsoft}

若要連線Microsoft Adobe Campaign Dynamics 365以透過 **Web API**，登入 [Microsoft Azure目錄](https://portal.azure.com) 使用 **全域管理員** 認證，然後遵循下列步驟：

1. 取得您的Dynamics 365應用程式（使用者端） ID。 [了解更多](#get-client-id-microsoft)
1. 產生Microsoft Dynamics憑證金鑰識別碼和金鑰ID。 [了解更多](#config-certificate-key-id)
1. 設定許可權。 [了解更多](#config-permissions-microsoft)
1. 建立應用程式使用者。 [了解更多](#create-app-user-microsoft)
1. 將私密金鑰編碼。 [了解更多](#configure-acc-for-microsoftt)


### 取得Dynamics 365使用者端ID {#get-client-id-microsoft}

若要取得應用程式（使用者端）識別碼，您必須在Azure Active Directory中註冊應用程式。

1. 瀏覽至 **Azure Active Directory >應用程式註冊**，並選取 **新註冊**.
1. 輸入有助於識別執行個體的唯一名稱，例如 **adobecampaign`<instance identifier>`**.

儲存後，Microsoft Azure目錄會指派唯一的 **應用程式（使用者端） ID** 至您的應用程式。 稍後在Adobe Campaign中設定Dynamics 365時，您將需要此ID。

進一步瞭解 [Microsoft Dynamics 365檔案](https://docs.microsoft.com/powerapps/developer/common-data-service/walkthrough-register-app-azure-active-directory){target="_blank"}.

### 產生Microsoft Dynamics憑證金鑰識別碼和金鑰ID {#config-certificate-key-id}

若要取得 **憑證金鑰識別碼(customKeyIdentifier)** 和 **金鑰ID (keyId)**，您必須上傳憑證。 在請求Token時，憑證可用作秘密以證明應用程式的身分。 也可以稱為公開金鑰。

請遵循以下步驟：

1. 瀏覽至 **Azure Active Directory >應用程式註冊** 並選取先前建立的應用程式。
1. 選擇於 **憑證和密碼**.
1. 從 **憑證** 標籤，按一下 **上傳憑證**
1. 上傳您的公開憑證。
1. 瀏覽至 **資訊清單** 連結以取得 **憑證金鑰識別碼(customKeyIdentifier)** 和 **金鑰ID (keyId)**.

此 **憑證金鑰識別碼(customKeyIdentifier)** 和 **金鑰ID (keyId)** 需要在Campaign中使用憑證設定您的Microsoft Dynamics 365 CRM外部帳戶 **[!UICONTROL CRM O-Auth type]**.

+++ 如何產生公開憑證

若要產生憑證，您可以使用openssl。

例如：

```
- openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout '<'private key name'>' -out '<'public certificate name'>
```

>[!NOTE]
>
>您可以在這裡變更天數 `-days 365`，在程式碼範例中取得較長的憑證有效期。

接著，您必須以base64編碼憑證。 要執行此操作，您可以使用Base64編碼器的說明或使用命令列 `base64 -w0 private.key` 適用於Linux。

+++

### 設定許可權 {#config-permissions-microsoft}

**步驟1**：設定 **必要許可權** 針對已建立的應用程式。

1. 瀏覽至 **Azure Active Directory >應用程式註冊** 並選取先前建立的應用程式。
1. 按一下 **設定** 左上角。
1. 開啟 **必要許可權**，按一下 **新增** 和 **選取API > Dynamics CRM Online**.
1. 按一下 **選取**，啟用 **以組織使用者身分存取Dynamics 365** 核取方塊並按一下 **選取**.
1. 然後，從應用程式中選取 **資訊清單** 在 **管理** 功能表。
1. 從 **資訊清單** 編輯者，設定 `allowPublicClient` 屬性來源 `null` 至 `true` 並按一下 **儲存**.

**步驟2**：授予管理員同意

1. 瀏覽至 **Azure Active Directory >企業應用程式**.
1. 選取您要授與租使用者範圍管理同意的應用程式。
1. 從左窗格功能表中選取 **許可權** 在 **安全性**.
1. 按一下 **授予管理員同意**.

如需詳細資訊，請參閱 [Azure檔案](https://docs.microsoft.com/azure/active-directory/manage-apps/grant-admin-consent#grant-admin-consent-from-the-azure-portal).

### 建立應用程式使用者 {#create-app-user-microsoft}

>[!NOTE]
>
> 此步驟是選填，適用於 **[!UICONTROL Password credentials]** 驗證。

應用程式使用者是上述註冊的應用程式將使用的使用者。 使用上述註冊的應用程式對Microsoft Dynamics所做的任何變更，都將透過此使用者完成。

**步驟1**：在azure active directory上建立非互動式使用者

1. 按一下 **Azure Active Directory >使用者** 並按一下 **新使用者**.
1. 提供您想要使用的適當名稱，且使用者名稱應為電子郵件格式。
1. 選擇 **Dynamics 365系統管理員** 在 **目錄角色**.

**步驟2**：將適當的授權指派給已建立的使用者

1. 從 [Microsoft Azure](https://portal.azure.com)，按一下 **管理應用程式**.
1. 前往 **使用者>作用中的使用者** 並按一下新建立的使用者。
1. 按一下 **編輯產品授權** 並選取 **Dynamics 365客戶參與計畫**.
1. 按一下 **關閉**。

**步驟3**：在Dynamics CRM上建立應用程式使用者

1. 從 [Microsoft Azure](https://portal.azure.com)，導覽至 **設定>安全性>使用者**.
1. 按一下下拉式清單，選取 **應用程式使用者**，然後按一下 **新增**.
1. 使用與上述在Active Directory上建立的使用者相同的使用者名稱。
1. 指派 **應用程式ID** 的 [您先前建立的應用程式](#get-client-id-microsoft).
1. 按一下 **管理角色** 並選擇 **系統管理員** 角色至使用者。

## 設定Campaign {#configure-acc-for-microsoft}

### 建立連線{#new-ms-dyn-external-account}

首先，您必須建立Microsoft Dynamics 365外部帳戶。

1. 瀏覽 **[!UICONTROL Administration > Platform > External accounts]** 節點，並建立外部帳戶。
1. 選取 **[!UICONTROL Microsoft Dynamics CRM]** 中的外部帳戶 **型別** 區段。
1. 選取中的驗證方法 **[!UICONTROL CRM O-Auth type]** 下拉式清單。

   ![](assets/ms-dyn-external-account.png)

   1. 若要設定Microsoft Dynamics CRM外部帳戶以與Adobe Campaign連線，請 **密碼認證**，提供下列詳細資訊：

      * **伺服器**： Microsoft CRM伺服器的URL。 若要尋找您的Microsoft CRM伺服器URL，請存取您的Microsoft Dynamics CRM帳戶，然後按一下Dynamics 365並選取您的應用程式。 接著，您可以在瀏覽器的位址列中找到您的伺服器URL，例如https://myserver.crm.dynamics.com/。
      * **帳戶**：用來登入Microsoft CRM的帳戶。
      * **密碼**：用來登入Microsoft CRM的帳戶。
      * **使用者端識別碼**：應用程式（使用者端）ID可以從「更新程式碼類別，使用者端ID」欄位中的Microsoft Azure管理入口網站找到。
      * **CRM版本**：選擇Dynamics CRM 365 CRM版本。

   1. 若要設定Microsoft Adobe Campaign Dynamics CRM外部帳戶以使用 **憑證**，提供下列詳細資訊：

      * **伺服器**： Microsoft CRM伺服器的URL。 若要尋找您的Microsoft CRM伺服器URL，請存取您的Microsoft Dynamics CRM帳戶，然後按一下Dynamics 365並選取您的應用程式。 接著，您可以在瀏覽器的位址列中找到您的伺服器URL，例如https://myserver.crm.dynamics.com/。
      * **私密金鑰**：複製/貼上私密金鑰（編碼為base64），如中所述 [本節](#config-certificate-key-id).
      * **金鑰ID**：中可用的金鑰 **資訊清單** 標籤中，如中所述 [本節](#config-certificate-key-id).
      * **自訂金鑰識別碼**：中可用的識別碼 **資訊清單** 標籤中，如中所述 [本節](#config-certificate-key-id).
      * **使用者端識別碼**：可從Microsoft Azure管理入口網站找到的應用程式（使用者端） ID，如中所述 [本節](#get-client-id-microsoft).
      * **CRM版本**：選擇Dynamics CRM 365 CRM版本。

1. 選取 **啟用** 在Campaign中啟用帳戶的選項。

>[!NOTE]
>
>若要核准此設定，請先登出再重新登入Adobe Campaign使用者端主控台。

### 選取要同步的資料表{#ms-dyn-create-tables}

您現在可以設定要同步處理的表格。

1. 按一下 **[!UICONTROL Microsoft CRM configuration wizard...]**.
1. 選取要同步處理的資料表並啟動程式。
1. 檢查中Adobe Campaign產生的結構描述 **[!UICONTROL Administration > Configuration > Data schemas]** 節點。

>[!NOTE]
>
>請務必將兩個URL新增至允許清單：伺服器URL和 `login.microsoftonline.com`. 若要執行此動作，請聯絡您的Adobe代表。

## 同步分項清單{#sfdc-enum-sync}

建立結構描述後，您就可以自動將列舉從Dynamics 365同步至Adobe Campaign。

1. 從以下位置開啟助理：  **[!UICONTROL Synchronizing enumerations...]** 連結。
1. 選取符合Dynamics 365列舉的Adobe Campaign列舉。
您可以將Adobe Campaign分項清單的所有值取代為CRM的值：若要這麼做，請選取 **[!UICONTROL Yes]** 在 **[!UICONTROL Replace]** 欄。
1. 按一下 **[!UICONTROL Next]** 然後 **[!UICONTROL Start]** 以開始匯入分項清單。
1. 瀏覽 **[!UICONTROL Administration > Platform > Enumerations]** 節點，以檢查匯入的值。

Adobe Campaign和Microsoft Dynamics 365現已連線。 您可以設定兩個系統之間的資料同步。

若要在Adobe Campaign資料和Microsoft CRM之間同步資料，請建立工作流程並使用 **[!UICONTROL CRM connector]** 活動。

進一步瞭解資料同步 [在此頁面中](crm-data-sync.md).

### 支援的欄位資料型別 {#ms-dyn-supported-types}

對於Microsoft Dynamics 365，支援/不支援的屬性型別列於下方：


| 屬性型別 | 支援 |
| --------------------------------------------------------------------------------- | --------- |
| 基本型別：布林值、日期時間、小數、浮點數、雙精度、整數、bigint 、字串 | 是 |
| 金錢（雙倍） | 是 |
| memo， entityname， primarykey， uniqueidentifier （字串） | 是 |
| 狀態、挑選清單（我們會將可能的值儲存在列舉中）、狀態（字串） | 是 |
| 所有者（字串） | 是 |
| 查詢（僅限單一實體參考查詢） | 是 |
| 客戶 | 否 |
| 相關 | 否 |
| PartyList | 否 |
| ManagedProperty | 否 |
