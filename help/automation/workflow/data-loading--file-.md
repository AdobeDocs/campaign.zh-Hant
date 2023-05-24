---
product: campaign
title: 資料載入 (檔案)
description: 進一步瞭解資料載入（檔案）工作流程活動
feature: Workflows, Data Management Activity
exl-id: 10351620-115c-4bd8-b216-e5ad6f205ef3
source-git-commit: 6464e1121b907f44db9c0c3add28b54486ecf834
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 14%

---

# 資料載入 (檔案){#data-loading-file}



## 使用 {#use}

此 **[!UICONTROL Data loading (File)]** 活動可讓您直接存取外部資料來源，並在Adobe Campaign中使用它。 事實上，鎖定目標作業所需的所有資料並不一定都能在Adobe Campaign資料庫中找到：這些資料可以在外部檔案中取得。

要載入的檔案可由轉變指定，或在此活動執行期間計算。 例如，它可以是客戶最喜愛的10種產品清單，這些產品的購買是在外部資料庫中進行管理的。

此活動的設定視窗的上半部可讓您定義檔案格式。 要執行此操作，請使用與要匯入的範例檔案具有相同格式的範例檔案。 此檔案可儲存在本機或伺服器上。

>[!CAUTION]
>
>僅支援「平面」結構檔案（例如CSV、TXT等）。 不建議使用XML格式。

![](assets/s_advuser_wf_etl_file.png)

您可以定義在檔案匯入期間執行的預先處理，例如不必在伺服器上解壓縮檔案（因此可節省解壓縮檔案的空間），而要在檔案處理中包括解壓縮。 選取 **[!UICONTROL Pre-process the file]** 選項，然後從3個選項中選擇一個： **[!UICONTROL None]**， **[!UICONTROL Decompression]** (zcat)或 **[!UICONTROL Decrypt]** (gpg)。

![](assets/preprocessing-dataloading.png)

## 定義檔案格式 {#defining-the-file-format}

載入檔案時，會自動偵測欄格式，並包含每個資料型別的預設引數。 您可以修改這些預設參數，以指定要套用至資料的特定程式，尤其是當有錯誤或空值時。

要執行此操作，請選取 **[!UICONTROL Click here to change the file format...]** 在的主視窗中 **[!UICONTROL Data loading (file)]** 活動。 然後會開啟格式詳細資訊視窗。

![](assets/file_loading_columns_format.png)

然後，您可以修改檔案的一般格式以及每欄的格式。

一般檔案格式設定可讓您定義識別欄的方式（檔案編碼、使用的分隔符號等）。

欄格式化可讓您定義每列的值處理：

* **[!UICONTROL Ignore column]**：不會在資料載入期間處理此欄。
* **[!UICONTROL Data type]**：指定每欄所需的資料類型。
* **[!UICONTROL Allow NULLs]**：指定如何管理空值。

   * **[!UICONTROL Adobe Campaign default]**：僅為數字欄位產生錯誤，否則插入 NULL 值。
   * **[!UICONTROL Empty value allowed]**：授權空值。因此插入值 NULL。
   * **[!UICONTROL Always populated]**：如果值為空，則產生錯誤。

* **[!UICONTROL Length]**：指定「 」的字元數上限。 **字串** 資料型別。
* **[!UICONTROL Format]**：定義時間和日期格式。
* **[!UICONTROL Data transformation]**：定義是否需要在 **字串**.

   * **[!UICONTROL None]**：未修改匯入的字串。
   * **[!UICONTROL First letter in upper case]**：字串中每個字詞的第一個字母都會以大寫開頭。
   * **[!UICONTROL Upper case]**：字串中的所有字元都會使用大寫。
   * **[!UICONTROL Lower case]**：字串中的所有字元均為小寫。

