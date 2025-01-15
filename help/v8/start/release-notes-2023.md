---
title: Campaign v8 （主控台） 2023年發行說明
description: 2023 Campaign v8 版本隨附的功能與改進清單
feature: Release Notes
role: User
level: Beginner
exl-id: b860c843-155e-4abb-bdd6-b68dc7eaa0ee
source-git-commit: fe96eb65ac04fc2b89f0dfe1e8ed4286223c3f85
workflow-type: tm+mt
source-wordcount: '1496'
ht-degree: 56%

---

# 2023 年發行說明 {#2023-rn}

此頁面列出&#x200B;**2023 Campaign v8版本**&#x200B;的新功能、改善和修正。

>[!BEGINSHADEBOX]

**在此頁面**

* Campaign v8.5 - [版本8.5.1](#release-8-5-1) | [版本8.5.2](#release-8-5-2)
* Campaign v8.4 - [版本8.4.3](#release-8-4-3) | [版本8.4.4](#release-8-4-4) | [版本8.4.5](#release-8-4-5)

>[!ENDSHADEBOX]

## 發行版本 8.5.2 {#release-8-5-2}

_2023年8月2日_

修正升級至8.5.1時可能發生的安全性問題。 (NEO-64767)

## 發行版本 8.5.1 {#release-8-5}

_2023年6月30日_


**增強推播通知服務**

Campaign v8.5.1推出我們最新的推播通知服務，以現代尖端技術為基礎的強大架構提供支援。 此服務旨在解鎖全新等級的擴充能力，確保您的通知能夠以順暢的效率觸及更廣泛的對象。 透過我們增強的基礎架構和最佳化程式，您可以期待更大規模且更可靠的服務，讓您以前所未有的方式與行動應用程式使用者互動和交流。 此功能僅適用於選取的客戶群組（可用性限制）。

如需詳細資訊，請參閱[詳細說明文件](../send/push-data-collection.md)。


<table style="table-layout:fixed" text-align="bottom"><tr style="border: 0;">
<td>
<br/><img alt="改善輸送量" src="../start/assets/do-not-localize/improvements.jpeg">
<p>
</td>
<td>
<div>
<p><strong>行動裝置頻道增加的輸送量</strong></p>
<p>新推出的推播通知服務顯示推播Android和推播iOS的輸送量比先前的版本(v8.4)有重大改善。 最新版本(v8.5)的升級服務可讓使用者體驗到更優異的效能。 </p>
<ul>
<li>推播通知(Android)：快達<strong>5x</strong> </li>
<li>推播通知(iOS)：快達<strong>2.2x</strong></li>
</ul>
<p>SMS輸送量已透過一系列最佳化而大幅提升，導致SMS通訊的速度和效率顯著提高。 這些升級已導致從先前版本(v8.4)到最新版本(v8.5)的輸送量增加，包括傳送和意見更新兩者。 使用者現在可以體驗此增強型簡訊服務的好處。</p>
<ul>
<li>SMS輸送量：快達<strong>5x</strong></li>
</ul>
<p><em>這些最大輸送量效能是由Adobe測試團隊在實驗室條件下測量的。</em></p>
</div>
<p></p>
</td>
</tr></table>


**一般改善**

* 您現在可以利用Adobe Experience Platform目的地連線來同步設定檔屬性，例如Adobe Experience Platform與Campaign v8資料庫之間的選擇退出資料。
* 已針對所有管道進行傳遞準備最佳化。
* 除了現有的使用者/密碼驗證方法之外，還為SFTP外部帳戶新增了金鑰型驗證選項。 使用者現在可以使用私密金鑰安全地驗證，增強安全性並為SFTP存取提供替代驗證機制。 若要了解詳細資訊，請參閱[本章節](../config/external-accounts.md)。

**安全性改善功能**

* 使用Campaign v8.5.1時，Campaign v8的驗證程式已改善並安全。 技術操作員現在必須使用AdobeIdentity Management系統(IMS)來連線至Campaign。 透過[此技術說明](../../technotes/upgrades/ims-migration.md)了解如何移轉您現有的技術帳戶。
* 從即將推出的v8.6開始，您將無法再從Campaign使用者端主控台建立運運算元。 如果您使用登入/密碼原生驗證，您必須將操作員移轉至AdobeIdentity Management System (IMS)。 閱讀此[技術說明](../../technotes/upgrades/migrate-users-to-ims.md)，了解如何移轉操作者。
* 已更新數個協力廠商工具，以最佳化安全性。

**相容性更新**

* 使用者端主控台的32位元版本現已棄用。 從8.6版開始，使用者端主控台將僅提供64位元版本。 使用者端主控台可順暢升級至64位元版本。 深入了解如何升級作業系統，請參閱此[技術說明](../../technotes/upgrades/console.md)。
* 您現在可以將Campaign v8執行個體連線至Azure synapse外部資料庫。 此連線透過新的外部帳戶進行管理。 深入瞭解[促銷活動相容性矩陣](../start/compatibility-matrix.md#federated-data-access-fdafederateddataaccessfda)。


**修正**

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
* Adobe Analytics聯結器現在會匯出具有正確管道型別的量度。 它之前一律設定為「電子郵件」頻道。 (NEO-26340)
* 修正搭配日期時間欄位使用Big Query聯結器時可能導致錯誤的問題。 (NEO-49768)


## 發行版本 8.4.5 {#release-8-4-5}

_2023年 4 月 3 日_

**修正**

* 修正若將數個核准工作流程設為相同排程時，可能導致重複金鑰限制錯誤的問題。(NEO-48968)
* 修正 NEO-54474 (8.4.4) 所導致在數位內容編輯器 (DCE) 上傳影像時，內文標籤的樣式屬性有所變更的回歸問題。 (NEO-57697)
* 修正使用 CRM 連接器匯出資料時，如果臨時表格的主索引鍵定義為 long 而非 uuid，則可能導致錯誤的問題。 (NEO-54153)
* 修正 8.4.1 提出的回歸問題，此問題可能導致套件匯出、FDA over HTTP 和報告錯誤。 (NEO-57731)
* 修正 8.3.8 提出的回歸問題，此問題會導致無法針對 ID 為負的傳送正確更新傳送狀態。 (NEO-54675)
* 修正使用 Big Query 連接器匯入資料時布林欄位的問題 (NEO-49181)


## 發行版本 8.4.4 {#release-8-4-4}

_2023 年 3 月 8 日_

**安全性增強功能**

* 為了改善安全性，已將 Tomcat 從 8.5.81 版更新至 8.5.85 版。 (NEO-50530)

**修正**

* 修正了無法在數位內容編輯器 (DCE) 捲動&#x200B;**編輯**&#x200B;索引標籤的問題。 (NEO-54474)
* 修正可能於複製期間導致 Web 伺服器當機的問題。 (NEO-53670)


## 發行版本 8.4.3 {#release-8-4-3}


_2023 年 1 月 27 日_

**修正**

* 修正行銷伺服器與中間來源伺服器之間的傳送指標同步問題。(NEO-50724) <!--OKKKK-->
* 修正匯出工作流程時可能導致錯誤的問題。(NEO-50555) <!--OKKKK-->
* 修正延伸以前延伸之架構時出現的問題。(NEO-49118) <!--OKKKK-->
* 修正在連結定義中使用兩個具有相同識別碼的擴充活動時出現的問題。(NEO-48851)
* 修正兩個傳送準備失敗問題。當操作的潛在優惠方案數量太多時，傳送準備可能會失敗。 當影像 URL 定義為要在文字格式傳送中追蹤的 URL 時，會出現第二個問題。(NEO-48807) <!--OKKKK-->
* 修正可能導致工作流程失敗的問題，即工作流程會覆寫非 FFDA 帳戶外部帳戶中定義的倉儲名稱。(NEO-43209) <!--OKKKK-->
* 改善網站應用程式的安全性，以防止 DDoS 攻擊。 (NEO-50757) <!--OKKKK-->
* **[!UICONTROL Consolidated tracking]**(nms:trackingStats) FFDA 表中對合併追蹤資料的管理已得到改善，以避免重複。(NEO-46409)
* 修正在邏輯運算子條件下使用`enableIf`時工作流程查詢中的邏輯運算問題。已覆寫先前的邏輯條件。 (NEO-45815)  <!--OKKKK-->
* 帳單工作流程中已最佳化活躍輪廓的產生，以改善效能。(NEO-47658) <!--OKKKK-->
* 修正當影像節點 (img) 包含具有個人化欄位的 URL 時，HTML 檔案匯入的問題。 (NEO-48396)
* 修正在&#x200B;**分割**&#x200B;工作流程活動中使用排序參數時 Snowflake (所有部署) 的問題。(NEO-45899) <!--OKKKK-->
* 修正了當 nmsDeliveryMapping 資料夾上具有讀取存取權限的使用者嘗試執行行銷活動或工作流程時，導致錯誤的問題。 (NEO-48230)
* 修正傳送 HTML 標籤中，大型 HTML 程式碼可能發生的效能問題。 (NEO-47440)
<!-- * Fixed an issue which could lead to a "Character set mismatch" error when using certain functions such as `to_nclob` with an Oracle unicode database where NChar was not enabled. (NEO-49361)
* Fixed an issue which prevented users from inserting a Time datatype in a **Data Update** workflow activity on MSSQL. (NEO-47763)-->
* 修正阻止使用者使用&#x200B;**合併所選列**&#x200B;工作流程選項的問題。(NEO-48488)
* 修正 Snowflake FDA 連接器所引入的問題，此問題在擴充期間使用「0 或 1 基數簡單加入」選項時，會導致記錄遭到捨棄。 (NEO-48737)
* 對 log4j 程式庫的其餘參考已從 Windows 上安裝的 Campaign 中移除。 (NEO-44851)
* 修正在&#x200B;**查詢** 工作流程活動的其他資料中新增&#x200B;**已開啟的收件者**  (estimatedRecipientOpen) 指標導致錯誤的問題。(NEO-46665)
* 透過多次傳送來改善工作流程中追蹤 URL 的管理，以提升效能。(NEO-50894) <!--OKKKK-->
* 修正可能導致使用 Xtkfolder 的結構複寫失敗的問題。(NEO-46787) <!--OKKKK-->
* 修正可能導致「lastModified」自訂欄在 NmsSubscription 表格中被刪除的問題。(NEO-48402)
