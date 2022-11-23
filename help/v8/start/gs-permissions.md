---
title: 開始使用Campaign v8的權限
description: 了解在Campaign v8中定義權限的步驟
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: b63dc1616bc7ce1387a7bd0590c289b59f11b33f
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 2%

---

# 開始使用權限{#gs-permissions}

Adobe Campaign可讓您定義及管理指派給使用者的權限。 這些是授權或拒絕的一組權限和限制：

* 存取特定功能
* 存取特定資料
* 存取特定動作（建立、修改、刪除）

這些權限是由結合運算子群組權限、資料夾的命名權限和權限所定義。

在Adobe Campaign中，使用者為 **運算子** 和 **運算元組** 代表使用者角色。 運算子是具有登入及執行動作權限的Adobe Campaign使用者。 使用者會在Admin Console中建立。 權限會套用至使用者設定檔或使用者群組。 您可以授予兩種權限：

* 您可以定義運算子群組，將其權限歸因於該群組，然後將運算子與一或多個群組關聯。 這可讓您重複使用權限，並讓運算子設定檔更加一致。 它還有助於用戶配置檔案的管理和維護。
* 您可以直接將指定的權限指派給使用者，在某些情況下，會使透過群組分配的權限過載。

## 授予權限的關鍵步驟{#key-steps-permissions}

身為產品管理員，您可以授予組織的使用者權限。 權限是透過Adobe Admin Console和Campaign用戶端主控台授予。 使用者使用其Adobe ID登入Adobe Campaign。 了解如何在 [本頁](connect.md).

關鍵步驟為：

* **步驟1**:在Campaign用戶端主控台中定義運算子群組並指派權限。 [了解更多](manage-permissions.md#create-product-profile).
請注意，您也可以使用內建運算子群組來開頭。 這些預設群組及其權限列於 [本節](manage-permissions.md#ootb-productprofiles).
* **步驟2**:在與這些群組相符的Admin Console中建立產品設定檔。 [了解更多](manage-permissions.md#create-product-profile).
您可以從使用內建的產品設定檔開始。 [了解更多資訊](manage-permissions.md#ootb-productprofiles)。
* **步驟3**:在Admin Console中建立使用者，並將其指派至產品設定檔。 [了解更多資訊](manage-permissions.md#add-users)。
* **步驟4** （可選）:指派資料夾的權限。 [了解更多資訊](manage-permissions.md#ootb-productprofiles)。

## 關於Admin Console{#gs-admin-console}

Adobe Admin Console是管理整個組織Adobe權益的集中位置。 產品管理員只能存取。

使用Admin Console來新增使用者、建立和指派產品設定檔（這些是運算元角色群組）。

了解如何在 [本頁](manage-permissions.md#add-users).

## 關於產品設定檔{#ootb-product-profiles}

產品設定檔是您可指派給使用者的產品和服務群組。 在Adobe Experience Cloud中，權限是根據產品的設定檔，而非使用者。 不過，您可以將管理權限委派給特定使用者。

在Admin Console中，每個Adobe Experience Cloud **產品設定檔** 針對促銷活動，會與 **運算元組** 在Campaign用戶端主控台中。

了解如何在 [本頁](manage-permissions.md#create-a-product-profile).

## 已命名的促銷活動權限{#named-rights}

作為產品設定檔（即運算元群組）的成員，使用者擁有執行操作的權限（稱為「已命名權限」），且具有資料的讀取和/或寫入存取權。 運算子可以是多個運算子組的成員：權限和存取權限可加入。

進一步了解中已命名的權限 [本節](manage-permissions.md#use-named-rights).
