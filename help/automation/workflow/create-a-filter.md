---
product: campaign
title: 建立篩選器
description: 瞭解如何在執行查詢時建立篩選器
feature: Query Editor, Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 8e6fd9b4-77c4-4af8-921b-c3fe104fa5bc
TQID: 'https://experienceleague.adobe.com/3EkEMTJs1-sdM9wSTYorHWO-emO3Nz5nugrWDU4h5pM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: f5293531-9312-4099-bfa3-9e67df6a8750
    internal-label: Query Editor
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 2%
---
# 建立篩選器 {#creating-a-filter}

Adobe Campaign中可用的篩選器是透過篩選條件來定義，這些條件是使用與在[查詢編輯器](../../v8/start/query-editor.md)中建立查詢時相同的作業模式建立的。

**[!UICONTROL Administration > Configuration > Predefined filters]**&#x200B;節點包含所有預設篩選器。 其中一些用於清單和概觀。 深入瞭解[內建預先定義的篩選器](../../v8/audiences/create-filters.md)。

例如，運運算元清單可由&#x200B;**[!UICONTROL Active accounts]**&#x200B;篩選：

![](assets/query_editor_filter_sample_1.png)

符合的篩選器包含對&#x200B;**[!UICONTROL Operators]**&#x200B;結構描述的&#x200B;**[!UICONTROL Account disabled]**&#x200B;值的查詢：

![](assets/query_editor_filter_sample_2.png)

對於相同的清單，**[!UICONTROL By login or label]**&#x200B;篩選器可讓您根據在篩選器欄位中輸入的值來篩選清單上的資料：

![](assets/query_editor_filter_sample_3.png)

其建置方式如下：

![](assets/query_editor_filter_sample_4.png)

若要符合篩選條件，運運算元帳戶必須勾選下列其中一個條件：

* 其標籤包含在輸入欄位中輸入的字元，
* 運運算元名稱包含輸入欄位中所輸入的字元。
* 說明區域的內容包含在輸入欄位中輸入的字元。

>[!NOTE]
>
>**[!UICONTROL Upper]**&#x200B;函式可讓您停用區分大小寫的函式。

**[!UICONTROL Taken into account if]**&#x200B;欄可讓您定義這些篩選條件的應用程式條件。 在此，**$(/tmp/@text)**&#x200B;字元代表連結至篩選的輸入欄位內容：

![](assets/query_editor_filter_sample_5.png)

在這裡，**$(/tmp/@text)=&#39;機構&#39;**

當輸入欄位不是空白時，**$(/tmp/@text)!=「**」運算式會套用每個條件。
