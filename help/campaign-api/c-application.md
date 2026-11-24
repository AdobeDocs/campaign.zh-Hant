---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 6%
---
# 應用程式（類別）

此類別有單一執行個體，可存取應用程式伺服器的特定屬性。 這個單一可以透過`application`全域變數存取。

## 方法

| 方法 | 說明 |
| --- | --- |
| [hasPackage](m-application-haspackage.md) | 測試是否已安裝套件。 |
| [getSchema](m-application-getschema.md) | 傳回與Adobe Campaign結構描述的對應，如果結構描述不存在，則傳回null。 |
| [getDBMSType](m-application-getdbmstype.md) | 傳回資料庫的伺服器型別。 |
| [getNewIds](m-application-getnewids.md) | 傳回內部資料庫金鑰的ID清單。 |
| [getConnection](m-application-getconnection.md) | 傳回資料庫伺服器的新連線。 |
| [getTimezoneJson](m-application-gettimezonejson.md) | 傳回字元字串，此字元是時間差異清單的JSON表示法，與UTC時間及其開始日期的時區比較，是UNIX期間。 |
| [登入](m-application-onlog.md) | 針對寫入日誌的訊息新增或刪除攔截函式 |
| [onTrace](m-application-ontrace.md) | 新增或刪除追蹤訊息攔截函式。 |

## 屬性

| 屬性 | 說明 |
| --- | --- |
| [buildNumber](p-application-buildnumber.md) | 傳回應用程式伺服器的組建編號。 |
| [執行個體名稱](p-application-instancename.md) | 執行指令碼的執行個體名稱。 |
| [instanceVarDir](p-application-instancevardir.md) | 執行指令碼之執行個體的「var」目錄的完整路徑。 |
| [instanceUploadDir](p-application-instanceuploaddir.md) | 執行指令碼之執行個體的「上傳」目錄的完整路徑。 |
| [運運算元](p-application-operator.md) | 傳回包含目前運運算元（名稱、識別碼、許可權等）相關資訊的物件。 |
| [地區設定](p-application-locale.md) | 傳回符合實體Local的字元字串。 |

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
