---
title: 市場活動安全最佳做法
description: 開始使用活動安全最佳做法
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
source-git-commit: 63b53fb6a7c6ecbfc981c93a723b6758b5736acf
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 1%

---

# 市場活動安全最佳做法 {#ac-security}

在Adobe，我們非常重視您的數字型驗的安全性。 安全做法已深深紮根於我們的內部軟體開發以及操作流程和工具中，我們的跨職能團隊也嚴格遵循這些做法，以便以權宜的方式預防、檢測和響應事件。

此外，我們與合作夥伴、領先研究人員、安全研究機構和其他行業組織的協作有助於我們及時瞭解最新的威脅和漏洞，並且我們定期將先進的安全技術納入我們提供的產品和服務中。

## 隱私權

隱私配置和強化是安全優化的關鍵。 以下是有關隱私的一些最佳做法：

* Protect您的客戶個人資訊(PI)，使用HTTPS而不是HTTP
* 使用 [PI視圖限制](../dev/restrict-pi-view.md) 保護隱私並防止資料被誤用
* 確保加密密碼受限
* Protect可能包含鏡像頁面、Web應用程式等個人資訊的頁面。

![](../assets/do-not-localize/speech.png)  作為受管理Cloud Services用戶，Adobe將與您協作，在您的環境中實施這些配置。

## 個人化

在向內容添加個性化連結時，始終避免在URL的主機名部分中出現任何個性化設定，以避免潛在的安全漏洞。 以下示例不應用於所有URL屬性&lt;`a href="">` 或 `<img src="">`:

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## 資料限制

您必須確保低權限的經過身份驗證的用戶無法訪問加密的密碼。 要做到這一點，主要有兩種方式：僅限制對密碼欄位或對整個實體的訪問。

此限制允許您刪除密碼欄位，但允許所有用戶從介面訪問外部帳戶。 在[本頁](../dev/restrict-pi-view.md)中瞭解更多。

1. 進去 **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**。

1. 新建 **[!UICONTROL Extension of a schema]**。

1. 選擇 **[!UICONTROL External Account]** （分機帳戶）。

1. 在最後一個螢幕中，您可以編輯新srcSchema以限制對所有密碼欄位的訪問：

   可以替換主元素(`<element name="extAccount" ... >`)依據：

   ```
   <element name="extAccount">
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
       <element name="s3Account">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
       </element>
       <element name="wapPush">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
       <element name="mms">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
   </element>
   ```

   因此，擴展的srcSchema可以是：

   ```
   <...>
       <element name="extAccount">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
           <element name="s3Account">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
           </element>
           <element name="wapPush">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
           <element name="mms">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
       </element>
   <...> 
   ```

   >[!NOTE]
   >
   >可以替換 `$(loginId) = 0 or $(login) = 'admin'` 按 `hasNamedRight('admin')` 允許具有管理員權限的所有用戶查看這些密碼。


## 存取管理

訪問管理是加強安全性的一個重要部分。 以下是一些主要的最佳做法：

* 建立足夠的安全組
* 檢查每個操作員是否具有適當的訪問權限
* 避免使用管理員操作員，並避免管理員組中的操作員過多

![](../assets/do-not-localize/book.png) 瞭解詳情 [Adobe Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management.html?lang=en#webapp-operator){target=&quot;_blank&quot;

## 編碼准則

在Adobe Campaign開發時（工作流、Javascript、JSSP等），請始終遵循以下准則：

* **指令碼**:嘗試避免使用SQL陳述式，使用參數化函式而不是字串連接，通過將要使用的SQL函式添加到允許清單來避免SQL注入。

* **保護資料模型**:使用命名權限限制運算子操作，添加系統篩選器(sysFilter)

* **在Web應用程式中添加捕獲**:在公共登錄頁和訂閱頁中添加captcha。

![](../assets/do-not-localize/book.png) 瞭解詳情 [Adobe Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=en#installing-campaign-classic){target=&quot;_blank&quot;
