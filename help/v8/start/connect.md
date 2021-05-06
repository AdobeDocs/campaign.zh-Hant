---
solution: Campaign Classic
product: campaign
title: 瞭解如何連線至Campaign v8
description: 連線至Campaign v8
feature: 受眾
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
translation-type: tm+mt
source-git-commit: 97cc2dd6f78fac2723306f06bea74e808c84b4ad
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 6%

---

# 連接到Adobe Campaignv8{#gs-ac-connect}

「促銷活動用戶端主控台」是rich client，可讓您連線至您的Campaign應用程式伺服器。

>[!CAUTION]
>
>在開始之前，您必須檢查促銷活動[相容性矩陣](compatibility-matrix.md)，取得您的促銷活動伺服器URL和使用者認證。

## 下載並安裝Client Console

首次使用Campaign時，或如果您需要升級至較新版本，則需下載Client Console並加以安裝。

有兩個選項可供使用：

1. 身為促銷活動管理員，請連線至Adobe[軟體散發](https://experience.adobe.com/#/downloads/content/software-distribution/encampaign.html)並下載用戶端主控台安裝程式。 然後，您就可以將它安裝在本機電腦上。

1. 作為最終用戶，Adobe可以為您部署控制台：在Console更新後，會在快顯視窗中提示您下載最新的Client Console版本。

>[!CAUTION]
>
>Adobe建議取消選中&#x200B;**[!UICONTROL No longer ask this question]**&#x200B;選項，以確保當有新版本的控制台可用時，所有用戶都會收到警報。  如果選取此選項，使用者將不會收到新可用版本的通知。

### 教學課程影片

本視頻介紹如何安裝和設定Adobe Campaign客戶端。

>[!VIDEO](https://video.tv.adobe.com/v/35124?quality=12)

## 建立您的連線

新安裝Client Console後，請依照下列步驟建立與應用程式伺服器的連線：

1. 從&#x200B;**Adobe Campaign**&#x200B;程式組中的Windows **[!UICONTROL Start]**&#x200B;菜單啟動控制台。

1. 按一下憑據欄位右上角的連結以訪問連接配置窗口。

1. 按一下&#x200B;**[!UICONTROL Add > Connection]**&#x200B;並輸入Adobe Campaign應用程式伺服器的標籤和URL。

1. 指定透過URL連線至您的Adobe Campaign應用程式伺服器。 使用DNS或電腦的別名或您的IP地址。

   例如，您可以使用[`https://<machine>.<domain>.com`](https://myserver.adobe.com)類型URL。

1. 如果已為您的組織配置了AdobeIdentity Management系統(IMS)，請選中&#x200B;**[!UICONTROL Connect with an Adobe ID]**&#x200B;選項。

1. 按一下&#x200B;**[!UICONTROL Ok]**&#x200B;以儲存您的設定。

例如，您可以視需要新增多個連線，以連線至測試、舞台和生產環境。

>[!NOTE]
>
>**[!UICONTROL Add]**&#x200B;按鈕可讓您建立&#x200B;**[!UICONTROL folders]**&#x200B;來組織所有連線。 只需將每個連線拖放到資料夾中即可。

## 登錄Adobe Campaign

要登錄到現有實例，請執行以下步驟：

1. 從&#x200B;**Adobe Campaign**&#x200B;程式組中的Windows **[!UICONTROL Start]**&#x200B;菜單啟動控制台。

1. 按一下憑據欄位右上角的連結以訪問連接配置窗口。

1. 選取您登入時需要的促銷活動例項。

1. 按一下 **[!UICONTROL Ok]**。

1. 輸入您的用戶登錄憑據，然後按一下&#x200B;**[!UICONTROL LOG IN]**。

   ![](assets/sign-in-v8.png)

根據您的配置，您的認證可以是：

* 由您的促銷活動管理員提供，授予您存取權
* 你的Adobe ID

## 授予使用者存取權

Adobe Campaign可讓您定義並管理指派給各種運算子的權限。 這些是授權或拒絕的一組權利和限制：

* 存取特定功能（透過指名的權利）,
* 存取特定元素、
* 建立、修改及／或刪除元素（傳送、連絡人、促銷活動、群組等）。

進一步瞭解使用者以及如何在[本節](permissions.md)中定義其權限。

身為促銷活動管理員，您負責建立運算子並與使用者共用其認證。


## 使用您的Adobe ID連線至促銷活動{#connect-ims}

促銷活動使用者可透過AdobeIdentity Management系統(IMS)，使用其Adobe ID連線至Adobe Campaign主控台。 此實作提供下列優點：

* 所有 Experience Cloud 解決方案都可以使用相同的 ID。
* 使用不同整合中的 Adobe Campaign 時，可以記憶連線。
* 更強大的密碼管理政策。
* 使用 Federated ID 帳戶（外部 ID 提供者）。

:speech_balloon:身為受管理的Cloud Services使用者，[連絡Adobe](support.md#support)以實作AdobeIMS與促銷活動。

## 使用LDAP登入連線至Campaign

Adobe Campaign可以進行配置，以便用戶通過其LDAP驗證訪問平台。

:speech_balloon:身為「受管理Cloud Services」使用者，[連絡Adobe](support.md#support)以設定與「促銷活動」的LDAP整合。


## 網路存取

應用程式的某些部分可透過簡單的網頁瀏覽器使用HTML使用者介面來存取：報告、傳送核准、例項監控等。
