---
title: 資料夾和檢視
description: 瞭解如何在Campaign Explorer中管理資料夾和檢視
feature: Audiences, Profiles, Application Settings
role: User
level: Beginner, Intermediate
exl-id: 762dcacc-4aeb-4990-af01-7f793bd69170
source-git-commit: 515520bb5b7131fc2ed2d1b2a843373f01af306a
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 1%

---

# 管理資料夾和檢視 {#folders-and-views}

Campaign資料夾是瀏覽器樹狀結構中的節點。 根據它們的型別，它們包含特定型別的資料。

檢視是一種特定的資料夾，不包含任何資料，但顯示實際儲存在相同型別之其他資料夾中的資料。 例如，如果您將傳送資料夾轉換為檢視，此資料夾會顯示所有傳送。 然後可以篩選此資料。


>[!NOTE]
>為了將檢視與標準資料夾區分開來，它們的名稱會以淺藍色顯示，而非黑色。
>

請注意，您可以指派許可權給檔案夾，以限制對特定資料的存取。 [了解更多](#restrict-access-to-a-folder)

## 使用資料夾時的最佳實務{#best-practices-folders}

* **使用內建資料夾** 讓每個參與專案的人更易於使用、維護及疑難排解應用程式。 請避免為收件者、清單、傳遞等建立自訂資料夾結構，但使用標準資料夾，例如 **管理**， **設定檔和目標**， **行銷活動管理**.

* **建立子資料夾**，例如將您的技術工作流程儲存在內建資料夾底下： **[!UICONTROL Administration > Production > Technical Workflows]**，並按每個工作流程型別建立子資料夾。

* **定義並套用命名慣例**&#x200B;例如，您可以按字母順序命名工作流程，讓它們按執行順序排序，例如：

  A1 — 匯入收件者，從10:00開始；A2 — 匯入票證，從11:00開始。

## 建立資料夾{#create-a-folder}

若要建立資料夾，請在現有資料夾上按一下滑鼠右鍵，並使用內容功能表。

若要建立與您選取的資料夾相同的資料夾型別，請選擇內容功能表中的第一個選項。 例如，從「收件者」資料夾中，選取 **[!UICONTROL Create a new 'Recipients' folder]**.

![](assets/create-recipient-folder.png)

您可以視需要拖放新資料夾以整理Campaign檔案總管樹狀結構。

若要建立其他型別的資料夾，請在現有資料夾上按一下滑鼠右鍵，然後選取 **[!UICONTROL Add new folder]**. 您可以根據要儲存的資料，建立所有型別的資料夾。

![](assets/add-new-folder.png)

>[!CAUTION]
>這些變更會套用至所有Campaign使用者。
>

## 將資料夾轉換為檢視{#turn-a-folder-to-a-view}

檢視是一種特定的資料夾，不包含任何資料，但顯示實際儲存在相同型別之其他資料夾中的資料。

您可以將任何資料夾轉換為檢視，但資料夾必須是空的。 將資料夾轉換為檢視時，會刪除資料夾中儲存的任何資料。

>[!CAUTION]
>
>檢視會顯示資料並提供存取權，即使資料並未實際儲存在檢視資料夾中亦然。 操作員若要存取內容，必須在來源資料夾中有適當的許可權，至少是讀取存取權。
>
>若要授予檢視的存取權而不授予其來源資料夾的存取權，請勿授予來源資料夾之父節點的讀取存取權。

在下列範例中，我們將建立一個新資料夾，以根據其內部名稱僅顯示美國的傳送。

1. 建立 **[!UICONTROL Deliveries]** 資料夾，並為其命名 **美國傳遞**.
1. 以滑鼠右鍵按一下此資料夾，然後選取 **[!UICONTROL Properties...]**.
1. 在 **[!UICONTROL Restriction]** 索引標籤，選取 **[!UICONTROL This folder is a view]**. 然後資料庫中的所有傳遞都會顯示。

   ![](assets/this-folder-is-a-view.png)

1. 從視窗中央區段的查詢編輯器定義篩選條件：資料夾中僅顯示與篩選對應的傳送。

   ![](assets/filter-view.png)

   >[!NOTE]
   >
   >瞭解如何在中設計查詢 [此頁面](create-filters.md#advanced-filters)


>[!CAUTION]
>
>管理時 [異動訊息傳送](../send/transactional.md) 事件， **[!UICONTROL Real time events]** 或 **[!UICONTROL Batch events]** 資料夾不得在執行例項上設定為檢視，因為這可能會導致許可權問題。

## 組織您的資料夾{#organize-your-folders}

依預設，新資料夾會新增到階層的頂端。

瀏覽 **子資料夾** 資料夾屬性的索引標籤，用以組織其子資料夾。

您可以使用右側的箭頭行動資料夾，或選取 **[!UICONTROL Sort the sub-folders in alphabetical order]** 自動排序的選項。

![](assets/sort-folders.png)


## 篩選資料夾中的資料{#filter-data-in-a-folder}

若要篩選儲存在資料夾中的資料，請存取資料夾屬性並選取限制標籤。

例如，下列資料夾將僅包含具有電子郵件地址且其來源未標籤為「外部」的連絡人 — 或空白。

![](assets/add-a-filter-to-a-folder.png)


## 限制資料夾的存取權{#restrict-access-to-a-folder}

使用檔案夾的許可權來組織和控制Campaign資料的存取。 進一步瞭解中檔案夾的許可權 [本節](../start/folder-permissions.md).
