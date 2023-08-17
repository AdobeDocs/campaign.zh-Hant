---
title: 授與Campaign v8的許可權
description: 瞭解如何授與Campaign v8的許可權
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: 1baeb8827a0eab4f9487bb5e5afe4d779e00efe4
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 5%

---

# 開始使用權限

在Adobe Campaign中，使用者為 **運運算元** 和 **運運算元群組** 代表使用者角色。

運運算元是有許可權登入及執行動作的Adobe Campaign使用者。 依預設，運運算元儲存在 **[!UICONTROL Administration > Access management > Operators]** 節點。

Adobe Campaign隨附內建運運算元群組，例如「行銷活動管理員」或「工作流程主管」。 進一步瞭解中的許可權 [本節](../start/gs-permissions.md)

作為操作員群組的成員，使用者有權執行稱為「已命名的許可權」的操作，並且有權存取包含在 **瀏覽器** 檢視。 運運算元可以是多個運運算元群組的成員：許可權和存取許可權是可相加的。

已命名的許可權會將許可權授予：

* 執行作業，例如 **分析** 傳遞編輯器中的按鈕已對以下專案中的成員啟動： **傳遞操作員** 擁有下列專案的群組： **準備傳遞** 已命名的右側

* 存取資料夾操作員群組的成員資格可以透過變更資料夾的安全性設定來授予或限制資料夾的存取權。 在[本頁](../start/folder-permissions.md)中瞭解更多。例如，它可能影響： **寫入許可權** 若要建立新實體（例如傳送、設定檔等）， **讀取許可權** 若要使用實體， **刪除存取權** 以刪除實體。

## 安全性區域

每個運運算元都必須連結到區域才能登入執行個體，而且運運算元IP必須包含在安全性區域中定義的位址或位址集中。 安全性區域設定是在Adobe Campaign伺服器的設定檔案中執行。

運運算元會從主控台中的設定檔連結至安全性區域，可在中存取 **[!UICONTROL Administration > Access management > Operators]** 節點。

![](../assets/do-not-localize/speech.png)  Adobe身為「受管理的Cloud Service」使用者，會為您設定安全性區域。 如需詳細資訊， [連絡人Adobe](https://helpx.adobe.com/tw/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}.

**了解更多**

* [內建已命名許可權](../start/gs-permissions.md)

* [設定許可權的步驟](../start/manage-permissions.md)
