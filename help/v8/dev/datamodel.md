---
solution: Campaign
product: Adobe Campaign
title: 開始使用 Campaign 資料模型
description: 開始使用 Campaign 資料模型
feature: 概覽
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896,b1319b34-ee07-48ed-9ab1-e2d12d3d99f8
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 4%

---

# 開始使用 Campaign 資料模型{#gs-ac-datamodel}

Adobe Campaign 隨附預先定義的資料模型。本節詳細介紹Adobe Campaign資料模型的內置表及其交互。 Adobe Campaign依賴於包含連結在一起的表的雲資料庫。

Adobe Campaign資料模型的基本結構可以描述為：

* **收件者表格**:資料模型依賴於主表，該主表預設為「接收者」表(nmsRecipient)。此表格可儲存所有行銷設定檔。

   ：球：有關「收件人」(Recipient)表格的詳細資訊，請參閱[本節](#ootb-profiles)。

* **傳送表格**:資料模型也包含專用於儲存所有行銷活動的部分。通常是「傳送」表(NmsDelivery)。 此表中的每個記錄都代表傳送動作或傳送範本。 它包含執行傳送的所有必要參數，例如目標、內容等。

* **日誌表**:這些表格會儲存與執行促銷活動相關的所有記錄檔。

   傳送記錄檔是所有通道中傳送給收件者或裝置的所有訊息。 主「傳送日誌」表(NmsBroadLog)包含所有接收者的傳送日誌。
主「追蹤記錄檔」表(NmsTrackingLog)會儲存所有收件者的追蹤記錄檔。 追蹤記錄是指收件者的反應，例如電子郵件的開信次數和點按次數。 每個反應都對應一個追蹤記錄。
傳送記錄檔和追蹤記錄檔會在特定期間後刪除，此期間在Adobe Campaign指定並可加以修改。 因此，強烈建議您定期匯出記錄檔。

* **技術表**:收集用於應用程式的技術資料，包括操作員和用戶權限(NmsGroup)、資料夾(XtkFolder)。

>[!NOTE]
>
>要訪問每個表的說明，請轉至「管理」>「配置」>「資料結構」，從清單中選擇資源，然後按一下「**文檔**」頁籤。

從Adobe Campaign開始，您需要評估預設資料模型，以檢查哪個表格最適合儲存行銷資料。

您可以使用預設的「收件者」表格和現成可用的欄位，例如[本節](#ootb-profiles)所述。 如有需要，您可以使用兩種機制來擴充它：

* [使用新欄位](extend-schema.md) 擴充現有表格。例如，您可以在「收件者」表格中新增「忠誠度」欄位。
* [建立新表格](create-schema.md)，例如列出資料庫每個描述檔所有購買項目的「購買」表格，並將其連結至「收件者」表格。

：球：在[本節](datamodel-best-practices.md)中使用促銷活動資料模型時，探索最佳實務。

## 內置配置檔案表{#ootb-profiles}

Adobe Campaign的內建收件者表(nmsrecipient)為您建立資料模型提供了良好的起點。 它有許多預先定義的欄位和表格連結，可輕鬆擴充。 當您主要針對收件者時，這特別有用，因為它適合簡單的收件者導向資料模型。

使用標準收件人表格的優點包括：

* 具備訂閱、種子清單等主要功能的現成可用功能
* 提供以收件者為中心的資料模型的行銷資料庫
* 更快速的實作
* 由支援和合作夥伴輕鬆維護

可以擴展收件者表，但不能減少表中的欄位或連結數。

：球：瞭解如何在[本節](extend-schema.md)中擴展現有模式。

:arrow_upper_right:在[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#extending-a-table)中探索內建收件者表格副檔名範例

您也可以使用不同的收件者表格，以更符合您的業務或功能需求。 此方法具有限制，並在[本節](custom-recipient.md)中說明。

## 促銷活動表格和雲端資料庫

為了更好地瞭解Campaign v8中的表格管理，請注意，表格會在Campaign與其Snowflake雲端資料庫之間複製。

：球：在[本節](../config/replication.md)中進一步瞭解複製策略和機制。

**相關主題**

：球：瞭解如何在[本節](../start/import.md)中匯入描述檔
：球：在[本節](../start/audiences.md)中進一步瞭解促銷活動觀眾
