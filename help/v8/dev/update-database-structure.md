---
title: 更新資料庫結構
description: 更新資料庫結構
feature: Configuration
role: Developer
level: Intermediate, Experienced
exl-id: fc64f3ca-67f1-47b7-b154-9c9dd044192c
TQID: 'https://experienceleague.adobe.com/1UBvvvkN-05BqOe4aOMpYFtKEMp0Yf-q9ECtbtmHzb0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: a14877cc-63b1-41d9-bf0b-5f97cadd0417
    internal-label: Configuration guidelines
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 0%
---
# 更新資料庫結構 {#updating-the-database-structure}

若要套用對結構描述所做的修改，請啟動資料庫更新精靈。 此助理可以透過&#x200B;**[!UICONTROL Tools > Advanced > Update database structure]**&#x200B;存取。 它會檢查資料庫的實體結構是否符合其邏輯描述，並執行SQL更新指令碼。

![](assets/schema_update.png)

資料庫中的模組會自動填入並啟動。

![](assets/schema_update_select2.png)

請依照下列步驟操作，並檢視資料庫更新SQL指令碼：

![](assets/schema_update2.png)

>[!NOTE]
>
>這是編輯欄位，可以修改以刪除或新增SQL程式碼。

接下來，啟動資料庫更新：

![](assets/schema_update3.png)
