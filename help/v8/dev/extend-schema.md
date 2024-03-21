---
title: 擴充行銷活動綱要
description: 瞭解如何延伸Campaign綱要
feature: Schema Extension, Data Model
role: Developer
level: Intermediate, Experienced
exl-id: e4dcb228-0683-437a-88cd-bd7ed33da921
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 2%

---

# 擴充綱要{#extend-schemas}

身為技術使用者，您可以自訂Campaign資料模型以符合實作需求：新增元素至現有結構描述、修改結構描述中的元素或刪除元素。

自訂Campaign資料模型的主要步驟為：

1. 建立擴充功能綱要
1. 更新Campaign資料庫
1. 調整輸入表單

>[!CAUTION]
>不可直接修改內建結構描述。 如果您需要調整內建方案，必須擴充方案。

若要更瞭解Campaign內建表格及其互動，請參閱 [此頁面](datamodel.md). 另請參閱在中建立新結構描述時的建議 [此頁面](create-schema.md).

若要擴充方案，請遵循下列步驟：

1. 導覽至 **[!UICONTROL Administration > Configuration > Data schemas]** 檔案夾。
1. 按一下 **新增** 按鈕並選取 **[!UICONTROL Extend the data in a table using an extension schema]**.

   ![](assets/extend-schema-option.png)

1. 識別要擴充的內建方案並加以選取。

   ![](assets/extend-schema-select.png)

   依照慣例，請將擴充功能綱要命名為與內建綱要相同的名稱，並使用自訂名稱空間。  請注意，某些名稱空間僅供內部使用。 [了解更多](schemas.md#reserved-namespaces)

   ![](assets/extend-schema-validate.png)

1. 在架構編輯器中，使用內容功能表新增所需的元素並儲存。

   ![](assets/extend-schema-edit.png)

   在以下範例中，我們新增 **MembershipYear** 屬性，輸入姓氏的長度限制（此限制會覆寫預設長度），並從內建方案中移除出生日期。

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

1. 中斷連線並重新連線至Campaign，以檢查 **[!UICONTROL Structure]** 標籤。

   ![](assets/extend-schema-structure.png)

1. 更新資料庫結構以套用變更。 [了解更多](update-database-structure.md)

1. 在資料庫中實作變更後，您可以調整收件者輸入表單以顯示變更。 [了解更多](forms.md)
