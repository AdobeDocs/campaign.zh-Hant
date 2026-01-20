---
source-git-commit: 548b4be24e26a6970f953f92af1f89d829689592
workflow-type: tm+mt
source-wordcount: '1522'
ht-degree: 0%

---
# AC-UI-26-01檔案分析

## 下一版本內容

本檔案會分析AC-UI-26-01和AC-UI-25-11每月發行的產品JIRA，以計畫檔案行動。

### JIRA篩選器

1. **[AC-UI-26-01-Monthly Stories](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-26-01-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** — 主要發行說明
2. **[NEO-92400改進](https://jira.corp.adobe.com/issues/?jql=issueFunction%20in%20linkedIssuesOf(%27key%3DNEO-92400%27%2C%20%27is%20implemented%20by%27))** — 版本改進連結問題
3. **[AC-UI-25-11月故事](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** — 舊版轉送
4. **[AC-UI-25-11不包括8.8.2](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20fixVersion%20!%3D%208.8.2%20and%20type%20%3D%20story%20order%20by%20status)** — 已篩選舊版

&#x200B;---

## 🟢建立DOCAC

### [NEO-91565](https://jira.corp.adobe.com/browse/NEO-91565) — 新增對個人化欄位的支援(進階AEM整合)**狀態：**&#x200B;已解決\**需要的檔案：**&#x200B;是\**現有DOCAC：**&#x200B;無\**動作：**&#x200B;建立DOCAC

**範圍：**
- 進階AEM整合中個人化欄位的檔案支援
- UI工作流程和設定步驟
- AEM多語言整合功能

**功能描述：**
支援使用進階AEM整合在傳遞中新增個人化欄位，可啟用動態內容從Campaign資料插入AEM編寫的電子郵件範本。

**內容：** ACS至ACC同位檢查，MSFT特定需求

**參考資料：** [AEM多語言Wiki](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=2988189953)

&#x200B;---

### [NEO-93487](https://jira.corp.adobe.com/browse/NEO-93487) — 傳遞排程運算程式（ACS同位檢查）**狀態：**&#x200B;新增\**需要的檔案：**&#x200B;是\**現有DOCAC：**&#x200B;無\**動作：**&#x200B;建立DOCAC

**範圍：**
- 推播通知的檔案傳遞排程計算程式
- 以時區為基礎的排程公式
- 多時區定位的檔案上傳

**功能描述：**
啟用以OOTB檔案為基礎的傳送排程，根據收件者時區計算傳送時間，允許跨多個時區的單一傳送目標定位，每個區域有最佳化的傳送時間。

**內容：**&#x200B;客戶導向(H&amp;M)，ACS到ACC同位要求

**參考：** [ACS檔案](https://experienceleague.adobe.com/zh-hant/docs/campaign-standard/using/testing-and-sending/scheduling-messages/computing-the-sending-date)

&#x200B;---

## 🔄更新DOCAC

### [NEO-80973](https://jira.corp.adobe.com/browse/NEO-80973) — 所有Web UI使用者的動態報告可用性&#x200B;**狀態：**&#x200B;進行中\**需要的檔案：**&#x200B;是\**現有DOCAC：** [DOCAC-11070](https://jira.corp.adobe.com/browse/DOCAC-11070) （已關閉），[DOCAC-13432](https://jira.corp.adobe.com/browse/DOCAC-13432) （已解決）\**動作：**&#x200B;檢閱DOCAC

**範圍：**
- 更新可用性資訊（現在適用於所有Web UI使用者，而不僅僅是8.7）
- 檔案語言限制
- 釐清與舊版報告顯示衝突的量度

**功能描述：**
現在，所有Campaign網頁UI使用者（先前對於ACC客戶僅限8.7個ACS）都可使用動態報告，透過ACS樣式的介面提供進階分析和自訂報告功能。

**內容：**&#x200B;功能擴充，後端組建相依性(8.8.1)

**參考資料：** [Wiki — 報表比較](https://wiki.corp.adobe.com/display/~kumarvishal/Reports+-+Client+console+vs+WebUI)

&#x200B;---

### [NEO-86754](https://jira.corp.adobe.com/browse/NEO-86754) - A/B測試&#x200B;**狀態：**&#x200B;進行中\**需要的檔案：**&#x200B;是\**現有DOCAC：** [DOCAC-13104](https://jira.corp.adobe.com/browse/DOCAC-13104) （新）\**動作：**&#x200B;更新DOCAC

**範圍：**
- 完成A/B測試工作流程檔案
- 內容實驗設定和變體設定
- 範例比例定義和成功者選取條件
- 統計資料收集和評估

**功能描述：**
針對電子郵件傳遞的內容實驗和A/B測試，可讓行銷人員測試不同的內容變體、定義樣本大小、收集效能統計資料，並自動將成功變體傳送給其餘收件者。

**內容：** Europa專案，Microsoft需求，已啟用功能標幟

**參考資料：** [Wiki](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=3017705719)，[Figma模組](https://www.figma.com/design/4EfXEaA6OIV0D8rauuXSWX/A-B-Testing)

&#x200B;---

### [NEO-76126](https://jira.corp.adobe.com/browse/NEO-76126) — 結構描述編寫（建立新資料表、擴充結構描述、存取外部資料庫）**狀態：**&#x200B;進行中\**需要的檔案：**&#x200B;是\**現有DOCAC：** [DOCAC-13826](https://jira.corp.adobe.com/browse/DOCAC-13826) （新）\**動作：**&#x200B;更新DOCAC

**範圍：**
- 檔案結構描述編寫工作流程（僅限3個選項：建立表格、擴充結構描述、存取外部DB）
- 自訂實體的表單定義
- 在自訂結構描述上導覽和CRUD操作
- 第2階段和第3階段功能

**功能描述：**
Web UI中的方案製作功能可讓管理員建立新的資料庫表格、使用自訂欄位擴充現有方案，以及連線至外部資料庫，這些對於資料模型自訂至關重要。

**內容：** Microsoft需求，Europa專案，分階段傳遞（階段2作用中，階段3二月底結束）

**參考：** [PRD](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=AC+Web+UI+-+Schemas+PRD)，[Figma](https://www.figma.com/design/lZkJso2HvXPbNjG0TmQTrC/Schemas)

&#x200B;---

### [NEO-92668](https://jira.corp.adobe.com/browse/NEO-92668) — 網站分析&#x200B;**狀態：**&#x200B;新增\**需要的檔案：**&#x200B;是\**現有DOCAC：**&#x200B;無\**動作：**&#x200B;建立DOCAC

**範圍：**
- 網站分析外部帳戶設定
- 整合設定和驗證
- Analytics行銷活動中的資料使用情況

**功能描述：**
Web Analytics整合可連線至Web Analytics平台，以追蹤及報告行銷活動績效和網站訪客行為。

**內容：**&#x200B;客戶請求(P2E-RSC)，環境可用性擱置中

**參考：**&#x200B;未提供任何參考

&#x200B;---

### [NEO-86753](https://jira.corp.adobe.com/browse/NEO-86753) — 即時副本/語言副本的AEM整合&#x200B;**狀態：**&#x200B;新增\**需要的檔案：**&#x200B;是\**現有DOCAC：** [DOCAC-13829](https://jira.corp.adobe.com/browse/DOCAC-13829) （已解決）\**動作：**&#x200B;檢閱DOCAC

**範圍：**
- 瀏覽AEM傳遞範本
- 按一下即可建立即時副本和語言副本
- 多語言內容變體建立工作流程

**功能描述：**
簡化的AEM整合可讓您從AEM傳遞範本按一下即可建立即時副本和語言副本，簡化AEM使用者的多語言行銷活動建立作業。

**內容：** Microsoft需求，工作已轉移給喜滿樹團隊

**參考：** [ACS檔案](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-experience-manager/creating-multilingual-email-aem.html?lang=zh-Hant)

&#x200B;---

### [NEO-88838](https://jira.corp.adobe.com/browse/NEO-88838) — 內容編輯器：在片段中使用主題變數&#x200B;**狀態：**&#x200B;新增\**需要的檔案：**&#x200B;是\**現有DOCAC：** [DOCAC-12941](https://jira.corp.adobe.com/browse/DOCAC-12941) （新）\**動作：**&#x200B;更新DOCAC

**範圍：**
- 電子郵件設計工具中的主題變數(Beta)
- 在片段中使用主題
- 啟用Acrite功能

**功能描述：**
支援在內容片段中使用主題變數，透過集中化的主題管理，跨電子郵件元件啟用一致的品牌和設計系統應用程式。

**內容：**&#x200B;等候重新造訪的Acrite功能

**參考：** [ATU-5460](https://jira.corp.adobe.com/browse/ATU-5460)

&#x200B;---

## ➕建立DOCAC （改善）

### [NEO-92942](https://jira.corp.adobe.com/browse/NEO-92942) — 預先定義的篩選器 — 共用選項&#x200B;**狀態：**&#x200B;已解決\**需要的檔案：**&#x200B;是\**現有DOCAC：** [DOCAC-13697](https://jira.corp.adobe.com/browse/DOCAC-13697) （程式碼檢閱），[DOCAC-13522](https://jira.corp.adobe.com/browse/DOCAC-13522) （已關閉 — 協助程式）\**動作：**&#x200B;檢閱DOCAC

**範圍：**
- 預先定義篩選器的共用選項
- 與其他運運算元的篩選器可見度（ACC與Brand Journey行為）
- 共用篩選器的使用者管理

**功能描述：**
預先定義的篩選器現在可以標示為「共用」，好讓其他操作者看見，ACC （預設）和Brand Journey （使用者特定篩選）有不同的行為。

**內容：**&#x200B;規則產生器增強功能，功能標幟： enable-query-filter-shared

**參考：**&#x200B;與[NEO-88441](https://jira.corp.adobe.com/browse/NEO-88441)相關

&#x200B;---

### [NEO-91299](https://jira.corp.adobe.com/browse/NEO-91299) — 持續傳遞活動&#x200B;**狀態：**&#x200B;已關閉\**需要的檔案：**&#x200B;是\**現有DOCAC：** [DOCAC-13586](https://jira.corp.adobe.com/browse/DOCAC-13586) （新），[DOCAC-13808](https://jira.corp.adobe.com/browse/DOCAC-13808) （已關閉 — 內容說明）\**動作：**&#x200B;更新DOCAC

**範圍：**
- 持續傳遞工作流程活動
- 傳遞範本選擇器設定
- 自動產生出站轉變
- 鎖定目標選項（無內容存取權）

**功能描述：**
工作流程的持續傳遞活動可從範本中重複執行傳遞，不需修改內容即可自動產生工作流程協調的出站轉變。

**內容：**&#x200B;功能標幟： enable-continuous-delivery

**參考：**&#x200B;相關史詩[NEO-67972](https://jira.corp.adobe.com/browse/NEO-67972)

&#x200B;---

### [NEO-90130](https://jira.corp.adobe.com/browse/NEO-90130) — 啟用多語言推播通知的OOTB檔案上傳&#x200B;**狀態：**&#x200B;已關閉\**需要的檔案：**&#x200B;是\**現有DOCAC：** [DOCAC-13606](https://jira.corp.adobe.com/browse/DOCAC-13606) （新）\**動作：**&#x200B;更新DOCAC

**範圍：**
- 多語言推播通知的檔案上傳(iOS和Android)
- CSV格式和欄位對應
- 具備多語言功能的豐富推送支援

**功能描述：**
OOTB檔案上傳功能可透過CSV匯入建立多語言推播通知傳遞、符合ACS功能並啟用有效的多語言行銷活動設定。

**內容：**&#x200B;客戶導向(H&amp;M)，ACS到ACC同位，移轉的關鍵

**參考：** [ACS檔案](https://experienceleague.adobe.com/zh-hant/docs/campaign-standard/using/communication-channels/push-notifications/generating-csv-multilingual-push)

&#x200B;---

## ❌已取消/不再適用

### [NEO-91566](https://jira.corp.adobe.com/browse/NEO-91566) — 支援webui中的CTA追蹤&#x200B;**狀態：**&#x200B;已關閉（不再適用）\**需要檔案：**&#x200B;否\**現有DOCAC：** [DOCAC-13821](https://jira.corp.adobe.com/browse/DOCAC-13821) （新）\**動作：**&#x200B;關閉DOCAC

**原因：**&#x200B;支援MSFT的新ACS功能 — 未啟動、來自MSFT的擱置資訊、預期沒有UI工作

**內容：** Microsoft特定、CTA追蹤需求

&#x200B;---

### [NEO-91564](https://jira.corp.adobe.com/browse/NEO-91564) - AEM多語言UI支援&#x200B;**狀態：**&#x200B;已關閉（不再適用）\**需要檔案：**&#x200B;否\**現有DOCAC：** [DOCAC-13822](https://jira.corp.adobe.com/browse/DOCAC-13822) （新）\**動作：**&#x200B;關閉DOCAC

**原因：** Himanshu團隊管理的UI工作（不同劇本）

**內容：** Microsoft需求，工作已轉移

&#x200B;---

### [NEO-91567](https://jira.corp.adobe.com/browse/NEO-91567) — 新增NRT功能支援&#x200B;**狀態：**&#x200B;已解決（不再適用）\**需要檔案：**&#x200B;否\**現有DOCAC：** [DOCAC-13824](https://jira.corp.adobe.com/browse/DOCAC-13824) （新）\**動作：**&#x200B;關閉DOCAC

**原因：**&#x200B;針對MSFT的新ACS特定功能 — 規格可用，但不會影響網頁UI

**內容：** Microsoft需求，異動訊息

&#x200B;---

### [NEO-91563](https://jira.corp.adobe.com/browse/NEO-91563) — 設定檔擴充的異動Rest API&#x200B;**狀態：**&#x200B;已解決（不再適用）\**需要檔案：**&#x200B;否\**現有DOCAC：** [DOCAC-13825](https://jira.corp.adobe.com/browse/DOCAC-13825) （新）\**動作：**&#x200B;關閉DOCAC

**原因：**&#x200B;沒有Web UI工作，擱置升級的執行個體，版本編號升級為發行所必需

**內容：** REST API端點功能

&#x200B;---

### [NEO-92151](https://jira.corp.adobe.com/browse/NEO-92151) — 設定檔擴充異動訊息階段2&#x200B;**狀態：**&#x200B;已解決（不再適用）\**需要檔案：**&#x200B;否\**現有DOCAC：** [DOCAC-13823](https://jira.corp.adobe.com/browse/DOCAC-13823) （新）\**動作：**&#x200B;關閉DOCAC

**原因：**&#x200B;本文沒有工作，標示為「不再適用」

**內容：** Microsoft需求，Europa專案

&#x200B;---

## 🟢份檔案已準備就緒（從AC-UI-25-11）

### [NEO-90183](https://jira.corp.adobe.com/browse/NEO-90183) — 多語言豐富推送 — UI&#x200B;**狀態：**&#x200B;已關閉\**需要的檔案：**&#x200B;是\**現有DOCAC：** [DOCAC-13565](https://jira.corp.adobe.com/browse/DOCAC-13565) （新）\**動作：**&#x200B;檢閱DOCAC

**範圍：**
- 多語言傳遞的豐富推送欄位
- iOS和Android平台支援
- 範本和內容設定

**功能描述：**
豐富推播通知支援支援多語言功能，可讓行銷人員為iOS和Android建立具有多語言影像、按鈕和豐富媒體的增強推播通知。

**內容：**&#x200B;客戶導向(H&amp;M)，25-11傳遞，後端工作已完成

**參考資料：** [Wiki](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=Rich+push+fields+in+multilingual)

&#x200B;---

### [NEO-84916](https://jira.corp.adobe.com/browse/NEO-84916) — 設定及管理核准程式&#x200B;**狀態：**&#x200B;已解決\**需要的檔案：**&#x200B;是\**現有DOCAC：** [DOCAC-13827](https://jira.corp.adobe.com/browse/DOCAC-13827) （新）\**動作：**&#x200B;更新DOCAC

**範圍：**
- 在傳遞/行銷活動中設定驗證運運算元
- 核准工作流程設定
- 內容與目標核准程式
- 多頻道支援（電子郵件、簡訊、推播、直接郵件、客服中心、自訂）

**功能描述：**
核准流程管理啟用傳遞內容和定位的驗證工作流程，並透過所有傳遞管道的操作者指派和核准追蹤。

**內容：**&#x200B;客戶導向(Pierre Fabre)、Microsoft需求、開發完成及測試中

**參考：** [傳統檔案](https://experienceleague.adobe.com/zh-hant/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval)，[Figma模組](https://www.figma.com/design/r2vpqXoVyI3aucKgkt8TLN/Approvals)

&#x200B;---

## 📊摘要（依動作）

| 動作 | 計數 |
|--------|-------|
| 🟢建立DOCAC | 3 |
| 🔄更新DOCAC | 6 |
| ✅檢閱DOCAC | 3 |
| ❌關閉DOCAC | 5 |
| **總計** | **17** |

&#x200B;---

## ⚠️個未完成的問題

1. Neo-93487 - H&amp;M提升 — 需要緊急關注以排程運算程式
2. Neo-92668 - Web Analytics — 等待環境可用性，然後才能完成檔案
3. Neo-76126 — 方案階段3 - ETA 2月底結束，需要個別說明檔案
4. Neo-88838 — 主題變數 — 擱置中Acrite功能修訂
5. 動態報告 — 透過舊式報告釐清衝突量度顯示指引

&#x200B;---

## 🔗個相關Epic

- Neo-85263 - ACS至ACC (EUROPA)父級epic
- Neo-67972 — 工作流程改善
- Neo-87980 — 進階AEM整合
- Neo-90199 — 動態報告版本整備
- Neo-63067 — 內容實驗UX/UI
- Neo-67726 - A/B測試和內容實驗
- Neo-85274 — 結構和表單（階段2）
- Neo-87993 — 結構和表單（階段3）
