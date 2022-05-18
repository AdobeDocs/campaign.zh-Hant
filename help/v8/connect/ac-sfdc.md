---
title: 使用 Campaign 及 SFDC
description: 瞭解如何使用Campaign和Salesforce.com
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 1e20f3b9-d1fc-411c-810b-6271360286f9
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 3%

---

# 使用 Campaign 及 SFDC{#crm-sfdc}

瞭解如何配置Campaign CRM連接器以將Campaign v8連接到 **Salesforce.com**。

一旦完成配置，則通過專用工作流活動在系統之間執行資料同步。 [了解更多資訊](crm-data-sync.md)。

>[!NOTE]
>
>市場活動中詳細介紹了支援的SFDC版本 [相容性矩陣](../start/compatibility-matrix.md)。


按照以下步驟配置專用外部帳戶以將Salesforce資料導入和導出到Adobe Campaign。

## 建立連接{#new-sfdc-external-account}

首先，必須建立Salesforce外部帳戶。

1. 瀏覽 **[!UICONTROL Administration > Platform > External accounts]** 活動瀏覽器的節點，並建立外部帳戶。
1. 選擇 **[!UICONTROL Salesforce.com]** 外部帳戶 **類型** 的子菜單。
1. 輸入設定以啟用連接。

   ![](assets/sfdc-external-account.png)

   要配置Salesforce CRM外部帳戶以與Adobe Campaign協作，您需要提供以下詳細資訊：

   * 在 **[!UICONTROL Account]** 的子菜單。
   * 輸入Salesforce密碼。
   * 您可以忽略 **[!UICONTROL Client identifier]** 的子菜單。
   * 複製/貼上您的Salesforce **[!UICONTROL Security token]**
   * 選擇 **[!UICONTROL API version]**。 市場活動中列出了支援的SFDC API版本 [相容性矩陣](../start/compatibility-matrix.md)。

1. 選擇 **啟用** 選項以激活市場活動中的帳戶。

>[!NOTE]
>
>要批准該設定，您需要註銷並重新登錄到Adobe Campaign控制台。

## 選擇要同步的表{#sfdc-create-tables}

現在可以配置表以進行同步。

1. 按一下 **[!UICONTROL Salesforce CRM configuration wizard...]**。
1. 選擇要同步並啟動進程的表。
1. 檢查在中的Adobe Campaign中生成的架構 **[!UICONTROL Administration > Configuration > Data schemas]** 的下界。

   示例 **Salesforce** 市場活動中導入的架構：

   ![](assets/sfdc-schemas.png)

## 同步枚舉{#sfdc-enum-sync}

建立架構後，可以自動將枚舉從Salesforce同步到Adobe Campaign。

1. 從  **[!UICONTROL Synchronizing enumerations...]** 的子菜單。
1. 選擇與Salesforce枚舉匹配的Adobe Campaign枚舉。
可以將Adobe Campaign枚舉的所有值替換為CRM的值：要執行此操作，請選擇 **[!UICONTROL Yes]** 的 **[!UICONTROL Replace]** 的雙曲餘切值。

   ![](assets/sfdc-enum.png)

1. 按一下 **[!UICONTROL Next]** 然後 **[!UICONTROL Start]** 開始導入枚舉。

1. 瀏覽 **[!UICONTROL Administration > Platform > Enumerations]** 節點以檢查導入的值。


Adobe Campaign和Salesforce.com現已連接。 可以設定兩個系統之間的資料同步。

要在Adobe Campaign資料和SFDC之間同步資料，請建立工作流並使用 **[!UICONTROL CRM connector]** 的子菜單。

瞭解有關資料同步的詳細資訊 [此頁](crm-data-sync.md)。
