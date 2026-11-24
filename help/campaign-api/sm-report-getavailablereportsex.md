---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 25%
---
# GetAvailableReportsEx

恢復沒有歷史記錄的報告清單，並考慮資料排序條件和頁碼編排

```text
XML reports = GetAvailableReportsEx ( String activeContext, String schema, String selection, XML where, XML orderBy, Number editionMode, Number lineCount, Number startLine, String locationName )
```

## 參數

**activeContext**&#x200B;作用中內容（選取範圍，全域）

涉及&#x200B;**結構描述**&#x200B;結構描述

所選實體的&#x200B;**選擇**&#x200B;識別碼，以&#39;，&#39;分隔

**where**&#x200B;篩選&#39;where&#39;節點

**orderBy**&#x200B;排序&#39;orderBy&#39;節點

**editionMode**&#x200B;編輯期間，未發佈的報告也會顯示

**lineCount**&#x200B;要收集的報表數

**startLine**&#x200B;要套用至頁碼編排的位移

**locationName**

## 傳回值

**個報告**&#x200B;合格報告清單

## 功能

**結構描述：** [xtk:report](s-xtk-report.md)

**靜態：**

是
