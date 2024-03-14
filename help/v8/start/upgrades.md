---
title: Campaign版本和升級
description: 深入瞭解Campaign版本和升級
feature: Release Notes
role: User
level: Beginner
exl-id: 04bda36f-051f-41a3-84b3-6af3c5e34ab2
source-git-commit: a779f243b0ba13dc3fcb7839377ca8766e5f7841
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 14%

---

# 版本和升級 {#upgrades}

## Campaign版本 {#versions}

Adobe Campaign會定期發行產品版本，以改善Campaign基礎建設的效能、安全性、邏輯和可用性。

這些升級可以是：

* **重大升級**，從主要版本升級至其他版本，例如從v7升級至v8。 這些升級帶來了新功能、改進、相容性和安全性更新以及修正。
* **小幅升級**，從次要版本升級為其他版本，例如從v8.5到v8.6。這些升級帶來改進、相容性和安全性更新，以及修正。
* **修補程式升級**，從修補程式版本更新至其他版本，例如從v8.5.1到v8.5.2。這些升級包含安全性更新和修正。

有關每個新版本的詳細資訊，請參見 [發行說明](release-notes.md).

若要確保穩定設定，Adobe建議您安裝 **完全相同的版本** 在您所有的Campaign伺服器上。 此外，除 [發行說明](release-notes.md)，使用者端主控台必須開啟 **完全相同的版本** 做為伺服器執行個體。 瞭解如何升級您的使用者端主控台 [在此頁面中](../start/connect.md#upgrade-ac-console).

身為Campaign Managed Services客戶，當有新的Campaign版本可用時，您的基礎架構會由Adobe升級，無需採取任何進一步的動作。

請注意，身為客戶，您必須確保您使用 [相容性矩陣](compatibility-matrix.md).


## 常見問題集 {#upgrades-faq}

### 如何檢查我的Campaign版本？ {#version}

若要檢查您的Campaign版本，請存取 **「說明>關於……」** 使用者端主控台的功能表。

![](assets/ac-version.png)

您可存取下列資訊：

* 此 **版本** 使用者端主控台和應用程式伺服器的數目。 在上述範例中，使用者端主控台和應用程式伺服器的版本為8.1.5。
* 括弧之間的 SHA 編號。
* 聯絡 Adobe 客戶服務的連結.
* 導覽至 Adobe 隱私權政策、使用條款與 Cookie 政策的連結.

### 如何通知我新版本的發行？ {#upgrades-0}

新版本及其帶來的變更會列在 [發行說明](release-notes.md). 新版本可用後，Adobe將會與您聯絡並升級您的環境。

若要接收最新Experience Cloud解決方案發行版本的通知，請訂閱 [Adobe優先順序產品更新](https://www.adobe.com/tw/subscription/priority-product-update.html){target="_blank"}.

您也可以造訪 [Campaign社群](https://experienceleaguecommunities.adobe.com/t5/custom/page/page-id/Community-TopicsPage?style=all&amp;sort=date&amp;order=desc&amp;filters=adobe-campaign-classic-community&amp;topic=Campaign+v8){target="_blank"} 以取得版本更新的相關資訊。


### 我的組織為何需要此升級？ {#upgrades-1}

將您的基礎架構升級至最新版本，可確保您的帳戶免受漏洞的侵擾，並可使用更新的效能技術。

通常，升級至最新版本會帶來：

* 提升安全性

  安全性需要持續關注及主動維護。 安全風險無處不在，不容忽視：每次Campaign升級都能提高安全性。 這些升級必須套用至您的所有Campaign執行個體，以及使用者端主控台。 這些技術的組合讓Adobe Campaign能夠共同合作，創造價值。 所有這些技術都必須保持最新狀態？

* 改善的支援

  大部份的重大問題都可透過升級實際解決，並且可以避免。 定期升級可協助您減少所面臨的挑戰，並透過消除這些挑戰來提高效率。 客戶服務量會減少，以提高解決問題的速度，而且對於無關升級的問題將可獲得更多關注。


* 改善維護與穩定性

  Adobe Campaign團隊會持續找出方法改善產品的穩定性和效能，並修正已知問題。 升級可透過這些改善功能更新您的執行個體，並消除了快速成長的組織常見的挑戰和/或Campaign執行個體中的複雜性。您組織的行銷團隊和IT團隊都能感受到支援Campaign之技術棧疊的各項改善。


### 此升級的流程和時間表為何？ {#upgrades-2}

身為v8客戶，如果您的帳戶被認定需要升級至新版本，Adobe會直接通知您。

Adobe團隊將帶領並引導您的組織完成這個過程。 客戶服務代表、產品經理、工程師和 TechOps 專家以及產品顧問等專門的團隊，隨時樂意提供協助並確保順暢的體驗。
