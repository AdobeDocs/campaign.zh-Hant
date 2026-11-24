---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 18%
---
# Installpackage

安裝套件。

```text
InstallPackage ( XML parameters )
```

## 參數

**引數**&#x200B;包含要匯入之封裝的XML專案。

## 傳回值

無。

## 備註

SpecFile.Generate()方法產生的套件必須封裝在產生器元素中。 範例：

```javascript
var params =
  {builder:
    {package:
      { ... }
    }
  }

NLWS.xtkBuilder.InstallPackage(params)
```

## 功能

**結構描述：** [xtk:builder](s-xtk-builder.md)

**靜態：**

是
