---
title: 在Campaign中建立新的結構描述
description: 瞭解如何在Campaign中建立新的結構描述
feature: Schema Extension, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: 796af848-b537-4b8d-a601-fe0628a1fc83
source-git-commit: f75b95faa570d7c3f59fd8fb15692d3c3cbe0d36
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 2%

---

# 建立新結構描述 {#create-new-schema}

若要編輯、建立及設定結構描述，請按一下Adobe Campaign使用者端主控台的&#x200B;**[!UICONTROL Administration > Configuration > Data schemas]**&#x200B;節點。

>[!NOTE]
>
>內建資料結構描述只能由Adobe Campaign主控台的管理員刪除。

![](assets/schema_navtree.png)

**[!UICONTROL Edit]**&#x200B;索引標籤顯示結構描述的XML內容：

![](assets/schema_edition.png)

>[!NOTE]
>
>「名稱」編輯控制項可讓您輸入由名稱和名稱空間組成的結構描述金鑰。 結構描述根元素的「名稱」和「名稱空間」屬性會在結構描述的XML編輯區域中自動更新。 請注意，某些名稱空間僅供內部使用。 [了解更多](schemas.md#reserved-namespaces)

**[!UICONTROL Preview]**&#x200B;索引標籤會自動產生延伸結構描述：

![](assets/schema_edition2.png)

>[!NOTE]
>
>儲存來源結構描述時，就會自動啟動產生延伸結構描述。

如果您需要檢查結構描述的完整結構，可以使用&#x200B;**[!UICONTROL Preview]**&#x200B;標籤。 如果結構描述已擴充，您就能將其所有擴充功能視覺化。 作為補充，**[!UICONTROL Documentation]**&#x200B;索引標籤會顯示所有結構描述屬性和元素，及其屬性（SQL欄位、型別/長度、標籤、說明）。 **[!UICONTROL Documentation]**&#x200B;索引標籤僅適用於產生的結構描述。

## 使用案例：建立合約表格 {#example--creating-a-contract-table}

在下列範例中，您為資料庫中的&#x200B;**合約**&#x200B;建立新的資料表。 此表格可讓您儲存每個合約的持有者和共同持有者的名字和姓氏，以及電子郵件地址。

要執行此操作，您需要建立表格的綱要，並更新資料庫結構以產生對應的表格。 詳細步驟列於下方。

1. 編輯Adobe Campaign樹狀結構的&#x200B;**[!UICONTROL Administration > Configuration > Data schemas]**&#x200B;節點並按一下&#x200B;**[!UICONTROL New]**。
1. 選擇&#x200B;**[!UICONTROL Create a new table in the data template]**&#x200B;選項，然後按一下&#x200B;**[!UICONTROL Next]** 。

   ![](assets/create_new_schema.png)

1. 指定資料表的名稱和名稱空間。

   ![](assets/create_new_param.png)

   >[!NOTE]
   >
   >依預設，使用者建立的方案會儲存在「cus」名稱空間。 如需詳細資訊，請參閱[結構描述識別](extend-schema.md#identification-of-a-schema)。

1. 建立表格內容。 我們建議使用專用助理來確認沒有遺失任何設定。 若要這麼做，請按一下&#x200B;**[!UICONTROL Insert]**&#x200B;按鈕，然後選擇要新增的設定型別。

   ![](assets/create_new_content.png)

1. 定義合約表格的設定。

   最佳做法是新增`dataSource="nms:extAccount:ffda"`屬性，以在雲端資料庫中建立資料表。 建立新表格時，預設會新增此屬性。

   ```xml
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

   ```xml
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

1. 儲存結構描述並按一下&#x200B;**[!UICONTROL Structure]**&#x200B;標籤以產生結構：

   ![](assets/configuration_structure.png)

1. 更新資料庫結構以建立將連結綱要的表格。 如需詳細資訊，請參閱[本章節](update-database-structure.md)。
