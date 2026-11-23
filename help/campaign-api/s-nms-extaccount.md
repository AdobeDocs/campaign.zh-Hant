---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 53%
---
# extAccount

外部帳戶（電子郵件、簡訊……）的定義 由模組使用

## 方法

| 方法 | 說明 |
| --- | --- |
| [CreateFDASchema](sm-extaccount-createfdaschema.md) | 在資料庫中建立工作結構描述 |
| [DeclareTableSpace](sm-extaccount-declaretablespaces.md) | 在 Adobe Campaign 資料庫中宣告選項，這些選項是使用可透過外部帳戶存取的遠端資料庫中的特定表格空間所必需。 |
| [DeploySQLFunctions](sm-extaccount-deploysqlfunctions.md) | 在遠端 RDBMS 伺服器上部署 Adobe Campaign 同盟資料存取所需的功能 |
| [測試帳戶](sm-extaccount-testaccount.md) | 執行連線測試 |

## 泛型方法

| 方法 | 說明 |
| --- | --- |
| [建立](f-create.md) | 建立與指定結構描述對應的新實體。 |
| [載入](f-load.md) | 載入並傳回與指定結構描述和索引鍵對應的實體。 |
| [儲存](m-entity-save.md) | 將實體儲存在資料庫中。 |
