---
title: 使用目標對應
description: 了解如何使用和建立目標對應
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
source-git-commit: a41bebfeb352b2f81f81b46c39b5f9b64431455b
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 1%

---

# 使用目標對應{#gs-target-mappings}

依預設，傳遞範本目標為 **[!UICONTROL Recipients]**. 因此，其目標對應會使用 **nms:recipient** 表格。

您可以為傳送使用其他目標對應，或建立新的目標對應。

## 內建目標對應 {#ootb-mappings}

Adobe Campaign隨附下列內建的target對應：

| 名稱 | 用於 | 結構描述 |
|---|---|---|
| 收件者 | 傳送給收件者（內建的收件者表格） | nms:recipient |
| 訪客 | 傳送給已透過轉介（病毒式行銷）收集設定檔的訪客（例如）。 | mns:visitor |
| 訂閱 | 傳送給已訂閱資訊服務（例如電子報）的收件者 | nms:subscription |
| 訪客訂閱 | 傳送給已訂閱資訊服務的訪客 | nms:visitorSub |
| 運算子 | 傳送至Adobe Campaign運算子 | nms:operator |
| 外部檔案 | 透過包含傳送所需所有資訊的檔案傳送 | 沒有連結的架構，未輸入目標 |

## 建立目標對應 {#new-mapping}

您也可以建立目標對應。 例如，您可能需要新增自訂目標對應：

* 使用自訂收件者表格，
* 您可以設定篩選維度，此維度與目標對應畫面上的內建目標維度不同。

進一步了解自訂收件者表格，位於 [本頁](../dev/custom-recipient.md).

Adobe Campaign目標對應建立精靈可協助您建立使用自訂目標對應所需的所有結構。

1. 瀏覽至 **[!UICONTROL Administration]** `>` **[!UICONTROL Campaign Management]** `>` **[!UICONTROL Target mappings]** 從Adobe Campaign資源管理器。

1. 建立新的目標對應，並選取您的自訂結構作為目標維度。

   ![](assets/new-target-mapping.png)


1. 指定儲存設定檔資訊的欄位：姓氏、名字、電子郵件、地址等。

   ![](assets/wf_new_mapping_define_join.png)

1. 指定資訊儲存的參數，包括擴充功能結構的尾碼，以便輕鬆識別。

   ![](assets/wf_new_mapping_define_names.png)

   您可以選擇是否儲存排除項目(**排除記錄**)，含訊息(**broadlog**)或個別表格中。

   您也可以選擇是否管理此傳送對應的追蹤(**trackinglog**)。

1. 然後選取要考慮的擴充功能。 擴充功能類型取決於您的Campaign設定和附加元件。

   ![](assets/wf_new_mapping_define_extensions.png)

   按一下 **[!UICONTROL Save]** 啟動傳遞對應建立的按鈕：所有連結表都會根據所選參數自動建立。

