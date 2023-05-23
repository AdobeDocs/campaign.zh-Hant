---
title: 新市場活動v8 API
description: 新市場活動v8 API
feature: API, FFDA
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: dd822f88-b27d-4944-879c-087f68e79825
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 2%

---

# 特定FFDA市場活動API{#gs-new-api}

在 [企業(FDA)部署](enterprise-deployment.md), Campaign v8附帶了兩個特定的API，用於管理Campaign本地資料庫和雲資料庫之間的資料。 使用它們的先決條件是在架構上啟用轉移機制。 [了解更多](staging.md)

* 接收API: **xtk.session.ingest**

   此API僅專用於資料插入。 [了解更多](#data-insert-api)

* 資料更新/刪除API: **xtk.session.ingestExt**

   此API用於更新或刪除資料。 [了解更多](#data-update-api)

專用的內置工作流將同步雲資料庫中的資料。

## 插入資料{#data-insert-api}

的 **xtk.session.ingest** API僅專用於資料插入。 無更新/刪除。

### 插入時無對帳{#insert-no-reconciliation}

**在工作流中**

在 **Javascript代碼** 在雲資料庫中插入資料而不進行協調的活動：

```
var xmlStagingSampleTable = <sampleTableStg
                                testcol1="testValue1"
                                testcol2="testValue2"
                                xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;
strUuid = xtk.session.Ingest(xmlStagingSampleTable);
logInfo(strUuid);
```

執行工作流後，將按照預期饋送臨時表。

**從SOAP調用**

1. 獲取身份驗證令牌。
1. 觸發API。 負載為：

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:Ingest>
           <urn:sessiontoken>___xxxxxxx-xxxx-xxx-xxx-xxxxxxxxxxx</urn:sessiontoken>
           <urn:domDoc>
               <sampleTableStg
                   testcol1="Test Value 1 (from SOAP)"
                   testcol2="Test Value 2 (from SOAP)"
                   xtkschema="dem:sampleTableStg">
               </sampleTableStg>
           </urn:domDoc>
       </urn:Ingest>
   </soapenv:Body>
   </soapenv:Envelope>
   ```

1. UUID將發回到SOAP響應：

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default">
           <pstrSUuids xsi:type="xsd:string">e1e7c8b3-6f79-44da-a72d-49ed0f73db2c</pstrSUuids>
       </IngestResponse>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

因此，按照預期饋送臨時表。

![](assets/no-reconciliation.png)

### 插入並協調

**在工作流中**

在 **Javascript代碼** 活動，在雲資料庫中插入資料，並進行協調：

```
var xmlStagingSampleTable = <sampleTableStg  _key="@id" id="ABC12345"
                              testcol1="testValue1"
                              testcol2="testValue2"
                              xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;         
strUuid = xtk.session.Ingest(xmlStagingSampleTable);
logInfo(strUuid);
```

執行工作流後，將按照預期饋送臨時表。

![](assets/with-reconciliation.png)


**從SOAP調用**

1. 獲取身份驗證令牌。
1. 觸發API。 負載為：

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
     <urn:Ingest>
        <urn:sessiontoken>___5e71f4bf-d38a-4ba8-ac15-35a958f7f138</urn:sessiontoken>
        <urn:domDoc>
           <sampleTableStg  _key="@id" id="ABDCD321"
                testcol1="Test Value 1 (from SOAP)"
                testcol2="Test Value 2 (from SOAP)"
                xtkschema="dem:sampleTableStg">
            </sampleTableStg>
        </urn:domDoc>
     </urn:Ingest>
    </soapenv:Body>
   </soapenv:Envelope>
   ```

1. 在這種情況下， UUID不會返回到響應，因為它在負載中已提供。 回應是：

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default">
           <pstrSUuids xsi:type="xsd:string"/>
       </IngestResponse>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

因此，按照預期饋送臨時表。

## 更新或刪除資料{#data-update-api}

的 **xtk.session.IngestExt** API被優化用於資料更新/刪除。 僅用於插入，首選 **xtk.session.ingest**。 插入正在處理記錄密鑰是否不在臨時表中。

### 插入/更新

**在工作流中**

在 **Javascript代碼** 更新雲資料庫中資料的活動：

```
var xmlStagingRecipient = <sampleTableStg  _key="@id" id="ABC12345"
                              testcol1="testValue A (updated)"
                              testcol2="testValue B (updated)"
                              xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;
xtk.session.IngestExt(xmlStagingRecipient);
```

執行工作流後，將按預期更新臨時表。

![](assets/updated-data.png)

**從SOAP調用**

1. 獲取身份驗證令牌。
1. 觸發API。 負載為：

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:IngestExt>
           <urn:sessiontoken>___444cd168-a1e2-4fb6-a2a8-73be9f133489</urn:sessiontoken>
           <urn:domDoc>
           <sampleTableStg  _key="@id" id="ABDCD321"
                   testcol1="Test Value E (from SOAP)"
                   testcol2="Test Value F (from SOAP)"
                   xtkschema="dem:sampleTableStg">
               </sampleTableStg>
           </urn:domDoc>
       </urn:IngestExt>
   </soapenv:Body>
   </soapenv:Envelope>
   ```

1. SOAP響應為：

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestExtResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default"/>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

因此，將按照預期更新臨時表。

## 訂閱管理 {#sub-apis}

市場活動中的訂閱管理如中所述 [此頁](../start/subscriptions.md)。

訂閱和取消訂閱資料的插入依賴於 [分級機構](staging.md) 在市場活動本地資料庫中。 訂閱者資訊臨時儲存在本地資料庫的臨時表中，同步工作流將此資料從本地資料庫發送到雲資料庫。 因此，訂閱和取消訂閱進程 **非同步**。 選擇加入和選擇退出請求每小時都通過特定的技術工作流進行處理。 [了解更多](replication.md#tech-wf)


**相關主題**

* [Campaign JSAPI](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html){target="_blank"}
