---
product: campaign
title: 使用傳遞範本
description: 了解如何在 Campaign 中建立和使用傳遞範本
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 3a4de36e-ba24-49ec-8113-f32f12c8ecdd
source-git-commit: acb559c74aea3f59c05792b7596d0f85ff05047c
workflow-type: tm+mt
source-wordcount: '939'
ht-degree: 19%

---

# 使用傳遞範本 {#work-with-delivery-template}

## 開始使用傳遞範本

每個傳遞都是根據範本建立的。 範本是一種可重複使用的設定，可促進並標準化您的實施。 您可以使用內建或自訂範本。

範本可包含部分或完整組態設定，例如：

* [類型規則](../../automation/campaign-opt/campaign-typologies.md)
* 寄件者和回覆地址
* 基本[個人化區塊](../send/personalization-blocks.md)
* 連結至[映象頁面](../send/mirror-page.md)和取消訂閱連結
* 內容、公司標誌或簽名
* 其他傳遞屬性，例如資源有效性、重試參數或隔離設定。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#delivery-template-video)

在Adobe Campaign中，您可以使用兩種型別的範本：

1. Adobe Campaign **內建**&#x200B;傳遞範本 — 每個管道都可使用內建範本。 這些檔案不得修改或刪除。 每個傳遞管道都包含基本設定。 身為管理員，您可以設定預設值，或限制使用者的特定功能，例如修改追蹤引數、寄件者電子郵件地址等。 內建範本在範本清單中以粗體顯示。

1. **自訂**&#x200B;傳遞範本 — 身為Adobe Campaign管理員，您可以建立新的傳遞範本。 最佳實務是複製和更新內建範本，而非從頭開始建立範本。 例如，您可以設定電子郵件傳遞範本，當使用者從此範本建立傳遞時，他們只需輸入文字或HTML內容即可。 所有其他設定均已定義。

>[!NOTE]
>
>可用的範本取決於存取權、執行個體設定和上下文。 例如，當您建立資訊服務時，可以連結確認訊息的傳遞範本：然後您只能存取其目標對應為訂閱對應的範本。 其他範本在此內容中不可見。 如需詳細資訊，請參閱[選取目標對應](../audiences/target-mappings.md)和[服務與訂閱](../start/subscriptions.md)。


## 建立範本 {#create-a-delivery-template}

若要建立傳遞範本，您可以複製內建範本或將現有傳遞轉換為範本。 您也可以從頭開始建立傳遞範本，但不建議這麼做。 這些方法的詳細資訊如下。

### 複製現有範本{#copy-an-existing-template}

Campaign為每個頻道提供一組內建範本：電子郵件、推播、簡訊、直接郵件等。

建立傳遞範本最簡單的方法是複製和自訂內建範本。

若要複製傳遞範本，請依照以下步驟進行：

1. 在Adobe Campaign總管中瀏覽至&#x200B;**[!UICONTROL Resources > Templates > Delivery templates]**。
1. 選取內建傳遞範本。 內建範本會以粗體顯示在清單中。
1. 按一下滑鼠右鍵並選取&#x200B;**[!UICONTROL Duplicate]**。

   ![](assets/duplicate-built-in-template.png)

1. 定義範本設定並儲存新範本。

   ![](assets/delivery-template-new.png)

該範本即新增到傳遞範本清單中。您現在建立新傳遞時即可以選取該範本。

![](assets/select-the-new-template.png)

### 將現有傳遞轉換為範本 {#convert-an-existing-delivery}

傳遞可以轉換為範本以供新的重複傳遞動作使用。

若要將傳遞轉換為範本，請依照以下步驟進行：

1. 從傳遞清單選取傳遞，可透過Campaign總管的&#x200B;**[!UICONTROL Campaign management]**&#x200B;節點存取。

1. 按一下滑鼠右鍵並選取&#x200B;**[!UICONTROL Actions > Save as template...]**。

   ![](assets/save-as-template.png)

