---
product: campaign
title: 技術檔案 — Adobe Campaign - Apache版本安全性更新
description: Adobe Campaign - Apache版本安全性更新
exl-id: 68e42fe4-7fb6-4b53-9f39-e77374e3753d
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---

# Adobe Campaign - Apache版本安全性更新 {#apache-update}

>[!CAUTION]
>本文適用於：Campaign Classicv7受管理的Cloud Services客戶、Campaign v8客戶和Campaign Standard客戶。

Adobe Campaign可與協力廠商工具搭配使用，產品相容性將定期更新，以僅實施所支援的版本，並受益於最新的修正和改良。

Adobe Campaign內含Apache Tomcat，可透過HTTP作為應用程式伺服器的進入點，並與Apache Web Server整合。 Apache Software Foundation已發行Apache HTTP Server 2.4.53。此版本解決可能允許遠端攻擊者控制受影響系統的漏洞。 進一步瞭解 [Apache 2.4.53發佈](https://downloads.apache.org/httpd/Announcement2.4.html){target="_blank"}.

Adobe Campaign團隊將透過以下方式進行Apache版本安全性升級活動 **2022年6月15日** 以緩解此Apache弱點，並讓您的執行個體環境更安全。 此升級適用於在易受攻擊的Apache HTTP Server版本上執行的所有Campaign Classic v7託管Cloud Services客戶、Campaign v8和Campaign Standard客戶。 如果您受到影響，Adobe已聯絡您，通知您有關此次升級的資訊。

此升級預計會在您正常營業時間以外自動執行，以便您繼續使用Campaign服務而不會造成任何中斷。

在升級您的生產執行個體之前，我們的團隊會先升級您的非生產執行個體。 由於這是Adobe擁有的自動升級程式，因此您不需要採取任何動作。 不過，如果您遇到任何問題，請聯絡 [Adobe客戶服務](https://experienceleague.adobe.com/?support-solution=Campaign#support).


>[!NOTE]
>此升級需要重新啟動Apache Web Server。 停機時間在下列時段內不會超過10分鐘。

## 常見問題集 {#apache-faq}

* **為什麼這是強制升級？**

   目前的Apache版本容易受到攻擊，並存在潛在的安全威脅。 請務必將Campaign執行個體升級至最新適用的Apache版本，以解決安全性風險。


* **哪些客戶是安全性升級的目標？**

   所有使用在舊版Apache上實作之Campaign環境的客戶，都會升級至最新適用的Apache版本。

* **預期的停機時間是多少？**

   預期停機時間少於10分鐘。

* **客戶是否需要執行任何安全性升級動作？**

   不需要採取任何動作，因為安全性升級會自動執行。

* **客戶需要執行哪些驗證？**

   此安全性升級不需要特定測試。 如果發現任何問題，請聯絡 [Adobe客戶服務](https://experienceleague.adobe.com/?support-solution=Campaign#support)


* **我可以請求變更排程安全性升級位置的日期/時間嗎？**

   由於這是安全性修正，強烈建議您調整至現有的排程。


如有任何其他問題，您可以聯絡 [Adobe客戶服務](https://experienceleague.adobe.com/?support-solution=Campaign#support).
