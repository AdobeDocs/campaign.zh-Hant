---
title: 授予和限制Campaign資料夾的權限
description: 了解如何授與或限制資料夾的權限
feature: Permissions
role: User, Admin
level: Beginner
source-git-commit: 857445d7d7d8080e479bdc596fb3162c2b4a2b6b
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# 管理資料夾權限{#manage-folder-permissions}

## 限制對資料夾的訪問{#restrict-access-to-a-folder}

使用資料夾的權限來組織及控制對Campaign資料的存取。

資料夾管理在 [本頁](../audiences/folders-and-views.md).

若要編輯特定Campaign資料夾的權限，請遵循下列步驟：

1. 按一下右鍵資料夾，然後選取 **[!UICONTROL Properties...]**.
1. 瀏覽至 **[!UICONTROL Security]** 頁簽查看此資料夾上的授權。

   ![](assets/folder-permissions.png)

* 結束日期 **授權群組或運算子**，按一下 **[!UICONTROL Add]** 按鈕，然後選擇組或運算子以分配此資料夾的授權。
* 結束日期 **禁止組或操作員**，按一下 **[!UICONTROL Delete]** 並選擇要刪除此資料夾授權的組或運算子。
* 結束日期 **選取指派給群組或運算子的權限**，選擇組或運算子，選擇要授予的訪問權限，然後取消選擇其他訪問權限。

## 傳播權限 {#propagate-permissions}

要傳播授權和訪問權限，請選擇 **[!UICONTROL Propagate]** 選項。

然後，此窗口中定義的授權將應用於當前節點的所有子資料夾。 您始終可以為每個子資料夾過載這些授權。

>[!NOTE]
>
>取消勾選 **[!UICONTROL Propagate]** 資料夾的選項不會清除子資料夾的選項：您必須為每個子資料夾明確清除它。

## 授予所有運算子的存取權 {#grant-access-to-all-operators}

在 **[!UICONTROL Security]** 頁簽，選擇 **[!UICONTROL System folder]** 允許所有運算子的存取權（無論其權限為何）。

如果清除了此選項，則必須將運算子（或其組）顯式添加回授權清單中，以使其具有訪問權限。
