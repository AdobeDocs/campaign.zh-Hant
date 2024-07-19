---
title: Campaign異動訊息設定
description: Campaign異動訊息設定
feature: Transactional Messaging
role: Admin, Developer
level: Experienced
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 4%

---

# 交易型訊息設定 {#mc-settings}

異動訊息（訊息中心）是專為管理觸發式訊息而設計的Campaign模組。 在[本節](../send/transactional.md)中進一步瞭解異動訊息。

瞭解[此頁面](../architecture/architecture.md#transac-msg-archi)中的交易式傳訊架構。


>[!NOTE]
>
>Cloud Service作為Managed Campaign使用者，[聯絡Adobe](../start/campaign-faq.md#support)以在您的環境中安裝和設定Campaign交易訊息。

## 定義許可權 {#mc-permissions}

若要為Adobe雲端上託管的訊息中心執行例項建立新使用者，請聯絡您的Adobe轉換經理。 訊息中心使用者是特定的操作者，需要專用許可權才能存取「即時事件」(nmsRtEvent)資料夾。

## 結構描述延伸  {#mc-schema-ext}

在[Message Center技術工作流程](#technical-workflows)於控制項或執行執行個體所使用的結構描述上建立的所有結構描述延伸，都必須在Adobe Campaign異動訊息模組使用的其他執行個體上複製。

## 傳送異動推播通知 {#mc-transactional-push}

與[行動應用程式頻道模組](../send/push.md)結合時，交易式訊息可讓您透過行動裝置上的通知推播交易式訊息。

若要傳送異動推播通知，您必須執行下列設定：

1. 將&#x200B;**行動應用程式通道**&#x200B;套件安裝至控制和執行執行個體。

   >[!CAUTION]
   >
   >在安裝新的Campaign內建套件之前，請檢查您的授權合約。

1. 在執行例項上復寫&#x200B;**行動應用程式**&#x200B;服務和關聯的行動應用程式。

此外，事件必須包含下列元素：

* 行動裝置ID：Android的&#x200B;**registrationId**&#x200B;和iOS的&#x200B;**deviceToken**。 此ID代表傳送通知的「地址」。
* 行動應用程式或整合金鑰的連結(**uuid**)，可讓您擷取應用程式的特定連線資訊。
* 通知將傳送至的頻道(**wishedChannel**)： 41適用於iOS，42適用於Android。
* 任何其他個人化資料。

以下是傳送異動推播通知的事件設定範例：

```xml
<SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
     <urn:PushEvent>
         <urn:sessiontoken>mc/</urn:sessiontoken>
         <urn:domEvent>

              <rtEvent wishedChannel="41" type="DELIVERY" registrationToken="2cefnefzef758398493srefzefkzq483974">
                <mobileApp _operation="none" uuid="com.adobe.NeoMiles"/>
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

## 清除事件 {#purge-events}

您可以調整部署精靈設定，以設定資料在資料庫中儲存的時間長度。

事件清除是由&#x200B;**資料庫清理**&#x200B;技術工作流程自動執行。 此工作流程會清除在執行例項上接收並儲存的事件，以及在控制例項上封存的事件。

視情況使用箭號來變更&#x200B;**事件** （在執行執行個體上）和&#x200B;**封存事件** （在控制執行個體上）的清除設定。


## 技術工作流程 {#technical-workflows}

在部署任何異動訊息範本之前，您必須確保已啟動控制和執行執行個體的技術工作流程。

然後可以從&#x200B;**管理>生產>訊息中心**&#x200B;資料夾存取這些工作流程。

### 控制例項工作流程 {#control-instance-workflows}

在控制執行個體上，您必須為每個&#x200B;**[!UICONTROL Message Center execution instance]**&#x200B;外部帳戶建立一個封存工作流程。 按一下&#x200B;**[!UICONTROL Create the archiving workflow]**&#x200B;按鈕以建立及啟動工作流程。

### 執行例項工作流程 {#execution-instance-workflows}

在執行例項上，您必須開始以下技術工作流程：

* **[!UICONTROL Processing batch events]** （內部名稱： **[!UICONTROL batchEventsProcessing]** ）：此工作流程可讓您在佇列中劃分批次事件，然後再連結至訊息範本。
* **[!UICONTROL Processing real time events]** （內部名稱： **[!UICONTROL rtEventsProcessing]** ）：此工作流程可讓您在佇列中的即時事件連結至訊息範本之前，劃分這些事件。
* **[!UICONTROL Update event status]** （內部名稱： **[!UICONTROL updateEventStatus]** ）：此工作流程可讓您將狀態歸因於事件。

  可能的事件狀態包括：

   * **[!UICONTROL Pending]**：事件在佇列中。 尚未為其指派訊息範本。
   * **[!UICONTROL Pending delivery]**：事件在佇列中，已指派訊息範本給該事件，並由傳遞處理。
   * **[!UICONTROL Sent]**：此狀態是從傳遞記錄檔複製而來。 這表示傳送已進行。
   * **[!UICONTROL Ignored by the delivery]**：此狀態是從傳遞記錄檔複製而來。 這表示會由傳送忽略。
   * **[!UICONTROL Delivery failed]**：此狀態是從傳遞記錄檔複製而來。 這表示傳送失敗。
   * **[!UICONTROL Event not taken into account]**：事件無法連結至訊息範本。 將不會處理事件。
