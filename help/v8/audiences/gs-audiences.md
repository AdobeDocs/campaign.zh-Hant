---
title: 開始使用Campaign中的設定檔和對象
description: 瞭解如何在Campaign中建立和管理設定檔和對象
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 43483085-8aa6-47e6-89e7-9211e37beaa4
version: Campaign v8, Campaign Classic v7
source-git-commit: 050612f6d7ab20aed5880454eec9cfc6e5fc18c2
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 20%

---

# 開始使用輪廓和客群{#gs-profiles-and-audiences}

設定檔是儲存在Campaign資料庫中的聯絡人，例如客戶、服務的訂閱者或潛在客戶。 要取得輪廓來建立此資料庫，有許多可行的機制：透過網路表單線上收集、手動或自動匯入文字檔、透過公司資料庫或其他資訊系統進行複寫。透過Adobe Campaign，您可以將行銷記錄、購買資訊、偏好設定、CRM資料以及任何相關的PI資料整合在整合檢視中，以進行分析並採取行動。 設定檔包含鎖定目標、確認及追蹤個人所需的所有資訊。

設定檔是&#x200B;**nmsRecipient**&#x200B;資料表中的記錄或儲存所有設定檔屬性的外部資料表，例如名字、姓氏、電子郵件地址、Cookie ID、客戶ID、行動識別碼或與特定頻道相關的其他資訊。 連結至收件者表格的其他表格包含設定檔相關資料，例如傳送記錄表格，其中包含傳送給收件者的所有傳送記錄。 在[本節](../dev/datamodel.md#ootb-profiles)中進一步瞭解內建設定檔和收件者表格。

![](assets/recipients-in-explorer.png)

在Adobe Campaign中，**位收件者**&#x200B;是傳送內容（電子郵件、簡訊等）時定位的預設設定檔。

儲存在資料庫中的收件者資料可讓您篩選將接收任何指定傳遞的目標，並在傳遞內容中新增個人化資料。 資料庫中還存在其他類型的輪廓。這些用戶檔案是針對不同用途設計的。例如，種子輪廓用於在內容傳送給最終目標前測試內容。

若要將設定檔資料填入Adobe Campaign中，您可以：

* 從外部資料來源（例如CRM系統或一般檔案）[匯入資料檔案](../start/import.md)
* [建立網路表單](../dev/webapps.md)，讓客戶輸入自己的資訊並建立自己的設定檔
* [對應到儲存設定檔的外部資料庫](../connect/fda.md)
* 在「使用者端主控台」中手動輸入設定檔，如下所示：

![](assets/create-profile.png)

匯入後，您可以建立對象以傳送訊息。 在本節[中瞭解如何建立對象](create-audiences.md)。