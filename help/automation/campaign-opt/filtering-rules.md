---
product: campaign
title: 配置篩選規則
description: 瞭解如何配置篩選規則
feature: Typology Rules
exl-id: 17507cdf-211f-4fa2-abb9-33d4f6dc47bb
source-git-commit: 7fe079c5473fa164405753c2be6cc8be16329f58
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 1%

---

# 篩選規則{#filtering-rules}

使用篩選規則根據查詢中定義的條件選擇要排除的消息。 這些規則連結到目標維。

過濾規則可以連結到其他類型的規則（控制、壓力等） 或按專用 **篩選** 類型學。 [了解更多](#create-and-use-a-filtering-typology)。

## 建立篩選規則 {#create-a-filtering-rule}

例如，您可以過濾新聞稿訂閱者，以防止將通信發送給未達到法定年齡的收件人。

要定義此篩選器，請應用以下步驟：

1. 瀏覽到 **[!UICONTROL Administration > Campaign management > Typology management > Typology rules]** 市場活動展示器的資料夾，然後按一下 **新建** 表徵圖以建立類型規則。
1. 建立 **[!UICONTROL Filtering]** 適用於所有渠道的類型規則。

   ![](assets/campaign_opt_create_filter_01.png)

1. 從 **篩選** 頁籤將預設目標維更改為 **訂閱** (**nms：訂閱**)。

   ![](assets/campaign_opt_create_filter_02.png)

1. 使用 **[!UICONTROL Edit the query from the targeting dimension...]** 的子菜單。

   ![](assets/campaign_opt_create_filter_03.png)

1. 在收件人年齡上篩選並保存篩選條件。

   ![](assets/campaign_opt_create_filter_03b.png)

1. 從 **類型** 頁籤，將此規則連結到市場活動類型並保存。

   ![](assets/campaign_opt_create_filter_04.png)

當此規則在交貨中使用時，未達到要求的訂戶將自動排除。 特定消息指明應用規則的時間：

![](assets/campaign_opt_create_filter_05.png)

## 條件篩選規則 {#condition-a-filtering-rule}

您可以基於連結的交貨或交貨大綱來限制篩選規則的應用程式欄位。

要執行此操作，請轉到 **[!UICONTROL General]** 頁籤，選擇要應用的限制類型並建立篩選器。
<!--
![](assets/campaign_opt_create_filter_06.png)
-->


在這種情況下，即使規則連結到所有交貨，它也將只應用於那些與定義的篩選器的標準相匹配的交貨。

>[!NOTE]
>
>類型和篩選規則可用於工作流， **[!UICONTROL Delivery outline]** 的子菜單。 [了解更多](../workflow/delivery-outline.md)。

## 建立和使用篩選類型 {#create-and-use-a-filtering-typology}

您可以建立 **[!UICONTROL Filtering]** 類型：它們只包含過濾規則。

![](assets/campaign_opt_create_typo_filtering.png)

選擇目標後，這些特定類型可以連結到傳遞：在交付嚮導中，按一下 **[!UICONTROL To]** 連結，然後按一下 **[!UICONTROL Exclusions]** 頁籤。

![](assets/campaign_opt_apply_typo_filtering.png)

然後選擇要應用於遞送的過濾類型。 要執行此操作，請按一下 **[!UICONTROL Add]** 按鈕並選擇要應用的類型。

您也可以通過此頁籤直接連結過濾規則，而不將其按類型分組。 為此，請使用窗口的下部。

![](assets/campaign_opt_select_typo_filtering.png)

>[!NOTE]
>
>選擇窗口中只有類型和篩選規則可用。
>
>這些配置可以在交貨模板中定義，以便自動應用於使用該模板建立的所有新交貨。

## 預設可交付性排除規則 {#default-deliverability-exclusion-rules}

預設情況下，有兩個篩選規則可用： **[!UICONTROL Exclude addresses]** ( **[!UICONTROL addressExclusions]** ) **[!UICONTROL Exclude domains]** ( **[!UICONTROL domainExclusions]** )。 在電子郵件分析期間，這些規則將收件人電子郵件地址與包含在可傳送性實例中管理的加密全局禁止清單中的禁止地址或域名進行比較。 如果存在匹配項，則不會將消息發送到該收件人。

這是為了避免由於惡意活動而被添加到密鑰清單，特別是使用垃圾郵件陷阱。 例如，如果使用Spamtrap通過您的一個Web表單訂閱，則會自動向該Spamtrap發送確認電子郵件，這將導致您的地址被自動添加到密鑰清單中。

>[!NOTE]
>
>全局隱藏清單中包含的地址和域名將被隱藏。 在傳遞分析日誌中只指示排除的收件人數。
