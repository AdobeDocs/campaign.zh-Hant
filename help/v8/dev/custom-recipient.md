---
title: 更改預設收件人表
description: 瞭解如何使用自定義收件人表
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

Adobe Campaign有一個內置的配置式表： **nms收件人**。 此表包含許多可輕鬆擴展的預定義欄位和表。 瞭解有關此表的詳細資訊，請參閱 [此頁](datamodel.md#ootb-profiles)。

內置表擴展提供了靈活性，但不允許刪除一些未使用的欄位或連結。 因此，當您的資料模型與「市場活動」內置的收件人表結構有顯著差異時，或者您擁有大量配置檔案時，使用自定義收件人表可能是一個不錯的選擇。  但是，這種方法在實施時需要一定的注意。

![](../assets/do-not-localize/book.png) 瞭解如何將實例配置為使用中的自定義收件人表 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/use-a-custom-recipient-table/about-custom-recipient-table.html){target=&quot;_blank&quot;}。