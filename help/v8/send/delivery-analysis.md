---
title: 傳遞分析
description: 瞭解如何準備並檢查您的傳遞
feature: Personalization
role: User
level: Beginner
exl-id: 1526048d-9f02-4853-948f-8fb618670dbd
source-git-commit: 69ff08567f3a0ab827a118a089495fc75bb550c5
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 5%

---

# 傳遞分析 {#analyze-delivery}

分析是傳送準備步驟。 一旦定義目標對象，且訊息內容準備好並進行測試後，即可啟動它。 在傳遞分析期間，會計算目標母體並準備傳遞內容。 完成傳遞後，便可傳送內容。

## 開始分析 {#start-the-analysis}

若要準備傳遞，請確定已定義傳遞內容和目標，然後遵循下列步驟：

1. 在傳遞視窗中，按一下&#x200B;**[!UICONTROL Send]**&#x200B;按鈕。
1. 選取&#x200B;**[!UICONTROL Deliver as soon as possible]**&#x200B;以執行對象計算，並準備立即傳送的內容。 您也可以將傳送延遲到較晚的日期，或是在未準備內容的情況下取得母體預估值。

   ![](assets/delivery-analysis-start.png)

1. 按一下&#x200B;**[!UICONTROL Analyze]**&#x200B;以手動啟動分析。 進度列會顯示分析的進度。

   一組檢查規則會在傳遞分析期間套用。 這些規則是在&#x200B;**型別**&#x200B;中定義，該型別是在傳遞屬性的&#x200B;**[!UICONTROL Typology]**&#x200B;索引標籤中選取的。 在[本節](../../automation/campaign-opt/campaign-typologies.md)中進一步瞭解型別。

   針對電子郵件，預設分析會涵蓋下列幾點：

   * 核准物件
   * 核准URL和影像
   * 核准URL標籤
   * 核准取消訂閱連結
   * 檢查校樣的大小
   * 檢查有效期
   * 檢查波段排程


1. 您可以隨時按一下&#x200B;**[!UICONTROL Stop]**&#x200B;按鈕來停止分析。

   在準備階段期間不會傳送任何訊息。 因此，您可以開始或取消分析而不會有風險。

   >[!IMPORTANT]
   >
   >執行時，分析會凍結傳送（或證明）。 對傳送（或證明）所做的任何變更都必須先進行其他分析，才能適用。

   分析完成後，視窗的上半部會指出傳遞準備是否已完成或是否發生任何錯誤。 會列出所有驗證步驟、警告和錯誤。彩色圖示顯示訊息類型：

   * 藍色圖示表示資訊訊息。
   * 黃色圖示表示非關鍵性處理錯誤。
   * 紅色圖示表示嚴重錯誤，無法傳送傳遞。

   ![](assets/delivery-analysis-results.png){width="800" align="left"}

1. 按一下&#x200B;**[!UICONTROL Close]**&#x200B;以更正錯誤（如果有的話）。 進行變更後，按一下&#x200B;**[!UICONTROL Analyze]**&#x200B;重新啟動分析。

   >[!NOTE]
   >
   >如果要傳送的訊息數目不符合您的預期，請按一下&#x200B;**[!UICONTROL Change the main delivery target]**&#x200B;連結。 此選項可讓您變更目標母體的定義，並重新啟動分析。
   >

1. 檢查完分析結果後，按一下&#x200B;**[!UICONTROL Confirm delivery]**&#x200B;將訊息傳送至主要目標。


## 分析設定 {#analysis-settings}

瀏覽至傳遞屬性的&#x200B;**[!UICONTROL Analysis]**&#x200B;標籤，以定義分析階段中訊息準備的設定。

![](assets/delivery-properties-analysis-tab.png){width="800" align="left"}

此索引標籤提供下列選項的存取權：

* **[!UICONTROL Label and code of the delivery]**：此區段中的選項是用來在傳遞分析階段計算這些欄位的值。 **[!UICONTROL Compute the execution folder during the delivery analysis]**&#x200B;欄位會在分析階段期間計算將包含此傳遞動作的資料夾名稱。

* **[!UICONTROL Approval mode]**：此欄位可讓您定義分析完成時的手動或自動傳遞。

  如果在分析期間產生警告（例如，如果傳送主題中的某些字元強調等），您可以設定傳送以定義是否仍應執行。 依預設，使用者必須在分析階段結束時確認傳送訊息：這是&#x200B;**手動**&#x200B;驗證。

  從適當欄位的下拉式清單中選取其他核准模式。

  可使用下列核准模式：

   * **[!UICONTROL Manual]**：在分析階段結束時，使用者必須確認傳遞才能開始傳送。 若要這麼做，請按一下&#x200B;**[!UICONTROL Start]**&#x200B;按鈕以啟動傳遞。
   * **[!UICONTROL Semi-automatic]**：如果分析階段未產生任何警告訊息，傳送會自動開始。
   * **[!UICONTROL Automatic]**：傳送會在分析階段結束時自動開始，無論結果為何。

* **[!UICONTROL Start job in a detached process]**：此選項可讓您以個別程式啟動傳遞分析。 依預設，分析函式會使用Adobe Campaign應用程式伺服器處理序(web nlserver)。 選取此選項，即可確保即使應用程式伺服器發生故障，也能完成分析。
* **[!UICONTROL Log SQL queries generated during the analysis in the journal]**：此選項會在分析階段將SQL查詢記錄檔新增至傳遞日誌。
* **[!UICONTROL Ignore personalization scripts during sending]**：此選項可讓您略過HTML內容中JavaScript指示詞的解譯。 它們將顯示為已傳送內容中的原樣。 這些指示詞是隨`<%=`標籤匯入的。
