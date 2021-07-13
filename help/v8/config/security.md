---
product: Adobe Campaign
title: Campaign安全性最佳實務
description: 開始使用Campaign安全性最佳實務
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 1%

---

# Campaign安全性最佳實務 {#ac-security}

在Adobe，我們非常重視數位體驗的安全性。 安全性做法已深深紮根於我們的內部軟體開發和操作流程及工具中，我們的跨職能團隊也嚴格遵循這些做法，以便以權宜的方式預防、檢測和響應事件。

此外，我們與合作夥伴、領先研究人員、安全研究機構和其他行業組織的協作有助於我們及時了解最新威脅和漏洞，並且我們定期將先進的安全技術納入我們提供的產品和服務中。

## 隱私權

隱私權配置和強化是安全性最佳化的關鍵元素。 以下是關於隱私權的一些最佳實務：

* Protect使用HTTPS而非HTTP來管理客戶個人資訊(PI)
* 使用[PI視圖限制](../dev/restrict-pi-view.md)保護隱私並防止資料被誤用
* 請確定加密密碼受限
* Protect可能包含個人資訊的頁面，例如鏡像頁面、網頁應用程式等。

??身為受管Cloud Services使用者，Adobe會與您合作，在您的環境中實作這些設定。

## 個人化

將個人化連結新增至內容時，請一律避免URL的主機名稱部分出現任何個人化，以避免潛在的安全漏洞。 所有URL屬性&lt;`a href="">`或`<img src="">`中一律不應使用下列範例：

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## 資料限制

您必須確保已加密密碼無法由低權限已驗證的使用者存取。 要做到這一點，有兩種主要方法：僅限訪問密碼欄位或限制訪問整個實體。

此限制可讓您移除密碼欄位，但讓所有使用者都能從介面存取外部帳戶。 在[本頁](../dev/restrict-pi-view.md)中瞭解更多。

1. 前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**。

1. 建立新的&#x200B;**[!UICONTROL Extension of a schema]**。

1. 選擇&#x200B;**[!UICONTROL External Account]**(extAccount)。

1. 在最後一個螢幕中，您可以編輯新的srcSchema以限制對所有密碼欄位的訪問：

   您可以以下列方式取代主要元素(`<element name="extAccount" ... >`):

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

   因此，您的延伸srcSchema看起來可能像：

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
   >您可以將`$(loginId) = 0 or $(login) = 'admin'`取代為`hasNamedRight('admin')`，讓所有具有管理員權限的使用者都能查看這些密碼。


## 存取管理

訪問管理是加強安全性的重要環節。 以下是一些主要最佳實務：

* 建立足夠的安全組
* 檢查每個運算子是否擁有適當的存取權限
* 請避免使用管理員運算子，並避免管理員群組中有太多運算子

↗️深入了解[Adobe Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management.html?lang=en#webapp-operator){target=&quot;_blank&quot;}

## 編碼准則

在Adobe Campaign中開發時（工作流程、Javascript、JSSP等），請一律遵循下列准則：

* **指令碼**:嘗試避免SQL陳述式，使用參數化函式而不是字串串連接，通過將要使用的SQL函式添加到允許清單來避免SQL插入。

* **保護資料模型**:使用命名權限來限制運算子操作，添加系統篩選器(sysFilter)

* **在Web應用程式中新增captcha**:在您的公開登錄頁面和訂閱頁面中新增captcha。

↗️深入了解[Adobe Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=en#installing-campaign-classic){target=&quot;_blank&quot;}
