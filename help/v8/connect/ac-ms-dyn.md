---
title: 使用 Campaign 及 Microsoft Dynamics
description: 了解如何使用Campaign和Microsoft Dynamics
feature: Microsoft CRM Integration
role: Admin, User
level: Beginner, Intermediate, Experienced
exl-id: 4f9e8f74-27dc-482c-a83c-25623b53560f
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '1366'
ht-degree: 3%

---

# 使用Campaign和Microsoft Dynamics 365{#crm-ms-dynamics}

在跨通道通訊時啟動您的CRM資料：了解如何從 **Microsoft Dynamics 365** 至Adobe Campaign，並將促銷活動績效資料（傳送、開啟、點按和退回）從Adobe Campaign分享回Microsoft Dynamics 365。

完成配置後，系統之間的資料同步將通過專用的工作流活動執行。 [了解更多資訊](crm-data-sync.md)。

>[!NOTE]
>
>支援的Microsoft Dynamics版本在Campaign中詳細說明 [相容性矩陣](../start/compatibility-matrix.md).

請依照下列步驟設定專用的外部帳戶，以匯入和匯出Microsoft Dynamics 365資料至Adobe Campaign。

對於每個系統，這些步驟需要由管理員執行。

>[!CAUTION]
> 本檔案中的步驟將引導您建立與指派權限和/或管理員存取權相關的整合/註冊。 您有責任在執行前確保這些步驟符合您的公司政策，並謹慎執行。

## 設定 Microsoft Dynamics 365 {#config-crm-microsoft}

