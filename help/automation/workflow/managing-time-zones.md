---
product: campaign
title: 管理時區
description: 管理時區
feature: Workflows, Configuration
role: User, Admin
version: Campaign v8, Campaign Classic v7
exl-id: 04b7638d-55dd-4317-b605-5d618ef014ba
TQID: 'https://experienceleague.adobe.com/M8aAiSm2KJdcKX0VuqX4NCIecbOm6u6B7xCvgs4bW-c'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
  - id: a14877cc-63b1-41d9-bf0b-5f97cadd0417
    internal-label: Configuration guidelines
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 4%
---
# 管理時區{#managing-time-zones}

Adobe Campaign可讓您管理同一個執行個體所關注的不同國家/地區之間的時間延遲。 套用的組態會在建立執行個體期間進行設定。

在工作流程中，您可以調整活動執行排程，並將特定時區連結至活動或整個工作流程。 此設定在匯入檔案時或是在傳送排程的架構中相當實用。

## 執行排程 {#execution-scheduling}

您可以使用排程器排程工作的執行（請參閱[排程器](scheduler.md)）。 您也可以使用提供此功能的活動中的可用排程選項。 這些活動提供&#x200B;**[!UICONTROL Schedule]**&#x200B;標籤： **[!UICONTROL File collector]**、**[!UICONTROL File transfer]**、**[!UICONTROL Web download]**、**[!UICONTROL Email reception]**&#x200B;與&#x200B;**[!UICONTROL SMS]**&#x200B;等。

對於所有已排程的工作（即具有排程選項的所有活動），您可以選取要套用的時區。 已透過相關活動的&#x200B;**[!UICONTROL Advanced]**&#x200B;索引標籤選取時區：

![](assets/wf-timezone-in-a-box.png)

可能的值包括：

* 伺服器時區

  使用Adobe Campaign應用程式伺服器的時區。

* 使用者時區

  使用執行工作流程的Adobe Campaign運運算元的時區。

* 資料庫時區

  使用所使用資料庫伺服器的時區。

* 特定時區

  使用選取的時區。

如果選取&#x200B;**[!UICONTROL By default]**&#x200B;值，則會套用工作流程的時區，否則會套用應用程式伺服器的時區。

## 將時區連結至活動 {#linking-a-time-zone-to-an-activity}

工作流程活動的&#x200B;**[!UICONTROL Advanced]**&#x200B;索引標籤可讓您選取其時區。 雖然在大部分時間中，工作流程的時區已經足夠，但是可能需要針對特定活動（例如資料匯入）一次又一次地讓時區超載，才能將日期連結到其正確的時區。
