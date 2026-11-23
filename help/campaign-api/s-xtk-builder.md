---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 73%
---
# 產生器

應用程式伺服器的產生服務

## 方法

| 方法 | 說明 |
| --- | --- |
| [BuildOutputNavTree](sm-builder-buildoutputnavtree.md) | 將在資料庫中找到的導覽樹狀結構定義與參數中給定的導覽樹狀結構定義合併。 |
| [BuildOutputSchema](sm-builder-buildoutputschema.md) | 從來源結構描述中產生結構描述。 |
| [BuildSchema](sm-builder-buildschema.md) | 從來源結構描述中產生結構描述。 |
| [BuildSchemaFromId](sm-builder-buildschemafromid.md) | 從來源結構描述識別碼中產生結構描述。 |
| [BuildSqlSchemaDiff](sm-builder-buildsqlschemadiff.md) | 產生描述實際資料庫結構和其邏輯描述之間差異的文件。 |
| [BuildUpdateOneSchemaDiff](sm-builder-buildupdateoneschemadiff.md) | 產生描述實體資料庫中的表格與此表格的邏輯描述之間差異的文件。 |
| [BuildUpdateSchemaDiff](sm-builder-buildupdateschemadiff.md) | 產生描述實際資料庫結構和其邏輯描述之間差異的文件。 |
| [檢查資料表存在](sm-builder-checktableexists.md) | 驗證資料庫中是否存在表格 |
| [CreateDb](sm-builder-createdb.md) | 建立資料庫 |
| [EvaluateJavaScript](sm-builder-evaluatejavascript.md) | 評估 JavaScript 程式碼。 |
| [EvaluateJavaScriptTemplate](sm-builder-evaluatejavascripttemplate.md) | JavaScript 範本 (JST) 評估。 |
| [ExecSql](sm-builder-execsql.md) | 執行 SQL 陳述式 |
| [ExecSqlScript](sm-builder-execsqlscript.md) | 執行 SQL 指令碼 |
| [GenCreateDbDDL](sm-builder-gencreatedbddl.md) | 產生用於建立資料庫結構的 SQL 指令碼。 |
| [GenCreateOrUpdateSchemaSequenceDDL](sm-builder-gencreateorupdateschemasequenceddl.md) | 產生用於建立或更新 autoPk 結構描述序列的 SQL 指令碼 |
| [GenerateNavTree](sm-builder-generatenavtree.md) | 合併所有導覽樹狀結構定義，並將結果儲存為&#39;xtk:merged&#39;。 |
| [GenerateSchema](sm-builder-generateschema.md) | 使用高層級參數來產生結構描述程式碼。 |
| [GetDbParams](sm-builder-getdbparams.md) | 擷取資料來源的目前引數。 |
| [GetDefaultNamespace](sm-builder-getdefaultnamespace.md) | 檢索預設命名空間。 |
| [InstallPackage](sm-builder-installpackage.md) | 安裝套件。 |
| [InstallPackageImpl](sm-builder-installpackageimpl.md) | 安裝套件 (內部方法，請勿使用)。 |
| [InstallVendorPackages](sm-builder-installvendorpackages.md) | 安裝一個或多個標準套件。 |
| [RemoveSchemaLinkRef](sm-builder-removeschemalinkref.md) | 移除結構描述和參考它的反向連結。 |
| [ResolvePackageReference](sm-builder-resolvepackagereferences.md) | 解決套件中的相依性 |
| [UpdateDb](sm-builder-updatedb.md) | 資料庫結構更新。 |
| [UpdateSchemaFromDatabase](sm-builder-updateschemafromdatabase.md) | 根據結構描述在資料庫中的實際表示，更新該結構描述。 |
| [UpdateTempSchemasFromDatabase](sm-builder-updatetempschemasfromdatabase.md) | 根據結構描述在資料庫中的實際表示，更新結構描述集合。 |

## 泛型方法

| 方法 | 說明 |
| --- | --- |
| [建立](f-create.md) | 建立與指定結構描述對應的新實體。 |
| [載入](f-load.md) | 載入並傳回與指定結構描述和索引鍵對應的實體。 |
| [儲存](m-entity-save.md) | 將實體儲存在資料庫中。 |
