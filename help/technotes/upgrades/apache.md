---
product: campaign
title: Technote - Adobe Campaign - Apache版本安全性更新
description: Adobe Campaign - Apache版本安全性更新
exl-id: 68e42fe4-7fb6-4b53-9f39-e77374e3753d
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---

# Adobe Campaign - Apache版本安全性更新 {#apache-update}

>[!CAUTION]
>本條適用於：Campaign Classicv7受管Cloud Services客戶、 Campaign v8客戶和Campaign Standard客戶。

Adobe Campaign與協力廠商工具搭配使用，而相容性會定期更新，以僅實作支援的版本，並受益於最新的修正和改善。

Adobe Campaign包含Apache Tomcat，可透過HTTP作為應用程式伺服器中的入口點，並與Apache Web伺服器整合。 Apache Software Foundation已發佈Apache HTTP Server 2.4.53。此版本解決了可能允許遠程攻擊者控制受影響系統的漏洞。 深入了解 [Apache 2.4.53公告](https://downloads.apache.org/httpd/Announcement2.4.html){target="_blank"}.

Adobe Campaign團隊將透過 **2022年6月15日** 以緩解此Apache漏洞，並讓您的執行個體環境更安全。 此升級適用於在有漏洞的Apache HTTP Server版本上執行的所有Campaign Classicv7受管Cloud Services客戶、Campaign v8和Campaign Standard客戶。 如果您受到影響，Adobe已與您聯絡，告知您此升級事宜。

此升級預計會在正常工作時間之外自動運行，以便您繼續使用Campaign服務，而不會中斷。

在升級您的生產執行個體之前，我們的團隊會先升級您的非生產執行個體。 由於這是Adobe擁有的自動升級程式，因此您不需要執行任何動作。 不過，如果您遇到任何問題，請聯絡 [Adobe客戶服務](https://experienceleague.adobe.com/?support-solution=Campaign#support).


>[!NOTE]
>此升級需要重新啟動Apache Web伺服器。 在下面提到的時段內，停機時間不會超過10分鐘。

## 常見問題集 {#apache-faq}

* **為什麼這是強制升級？**

   當前的Apache版本易受攻擊，並且存在潛在的安全威脅。 請務必將您的Campaign執行個體升級至最新適用的Apache版本，以解決安全性風險。


* **哪些客戶是安全升級的目標？**

   所有使用舊版Apache上實作之Campaign環境的客戶，都會升級至最新適用的Apache版本。

* **預期停機時間是多少？**

   預計停機時間不到10分鐘。

* **客戶是否需要執行此安全升級操作？**

   安全升級將自動運行，因此無需執行任何操作。

* **客戶需要運行哪些驗證？**

   此安全升級不需要特定測試。 若發現任何問題，請洽詢 [Adobe客戶服務](https://experienceleague.adobe.com/?support-solution=Campaign#support)


* **是否可以請求對計畫的安全升級插槽進行日期/時間更改？**

   由於這是安全性修正，強烈建議您調整以符合現有排程。


若有其他問題，您可以聯絡 [Adobe客戶服務](https://experienceleague.adobe.com/?support-solution=Campaign#support).
