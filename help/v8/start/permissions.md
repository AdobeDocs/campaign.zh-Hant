---
title: 將權限授予Campaign v8
description: 了解如何授與Campaign v8的權限
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: 63b53fb6a7c6ecbfc981c93a723b6758b5736acf
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 7%

---

# 開始使用權限

在Adobe Campaign中，使用者為&#x200B;**operators**，而&#x200B;**運算元群組**&#x200B;代表使用者角色。

運算子是具有登入及執行動作權限的Adobe Campaign使用者。 預設情況下，運算子儲存在&#x200B;**[!UICONTROL Administration > Access management > Operators]**&#x200B;節點中。

Adobe Campaign隨附內建運算元群組，例如促銷活動管理員或工作流程監督者。 所有內建群組都列在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}中。

作為運算子組的成員，用戶具有執行操作的權限（稱為「命名權限」），並具有對資料的訪問權限，該資料包含在&#x200B;**Explorer**&#x200B;視圖中的資料夾中。 運算子可以是多個運算子組的成員：權限和存取權限可加入。

指定權限授予：

* 執行操作
例如，為**準備傳送**&#x200B;名為右的&#x200B;**傳送運算子**&#x200B;群組成員啟用傳送編輯器中的&#x200B;**分析**&#x200B;按鈕

* 資料夾存取權
操作員組的成員資格可以通過更改資料夾的安全設定來授予或限制對資料夾的訪問權限。 [在 Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder){target=&quot;_blank&quot;} 深入瞭解。例如，它可能會影響：**寫入訪問**&#x200B;以建立新實體（如傳遞、配置檔案等）,**讀取訪問**&#x200B;以使用實體，**刪除訪問**&#x200B;以刪除實體。

## 安全區域

每個運算子都需要連結到區域才能登錄到實例，並且運算子IP必須包含在安全區域中定義的地址或地址集中。 安全區配置在Adobe Campaign伺服器的配置檔案中執行。

操作員從控制台中的配置檔案連結到安全區域，可在&#x200B;**[!UICONTROL Administration > Access management > Operators]**&#x200B;節點中訪問。

![](../assets/do-not-localize/speech.png)  作為托管Cloud Services用戶，Adobe會為您設定安全區域。如需詳細資訊，請[連絡Adobe](https://helpx.adobe.com/tw/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target=&quot;_blank&quot;}。

**在 Campaign Classic v7 文件** 中深入瞭解

* [內建的命名權限](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html){target=&quot;_blank&quot;}

* [內建運算子群組](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}

* [設定權限](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html){target=&quot;_blank&quot;}的步驟
