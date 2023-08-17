---
product: campaign
title: 等待
description: 進一步瞭解等待工作流程活動
feature: Workflows
exl-id: a9bcb214-5c87-4b26-804a-22b868905022
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 1%

---

# 等待{#wait}



A **等待** 活動會在延遲數秒到幾個月之間的任何時間後啟動其轉變。 等待任務不會阻礙其他任務的執行；當此任務擱置時，工作流程可以並行執行任務。

您可以使用編輯器輸入標籤和等待時間，如以下範例所示：

![](assets/edit_wait.png)

在 **[!UICONTROL Duration]** 欄位，值可以您所選擇的單位表示：（根據運運算元的地區設定）：

* 如果未指定地區設定： **s** 幾秒鐘， **m** 數分鐘， **h** 代表小時， **d** 天數， **y** 數年。 核準時，值會自動轉換為最易讀的單位。

  預設單位為日(**d**)。

* 而如果（舉例來說）地區設定設為「Français」： **s** 幾秒鐘， **mn** 數分鐘， **h** 代表小時， **j** 天數， **m** 幾個月， **a** 數年。 在核準時，值會自動轉換為最易讀的單位，如上述範例所示 **90年代** 已轉換為 **1mn 30s**.

  預設單位為日(**d**)。
