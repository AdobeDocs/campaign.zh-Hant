---
title: 在Campaign中建立新的結構描述
description: 瞭解如何在Campaign中建立新結構描述
feature: Schema Extension
role: Developer
level: Intermediate, Experienced
exl-id: 796af848-b537-4b8d-a601-fe0628a1fc83
source-git-commit: 290f4e9a0d13ef49caacb7a128ccc266bafd5e69
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 2%

---

# 建立新結構描述{#create-new-schema}

若要編輯、建立及設定方案，請按一下 **[!UICONTROL Administration > Configuration > Data schemas]** Adobe Campaign使用者端主控台的節點。

>[!NOTE]
>
>內建資料結構描述只能由Adobe Campaign主控台的管理員刪除。

![](assets/schema_navtree.png)

此 **[!UICONTROL Edit]** 索引標籤顯示結構描述的XML內容：

![](assets/schema_edition.png)

>[!NOTE]
>
>「名稱」編輯控制項可讓您輸入由名稱和名稱空間組成的結構描述金鑰。 結構描述根元素的「名稱」和「名稱空間」屬性會在結構描述的XML編輯區域中自動更新。 請注意，某些名稱空間僅供內部使用。 [了解更多](schemas.md#reserved-namespaces)

此 **[!UICONTROL Preview]** tab會自動產生擴充型結構描述：

![](assets/schema_edition2.png)

>[!NOTE]
>
>儲存來源結構描述後，就會自動產生延伸結構描述。

如果您需要檢查架構的完整結構，可以使用 **[!UICONTROL Preview]** 標籤。 如果結構描述已擴充，您隨後將能夠將其所有擴充功能視覺化。 作為補充， **[!UICONTROL Documentation]** 索引標籤會顯示所有綱要屬性和元素及其特性（SQL欄位、型別/長度、標籤、說明）。 此 **[!UICONTROL Documentation]** 索引標籤僅適用於產生的結構描述。

## 使用案例：建立合約表格 {#example--creating-a-contract-table}

在下列範例中，您會建立 **合約** 在資料庫中。 此表格可讓您儲存每個合約的持有者和共同持有者的名字和姓氏，以及電子郵件地址。

要執行此操作，您需要建立表格的綱要，並更新資料庫結構以產生對應的表格。 詳細步驟列於下方。

1. 編輯 **[!UICONTROL Administration > Configuration > Data schemas]** Adobe Campaign樹狀結構的節點，然後按一下 **[!UICONTROL New]**.
1. 選擇 **[!UICONTROL Create a new table in the data template]** 選項並按一下 **[!UICONTROL Next]** .

   ![](assets/create_new_schema.png)

1. 指定資料表的名稱和名稱空間。

   ![](assets/create_new_param.png)

   >[!NOTE]
   >
   >依預設，使用者建立的方案會儲存在「cus」名稱空間中。 有關詳細資訊，請參閱 [結構描述的識別](extend-schema.md#identification-of-a-schema).

1. 建立表格的內容。 我們建議使用專用助理，以確保沒有設定遺失。 若要這麼做，請按一下 **[!UICONTROL Insert]** 按鈕，並選擇要新增的設定型別。

   ![](assets/create_new_content.png)

1. 定義合約表格的設定。

   最佳做法是在雲端資料庫中新增表格 `dataSource="nms:extAccount:ffda"` 屬性。 建立新表格時，預設會新增此屬性。

   ```
   <srcSchema created="YYYY-MM-DD HH:MM:SS.TZ" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" lastModified="YYYY-MM-DD HH:MM:SS.TZ"
           mappingType="sql" name="Contracts" namespace="cus" xtkschema="xtk:srcSchema">
      <element dataSource="nms:extAccount:ffda" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" name="Contracts">
           <attribute name="holderName" label="Holder last name" type="string"/>
           <attribute name="holderFirstName" label="Holder first name" type="string"/>
           <attribute name="holderEmail" label="Holder email" type="string"/>
           <attribute name="co-holderName" label="Co-holder last name" type="string"/>           
           <attribute name="co-holderFirstName" label="Co-holder first name" type="string"/>           
           <attribute name="co-holderEmail" label="Co-holder email" type="string"/>    
           <attribute name="date" label="Subscription date" type="date"/>     
           <attribute name="noContract" label="Contract number" type="long"/> 
      </element>
   </srcSchema>
   ```

   新增合約分項清單的型別。

   ```
   <srcSchema created="AA-MM-DD HH:MM:SS.TZ" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png" label="Contracts" labelSingular="Contract" AA-MM-DD HH:MM:SS.TZ"mappingType="sql" name="Contracts" namespace="cus" xtkschema="xtk:srcSchema">
      <enumeration basetype="byte" name="typeContract">
         <value label="Home" name="home" value="0"/>
         <value label="Car" name="car" value="1"/>
         <value label="Health" name="health" value="2"/>
         <value label="Pension fund" name="pension fund" value="2"/>
      </enumeration>
      <element dataSource="nms:extAccount:ffda" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" name="Contracts">
           <attribute name="holderName" label="Holder last name" type="string"/>
           <attribute name="holderFirstName" label="Holder first name" type="string"/>
           <attribute name="holderEmail" label="Holder email" type="string"/>
           <attribute name="co-holderName" label="Co-holder last name" type="string"/>           
           <attribute name="co-holderFirstName" label="Co-holder first name" type="string"/>           
           <attribute name="co-holderEmail" label="Co-holder email" type="string"/>    
           <attribute name="date" label="Subscription date" type="date"/>     
           <attribute name="noContract" label="Contract number" type="long"/> 
      </element>
   </srcSchema>
   ```

1. 儲存結構描述並按一下 **[!UICONTROL Structure]** 索引標籤以產生結構：

   ![](assets/configuration_structure.png)

1. 更新資料庫結構以建立將連結結構描述的表格。 如需詳細資訊，請參閱[本章節](update-database-structure.md)。
