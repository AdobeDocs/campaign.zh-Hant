---
title: Campaign安全性最佳做法
description: 開始使用Campaign安全性最佳做法
feature: Privacy, PI
role: Developer
level: Beginner
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 1%

---

# Campaign安全性最佳做法 {#ac-security}

Adobe非常重視您數位體驗的安全性。 安全性實務已深深植入我們的內部軟體開發和作業流程及工具，我們的跨職能團隊也嚴格遵循這些實務准則，以迅速預防、偵測和回應事件。

此外，我們與合作夥伴、領先的研究人員、安全性研究機構和其他產業組織締結合作關係，這能協助我們掌握最新的威脅和弱點，並定期將進階安全性技術整合至我們提供的產品和服務中。

## 隱私權

隱私權設定和強化是安全性最佳化的關鍵元素。 以下是隱私權方面的一些最佳實務：

* 使用HTTPS而非HTTP，Protect您的客戶個人資訊(PI)
* 使用 [PI檢視限制](../dev/restrict-pi-view.md) 以保護隱私權並防止資料被濫用
* 請確定加密的密碼受到限制
* Protect中可能包含個人資訊的頁面，例如映象頁面、網頁應用程式等。

![](../assets/do-not-localize/speech.png)  作為「受管理的Cloud Service」使用者，Adobe將與您合作，在您的環境中實作這些設定。


## 存取管理

存取管理是強化安全性的重要一環。 以下是一些主要最佳實務：

* 建立足夠的安全性群組
* 檢查每個操作員是否具有適當的存取許可權

進一步瞭解中的許可權 [本節](../start/gs-permissions.md)

## 編碼准則

在Adobe Campaign中進行開發時（工作流程、JavaScript、JSSP等），請一律遵循下列准則：

* **指令碼**：請嘗試避免SQL陳述式，使用引數化函式而非字串串串連，將要使用的SQL函式新增至允許清單以避免SQL插入。

* **保護資料模型**：使用已命名的許可權來限制運運算元動作、新增系統篩選器(sysFilter)

* **在Web應用程式中新增字幕**：在您的公開登陸頁面和訂閱頁面中新增驗證碼。

![](../assets/do-not-localize/book.png) 進一步瞭解 [Adobe Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html#installing-campaign-classic){target="_blank"}


## 個人化

將個人化連結新增至您的內容時，請一律避免URL的主機名稱部分有任何個人化專案，以避免潛在的安全性缺口。 下列範例絕不應該用於所有URL屬性&lt;`a href="">` 或 `<img src="">`：

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## 資料限制

您必須確定低許可權驗證的使用者無法存取加密的密碼。 要執行此操作，有兩個主要方法：限制僅存取密碼欄位或存取整個實體。

此限制可讓您移除密碼欄位，但讓所有使用者都可從介面存取外部帳戶。 在[本頁](../dev/restrict-pi-view.md)中瞭解更多。

1. 前往 **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**.

1. 建立新的 **[!UICONTROL Extension of a schema]**.

1. 選擇 **[!UICONTROL External Account]** (extAccount)。

1. 在最後一個畫面中，您可以編輯新的srcSchema來限制存取所有密碼欄位：

   您可以取代主要元素(`<element name="extAccount" ... >`)方式：

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

   因此，您的擴充式srcSchema看起來可能像這樣：

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
   >您可以取代 `$(loginId) = 0 or $(login) = 'admin'` 作者： `hasNamedRight('admin')` 讓所有具有管理員許可權的使用者看見這些密碼。


## 存取管理

存取管理是強化安全性的重要一環。 以下是一些主要最佳實務：

* 建立足夠的安全性群組
* 檢查每個操作員是否具有適當的存取許可權

進一步瞭解中的許可權 [在本節中](../start/gs-permissions.md).

## 編碼准則

在Adobe Campaign中進行開發時（工作流程、JavaScript、JSSP等），請一律遵循下列准則：

* **指令碼**：請嘗試避免SQL陳述式，使用引數化函式而非字串串串連，將要使用的SQL函式新增至允許清單以避免SQL插入。

* **保護資料模型**：使用已命名的許可權來限制運運算元動作、新增系統篩選器(sysFilter)

* **在Web應用程式中新增字幕**：在您的公開登陸頁面和訂閱頁面中新增驗證碼。

![](../assets/do-not-localize/book.png) 進一步瞭解 [Adobe Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html#installing-campaign-classic){target="_blank"}
