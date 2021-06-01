---
product: Adobe Campaign
title: 更改預設收件人表
description: 了解如何使用自訂收件者表格
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 2%

---

# 使用自訂收件者表格{#gs-ac-custom-recipient}

Adobe Campaign隨附內建的設定檔表格：**nmsRecipient**。 此表格包含許多預先定義的欄位和表格，可輕鬆擴充。 在[此頁](datamodel.md#ootb-profiles)中了解有關此表的詳細資訊。

內建表格擴充功能提供彈性，但不允許移除某些未使用的欄位或連結。 因此，當您的資料模型與Campaign內建的收件者表格結構（或如果您有大量設定檔）有顯著差異時，使用自訂收件者表格可能是個不錯的選項。  但是，此方法在實施時需要一定的預防措施。

此功能可讓Adobe Campaign處理來自外部資料庫的資料：此資料將用作傳送的一組設定檔。 實作此程式涉及限制，例如：

* 沒有從Campaign Cloud資料庫進行資料流更新：可通過承載此表的資料庫引擎直接更新表中的資料。
* 在現有資料庫上運行的進程必須是穩定的。
* 使用具有非標準結構的配置檔案資料庫：可使用單一例項，以各種結構傳送至儲存在各種表格中的設定檔。

本節說明映射Adobe Campaign中現有表格的關鍵點，以及要套用以根據任何表格執行傳送的組態設定。 還介紹了如何為最終用戶設計查詢介面。

>[!CAUTION]
>
>Adobe Campaign自訂僅保留給專家使用者。 它需要輸入表單和架構設計方面的專業知識。

