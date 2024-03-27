---
product: campaign
title: 使用傳遞範本
description: 了解如何在 Campaign 中建立和使用傳遞範本
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 3a4de36e-ba24-49ec-8113-f32f12c8ecdd
source-git-commit: 34af97ae01f7dba418fd0a8c950fc549dfbbd98b
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 33%

---

# 使用傳遞範本{#work-with-delivery-template}

使用傳遞範本將創意外觀和風格標準化，以便更快速地執行和啟動行銷活動。

範本可能包括：

* 類型
* 寄件者和回覆地址
* 基本 [個人化區塊](../send/personalization-blocks.md)
* 連結至 [映象頁面](../send/mirror-page.md) 和取消訂閱連結
* 內容、公司標誌或簽名
* 其他傳遞屬性，例如資源有效性、重試參數或隔離設定。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#delivery-template-video)


## 建立範本{#create-a-delivery-template}

若要建立傳遞範本，您可以複製內建範本、將現有傳遞轉換為範本或從頭開始建立傳遞範本。

### 複製現有範本{#copy-an-existing-template}

Campaign為每個頻道提供一組內建範本：電子郵件、推播、簡訊、直接郵件等。

建立傳遞範本最簡單的方法是複製和自訂內建範本。

若要複製傳遞範本，請依照以下步驟進行：

1. 瀏覽至 **[!UICONTROL Resources > Templates > Delivery templates]** 在Adobe Campaign explorer中。
1. 選取內建傳遞範本。 內建範本會以粗體顯示在清單中。
1. 按一下右鍵並選取 **[!UICONTROL Duplicate]**.

   ![](assets/duplicate-built-in-template.png)

1. 定義範本設定並儲存新範本。

   ![](assets/delivery-template-new.png)

該範本即新增到傳遞範本清單中。您現在建立新傳遞時即可以選取該範本。

![](assets/select-the-new-template.png)

### 將現有傳遞轉換為範本 {#convert-an-existing-delivery}

傳遞可以轉換為範本以供新的重複傳遞動作使用。

若要將傳遞轉換為範本，請依照以下步驟進行：

1. 從傳遞清單中選取傳遞，存取方式為 **[!UICONTROL Campaign management]** Campaign總管的節點。

1. 按一下右鍵並選取 **[!UICONTROL Actions > Save as template...]**.

   ![](assets/save-as-template.png)

1. 編輯傳送屬性，並選取必須儲存新範本的資料夾(在 **[!UICONTROL Folder]** 欄位)，以及根據此範本建立傳遞時所在的資料夾(位於 **[!UICONTROL Execution folder]** 欄位)。

   ![](assets/template-select-folders.png)

### 建立新的範本 {#create-a-new-template}

>[!NOTE]
>
>為避免發生設定錯誤，Adobe 建議您[複製內建範本](#copy-an-existing-template)並自訂其屬性，而不是建立新範本。

若要從頭設定傳遞範本，請依照以下步驟進行：

1. 瀏覽至 **資源** 資料夾，然後選取 **範本** 則 **傳遞範本**.
1. 按一下 **新增** ，以建立新的傳遞範本。
1. 設定 **標籤** 和 **內部名稱** 檔案夾的。
1. 儲存範本並重新開啟。
1. 從 **屬性** 按鈕，調整設定。
1. 在 **一般** 標籤，確認或變更 **執行資料夾**， **資料夾**、和 **路由** 下拉式功能表。
1. 完成 **電子郵件引數** 類別，以及您的電子郵件主題和目標母體。
1. 新增您的 **HTML內容** 若要個人化您的範本，您可以顯示 [映象頁面連結](../send/mirror-page.md) 和取消訂閱連結。
1. 選取 **預覽** 標籤。 在 **測試個人化** 下拉式功能表，選取 **收件者** 以預覽您所選設定檔的範本。
1. 按一下 **儲存**. 您的範本現在已準備好用於傳遞。


## 使用範本{#use-a-delivery-template}

### 使用範本建立傳遞{#create-a-delivery-from-a-template}

若要根據現有範本建立傳遞，請從可用傳遞範本清單中選取範本。

![](assets/select-the-new-template.png)

如果您看不到範本，請按一下 **[!UICONTROL Select link]** 欄位右側的資料夾以瀏覽Campaign資料夾。

![](assets/browse-templates.png)

從中選擇所需的目錄 **[!UICONTROL Folder]** 欄位，或按一下 **[!UICONTROL Display sub-levels]** 圖示來顯示目前目錄之子樹狀結構中目錄的內容。

選取要使用的傳遞範本，然後按一下 **[!UICONTROL Ok]**.

### 執行範本 {#execute-a-template}

您可以直接從範本清單中啟動範本執行，而不需要先建立傳遞。

若要這麼做，請選取要執行的範本，然後按一下滑鼠右鍵。 選取 **[!UICONTROL Actions>Execute the delivery template...]**。

您也可以使用 **[!UICONTROL File>Actions>Execute the delivery template...]**.

![](assets/execute-delivery-template.png)

輸入傳遞引數，然後按一下 **[!UICONTROL Send]**.

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

提供其他Campaign操作說明影片 [此處](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html){target="_blank"}.
