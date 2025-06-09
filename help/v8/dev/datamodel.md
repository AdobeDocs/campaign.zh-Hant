---
title: 開始使用 Campaign 資料模型
description: 開始使用 Campaign 資料模型，並利用來自您的來源的資料，來使您的通訊和行銷輸出受益。
feature: Data Model
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
source-git-commit: be085eaf7e1e7ded5986fdb6100045daba4d88fe
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 5%

---

# 開始使用 Campaign 資料模型 {#gs-ac-datamodel}

Adobe Campaign 附有預定義的資料模型。本節提供Adobe Campaign資料模型的內建表格及其互動的相關細節。 Adobe Campaign仰賴包含連結在一起之表格的雲端資料庫。

Adobe Campaign資料模型的基本結構描述如下：

* **收件者資料表**：資料模型依賴的主要資料表，預設為收件者資料表(**nmsRecipient**)。 此表格會儲存所有行銷設定檔。 在[本節](#ootb-profiles)中進一步瞭解收件者資料表。

* **傳遞資料表**：此資料表會針對每個傳遞動作儲存一個記錄。 通常是傳遞表格(**NmsDelivery**)。 此表格中的專案代表傳遞動作或傳遞範本。 它包含執行傳遞所需的所有引數，例如目標、內容等。 每個記錄都會更新數次，以反映傳遞進度

* **記錄表**：這些表會儲存與行銷活動執行相關的所有記錄。

   * 傳遞記錄檔是跨所有通道傳送給收件者或裝置的所有訊息。 主要傳遞記錄表格(**NmsBroadLogRcp**)包含所有收件者的傳遞記錄。
   * **nmsBroadlog**&#x200B;表格是系統中最大的表格。 它會儲存每封傳送的訊息一個記錄，這些記錄會插入、更新以追蹤傳遞狀態，並在清除歷史記錄時刪除。
   * 主要追蹤記錄表(**NmsTrackingLogRcp**)儲存所有收件者的追蹤記錄。 追蹤記錄會參照收件者的回應，例如電子郵件開啟次數和點按次數。 每個回應都會對應至追蹤記錄。

  傳送記錄檔和追蹤記錄檔會在特定時段後刪除，該特定時段會在Adobe Campaign中指定並加以修改。 因此，強烈建議您定期匯出記錄檔。

* **技術資料表**：收集用於應用程式流程的技術資料，包括操作員與使用者許可權(**xtkGroup**)、使用者工作階段(**xtkSessionInfo**)、瀏覽器樹狀結構中的資料夾(**XtkFolder**)、工作流程(**xtkWorkflow**)等等。

>[!NOTE]
>
>若要存取每個資料表的說明，請瀏覽至&#x200B;**管理>組態>資料結構描述**，從清單中選取資源，然後按一下&#x200B;**檔案**&#x200B;索引標籤。

開始使用Adobe Campaign時，您需要評估預設資料模型，以檢查哪個表格最適合儲存行銷資料。

您可以將預設收件者表格與現成欄位搭配使用，例如[此區段](#ootb-profiles)中所述。 如有需要，您可以使用兩種機制來擴充它：

* [使用新欄位擴充現有資料表](extend-schema.md)。 例如，您可以新增「忠誠度」欄位至「收件者」表格。
* [建立新資料表](create-schema.md)，例如「Purchase」資料表，列出資料庫中每個設定檔進行的所有採購，並將其連結至收件者資料表。

在[本節](datamodel-best-practices.md)中探索使用Campaign資料模型的最佳實務。

## 內建設定檔表格 {#ootb-profiles}

Adobe Campaign中的內建收件者表格(nmsrecipient)是建立資料模型的良好起點。 它具有許多預先定義的欄位和表格連結，可輕鬆擴充。 當您主要鎖定收件者時，這項功能特別實用，因為適合使用以收件者為中心的簡單資料模型。

使用標準收件者表格的好處包括：

* 開箱即用且具有訂閱、種子清單等關鍵功能
* 提供具有收件者導向資料模型的行銷資料庫
* 更快速的實作
* 由支援和合作夥伴輕鬆維護

您可以擴充收件者表格，但無法減少表格中的欄位或連結數量。

在[本節](extend-schema.md)中瞭解如何擴充現有結構描述。

在[Campaign Classic v7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=zh-Hant#extending-a-table){target="_blank"}中探索內建收件者表格擴充功能的範例

您也可以使用不同的收件者表格，以更符合您的業務或功能需求。 此方法具有限制，在[此區段](custom-recipient.md)中說明。

## Campaign表格和雲端資料庫

如需深入瞭解Campaign v8中的表格管理，請注意，在[企業(FFDA)部署](../architecture/enterprise-deployment.md)的內容中，表格會在Campaign與其Snowflake雲端資料庫之間復寫。

在[本節](../architecture/replication.md)中進一步瞭解復寫策略和機制。

**相關主題**

探索如何在[本節](../start/import.md)中匯入設定檔
在[本節](../start/audiences.md)中進一步瞭解Campaign對象
