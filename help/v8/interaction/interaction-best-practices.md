---
product: campaign
title: Adobe Campaign互動最佳實務
description: 在Adobe Campaign中管理互動模組的最佳實務方法
feature: Interaction, Offers
role: User, Admin
exl-id: 28f3a5bc-67f5-413e-b2ba-35c341f9ec5f
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 0%

---

# 互動最佳實務 {#interaction-best-practices}

## 一般性建議 {#general-recommendations}

在Adobe Campaign中管理優惠方案需要謹慎的管理，才能有效運作。 若要避免發生任何問題，您必須在聯絡人數量與優惠方案類別和優惠方案數量之間找到平衡。

本節提供管理的最佳實務 **互動** Adobe Campaign模組，包括適用性規則、預先定義的篩選器、工作流程活動和資料庫選項。

* 時間 **實作和設定互動**，您必須注意下列建議：

   * 對於批次引擎（通常用於電子郵件之類的傳出通訊），吞吐量是主要問題，因為可同時處理多個聯絡人。 典型的瓶頸是資料庫效能。
   * 單一引擎的主要限制（通常用於網站橫幅之類的傳入通訊）是延遲，因為有人正在期待答案。 典型的瓶頸是CPU效能。
   * 優惠方案目錄設計對Adobe Campaign的效能有巨大影響。
   * 使用許多優惠方案時，最佳實務是將優惠方案分割為數個優惠方案目錄。

* 以下列出使用時的一些最佳實務 **適用性規則**：

   * 簡化規則。 規則複雜性會因延伸查詢而影響效能。 複雜規則是指具有五個以上條件的任何規則。
   * 若要提高效能，可在多個選件間共用的不同預先定義篩選器中劃分規則。
   * 將限制最嚴格的選件類別規則放在樹狀結構中最高的位置。 這樣一來，他們會先篩選掉最多聯絡人，減少目標數量，並防止其他規則處理這些聯絡人。
   * 將時間或處理成本最高的規則放在樹狀結構底部。 這麼做時，這些規則只會在剩餘的目標對象上執行。
   * 從特定類別開始，以避免掃描整個樹狀結構。
   * 為了節省處理時間，請預先計算彙總，而非使用聯結來建置複雜的規則。 若要這麼做，請嘗試將客戶資料儲存在參考表格中，可在適用性規則中查詢該表格。
   * 使用最小權重來限制查詢數量。
   * 建議每個優惠方案空間中的優惠方案數量有限。 這可確保在任何指定空間中更快地擷取選件。
   * 使用索引，尤其是在常用的查閱欄上。

* 以下列出幾項最佳實務准則， **主張表格**：

   * 使用最少的規則數讓處理速度儘可能快。
   * 限制主張表格中的記錄數量：僅保留追蹤其狀態更新以及規則所需的記錄，然後將它們封存到另一個系統中。
   * 對主張表格執行大量資料庫維護，例如重建索引或重新建立表格。
   * 限制每個目標要求的主張數。 請勿設定超過您實際要使用的專案。
   * 在規則條件中儘可能避免聯結。

## 管理優惠方案時的提示 {#tips-managing-offers}

本節包含有關管理優惠方案與Adobe Campaign中使用互動模組的更多詳細建議。

### 電子郵件中的多個優惠方案空間 {#multiple-offer-spaces}

在傳遞中包含優惠方案時，通常會透過在行銷活動工作流程中的上游選取優惠方案 **擴充** 工作流程活動（或其他類似活動）。

在中選取選件時 **擴充** 活動，您可以選擇要使用的選件空間。 但是，無論所選的優惠方案空間為何，傳送自訂功能表都取決於傳送中設定的優惠方案空間。

在以下範例中，在傳送中選取的優惠方案空間為 **[!UICONTROL Email (Environment - Recipient)]**：

![](assets/Interaction-best-practices-offer-space-selected.png)