1. 編輯傳遞屬性，並選取必須儲存新範本的資料夾（在「**[!UICONTROL Folder]**」欄位中），以及必須建立根據此範本之傳遞的資料夾（在「**[!UICONTROL Execution folder]**」欄位中）。

   ![](assets/template-select-folders.png)

### 建立新的範本 {#create-a-new-template}

>[!NOTE]
>
>為避免發生設定錯誤，Adobe 建議您[複製內建範本](#copy-an-existing-template)並自訂其屬性，而不是建立新範本。

若要從頭設定傳遞範本，請依照以下步驟進行：

1. 瀏覽至Campaign檔案總管中的&#x200B;**資源**&#x200B;資料夾，並選取&#x200B;**範本**&#x200B;然後&#x200B;**傳遞範本**。
1. 按一下工具列中的「新增&#x200B;****」以建立新的傳遞範本。
1. 設定資料夾的&#x200B;**標籤**&#x200B;和&#x200B;**內部名稱**。
1. 儲存範本並重新開啟。
1. 從&#x200B;**屬性**&#x200B;按鈕，調整設定。
1. 在&#x200B;**一般**&#x200B;索引標籤中，確認或變更&#x200B;**執行資料夾**、**資料夾**&#x200B;及&#x200B;**路由**&#x200B;下拉式功能表中選取的位置。
1. 使用您的電子郵件主旨和目標母體完成&#x200B;**電子郵件引數**&#x200B;類別。
1. 新增您的&#x200B;**HTML內容**&#x200B;以個人化您的範本，您可以顯示[映象頁面連結](../send/mirror-page.md)和取消訂閱連結。
1. 選取&#x200B;**預覽**&#x200B;索引標籤。 在&#x200B;**測試個人化**&#x200B;下拉式功能表中，選取&#x200B;**收件者**&#x200B;以預覽您的範本作為所選設定檔。
1. 按一下&#x200B;**儲存**。 您的範本現在已準備好用於傳遞。


## 使用範本 {#use-a-delivery-template}

### 使用範本建立傳遞 {#create-a-delivery-from-a-template}

若要根據現有範本建立傳遞，請從可用傳遞範本清單中選取範本。

![](assets/select-the-new-template.png)

如果您看不到範本，請按一下欄位右側的&#x200B;**[!UICONTROL Select link]**&#x200B;資料夾，以瀏覽Campaign資料夾。

![](assets/browse-templates.png)

從&#x200B;**[!UICONTROL Folder]**&#x200B;欄位選取所要的目錄，或按一下&#x200B;**[!UICONTROL Display sub-levels]**&#x200B;圖示以顯示目前目錄子樹狀結構中的目錄內容。

選取要使用的傳遞範本，然後按一下&#x200B;**[!UICONTROL Ok]**。

### 執行範本 {#execute-a-template}

您可以直接從範本清單中啟動範本執行，而不需要先建立傳遞。

若要這麼做，請選取要執行的範本，然後按一下滑鼠右鍵。 選取 **[!UICONTROL Actions>Execute the delivery template...]**。

您也可以使用&#x200B;**[!UICONTROL File>Actions>Execute the delivery template...]**。

![](assets/execute-delivery-template.png)

輸入傳遞引數並按一下&#x200B;**[!UICONTROL Send]**。

此動作會在與範本關聯的資料夾中產生傳遞。 此傳遞的名稱是從中建立其傳遞範本的名稱。


## 教學課程影片 {#delivery-template-video}

### 如何設定傳遞範本

下列影片示範如何設定隨選傳遞的範本。

>[!VIDEO](https://video.tv.adobe.com/v/342082?quality=12)

### 如何設定傳遞範本屬性

以下影片說明如何設定傳遞範本屬性，並詳細說明每個屬性。

>[!VIDEO](https://video.tv.adobe.com/v/338969?quality=12)

### 如何部署隨選傳遞範本

此影片說明如何部署隨選電子郵件傳遞範本，並說明電子郵件傳遞與傳遞工作流程之間的差異。

>[!VIDEO](https://video.tv.adobe.com/v/338965?quality=12)

[此處](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html){target="_blank"}提供其他Campaign操作說明影片。
