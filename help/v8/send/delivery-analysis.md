---
title: 傳遞分析
description: 瞭解如何準備和檢查交付
feature: Personalization
role: User
level: Beginner
exl-id: 1526048d-9f02-4853-948f-8fb618670dbd
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 5%

---

# 傳遞分析 {#analyze-delivery}

分析是遞送準備步驟。 定義目標受眾並準備好並測試消息內容後，即可啟動它。 在遞送分析期間，計算目標總量並準備遞送內容。 完成後，即可發送。

## 啟動分析 {#start-the-analysis}

要準備交付，請確保已定義交付內容和目標，並按照以下步驟操作：

1. 在交貨窗口中，按一下 **[!UICONTROL Send]** 按鈕
1. 選擇 **[!UICONTROL Deliver as soon as possible]** 執行受眾計算和內容準備，以便立即發送。 您還可以將交付推遲到以後，或在不準備內容的情況下獲得人口估計。

   ![](assets/delivery-analysis-start.png)

1. 按一下 **[!UICONTROL Analyze]** 手動啟動分析。 進度欄顯示分析的進度。

   在交貨分析期間應用集檢查規則。 這些規則在 **類型學**，在 **[!UICONTROL Typology]** 的子菜單。 瞭解有關中類型的詳細資訊 [此部分](../../automation/campaign-opt/campaign-typologies.md)。

   預設情況下，對於電子郵件，分析涵蓋以下幾點：

   * 批准對象
   * 批准URL和影像
   * 批准URL標籤
   * 正在批准取消訂閱連結
   * 檢查校樣的大小
   * 檢查有效期
   * 檢查波次的調度


1. 可通過按一下 **[!UICONTROL Stop]** 按鈕

   在準備階段不發送任何消息。 因此，您可以啟動或取消分析，而無風險。

   >[!IMPORTANT]
   >
   >運行時，分析將凍結交貨（或證明）。 對交貨（或證據）的任何更改，必須先進行另一分析，然後才能生效。

   分析完成後，窗口的上半部分將指示交貨準備是否完成或是否出現錯誤。 會列出所有驗證步驟、警告和錯誤。彩色圖示顯示訊息類型：

   * 藍色表徵圖表示資訊性消息。
   * 黃色表徵圖表示非臨界處理錯誤。
   * 紅色表徵圖表示嚴重錯誤，導致無法發送傳遞。

   ![](assets/delivery-analysis-results.png){width="800" align="left"}

1. 按一下 **[!UICONTROL Close]** 更正錯誤（如果有）。 進行更改後，重新啟動分析，按一下 **[!UICONTROL Analyze]**。

   >[!NOTE]
   >
   >按一下 **[!UICONTROL Change the main delivery target]** 連結。 此選項允許您更改目標填充的定義並重新啟動分析。

1. 檢查分析結果後，按一下 **[!UICONTROL Confirm delivery]** 將消息發送到主目標。


## 分析設定 {#analysis-settings}

瀏覽到 **[!UICONTROL Analysis]** 頁籤，以定義分析階段消息準備的設定。

![](assets/delivery-properties-analysis-tab.png){width="800" align="left"}

此頁籤允許訪問以下選項：

* **[!UICONTROL Label and code of the delivery]** :此部分中的選項用於在交貨分析階段計算這些欄位的值。 的 **[!UICONTROL Compute the execution folder during the delivery analysis]** 欄位將計算在分析階段包含此傳遞操作的資料夾的名稱。

* **[!UICONTROL Approval mode]** :此欄位允許您在分析完成後定義人工或自動交付。

   如果在分析期間生成警告（例如，如果某些字元在傳遞的主題中突出等），則可以配置傳遞以定義是否仍應執行它。 依預設，使用者必須在分析階段結束時確認傳送訊息：這是&#x200B;**手動**&#x200B;驗證。

   從相應欄位的下拉清單中選擇另一個批准模式。

   可使用以下審批模式：

   * **[!UICONTROL Manual]**:在分析階段結束時，用戶必須確認發送開始。 要執行此操作，請按一下 **[!UICONTROL Start]** 按鈕啟動交貨。
   * **[!UICONTROL Semi-automatic]**:如果分析階段未生成警告消息，則自動開始發送。
   * **[!UICONTROL Automatic]**:發送在分析階段結束時自動開始，而與其結果無關。

* **[!UICONTROL Start job in a detached process]** :此選項允許您在單獨的進程中啟動交貨分析。 預設情況下，分析函式使用Adobe Campaign應用程式伺服器進程(web nlserver)。 通過選擇此選項，可確保即使在應用程式伺服器出現故障時也能完成分析。
* **[!UICONTROL Log SQL queries generated during the analysis in the journal]** :此選項在分析階段將SQL查詢日誌添加到傳遞日誌。
* **[!UICONTROL Ignore personalization scripts during sending]** :此選項允許您繞過在HTML內容中找到的JavaScript指令的解釋。 它們將像在已傳送內容中一樣顯示。 這些指令與 `<%=` 標籤。
