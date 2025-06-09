---
title: 預覽和測試您的電子郵件
description: 瞭解如何在傳送前驗證您的傳遞
feature: Personalization
role: User
level: Beginner
exl-id: 5b9fa90c-c23e-47a7-b2ca-de75da4da2ab
source-git-commit: 70af3bceee67082d6a1bb098e60fd2899dc74600
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 16%

---

# 預覽和測試您的電子郵件 {#preview-test}

定義訊息內容後，您就可以使用測試設定檔來預覽及測試。 如果您已插入[個人化內容](personalize.md)，您可以使用測試設定檔資料檢查此內容在訊息中的顯示方式。 此外，若要偵測訊息內容或個人化設定中可能出現的錯誤，請將校樣傳送至測試設定檔。 每次進行變更時都應傳送校樣，以驗證最新內容。

## 內容預覽 {#preview-content}

在傳送校樣之前，最佳實務是在傳送視窗的預覽區段中檢查訊息內容。

若要預覽訊息內容，請遵循下列步驟：

1. 瀏覽至傳遞的&#x200B;**預覽**&#x200B;標籤。
1. 按一下&#x200B;**[!UICONTROL Test personalization]**&#x200B;按鈕以選取設定檔以填入個人化資料。 您可以在資料庫中選擇特定的收件者、種子地址，或從目標母體中選取設定檔（如果已經定義）。 您也可以檢查內容而不進行個人化。

   ![](assets/test-personalization.png)

1. 會產生預覽，讓您可檢查訊息呈現。 在訊息預覽中，個人化元素會由選取的測試設定檔資料取代。

   ![](assets/test-personalization-with-a-recipient.png)

1. 選取其他測試設定檔，以預覽訊息每個變體的電子郵件呈現。

## 傳送校樣 {#send-proofs}

針對電子郵件傳遞，您可以傳送校樣以驗證訊息內容。 傳送校樣可讓您檢查選擇退出連結、鏡像頁面和任何其他連結、驗證訊息、驗證影像是否顯示、偵測可能的錯誤等。 您可能也會想要在不同裝置檢查您的設計和轉譯。

校樣是一種特定訊息，可讓您在將訊息傳送至主要客群之前先測試訊息。校樣的收件者負責核准訊息：轉譯、內容、個人化設定、設定。

### 校訂收件者 {#proofs-recipients}

校樣目標可以在傳遞範本中定義，或專用於傳遞。 在這兩種情況下，都從&#x200B;**[!UICONTROL To]**&#x200B;連結瀏覽至目標定義畫面，並選取&#x200B;**[!UICONTROL Target of the proofs]**&#x200B;標籤。

![](assets/target-of-proofs.png)

已從&#x200B;**[!UICONTROL Targeting mode]**&#x200B;下拉式清單中選取校訂目標的型別。

* 使用&#x200B;**[!UICONTROL Definition of a specific proof target]**&#x200B;選項選取資料庫中的收件者作為校訂目標。
* 使用&#x200B;**[!UICONTROL Substitution of the address]**&#x200B;選項輸入電子郵件地址，並使用目標收件者資料來驗證內容。 您可以手動輸入替代地址，或從下拉式清單中選取替代地址。 關聯的列舉是替代地址(rcpAddress)。
預設會隨機執行替代，但您可以透過&#x200B;**[!UICONTROL Detail]**&#x200B;圖示從主要目標中選取特定收件者。

  ![](assets/target-of-proofs-substitution-details.png){width="800" align="left"}

  選擇&#x200B;**[!UICONTROL Select a profile (must be included in the target)]**&#x200B;選項並選取收件者。

  ![](assets/target-of-proofs-substitution.png){width="800" align="left"}


* 使用&#x200B;**[!UICONTROL Seed addresses]**&#x200B;選項以使用種子地址作為證明目標。 這些位址可從檔案匯入或手動輸入。

  >[!NOTE]
  >
  >種子地址不屬於預設收件者表格(nms：recipient)，這些地址是在單獨的表格中建立的。 如果您使用新資料擴充收件者表格，則必須使用相同資料擴充種子地址表格。

  在[本節](../audiences/test-profiles.md)中進一步瞭解種子地址。

* 使用&#x200B;**[!UICONTROL Specific target and Seed addresses]**&#x200B;選項結合種子地址和特定的電子郵件地址。 相關設定隨後會在兩個單獨的子標籤中定義。

### 傳送校樣 {#proofs-send}

若要傳送訊息校樣，請遵循下列步驟：

1. 在訊息定義畫面中，按一下&#x200B;**[!UICONTROL Send a proof]**&#x200B;按鈕。
1. 從&#x200B;**[!UICONTROL Send a proof]**&#x200B;視窗，檢查證明收件者。
1. 按一下&#x200B;**[!UICONTROL Analyze]**&#x200B;開始準備校訂訊息。

   ![](assets/send-proof-analyze.png){width="800" align="left"}

1. 傳遞準備完成後，請使用&#x200B;**[!UICONTROL Confirm delivery]**&#x200B;開始傳送證明訊息。

瀏覽至傳遞的&#x200B;**[!UICONTROL Audit]**&#x200B;索引標籤，以檢查證明復本的傳遞。

建議在每次修改訊息內容後傳送校樣。

>[!NOTE]
>
>在傳送的校樣中，指向映象頁面的連結未啟用。 它僅在最終訊息中啟用。

### 校訂屬性 {#proofs-properties}

已在傳遞屬性視窗的&#x200B;**[!UICONTROL Advanced]**&#x200B;索引標籤中設定校訂屬性。 瀏覽至&#x200B;**[!UICONTROL Proof properties...]**&#x200B;連結以定義引數和校訂的標籤。 您可以選擇保留：

* 證明中的重複地址
* 校訂中的已加入封鎖清單的地址
* 證明中的隔離地址

根據預設，主旨中的`Proof #N`提及可識別校訂訊息，其中`N`為校訂號碼。 此數字會隨著每個證明傳遞分析而增加。 您可以視需要變更`proof`首碼。

![](assets/proof-parameters.png){width="800" align="left"}


## 操作說明影片 {#video-proof}

瞭解如何傳送及驗證電子郵件傳遞的校樣。

>[!VIDEO](https://video.tv.adobe.com/v/333404)
