---
solution: Campaign
product: Adobe Campaign
title: 在促銷活動中建立新結構
description: 瞭解如何在Campaign中建立新結構
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 2%

---

# 建立新模式{#create-new-schema}

要編輯、建立和配置模式，請按一下Adobe Campaign客戶機控制台的&#x200B;**[!UICONTROL Administration > Configuration > Data schemas]**&#x200B;節點。

>[!NOTE]
>
>您的Adobe Campaign Classic控制台管理員只能刪除內建資料結構。

![](assets/schema_navtree.png)

**[!UICONTROL Edit]**&#x200B;標籤顯示架構的XML內容：

![](assets/schema_edition.png)

>[!NOTE]
>
>「名稱」編輯控制項可讓您輸入由名稱和名稱空間組成的架構索引鍵。 架構的根元素的&quot;name&quot;和&quot;namespace&quot;屬性會在架構的XML編輯區域中自動更新。

**[!UICONTROL Preview]**&#x200B;頁籤自動生成擴展模式：

![](assets/schema_edition2.png)

>[!NOTE]
>
>保存源模式時，將自動啟動擴展模式的生成。

如果需要檢查方案的完整結構，可以使用&#x200B;**[!UICONTROL Preview]**&#x200B;頁籤。 如果架構已擴充，則您將能夠直觀顯示其所有擴展。 作為補充，**[!UICONTROL Documentation]**&#x200B;頁籤顯示所有模式屬性和元素及其屬性（SQL欄位、類型／長度、標籤、說明）。 **[!UICONTROL Documentation]**&#x200B;標籤僅適用於生成的方案。

## 使用案例：建立合同表{#example--creating-a-contract-table}

在以下示例中，您為資料庫中的&#x200B;**contracts**&#x200B;建立新表。 此表格可讓您儲存每個合約持有人和共同持有人的名字和姓氏以及電子郵件地址。

為此，需要建立表的模式並更新資料庫結構以生成相應表。 詳細步驟列於下方。

1. 編輯Adobe Campaign樹的&#x200B;**[!UICONTROL Administration > Configuration > Data schemas]**&#x200B;節點，然後按一下&#x200B;**[!UICONTROL New]**。
1. 選擇&#x200B;**[!UICONTROL Create a new table in the data template]**&#x200B;選項，然後按一下&#x200B;**[!UICONTROL Next]**。

   ![](assets/create_new_schema.png)

1. 指定表的名稱和命名空間。

   ![](assets/create_new_param.png)

   >[!NOTE]
   >
   >依預設，由使用者建立的結構描述會儲存在&#39;cus&#39;命名空間中。 有關詳細資訊，請參閱[方案標識](extend-schema.md#identification-of-a-schema)。

1. 建立表的內容。 我們建議使用專用的助理，以確保沒有遺失設定。 若要這麼做，請按一下&#x200B;**[!UICONTROL Insert]**&#x200B;按鈕，然後選擇要新增的設定類型。

   ![](assets/create_new_content.png)

1. 定義合同表的設定：

   ```
   <srcSchema created="AA-MM-DD HH:MM:SS.TZ" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" lastModified="AA-MM-DD HH:MM:SS.TZ"
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

   新增合約列舉類型。

   ```
   <srcSchema created="AA-MM-DD HH:MM:SS.TZ" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png" label="Contracts" labelSingular="Contract" lastModified="AA-MM-DD HH:MM:SS.TZ"mappingType="sql" name="Contracts" namespace="cus" xtkschema="xtk:srcSchema">
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

1. 保存模式並按一下&#x200B;**[!UICONTROL Structure]**&#x200B;頁籤以生成結構：

   ![](assets/configuration_structure.png)

1. 更新資料庫結構以建立將連結模式的表。 如需詳細資訊，請參閱[本章節](update-database-structure.md)。

