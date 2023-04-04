---
product: campaign
title: Adobe Campaign互動最佳實務
description: 在Adobe Campaign中管理互動模組的最佳實務方法
exl-id: 28f3a5bc-67f5-413e-b2ba-35c341f9ec5f
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '1160'
ht-degree: 0%

---

# 互動最佳實務{#interaction-best-practices}

## 一般性建議 {#general-recommendations}

在Adobe Campaign中管理優惠方案需要謹慎管理，才能有效運作。 為避免出現任何問題，您必須在聯絡人數量與優惠方案類別和優惠方案數量之間找到平衡。

本節提供管理 **互動** Adobe Campaign中的模組，包括適用性規則、預先定義的篩選器、工作流程活動和資料庫選項。

* 當 **實作與設定互動**，您必須注意下列建議：

   * 對於批次引擎（通常用於傳出通訊，例如電子郵件），吞吐量是主要考量，因為可以同時處理多個連絡人。 典型的瓶頸是資料庫效能。
   * 單一引擎的主要限制（通常用於傳入通訊，例如網站上的橫幅）是延遲，因為有人預期會有答案。 典型的瓶頸是CPU效能。
   * 優惠方案目錄設計對Adobe Campaign效能有重大影響。
   * 使用許多優惠方案時，最佳實務是將優惠方案分割為數個優惠方案目錄。

* 以下列出使用時的一些最佳實務 **適用性規則**:

   * 簡化規則。 規則複雜性會影響效能，因為它會延長查詢時間。 複雜規則是指具有超過五個條件的任何規則。
   * 若要提高效能，可以用跨多個選件共用的不同預先定義篩選器來劃分規則。
   * 將限制最嚴格的優惠方案類別規則放在樹狀結構中盡可能最高的位置。 這樣，他們會先篩選出最多的聯絡人，減少目標數量，並防止其被進一步規則處理。
   * 將最昂貴的規則放在樹的底部進行時間或處理。 如此一來，這些規則只會在剩餘的目標對象上執行。
   * 從特定類別開始，以避免掃描整個樹。
   * 為了節省處理時間，請預先計算匯總，而非使用連結建立複雜規則。 要執行此操作，請嘗試將客戶資料儲存在可在適用性規則中查詢的參考表格中。
   * 使用最小權數來限制查詢數。
   * 建議每個優惠方案空間的優惠方案數量有限。 這可確保更快速地擷取任何指定空間中的選件。
   * 使用索引，尤其是常用的查詢欄。

* 以下列出幾個與 **命題表**:

   * 使用最少的規則數量，以盡快處理。
   * 限制主張表中的記錄數：僅保留跟蹤其狀態更新所需的記錄以及規則需要的記錄，然後將其歸檔到其他系統。
   * 對主張表執行密集的資料庫維護，例如重建索引或重新建立表。
   * 限制每個目標所請求的主張數。 請勿設定超出您實際要使用的項目。
   * 盡可能避免在規則條件中加入。

## 管理優惠方案時的提示 {#tips-managing-offers}

本節包含管理優惠方案和使用Adobe Campaign中互動模組的更詳細建議。

### 電子郵件中有多個優惠方案空間 {#multiple-offer-spaces}

將選件納入傳送時，通常會透過 **擴充** 工作流程活動（或其他類似活動）。

在 **擴充** 活動中，您可以選擇要使用哪個優惠方案空間。 不過，無論選取的優惠方案空間為何，傳遞自訂功能表取決於傳遞中設定的優惠方案空間。

在下列範例中，傳送中選取的優惠方案空間為 **[!UICONTROL Email (Environment - Recipient)]**:

![](assets/Interaction-best-practices-offer-space-selected.png)

如果您在傳送中選取的選件空間未設定HTML呈現功能，您就不會在傳送功能表中看到，且將無法供選取。 這與在 **擴充** 活動。

在下列範例中，HTML呈現函式可在下拉式清單中使用，因為傳送中選取的選件空間具有呈現函式：

![](assets/Interaction-best-practices-HTML-rendering.png)

此函式會插入程式碼，例如： `<%@ include proposition="targetData.proposition" view="rendering/html" %>`.

當您選取主張時， **[!UICONTROL view]** 屬性如下：
* &quot;rendering/html&quot;:html呈現。 它使用HTML呈現函式。
* &quot;offer/view/html&quot;:html內容。 它不使用HTML呈現函式。 它只包含HTML欄位。

當您在單一電子郵件傳送中包含多個選件空間，且其中部分內容具有呈現函式，而部分內容沒有，您必須記住哪些選件使用哪些選件空間，哪些選件空間具有呈現函式。

因此，為避免任何問題，建議所有選件空間都定義一個HTML呈現函式，即使您的選件空間僅需要HTML內容亦然。

### 在命題日誌表中設定排名 {#rank-proposition-log-table}

當生成或接受命題時，選件空間能夠將資料儲存在命題表中：

![](assets/Interaction-best-practices-offer-space-storage.png)

不過，這只會套用至入站互動。

使用對外互動時，以及在不使用互動模組使用對外選件時，也可以在主張表格中儲存其他資料。

工作流臨時表中名稱與命題表中的欄位名稱匹配的任何欄位都會複製到命題表中的相同欄位。

例如，手動選取選件時（不進行互動）, **擴充** 工作流程活動，標準欄位的定義如下：

![](assets/Interaction-best-practices-manual-offer-std-fields.png)

可新增其他欄位，例如 `@rank` 欄位：

![](assets/Interaction-best-practices-manual-offer-add-fields.png)

因為主張表中有一個欄位名為 `@rank`，則會複製工作流程臨時表格中的值。

有關在主張表中儲存其他欄位的詳細資訊，請參閱 [本節](interaction-send-offers.md#storing-offer-rankings-and-weights).

對於具有互動的對外優惠方案，當選取了數個優惠方案且您想記錄它們在電子郵件中的顯示順序時，這個用法很有幫助。

您也可以直接在主張表格中儲存其他中繼資料，例如目前的支出層級，以保留在產生選件時有關支出的歷史記錄。

使用傳出互動時， `@rank` 欄位可以新增，如上例所示，但其值會根據互動傳回的順序自動設定。 例如，如果您使用互動來選取三個選件，則 `@rank` 欄位會傳回值1、2和3。

使用「互動」和手動選取選件時，使用者可以結合這兩種方法。 例如，使用者可手動設定 `@rank` 欄位為1（針對手動選取的選件），並使用如 `"1 + @rank"` 針對互動傳回的選件。 假設「互動」選取三個選件，則兩個方法傳回的選件會排名1-4:

![](assets/Interaction-best-practices-manual-offer-combined.png)

### 擴充nms:offer方案 {#extending-nms-offer-schema}

擴充nms:offer結構時，請務必遵循已設定的現成結構：
* 為下的內容儲存定義任何新欄位 `<element name="view">`.
* 每個新欄位需要定義兩次。 一次作為常規XML欄位，另一次作為CDATA XML欄位，名稱后面附加「_jst」。 例如：

   ```
   <element label="Price" name="price" type="long" xml="true"/>
   <element advanced="true" label="Script price" name="price_jst" type="CDATA" xml="true"/>
   ```

* 任何包含要追蹤之URL的欄位都必須放在 `<element name="trackedUrls">` 可在 `<element name="view" >`.
