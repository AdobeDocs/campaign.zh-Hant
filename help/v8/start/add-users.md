---
title: 將權限授予Campaign v8
description: 了解如何授與Campaign v8的權限
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: ac4d0d0c16f429ca0948a3c3257558c46700baeb
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 7%

---

# 開始使用權限

在Adobe Campaign中，使用者為 **運算子** 和 **運算元組** 代表使用者角色。

運算子是具有登入及執行動作權限的Adobe Campaign使用者。 依預設，運算子會儲存在 **[!UICONTROL Administration > Access management > Operators]** 節點。

Adobe Campaign隨附內建運算元群組，例如促銷活動管理員或工作流程監督者。 所有內建群組均列於 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}。

作為運算元組的成員，用戶具有執行操作的權限（稱為「命名權限」），並且有權訪問資料，這些資料包含在 **瀏覽器** 檢視。 運算子可以是多個運算子組的成員：權限和存取權限可加入。

指定權限授予：

* 執行操作例如 **分析** 按鈕（在「傳送」編輯器中） **傳送運算子** 具有 **準備傳送** 已命名權限

* 對資料夾的訪問操作員組的成員資格可以通過更改資料夾的安全設定來授予或限制對資料夾的訪問權限。 [在 Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder){target=&quot;_blank&quot;} 深入瞭解。例如，它可能會影響： **寫入訪問** 建立新實體（例如傳送、設定檔等）, **讀取存取** 要使用實體， **刪除存取權** 刪除實體。

## 安全區域

每個運算子都需要連結到區域才能登錄到實例，並且運算子IP必須包含在安全區域中定義的地址或地址集中。 安全區配置在Adobe Campaign伺服器的配置檔案中執行。

運算子會從主控台的設定檔連結至安全區域，可在 **[!UICONTROL Administration > Access management > Operators]** 節點。

![](../assets/do-not-localize/speech.png)  作為托管Cloud Services用戶，Adobe會為您設定安全區域。 如需詳細資訊， [連絡Adobe](https://helpx.adobe.com/tw/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target=&quot;_blank&quot;}。

**在 Campaign Classic v7 文件** 中深入瞭解

* [內建的已命名權限](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html){target=&quot;_blank&quot;}

* [內建運算子組](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}

* [設定權限的步驟](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html){target=&quot;_blank&quot;}
