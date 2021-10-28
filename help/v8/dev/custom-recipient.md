---
title: 更改預設收件人表
description: 了解如何使用自訂收件者表格
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 0b71c76b-03d9-4023-84fc-3ecc0df9261b
source-git-commit: 7234ca65f785b005b11851a5cd88add8cddeff4f
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 3%

---

# 使用自訂收件者表格{#gs-ac-custom-recipient}

Adobe Campaign隨附內建的設定檔表格： **nmsRecipient**. 此表格包含許多預先定義的欄位和表格，可輕鬆擴充。 進一步了解此表格，請參閱 [本頁](datamodel.md#ootb-profiles).

內建表格擴充功能提供彈性，但不允許移除某些未使用的欄位或連結。 因此，當您的資料模型與Campaign內建的收件者表格結構（或如果您有大量設定檔）有顯著差異時，使用自訂收件者表格可能是個不錯的選項。  但是，此方法在實施時需要一定的預防措施。

![](../assets/do-not-localize/book.png) 了解如何設定您的執行個體，以使用 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/use-a-custom-recipient-table/about-custom-recipient-table.html){target=&quot;_blank&quot;}。