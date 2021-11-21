---
title: 在Campaign中建立新結構
description: 了解如何在Campaign中建立新結構
exl-id: 796af848-b537-4b8d-a601-fe0628a1fc83
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 2%

---

# 建立新結構{#create-new-schema}

若要編輯、建立和設定結構，請按一下 **[!UICONTROL Administration > Configuration > Data schemas]** Adobe Campaign用戶端主控台的節點。

>[!NOTE]
>
>您的Adobe Campaign主控台管理員只能刪除內建資料結構。

![](assets/schema_navtree.png)

此 **[!UICONTROL Edit]** 頁簽顯示架構的XML內容：

![](assets/schema_edition.png)

>[!NOTE]
>
>「名稱」編輯控制項可讓您輸入由名稱和命名空間組成的架構金鑰。 架構的根元素的「name」和「namespace」屬性會在架構的XML編輯區域中自動更新。 請注意，有些命名空間僅為內部。 [了解更多](schemas.md#reserved-namespaces)

此 **[!UICONTROL Preview]** 頁簽自動生成擴展架構：

![](assets/schema_edition2.png)

>[!NOTE]
>
>儲存來源架構時，會自動啟動延伸架構的產生。

如果您需要檢查架構的完整結構，可以使用 **[!UICONTROL Preview]** 標籤。 如果結構已擴充，您便能將其所有擴充功能視覺化。 作為補充， **[!UICONTROL Documentation]** 頁簽顯示所有架構屬性和元素及其屬性（SQL欄位、類型/長度、標籤、說明）。 此 **[!UICONTROL Documentation]** 索引標籤僅適用於產生的結構。

## 使用案例：建立合同表 {#example--creating-a-contract-table}

在以下範例中，您為 **合同** 在資料庫中。 此表格可讓您儲存每個合約的持有人和共同持有人的名字和姓氏以及電子郵件地址。

要執行此操作，需要建立表的架構並更新資料庫結構以生成相應的表。 以下列出詳細步驟。

1. 編輯 **[!UICONTROL Administration > Configuration > Data schemas]** 節點，然後按一下 **[!UICONTROL New]**.
1. 選擇 **[!UICONTROL Create a new table in the data template]** 選項，然後按一下 **[!UICONTROL Next]** .

   ![](assets/create_new_schema.png)

1. 指定表的名稱和命名空間。

   ![](assets/create_new_param.png)

   >[!NOTE]
   >
   >依預設，使用者建立的結構會儲存在「自訂」命名空間中。 有關詳細資訊，請參閱 [方案的標識](extend-schema.md#identification-of-a-schema).

1. 建立表格的內容。 建議您使用專用助理，確保未遺失任何設定。 若要這麼做，請按一下 **[!UICONTROL Insert]** 按鈕，然後選擇要添加的設定類型。

   ![](assets/create_new_content.png)

1. 定義合約表格的設定。

   最佳作法是在雲端資料庫中，新增 `dataSource="nms:extAccount:ffda"` 屬性。 建立新表格時，預設會新增此屬性。

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

   新增合約分項清單的類型。

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

1. 儲存結構，然後按一下 **[!UICONTROL Structure]** 頁簽生成結構：

   ![](assets/configuration_structure.png)

1. 更新資料庫結構以建立將連結架構的表。 如需詳細資訊，請參閱[本章節](update-database-structure.md)。
