---
title: 變更您的預設收件者表格
description: 瞭解如何使用自訂收件者表格
feature: Custom Resources, Profiles, Configuration
role: User, Developer
level: Intermediate, Experienced
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
TQID: 'https://experienceleague.adobe.com/W67Z2xVEBDpju5xlL2WiE5ZTzvrFmhuByMvfPb4x6nM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: a2002dba-5e37-4dff-8e04-1cc3ec73558c
    internal-label: Custom resources
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
    internal-label: Profiles
  - id: a14877cc-63b1-41d9-bf0b-5f97cadd0417
    internal-label: Configuration guidelines
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 3%
---
# 使用自訂收件者表格{#gs-ac-custom-recipient}

Adobe Campaign隨附內建的設定檔資料表： **nmsRecipient**。 此表格有許多預先定義的欄位和表格，可以輕鬆擴充。 在[此頁面](datamodel.md#ootb-profiles)中進一步瞭解此資料表。

內建表格擴充功能提供靈活性，但不允許移除某些未使用的欄位或連結。 因此，當您的資料模型與Campaign內建的收件者表格結構完全不同，或您有大量設定檔時，使用自訂收件者表格可能是很好的選項。  不過，此方法在實作時需要特別注意。

在[Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/use-a-custom-recipient-table/about-custom-recipient-table.html?lang=zh-Hant){target="_blank"}中瞭解如何設定您的執行個體以使用自訂收件者表格。