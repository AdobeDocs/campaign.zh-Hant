---
product: campaign
title: 向匿名配置檔案提供優惠（入站交互）
description: 瞭解如何向匿名配置檔案顯示優惠
exl-id: b7a04360-f8c6-4c69-9594-2b44d3f819b7
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---

# 匿名互動{#anonymous-interactions}

## 用於匿名交互的環境 {#environment-for-anonymous-interactions}

預設情況下，市場活動 **交互** 模組附帶一個預配置的環境，以針對內置的收件人表（已識別的優惠）。 如果需要將另一個表、匿名聘用的訪問者表或自定義收件人表作為目標，則必須使用目標映射嚮導來建立環境。 [瞭解有關環境的更多資訊](interaction-env.md)。

通過映射建立嚮導建立匿名環境時， **[!UICONTROL Environment dedicated to incoming anonymous interactions]** 框中 **[!UICONTROL General]** 頁籤。

的 **[!UICONTROL Targeting dimension]** 自動完成。 預設情況下，它連結到訪問者表。

的 **[!UICONTROL Visitor folder]** 的子菜單。 自動完成以連結到 **[!UICONTROL Visitors]** 的子菜單。 此欄位允許您選擇儲存訪問者配置檔案的位置。

![](assets/anonymous_environment_option.png)

>[!NOTE]
>
>如果要過濾幾種類型的訪問者，例如，對於一個或多個品牌提供的匿名優惠，您需要為每個品牌建立一個環境，並 **[!UICONTROL Visitors]** 為每個環境鍵入資料夾。

## 為匿名交互提供目錄 {#offer-catalog-for-anonymous-interactions}

就像出站交往一樣，入站交往也被組織在由類別和聘用組成的聘用目錄中。

要建立類別和空間，請應用與已標識訪問者相同的流程。 請參閱 [建立聘用類別](interaction-offer-catalog.md#creating-offer-categories) 和 [建立服務環境](interaction-env.md#creating-an-offer-environment))。

## 匿名訪問者 {#anonymous-visitors}

當匿名訪問者連接時，可將其提交到cookie標識進程。 這種隱含的識別是基於訪問者的瀏覽器歷史。

在此步驟中，將比較由cookie恢復的資料與資料庫中的資料。 在某些情況下，訪問者被識別（然後隱含地識別），在其他情況下，訪問者不被識別（因此仍然匿名）。

要運行此分析，請對於聘用空間，檢查 **[!UICONTROL Implicitly identify the individual based on their browser history]** 的雙曲餘切值。

![](assets/identification_anonymous_visitors.png)

## 處理未識別的匿名訪問者 {#processing-unidentified-anonymous-visitors}

分析後，如果未識別匿名訪問者，則可以將其資料儲存在給定空間中。 這將允許您建議專門針對此類訪問者的服務，並與指定的類型規則匹配。

如果沒有允許您標識聯繫人的要素，或者如果您不想向可隱式標識的聯繫人建議已標識的優惠，則可以選擇對匿名環境執行回退。

要執行此操作，請檢查 **[!UICONTROL Fall back on an anonymous environment if no individuals were identified]**，然後在 **[!UICONTROL Linked anonymous space]** 指定聘用空間時。

![](assets/anonymous_to_anonymous_environment.png)
