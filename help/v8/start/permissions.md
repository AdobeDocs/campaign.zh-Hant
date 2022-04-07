---
title: 授予市場活動v8的權限
description: 瞭解如何授予市場活動v8的權限
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

在Adobe Campaign，用戶 **運算子** 和 **運算子組** 表示用戶角色。

操作員是具有登錄和執行操作權限的Adobe Campaign用戶。 預設情況下，運算子儲存在 **[!UICONTROL Administration > Access management > Operators]** 的下界。

Adobe Campaign還配備了內置運營商組，如「活動經理」或「工作流主管」。 所有內置組都列在 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}。

作為操作員組的成員，用戶有權執行名為「命名權限」的操作，並有權訪問包含在 **瀏覽器** 的子菜單。 運算子可以是多個運算子組的成員：權限和訪問權限是附加的。

命名權限授予：

* 執行操作例如， **分析** 按鈕 **交貨操作員** 具有 **準備交付** 右命名

* 訪問資料夾操作員組的成員資格可以通過更改資料夾的安全設定來授予或限制對資料夾的訪問權限。 [在 Campaign Classic v7 文件](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder){target=&quot;_blank&quot;} 深入瞭解。例如，它可能會影響： **寫入訪問** 建立新實體（如交貨、配置檔案等）, **讀取訪問** 使用實體， **刪除訪問權限** 的子菜單。

## 安全區域

每個操作員需要連結到區域才能登錄到實例，並且必須將操作員IP包括在安全區域中定義的地址或地址集中。 安全區域配置在Adobe Campaign伺服器的配置檔案中執行。

操作員從控制台中的配置檔案連結到安全區域，可在 **[!UICONTROL Administration > Access management > Operators]** 的下界。

![](../assets/do-not-localize/speech.png)  作為托管Cloud Services用戶，Adobe為您設定安全區域。 有關詳細資訊， [聯繫人Adobe](https://helpx.adobe.com/tw/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target=&quot;_blank&quot;}。

**在 Campaign Classic v7 文件** 中深入瞭解

* [內置命名權限](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html){target=&quot;_blank&quot;

* [內置運算子組](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;

* [設定權限的步驟](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html){target=&quot;_blank&quot;
