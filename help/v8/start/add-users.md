---
title: 授與Campaign v8的許可權
description: 瞭解如何授與Campaign v8的許可權
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 2%

---

# 開始使用權限

在Adobe Campaign中，使用者是&#x200B;**操作員**，而&#x200B;**操作員群組**&#x200B;代表使用者角色。

運運算元是有許可權登入及執行動作的Adobe Campaign使用者。 依預設，運運算元儲存在&#x200B;**[!UICONTROL Administration > Access management > Operators]**&#x200B;節點中。

Adobe Campaign隨附內建運運算元群組，例如「行銷活動管理員」或「工作流程主管」。 在[本節](../start/gs-permissions.md)中進一步瞭解許可權

作為操作員群組的成員，使用者有權執行稱為「已命名的許可權」的操作，並且有權存取包含在&#x200B;**總管**&#x200B;檢視資料夾中的資料。 運運算元可以是多個運運算元群組的成員：許可權和存取許可權是可相加的。

已命名的許可權會將許可權授予：

* 執行作業
例如，已針對具有&#x200B;**準備傳遞**&#x200B;命名許可權的&#x200B;**傳遞操作員**&#x200B;群組的成員，啟用傳遞編輯器中的&#x200B;**分析**&#x200B;按鈕

* 存取資料夾
操作員群組的成員資格可以透過變更資料夾的安全性設定，來授予或限制資料夾的存取權。 在[此頁面](../start/folder-permissions.md)瞭解更多資訊。 例如，它可以影響： **寫入存取權**&#x200B;以建立新實體（例如傳送、設定檔等）、**讀取存取權**&#x200B;以使用實體、**刪除存取權**&#x200B;以刪除實體。

## 安全性區域

每個運運算元都必須連結到區域才能登入執行個體，而且運運算元IP必須包含在安全性區域中定義的位址或位址集中。 安全性區域設定是在Adobe Campaign伺服器的設定檔案中執行。

運運算元會從其在主控台中的設定檔連結至安全性區域，可在&#x200B;**[!UICONTROL Administration > Access management > Operators]**&#x200B;節點中存取。

>[!NOTE]
>
>Adobe身為「受管理的Cloud Service」使用者，會為您設定安全性區域。 如需詳細資訊，[連絡Adobe](https://helpx.adobe.com/tw/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}。

**了解更多**

* [內建已命名許可權](../start/gs-permissions.md)

* [設定許可權的步驟](../start/manage-permissions.md)
