---
title: 在活動中開始使用個人資料和受眾
description: 瞭解如何建立和管理活動中的個人資料和受眾
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 43483085-8aa6-47e6-89e7-9211e37beaa4
source-git-commit: c316da3c431e42860c46b5a23c73a7c129abf3ac
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 9%

---

# 在活動中開始使用個人資料和受眾{#gs-profiles-and-audiences}

配置檔案是儲存在市場活動資料庫中的聯繫人，如客戶、服務或潛在客戶的訂戶。 獲取配置檔案和建立此資料庫的可能機制有很多：通過Web表單進行線上收集、手動或自動導入文本檔案、與公司資料庫或其他資訊系統進行複製。 使用Adobe Campaign，您可以將市場營銷歷史記錄、購買資訊、首選項、CRM資料和任何相關PI資料合併到一個合併視圖中，以進行分析和採取行動。 配置檔案包含針對、確認和跟蹤個人所需的所有資訊。

配置檔案是 **nms收件人** 表或外部表，它儲存所有配置檔案屬性，如名、姓、電子郵件地址、cookie ID、客戶ID、移動標識符或與特定渠道相關的其他資訊。 連結到收件人表的其他表包含與配置檔案相關的資料，例如，包含發送給收件人的所有交貨記錄的交貨日誌表。 瞭解有關中內置配置檔案和收件人表的詳細資訊 [此部分](../dev/datamodel.md#ootb-profiles)。

在Adobe Campaign, **收件人** 是用於發送遞送（電子郵件、SMS等）的預設配置檔案。 儲存在資料庫中的收件人資料使您能夠篩選將接收任何給定傳遞的目標，並在傳遞內容中添加個性化資料。 資料庫中還存在其他類型的用戶檔案。這些用戶檔案是針對不同用途設計的。例如，種子用戶檔案用於在內容傳送給最終目標前測試內容。


要用配置檔案資料填充Adobe Campaign，您可以：

* [導入資料檔案](../start/import.md) 從外部資料源（如CRM系統）
* [建立Web表單](../dev/webapps.md) 允許客戶輸入自己的資訊並建立自己的配置檔案
* [映射到外部資料庫](../connect/fda.md) 其中儲存配置檔案
* 在客戶端控制台中手動輸入配置檔案，如下所示：

![](assets/create-profile.png)

<!--You can also select your message audience in an external file: recipients are stored not in the database, but in files. These are known as “external” deliveries. These contacts can be imported or not in Adobe Campaign. [Learn more](external-profiles.md).-->
