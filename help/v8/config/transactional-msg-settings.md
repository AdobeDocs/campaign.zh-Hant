---
title: 市場活動事務性消息傳遞設定
description: 市場活動事務性消息傳遞設定
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 0%

---

# 異動訊息設定

![](../assets/do-not-localize/speech.png)  作為托管Cloud Services用戶， [聯繫人Adobe](../start/campaign-faq.md#support) 在您的環境中安裝和配置市場活動事務性消息傳遞。

![](../assets/do-not-localize/glass.png) 事務性消息傳遞功能詳見 [此部分](../send/transactional.md)。

![](../assets/do-not-localize/glass.png) 瞭解中的事務性消息傳遞體系結構 [此頁](../dev/architecture.md)。

## 定義權限

要為托管在Adobe雲上的消息中心執行實例建立新用戶，您需要與Adobe客戶服務部門聯繫。 消息中心用戶是需要專用權限才能訪問「即時事件」(nmsRtEvent)資料夾的特定運算子。

## 架構擴展

對使用的架構進行的所有架構擴展 **消息中心技術工作流** 在控制或執行實例上，需要在Adobe Campaign事務性消息傳遞模組使用的其他實例上進行複製。

![](../assets/do-not-localize/book.png) 瞭解有關消息中心技術工作流的詳細資訊 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/configure-transactional-messaging/additional-configurations.html#technical-workflows)

## 發送事務推送通知

與移動應用通道模組結合使用時，事務性消息傳遞使您能夠通過移動設備上的通知推送事務性消息。

![](../assets/do-not-localize/book.png) Mobile應用頻道詳見 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages)。

要發送事務推式通知，您需要執行以下配置：

1. 安裝 **移動應用頻道** 包到控制項和執行實例上。

   >[!CAUTION]
   >
   >在安裝新的市場活動內置軟體包之前，請檢查您的許可協定。

1. 複製 **Mobile應用** 執行實例上的服務和關聯的移動應用。

為使市場活動能夠發送事務性推式通知，事件必須包含以下元素：

* 移動設備ID: **註冊ID** 適用於Android和 **設備令牌** iOS。 此ID表示通知將發送到的「地址」。
* 到移動應用程式或整合密鑰的連結(**UU**)，用於檢索特定於應用程式的連接資訊。
* 將通知發送到的通道(**希望頻道**):iOS41，安卓42。
* 用於個性化的其他資料。

下面是包含此資訊的事件的示例：

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
