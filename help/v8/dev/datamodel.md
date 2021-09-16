---
title: 開始使用 Campaign 資料模型
description: 開始使用 Campaign 資料模型
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 4%

---

# 開始使用 Campaign 資料模型{#gs-ac-datamodel}

Adobe Campaign 附有預定義的資料模型。本節提供Adobe Campaign資料模型的內建表格及其互動的一些詳細資料。 Adobe Campaign仰賴雲端資料庫，其中包含連結在一起的表格。

Adobe Campaign資料模型的基本結構描述如下：

* **收件者表格**:資料模型依賴主表，預設情況下主表為收件者表(nmsRecipient)。此表格可讓儲存所有行銷設定檔。

   ??如需「收件者」表格的詳細資訊，請參閱[此區段](#ootb-profiles)。

* **傳送表格**:資料模型也包含專用於儲存所有行銷活動的部分。通常為傳送表格(NmsDelivery)。 此表中的每個記錄都表示傳遞操作或傳遞模板。 它包含執行傳送所需的所有必要參數，例如目標、內容等。

* **記錄表**:這些表格會儲存與執行促銷活動相關聯的所有記錄檔。

   傳送記錄是所有通道上傳送給收件者或裝置的所有訊息。 主要傳送記錄表(NmsBroadLogRcp)包含所有收件者的傳送記錄。
主要追蹤記錄表(NmsTrackingLogRcp)會儲存所有收件者的追蹤記錄。 追蹤記錄會參考收件者的反應，例如電子郵件開啟次數和點按次數。 每個反應都對應至追蹤記錄。
傳送記錄檔和追蹤記錄檔會在特定時段後刪除，而特定時段會在Adobe Campaign中指定，且可以修改。 因此，強烈建議定期匯出日誌。

* **技術表**:收集用於應用程式的技術資料，包括運算子和使用者權限(xtkGroup)、資料夾(XtkFolder)。

>[!NOTE]
>
>若要存取每個表格的說明，請前往「管理員>設定>資料結構」，從清單中選取資源，然後按一下「**檔案**」標籤。

從Adobe Campaign開始，您需要評估預設資料模型，以檢查哪個表格最適合儲存行銷資料。

您可以使用預設的收件者表格搭配現成欄位，例如[此區段](#ootb-profiles)中所述。 如有需要，您可使用兩種機制來擴充：

* [使用新欄位](extend-schema.md) 擴展現有表。例如，您可以將新的「忠誠度」欄位新增至「收件者」表格。
* [建立新表格](create-schema.md)，例如「購買」表格，列出資料庫每個設定檔進行的所有購買，並將其連結至收件者表格。

??探索在[此區段](datamodel-best-practices.md)中使用Campaign資料模型時的最佳作法。

## 內建設定檔表格 {#ootb-profiles}

Adobe Campaign中的內建收件者表格(nmsrecipient)是建立資料模型的好起點。 它有許多預先定義的欄位和表格連結，可輕鬆擴充。 當您主要鎖定收件者時，這項功能特別實用，因為它適合簡單的收件者導向資料模型。

使用標準收件者表格的好處如下：

* 具備訂閱、種子清單等主要功能且立即可用
* 以收件者為中心的資料模型提供行銷資料庫
* 更快速的實作
* 由支援和合作夥伴輕鬆維護

可以擴展收件者表，但不能減少表中的欄位或連結數。

??了解如何在[此小節](extend-schema.md)中擴展現有架構。

↗️在[Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#extending-a-table)中探索內建收件者表格副檔名的範例

您也可以使用不同的收件者表格，以更符合您的業務或功能需求。 此方法有其限制，如[本節](custom-recipient.md)所述。

## Campaign表格和雲端資料庫

為了更好地了解Campaign v8中的表格管理，請注意，表格會在Campaign與其Snowflake雲端資料庫之間複製。

??在[本小節](../config/replication.md)中了解有關複製策略和機制的詳細資訊。

**相關主題**

??探索如何在[此區段](../start/import.md)中匯入設定檔
??在[此小節](../start/audiences.md)中深入了解Campaign對象
