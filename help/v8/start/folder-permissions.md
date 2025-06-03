---
title: 授與和限制Campaign資料夾的許可權
description: 瞭解如何授與或限制檔案夾的許可權
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 5bd8dbba-7a06-4737-bc5a-60354f91c709
version: Campaign v8, Campaign Classic v7
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 18%

---

# 管理檔案夾許可權{#manage-folder-permissions}

## 限制資料夾的存取權{#restrict-access-to-a-folder}

使用檔案夾的許可權來組織和控制Campaign資料的存取。

[此頁面](../audiences/folders-and-views.md)中詳細說明了資料夾管理。

若要編輯特定Campaign資料夾的許可權，請遵循下列步驟：

1. 在資料夾上按一下滑鼠右鍵，然後選取&#x200B;**[!UICONTROL Properties...]**。
1. 瀏覽至&#x200B;**[!UICONTROL Security]**&#x200B;標籤，檢視此資料夾的授權。

   ![](assets/folder-permissions.png)

* 若要&#x200B;**授權群組或操作員**，請按一下&#x200B;**[!UICONTROL Add]**&#x200B;按鈕，然後選取群組或操作員以指派此資料夾的授權。
* 若要&#x200B;**禁止群組或運運算元**，請按一下&#x200B;**[!UICONTROL Delete]**&#x200B;並選取群組或運運算元以移除此資料夾的授權。
* 若要&#x200B;**選取指派給群組或運運算元的許可權**，請選取群組或運運算元，選取您要授與的存取許可權，然後取消選取其他許可權。

>[!NOTE]
>
>您必須至少擁有一個資料夾的寫入權限，才能夠建立物件。
>
>若要建立片段，您無需具備管理員身分，但是您必須擁有至少一個「內容視覺片段」資料夾的寫入權限。否則，您將無法建立視覺片段。

## 傳播許可權 {#propagate-permissions}

若要傳播授權和存取許可權，請在資料夾屬性中選取&#x200B;**[!UICONTROL Propagate]**&#x200B;選項。

此視窗中定義的授權將套用至目前節點的所有子資料夾。 您一律可以超載每個子資料夾的這些授權。

>[!NOTE]
>
>取消核取資料夾的&#x200B;**[!UICONTROL Propagate]**&#x200B;選項並不會為子資料夾清除它：您必須為每個子資料夾明確清除它。

## 授與存取權給所有運運算元 {#grant-access-to-all-operators}

在&#x200B;**[!UICONTROL Security]**&#x200B;索引標籤中，選取&#x200B;**[!UICONTROL System folder]**&#x200B;以允許存取所有運運算元，無論其許可權為何。

如果清除此選項，您必須明確將運運算元（或其群組）新增回授權清單，讓運運算元（或其群組）才能存取。
