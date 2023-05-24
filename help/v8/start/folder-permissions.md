---
title: 授與和限制Campaign資料夾的許可權
description: 瞭解如何授與或限制檔案夾的許可權
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 5bd8dbba-7a06-4737-bc5a-60354f91c709
source-git-commit: b96ac3bd2365c548d071e626721d606dd33200b5
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# 管理檔案夾許可權{#manage-folder-permissions}

## 限制對資料夾的存取{#restrict-access-to-a-folder}

使用資料夾的許可權來組織和控制Campaign資料的存取。

檔案夾管理的詳細資訊，請參閱 [此頁面](../audiences/folders-and-views.md).

若要編輯特定Campaign資料夾的許可權，請遵循下列步驟：

1. 以滑鼠右鍵按一下資料夾並選取 **[!UICONTROL Properties...]**.
1. 瀏覽至 **[!UICONTROL Security]** 標籤以檢視此資料夾的授權。

   ![](assets/folder-permissions.png)

* 至 **授權群組或操作員**，按一下 **[!UICONTROL Add]** 按鈕並選取群組或運運算元，以指派此資料夾的授權。
* 至 **禁止群組或操作員**，按一下 **[!UICONTROL Delete]** 並選取群組或運運算元，以移除此資料夾的授權。
* 至 **選取指派給群組或操作員的許可權**，選取群組或操作員，選取您要授與的存取許可權，然後取消選取其他許可權。

## 傳播許可權 {#propagate-permissions}

若要傳播授權和存取許可權，請選取 **[!UICONTROL Propagate]** 資料夾屬性中的選項。

然後此視窗中定義的授權將套用至目前節點的所有子資料夾。 您可以隨時為每個子資料夾多載這些授權。

>[!NOTE]
>
>取消核取 **[!UICONTROL Propagate]** 資料夾的選項不會為子資料夾清除它：您必須為每個子資料夾明確清除它。

## 授與存取權給所有運運算元 {#grant-access-to-all-operators}

在 **[!UICONTROL Security]** 索引標籤中，選取 **[!UICONTROL System folder]** 允許存取所有運運算元，無論其許可權為何。

如果清除此選項，您必須明確地將運運算元（或其群組）新增回授權清單，才能讓運運算元存取許可權。
