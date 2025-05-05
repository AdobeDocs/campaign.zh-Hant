---
title: 在Campaign中建立測試設定檔
description: 瞭解如何在Adobe Campaign中建立和管理測試設定檔
feature: Audiences, Profiles, Seed Address, Proofs
role: User
level: Beginner
exl-id: 878b5963-100c-4dd7-97a0-c59a62c493b1
source-git-commit: 70af3bceee67082d6a1bb098e60fd2899dc74600
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 1%

---

# 建立和管理測試輪廓 {#create-test-profiles}

## 什麼是種子地址？ {#gs-seeds}

測試輪廓為種子地址。它們用於鎖定不符合所定義目標條件的收件者。 種子地址可讓您透過傳送校樣，在傳送傳遞之前預覽和測試個人化和轉譯。

種子地址的優點如下：

* 使用從收件者設定檔中取得的資料隨機替代欄位：例如，您可以在種子地址區段中僅輸入電子郵件地址，並讓Campaign自動填寫設定檔的其他欄位。 深入瞭解[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html?lang=zh-Hant){target="_blank"}。
* 使用具有資料管理功能的工作流程時，可在種子地址層級輸入傳送中處理的其他資料，以強制執行值：這可作為隨機值替代的另一做法。
* 系統會自動從下列傳遞統計資料的報表中排除種子地址： **[!UICONTROL Clicks]**、**[!UICONTROL Opens]**、**[!UICONTROL Unsubscriptions]**。

種子地址會透過匯入或直接在傳遞或行銷活動中建立來新增到傳遞的目標中。

>[!NOTE]
>
>種子地址不會建立在收件人表格中，而是會在單獨的表格中。 如果您使用新資料擴充收件者表格，則必須使用相同資料擴充種子地址表格。 否則，種子地址不會考慮這些擴展欄位。
>
>[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html?lang=zh-Hant){target="_blank"}中提供了如何擴充種子位址表格的範例。

## 建立種子地址

種子位址不是透過標準設定檔和目標來管理，而是在Adobe Campaign Explorer的專用節點中： **[!UICONTROL Resources > Campaign management > Seed addresses]**。 您可以建立子資料夾來組織種子地址。

Adobe Campaign也可讓您建立種子地址範本，這些範本會匯入至傳遞或行銷活動中，並根據相關傳遞和行銷活動的特定需求進行調整。 請參閱[建立種子地址範本](#creating-seed-address-templates)。

### 定義地址 {#defining-addresses}

若要建立種子地址，請執行下列步驟：

1. 按一下種子地址清單上方的&#x200B;**[!UICONTROL New]**&#x200B;按鈕。
1. 從&#x200B;**[!UICONTROL Recipient]**&#x200B;索引標籤的相符欄位中，輸入連結到位址的資料。 可用欄位與傳送收件者（nms：recipient表格）之設定檔中的標準欄位相對應：名稱、名字、電子郵件等。

   >[!NOTE]
   >
   >地址的標籤會自動填入您定義的姓氏和名字。
   >
   >建立種子地址時，不需要輸入每個標籤的所有欄位。 在傳遞分析期間隨機輸入缺少的個人化元素。

1. 在&#x200B;**[!UICONTROL Address fields]**&#x200B;索引標籤中，於&#x200B;**[!UICONTROL nms:broadLog]**&#x200B;表格中輸入分析階段期間要插入傳遞記錄中的值。

1. 在&#x200B;**[!UICONTROL Additional data]**&#x200B;索引標籤中，輸入用於資料管理工作流程中所建立傳遞的個人化資料，以及您想要指派特定值的對象。

   請確定已在&#x200B;**[!UICONTROL Enrichment]**&#x200B;工作流程活動中定義其他目標資料，且別名的開頭為&#39;@&#39;。 否則，您將無法在傳送活動中正確搭配種子地址使用。

### 建立種子地址範本 {#creating-seed-address-templates}

您可以建立地址範本，這些範本可針對每次傳遞匯入和修改。 此程式與定義新種子地址時的程式相同。 唯一的區別是種子地址範本地址必須儲存在「範本」型別資料夾中。

### 直接郵件傳遞的種子地址 {#direct-mail-seed-addresses}

針對[直接郵件傳遞](../send/direct-mail.md)，種子地址會在擷取期間新增，並在輸出檔案中進行混合。

如果是直接郵件傳送，解壓縮檔案格式必須符合下列限制：

* 它不得使用選項&#x200B;**[!UICONTROL Handle groupings (GROUP BY+HAVING)]**。

* 如果擷取元素集合，則這些欄位的種子地址將具有空值，除非選取了&#x200B;**[!UICONTROL Single row (expert user)]**&#x200B;選項。

## 在傳遞中新增種子地址{#seed-addresses-in-a-delivery}

若要新增傳遞的特定種子地址，請按一下&#x200B;**[!UICONTROL To]**&#x200B;連結，然後選取&#x200B;**[!UICONTROL Seed addresses]**&#x200B;標籤。

有三種可能的插入模式：

1. 輸入單一種子地址。  若要這麼做，請按一下&#x200B;**[!UICONTROL Add]**&#x200B;按鈕並定義位址列位的內容。 對每個位址重複此步驟。

1. 匯入[種子地址範本](#creating-seed-address-template)，並根據您的需求加以調整。 若要這麼做，請按一下&#x200B;**[!UICONTROL Import seed templates...]**&#x200B;連結，然後選取包含地址範本的資料夾。

   如有必要，在新增地址之後，您可以連按兩下它們，或按一下&#x200B;**[!UICONTROL Detail...]**&#x200B;按鈕以調整每個地址的內容。

1. 建立條件以動態選取要插入的控制位址。 若要這麼做，請按一下&#x200B;**[!UICONTROL Edit the dynamic condition...]**&#x200B;連結，然後輸入種子位址選取引數。 例如，您可以包含特定資料夾中包含的所有種子地址，或屬於您組織特定部門的種子地址。

   [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html?lang=zh-Hant){target="_blank"}中提供了這方面的範例。

對於傳送，您也可以自訂將位址插入解壓縮檔案的方式。 預設會依輸出檔案的排序順序插入，但您可以選擇在檔案結尾或開頭插入，或隨機插入主要目標的收件者之間。

## 在行銷活動中新增種子地址 {#seed-addresses-in-a-campaign}

若要新增種子地址至行銷活動的目標，請選取作業並按一下&#x200B;**[!UICONTROL Edit]**&#x200B;標籤。

按一下&#x200B;**[!UICONTROL Advanced campaign settings...]**&#x200B;連結，然後按一下&#x200B;**[!UICONTROL Seed addresses]**&#x200B;標籤。 從行銷活動中插入的種子地址會新增到行銷活動中每個傳遞的目標中。

## 種子地址和自訂表格 {#using-an-external-recipient-table}

如果傳送表格是外部表格，您將需要執行其他設定。 **[!UICONTROL nms:seedmember]**&#x200B;結構描述必須延伸。 索引標籤會新增至種子地址，以定義適當的欄位

在這種情況下，若要將種子地址新增到傳送中，請直接在比對索引標籤中輸入適當的欄位，或匯入地址範本。

<!--The **nms:seedMember** schema extension is [this section](../../configuration/using/seed-addresses.md).-->
