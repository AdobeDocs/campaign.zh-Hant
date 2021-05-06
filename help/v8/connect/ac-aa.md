---
solution: Campaign Classic
product: campaign
title: 與Campaign和Adobe Analytics合作
description: 瞭解如何與Campaign和Adobe Analytics合作
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
translation-type: tm+mt
source-git-commit: c2d066ca2f935455861c3d6747c9805c847f2e0d
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 3%

---

# 與Campaign和Adobe Analytics合作

## Experience Cloud Triggers

您可以使用Experience Cloud觸發器，使用管線連接Adobe Campaign和Adobe Analytics之間的資料。 管線會從您的網站擷取使用者的動作或觸發器。 放棄購物車是觸發的範例。 觸發器會在Adobe Campaign處理，以便近乎即時地傳送電子郵件。

:speech_balloon:身為受管理的Cloud Services使用者，[連絡Adobe](../start/support.md#support)以使用促銷活動實施Experience Cloud觸發。

## Adobe Analytics 資料連接器

若要更新新的整合

您也可以設定「Adobe Analytics資料連接器」以整合「促銷活動」和「分析」。

資料連接器(先前稱為Adobe Genesis)可讓Adobe Campaign和Adobe Analytics透過&#x200B;**Web Analytics連接器**&#x200B;套件進行互動。 此整合會將資料從Analytics共用至Campaign，做為與電子郵件後使用者行為相關的區段。 相反地，它會將Adobe Campaign傳送的電子郵件促銷活動的指標和屬性傳送至Adobe Analytics-資料連接器。

有了這些整合，Adobe Campaign可以復原行銷促銷活動後一或多個網站的訪客行為資料，並（分析後）執行再行銷促銷活動，以便將其轉換為購買者。 相反地，網頁分析工具讓Adobe Campaign能夠將指標和促銷活動屬性轉送至其平台。

每個工具的操作欄位如下：

* Adobe Analytics:

   * 標誌著與Adobe Campaign一起推出的電子郵件宣傳
   * 以區段的形式儲存收件者在點按促銷活動電子郵件後所瀏覽之網站上的行為。 區段與放棄的產品（已檢視但未新增至購物車或購買的產品）、購買或購物車放棄有關。

* Adobe Campaign:

   * 將指標和促銷活動屬性傳送至連接器，接著連接器會將它們轉送至網頁分析工具
   * 恢復和分析段
   * 觸發重新行銷促銷活動

請參閱https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/adobe-analytics-data-connector.html?lang=en#technical-workflows-of-web-analytics-processes

:speech_balloon:身為受管理的Cloud Services使用者，[連絡Adobe](../start/support.md#support)以整合Adobe Analytics資料連接器與促銷活動。

