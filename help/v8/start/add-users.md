---
title: 授與Campaign v8的許可權
description: 瞭解如何授與Campaign v8的許可權
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e3988c18-3cfa-4f16-b812-ac2d2b1056fa
    internal-label: Permissions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 7%
---
# 開始使用權限

在Adobe Campaign中，使用者是&#x200B;**操作員**，而&#x200B;**操作員群組**&#x200B;代表使用者角色。

運運算元是有許可權登入及執行動作的Adobe Campaign使用者。 依預設，運運算元儲存在&#x200B;**[!UICONTROL Administration > Access management > Operators]**&#x200B;節點中。

Adobe Campaign隨附內建運運算元群組，例如「行銷活動管理員」或「工作流程主管」。 在[本節](../start/gs-permissions.md)中進一步瞭解許可權

作為操作員群組的成員，使用者有權執行稱為「已命名的許可權」的操作，並且有權存取包含在&#x200B;**總管**&#x200B;檢視資料夾中的資料。 運運算元可以是多個運運算元群組的成員：許可權和存取許可權是可相加的。

已命名的許可權會將許可權授予：

* 執行作業
例如，已針對具有**準備傳遞**&#x200B;命名許可權的&#x200B;**傳遞操作員**&#x200B;群組的成員，啟用傳遞編輯器中的&#x200B;**分析**&#x200B;按鈕

* 存取資料夾
操作員群組的成員資格可以透過變更資料夾的安全性設定，來授予或限制資料夾的存取權。 在[本頁](../start/folder-permissions.md)中瞭解更多。 例如，它可以影響： **寫入存取權**&#x200B;以建立新實體（例如傳送、設定檔等）、**讀取存取權**&#x200B;以使用實體、**刪除存取權**&#x200B;以刪除實體。

## 安全性區域

每個運運算元都必須連結到區域才能登入執行個體，而且運運算元IP必須包含在安全性區域中定義的位址或位址集中。 安全性區域設定是在Adobe Campaign伺服器的設定檔案中執行。

運運算元會從其在主控台中的設定檔連結至安全性區域，可在&#x200B;**[!UICONTROL Administration > Access management > Operators]**&#x200B;節點中存取。

>[!NOTE]
>
>Adobe以「受管理的Cloud Services」使用者的身分為您設定安全性區域。 如需詳細資訊，[請連絡Adobe](https://helpx.adobe.com/tw/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}。

**了解更多**

* [內建已命名許可權](../start/gs-permissions.md)

* [設定許可權的步驟](../start/manage-permissions.md)
