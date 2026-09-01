---
title: Campaign版本和升級
description: 深入瞭解Campaign版本和升級
feature: Release Notes
role: User
level: Beginner
exl-id: 04bda36f-051f-41a3-84b3-6af3c5e34ab2
TQID: https://experienceleague.adobe.com/EaoWEmt7vNplA6Cs6CdMvP-iwia6BkaDRjawsPoa6fs
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080bid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 59a1ad4bbb194222f0c2b86117cc7dc6ecc3335d
workflow-type: tm+mt
source-wordcount: 1190
ht-degree: 10%

---

# 版本和升級 {#upgrades}

Adobe Campaign v8是以&#x200B;**受管理的Cloud Services**&#x200B;解決方案獨家提供。 Adobe會為您管理和執行每個伺服器端升級 — 沒有內部部署或混合部署v8，也沒有伺服器升級可讓您自行排程或執行。

Adobe Campaign 會定期更新。 此定期更新的目的是為了讓您掌握最新、最佳的資訊，進而確保環境的安全，並改產品使用體驗。

以受管理的Cloud Services使用者身分：

* 您的Campaign伺服器執行個體會由Adobe隨著每個新版本自動升級，而不需要您採取任何動作。
* 在會影響您環境的升級之前，您的Adobe代表會與您聯絡。
* **您的使用者端主控台是您負責維持最新狀態的元件。** 它必須升級至與您的Campaign伺服器相同的版本。 透過[本頁](../start/connect.md#upgrade-ac-console)了解如何升級您的用戶端主控台。

此外，身為客戶，請確定您使用的是列於[相容性矩陣](compatibility-matrix.md)的最新受支援系統版本。

>[!IMPORTANT]
>
>Adobe保留隨時將重要安全性修補程式套用至託管環境的權利，恕不另行通知，以儘快修正漏洞。 部署這些修補程式時不會中斷服務。 修正重大漏洞的優先順序高於進階通知。

## Campaign版本 {#versions}

Adobe Campaign會定期發行產品版本，以改善Campaign基礎建設的效能、安全性、邏輯和可用性。

這些升級可以是：

* **重大升級**，從主要版本升級至其他版本，例如從v7升級至v8。 這些升級帶來了新功能、改進、相容性和安全性更新以及修正。
* **從次要版本升級至另一個次要版本**，例如從v8.5升級至v8.6。 這些升級帶來改進、相容性和安全性更新，以及修正。
* **修補程式升級**，從修補程式版本升級至其他版本，例如從v8.5.1升級至v8.5.2。 這些升級包含安全性更新和修正。

有關每個新版本的詳細資訊，請參閱[發行說明](release-notes.md)。 安全性相關修正會出現在每個版本的說明中 — 請參閱[如何通知我新版本的發行？](#upgrades-0) 底下。

若要確保穩定設定，Adobe建議您在所有的Campaign伺服器上安裝&#x200B;**完全相同的版本**。 此外，除在[發行說明](release-notes.md)中另有提及外，使用者端主控台必須使用&#x200B;**與伺服器執行個體完全相同的版本**。 透過[本頁面](../start/connect.md#upgrade-ac-console)了解如何升級您的用戶端主控台。

## 讓您的使用者端主控台保持最新狀態 {#ac-upgrades}

作為Campaign Managed Services客戶，當有新的Campaign版本可用時，您的伺服器基礎架構會由Adobe升級，您無需採取任何進一步的動作。

因為伺服器會自動進行升級，所以若未同時更新，您的&#x200B;**使用者端主控台**&#x200B;就會顯示間隙。 如果您的主控台版本不符合伺服器版本：

* 在更新主控台之前，您可能會失去連線至Campaign執行個體的能力。
* 您的主機停止受益於伺服器已移至的版本中隨附的修正和安全性更新，即使伺服器本身是最新版本。

若要避免此問題，請在收到新版本通知後立即升級使用者端主控台。 瞭解如何[升級您的使用者端主控台](../start/connect.md#upgrade-ac-console)。

請注意，身為客戶，您也必須確保使用[相容性矩陣](compatibility-matrix.md)所列之系統的最新支援版本。

## 常見問題集 {#upgrades-faq}

### 如何檢查我的Campaign版本？ {#version}

若要檢查您的Campaign版本，請從使用者端主控台存取&#x200B;**說明>關於……**&#x200B;功能表。

![](assets/ac-version.png)

您可存取下列資訊：

* 您的使用者端主控台和應用程式伺服器的&#x200B;**版本**&#x200B;編號。 在上述範例中，使用者端主控台和應用程式伺服器的版本為8.1.5。
* 括弧之間的 SHA 編號。
* 聯絡 Adobe 客戶服務的連結.
* 導覽至 Adobe 隱私權政策、使用條款與 Cookie 政策的連結.

>[!NOTE]
>
>如果顯示給使用者端主控台的版本與顯示給應用程式伺服器的版本不符，請依照[讓使用者端主控台保持最新狀態](#ac-upgrades)中的說明升級主控台。

### 如何通知我新版本的發行？ {#upgrades-0}

新版本及其帶來的變更（包括安全性修正）列於[發行說明](release-notes.md)。 新版本推出後，您的Adobe代表會與您連絡並升級您的伺服器環境；您將另外需要升級您的使用者端主控台（請參閱[讓您的使用者端主控台保持最新狀態](#ac-upgrades)）。

若要接收最新Experience Cloud解決方案發行版本及其內容的通知，請訂閱[Adobe優先產品更新](https://www.adobe.com/tw/subscription/priority-product-update.html){target="_blank"}通訊。

您也可以造訪[Campaign社群](https://experienceleaguecommunities.adobe.com/t5/custom/page/page-id/Community-TopicsPage?style=all&sort=date&order=desc&filters=adobe-campaign-classic-community&topic=Campaign+v8){target="_blank"}，以取得版本更新的相關資訊。

### 我的組織為何需要升級？ {#upgrades-1}

升級可確保您的帳戶免受漏洞的侵擾，並使用最新的效能技術。

通常，升級至最新版本會帶來：

* **已改善安全性**

  安全性需要持續關注及主動維護。 安全風險無處不在，不容忽視 — Campaign的每次升級都會提高安全性。 各種技術的組合可以共同支援Adobe Campaign，而且所有這些技術都必須保持最新狀態。 Adobe會自動將這些更新套用至您的伺服器；在步驟中升級您的使用者端主控台可確保對其提供相同的保護。

* **改善的支援**

  大多數關鍵問題都可透過升級解決，並可完全避免。 定期升級有助於減少您面臨的挑戰，並提高效率。 客戶服務量會減少，以提高解決問題的速度，而且對於無關升級的問題將可獲得更多關注。

* **改善的維護與穩定性**

  Adobe Campaign 團隊會持續找出方法改善產品穩定性及效能，並修正已知問題。 升級可透過這些改善功能更新您的執行個體，並消除了快速成長的組織常見的挑戰和/或Campaign執行個體中的複雜性。 您的行銷團隊和IT團隊都能感受到支援Campaign技術棧疊的各項改善。

* **保持連線**

  您的使用者端主控台只能與執行相同版本的伺服器可靠通訊。 讓您的主機保持最新狀態（每次伺服器升級時），就是讓此連線保持完整，以及隨之而來的安全性和修正。

### 升級的流程和時間表為何？ {#upgrades-2}

Adobe身為v8客戶，負責端對端管理您的伺服器升級：

1. 當有新版本可用，或您的帳戶被識別為需要移至新版本時，您的Adobe代表會通知您。
1. Adobe會升級您的伺服器基礎結構 — 此步驟不需要您採取任何動作。
1. 在您這邊，唯一需要的動作是升級您的使用者端主控台以符合要求，並且仍支援[相容性矩陣](compatibility-matrix.md)中的確認系統。 檢視[讓您的使用者端主控台保持最新](#ac-upgrades)。

客戶服務代表、產品經理、工程師、TechOps專家和產品顧問等專門的團隊，隨時樂意提供協助並確保順暢的體驗。

>[!NOTE]
>
>重要安全性修補程式可在此通知週期之外套用至您的託管環境 — 請參閱此頁面頂端的附註。
