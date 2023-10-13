---
title: Campaign v8 早期發行說明
description: 早期 Campaign v8 版本
feature: Release Notes
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: e0ec2940db3120dc8fbfd17dd2f5083bbf31232c
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 33%

---

# 早期發行說明 {#e-new-release}

本頁介紹了下一個 Campaign v8 版本中包含的改善及修正。在發行日期前，此內容可能會有所變更，恕不另行通知。 本[頁面](../start/release-notes.md)提供正式發行說明。

## 發行版本8.5.1 {#release-8-5}

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
<td><p>Campaign 8.5.1隆重推出我們在v8最新的推播通知服務，並擁有以現代尖端技術為基礎的強大架構。 此服務旨在解鎖全新等級的擴充能力，確保您的通知能夠以順暢的效率觸及更廣泛的對象。 透過我們增強的基礎架構和最佳化程式，您可以期待更大規模且更可靠的服務，讓您以前所未有的方式與行動應用程式使用者互動和交流。 此功能僅適用於選取的客戶群組（可用性限制）。</p>
</td> 
</tr> 
</tbody> 
</table>

**相容性更新**

* 使用者端主控台的32位元版本現已棄用。 從 8.6 版本開始，用戶端主控台將僅以 64 位元提供。使用者端主控台可順暢升級至64位元版本。 深入了解如何升級作業系統，請參閱此[技術說明](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/console.html?lang=zh-Hant)。
* 您現在可以將Campaign v8執行個體連線至Azure synapse外部資料庫。 此連線透過新的外部帳戶進行管理。

**功能改進**

* 透過實施一系列最佳化，SMS吞吐量已大幅提升，導致SMS通訊的速度和效率改善。
* 從Campaign v8.5.1開始，已改善Campaign v8的驗證流程。 技術操作員必須使用AdobeIdentity Management系統(IMS)來連線至Campaign。
* 您現在可以善用目的地和來源連線來同步設定檔屬性，例如Adobe Experience Platform和Campaign v8資料庫之間的選擇退出資料
* 已最佳化傳遞準備。
* 除了現有的使用者/密碼驗證方法之外，還為SFTP外部帳戶新增了金鑰型驗證選項。 使用者現在可以使用私密金鑰安全地驗證，增強安全性並為SFTP存取提供替代驗證機制。

**安全性改善功能**

* 您無法再從使用者端主控台建立運運算元。 您現在需要使用Admin Console。 [了解更多](../start/gs-permissions.md)。
* 已更新數個協力廠商工具，以最佳化安全性。

**修補程式**

* 已修正可能導致傳遞的 HTML 內容中的特殊字元在數種瀏覽器中編碼錯誤的問題。 (NEO-60081)
* 修正了無法在Campaign v8企業(FFDA)部署中儲存報表的問題。 (NEO-56836)
* 修正透過更新資料工作流程活動將資料插入或更新至自訂FFDA結構描述中的問題。 (NEO-54708)
* 修正資料庫清理工作流程無法移除FFDA上nms：address表格中的位址的問題。 (NEO-54460)
* 修正計費工作流程可能因「編譯記憶體耗盡」錯誤而失敗的問題。 (NEO-51137)
* 修正了GPG解密在資料載入（檔案）工作流程活動中無法正常運作的問題。 (NEO-50257)
* 修正使 `JSPContext.sqlExecWithOneParam` 函式無法運作的問題。 (NEO-50066)
* 修正在個人化欄位中使用無法列印的字元時，導致傳送失敗的問題。 (NEO-48588)
* 修正插入Adobe Target動態影像時，可能導致傳送錯誤的問題。 (NEO-62689)
* 已修正瀏覽器使用傳遞中的條件式內容時，無法新增額外空格的問題。 (NEO-62132)
* 已修正在電子郵件內容編輯器中按一下影像時，造成快顯視窗開啟的問題。 (NEO-60752)
* 已修正可能導致發生錯誤，以及讓您無法在編輯傳遞內容時進行捲動的問題。 (NEO-61364)