連接Microsoft Dynamics 365以透過 **網頁API**，登入 [Microsoft Azure目錄](https://portal.azure.com) 使用 **全局管理員** 憑據，並按照以下步驟操作：

1. 獲取Dynamics 365應用程式（客戶端）ID。 [了解更多](#get-client-id-microsoft)
1. 產生Microsoft Dynamics憑證金鑰識別碼和金鑰ID。 [了解更多](#config-certificate-key-id)
1. 設定權限。 [了解更多](#config-permissions-microsoft)
1. 建立應用程式使用者。 [了解更多](#create-app-user-microsoft)
1. 為私密金鑰編碼。 [了解更多](#configure-acc-for-microsoftt)


### 獲取Dynamics 365客戶端ID {#get-client-id-microsoft}

若要取得應用程式（用戶端）ID，您必須在Azure Active Directory中註冊應用程式。

1. 瀏覽至 **Azure Active Directory >應用程式註冊**，然後選取 **新註冊**.
1. 輸入唯一名稱，以便識別例項，例如 **adobecampaign`<instance identifier>`**.

儲存後，Microsoft Azure目錄會指派一個唯一的 **應用程式（客戶端）ID** 至您的應用程式。 您稍後在Adobe Campaign中設定Dynamics 365時將需要此ID。

深入了解 [Microsoft Dynamics 365檔案](https://docs.microsoft.com/powerapps/developer/common-data-service/walkthrough-register-app-azure-active-directory){target=&quot;_blank&quot;}。

### 產生Microsoft Dynamics憑證金鑰識別碼和金鑰ID {#config-certificate-key-id}

若要取得 **憑證金鑰識別碼(customKeyIdentifier)** 和 **金鑰ID(keyId)**，您必須上傳憑證。 憑證可作為機密，以在請求代號時證明應用程式的身分。 也可稱為公開金鑰。

請遵循以下步驟：

1. 瀏覽至 **Azure Active Directory >應用程式註冊** 並選擇先前建立的應用程式。
1. 選擇 **憑證與密碼**.
1. 從 **憑證** 按一下 **上傳憑證**
1. 上傳您的公開憑證。
1. 瀏覽至 **資訊清單** 連結以取得 **憑證金鑰識別碼(customKeyIdentifier)** 和 **金鑰ID(keyId)**.

此 **憑證金鑰識別碼(customKeyIdentifier)** 和 **金鑰ID(keyId)** 需要在Campaign中使用憑證來設定您的Microsoft Dynamics 365 CRM外部帳戶 **[!UICONTROL CRM O-Auth type]**.

+++ 如何產生公開憑證

若要產生憑證，您可以使用openssl。

例如：

```
- openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout '<'private key name'>' -out '<'public certificate name'>
```

>[!NOTE]
>
>您可以在此處變更天數 `-days 365`，在程式碼範例中取得較長憑證有效期。

然後，您必須將憑證編碼為base64。 要執行此操作，可以使用Base64編碼器的幫助或使用命令行 `base64 -w0 private.key` Linux版。

+++

### 設定權限 {#config-permissions-microsoft}

**步驟1**:設定 **必要權限** 針對已建立的應用程式。

1. 導覽至 **Azure Active Directory >應用程式註冊** 並選擇先前建立的應用程式。
1. 按一下 **設定** 左上角。
1. 開啟 **必要權限**，按一下 **新增** 和 **選取API > Dynamics CRM Online**.
1. 按一下 **選擇**，啟用 **以組織使用者身分存取Dynamics 365** 核取方塊和按一下 **選擇**.
1. 然後，從您的應用程式中選取 **資訊清單** 在 **管理** 功能表。
1. 從 **資訊清單** 編輯器，設定 `allowPublicClient` 屬性來源 `null` to `true` 按一下 **儲存**.

**步驟2**:授予管理員同意

1. 導覽至 **Azure Active Directory >企業應用程式**.
1. 選取您要授予租用戶範圍管理員同意的應用程式。
1. 從左窗格菜單中，選擇 **權限** 在 **安全性**.
1. 按一下 **授予管理員同意**.

如需詳細資訊，請參閱 [Azure檔案](https://docs.microsoft.com/azure/active-directory/manage-apps/grant-admin-consent#grant-admin-consent-from-the-azure-portal).

### 建立應用程式使用者 {#create-app-user-microsoft}

>[!NOTE]
>
> 此步驟是選用的 **[!UICONTROL Password credentials]** 驗證。

應用程式使用者是上述註冊的應用程式將使用的使用者。 使用上述註冊的應用程式對Microsoft Dynamics所做的任何變更，都會透過此使用者完成。

**步驟1**:在azure active directory上建立非互動用戶

1. 按一下 **Azure Active Directory >用戶** 按一下 **新用戶**.
1. 請指定您要使用的正確名稱，使用者名稱應為電子郵件格式。
1. 選擇 **Dynamics 365管理員** 在 **目錄角色**.

**步驟2**:為已建立的用戶分配適當的許可證

1. 從 [Microsoft Azure](https://portal.azure.com)，按一下 **管理應用程式**.
1. 前往 **使用者>作用中使用者** 然後按一下新建立的使用者。
1. 按一下 **編輯產品授權** ，然後選取 **Dynamics 365客戶參與計畫**.
1. 按一下 **關閉**。

**步驟3**:在Dynamics CRM上建立應用程式使用者

1. 從 [Microsoft Azure](https://portal.azure.com)，導覽至 **設定>安全性>使用者**.
1. 按一下下拉式清單，選取 **應用程式使用者**，然後按一下 **新增**.
1. 使用與上述active directory上建立的用戶相同的用戶名。
1. 指派 **應用程式ID** for [您先前建立的應用程式](#get-client-id-microsoft).
1. 按一下 **管理角色** 並選擇 **系統管理員** 角色。

## 設定 Campaign {#configure-acc-for-microsoft}

### 建立連線{#new-ms-dyn-external-account}

首先，您必須建立Microsoft Dynamics 365外部帳戶。

1. 瀏覽 **[!UICONTROL Administration > Platform > External accounts]** 節點，並建立外部帳戶。
1. 選擇 **[!UICONTROL Microsoft Dynamics CRM]** 外部帳戶 **類型** 區段。
1. 在 **[!UICONTROL CRM O-Auth type]** 下拉式清單。

   ![](assets/ms-dyn-external-account.png)

   1. 若要設定Microsoft Dynamics CRM外部帳戶以連線至Adobe Campaign，請使用 **密碼憑據**，請提供下列詳細資料：

      * **伺服器**:Microsoft CRM伺服器的URL。 若要尋找您的Microsoft CRM伺服器URL，請存取您的Microsoft Dynamics CRM帳戶，然後按一下Dynamics 365並選取您的應用程式。 接著，您就可以在瀏覽器的位址列中找到您的伺服器URL，例如https://myserver.crm.dynamics.com/。
      * **帳戶**:用來登入Microsoft CRM的帳戶。
      * **密碼**:用來登入Microsoft CRM的帳戶。
      * **用戶端識別碼**:應用程式（用戶端）ID，可在「更新您的代碼類別，用戶端ID」欄位中的Microsoft Azure管理入口網站中找到。
      * **CRM版本**:選擇Dynamics CRM 365 CRM版本。
   1. 若要設定Microsoft Dynamics CRM外部帳戶以使用 **憑證**，請提供下列詳細資料：

      * **伺服器**:Microsoft CRM伺服器的URL。 若要尋找您的Microsoft CRM伺服器URL，請存取您的Microsoft Dynamics CRM帳戶，然後按一下Dynamics 365並選取您的應用程式。 接著，您就可以在瀏覽器的位址列中找到您的伺服器URL，例如https://myserver.crm.dynamics.com/。
      * **私密金鑰**:複製/貼上私密金鑰（編碼base64），如 [本節](#config-certificate-key-id).
      * **索引鍵ID**:中可用的金鑰 **資訊清單** 頁簽，如 [本節](#config-certificate-key-id).
      * **自訂金鑰識別碼**:可用於 **資訊清單** 頁簽，如 [本節](#config-certificate-key-id).
      * **用戶端識別碼**:可從Microsoft Azure管理入口網站找到應用程式（用戶端）ID，如 [本節](#get-client-id-microsoft).
      * **CRM版本**:選擇Dynamics CRM 365 CRM版本。


1. 選取 **啟用** 選項，在Campaign中啟用帳戶。

>[!NOTE]
>
>若要核准設定，請註銷並重新登入Adobe Campaign主控台。

### 選擇要同步的表{#ms-dyn-create-tables}

您現在可以配置要同步的表。

1. 按一下 **[!UICONTROL Microsoft CRM configuration wizard...]**.
1. 選擇要同步的表並啟動進程。
1. 檢查在Adobe Campaign中產生的結構 **[!UICONTROL Administration > Configuration > Data schemas]** 節點。

>[!NOTE]
>
>請務必將兩個URL新增至允許清單：伺服器URL和 `login.microsoftonline.com`. 若要執行此作業，請連絡您的Adobe代表。

## 同步枚舉{#sfdc-enum-sync}

建立架構後，您可以自動將列舉從Dynamics 365同步至Adobe Campaign。

1. 從  **[!UICONTROL Synchronizing enumerations...]** 連結。
1. 選取符合Dynamics 365分項的Adobe Campaign分項清單。
您可以將Adobe Campaign分項清單的所有值取代為CRM的值：要執行此操作，請選取 **[!UICONTROL Yes]** 在 **[!UICONTROL Replace]** 欄。
1. 按一下 **[!UICONTROL Next]** 然後 **[!UICONTROL Start]** 開始導入枚舉。
1. 瀏覽 **[!UICONTROL Administration > Platform > Enumerations]** 要檢查導入值的節點。

Adobe Campaign和Microsoft Dynamics 365現已連接。 您可以在兩個系統之間設定資料同步。

若要同步Adobe Campaign資料與Microsoft CRM之間的資料，請建立工作流程，並使用 **[!UICONTROL CRM connector]** 活動。

深入了解資料同步 [在本頁](crm-data-sync.md).

### 支援的欄位資料類型 {#ms-dyn-supported-types}

下列為Microsoft Dynamics 365支援/不支援的屬性類型：


| 屬性類型 | 支援 |
| --------------------------------------------------------------------------------- | --------- |
| 基本類型：布林值，日期時間，小數，浮點數，雙精度，整數， bigint，字串 | 是 |
| 貨幣（雙倍） | 是 |
| memo, entityname , primarykey, uniqueidentifier（作為字串） | 是 |
| 狀態、選擇清單（我們將可能的值儲存在枚舉中）、狀態（字串） | 是 |
| 擁有者（作為字串） | 是 |
| 查閱（僅單一實體參考查閱） | 是 |
| 客戶 | 否 |
| 關於 | 否 |
| PartyList | 否 |
| ManagedProperty | 否 |