* **[!UICONTROL White space management]**：指定是否需要忽略字串中的某些空格。 此 **[!UICONTROL Ignore spaces]** value只允許忽略字串開頭和結尾的空格。
* **[!UICONTROL Error processings]**：會定義發生錯誤時的行為。

   * **[!UICONTROL Ignore the value]**：會忽略值。會在工作流程執行記錄檔中產生警告。
   * **[!UICONTROL Reject line]**：不會處理整行。
   * **[!UICONTROL Use a default value in case of error]**：以在　**[!UICONTROL Default value]**　欄位中定義的預設值取代造成錯誤的值。
   * **[!UICONTROL Reject the line when there is no remapping value]**：除非已針對錯誤值定義對應，否則不會處理整行(請參閱 **[!UICONTROL Mapping]** 下方的選項)。
   * **[!UICONTROL Use a default value in case the value is not remapped]**：以中定義的預設值取代導致錯誤的值 **[!UICONTROL Default value]** 欄位，除非已針對錯誤值定義對應(請參閱 **[!UICONTROL Mapping]** 下方的選項)。

* **[!UICONTROL Default value]**：根據選取的錯誤處理指定預設值。
* **[!UICONTROL Mapping]**：此欄位僅在欄詳細資料設定（透過按兩下或透過欄清單右側的選項存取）中可用。 這會在匯入特定值時加以轉換。 例如，您可將　&quot;three&quot;　轉換為　&quot;3&quot;。

## 範例：收集資料並將其載入資料庫 {#example--collecting-data-and-loading-it-in-the-database}

以下範例可讓您每天在伺服器上收集檔案、載入其內容，並根據其中包含的資訊更新資料庫中的資料。 要收集的檔案包含客戶的相關資訊，這些客戶可能購買過商品（3,000歐元以上）、要求退款，或是未購買任何東西就造訪商店。 根據此資訊，各種處理作業將套用至資料庫中的設定檔。

![](assets/s_advuser_load_file_sample_0.png)

1. 檔案收集器可讓您根據指定的頻率，復原儲存在目錄中的檔案。

   此 **[!UICONTROL Directory]** 索引標籤包含要復原的檔案的相關資訊。 在我們的範例中，將會復原名稱包含&#39;customers&#39;一字且儲存在伺服器的tmp/Adobe/資料/檔案目錄中的所有文字格式檔案。

   使用 **[!UICONTROL File collector]** 的詳細說明，請參見 [檔案收集器](file-collector.md) 區段。

   ![](assets/s_advuser_load_file_sample_1.png)

   此 **[!UICONTROL Schedule]** 索引標籤可讓您排程收集器的執行，即指定檢查這些檔案存在的頻率。

   在此，我們想要在每個工作日晚上9點觸發收集器。

   ![](assets/s_advuser_load_file_sample_2.png)

   若要這麼做，請按一下 **[!UICONTROL Change...]** 按鈕來設定排程，該按鈕位於編輯工具的右下角部分。

   有關詳細資訊，請參閱 [排程器](scheduler.md).

1. 然後設定資料載入（檔案）活動，以指出應如何讀取收集的檔案。 要執行此操作，請選取與要載入的檔案具有相同結構的範例檔案。

   ![](assets/s_advuser_load_file_sample_3.png)

   在此處，檔案包含五欄：

   * 第一欄包含與事件一致的程式碼：購買（大於或小於3,000歐元）、一次或多次購買不購買或退款。
   * 以下四欄包含使用者端的名字、姓氏、電子郵件和帳號。

   要載入之檔案的格式設定與Adobe Campaign中匯入資料時定義的格式設定一致。

1. 在分割活動中，指定要建立的子集，根據 **事件** 欄值。

   「分割」活動在區段中詳細說明。

   ![](assets/s_advuser_load_file_sample_4.png)

   對於每個子集，請在 **事件** 欄。

   ![](assets/s_advuser_load_file_sample_5.png)

   此 **[!UICONTROL Split]** 因此，活動將包含下列資訊：

   ![](assets/s_advuser_load_file_sample_6.png)

1. 然後指定針對每種母體型別執行的程式。 在我們的範例中，我們將 **[!UICONTROL Update the data]** 在資料庫中。 若要這麼做，請放置 **[!UICONTROL Update data]** 分割活動的每個出站轉變結尾的活動。

   此 **[!UICONTROL Update data]** 有關活動的詳情，請參閱 [更新資料](update-data.md) 區段。
