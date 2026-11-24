---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 8%
---
# 結構描述（類別）

代表結構描述定義。

透過呼叫`application`全域變數的方法取得結構描述。 此物件的執行個體會將物件當作原型，因此會繼承其方法。

## 方法

| 方法 | 說明 |
| --- | --- |
| [toDocument](m-schema-todocument.md) | 將結構描述轉換為XML檔案表單。 |

## 屬性

| 屬性 | 說明 |
| --- | --- |
| [分項清單](p-schema-enumerations.md) | 傳回包含此結構描述中所定義[列舉](c-enumeration.md)清單的資料表。 |
| [id](p-schema-id.md) | 字串形式的結構描述識別碼。 |
| [isLibrary](p-schema-islibrary.md) | 傳回布林值，指定結構描述是否為元件程式庫。 |
| [標籤單數](p-schema-labelsingular.md) | 字串形式的結構描述單數名稱。 |
| [mappingType](p-schema-mappingtype.md) | 字串形式的結構描述對應性質 |
| [md5](p-schema-md5.md) | 以十六進位字串形式呈現的結構描述的MD5程式碼。 |
| [名稱空間](p-schema-namespace.md) | 字串形式的結構描述名稱空間。 |
| [根](p-schema-root.md) | 結構描述的主要元素，如果未定義則為Null。 |
| [userDescription](p-schema-userdescription.md) | 以字串形式呈現的結構描述說明。 |

## 功能

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
