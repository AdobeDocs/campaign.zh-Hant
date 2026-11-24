---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 1%
---
# SchemaNode （類別）

代表結構描述的元素

## 方法

| 方法 | 說明 |
| --- | --- |
| [findNode](m-schemanode-findnode.md) | 傳回[SchemaNode](c-schemanode.md)的執行個體，如果節點不存在且mustExist引數設定為false，則傳回null。 |

## 屬性

| 屬性 | 說明 |
| --- | --- |
| [子項](p-schemanode-children.md) | 傳回物件，其中每個屬性都是根據其名稱編制索引的子節點。 |
| [computeString](p-schemanode-computestring.md) | 傳回由目前節點計算的字串。 |
| [資料原則](p-schemanode-datapolicy.md) | 傳回提供目前節點資料原則的字元字串。 |
| [描述](p-schemanode-description.md) | 傳回描述目前節點的字元字串。 |
| [defaultValue](p-schemanode-defaultvalue.md) | 傳回提供目前節點預設值的字元字串。 |
| [editType](p-schemanode-edittype.md) | 傳回字元字串，指定目前節點的編輯型別。 |
| [分項清單](p-schemanode-enumeration.md) | 傳回[Enumeration](c-enumeration.md)物件，此物件為連結至目前節點的列舉，如果沒有列舉，則為null。 |
| [列舉影像](p-schemanode-enumerationimage.md) | 以字串形式傳回目前節點的影像名稱。 |
| [folderModel](p-schemanode-foldermodel.md) | 只有在根節點上，才會傳回包含資料夾範本的字串。 在其他節點上，它會傳回undefined。 |
| [影像](p-schemanode-image.md) | 以字串形式傳回影像名稱。 |
| [完整性](p-schemanode-integrity.md) | 傳回連結完整性型別。 |
| [個金鑰](p-schemanode-keys.md) | 傳回含有目前節點[SchemaKey](c-schemakey.md)索引鍵之定義的資料表。 |
| [hasEnumeration](p-schemanode-hasenumeration.md) | 傳回布林值，指出目前節點的值是否已連結至分項清單。 |
| [childrenCount](p-schemanode-childrencount.md) | 傳回指定子節點數目的數字。 |
| [hasSQLTable](p-schemanode-hassqltable.md) | 傳回布林值，指出目前節點是否連結至SQL表格。 |
| [hasUserEnumeration](p-schemanode-hasuserenumeration.md) | 傳回布林值，指出目前節點的值是否連結至使用者分項清單。 |
| [說明](p-schemanode-help.md) | 傳回說明字元字串。 |
| [結構描述](p-schemanode-schema.md) | 傳回此節點的父[結構描述](c-schema.md)物件的執行個體。 |
| [isAdvanced](p-schemanode-isadvanced.md) | 傳回布林值，指出目前節點是否為進階節點。 |
| [isAnyType](p-schemanode-isanytype.md) | 傳回布林值，指出目前節點是否為普通節點。 |
| [isAttribute](p-schemanode-isattribute.md) | 傳回布林值，指出目前節點是否為屬性。 |
| [isAutoIncrement](p-schemanode-isautoincrement.md) | 傳回布林值，指出目前節點的值是否自動增加。 |
| [isAutoPK](p-schemanode-isautopk.md) | 傳回布林值，指出目前節點是否為主索引鍵。 |
| [isBlob](p-schemanode-isblob.md) | 傳回布林值，指出目前節點是否為BLOB。 |
| [isCalculated](p-schemanode-iscalculated.md) | 傳回布林值，指出目前節點的值是否為計算的結果。 |
| [isCDATA](p-schemanode-iscdata.md) | 傳回布林值，指出目前節點是否從CDATA型別XML對應。 |
| [isCollection](p-schemanode-iscollection.md) | 傳回布林值，指出目前節點是否為子元素和/或屬性的集合。 |
| [isDefaultOnDuplicate](p-schemanode-isdefaultonduplicate.md) | 傳回布林值。 如果新增的值是變數，則在記錄重複資料刪除期間，預設值（在defaultValue中定義）會在記錄期間自動重新套用。 |
| [isElementOnly](p-schemanode-iselementonly.md) | 傳回布林值，指出目前節點是否為架構的邏輯子分支。 |
| [isExternalJoin](p-schemanode-isexternaljoin.md) | 如果節點是連結且連線是外部的，則為True。 |
| [isFeature](p-schemanode-isfeature.md) | 傳回布林值，指出節點是否為功能。 |
| [isLink](p-schemanode-islink.md) | 傳回布林值，指出節點是否為連結。 |
| [isMappedAsXML](p-schemanode-ismappedasxml.md) | 傳回布林值，指出節點是否為XML對應。 |
| [isMemo](p-schemanode-ismemo.md) | 傳回布林值，指出目前的節點是否由備忘錄對應。 |
| [isMemoData](p-schemanode-ismemodata.md) | 傳回布林值，指出目前的節點是否由MemoData對應。 |
| [isNotNull](p-schemanode-isnotnull.md) | 傳回布林值，指出目前節點是否可考慮null值。 |
| [是必要的](p-schemanode-isrequired.md) | 傳回布林值，指出目前節點的值是否為必要值。 |
| [isRoot](p-schemanode-isroot.md) | 傳回布林值，指出節點是否為結構的根。 |
| [isSQL](p-schemanode-issql.md) | 傳回布林值，指出目前節點是否以SQL對應。 |
| [isTemporaryTable](p-schemanode-istemporarytable.md) | 傳回布林值，指出資料表是否為暫存資料表。 資料表不會在資料庫建立期間建立。 |
| [isUnbound](p-schemanode-isunbound.md) | 傳回布林值，指出目前節點是否有相同型別的無限子系。 |
| [isUser](p-schemanode-isuser.md) | 傳回布林值，指出節點是否為使用者型別。 |
| [joinParts](p-schemanode-joinparts.md) | 傳回SchemaNode執行個體的表格，其中每個元素代表聯結的條件。 |
| [標籤](p-schemanode-label.md) | 傳回字元字串，這是目前節點的說明。 |
| [名稱](p-schemanode-name.md) | 傳回字元字串，這是目前節點的名稱。 |
| [nodePath](p-schemanode-nodepath.md) | 傳回字元字串，這是目前節點的絕對路徑。 |
| [父系](p-schemanode-parent.md) | 傳回作為父物件的[SchemaNode](c-schemanode.md)物件，如果沒有，則傳回null。 |
| [PKSequence](p-schemanode-pksequence.md) | 傳回字元字串，該字元字串提供用於主鍵的序列名稱。 |
| [packageStatus](p-schemanode-packagestatus.md) | 傳回提供封裝狀態的數字。 |
| [reverseLink](p-schemanode-reverselink.md) | 如果元素是連結，會傳回代表反向連結（透過目標結構描述）的[SchemaNode](c-schemanode.md)物件。 如果沒有，則未定義屬性。 |
| [SQLName](p-schemanode-sqlname.md) | 欄位的SQL名稱。 如果物件不是SQL型別欄位，則屬性是空字串。 |
| [SQLTable](p-schemanode-sqltable.md) | 表格的SQL名稱。 如果物件不是主要元素，或如果結構描述對應不是SQL型別，則屬性是空字串。 |
| [大小](p-schemanode-size.md) | 字元字串型別的大小。 |
| [tableDefinition](p-schemanode-tabledefinition.md) | [SchemaNode](c-schemanode.md)的執行個體，這是包含目前節點的資料表描述，如果沒有執行個體則為Null。 |
| [目標](p-schemanode-target.md) | 連結目標之結構描述的主要元素。 如果物件不是連結，則不會定義屬性。 |
| [型別](p-schemanode-type.md) | 傳回提供目前節點值型別的字元字串。 |
| [userEnumeration](p-schemanode-userenumeration.md) | 傳回字元字串，這是目前節點使用的使用者分項清單名稱。 |

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
