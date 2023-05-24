---
product: campaign
title: 設定控制規則
description: 瞭解如何設定控制規則
feature: Typology Rules
exl-id: 79e442ea-f856-41bf-b065-25cb2ad2c65b
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 1%

---

# 控制規則{#control-rules}

控制規則可讓您在傳送之前保證訊息的有效性和品質：字元顯示、SMS大小、位址格式等。

一組現成的規則可讓您執行一般的檢查。 這些檢查（在介面中以粗體顯示）包括：

* **[!UICONTROL Object approval]** （電子郵件）：檢查寄件者物件和地址是否不包含特殊字元，這可能造成某些郵件代理程式發生問題。
* **[!UICONTROL URL label approval]** （電子郵件）：檢查每個追蹤URL是否都有標籤。
* **[!UICONTROL URL approval]** （電子郵件）：檢查追蹤URL （存在「&amp;」字元）。
* **[!UICONTROL Message size approval]** （行動）：檢查SMS訊息的大小。
* **[!UICONTROL Validity period check]** （電子郵件）：檢查傳遞的有效期是否足夠長，足以傳送所有訊息。
* **[!UICONTROL Proof size check]** （所有管道）：如果校樣目標母體超過100個收件者，則產生錯誤訊息。
* **[!UICONTROL Wave scheduling check]** （電子郵件）：檢查最後一波傳送是否已排定在有效期間結束前開始（如果傳送會劃分為數個波段）。
* **[!UICONTROL Unsubscription link approval]** （電子郵件）：檢查每個內容(HTML和文字)中是否存在至少一個取消訂閱（選擇退出） URL。

## 建立控制規則 {#create-a-control-rule}

您可以建立新的控制規則以符合您的需求。 若要這麼做，請建立 **[!UICONTROL Control]** 型別規則，並在SQL中輸入控制公式 **[!UICONTROL Code]** 標籤。

**範例:**

在下列範例中，我們將建立規則來防止將SMS選件傳送給超過100個收件者。 此規則將連結至行銷活動型別，然後連結至可使用相關選件的SMS傳送。

應用以下步驟：

1. 建立 **[!UICONTROL Control]** 型別規則。 選取 **[!UICONTROL Warning]** 警示等級。

   ![](assets/campaign_opt_create_control_01.png)

1. 在 **[!UICONTROL Code]** 索引標籤中，輸入指令碼以套用所需的臨界值，如下所示：

   ![](assets/campaign_opt_create_control_02.png)

   如果傳送目標超過100個連絡人，此指令碼會觸發警告：

   ```
   if( delivery.FCP == false && delivery.properties.toDeliver > 100 ) { logWarning("Significant number of SMS to deliver (" + delivery.properties.toDeliver + "). Please make sure the target is correct.") return false; } return true
   ```

1. 將此規則連結至行銷活動型別，並參考相關SMS傳送中的型別。

   ![](assets/campaign_opt_create_control_03.png)

1. 在傳遞分析期間，會套用規則並建立警告（如適用）。

   ![](assets/campaign_opt_create_control_04.png)

   不過，傳遞仍可傳送。

   如果您提高警示等級，這將會阻止傳送的開始。

   ![](assets/campaign_opt_create_control_05.png)

   分析結束時， **[!UICONTROL Confirm delivery]** 按鈕將不可用。

   ![](assets/campaign_opt_create_control_06.png)
