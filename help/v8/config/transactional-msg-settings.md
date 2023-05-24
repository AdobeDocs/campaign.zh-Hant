---
title: Campaign異動訊息設定
description: Campaign異動訊息設定
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

異動訊息（訊息中心）是用於管理觸發式訊息的Campaign模組。 進一步瞭解中的異動訊息傳送 [本節](../send/transactional.md).

瞭解中的交易式傳訊架構 [此頁面](../architecture/architecture.md#transac-msg-archi).

![](../assets/do-not-localize/speech.png) 身為Managed Cloud Services使用者， [連絡人Adobe](../start/campaign-faq.md#support) 在您的環境中安裝和設定Campaign異動訊息。

## 定義許可權

若要為Adobe Cloud上託管的訊息中心執行例項建立新使用者，您需要聯絡Adobe客戶服務。 訊息中心使用者是特定的操作者，需要專用許可權才能存取「即時事件」(nmsRtEvent)資料夾。

## 結構描述延伸模組

在使用的結構描述上進行的所有結構描述擴充功能 [訊息中心技術工作流程](#technical-workflows) 在Adobe Campaign異動訊息模組使用的其他執行個體上，需要複製控制或執行執行個體。

## 傳送異動推播通知

合併時 [行動應用程式頻道模組](../send/push.md)，異動訊息可讓您透過行動裝置上的通知推送異動訊息。

若要傳送異動推播通知，您必須執行下列設定：

1. 安裝 **行動應用程式頻道** 封裝至控制和執行執行個體。

   >[!CAUTION]
   >
   >在安裝新的Campaign內建套件之前，請檢查您的授權合約。

1. 復寫 **行動應用計畫** 以及執行例項上關聯的行動應用程式。

此外，事件必須包含下列元素：

* 行動裝置ID： **registrationId** 適用於Android和 **deviceToken** 適用於iOS。 此ID代表傳送通知的「地址」。
* 行動應用程式或整合金鑰的連結(**uuid**)，可讓您擷取應用程式的特定連線資訊。
* 通知將傳送到的頻道(**Wisdechannel**)：41適用於iOS，42適用於Android。
* 任何其他個人化資料。

以下是傳送異動推播通知的事件設定範例：

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

您可以調整部署精靈設定，以設定資料在資料庫中儲存的時間長度。

事件清除會由 **資料庫清理** 技術工作流程。 此工作流程會清除在執行例項上接收和儲存的事件，以及控制例項上封存的事件。

視需要使用箭頭來變更清除設定 **事件** （在執行例項上）和 **已封存的事件** （在控制例項上）。


## 技術工作流程 {#technical-workflows}

在部署任何交易式訊息範本之前，您必須確保已啟動控制項和執行例項上的技術工作流程。

接著，您就可以從以下位置存取這些工作流程： **管理>生產>訊息中心** 資料夾。

### 控制例項工作流程 {#control-instance-workflows}

在控制執行個體上，您必須為每個執行個體建立一個封存工作流程 **[!UICONTROL Message Center execution instance]** 外部帳戶。 按一下 **[!UICONTROL Create the archiving workflow]** 按鈕來建立和啟動工作流程。

### 執行例項工作流程 {#execution-instance-workflows}

在執行例項上，您必須開始以下技術工作流程：

* **[!UICONTROL Processing batch events]** (內部名稱： **[!UICONTROL batchEventsProcessing]** )：此工作流程可讓您在佇列中劃分批次事件，然後再將其連結至訊息範本。
* **[!UICONTROL Processing real time events]** (內部名稱： **[!UICONTROL rtEventsProcessing]** )：此工作流程可讓您在佇列中的即時事件連結至訊息範本之前，先加以劃分。
* **[!UICONTROL Update event status]** (內部名稱： **[!UICONTROL updateEventStatus]** )：此工作流程可讓您將狀態歸因於事件。

   可能的事件狀態包括：

   * **[!UICONTROL Pending]**：事件在佇列中。 尚未為其指派訊息範本。
   * **[!UICONTROL Pending delivery]**：事件在佇列中，已指派訊息範本給該事件，並由傳遞處理。
   * **[!UICONTROL Sent]**：此狀態是從傳送記錄檔複製而來。 這表示傳遞已傳送。
   * **[!UICONTROL Ignored by the delivery]**：此狀態是從傳送記錄檔複製而來。 這表示會由傳送忽略。
   * **[!UICONTROL Delivery failed]**：此狀態是從傳送記錄檔複製而來。 這表示傳送失敗。
   * **[!UICONTROL Event not taken into account]**：無法將事件連結至訊息範本。 將不會處理事件。
