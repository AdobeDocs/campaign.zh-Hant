---
title: 資料夾和視圖
description: 瞭解如何在市場活動瀏覽器中管理資料夾和視圖
feature: Audiences, Profiles, Application Settings
role: User
level: Beginner, Intermediate
exl-id: 762dcacc-4aeb-4990-af01-7f793bd69170
source-git-commit: 515520bb5b7131fc2ed2d1b2a843373f01af306a
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 1%

---

# 管理資料夾和檢視 {#folders-and-views}

市場活動資料夾是瀏覽器樹中的節點。 根據其類型，它們包含某些類型的資料。

視圖是一個特定資料夾，它不包含任何資料，但顯示物理上儲存在相同類型的其他資料夾中的資料。 例如，如果將交貨資料夾轉到視圖，則此資料夾將顯示所有交貨。 然後可以過濾此資料。


>[!NOTE]
>要區分視圖和標準資料夾，其名稱以淡藍色而不是黑色顯示。

請注意，您可以為資料夾分配權限，以限制對某些資料的訪問。 [了解更多](#restrict-access-to-a-folder)

## 使用資料夾時的最佳做法{#best-practices-folders}

* **使用內置資料夾** 使項目中的每個參與者都更容易使用、維護和排除應用程式故障。 避免為收件人、清單、遞送等建立自定義資料夾結構，但使用標準資料夾，如 **管理**。 **配置檔案和目標**。 **市場活動管理**。

* **建立子資料夾**&#x200B;例如，將技術工作流保存在內置資料夾下： **[!UICONTROL Administration > Production > Technical Workflows]**，並按工作流類型建立子資料夾。

* **定義和應用命名約定**&#x200B;例如，您可以按字母順序命名工作流，以便它們按執行順序排列，例如：

   A1 — 導入收件人，從10:00開始；A2 — 導入票證，11:00開始。

## 建立資料夾{#create-a-folder}

要建立資料夾，請按一下右鍵現有資料夾並使用上下文菜單。

要建立與所選資料夾類型相同的資料夾類型，請在上下文菜單中選擇第一個選項。 例如，從「收件人」資料夾中，選擇 **[!UICONTROL Create a new 'Recipients' folder]**。

![](assets/create-recipient-folder.png)

您可以拖放新資料夾以根據需要組織市場活動瀏覽器樹。

要建立另一類資料夾，請按一下右鍵現有資料夾並選擇 **[!UICONTROL Add new folder]**。 您可以根據要儲存的資料建立所有類型的資料夾。

![](assets/add-new-folder.png)

>[!CAUTION]
>這些更改適用於所有市場活動用戶。

## 將資料夾轉換為視圖{#turn-a-folder-to-a-view}

視圖是一個特定資料夾，它不包含任何資料，但顯示物理上儲存在相同類型的其他資料夾中的資料。

可以將任何資料夾轉換為視圖，但該資料夾必須為空。 將資料夾轉換為視圖時，資料夾中儲存的任何資料都會被刪除。

>[!CAUTION]
>
>視圖顯示資料並提供對其的訪問權限，即使資料未實際儲存在視圖資料夾中。 要訪問內容，操作員必須在源資料夾中擁有相應的權限，至少具有「讀取」權限。
>
>若要授予對視圖的訪問權限而不授予對其源資料夾的訪問權限，請不要授予對源資料夾父節點的讀訪問權限。

在下面的示例中，我們將根據美國交貨的內部名稱建立一個新資料夾，以僅顯示美國交貨。

1. 建立 **[!UICONTROL Deliveries]** 資料夾，並命名 **美國交貨**。
1. 按一下右鍵此資料夾並選擇 **[!UICONTROL Properties...]**。
1. 在 **[!UICONTROL Restriction]** 索引標籤中，選取 **[!UICONTROL This folder is a view]**。然後將顯示資料庫中的所有交貨。

   ![](assets/this-folder-is-a-view.png)

1. 從窗口中央部分的查詢編輯器中定義篩選條件：資料夾中只顯示與篩選器對應的交貨。

   ![](assets/filter-view.png)

   >[!NOTE]
   >
   >瞭解如何在 [此頁](create-filters.md#advanced-filters)


>[!CAUTION]
>
>管理時 [事務消息](../send/transactional.md) 事件、 **[!UICONTROL Real time events]** 或 **[!UICONTROL Batch events]** 不能將資料夾設定為執行實例的視圖，因為這可能導致權限問題。

## 組織資料夾{#organize-your-folders}

預設情況下，會在層次結構的頂部添加新資料夾。

瀏覽 **子資料夾** 的子資料夾。

可以使用右側的箭頭移動資料夾，或選擇 **[!UICONTROL Sort the sub-folders in alphabetical order]** 頁籤

![](assets/sort-folders.png)


## 篩選資料夾中的資料{#filter-data-in-a-folder}

要篩選儲存在資料夾中的資料，請訪問資料夾屬性並選擇「限制」頁籤。

例如，下面的資料夾將僅包含具有電子郵件地址且其來源未標籤為「外部」或為空的聯繫人。

![](assets/add-a-filter-to-a-folder.png)


## 限制對資料夾的訪問{#restrict-access-to-a-folder}

使用對資料夾的權限來組織和控制對市場活動資料的訪問。 瞭解有關中資料夾權限的詳細資訊 [此部分](../start/folder-permissions.md)。
