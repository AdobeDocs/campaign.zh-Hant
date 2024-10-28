---
title: 將技術使用者移轉至Adobe Developer主控台
description: 瞭解如何將使用者存取管理從Campaign Standard移轉至Campaign V8
feature: Technote
role: Admin
source-git-commit: ccd60b7ff54bb538ae21693eff41a3943f1c6c88
workflow-type: tm+mt
source-wordcount: '839'
ht-degree: 2%

---

# 從Campaign Standard到Campaign V8的使用者存取管理 {#user-management-acs}

Adobe Campaign Standard和Adobe Campaign V8都可讓使用者定義和管理不同使用者/運運算元的許可權。 這些許可權包含授予使用者存取產品各種功能的特定許可權。 不過，這兩種產品使用不同的方法和實作來管理使用者存取許可權。

Adobe Campaign Standard和Campaign V8會使用下列概念，來達成使用者存取管理：

| Campaign Standard | Campaign V8 |
|---------|----------|
| 使用者 | 操作員 |
| 角色 | 已命名的右側 |
| 安全性群組 | 操作員群組 |
| 組織單位 | 檔案夾許可權 |

## 從安全性群組移轉至操作員群組的方式

>[!CAUTION]
>
>這些角色/已命名許可權的功能在實施中可能會有所不同，這可能會造成授權問題（例如，許可權提升或功能中斷）。 我們建議使用者在轉換後檢閱這些對應，以確保適當的存取控制。 [進一步瞭解許可權](../../v8/start/manage-permissions.md)

下表概述從Adobe Campaign Standard轉換至Campaign V8時，使用者角色群組的移轉方法。 在Campaign Standard中，Campaign V8中稱為&#x200B;**操作員群組**&#x200B;的&#x200B;**安全性群組**&#x200B;用於將一組角色指派給使用者。 雖然有些安全性群組/運運算元群組是現成可用的群組，但使用者可視需要建立新群組或修改現有群組。

| | **Campaign Standard** | **促銷活動V8** |
|---------|----------|---------|
| **術語**  | 安全性群組 | 操作員群組 |

在Adobe Campaign Standard和Campaign V8中，**安全性群組**&#x200B;和&#x200B;**操作員群組**&#x200B;都會對應到Admin Console中的產品設定檔。 如果您想要將&#x200B;**安全性群組**&#x200B;或&#x200B;**操作員群組**&#x200B;指派給使用者，可以在Admin Console中連結對應的&#x200B;**產品設定檔**。 此關聯會在使用者登入時同步化。 [進一步瞭解產品設定檔](../../v8/start/manage-permissions.md)

| **Campaign Standard安全性群組** | **Campaign V8操作員群組** |
|----------|---------|
| 管理員 | 管理員 |
| 傳遞主管 | 管理員 |
| 工作流程主管 | 工作流程主管  |

## 從使用者角色移轉至已命名許可權的方法

在Adobe Campaign Standard中，術語&#x200B;**使用者角色**&#x200B;在Campaign V8中稱為&#x200B;**已命名許可權**。 下表概述Campaign V8中與Campaign Standard中&#x200B;**使用者角色**&#x200B;對應的&#x200B;**已命名許可權**&#x200B;所使用的術語。

| **Campaign Standard使用者角色** | **行銷活動V8已命名許可權** | **描述**  |
|----------|---------|---------|
| 管理 | 管理 | 具有管理許可權的使用者擁有執行個體的完整存取權。 |
| 資料模型  | 管理 | 直接執行出版物並建立自訂資源。 管理員可在Campaign V8中使用結構描述建立相關功能。  |
| 傳遞能力  | 管理  | 核准先前分析的傳遞的權利。  |
| 匯出 | 匯出 | 匯出資料的權利。  |
| 檔案存取  | 檔案存取  | 核准先前分析的傳遞的權利。  |
| 一般匯入  | 匯入  | 一般資料匯入的許可權 |
| 準備傳遞 | 準備傳遞 | 建立、修改、準備和刪除傳送的權利。  |
| SQL指令碼執行 | SQL指令碼執行 | 直接在資料庫上執行任何SQL命令的許可權。 |
| 開始傳遞  | 開始傳遞  | 核准先前分析的傳遞的權利。  |
| 系統命令執行 | 程式執行 | 在伺服器上執行系統命令的許可權。 |
| 工作流程 | 工作流程 | 管理工作流程開始、停止、暫停等的執行。 |

## 從組織單位移轉方法

在Adobe Campaign Standard中，**組織uni** t對應至Campaign V8中的現有&#x200B;**資料夾**&#x200B;階層模型，以維護類似的存取控制。 [進一步瞭解資料夾管理](../../v8/start/folder-permissions.md)

| | **Campaign Standard** | **促銷活動V8** |
|---------|----------|---------|
| **術語**  | 組織單位 | 資料夾 |

## 從計畫移轉方法

在Campaign V8中，**方案**&#x200B;表示為&#x200B;**資料夾**。 Campaign V8可建立資料夾並限制對資料夾的存取。

使用&#x200B;**群組**&#x200B;和&#x200B;**已命名的許可權**，**操作員**&#x200B;可以授與導覽階層內特定&#x200B;**資料夾**&#x200B;的存取權，並且能夠指派讀取、寫入和刪除許可權。 [進一步瞭解資料夾管理](../../v8/start/folder-permissions.md)

由於Campaign V8將&#x200B;**方案**&#x200B;視為&#x200B;**資料夾**，因此其存取的管理方式與任何其他資料夾相同。 移轉後，Campaign Standard管理員可依照下列步驟操作：

1. 在檔案總管中，對任何資料夾按一下滑鼠右鍵並選取&#x200B;**[!UICONTROL Properties...]**。
1. 導覽至&#x200B;**[!UICONTROL Security]**&#x200B;標籤。
1. 根據所需的存取模式修改操作員群組許可權。 

## 用於存取REST API的產品設定檔對應 

若要從Campaign V8的執行執行個體存取交易API，除了&#x200B;**管理員**&#x200B;和&#x200B;**訊息中心**&#x200B;產品設定檔之外，還需要新的&#x200B;**產品設定檔**。 這個新的&#x200B;**產品設定檔**&#x200B;將新增至Campaign Standard中現有或預先建立的技術帳戶。

移轉後，如果Campaign Standard使用者不想將其&#x200B;**技術帳戶**&#x200B;連結至&#x200B;**管理員**&#x200B;產品設定檔，則應檢閱其&#x200B;**產品設定檔對應**，並指派適當的&#x200B;**產品設定檔**。 若是未來的整合，我們建議在&#x200B;**REST URL**&#x200B;中使用Campaign V8 **租使用者ID**，而不是使用先前的Campaign Standard **租使用者ID**。

## 移轉Campaign Standard操作員的內建Campaign資源存取權

從Campaign Standard移轉的操作者將擁有Campaign V8中特定內建資源的讀取存取權。

## 未移轉的安全性群組和角色 {#non-migrated-groups-roles}

以下是尚未轉換的Campaign Standard角色清單：

* 預設轉送帳戶 

* 訊息中心推播 

以下是尚未轉換的Campaign Standard安全性群組對應清單。

* 訊息中心代理程式

* 訊息中心推播代理程式

* Adobe Experience Manager應用程式管理員

* 轉送帳戶
 


 

 


