---
title: 在Campaign v8中開始使用權限
description: 瞭解在市場活動v8中定義權限的步驟
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

Adobe Campaign允許您定義和管理分配給用戶的權限。 這些是授權或拒絕的一組權利和限制：

* 訪問某些功能
* 訪問某些資料
* 訪問某些操作（建立、修改、刪除）

這些權限是通過組合操作員組權限、指定權限和資料夾權限來定義的。

在Adobe Campaign，用戶 **運算子** 和 **運算子組** 表示用戶角色。 操作員是具有登錄和執行操作權限的Adobe Campaign用戶。 用戶在Admin Console中建立。 權限應用於用戶配置檔案或用戶組。 可授予的權限有兩種類型：

* 您可以定義屬性權限的運算子組，然後將運算子與一個或多個組關聯。 這使您能夠重新使用權限並使操作員配置檔案更加一致。 它還方便了用戶配置檔案的管理和維護。
* 您可以直接將命名權限分配給用戶，在某些情況下，會使通過組分配的權限超負荷。

## 授予權限的關鍵步驟{#key-steps-permissions}

作為產品管理員，您可以向組織的用戶授予權限。 權限通過Adobe Admin Console和市場活動客戶端控制台授予。 用戶使用他們的Adobe ID登錄Adobe Campaign。 瞭解如何連接Adobe Campaign [此頁](connect.md)。

關鍵步驟是：

* **步驟1**:在市場活動客戶端控制台中定義操作員組並為其分配權限。 [了解更多](manage-permissions.md#create-product-profile).
請注意，您還可以使用內置運算子組開始。 這些預設組及其權限列於 [此部分](manage-permissions.md#ootb-productprofiles)。
* **步驟2**:在Admin Console中建立與這些組匹配的產品配置檔案。 [了解更多](manage-permissions.md#create-product-profile).
您可以使用內置產品配置檔案開始。 [了解更多](manage-permissions.md#ootb-productprofiles)。
* **步驟3**:在Admin Console中建立用戶，並將其分配給產品配置檔案。 [了解更多](manage-permissions.md#add-users)。
* **步驟4** （可選）:為資料夾分配權限。 [了解更多](manage-permissions.md#ootb-productprofiles)。

## 關於Admin Console{#gs-admin-console}

Adobe Admin Console是管理整個組織的Adobe權利的中心位置。 只有產品管理員才能訪問它。

使用Admin Console添加用戶、建立和分配產品配置檔案（這些是操作員角色組）。

瞭解如何在 [此頁](manage-permissions.md#add-users)。

## 關於產品配置檔案{#ootb-product-profiles}

產品配置檔案是可分配給用戶的產品和服務組。 在Adobe Experience Cloud，權限基於產品的配置檔案，而不是用戶。 但是，您可以將管理權限委託給特定用戶。

在Admin Console，每個Adobe Experience Cloud **產品配置檔案** 對於市場活動，與 **運算子組** 在市場活動客戶端控制台中。

瞭解如何在中建立和分配產品配置檔案 [此頁](manage-permissions.md#create-a-product-profile)。

## 指定權限的市場活動{#named-rights}

作為產品配置檔案（即操作員組）的成員，用戶具有執行操作（稱為「命名權限」）的權限，並且對資料具有讀和/或寫訪問權限。 運算子可以是多個運算子組的成員：權限和訪問權限是附加的。

瞭解有關中命名權限的詳細資訊 [此部分](manage-permissions.md#use-named-rights)。
