---
title: 市場活動事務性消息傳遞設定
description: 市場活動事務性消息傳遞設定
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

事務性消息傳遞（消息中心）是一個市場活動模組，用於管理觸發的消息。 瞭解有關中事務性消息傳遞的詳細資訊 [此部分](../send/transactional.md)。

瞭解中的事務性消息傳遞體系結構 [此頁](../architecture/architecture.md#transac-msg-archi)。

![](../assets/do-not-localize/speech.png) 作為托管Cloud Services用戶， [聯繫人Adobe](../start/campaign-faq.md#support) 在您的環境中安裝和配置市場活動事務性消息傳遞。

## 定義權限

要為托管在Adobe雲上的消息中心執行實例建立新用戶，您需要與Adobe客戶服務部門聯繫。 消息中心用戶是需要專用權限才能訪問「即時事件」(nmsRtEvent)資料夾的特定運算子。

## 架構擴展

對使用的架構進行的所有架構擴展 [消息中心技術工作流](#technical-workflows) 在控制或執行實例上，需要在Adobe Campaign事務性消息傳遞模組使用的其他實例上進行複製。

## 發送事務推送通知

與 [移動應用頻道模組](../send/push.md)，事務性消息傳遞使您能夠通過移動設備上的通知推送事務性消息。

要發送事務推式通知，您需要執行以下配置：

1. 安裝 **移動應用頻道** 包到控制項和執行實例上。

   >[!CAUTION]
   >
   >在安裝新的市場活動內置軟體包之前，請檢查您的許可協定。

1. 複製 **移動應用** 執行實例上的服務和關聯的移動應用。

此外，事件必須包含以下元素：

* 移動設備ID: **註冊ID** 適用於Android和 **設備令牌** iOS。 此ID表示通知發送到的「地址」。
* 到移動應用程式或整合密鑰的連結(**UU**)，用於檢索特定於應用程式的連接資訊。
* 將通知發送到的通道(**希望頻道**):iOS41，安卓42。
* 任何其他個性化資料。

下面是發送事務推式通知的事件配置示例：

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

您可以調整部署嚮導設定以配置資料在資料庫中儲存的時間。

事件清除由 **資料庫清理** 技術工作流。 此工作流清除在執行實例上接收和儲存的事件以及在控制實例上存檔的事件。

根據需要使用箭頭來更改 **事件** （在執行實例上）和 **存檔事件** （在控制實例上）。


## 技術工作流程 {#technical-workflows}

在部署任何事務性消息模板之前，必須確保已啟動控制和執行實例上的技術工作流。

然後，可以從 **管理>生產>消息中心** 的子菜單。

### 控制實例工作流 {#control-instance-workflows}

在控制項實例上，必須為每個實例建立一個存檔工作流 **[!UICONTROL Message Center execution instance]** 外部帳戶。 按一下 **[!UICONTROL Create the archiving workflow]** 按鈕，將選定控制項在Tab鍵次序中下移一個位置。

### 執行實例工作流 {#execution-instance-workflows}

在執行實例上，必須啟動以下技術工作流：

* **[!UICONTROL Processing batch events]** (內部名稱： **[!UICONTROL batchEventsProcessing]** ):通過此工作流，您可以在將批處理事件連結到消息模板之前，先在隊列中分解這些事件。
* **[!UICONTROL Processing real time events]** (內部名稱： **[!UICONTROL rtEventsProcessing]** ):通過此工作流，您可以在將即時事件連結到消息模板之前，先在隊列中分解它們。
* **[!UICONTROL Update event status]** (內部名稱： **[!UICONTROL updateEventStatus]** ):此工作流允許您將狀態屬性化到事件。

   可能的事件狀態包括：

   * **[!UICONTROL Pending]**:事件在隊列中。 尚未為其指派訊息範本。
   * **[!UICONTROL Pending delivery]**:該事件在隊列中，已為其分配消息模板，並且正在由傳遞處理該模板。
   * **[!UICONTROL Sent]**:此狀態從交貨日誌中複製。 這意味著送貨已經寄出。
   * **[!UICONTROL Ignored by the delivery]**:此狀態從交貨日誌中複製。 這表示會由傳送忽略。
   * **[!UICONTROL Delivery failed]**:此狀態從交貨日誌中複製。 這表示傳送失敗。
   * **[!UICONTROL Event not taken into account]**:無法將事件連結到消息模板。 將不會處理事件。
