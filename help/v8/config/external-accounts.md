---
solution: Campaign Classic
product: campaign
title: 促銷活動外部帳戶
description: 促銷活動外部帳戶
feature: 概覽
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 0e0cd6eb9fcf656c9ba6c72cd1a782098f9399fe
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 13%

---

# 設定您的外部帳戶

Adobe Campaign 隨附一組預先定義的外部帳戶。為了與外部系統建立連接，您可以建立新的外部帳戶。

技術流程（例如技術工作流程或宣傳工作流程）會使用外部帳戶。例如，在工作流程中設定檔案傳輸或與任何其他應用程式(Adobe Target、Experience Manager等)進行資料交換時，您需要選取外部帳戶。

:arrow_upper_right:瞭解如何在[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/accessing-external-database/external-accounts.html)中建立和設定外部帳戶

特定外部帳戶管理Campaign本機資料庫與Cloud資料庫([!DNL Snowflake])之間的連線。

:speech_balloon:作為受管理的Cloud Services用戶，[!DNL Snowflake]外部帳戶是按Adobe配置的。

您可以訪問此外部帳戶來檢查設定並執行複製工作流。 若要執行此動作，請依照下列步驟：

1. 在促銷活動&#x200B;**[!UICONTROL Explorer]**&#x200B;中，按一下&#x200B;**[!UICONTROL Administration > Platform > External Accounts]**。

1. 選擇&#x200B;**[!UICONTROL Full FDA]**&#x200B;外部帳戶。

![](assets/snowflake-ext-account.png)

全局設定顯示在&#x200B;**[!UICONTROL General tab]**&#x200B;中。

使用&#x200B;**[!UICONTROL Parameters]**&#x200B;標籤，然後使用&#x200B;**[!UICONTROL Deploy functions]**&#x200B;按鈕來建立函式。

![](assets/snowflake-parameters.png)

**在此處添加參數**

使用&#x200B;**[!UICONTROL Full FDA]**&#x200B;頁籤強制執行複製工作流。

![](assets/snowflake-full-fda.png)

**在此處添加詳細資訊**

