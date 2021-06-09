---
product: Adobe Campaign
title: Campaign交易式訊息設定
description: Campaign交易式訊息設定
feature: 概覽
role: Data Engineer
level: Beginner
source-git-commit: 9cb1b38456601bce21d458fea42a5c112d9fafb4
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 1%

---

# 異動訊息設定

[!DNL :speech_balloon:] 以「受管Cloud Services」使用者的身 [分，](../start/campaign-faq.md#support) 請連絡Adobe，在您的環境中安裝及設定Campaign交易訊息。

[!DNL :bulb:] 本節將詳細說明交易式 [訊息功能](../send/transactional.md)。

[!DNL :bulb:] 在本頁面中了解交易式 [訊息架構](../dev/architecture.md)。

## 定義權限

若要為托管於Adobe雲端的訊息中心執行例項建立新使用者，您需要聯絡Adobe客戶服務。 訊息中心使用者是需要專用權限才能存取「即時事件」(nmsRtEvent)資料夾的特定運算子。

## 結構擴充功能

在&#x200B;**Message Center技術工作流程**&#x200B;在控制或執行例項上所使用架構上所建立的所有架構擴充功能，必須複製到Adobe Campaign交易訊息模組所使用的其他例項上。

[!DNL :arrow_upper_right:] 進一步了解Campaign Classicv7檔案中的訊息中 [心技術工作流程](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/configure-transactional-messaging/additional-configurations.html#technical-workflows)

## 傳送交易式推播通知

與行動應用程式通道模組結合時，交易式訊息可讓您透過行動裝置上的通知推送交易式訊息。

[!DNL :arrow_upper_right:] 行動應用程式通道在Campaign Classicv7 [檔案中有詳細說明](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages)。

若要傳送交易式推播通知，您必須執行下列設定：

1. 將&#x200B;**行動應用程式頻道**&#x200B;套件安裝至控制項和執行個體。

   >[!CAUTION]
   >
   >安裝新的Campaign內建套件前，請先檢查您的授權合約。

1. 在執行實例上複製&#x200B;**Mobile application**&#x200B;服務和相關的移動應用程式。

為了讓Campaign傳送交易式推播通知，事件必須包含下列元素：

* 行動裝置ID:**registrationId**&#x200B;適用於Android,**deviceToken**&#x200B;適用於iOS。 此ID代表通知將傳送至的「位址」。
* 行動應用程式的連結或整合索引鍵(**uuid**)，可讓您擷取應用程式專屬的連線資訊。
* 將向其發送通知的通道(**wishedChannel**):iOS為41,Android為42。
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

