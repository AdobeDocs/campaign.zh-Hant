---
product: campaign
title: 技術檔案 — Adobe Campaign - Apache版本安全性更新
description: Adobe Campaign - Apache版本安全性更新
hide: true
hidefromtoc: true
exl-id: 68e42fe4-7fb6-4b53-9f39-e77374e3753d
source-git-commit: 50dcdf1f6bcc8c8a195a0bf0a37af254f33b80d5
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Adobe Campaign - Apache版本安全性更新 {#apache-update}

>[!CAUTION]
>本文適用於： Campaign Classic v7 Managed Cloud Services客戶、Campaign v8客戶和Campaign Standard客戶。

Adobe Campaign可與第三方工具合作，產品相容性將定期更新，以僅實施所支援的版本，並受益於最新的修正和改良。

Adobe Campaign內含Apache Tomcat，可透過HTTP當做應用程式伺服器的進入點，並與Apache Web Server整合。 Apache Software Foundation已發行Apache HTTP Server 2.4.53。此版本解決可能允許遠端攻擊者控制受影響系統的漏洞。 在[Apache 2.4.53公告](https://downloads.apache.org/httpd/Announcement2.4.html){target="_blank"}中瞭解更多。

Adobe Campaign團隊將在&#x200B;**2022年6月15日**&#x200B;前執行Apache版本安全性升級活動，以減少此Apache弱點並使您的執行個體環境更安全。 此升級適用於所有Campaign Classic v7 Managed Cloud Services客戶、在Apache HTTP Server易受攻擊版本上執行的Campaign v8和Campaign Standard客戶。 如果您受到影響，Adobe已聯絡您，通知您有關此次升級的事宜。

此升級預計會在您正常營業時間以外自動執行，以便您繼續使用Campaign服務而不會造成任何中斷。

我們的團隊會先升級您的非生產執行個體，然後再升級您的生產執行個體。 由於這是Adobe所擁有的自動升級程式，因此您不需要採取任何動作。 不過，如果您發生任何問題，請連絡[Adobe客戶服務](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}。


>[!NOTE]
>此升級需要重新啟動Apache Web Server。 停機時間在下列時間範圍內不會超過10分鐘。
> 

## 常見問題集 {#apache-faq}

* **為什麼這是強制升級？**

  目前的Apache版本易受攻擊，並存在潛在的安全威脅。 請務必將Campaign執行個體升級至最新適用的Apache版本，以解決安全性風險。


* **哪些客戶是安全性升級的目標？**

  所有使用在舊版Apache上實作之Campaign環境的客戶，都會升級至最新適用的Apache版本。

* **預期的停機時間是多少？**

  預計停機時間少於10分鐘。

* **此安全性升級是否需要客戶採取任何動作？**

  不需要採取任何動作，因為安全性升級會自動執行。

* **客戶需要執行哪些驗證？**

  此安全性升級不需要任何特定測試。 如果發現任何問題，請聯絡[Adobe客戶服務](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}。


* **我可以要求變更排定的安全性升級位置的日期/時間嗎？**

  由於這是安全性修正，強烈建議您調整以符合現有的排程。


如有任何其他問題，請連絡[Adobe客戶服務](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}。
