---
title: 傳遞分析
description: 了解如何準備和檢查您的傳遞內容
feature: Personalization
role: User
level: Beginner
source-git-commit: 8f04981e38da79e69afc890311c559f9ffa136f4
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 0%

---

# 傳遞分析 {#analyze-delivery}

分析是傳遞準備步驟。 定義目標對象後，訊息內容就可開始使用並測試。 在傳遞分析期間，會計算目標母體，並準備傳遞內容。 完成傳遞後，即可傳送。

## 開始分析 {#start-the-analysis}

若要準備傳送，請確定已定義傳送內容和目標，並遵循下列步驟：

1. 在傳送視窗中，按一下 **[!UICONTROL Send]** 按鈕。
1. 選擇 **[!UICONTROL Deliver as soon as possible]** 以執行對象計算，以及立即傳送的內容準備。 您也可以將傳送延遲至較晚的日期，或在不準備內容的情況下取得母體的估計。

   ![](assets/delivery-analysis-start.png)

1. 按一下 **[!UICONTROL Analyze]** 以手動啟動分析。 進度列會顯示分析的進度。

   集檢查規則會在傳送分析期間套用。 這些規則定義於 **類型**，在 **[!UICONTROL Typology]** 標籤。 深入了解 [本節](../../automation/campaign-opt/campaign-typologies.md).

   依預設，對於電子郵件，分析涵蓋下列幾點：

   * 核准物件
   * 核准URL和影像
   * 核准URL標籤
   * 核准取消訂閱連結
   * 檢查校樣的大小
   * 檢查有效期
   * 檢查波的調度


1. 您可以隨時按一下 **[!UICONTROL Stop]** 按鈕。

   準備階段期間不會傳送任何訊息。 因此，您可以開始或取消分析，而無風險。

   >[!IMPORTANT]
   >
   >執行時，分析會凍結傳送（或校樣）。 傳送的任何變更（或證明）都必須先進行其他分析，才能適用。

分析完成時，視窗的上方區段會指出傳送準備是否完成或是否發生任何錯誤。 列出所有驗證步驟、警告和錯誤。 彩色表徵圖顯示消息類型：

* 藍色圖示表示資訊性訊息。
* 黃色表徵圖表示非關鍵處理錯誤。
* 紅色圖示表示無法傳送傳送的重大錯誤。

   ![](assets/delivery-analysis-results.png){width="800" align="left"}

1. 按一下 **[!UICONTROL Close]** 以更正錯誤（如果有）。 進行變更後，請按一下「 」以重新啟動分析 **[!UICONTROL Analyze]**.

   >[!NOTE]
   >
   >按一下 **[!UICONTROL Change the main delivery target]** 如果要傳送的訊息數量不符合您的期望，則連結。 此選項可讓您變更目標母體的定義並重新啟動分析。

1. 檢查分析結果後，按一下 **[!UICONTROL Confirm delivery]** 將訊息傳送至主要目標。


## 分析設定 {#analysis-settings}

瀏覽至 **[!UICONTROL Analysis]** 索引標籤，以定義分析階段期間訊息準備的設定。

![](assets/delivery-properties-analysis-tab.png){width="800" align="left"}

此索引標籤可供存取下列選項：

* **[!UICONTROL Label and code of the delivery]** :本區段中的選項可用來計算傳送分析階段期間這些欄位的值。 此 **[!UICONTROL Compute the execution folder during the delivery analysis]** 欄位會計算在分析階段期間包含此傳送動作的資料夾名稱。

* **[!UICONTROL Approval mode]** :分析完成後，此欄位可讓您定義手動或自動傳送。

   如果分析期間產生警告（例如，如果傳送的主旨中會強調某些字元等），您可以設定傳送以定義是否應仍執行該傳送。 依預設，使用者必須在分析階段結束時確認訊息的傳送：這是 **手動** 驗證。

   從適當欄位的下拉式清單中選取其他核准模式。

   提供下列核准模式：

   * **[!UICONTROL Manual]**:在分析階段結束時，使用者必須確認傳送以開始傳送。 若要這麼做，請按一下 **[!UICONTROL Start]** 按鈕以啟動傳送。
   * **[!UICONTROL Semi-automatic]**:如果分析階段未產生警告訊息，則會自動開始傳送。
   * **[!UICONTROL Automatic]**:無論結果如何，發送都會在分析階段結束時自動開始。

* **[!UICONTROL Start job in a detached process]** :此選項可讓您以個別程式開始傳送分析。 依預設，分析函式會使用Adobe Campaign應用程式伺服器程式(web nlserver)。 通過選擇此選項，您確保即使在應用程式伺服器出現故障時也能完成分析。
* **[!UICONTROL Log SQL queries generated during the analysis in the journal]** :此選項會在分析階段期間將SQL查詢日誌添加到傳遞日誌。
* **[!UICONTROL Ignore personalization scripts during sending]** :此選項可讓您略過HTML內容中找到的JavaScript指令的解譯。 它們會如傳送內容中所示顯示。 這些指令與 `<%=` 標籤。


