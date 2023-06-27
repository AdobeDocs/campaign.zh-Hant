---
title: Campaign v8 早期發行說明
description: 早期 Campaign v8 版本
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: 9736ebb3d2a60bfe23b135318b899acb657a580c
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 20%

---

# 早期發行說明 {#e-new-release}

本頁介紹了下一個 Campaign v8 版本中包含的改善及修正。在發行日期前，此內容可能會有所變更，恕不另行通知。 本[頁面](../start/release-notes.md)提供正式發行說明。

## 發行版本 8.5 {#release-8-5}

_2023年6月30日_

**有哪些新功能？**

<table> 
<thead>
<tr> 
<th> <strong>增強推播通知服務</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>Campaign 8.5隆重推出我們在v8的最新推播通知服務，並以現代尖端技術為基礎打造的強大架構為後盾。 此服務旨在解鎖全新等級的擴充性，確保您的通知能夠以順暢的效率觸及更多對象。 透過我們增強的基礎架構和最佳化程式，您可以期待更龐大的規模和可靠性，讓您以前所未有的方式與行動應用程式使用者互動和交流。 此功能僅適用於選取的客戶群組（可用性限制）。</p>
</td> 
</tr> 
</tbody> 
</table>

**相容性更新**

* 32位元版本的使用者端主控台現已棄用。 從 8.6 版本開始，用戶端主控台將僅以 64 位元提供。使用者端主控台升級至64位元版本相當順暢。 深入了解如何升級作業系統，請參閱此[技術說明](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/console.html?lang=zh-Hant)。
* 您現在可以將Campaign v8執行個體連線至Azure synapse外部資料庫。 此連線透過新的外部帳戶進行管理。

**功能改進**

* 透過實施一系列最佳化，SMS吞吐量已大幅提升，進而改善SMS通訊的速度和效率。
* 從Campaign v8.5開始，已改善Campaign v8的驗證流程。 技術操作員必須使用AdobeIdentity Management系統(IMS)來連線至Campaign。
* 您現在可以善用目的地和來源連線來同步設定檔屬性，例如Adobe Experience Platform和Campaign v8資料庫之間的選擇退出資料
* 已最佳化傳遞準備。
* 已為SFTP外部帳戶新增基於金鑰的驗證選項，以及現有的使用者/密碼驗證方法。 使用者現在可以使用私密金鑰安全地驗證，增強安全性並為SFTP存取提供替代驗證機制。

**安全性改善功能**

* 您無法再從使用者端主控台建立運運算元。 您現在需要使用Admin Console。 [了解更多](../start/gs-permissions.md)。
* 已更新數個協力廠商工具，以最佳化安全性。

**修補程式**

* 修正可能導致傳遞的HTML內容中的特殊字元在數個瀏覽器中編碼錯誤的問題。 (NEO-60081)
* 修正無法在Campaign v8企業(FFDA)部署中儲存報表的問題。 (NEO-56836)
* 修正透過更新資料工作流程活動將資料插入或更新至自訂FFDA結構描述時的問題。 (NEO-54708)
* 修正資料庫清理工作流程無法移除FFDA上nms：address表格中的位址的問題。 (NEO-54460)
* 修正計費工作流程可能因「編譯記憶體耗盡」錯誤而失敗的問題。 (NEO-51137)
* 修正了GPG解密在資料載入（檔案）工作流程活動中無法正常運作的問題。 (NEO-50257)
* 修正使 `JSPContext.sqlExecWithOneParam` 函式無法運作的問題。 (NEO-50066)
* 修正在個人化欄位中使用無法列印的字元時，導致傳送失敗的問題。 (NEO-48588)
* 修正插入Adobe Target動態影像時，可能導致傳送錯誤的問題。 (NEO-62689)
* 修正在傳送中使用條件式內容時，瀏覽器無法新增額外空格的問題。 (NEO-62132)
* 修正在電子郵件內容編輯器中按一下影像時，導致快顯視窗開啟的問題。 (NEO-60752)
* 修正在編輯傳遞內容時，可能導致錯誤並妨礙您捲動的問題。 (NEO-61364)