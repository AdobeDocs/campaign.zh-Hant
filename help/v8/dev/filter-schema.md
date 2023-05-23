---
title: 篩選市場活動架構
description: 瞭解如何篩選市場活動架構
feature: Schema Extension
role: Developer
level: Intermediate, Experienced
exl-id: e8ad021c-ce2e-4a74-b9bf-a989d8879fd1
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---

# 篩選結構{#filter-schemas}

## 系統篩選器 {#system-filters}

您可以根據特定用戶的權限篩選對特定用戶的架構訪問。 系統篩選器允許您使用 **讀取訪問** 和 **寫訪問** 參數。

>[!NOTE]
>
>此限制僅適用於非技術用戶：具有相關權限或使用工作流的技術用戶將能夠檢索和更新資料。

* **讀取訪問**:提供對架構資料的只讀訪問。

   **警告**  — 所有連結表都必須設定相同的限制。 此配置會影響效能。

* **寫訪問**:提供對架構資料的寫訪問。

這些篩選器是在主 **元素** 架構的級別和（如以下示例所示）可以形成為限制訪問。

* 限制WRITE權限

   此處，該篩選器用於禁止在沒有ADMINISTRATION權限的情況下對運算子的架構具有WRITE權限。 這意味著只有管理員才對此架構描述的實體具有寫權限。

   ```
   <sysFilter name="writeAccess">      
    <condition enabledIf="hasNamedRight('admin')=false" expr="FALSE"/>    
   </sysFilter>
   ```

* 限制讀權限和寫權限：

   此處，篩選器用於禁止所有運算子對架構的READ和WRITE權限。 僅 **內部** 帳戶，由表達式「$(loginId)！」表示=0&quot;，具有這些權限。

   ```
   <sysFilter name="readAccess"> 
    <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
   </sysFilter>
   
   <sysFilter name="writeAccess">  
    <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
   </sysFilter>
   ```

   可能 **EXPR** 用於定義條件的屬性值為TRUE或FALSE。

>[!NOTE]
>
>如果未指定篩選器，則所有運算子都對架構具有讀和寫權限。

## Protect內置架構

預設情況下，只有具有ADMINISTRATION權限的運算子才能使用WRITE權限訪問內置架構：

* ncm：發佈
* nl：監視
* nms：日曆
* xtk：生成器
* xtk：連接
* xtk:dbInit
* xtk:entityBackupNew
* xtk:entityBackupOriginal
* xtk：實體原始
* xtk：格式
* xtk:funcList
* xtk：融合
* xtk：影像
* xtk:javascript
* xtk:jssp
* xtk:jst
* xtk：導航樹
* xtk:operatorGroup
* xtk：包
* xtk:queryDef
* xtk：資源菜單
* xtk：權限
* xtk：架構
* xtk：指令碼上下文
* xtk:spec檔案
* xtk:sql
* xtk:sqlSchema
* xtk:srcSchema
* xtk：字串
* xtk:xslt

>[!CAUTION]
>
>對的READ和WRITE權限 **xtk:sessionInfo** 模式僅可由Adobe Campaign實例的內部帳戶訪問。

## 修改內置架構的系統篩選器

內置架構受保護，以避免與舊版本的相容性問題。 Adobe建議您不要修改預設架構參數以確保最佳安全性。

但是，在特定上下文中，可能需要修改內置架構的系統篩選器。 要執行此操作，請執行以下步驟：

1. 為內置架構建立擴展或開啟現有擴展。
1. 添加子元素 **`<sysfilter name="<filter name>" _operation="delete"/>`** 在主元素中，忽略內置架構中相同的篩選器。
1. 可以添加新篩選器，如 [系統篩選器](#system-filters) 的子菜單。