如果您在傳送中選取的優惠方案空間未設定HTML演算功能，您會在傳送功能表中看到該空間，且將無法選取。 這與中選取的優惠方案空間無關 **擴充** 活動。

在下列範例中，下拉式清單提供HTML轉譯函式，因為傳送中選取的選件空間具有轉譯函式：

![](assets/Interaction-best-practices-HTML-rendering.png)

此函式插入程式碼，例如： `<%@ include proposition="targetData.proposition" view="rendering/html" %>`.

當您選取主張時， **[!UICONTROL view]** 屬性如下：
* &quot;rendering/html&quot;： html rendering. 它會使用HTML演算函式。
* &quot;offer/view/html&quot;： html內容。 它不會使用HTML演算函式。 它只包含HTML欄位。

當您在單一電子郵件傳遞中包含多個選件空間時，如果部分選件具有轉譯函式，而部分選件沒有該函式，您必須記住哪些選件使用哪些選件空間，以及哪些選件空間具有轉譯函式。

因此，為避免任何問題，建議所有選件空間都定義有HTML轉譯函式，即使您的選件空間只需要HTML內容亦然。

### 在主張記錄表中設定排名 {#rank-proposition-log-table}

建議產生或接受時，優惠方案空間能夠將資料儲存在主張表格中：

![](assets/Interaction-best-practices-offer-space-storage.png)

但是，這僅適用於傳入互動。

使用傳出互動時，以及使用沒有互動模組的傳出選件時，也可以在主張表格中儲存其他資料。

工作流程暫存表格中名稱與主張表格中欄位名稱相符的任何欄位，都會複製到主張表格的相同欄位中。

例如，在中手動選取優惠方案（不進行互動）時 **擴充** 工作流程活動，標準欄位的定義如下：

![](assets/Interaction-best-practices-manual-offer-std-fields.png)

可新增其他欄位，例如 `@rank` 欄位：

![](assets/Interaction-best-practices-manual-offer-add-fields.png)

因為主張表格中有一個欄位名為 `@rank`，則會複製工作流程暫存表格中的值。

有關在主張表格中儲存其他欄位的詳細資訊，請參閱 [本節](interaction-send-offers.md#storing-offer-rankings-and-weights).

針對具有互動的傳出優惠方案，在選取數個優惠方案且您想要記錄它們在電子郵件中的顯示順序時，此功能會很實用。

您也可以直接在主張表格中儲存其他中繼資料，例如目前的支出層級，以保留產生優惠方案時支出的相關歷史記錄。

使用傳出互動時， `@rank` 欄位可以新增，如上述範例所示，但其值會根據「互動」傳回的順序自動設定。 例如，如果您使用互動來選取三個優惠方案，則 `@rank` 欄位會傳回值1、2和3。

使用互動及手動選取優惠方案時，使用者可以將兩種方法結合使用。 例如，使用者可以手動設定 `@rank` 欄位設為1，代表手動選取的選件，並使用運算式，例如 `"1 + @rank"` 互動傳回的優惠方案。 假設「互動」選取三個優惠方案，則兩種方法傳回的優惠方案排名都將是1-4：

![](assets/Interaction-best-practices-manual-offer-combined.png)

### 擴充nms：offer綱要 {#extending-nms-offer-schema}

擴充nms：offer綱要時，請務必遵循已設定的現成結構：
* 定義下內容儲存的任何新欄位 `<element name="view">`.
* 每個新欄位需要定義兩次。 一次作為一般XML欄位，另一次作為CDATA XML欄位，並在名稱后面附加「_jst」。 例如：

  ```
  <element label="Price" name="price" type="long" xml="true"/>
  <element advanced="true" label="Script price" name="price_jst" type="CDATA" xml="true"/>
  ```

* 包含要追蹤之URL的任何欄位都必須放在 `<element name="trackedUrls">` ，位於 `<element name="view" >`.
