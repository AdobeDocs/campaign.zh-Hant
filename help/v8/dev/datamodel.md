---
title: 開始使用 Campaign 資料模型
description: 開始使用Campaign資料模型，並運用來源的資料，讓您的通訊和行銷成果受益。
feature: Data Model
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
source-git-commit: 507f30d16eecf5400ee88a4d29913e4cdaca9cba
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 3%

---

# 開始使用 Campaign 資料模型{#gs-ac-datamodel}

Adobe Campaign 附有預定義的資料模型。本節提供Adobe Campaign資料模型的內建表格及其互動的一些詳細資料。 Adobe Campaign仰賴雲端資料庫，其中包含連結在一起的表格。

Adobe Campaign資料模型的基本結構描述如下：

* **收件者表格**:資料模型依賴主表，預設情況下主表為收件者表(nmsRecipient)。 此表格會儲存所有行銷設定檔。

   ![](../assets/do-not-localize/glass.png) 如需「收件者」表格的詳細資訊，請參閱 [本節](#ootb-profiles).

* **傳送表格**:資料模型也包含專用於儲存所有行銷活動的部分。 通常為傳送表格(NmsDelivery)。 此表中的每個記錄都表示傳遞操作或傳遞模板。 它包含執行傳送所需的所有必要參數，例如目標、內容等。

* **記錄表**:這些表格會儲存與執行促銷活動相關聯的所有記錄檔。

   傳送記錄是所有通道上傳送給收件者或裝置的所有訊息。 主要傳送記錄表(NmsBroadLogRcp)包含所有收件者的傳送記錄。
主要追蹤記錄表(NmsTrackingLogRcp)會儲存所有收件者的追蹤記錄。 追蹤記錄會參考收件者的反應，例如電子郵件開啟次數和點按次數。 每個反應都對應至追蹤記錄。
傳送記錄檔和追蹤記錄檔會在特定時段後刪除，而特定時段會在Adobe Campaign中指定，且可以修改。 因此，強烈建議定期匯出日誌。

* **技術表**:收集用於應用程式的技術資料，包括運算子和使用者權限(xtkGroup)、資料夾(XtkFolder)。

>[!NOTE]
>
>若要存取每個表格的說明，請前往「管理員>設定>資料結構」，從清單中選取資源，然後按一下 **檔案** 標籤。

從Adobe Campaign開始，您需要評估預設資料模型，以檢查哪個表格最適合儲存行銷資料。

您可以使用預設的收件者表格搭配現成可用欄位，如 [本節](#ootb-profiles). 如有需要，您可使用兩種機制來擴充：

* [擴展現有表](extend-schema.md) 新欄位。 例如，您可以將新的「忠誠度」欄位新增至「收件者」表格。
* [建立新表格](create-schema.md)，例如，「購買」表格會列出資料庫每個設定檔進行的所有購買，並將其連結至收件者表格。

![](../assets/do-not-localize/glass.png) 在中使用Campaign資料模型時，探索最佳作法 [本節](datamodel-best-practices.md).

## 內建設定檔表格 {#ootb-profiles}

Adobe Campaign中的內建收件者表格(nmsrecipient)是建立資料模型的好起點。 它有許多預先定義的欄位和表格連結，可輕鬆擴充。 當您主要鎖定收件者時，這項功能特別實用，因為它適合簡單的收件者導向資料模型。

使用標準收件者表格的好處如下：

* 具備訂閱、種子清單等主要功能且立即可用
* 以收件者為中心的資料模型提供行銷資料庫
* 更快速的實作
* 由支援和合作夥伴輕鬆維護

可以擴展收件者表，但不能減少表中的欄位或連結數。

![](../assets/do-not-localize/glass.png) 了解如何在 [本節](extend-schema.md).

![](../assets/do-not-localize/book.png) 探索中內建收件者表格擴充功能的範例，位於 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#extending-a-table){target=&quot;_blank&quot;}

您也可以使用不同的收件者表格，以更符合您的業務或功能需求。 此方法有其限制，其說明於 [本節](custom-recipient.md).

## Campaign表格和雲端資料庫

為了更好地了解Campaign v8中的表格管理，請注意，在 [企業(FFDA)部署](../architecture/enterprise-deployment.md)，表會在Campaign及其Snowflake雲端資料庫之間複製。

![](../assets/do-not-localize/glass.png) 深入了解復寫策略和機制： [本節](../architecture/replication.md).

**相關主題**

![](../assets/do-not-localize/glass.png) 探索如何在 [本節](../start/import.md)
![](../assets/do-not-localize/glass.png) 進一步了解Campaign閱聽眾，位於 [本節](../start/audiences.md)
