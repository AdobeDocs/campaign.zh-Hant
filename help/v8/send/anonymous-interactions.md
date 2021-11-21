---
product: campaign
title: 向匿名設定檔提供選件（入站互動）
description: 了解如何向匿名設定檔呈現優惠方案
exl-id: b7a04360-f8c6-4c69-9594-2b44d3f819b7
source-git-commit: 00a88cf9217faf32070a3cd34a2c1ae5243d9a6e
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---

# 匿名互動{#anonymous-interactions}

## 匿名互動環境 {#environment-for-anonymous-interactions}

依預設，促銷活動 **互動** 模組隨附預先設定的環境，以鎖定內建的收件者表格（已識別的選件）。 如果您需要鎖定另一個表、匿名選件的訪客表或自訂收件者表，則必須使用目標對應精靈來建立環境。 [深入了解環境](interaction-env.md).

當您透過對應建立精靈建立匿名環境時， **[!UICONTROL Environment dedicated to incoming anonymous interactions]** 框中的 **[!UICONTROL General]** 標籤。

此 **[!UICONTROL Targeting dimension]** 自動完成。 依預設，它會連結至訪客表格。

此 **[!UICONTROL Visitor folder]** 欄位。 會自動完成，以連結至 **[!UICONTROL Visitors]** 檔案夾。 此欄位可讓您選擇要將訪客設定檔儲存於何處。

![](assets/anonymous_environment_option.png)

>[!NOTE]
>
>如果您想要篩選數種類型的訪客，例如針對一或多個品牌呈現的匿名選件，則需要為每個品牌建立環境，並 **[!UICONTROL Visitors]** 為每個環境鍵入資料夾。

## 匿名互動的選件目錄 {#offer-catalog-for-anonymous-interactions}

就像對外互動一樣，入站互動也會組織在由類別和選件組成的選件目錄中。

若要建立類別和空格，請套用與已識別訪客相同的程式。 請參閱 [建立優惠方案類別](interaction-offer-catalog.md#creating-offer-categories) 和 [建立優惠方案環境](interaction-env.md#creating-an-offer-environment))。

## 匿名訪客 {#anonymous-visitors}

當匿名訪客連線時，可將其提交至Cookie識別程式。 此隱含識別是根據訪客的瀏覽器記錄。

在此步驟中，會比較由Cookie復原的資料與資料庫中的資料。 在某些情況下，訪客會被識別（接著會以隱含方式識別），而在其他情況下，訪客不會被識別（因此會保持匿名）。

若要執行此分析，請針對優惠方案空間，檢查 **[!UICONTROL Implicitly identify the individual based on their browser history]** 選項。

![](assets/identification_anonymous_visitors.png)

## 處理未識別的匿名訪客 {#processing-unidentified-anonymous-visitors}

分析後，如果未識別匿名訪客，您可以將其資料儲存在指定空間。 這可讓您建議專門針對這類訪客的選件，並符合指定的類型規則。

如果沒有任何元素可讓您識別連絡人，或如果您不想向可以隱含識別的連絡人建議已識別的優惠方案，您可以選擇對匿名環境進行備援。

若要這麼做，請檢查 **[!UICONTROL Fall back on an anonymous environment if no individuals were identified]**，然後在 **[!UICONTROL Linked anonymous space]** 指定優惠方案空間時。

![](assets/anonymous_to_anonymous_environment.png)
