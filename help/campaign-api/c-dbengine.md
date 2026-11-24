---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 4%
---
# DBEngine （類別）

代表資料庫連線。

此物件可讓您查詢資料庫並執行相關作業。

此類別中的大部分方法都需要&#39;sql&#39;許可權。 如果運運算元叫用方法但沒有適當的許可權，則會引發例外狀況。 一般而言，所有變更資料庫的方法都需要&#39;sql&#39;許可權，而只是檢視資訊的方法則否。 請參閱每種方法的檔案，以瞭解是否需要許可權。

## 方法

| 方法 | 說明 |
| --- | --- |
| [batchDelete](m-dbengine-batchdelete.md) | 依封包刪除表格的記錄。 |
| [處置](m-dbengine-dispose.md) | 將連線從連結到它的所有資源中釋放。 |
| [執行](m-dbengine-execute.md) | 執行SQL命令。 |
| [執行](m-dbengine-exec.md) | 執行命令的別名。 此函式已過時，請使用[execute()](m-dbengine-execute.md) |
| [查詢](m-dbengine-query.md) | 執行SELECT型別SQL查詢。 |
| [queryWithTypes](m-dbengine-querywithtypes.md) | 執行具有資料行型別規格的SELECT型別SQL查詢。 |
| [開始](m-dbengine-begin.md) | 在連線上開始新的交易。 |
| [認可](m-dbengine-commit.md) | 核准連線上進行中的交易。 |
| [回覆](m-dbengine-rollback.md) | 取消連線上進行中的交易。 |

## 屬性

| 屬性 | 說明 |
| --- | --- |
| [是Oracle](p-dbengine-isoracle.md) | 如果資料庫是Oracle，則傳回true。 |
| [isDB2](p-dbengine-isdb2.md) | 如果資料庫為DB2型別，則傳回true。 |
| [isMySQL](p-dbengine-ismysql.md) | 如果資料庫為MySQL型別，則傳回true。 |
| [isMSSQL](p-dbengine-ismssql.md) | 如果資料庫是SQL Server，則傳回true。 |
| [isPostgreSQL](p-dbengine-ispostgresql.md) | 如果資料庫為PostgreSQL，則傳回true。 |
| [isSybase](p-dbengine-issybase.md) | 如果資料庫是Sybase，則傳回true。 |
| [isSybaseIQ](p-dbengine-issybaseiq.md) | 如果資料庫是Sybase IQ，則傳回true。 |
| [isFDA](p-dbengine-isfda.md) | 如果透過FDA存取資料庫，則傳回true。 |
| [isBroken](p-dbengine-isbroken.md) | 如果連線不再可用，則傳回true。 |
| [useUnicodeData](p-dbengine-useunicodedata.md) | 如果資料庫包含Unicode資料，則傳回True。 |
| [useNChar](p-dbengine-usenchar.md) | 如果Adobe Campaign使用NCHAR、NVARCHAR、NCLOB、NTEXT型別欄位，則傳回true。 |

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
