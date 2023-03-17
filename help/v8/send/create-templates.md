---
product: campaign
title: 利用傳送範本
description: 了解如何在Campaign中建立和使用傳遞範本
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 3a4de36e-ba24-49ec-8113-f32f12c8ecdd
source-git-commit: edb099b3e882d857752af76798012ccd1c5a99be
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 6%

---

# 使用傳遞範本{#work-with-delivery-template}

使用傳遞範本來標準化創意外觀和風格，以便更快執行和啟動行銷活動。

範本可系統地包括：

* 類型
* 寄件者和回覆地址
* 基本個人化區塊
* 連結至 [鏡像頁面](../send/mirror-page.md) 取消訂閱連結
* 內容、公司標誌或簽名
* 其他傳送屬性，例如資源有效性、重試參數或隔離設定。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#delivery-template-video)


## 建立範本{#create-a-delivery-template}

若要建立傳遞範本，您可以複製內建的範本、將現有的傳遞轉換為範本，或從頭建立傳遞範本。

### 複製現有範本{#copy-an-existing-template}

Campaign隨附一組適用於每個管道的內建範本：電子郵件、推播、簡訊、直接郵件等。

建立傳遞範本最簡單的方式是複製和自訂內建範本。

若要複製傳送範本，請遵循下列步驟：

1. 瀏覽至 **[!UICONTROL Resources > Templates > Delivery templates]** 在Adobe Campaign探險家。
1. 選取內建的傳遞範本。 內建範本會以粗體顯示在清單中。
1. 按一下滑鼠右鍵並選取 **[!UICONTROL Duplicate]**.

   ![](assets/duplicate-built-in-template.png)

1. 定義範本設定並儲存新範本。

   ![](assets/delivery-template-new.png)

範本會新增至傳遞範本清單。 您現在可以在建立新傳送時選取它。

![](assets/select-the-new-template.png)

### 將現有傳送轉換為範本 {#convert-an-existing-delivery}

傳送可轉換為範本，以執行新的重複傳送動作。

若要將傳遞轉換為範本，請遵循下列步驟：

1. 從傳送清單中選取傳送，可透過 **[!UICONTROL Campaign management]** 行銷活動總管的節點。

1. 按一下滑鼠右鍵並選取 **[!UICONTROL Actions > Save as template...]**.

   ![](assets/save-as-template.png)

1. 編輯傳送屬性，並選取必須儲存新範本的資料夾(位於 **[!UICONTROL Folder]** 欄位)，以及必須建立根據此範本建立的傳送的資料夾(在 **[!UICONTROL Execution folder]** 欄位)。

   ![](assets/template-select-folders.png)

### 建立新範本 {#create-a-new-template}

>[!NOTE]
>
>為避免設定錯誤，Adobe建議您 [複製內建範本](#copy-an-existing-template) 和自訂其屬性，而非建立新範本。

若要從草稿開始設定傳送範本，請遵循下列步驟：

1. 瀏覽至 **資源** 資料夾，然後選取 **範本** then **傳遞範本**.
1. 按一下 **新增** ，建立新的傳遞範本。
1. 設定 **標籤** 和 **內部名稱** 的下限。
1. 儲存範本並重新開啟。
1. 從 **屬性** 按鈕，調整設定。
1. 在 **一般** ，確認或變更 **執行資料夾**, **資料夾**，和 **路由** 下拉式功能表。
1. 完成 **電子郵件參數** 類別，以及您的電子郵件主旨和目標母體。
1. 新增 **HTML內容** 若要個人化您的範本，您可以顯示 [鏡像頁面連結](../send/mirror-page.md) 和取消訂閱連結。
1. 選取 **預覽** 標籤。 在 **測試個人化** 下拉式功能表，選取 **收件者** 將範本預覽為選取的設定檔。
1. 按一下 **儲存**. 您的範本現在已可用於傳送。


## 使用範本{#use-a-delivery-template}

### 使用範本建立傳遞{#create-a-delivery-from-a-template}

若要根據現有範本建立傳送，請從可用的傳送範本清單中選取範本。

![](assets/select-the-new-template.png)

如果您看不到範本，請按一下 **[!UICONTROL Select link]** 資料夾，以瀏覽Campaign資料夾。

![](assets/browse-templates.png)

從 **[!UICONTROL Folder]** 欄位，或按一下 **[!UICONTROL Display sub-levels]** 表徵圖，以顯示當前目錄的子樹中目錄的內容。

選取要使用的傳送範本，然後按一下 **[!UICONTROL Ok]**.

### 執行範本 {#execute-a-template}

您可以直接從範本清單啟動範本的執行，不需先建立傳送。

要執行此操作，請選取要執行的範本，然後按一下滑鼠右鍵。 選取 **[!UICONTROL Actions>Execute the delivery template...]**。

您也可以使用 **[!UICONTROL File>Actions>Execute the delivery template...]**.

![](assets/execute-delivery-template.png)

輸入傳送參數，然後按一下 **[!UICONTROL Send]**.

此動作會在與範本相關聯的資料夾中產生傳送。 此傳送的名稱是建立傳送範本的傳送範本名稱。


## 教學課程影片 {#delivery-template-video}

### 如何設定傳遞範本

下列影片示範如何設定隨選傳遞的範本。

>[!VIDEO](https://video.tv.adobe.com/v/342082?quality=12)

### 如何設定傳遞範本屬性

以下影片說明如何設定傳送範本屬性，並詳細說明每個屬性。

>[!VIDEO](https://video.tv.adobe.com/v/338969?quality=12)

### 如何部署臨機傳遞範本

此影片說明如何部署隨選電子郵件傳送範本，並說明電子郵件傳送與傳送工作流程之間的差異。

>[!VIDEO](https://video.tv.adobe.com/v/338965?quality=12)

提供其他Campaign作法影片 [此處](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html){target="_blank"}.
