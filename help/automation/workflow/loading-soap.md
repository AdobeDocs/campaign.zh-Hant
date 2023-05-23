---
product: campaign
title: 載入 (SOAP)
description: 載入 (SOAP)
feature: Workflows
exl-id: 21c42a36-9a50-49b8-8a07-b041ba8b2026
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 4%

---

# 載入 (SOAP){#loading-soap}



>[!CAUTION]
>
>的 **載入(SOAP)** 活動僅在您 **FDA（聯合資料存取）** 已安裝模組。 請檢查您的授權合約。

的 **載入(SOAP)** 除 **資料載入(RDBMS)** 當無法通過外部資料庫中的FDA直接收集資料時，將執行活動。

操作如下：

1. 選擇使用XML示例或WSDL。

   以下示例來自消息中心模組的技術工作流。

   ![](assets/load_soap_002.png)

1. 對於XML示例，選擇示例檔案。 分析檔案以建立結果示例。

   對於WSDL，輸入匹配訪問URL，然後生成骨骼代碼。 選定的服務和呼叫將自動更新並顯示。

   ![](assets/soap_load_003.png)

1. 選擇 **[!UICONTROL Click here to view and edit analysis results]** 指定每個標識列。

   ![](assets/soap_load_001.png)

   如果要更新示例，請選擇 **[!UICONTROL Re-analyze the example]**。

1. 您可以將行號用作標識符和/或指定SOAP調用返回多個元素。
1. 根據頁籤指令碼的功能輸入以下頁籤指令碼：

   * **[!UICONTROL Initialization]**:建立SOAP連接。
   * **[!UICONTROL Iteration]**:執行對SOAP服務的調用。 此函式的返回必須是與示例或WSDL的說明相容的XML對象。

      此頁籤的代碼將由Adobe Campaign在循環中調用，直到返回空XML對象。

   * **[!UICONTROL Finalization]**:關閉連接和/或釋放處理過程中建立的其他資源。
