---
title: 篩選行銷活動結構描述
description: 瞭解如何篩選Campaign結構描述
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

您可以根據特定使用者的許可權，篩選其結構描述存取權。 系統篩選器可讓您使用管理結構描述中詳述之實體的讀取和寫入許可權 **readAccess** 和 **writeAccess** 引數。

>[!NOTE]
>
>此限制僅適用於非技術使用者：具有相關許可權或使用工作流程的技術使用者將能夠擷取和更新資料。

* **readAccess**：提供對結構描述資料的唯讀存取權。

   **警告**  — 所有連結的表格都必須設定相同的限制。 此設定會影響效能。

* **writeAccess**：提供對結構描述資料的寫入許可權。

這些篩選器輸入在主要 **元素** 如下列範例所示，可形成架構的層級和來限制存取。

* 限制寫入許可權

   在此，篩選器用於在沒有ADMINISTRATION許可權的情況下禁止操作員在結構描述上執行WRITE許可權。 這表示只有管理員擁有此結構描述所說明之實體的寫入許可權。

   ```
   <sysFilter name="writeAccess">      
    <condition enabledIf="hasNamedRight('admin')=false" expr="FALSE"/>    
   </sysFilter>
   ```

* 限制讀取和寫入許可權：

   在此，篩選器用於禁止所有運運算元在結構描述上同時具有讀取和寫入許可權。 僅限 **內部** 帳號，由運算式「$(loginId)」表示！=0」擁有這些許可權。

   ```
   <sysFilter name="readAccess"> 
    <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
   </sysFilter>
   
   <sysFilter name="writeAccess">  
    <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
   </sysFilter>
   ```

   可能 **運算式** 用來定義條件的屬性值是TRUE或FALSE。

>[!NOTE]
>
>如果未指定篩選器，則所有運運算元都將具有結構描述的讀取和寫入許可權。

## Protect內建結構描述

依預設，只有具備管理員許可權的運運算元才可透過寫入許可權存取內建結構描述：

* ncm：發佈
* nl：monitoring
* nms：calendar
* xtk：builder
* xtk：連線
* xtk：dbInit
* xtk：entityBackupNew
* xtk：entityBackupOriginal
* xtk：entityOriginal
* xtk：form
* xtk：funcList
* xtk：fusion
* xtk：image
* xtk：javascript
* xtk：jssp
* xtk：jst
* xtk：navtree
* xtk：operatorGroup
* xtk：package
* xtk：queryDef
* xtk：resourceMenu
* xtk：rights
* xtk：schema
* xtk：scriptContext
* xtk：specFile
* xtk：sql
* xtk：sqlSchema
* xtk：srcSchema
* xtk：strings
* xtk：xslt

>[!CAUTION]
>
>的讀取和寫入許可權 **xtk：sessionInfo** 結構描述只能由Adobe Campaign執行個體的內部帳戶存取。

## 修改內建結構描述的系統篩選器

內建方案受到保護，以避免與舊版發生相容性問題。 Adobe建議您不要修改預設的結構描述引數，以確保最佳安全性。

但是，在特定上下文中，您可能需要修改內建結構描述的系統篩選器。 若要執行此動作，請遵循下列步驟：

1. 為內建方案建立擴充功能或開啟現有的擴充功能。
1. 新增子元素 **`<sysfilter name="<filter name>" _operation="delete"/>`** 在內建結構描述中，忽略相同專案下的篩選器。
1. 您可以新增篩選器，如 [系統篩選器](#system-filters) 區段。
