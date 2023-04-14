---
title: 預覽和測試您的電子郵件
description: 了解如何在傳送前驗證傳遞內容
feature: Personalization
role: User
level: Beginner
exl-id: 5b9fa90c-c23e-47a7-b2ca-de75da4da2ab
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 4%

---

# 預覽和測試您的電子郵件 {#preview-test}

定義訊息內容後，您就可以使用測試設定檔進行預覽及測試。 如果您已插入 [個人化內容](personalize.md)，您可以使用測試設定檔資料，檢查訊息中此內容的顯示方式。 此外，若要偵測訊息內容或個人化設定中可能的錯誤，請傳送校樣至測試設定檔。 每次進行變更時都應傳送校樣，以驗證最新內容。

## 內容預覽{#preview-content}

傳送校樣之前，最佳實務是檢查傳送視窗預覽區段中的訊息內容。

若要預覽訊息內容，請遵循下列步驟：

1. 瀏覽至 **預覽** 標籤。
1. 按一下 **[!UICONTROL Test personalization]** 按鈕，以選取要填入個人化資料的設定檔。 您可以在資料庫中選擇特定收件者、種子地址，或從目標母體中選擇配置檔案（如果已定義）。 您也可以檢查內容而不需個人化。

   ![](assets/test-personalization.png)

1. 系統會產生預覽，讓您檢查訊息呈現。 在訊息預覽中，個人化元素會由選取的測試設定檔資料取代。

   ![](assets/test-personalization-with-a-recipient.png)

1. 選取其他測試設定檔，以針對訊息的每個變體預覽電子郵件呈現。

## 傳送校樣 {#send-proofs}

對於電子郵件傳遞，您可以傳送校樣以驗證訊息內容。 傳送校樣可讓您檢查選擇退出連結、鏡像頁面和任何其他連結、驗證訊息、確認影像已顯示、偵測可能的錯誤等。 您也可能想要檢查您的設計和在不同裝置上呈現。

校樣是特定訊息，可讓您在將訊息傳送給主要對象之前先測試訊息。 校樣的收件者負責核准訊息：轉譯、內容、個人化設定、設定。

### 校樣收件者 {#proofs-recipients}

校樣目標可在傳遞範本中定義，或特定於傳遞。 在這兩種情況下，請從 **[!UICONTROL To]** 連結，然後選取 **[!UICONTROL Target of the proofs]** 標籤。

![](assets/target-of-proofs.png)

校樣目標的類型從 **[!UICONTROL Targeting mode]** 下拉式清單。

* 使用 **[!UICONTROL Definition of a specific proof target]** 選項，以在資料庫中選取收件者作為校樣目標。
* 使用 **[!UICONTROL Substitution of the address]** 選項，輸入電子郵件地址並使用target收件者資料來驗證內容。 可以手動輸入替代地址，或從下拉清單中選擇替代地址。 關聯的枚舉為替代地址(rcpAddress)。
預設會隨機執行替代，但您可以透過  **[!UICONTROL Detail]** 表徵圖。

   ![](assets/target-of-proofs-substitution-details.png){width="800" align="left"}

   選擇 **[!UICONTROL Select a profile (must be included in the target)]** 選項並選取收件者。

   ![](assets/target-of-proofs-substitution.png){width="800" align="left"}


* 使用 **[!UICONTROL Seed addresses]**  選項，將種子地址用作校樣目標。 可從檔案匯入或手動輸入這些地址。

   >[!NOTE]
   >
   >種子地址不屬於預設收件人表(nms:recipient)，它們將建立在單獨的表中。 如果使用新資料擴展收件者表，則必須擴展種子地址表以及使用相同資料擴展種子地址表。

   進一步了解種子地址，位於 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target="_blank"}.

* 使用 **[!UICONTROL Specific target and Seed addresses]** 選項來結合種子地址和特定電子郵件地址。 然後，在兩個不同的子標籤中定義相關配置。

### 傳送證明{#proofs-send}

若要傳送訊息校樣，請遵循下列步驟：

1. 在訊息定義畫面中，按一下 **[!UICONTROL Send a proof]** 按鈕。
1. 從 **[!UICONTROL Send a proof]** ，檢查校樣收件者。
1. 按一下 **[!UICONTROL Analyze]** 開始校樣訊息準備。

   ![](assets/send-proof-analyze.png){width="800" align="left"}

1. 傳送準備完成後，請使用 **[!UICONTROL Confirm delivery]** 開始傳送校樣訊息。

瀏覽至 **[!UICONTROL Audit]** 索引標籤，以檢查校樣副本的傳送。

建議在每次修改後傳送校樣至訊息內容。

>[!NOTE]
>
>在傳送的校樣中，鏡像頁面的連結未作用中。 它只會在最終訊息中啟動。

### 校樣屬性{#proofs-properties}

校樣屬性設定於 **[!UICONTROL Advanced]** 頁簽。 瀏覽至 **[!UICONTROL Proof properties...]** 連結以定義校樣的參數和標籤。 您可以選擇保留：

* 校樣中的重複地址
* 校樣中已拒絕列出的地址
* 校樣中的隔離地址

依預設，校樣訊息的識別方式為 `Proof #N` 在主題中提及， `N` 是校樣號碼。 此數字會隨著每次校樣傳送分析而增加。 您可以變更 `proof` 前置詞，視需要。

![](assets/proof-parameters.png){width="800" align="left"}


## 作法影片 {#video-proof}

瞭解如何傳送及驗證電子郵件傳遞的校樣。

>[!VIDEO](https://video.tv.adobe.com/v/333404)
