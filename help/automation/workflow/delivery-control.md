---
product: campaign
title: 傳遞控制
description: 進一步瞭解傳遞控制工作流程活動
feature: Workflows
exl-id: 09fe638d-5e1c-49d1-9196-6300c1e56703
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 5%

---

# 傳遞控制{#delivery-control}



A **傳遞控制**-type動作可讓您開始、暫停或停止傳遞。

這可以是轉變中指定的傳遞、明確選取的傳遞或指令碼計算的傳遞。 有關詳細資訊，請參閱 [傳遞](delivery.md).

![](assets/edit_diffusion_act.png)

如果您選取 **[!UICONTROL Start]**，活動會執行開始傳送所需的所有步驟（目標計算、內容準備、傳送）。 如果先前的工作流程活動已執行其中某些步驟，則不會再執行這些步驟。 例如，如果目標估計已經由 **[!UICONTROL Delivery]** 型別活動(請參閱 [傳遞](delivery.md))， **[!UICONTROL Act on the delivery]** 活動將啟動其餘步驟（內容準備和傳送）。

可以使用以下選項：

* **[!UICONTROL Generate an outbound transition]**

  建立將在執行結束時啟用的出站轉變。 您可以選擇是否要擷取傳出傳遞的目標。

* **[!UICONTROL Processing errors]**

  請參閱 [正在處理錯誤](monitor-workflow-execution.md#processing-errors).

## 輸入引數 {#input-parameters}

* deliveryId

傳遞識別碼，如果選取的動作為 **[!UICONTROL Specified in the transition]**.
