---
title: 擴展市場活動架構
description: 瞭解如何擴展市場活動架構
exl-id: e4dcb228-0683-437a-88cd-bd7ed33da921
source-git-commit: 9e07353859e63b71abb61526f40675f18837bc59
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 2%

---

# 擴展架構{#extend-schemas}

作為技術用戶，您可以自定義市場活動資料模型以滿足實施的需要：將元素添加到現有架構中，修改架構中的元素或刪除元素。

自定義市場活動資料模型的關鍵步驟包括：

1. 建立擴展架構
1. 更新市場活動資料庫
1. 調整輸入表單

>[!CAUTION]
>內置架構不能直接修改。 如果需要調整內置架構，則必須擴展它。

![](../assets/do-not-localize/glass.png) 要更好地瞭解活動內置表及其交互作用，請參閱 [此頁](datamodel.md)。 另請參見中建立新架構時的建議 [此頁](create-schema.md)。

要擴展架構，請執行以下步驟：

1. 導航到 **[!UICONTROL Administration > Configuration > Data schemas]** 資料夾。
1. 按一下 **新建** 按鈕 **[!UICONTROL Extend the data in a table using an extension schema]**。

   ![](assets/extend-schema-option.png)

1. 標識要擴展的內置架構並選擇它。

   ![](assets/extend-schema-select.png)

   按照約定，將擴展架構命名為與內置架構相同，並使用自定義命名空間。  請注意，某些命名空間僅是內部的。 [了解更多](schemas.md#reserved-namespaces)

   ![](assets/extend-schema-validate.png)

1. 在架構編輯器中，使用上下文菜單添加所需元素並保存。

   ![](assets/extend-schema-edit.png)

   在下面的示例中，我們將 **會員年** 屬性，為姓氏設定長度限制（此限制將覆蓋預設限制），並從內置架構中刪除出生日期。

   ![](assets/extend-schema-sample.png)

   ```
   <srcSchema created="YYYY-MM-DD" desc="Recipient table" extendedSchema="nms:recipient"
           img="nms:recipient.png" label="Recipients" labelSingular="Recipient" lastModified="YYYY-MM-DD"
           mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:srcSchema">
    <element desc="Recipient table" img="nms:recipient.png" label="Recipients" labelSingular="Recipient" name="recipient">
       <attribute label="Member since" name="MembershipYear" type="long"/>
       <attribute length="50" name="lastName"/>
       <attribute _operation="delete" name="birthDate"/>
   </element>
   </srcSchema>
   ```

1. 斷開與市場活動的連接並重新連接，以在 **[!UICONTROL Structure]** 頁籤。

   ![](assets/extend-schema-structure.png)

1. 更新資料庫結構以應用更改。 [了解更多](update-database-structure.md)

1. 在資料庫中實施更改後，您可以調整收件人輸入表單以使更改可見。 [了解更多](forms.md)
