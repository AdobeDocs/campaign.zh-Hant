---
product: campaign
title: 編輯結構描述
description: 進一步瞭解編輯結構描述工作流程活動
feature: Workflows, Targeting Activity
role: User, Developer
version: Campaign v8, Campaign Classic v7
exl-id: 16fb1aa5-cf99-4461-a1a4-7a68d97e2a74
TQID: 'https://experienceleague.adobe.com/uHsIfXEPlhLjwbGdRaUagbAhFhZb5JFxGurpSH4c0fI'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: ff84ab2f-a7c2-4ced-a3c8-5113f4348d99
    internal-label: Targeting Activity
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 3%
---
# 編輯結構描述{#edit-schema}



資料可以使用&#x200B;**[!UICONTROL Edit schema]**&#x200B;活動在工作流程中進行轉換、正規化及擴充（如有需要）。 它通常用於標準化資料結構：例如，您可以計算欄位或彙總的平均值，重新命名輸出欄或修改其內容。

此活動不會變更工作表中的資料，只會變更其結構描述，即資料的邏輯檢視。

![](assets/wf_manipulation_box.png)

您也可以透過&#x200B;**[!UICONTROL Links]**&#x200B;索引標籤建立與其他工作表的聯結。

![](assets/wf_manipulation_box_link_tab.png)

下方可讓您設定加入條件的清單，也就是用來協調兩個表格資料的准則。
