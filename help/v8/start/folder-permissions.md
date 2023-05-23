---
title: 授予和限制市場活動資料夾的權限
description: 瞭解如何授予或限制資料夾的權限
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 5bd8dbba-7a06-4737-bc5a-60354f91c709
source-git-commit: b96ac3bd2365c548d071e626721d606dd33200b5
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# 管理資料夾權限{#manage-folder-permissions}

## 限制對資料夾的訪問{#restrict-access-to-a-folder}

使用對資料夾的權限來組織和控制對市場活動資料的訪問。

資料夾管理的詳細資訊 [此頁](../audiences/folders-and-views.md)。

要編輯特定市場活動資料夾的權限，請執行以下步驟：

1. 按一下右鍵資料夾並選擇 **[!UICONTROL Properties...]**。
1. 瀏覽到 **[!UICONTROL Security]** 頁籤，查看此資料夾的授權。

   ![](assets/folder-permissions.png)

* 至 **授權組或操作員**，按一下 **[!UICONTROL Add]** 按鈕並選擇要為此資料夾分配授權的組或運算子。
* 至 **禁止組或運算子**&#x200B;按一下 **[!UICONTROL Delete]** 並選擇要刪除此資料夾的授權的組或運算子。
* 至 **選擇分配給組或運算子的權限**，選擇組或運算子，選擇要授予的訪問權限，然後取消選擇其他訪問權限。

## 傳播權限 {#propagate-permissions}

要傳播授權和訪問權限，請選擇 **[!UICONTROL Propagate]** 的子菜單。

然後，此窗口中定義的授權將應用於當前節點的所有子資料夾。 您始終可以使每個子資料夾的這些授權過載。

>[!NOTE]
>
>取消檢查 **[!UICONTROL Propagate]** 資料夾的選項不清除子資料夾：必須為每個子資料夾明確清除它。

## 授予對所有運算子的訪問權限 {#grant-access-to-all-operators}

在 **[!UICONTROL Security]** 頁籤 **[!UICONTROL System folder]** 允許訪問所有運算子，而不管其權限如何。

如果清除此選項，則必須將運算子（或其組）顯式添加回授權清單中，以便它們具有訪問權限。
