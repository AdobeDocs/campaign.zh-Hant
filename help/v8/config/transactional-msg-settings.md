---
title: Campaign交易式訊息設定
description: Campaign交易式訊息設定
feature: Transactional Messaging
role: Admin, Developer
level: Intermediate, Experienced
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: 3c7455f348468a8f00fb853a3269a1d63b81e7b8
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 5%

---

# 異動訊息設定

交易式訊息（訊息中心）是專為管理觸發訊息而設計的Campaign模組。 進一步了解交易式訊息 [本節](../send/transactional.md).

了解 [本頁](../architecture/architecture.md#transac-msg-archi).

![](../assets/do-not-localize/speech.png) 作為托管Cloud Services用戶， [連絡Adobe](../start/campaign-faq.md#support) 若要在您的環境中安裝及設定Campaign交易式訊息。

## 定義權限

若要為托管於Adobe雲端的訊息中心執行例項建立新使用者，您需要聯絡Adobe客戶服務。 訊息中心使用者是需要專用權限才能存取「即時事件」(nmsRtEvent)資料夾的特定運算子。

## 結構擴充功能

對使用的結構進行的所有架構擴充功能 [訊息中心技術工作流程](#technical-workflows) 控制或執行例項必須重複於Adobe Campaign交易式訊息模組所使用的其他例項。

## 傳送交易式推播通知

結合時 [行動應用程式頻道模組](../send/push.md)，交易式訊息可讓您透過行動裝置上的通知推送交易式訊息。

若要傳送交易式推播通知，您必須執行下列設定：

1. 安裝 **行動應用程式頻道** 封裝至控制和執行執行個體。

   >[!CAUTION]
   >
   >安裝新的Campaign內建套件前，請先檢查您的授權合約。

1. 復寫 **行動應用程式** 執行例項上的服務及相關行動應用程式。

此外，事件必須包含下列元素：

* 行動裝置ID: **registrationId** 適用於Android和 **deviceToken** iOS。 此ID代表通知所要傳送到的「位址」。
* 行動應用程式或整合金鑰的連結(**uid**)，可讓您擷取應用程式的特定連線資訊。
* 將傳送通知的通道(**whiskChannel**):iOS為41,Android為42。
* 任何其他個人化資料。

以下是傳送交易式推播通知的事件設定範例：

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



## 清除事件 {#purge-events}

您可以調整部署嚮導設定，以配置資料儲存在資料庫中的時間。

事件清除會由 **資料庫清理** 技術工作流程。 此工作流程會清除在執行執行個體上收到和儲存的事件，以及封存在控制執行個體上的事件。

視需要使用箭頭來變更 **事件** （在執行執行個體上）和 **封存的事件** （在控制例項上）。


## 技術工作流程 {#technical-workflows}

部署任何交易式訊息範本之前，您必須確定控制和執行例項的技術工作流程已啟動。

然後，您就可以從 **管理>生產>訊息中心** 檔案夾。

### 控制執行個體工作流程 {#control-instance-workflows}

在控制實例上，必須為每個實例建立一個存檔工作流 **[!UICONTROL Message Center execution instance]** 外部帳戶。 按一下 **[!UICONTROL Create the archiving workflow]** 按鈕來建立和啟動工作流。

### 執行執行個體工作流程 {#execution-instance-workflows}

在執行例項上，您必須啟動下列技術工作流程：

* **[!UICONTROL Processing batch events]** (內部名稱： **[!UICONTROL batchEventsProcessing]** ):此工作流程可讓您在將批次事件連結至訊息範本之前，先劃分佇列中的批次事件。
* **[!UICONTROL Processing real time events]** (內部名稱： **[!UICONTROL rtEventsProcessing]** ):此工作流程可讓您在將佇列中的即時事件連結至訊息範本之前，先加以劃分。
* **[!UICONTROL Update event status]** (內部名稱： **[!UICONTROL updateEventStatus]** ):此工作流程可讓您將狀態歸因於事件。

   可能的事件狀態包括：

   * **[!UICONTROL Pending]**:事件在佇列中。 尚未為其指派訊息範本。
   * **[!UICONTROL Pending delivery]**:事件在佇列中，已指派訊息範本給該事件，並由傳送處理。
   * **[!UICONTROL Sent]**:此狀態是從傳送記錄檔複製而來。 這表示已傳送傳遞。
   * **[!UICONTROL Ignored by the delivery]**:此狀態是從傳送記錄檔複製而來。 這表示會由傳送忽略。
   * **[!UICONTROL Delivery failed]**:此狀態是從傳送記錄檔複製而來。 這表示傳送失敗。
   * **[!UICONTROL Event not taken into account]**:無法將事件連結到消息模板。 將不會處理事件。
