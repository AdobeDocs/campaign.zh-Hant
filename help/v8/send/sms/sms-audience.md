---
title: 簡訊選取對象
description: 瞭解如何設定SMS傳送的對象
feature: SMS
role: User
level: Beginner, Intermediate
source-git-commit: 24a6d56a79995cd0113d8438d1bd3314a3872e35
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 1%

---


# 選取SMS傳送的對象 {#sms-audience}

在選取您的對象之前，[在此瞭解更多有關對象的資訊](../../audiences/gs-audiences.md)。

在大多數情況下，傳遞的主要目標會從Adobe Campaign資料庫（預設模式）擷取。 不過，閱聽眾也可以儲存在外部檔案中。 [在本章節了解更多資訊](#external-audience)。

## Adobe Campaign中的受眾

若要選取您傳送的對象，請遵循下列步驟：

1. 在傳遞編輯器中，按一下&#x200B;**[!UICONTROL To]**&#x200B;連結。 您將會開啟&#x200B;**[!UICONTROL Select target]**&#x200B;視窗

1. 由於對象儲存在Adobe Campaign資料庫中，請在&#x200B;**[!UICONTROL Main target]**&#x200B;索引標籤中選擇&#x200B;**[!UICONTROL Defined in the database]**&#x200B;選項。

   ![](assets/audience_to.png){zoomable="yes"}

1. 在下拉式清單中選取&#x200B;**[!UICONTROL Target mapping]**。 Adobe Campaign預設目標對應是收件者，根據&#x200B;**[!UICONTROL nms:recipient]**&#x200B;結構描述。

   有其他目標對應可供使用，其中一些可能與您的特定設定相關。 如需目標對應的詳細資訊，請參閱[使用目標對應](../../audiences/target-mappings.md)。

1. 按一下&#x200B;**[!UICONTROL Add]**&#x200B;按鈕以定義限制篩選器。

   然後，您可以選取要套用的篩選型別：

   ![](assets/audience_filters.png){zoomable="yes"}

   若要使用目標型別，請選取它並按一下&#x200B;**[!UICONTROL Next]**&#x200B;按鈕。

   以下是預設提供的目標型別：

   * **[!UICONTROL Filtering conditions]**：可讓您定義查詢並顯示結果。
   * **[!UICONTROL A list of recipients]**：可讓您選取您準備的包含對象清單
   * **[!UICONTROL A recipient]**：讓您直接在表格中選取收件者。
   * **[!UICONTROL Recipients included in a folder]**：讓您在瀏覽器導覽樹狀結構中選取資料夾
   * **[!UICONTROL Recipients of a delivery]**：可讓您選取先前傳遞的對象
   * **[!UICONTROL Recipients of deliveries belonging to a folder]**：可讓您選取指定資料夾中所有傳送的對象
   * **[!UICONTROL Subscribers of an information service]**：此選項可讓您選取收件者必須訂閱的Newsletter，才能由正在建立的傳遞定位。
   * **[!UICONTROL User filters]**：可讓您使用預先定義的篩選器。

   選項&#x200B;**[!UICONTROL Exclude recipients from this segment]**&#x200B;可讓您鎖定不符合已定義之目標條件的收件者。 若要使用此選項，請選取適當的方塊，然後套用定位（如先前所定義）以排除產生的設定檔。

1. 在標籤欄位中輸入對象名稱，然後按一下&#x200B;**[!UICONTROL Finish]**&#x200B;按鈕以驗證對象。

   ![](assets/audience_finish.png){zoomable="yes"}

   您可以視需要新增目標母體，只要再按一下&#x200B;**[!UICONTROL Add]**&#x200B;按鈕即可。 您也可以按一下標籤後方的十字以刪除部分標籤。

## 外部檔案中的對象 {#external-audience}

您可以使用Adobe Campaign傳送不在資料庫中，但位於外部檔案中的傳送給對象。

以下是此專案的步驟：

1. 在傳遞編輯器中，按一下&#x200B;**[!UICONTROL To]**&#x200B;連結。 您將會開啟&#x200B;**[!UICONTROL Select target]**&#x200B;視窗

1. 選取 **[!UICONTROL Defined in an external file]** 選項。

   ![](assets/audience_externalfile.png){zoomable="yes"}

1. 依預設，收件者會匯入資料庫中。 在這種情況下，您需要選取&#x200B;**[!UICONTROL Target mapping]**。 如需目標對應的詳細資訊，請參閱[使用目標對應](../../audiences/target-mappings.md)。

   否則，您也可以選擇&#x200B;**[!UICONTROL Do not import the recipients into the database]**。

1. 匯入檔案時，按一下&#x200B;**[!UICONTROL File format definition…]**&#x200B;連結以選取並設定外部檔案。

1. 按一下&#x200B;**[!UICONTROL Finish]**&#x200B;按鈕以驗證您的對象。
