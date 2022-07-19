---
product: campaign
title: 營銷活動目標受眾
description: 瞭解如何定義市場營銷活動的受眾
feature: Campaigns, Audiences
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '1458'
ht-degree: 1%

---

# 選取行銷活動的對象 {#marketing-campaign-deliveries}

在市場營銷市場活動中，對於每個交貨，您可以定義：

* 目標受眾。 您可以將消息發送到 [收件人清單](#send-to-a-group) 或建造 [工作流中的受眾](#build-the-main-target-in-a-workflow)
* 控制組。 你可以 [添加控制組](#add-a-control-group) 監視郵件傳遞後收件人的行為
<!--
* Seed addresses - Learn more in [this section](../../delivery/using/about-seed-addresses.md).-->

某些資訊可以從 [活動模板](marketing-campaign-templates.md#campaign-templates)。

<!--
To build the delivery target, you can define filtering criteria for the recipients in the database. This recipient selection mode is presented in [this section](../../delivery/using/steps-defining-the-target-population.md).
-->

## 發送到組{#send-to-a-group}

您可以將人口導入清單，然後在交貨中瞄準此清單。 要執行此操作，請遵循下列步驟：

1. 編輯交貨並按一下 **[!UICONTROL To]** 連結以更改目標人口。
1. 在 **[!UICONTROL Main target]** 頁籤 **[!UICONTROL Defined via the database]** 選項 **[!UICONTROL Add]** 來修改選定線條的屬性。

   ![](assets/select-main-target.png)

1. 選擇 **[!UICONTROL A list of recipients]**。

   ![](assets/target-a-list.png)


1. 按一下 **[!UICONTROL Next]** 的子菜單。

   ![](assets/select-the-list.png)

   可以通過添加新的篩選條件來細化目標。

1. 按一下 **[!UICONTROL Finish]** 定義所有條件後，保存主目標。

## 在市場活動工作流中構建受眾 {#build-the-main-target-in-a-workflow}

也可以在市場活動工作流中定義交貨的主要目標：此圖形環境允許您使用查詢、test和運算子構建目標：聯合、重複資料消除、共用等。

>[!IMPORTANT]
>
>在市場活動中添加的工作流不能超過28個。 超過此限制後，介面中將看不到其他工作流，並可能生成錯誤。

### 建立工作流 {#create-a-targeting-workflow}

目標可以通過工作流中圖形序列中的過濾條件的組合來建立。 您可以建立人口和子人口，這些人口和子人口將根據您的要求成為目標。 要顯示工作流編輯器，請按一下 **[!UICONTROL Targeting and workflows]** 頁籤

![](assets/targeting-and-wf-tab.png)

通過置於工作流中的一個或多個查詢從Adobe Campaign資料庫提取目標群體。 瞭解如何在中生成查詢 [此部分](../workflow/query.md)。

您可以通過Union、Intersection、Sharing、Exclusion等框啟動查詢和共用群。

從工作區左側的清單中選擇對象並連結它們以構建目標。

![](assets/campaign-wf.png)

在圖中，將圖中目標構建所需的目標查詢和計畫查詢連結起來。 您可以在進行建設時執行目標，以檢查從資料庫提取的人口。

>[!NOTE]
>
>有關定義查詢的示例和過程的詳細說明，請參見 [此部分](../workflow/query.md)。

編輯器的左側部分包含表示活動的圖形對象庫。 第一個頁籤包含目標活動，第二個頁籤包含流控制活動，這些活動偶爾用於協調目標活動。

目標工作流執行和格式設定功能可通過圖編輯器工具欄訪問。

![](assets/wf-diagram.png)

>[!NOTE]
>
>有關構建圖以及所有顯示和佈局功能的活動的詳細資訊，請參見 [此部分](../workflow/about-workflows.md)。

您可以為單個市場活動建立多個目標工作流。 要添加工作流，請執行以下操作：

1. 轉到工作流建立區域的左上部分，按一下右鍵，然後選擇 **[!UICONTROL Add]**。 您還可以使用 **[!UICONTROL New]** 按鈕。

   ![](assets/add-a-wf.png)

1. 選擇 **[!UICONTROL New workflow]** 模板並命名此工作流。
1. 按一下 **[!UICONTROL OK]** 確認工作流的建立，然後建立此工作流的圖。

### 執行工作流 {#execute-a-workflow}

目標工作流可通過 **[!UICONTROL Start]** 的子菜單。

可根據調度（調度器）或事件（外部信號、檔案導入等）對目標進行寫程式以自動執行。

與執行目標工作流（啟動、停止、暫停等）相關的操作 是 **非同步** 進程：該命令已保存，一旦伺服器可用以應用該命令，該命令即會生效。

工具欄表徵圖允許您對目標工作流的執行採取操作。

* 啟動或重新啟動

   * 的 **[!UICONTROL Start]** 表徵圖，您可以啟動目標工作流。 按一下此表徵圖時，將激活所有沒有輸入轉換的活動（端點跳轉除外）。

      ![](assets/start.png)

      伺服器將請求考慮在內，如其狀態所示： **[!UICONTROL Start as soon as possible]**。

   * 您可以通過相應的工具欄表徵圖重新啟動目標工作流。 如果 **[!UICONTROL Start]** 表徵圖不可用，例如，當正在停止目標工作流時。 在這種情況下，按一下 **[!UICONTROL Restart]** 表徵圖以預測重新啟動。 伺服器考慮請求，其狀態顯示： **[!UICONTROL Restart requested]**。

* 停止或暫停

   * 工具欄表徵圖允許您停止或暫停正在進行的目標工作流。

      按一下 **[!UICONTROL Pause]**，操作正在進行 **[!UICONTROL are not]** 已暫停，但在下次重新啟動之前不會啟動其他活動。

      ![](assets/pause.png)

      伺服器會考慮該命令，因為其狀態顯示： **[!UICONTROL Pause requested]**。

      您還可以在目標工作流執行到特定活動時自動暫停。 為此，按一下右鍵要暫停目標工作流的活動，然後選擇 **[!UICONTROL Enable but do not execute]**。

      ![](assets/donotexecute.png)

      此配置由特殊表徵圖顯示。

      ![](assets/pause_activity.png)

      >[!NOTE]
      >
      >此選項在高級目標市場活動設計和test階段非常有用。

      按一下 **[!UICONTROL Start]** 恢復執行。

   * 按一下 **[!UICONTROL Stop]** 表徵圖以停止正在執行的操作。

      ![](assets/stop.png)

      伺服器會考慮該命令，因為其狀態顯示： **[!UICONTROL Stop requested]**。
   您還可以在執行到達活動時自動停止目標工作流。 為此，按一下右鍵要停止目標工作流的活動，然後選擇 **[!UICONTROL Do not activate]**。

   ![](assets/donotactivate.png)

   此配置由特殊表徵圖顯示。

   ![](assets/unactivation.png)


   >[!NOTE]
   >
   >此選項在高級目標市場活動設計和test階段非常有用。

* 無條件停止

   在瀏覽器中，選擇 **[!UICONTROL Administration > Production > Object created automatically > Campaign workflows]** 訪問並處理每個市場活動工作流。

   通過按一下 **[!UICONTROL Actions]** 表徵圖和選擇 **[!UICONTROL Unconditional]** 停。 此操作將終止您的市場活動工作流。

   ![](assets/stop_unconditional.png)

## 添加控制組 {#add-a-control-group}

控制組是不能接收交貨的群體；它用於通過與收到交貨的目標群體的行為進行比較來跟蹤交貨後行為和促銷活動影響。

控制組可以從主目標中提取和/或來自特定組或查詢。

### 激活市場活動的控制組 {#activate-the-control-group-for-a-campaign}

您可以在市場活動層定義控制組，在這種情況下，控制組將應用於有關市場活動的每個交貨。

1. 編輯相關市場活動，然後按一下 **[!UICONTROL Edit]** 頁籤。
1. 按一下&#x200B;**[!UICONTROL Advanced campaign parameters...]**。

   ![](assets/enable-control-group.png)

1. 選擇 **[!UICONTROL Enable and edit control group configuration]** 的雙曲餘切值。
1. 按一下 **[!UICONTROL Edit...]** 以配置控制組。

   ![](assets/edit-control-group.png)

完整過程的詳細資訊 [此部分](#extract-the-control-group-from-the-main-target)。 瞭解有關中的控制組的詳細資訊 [此部分](#add-a-population)。

### 為交貨激活控制組 {#activate-the-control-group-for-a-delivery}

您可以在交貨層定義控制組，在這種情況下，控制組將應用於有關市場活動的每個交貨。

預設情況下，在市場活動層定義的控制組配置適用於該市場活動的每個交貨。 但是，您可以為單個交貨調整控制組。

>[!NOTE]
>
>如果您為市場活動定義了控制組，並且還為連結到此市場活動的交貨配置了控制組，則只應用為交貨定義的控制組。

1. 編輯有關的交貨，然後按一下 **[!UICONTROL To]** 的子菜單。
1. 按一下 **[!UICONTROL Control group]** 頁籤 **[!UICONTROL Enable and edit control group configuration]**。

   ![](assets/enable-control-group-for-a-delivery.png)

1. 按一下 **[!UICONTROL Edit...]** 以配置控制組。

完整過程的詳細資訊 [此部分](#extract-the-control-group-from-the-main-target)。

### 將新人口用作控制組 {#add-a-population}

您可以為控制組使用特定的填充。 在這種情況下，在相關欄位中選擇要用作控制組的清單。

此填充可以來自收件人清單，也可以通過特定查詢定義。

![](assets/new-population-as-control-group.png)

>[!NOTE]
>
>Adobe Campaign查詢編輯器在 [此部分](../workflow/query.md)。

### 從主目標中提取控制組 {#extract-the-control-group-from-the-main-target}

您也可以從傳遞的主要目標中提取收件人。 在這種情況下，收件人將從受此配置影響的傳遞操作的目標接收。 此提取可以是隨機的，也可以是對接收者進行排序的結果。

![](assets/extract-control-group-from-target.png)

要提取控制組，請啟用市場活動或交貨的控制組，然後選擇以下選項之一： **[!UICONTROL Activate random sampling]** 或 **[!UICONTROL Keep only the first records after sorting]**。

* 使用 **[!UICONTROL Activate random sampling]** 選項，以對主人口中的收件人應用隨機抽樣。 如果隨後將閾值設定為100，則控制組將由從目標群體中隨機選擇的100個收件人組成。 隨機採樣取決於資料庫引擎。
* 使用 **[!UICONTROL Keep only the first records after sorting]** 按鈕，將選定控制項在Tab鍵次序上移動。 如果選擇 **[!UICONTROL Age]** 欄位作為分類標準，然後定義100作為閾值，控制組由100個最年輕的接收者組成。 例如，定義一個控制組可能非常有意思，該控制組包括很少購買的收件人或頻繁購買的收件人，並將他們的行為與聯繫的收件人的行為進行比較。

按一下 **[!UICONTROL Next]** 定義排序順序（如有必要）並選擇收件人限制模式。

![](assets/limit-control-group.png)

此配置等效於 **[!UICONTROL Split]** 的子集。 控制組是這些子集之一。


#### 教程視頻 {#create-email-video}

這段視頻說明了如何在Adobe Campaign建立活動和電子郵件。

>[!VIDEO](https://video.tv.adobe.com/v/25604?quality=12)

還提供了其他市場活動操作視頻 [這裡](https://experienceleague.adobe.com/docs/campaign-classic-learn/tutorials/overview.html?lang=zh-Hant)。
