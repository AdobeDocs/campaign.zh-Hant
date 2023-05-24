---
product: campaign
title: SQL 資料管理
description: 深入瞭解SQL資料管理工作流程活動
feature: Workflows
exl-id: a1e08d57-0387-4802-b447-f6d9ad87072a
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 1%

---

# SQL 資料管理{#sql-data-management}

此 **SQL資料管理** 活動可讓您撰寫自己的SQL指令碼，以建立和填入工作表。

## 必要條件 {#prerequisites}

在設定活動之前，請確定已符合下列先決條件：

* 活動僅適用於遠端資料來源。
* 傳出結構描述必須存在於資料庫中，並連結至FDA資料庫。


## 設定SQL資料管理活動 {#configuring-the-sql-data-management-activity}

1. 指定活動 **[!UICONTROL Label]**.
1. 選取 **[!UICONTROL External account]** ，然後選取 **[!UICONTROL Outbound schema]** 連結至此外部帳戶。

   >[!CAUTION]
   >
   >傳出結構描述是固定的，無法編輯。

1. 新增SQL指令碼。

   >[!CAUTION]
   >
   >SQL指令碼編寫者應負責確認SQL指令碼運作正常，以及其參考（欄位名稱等） 符合傳出綱要。

   如果要載入現有的SQL程式碼，請選取 **[!UICONTROL The SQL script is contained in an entity stored in the database]** 選項。 SQL指令碼必須建立並儲存在 **[!UICONTROL Administration]** / **[!UICONTROL Configuration]** / **[!UICONTROL SQL scripts]** 功能表。

   否則，請在專用區域中鍵入或複製並貼上您的SQL指令碼。

   ![](assets/sql_datamanagement.png)

   活動可讓您在指令碼中使用下列變數：

   * **activity.tableName**：傳出工作表的SQL名稱。
   * **task.incomingTransitionByName(&#39;name&#39;)。tableName**：傳入轉變所承載要使用的工作表的SQL名稱（轉變由其名稱識別）。

      >[!NOTE]
      >
      >(&#39;name&#39;)值對應至 **[!UICONTROL Name]** 切換屬性中的欄位。

1. 如果SQL命令檔已經包含建立出站工作表格的命令，請取消選取 **[!UICONTROL Automatically create work table]** 選項。 否則，工作流程執行後會自動建立工作表。
1. 按一下 **[!UICONTROL Ok]** 以確認活動設定。

活動現在已設定。 它可以在工作流程中執行。

>[!CAUTION]
>
>執行活動後，出站轉變記錄計數僅供參考。 它可能會因SQL指令碼的複雜度而有所不同。
>  
>如果活動重新啟動，則會從頭執行整個指令碼，無論其執行狀態為何。

## SQL指令碼範例 {#sql-script-samples}

>[!NOTE]
>
>本節中的指令碼範例旨在在PostgreSQL下執行。

以下指令碼可讓您建立工作表，並將資料插入此相同工作表中：

```
CREATE UNLOGGED TABLE <%= activity.tableName %> (
  iRecipientId INTEGER DEFAULT 0,
  sFirstName VARCHAR(100),
  sMiddleName VARCHAR(100),
  sLastName VARCHAR(100),
  sEmail VARCHAR(100)
);

INSERT INTO <%= activity.tableName %>
SELECT iRecipientId, sFirstName, sMiddleName, sLastName, sEmail
FROM nmsRecipient
GROUP BY iRecipientId, sFirstName, sMiddleName, sLastName, sEmail;
```

以下指令碼可讓您執行CTAS作業(CREATE TABLE AS SELECT)並建立工作表索引：

```
CREATE TABLE <%= activity.tableName %>
AS SELECT iRecipientId, sEmail, sFirstName, sLastName, sMiddleName
FROM nmsRecipient
WHERE sEmail IS NOT NULL
GROUP BY iRecipientId, sEmail, sFirstName, sLastName, sMiddleName;

CREATE INDEX ON <%= activity.tableName %> (sEmail);

ANALYZE <%= activity.tableName %> (sEmail);
```

以下指令碼可讓您合併兩個工作表格：

```
CREATE TABLE <%= activity.tableName %>
AS SELECT i1.sFirstName, i1.sLastName, i2.sEmail
FROM <%= task.incomingTransitionByName('input1').tableName %> i1
JOIN <%= task.incomingTransitionByName('input2').tableName %> i2 ON (i1.id = i2.id)
```
