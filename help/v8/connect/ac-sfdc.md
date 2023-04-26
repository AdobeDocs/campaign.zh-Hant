---
title: 使用 Campaign 及 SFDC
description: 了解如何與Campaign和Salesforce.com搭配使用
feature: Salesforce Integration
role: Admin, User
level: Beginner, Intermediate, Experienced
exl-id: 1e20f3b9-d1fc-411c-810b-6271360286f9
source-git-commit: 3c7455f348468a8f00fb853a3269a1d63b81e7b8
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 3%

---

# 使用 Campaign 及 SFDC{#crm-sfdc}

了解如何設定Campaign CRM連接器，將Campaign v8連線至 **Salesforce.com**.

完成配置後，系統之間的資料同步將通過專用的工作流活動執行。 [了解更多資訊](crm-data-sync.md)。

>[!NOTE]
>
>Campaign中詳細說明了支援的SFDC版本 [相容性矩陣](../start/compatibility-matrix.md).

請依照下列步驟設定專用的外部帳戶，以匯入和匯出Salesforce資料至Adobe Campaign。

## 建立連線{#new-sfdc-external-account}

首先，您必須建立Salesforce外部帳戶。

1. 瀏覽 **[!UICONTROL Administration > Platform > External accounts]** 節點，並建立外部帳戶。
1. 選擇 **[!UICONTROL Salesforce.com]** 外部帳戶 **類型** 區段。
1. 輸入啟用連接的設定。

   ![](assets/sfdc-external-account.png)

   若要設定Salesforce CRM外部帳戶以搭配Adobe Campaign運作，您需要提供下列詳細資訊：

   * 在 **[!UICONTROL Account]** 欄位。
   * 輸入您的Salesforce密碼。
   * 您可以忽略 **[!UICONTROL Client identifier]** 欄位。
   * 複製/貼上您的Salesforce **[!UICONTROL Security token]**
   * 選取 **[!UICONTROL API version]**. Campaign中列出支援的SFDC API版本 [相容性矩陣](../start/compatibility-matrix.md).

1. 選取 **啟用** 選項，在Campaign中啟用帳戶。

>[!NOTE]
>
>若要核准設定，您必須註銷並返回Adobe Campaign主控台。

## 選擇要同步的表{#sfdc-create-tables}

您現在可以配置要同步的表。

1. 按一下 **[!UICONTROL Salesforce CRM configuration wizard...]**.
1. 選擇要同步的表並啟動進程。
1. 檢查在Adobe Campaign中產生的結構 **[!UICONTROL Administration > Configuration > Data schemas]** 節點。

   範例 **Salesforce** 在Campaign中匯入的結構：

   ![](assets/sfdc-schemas.png)

## 同步枚舉{#sfdc-enum-sync}

建立結構後，您就可以自動將列舉從Salesforce同步至Adobe Campaign。

1. 從  **[!UICONTROL Synchronizing enumerations...]** 連結。
1. 選取符合Salesforce分項的Adobe Campaign分項清單。
您可以將Adobe Campaign分項清單的所有值取代為CRM的值：要執行此操作，請選取 **[!UICONTROL Yes]** 在 **[!UICONTROL Replace]** 欄。

   ![](assets/sfdc-enum.png)

1. 按一下 **[!UICONTROL Next]** 然後 **[!UICONTROL Start]** 開始導入枚舉。

1. 瀏覽 **[!UICONTROL Administration > Platform > Enumerations]** 要檢查導入值的節點。 進一步了解 [本頁](../config/ui-settings.md#enumerations).

Adobe Campaign和Salesforce.com現已連接。 您可以在兩個系統之間設定資料同步。

若要同步Adobe Campaign資料和SFDC之間的資料，請建立工作流程，並使用 **[!UICONTROL CRM connector]** 活動。

深入了解資料同步 [在本頁](crm-data-sync.md).
