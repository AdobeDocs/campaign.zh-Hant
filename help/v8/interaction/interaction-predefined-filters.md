---
title: Campaign互動提供預先定義的篩選器
description: 瞭解如何建立預先定義的篩選器
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 092262c7-768c-4e86-9b2b-c52516f6a030
TQID: 'https://experienceleague.adobe.com/XWkWbgrMASz-9FfrXC23tTwiw54oQH5U4iWM9fa2FDQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 4%
---
# 建立預先定義的篩選器{#creating-pre-defined-filters}

建立預先定義的篩選器，以定義目標群體的適用性規則，以便在建立優惠方案期間輕鬆重複使用。 它們是每個環境專屬的行為，並將優惠方案引數列入考量。

>[!NOTE]
>
>Adobe Campaign Web UI提供使用者易用的介面，讓您輕鬆管理和自訂預先定義的篩選器，以符合特定需求。 建立一次並儲存，即可供未來使用。 若要深入瞭解預先定義的Web UI篩選器，請參閱[Adobe Campaign Web UI檔案](https://experienceleague.adobe.com/zh-hant/docs/campaign-web/v8/start/predefined-filters){target=_blank}。


若要建立預先定義的篩選，請套用下列程式：

1. 瀏覽至&#x200B;**[!UICONTROL Administration]**&#x200B;資料夾並選取&#x200B;**[!UICONTROL Pre-defined offer filters]**。

   ![優惠方案 — 在「管理」下選取預先定義優惠方案篩選器節點的設計樹狀結構](assets/offer_filter_create_005.png)

1. 按一下 **[!UICONTROL New]**。

   ![預先定義的優惠方案篩選器清單，其中反白顯示[新增]按鈕，並列出[年齡]篩選器](assets/offer_filter_create_001.png)

1. 變更標籤，以便稍後識別篩選器。

   ![應用程式篩選器對話方塊，其[標籤]欄位設定為[電子郵件頻道]](assets/offer_filter_create_002.png)

1. 選取篩選條件將關注的欄位。

   ![Select運算式對話方塊，其中包含從收件者欄位中選擇的電子郵件欄位](assets/offer_filter_create_003.png)

1. 視需要選取運運算元和值，然後儲存查詢。

   ![運運算元設為的電子郵件運算式上的篩選條件不是空的](assets/offer_filter_create_004.png)

1. 按一下&#x200B;**[!UICONTROL Preview]**&#x200B;以檢視篩選結果。

   電子郵件通道篩選的![預覽索引標籤，列出符合篩選條件的收件者](assets/offer_filter_create_006.png)
