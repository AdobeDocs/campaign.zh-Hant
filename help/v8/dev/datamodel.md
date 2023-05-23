---
title: 開始使用 Campaign 資料模型
description: 開始使用 Campaign 資料模型，並利用來自您的來源的資料，來使您的通訊和行銷輸出受益。
feature: Data Model
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 6%

---

# 開始使用 Campaign 資料模型{#gs-ac-datamodel}

Adobe Campaign 附有預定義的資料模型。本節介紹了Adobe Campaign資料模型的內置表及其相互作用。 Adobe Campaign依賴於包含連結在一起的表的雲資料庫。

Adobe Campaign資料模型的基本結構可以描述如下：

* **收件人表**:資料模型依賴於主表，該主表預設為「收件人」表(nmsRecipient)。 此表儲存所有市場營銷配置檔案。

   ![](../assets/do-not-localize/glass.png) 有關「收件人」(Recipient)表格的詳細資訊，請參見 [此部分](#ootb-profiles)。

* **交貨表**:資料模型還包括專用於儲存所有營銷活動的部件。 通常是「傳遞」表(NmsDelivery)。 此表中的每個記錄都表示交貨操作或交貨模板。 它包含執行遞送所需的所有參數，如目標、內容等。

* **日誌表**:這些表儲存與市場活動執行相關的所有日誌。

   傳遞日誌是所有通道中發送給收件人或設備的所有消息。 主傳遞日誌表(NmsBroadLogRcp)包含所有收件人的傳遞日誌。
主跟蹤日誌表(NmsTrackingLogRcp)儲存所有收件人的跟蹤日誌。 跟蹤日誌是指收件人的反應，如電子郵件的開啟和點擊。 每個反應都對應於跟蹤日誌。
交貨日誌和跟蹤日誌在特定時間段後被刪除，該時間段在Adobe Campaign指定，可以修改。 因此，強烈建議定期導出日誌。

* **技術表**:收集用於應用程式流程的技術資料，包括運算子和用戶權限(xtkGroup)、資料夾(XtkFolder)。

>[!NOTE]
>
>要訪問每個表的說明，請轉到「管理」>「配置」>「資料方案」，從清單中選擇資源，然後按一下 **文檔** 頁籤。

從Adobe Campaign開始，您需要評估預設資料模型，以檢查哪個表最適合儲存您的營銷資料。

可以使用預設的「收件人」表和現成欄位，如中所述 [此部分](#ootb-profiles)。 如果需要，可以使用兩種機制擴展它：

* [擴展現有表](extend-schema.md) 的子菜單。 例如，您可以向「收件人」表添加新的「會員」欄位。
* [建立新表](create-schema.md)例如，「採購」表列出了資料庫每個配置檔案所做的所有採購，並將其連結到「收件人」表。

![](../assets/do-not-localize/glass.png) 在中使用市場活動資料模型時發現最佳做法 [此部分](datamodel-best-practices.md)。

## 內置配置檔案表 {#ootb-profiles}

Adobe Campaign的內置收件人表(nmsrecipient)為構建資料模型提供了良好的起點。 它具有許多可輕鬆擴展的預定義欄位和表連結。 當您主要針對收件人時，此功能特別有用，因為它適合以收件人為中心的簡單資料模型。

使用標準收件人表的好處有：

* 使用訂閱、種子清單等關鍵功能開箱即用
* 提供具有以收件人為中心的資料模型的市場營銷資料庫
* 加快實施
* 支援和合作夥伴可輕鬆維護

可以擴展收件人表，但不能減少表中的欄位或連結數。

![](../assets/do-not-localize/glass.png) 瞭解如何在中擴展現有架構 [此部分](extend-schema.md)。

![](../assets/do-not-localize/book.png) 查找中內置收件人表擴展示例 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html#extending-a-table){target="_blank"}

您還可以使用不同的收件人表來更好地滿足您的業務或功能要求。 此方法具有局限性，如 [此部分](custom-recipient.md)。

## 活動表和雲資料庫

為了更好地理解市場活動v8中的表管理，請注意，在 [企業(FDA)部署](../architecture/enterprise-deployment.md)，表在Campaigm和其Snowflake雲資料庫之間複製。

![](../assets/do-not-localize/glass.png) 瞭解有關中的複製策略和機制的更多資訊 [此部分](../architecture/replication.md)。

**相關主題**

![](../assets/do-not-localize/glass.png) 瞭解如何在中導入配置檔案 [此部分](../start/import.md)
![](../assets/do-not-localize/glass.png) 瞭解有關中的活動受眾的詳細資訊 [此部分](../start/audiences.md)
