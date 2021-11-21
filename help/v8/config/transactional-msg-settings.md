---
title: Campaign交易式訊息設定
description: Campaign交易式訊息設定
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: 63b53fb6a7c6ecbfc981c93a723b6758b5736acf
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 0%

---

# 異動訊息設定

![](../assets/do-not-localize/speech.png)  作為托管Cloud Services用戶， [連絡Adobe](../start/campaign-faq.md#support) 若要在您的環境中安裝及設定Campaign交易式訊息。

![](../assets/do-not-localize/glass.png) 交易式訊息功能於 [本節](../send/transactional.md).

![](../assets/do-not-localize/glass.png) 了解 [本頁](../dev/architecture.md).

## 定義權限

若要為托管於Adobe雲端的訊息中心執行例項建立新使用者，您需要聯絡Adobe客戶服務。 訊息中心使用者是需要專用權限才能存取「即時事件」(nmsRtEvent)資料夾的特定運算子。

## 結構擴充功能

對使用的結構進行的所有架構擴充功能 **訊息中心技術工作流程** 控制或執行例項必須重複於Adobe Campaign交易式訊息模組所使用的其他例項。

![](../assets/do-not-localize/book.png) 深入了解訊息中心技術工作流程，位於 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/configure-transactional-messaging/additional-configurations.html#technical-workflows)

## 傳送交易式推播通知

與行動應用程式通道模組結合時，交易式訊息可讓您透過行動裝置上的通知推送交易式訊息。

![](../assets/do-not-localize/book.png) 行動應用程式頻道於 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages).

若要傳送交易式推播通知，您必須執行下列設定：

1. 安裝 **行動應用程式頻道** 封裝至控制和執行執行個體。

   >[!CAUTION]
   >
   >安裝新的Campaign內建套件前，請先檢查您的授權合約。

1. 復寫 **行動應用程式** 執行例項上的服務及相關行動應用程式。

為了讓Campaign傳送交易式推播通知，事件必須包含下列元素：

* 行動裝置ID: **registrationId** 適用於Android和 **deviceToken** iOS。 此ID代表通知將傳送至的「位址」。
* 行動應用程式或整合金鑰的連結(**uid**)，可讓您擷取應用程式的特定連線資訊。
* 將傳送通知的通道(**whiskChannel**):iOS為41,Android為42。
* 用於個人化的其他資料。

以下是包含此資訊的事件範例：

```
<SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
     <urn:PushEvent>
         <urn:sessiontoken>mc/</urn:sessiontoken>
         <urn:domEvent>

              <rtEvent wishedChannel="41" type="DELIVERY" registrationToken="2cefnefzef758398493srefzefkzq483974">
                <mobileApp _operation=”none” uuid="com.adobe.NeoMiles"/>
                <ctx>
                    <deliveryTime>1:30 PM</deliveryTime>
                    <url>http://www.adobe.com</url>
                </ctx>
              </rtEvent>

         </urn:domEvent>
     </urn:PushEvent>           
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
