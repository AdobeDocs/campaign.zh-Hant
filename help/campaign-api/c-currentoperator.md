---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 9%
---
# CurrentOperator （類別）

包含目前運運算元（名稱、識別碼、許可權等）相關資訊的物件。

此類別有單一執行個體，可存取應用程式伺服器的特定屬性。 這個單一專案可透過`application`全域變數的屬性存取。

範例：

```text
var operator = application.operator logInfo("login: " + operator.login) logInfo("id: " + operator.id) logInfo("description: " + operator.computeString) logInfo("=== Groups ===") for each(var id in operator.groups) logInfo(id) logInfo("=== Rights ===") for each(var right in operator.rights) logInfo(right)
```

## 方法

| 方法 | 說明 |
| --- | --- |
| [hasRight](m-currentoperator-hasright.md) | 測試運運算元是否有特定的已命名許可權。 |

## 屬性

| 屬性 | 說明 |
| --- | --- |
| [登入](p-currentoperator-login.md) | 傳回目前運運算元的登入。 |
| [id](p-currentoperator-id.md) | 傳回目前運運算元的內部識別碼。 |
| [computeString](p-currentoperator-computestring.md) | 傳回目前運運算元說明字串。 依預設，這是運運算元的名稱，隨後是運運算元的登入。 |
| [群組](p-currentoperator-groups.md) | 傳回目前運運算元群組中的識別碼清單。 |
| [權利](p-currentoperator-rights.md) | 傳回目前操作員的許可權清單。 |
| [時區](p-currentoperator-timezone.md) | 傳回目前運運算元使用的時區名稱。 |
| [首頁](p-currentoperator-home.md) | 傳回目前運運算元的根資料夾名稱。 |

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
