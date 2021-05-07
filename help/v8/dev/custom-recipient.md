---
solution: Campaign
product: Adobe Campaign
title: 變更您的預設收件者表格
description: 瞭解如何使用自訂收件者表格
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 2%

---

# 使用自訂收件者表格{#gs-ac-custom-recipient}

Adobe Campaign有一個內置的配置檔案表：**nmsRecipient**。 此表格包含許多可輕鬆擴充的預先定義欄位和表格。 在[本頁](datamodel.md#ootb-profiles)中進一步瞭解此表。

內建表格擴充功能提供良好的彈性，但不允許移除某些未使用的欄位或連結。 因此，當您的資料模型與促銷活動內建的收件者表格結構顯著不同，或者您有大量的描述檔時，使用自訂收件者表格可能是個不錯的選項。  但是，這種方法在實施時需要一定的預防措施。

此功能使Adobe Campaign能夠處理來自外部資料庫的資料：此資料將用作一組傳送的描述檔。 實作此程式涉及限制，例如：

* 無更新串流進出Campaign Cloud資料庫：此表中的資料可以通過托管該表的資料庫引擎直接更新。
* 在現有資料庫上運行的進程需要是穩定的。
* 使用具有非標準結構的配置檔案資料庫：使用單個實例，將檔案傳遞到保存在各種結構的表中。

本節介紹映射Adobe Campaign現有表的關鍵點，以及基於任何表執行交付時要應用的配置設定。 此外，還介紹如何設計面向最終用戶的查詢介面。

>[!CAUTION]
>
>Adobe Campaign自訂僅保留給專家使用者。 它需要輸入表單和架構設計方面的專業知識。

