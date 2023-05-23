---
product: campaign
title: 利用傳送範本
description: 瞭解如何在市場活動中建立和使用交付模板
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 3a4de36e-ba24-49ec-8113-f32f12c8ecdd
source-git-commit: 34af97ae01f7dba418fd0a8c950fc549dfbbd98b
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 5%

---

# 使用交貨模板{#work-with-delivery-template}

使用交付模板來規範創意外觀，以便更快地執行和啟動活動。

模板可包括：

* 類型
* 寄件者和回覆地址
* 基本 [個性化塊](../send/personalization-blocks.md)
* 指向 [鏡像頁](../send/mirror-page.md) 取消訂閱連結
* 內容、公司徽標或簽名
* 其他傳遞屬性，如資源有效性、重試參數或隔離設定。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#delivery-template-video)


## 建立模板{#create-a-delivery-template}

要建立交貨模板，您可以複製內置模板、將現有交貨轉換為模板或從頭建立交貨模板。

### 複製現有模板{#copy-an-existing-template}

市場活動附帶了一套適用於每個渠道的內置模板：電子郵件、推送、簡訊、直郵等。

建立交貨模板的最簡單方法是複製和自定義內置模板。

要複製交貨模板，請執行以下步驟：

1. 瀏覽到 **[!UICONTROL Resources > Templates > Delivery templates]** Adobe Campaign探險家。
1. 選擇內置交貨模板。 內置模板將在清單中加粗。
1. 按一下右鍵並選擇 **[!UICONTROL Duplicate]**。

   ![](assets/duplicate-built-in-template.png)

1. 定義模板設定並保存新模板。

   ![](assets/delivery-template-new.png)

模板將添加到交貨模板清單。 現在，您可以在建立新交貨時選擇它。

![](assets/select-the-new-template.png)

### 將現有交貨轉換為模板 {#convert-an-existing-delivery}

可以將交貨轉換為用於新的重複交貨操作的模板。

要將交貨轉換為模板，請執行以下步驟：

1. 從交貨清單中選擇可通過 **[!UICONTROL Campaign management]** 市場活動瀏覽器的節點。

1. 按一下右鍵並選擇 **[!UICONTROL Actions > Save as template...]**。

   ![](assets/save-as-template.png)

1. 編輯交貨屬性並選擇必須保存新模板的資料夾(位於 **[!UICONTROL Folder]** )，以及必須建立基於此模板建立的交貨的資料夾(在 **[!UICONTROL Execution folder]** )。

   ![](assets/template-select-folders.png)

### 建立新模板 {#create-a-new-template}

>[!NOTE]
>
>為避免配置錯誤，Adobe建議您 [複製內置模板](#copy-an-existing-template) 並自定義其屬性，而不是建立新模板。

要從頭配置交貨模板，請執行以下步驟：

1. 瀏覽到 **資源** 市場活動瀏覽器中的資料夾，然後選擇 **模板** 然後 **交貨模板**。
1. 按一下 **新建** 的子菜單。
1. 設定 **標籤** 和 **內部名稱** 的子菜單。
1. 保存模板並重新開啟它。
1. 從 **屬性** 按鈕，修改設定。
1. 在 **常規** 頁籤，確認或更改在 **執行資料夾**。 **資料夾**, **路由** 的下界。
1. 完成 **電子郵件參數** 與您的電子郵件主題和目標群體的類別。
1. 添加 **HTML內容** 要個性化模板，可以顯示 [鏡像頁面連結](../send/mirror-page.md) 和取消訂閱連結。
1. 選擇 **預覽** 頁籤。 在 **Test個性化** 下拉菜單，選擇 **收件人** 將模板作為所選配置檔案預覽。
1. 按一下「**儲存**」。您的模板現在已準備好用於交貨。


## 使用範本{#use-a-delivery-template}

### 使用範本建立傳遞{#create-a-delivery-from-a-template}

要基於現有模板建立交貨，請從可用交貨模板清單中選擇該模板。

![](assets/select-the-new-template.png)

如果看不到模板，請按一下 **[!UICONTROL Select link]** 資料夾，以瀏覽市場活動資料夾。

![](assets/browse-templates.png)

從 **[!UICONTROL Folder]** ，或按一下 **[!UICONTROL Display sub-levels]** 表徵圖，顯示當前目錄子樹中目錄的內容。

選擇要使用的交貨模板，然後按一下 **[!UICONTROL Ok]**。

### 執行模板 {#execute-a-template}

您可以直接從模板清單啟動模板的執行，而無需先建立傳遞。

為此，請選擇要執行的模板，然後按一下右鍵。 選取 **[!UICONTROL Actions>Execute the delivery template...]**。

您還可以使用 **[!UICONTROL File>Actions>Execute the delivery template...]**。

![](assets/execute-delivery-template.png)

輸入交貨參數，然後按一下 **[!UICONTROL Send]**。

此操作將在與模板關聯的資料夾中生成交貨。 此傳遞的名稱是從中建立它的傳遞模板的名稱。


## 教學課程影片 {#delivery-template-video}

### 如何配置傳遞模板

下列影片示範如何設定隨選傳遞的範本。

>[!VIDEO](https://video.tv.adobe.com/v/342082?quality=12)

### 如何設定交貨模板屬性

以下視頻顯示如何設定交付模板屬性並詳細說明每個屬性。

>[!VIDEO](https://video.tv.adobe.com/v/338969?quality=12)

### 如何部署即席交付模板

此視頻說明了如何部署即席電子郵件傳遞模板，並說明了電子郵件傳遞與傳遞工作流之間的區別。

>[!VIDEO](https://video.tv.adobe.com/v/338965?quality=12)

還提供了其他市場活動操作視頻 [這裡](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html){target="_blank"}。
