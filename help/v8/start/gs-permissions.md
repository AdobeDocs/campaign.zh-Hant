---
title: 開始使用Campaign v8中的許可權
description: 瞭解在Campaign v8中定義許可權的步驟
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: b71197027d9521fd648a0c2657b6b76a1aa7fc9a
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 2%

---

# 開始使用權限{#gs-permissions}

Adobe Campaign可讓您定義和管理指派給使用者的許可權。 這些是一組授權或拒絕的許可權和限制：

* 存取特定功能
* 存取特定資料
* 存取特定動作（建立、修改、刪除）

這些許可權是透過結合操作員群組許可權、已命名的許可權和檔案夾的許可權來定義。

在Adobe Campaign中，使用者是 **運運算元** 和 **運運算元群組** 代表使用者角色。 操作員是有許可權登入及執行動作的Adobe Campaign使用者。 會在Admin Console中建立使用者。 許可權適用於使用者設定檔或使用者群組。 您可授與兩種型別的許可權：

* 您可以定義您賦予許可權的運運算元群組，然後將運運算元與一或多個群組建立關聯。 這可讓您重複使用許可權，並讓運運算元設定檔更加一致。 它還有助於管理和維護使用者設定檔。
* 您可以直接將已命名的許可權指派給使用者，在某些情況下，這會使透過群組配置的許可權過載。

## 授與許可權的關鍵步驟{#key-steps-permissions}

作為產品管理員，您可以授予組織使用者的許可權。 許可權是透過Adobe Admin Console和Campaign使用者端主控台授與。 使用者使用其Adobe ID登入Adobe Campaign。 瞭解如何在中連線至Adobe Campaign [此頁面](connect.md).

主要步驟為：

* **步驟1**：在Campaign使用者端主控台中定義運運算元群組並指派許可權。 [了解更多](manage-permissions.md#create-product-profile)。請注意，您也可以使用內建運運算元群組作為開頭。 這些預設群組及其許可權列於 [本節](manage-permissions.md#ootb-productprofiles).
* **步驟2**：在Adobe Admin Console中建立與這些群組相符的產品設定檔。 [了解更多](manage-permissions.md#create-product-profile)。您可以使用內建的產品設定檔來開始。 [了解更多](manage-permissions.md#ootb-productprofiles)。
* **步驟3**：在Adobe Admin Console中建立使用者，並將其指派至產品設定檔。 [了解更多](manage-permissions.md#add-users)。
* **步驟4** （選用）：指派檔案夾許可權。 [了解更多](manage-permissions.md#ootb-productprofiles)。

## 關於Admin Console{#gs-admin-console}

Adobe Admin Console是管理整個組織Adobe許可權的中央位置。 僅產品管理員可存取。

使用Admin Console來新增使用者、建立及指派產品設定檔（這是操作員角色群組）。

瞭解如何在中新增使用者 [此頁面](manage-permissions.md#add-users).

## 關於產品設定檔{#ootb-product-profiles}

產品設定檔是您可以指派給使用者的產品和服務群組。 在Adobe Experience Cloud中，許可權是根據產品設定檔，而不是使用者。 不過，您可以將管理許可權委派給特定使用者。

在Admin Console中，每個Adobe Experience Cloud **產品設定檔** （適用於與關聯的促銷活動） **操作員群組** Campaign使用者端主控台中的。

瞭解如何在中建立和指派產品設定檔 [此頁面](manage-permissions.md#create-a-product-profile).

## 行銷活動已命名的許可權{#named-rights}

作為產品設定檔（即操作員群組）的成員，使用者有權執行稱為「已命名的許可權」的操作，並擁有資料的讀取和/或寫入許可權。 運運算元可以是多個運運算元群組的成員：許可權和存取許可權是可附加的。

進一步瞭解中的已命名許可權 [本節](manage-permissions.md#use-named-rights).
