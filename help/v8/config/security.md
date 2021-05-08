---
solution: Campaign
product: Adobe Campaign
title: 促銷活動安全性最佳實務
description: 開始使用Campaign安全性最佳實務
translation-type: tm+mt
source-git-commit: 5592dd4e79391d953a4bc54cdd47475417e07b56
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 0%

---

# 促銷活動安全性最佳實務{#ac-security}

在Adobe，我們非常重視您數位體驗的安全性。 安全性做法已深植於我們的內部軟體開發與作業程式與工具中，我們的跨職能團隊會嚴格遵循這些做法，以便在權宜的方式預防、偵測和回應事件。

此外，我們與合作夥伴、頂尖研究人員、安全性研究機構和其他產業組織的合作有助於我們隨時掌握最新的威脅和弱點，並定期將進階的安全性技術加入我們提供的產品和服務中。

## 隱私權

隱私權配置和強化是安全性最佳化的關鍵要素。 以下是有關隱私權的一些最佳實務：

* Protect客戶個人資訊(PI)，使用HTTPS而非HTTP
* 使用[PI檢視限制](../dev/restrict-pi-view.md)來保護隱私權並防止資料遭到濫用
* 確保加密密碼受到限制
* Protect可能包含個人資訊的頁面，例如鏡像頁面、Web應用程式等。

:speech_balloon:作為受管理的Cloud Services用戶，Adobe將與您合作在您的環境中實施這些配置。

## 個人化

在將個人化連結新增至您的內容時，請務必避免URL的主機名稱部分有任何個人化，以避免潛在的安全性缺口。 以下範例不應用於所有URL屬性&lt;`a href="">`或`<img src="">`:

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## 資料限制

您必須確保已加密密碼無法由低權限的已驗證用戶訪問。 要做到這一點，有兩種主要方式：僅限存取密碼欄位或限制存取整個實體。

此限制允許您移除密碼欄位，但讓所有使用者都可從介面存取外部帳戶。 進一步瞭解[本頁](../dev/restrict-pi-view.md)。

1. 進入&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**。

1. 建立新的&#x200B;**[!UICONTROL Extension of a schema]**。

1. 選擇&#x200B;**[!UICONTROL External Account]**(extAccount)。

1. 在最後一個畫面中，您可以編輯新的srcSchema，以限制對所有密碼欄位的存取：

   您可以以下列方式替換主要元素(`<element name="extAccount" ... >`):

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

   因此，擴展的srcSchema可以如下所示：

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
   >您可以將`$(loginId) = 0 or $(login) = 'admin'`取代為`hasNamedRight('admin')`，讓擁有管理員權限的所有使用者都能看到這些密碼。


## 存取管理

訪問管理是加強安全性的一個重要部分。 以下是一些主要的最佳實務：

* 建立足夠的安全性群組
* 檢查每個運算子是否擁有適當的存取權限
* 避免使用管理員運算子，並避免管理群組中的運算子過多

:arrow_upper_right:進一步瞭解[Adobe Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management.html?lang=en#webapp-operator)

## 編碼准則

在Adobe Campaign進行開發時（工作流程、Javascript、JSSP等），請一律遵循下列准則：

* **指令碼**:嘗試避免SQL陳述式，使用參數化函式而不是字串串連，通過將要使用的SQL函式添加到允許清單來避免SQL插入。

* **保護資料模型**:使用命名權限來限制運算元動作，新增系統篩選(sysFilter)

* **在Web應用程式中新增擷取功能**:在您的公開登陸頁面和訂閱頁面中新增captchas。

:arrow_upper_right:進一步瞭解[Adobe Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=en#installing-campaign-classic)
