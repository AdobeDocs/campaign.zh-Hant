---
product: campaign
title: 工作流程生命週期
description: 進一步瞭解工作流程的生命週期
feature: Workflows
exl-id: 4356b90c-9d7c-49ef-88cd-716b2ccdb7f0
source-git-commit: 7f6c394f56d517c0a675e0fd2341bb6ef98044f0
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 2%

---

# 工作流程生命週期 {#workflow-life-cycle}



工作流程週期有三個主要步驟。

* **正在編輯**

  這是初始設計階段：建立新工作流程時，其狀態為「正在編輯」。 伺服器尚未處理工作流程，且修改工作流程時不會有風險。

* **已開始**

  完成初始設計階段後，即可開始工作流程。 在此階段中，執行個體是由伺服器處理，而個別工作則會執行。 仍可藉由某些預防措施來修改工作流程。

* **已完成**

  當沒有任何正在進行的任務或運運算元已明確停止執行個體時，工作流程為「已完成」。

例如， **開始** 和 **傳遞** 活動會進行概述，而 **核准** 活動會在下方的工作流程中閃爍。

![](assets/new-workflow-6.png)

這表示前兩個活動已成功執行，且核准正在進行中，即已建立但尚未完成。

字元 **574 — 確定** 顯示在轉變上方，緊接在 **傳遞** 活動表示傳遞準備已鎖定到574位收件者，且操作已成功完成。 這項資訊在執行時新增至轉變中，由處理資料的活動計算。

工作流程已啟動，且正在等候屬於中指定的群組的運運算元。 **核准** 進行決策的活動。 屬於群組且擁有電子郵件地址或行動電話號碼的運運算元會收到通知。

有關如何監視工作流程的詳細資訊，請參閱 [本節](monitor-workflow-execution.md).
