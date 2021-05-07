---
solution: Campaign
product: Adobe Campaign
title: 促銷活動交易訊息設定
description: 促銷活動交易訊息設定
feature: 概覽
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# 交易式訊息設定

:speech_balloon:作為受管理Cloud Services用戶， [與Adobe](../start/support.md#support)聯繫，以在您的環境中安裝和配置促銷活動事務性消息。

：球：[本節](../send/transactional.md)中詳細介紹了事務性消息傳遞功能。

：球：瞭解[本頁](../dev/architecture.md)中的事務性消息傳遞體系結構。

## 定義權限

若要為Adobe雲端托管的訊息中心執行例項建立新使用者，您必須聯絡Adobe客戶服務。 消息中心用戶是需要專用權限才能訪問「即時事件」(nmsRtEvent)資料夾的特定操作員。

## 架構擴充功能

**消息中心技術工作流**&#x200B;在控制或執行實例上對方案執行的所有方案擴展都必須複製到Adobe Campaign事務消息模組使用的其他實例上。

:arrow_upper_right:在[Campaign Classic文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/instance-configuration/technical-workflows.html?lang=en#control-instance-workflows)中進一步瞭解消息中心技術工作流

## 傳送交易推播通知

當與行動應用程式頻道模組結合時，交易訊息可讓您透過行動裝置上的通知來推播交易訊息。

:arrow_upper_right:行動應用程式頻道詳見[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages)。

若要傳送交易推播通知，您必須執行下列設定：

1. 將&#x200B;**行動應用程式頻道**&#x200B;套件安裝至控制項和執行例項。

   >[!CAUTION]
   >
   >在安裝新的Campaign內建套件之前，請先檢查您的授權合約。

1. 在執行實例上複製&#x200B;**Mobile application**&#x200B;服務和相關的移動應用程式。

為了讓促銷活動傳送交易推播通知，事件必須包含下列元素：

* 行動裝置ID:**Android的registrationId**&#x200B;和iOS的&#x200B;**deviceToken**。 此ID代表通知要傳送至的「位址」。
* 指向行動應用程式的連結或整合金鑰(**uuid**)，可讓您擷取應用程式的特定連線資訊。
* 通知要傳送到的頻道(**whishedChannel**):iOS為41,Android為42。
* 其他資料，以利個人化。

以下是包含此資訊之事件的範例：

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

