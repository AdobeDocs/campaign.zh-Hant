---
title: 使用 Campaign 及 SFDC
description: 瞭解如何使用Campaign和Salesforce.com
feature: Salesforce Integration
role: Admin, User
level: Beginner, Intermediate
exl-id: 1e20f3b9-d1fc-411c-810b-6271360286f9
TQID: 'https://experienceleague.adobe.com/N50ecfMFC641fveGfyxx4W9XvZgWPgddrdpj9KrCHBY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: f09afca2-2160-4624-bedb-639c4f4c236f
    internal-label: Salesforce integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: df8d8e17c486122e23a6db0e44263f9f9632a204
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 2%
---
# 使用 Campaign 及 SFDC{#crm-sfdc}

瞭解如何設定Campaign CRM聯結器，將Campaign v8連線至&#x200B;**Salesforce.com**。

完成設定後，會透過專用工作流程活動在系統之間執行資料同步。 [了解更多資訊](crm-data-sync.md)。

>[!NOTE]
>
>支援的SFDC版本在Campaign [相容性矩陣](../start/compatibility-matrix.md)中詳細說明。

請依照下列步驟，設定專用的外部帳戶，將Salesforce資料匯入並匯出至Adobe Campaign。

## 建立連線{#new-sfdc-external-account}

首先，您必須建立Salesforce外部帳戶。

1. 瀏覽Campaign檔案總管的&#x200B;**[!UICONTROL Administration > Platform > External accounts]**&#x200B;節點並建立外部帳戶。
1. **型別**&#x200B;區段中的Select **[!UICONTROL Salesforce.com]**&#x200B;外部帳戶。
1. 輸入設定以啟用連線。

   ![Salesforce CRM外部帳戶，包含帳戶、密碼、安全性權杖及API版本欄位](assets/sfdc-external-account.png)

   若要設定Salesforce CRM外部帳戶以搭配Adobe Campaign使用，您必須提供下列詳細資料：

   * 在「**[!UICONTROL Account]**」欄位中輸入您的Salesforce登入資訊。
   * 輸入您的Salesforce密碼。
   * 您可以忽略&#x200B;**[!UICONTROL Client identifier]**&#x200B;欄位。
   * 複製/貼上您的Salesforce **[!UICONTROL Security token]**
   * 選取您的&#x200B;**[!UICONTROL API version]**。 支援的SFDC API版本列於Campaign [相容性矩陣](../start/compatibility-matrix.md)。

1. 使用&#x200B;**啟用**&#x200B;選項Select，在Campaign中啟用帳戶。

>[!NOTE]
>
>若要核准此設定，您必須登出並重新登入Adobe Campaign使用者端主控台。

## 要同步的Select表格{#sfdc-create-tables}

您現在可以設定要同步處理的表格。

1. 按一下&#x200B;**[!UICONTROL Salesforce CRM configuration wizard...]**。
1. Select要同步和啟動程式的表格。
1. 檢查&#x200B;**[!UICONTROL Administration > Configuration > Data schemas]**&#x200B;節點中Adobe Campaign產生的結構描述。

   在Campaign中匯入的&#x200B;**Salesforce**&#x200B;結構描述範例：

   ![在Salesforce上篩選的資料結構描述清單，顯示匯入的Salesforce CRM來源結構描述](assets/sfdc-schemas.png)

## 同步分項清單{#sfdc-enum-sync}

建立結構描述後，您就可以從Salesforce自動將分項清單同步到Adobe Campaign。

1. 從&#x200B;**[!UICONTROL Synchronizing enumerations...]**&#x200B;連結開啟助理。
1. 選取符合Adobe Campaign分項清單的Salesforce分項清單。
您可以將Adobe Campaign列舉的所有值取代為CRM的值：若要這麼做，請在&#x200B;**[!UICONTROL Replace]**&#x200B;欄中選取&#x200B;**[!UICONTROL Yes]**。

   ![使用「取代」欄同步化將CRM列舉對應到Campaign列舉的列舉對話方塊](assets/sfdc-enum.png)

1. 按一下&#x200B;**[!UICONTROL Next]**，然後按&#x200B;**[!UICONTROL Start]**&#x200B;開始匯入分項清單。

1. 瀏覽&#x200B;**[!UICONTROL Administration > Platform > Enumerations]**&#x200B;節點以檢查匯入的值。 深入瞭解[Campaign介面設定](../config/ui-settings.md)中的分項清單。

Adobe Campaign和Salesforce.com現已連線。 您可以設定兩個系統之間的資料同步。

若要在Adobe Campaign資料和SFDC之間同步資料，請建立工作流程並使用&#x200B;**[!UICONTROL CRM connector]**&#x200B;活動。

在此頁面[&#128279;](crm-data-sync.md)中進一步瞭解資料同步處理。

在此頁面[&#128279;](../config/enumerations.md)中進一步瞭解Campaign 中的列舉管理。
