---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '67'
ht-degree: 13%
---
# 完整性

傳回連結完整性型別。

```text
integrity
```

## 備註

屬性可以有下列其中一個值：

* Schema.INTEGRITY\_NORMAL - 「一般」型別連結。
* Schema.INTEGRITY\_DEFINE - 「定義」型別連結。
* Schema.INTEGRITY\_NEUTRAL - 「中性」型別連結。
* Schema.INTEGRITY\_USED - 「已使用」型別連結。
* Schema.INTEGRITY\_OWN - &quot;own&quot;型別連結。
* Schema.INTEGRITY\_OWNCOPY - &quot;owncopy&quot;型別連結。

## 功能

類別的&#x200B;**屬性：** [SchemaNode](c-schemanode.md)

**唯讀：**

是

**可用於：**

* 內容管理
* 傳遞屬性
* 類型規則
* JSSP
* SOAP方法
* WebApp
* 工作流程
