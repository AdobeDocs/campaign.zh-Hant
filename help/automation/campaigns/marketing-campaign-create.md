---
product: campaign
title: 建立市場營銷活動
description: 瞭解如何建立和執行市場營銷活動
feature: Campaigns, Cross Channel Orchestration, Programs
source-git-commit: 72467caf94e652ede70c00f1ea413012fc4c7e1f
workflow-type: tm+mt
source-wordcount: '1297'
ht-degree: 3%

---

# 建立計畫和市場活動{#create-programs-and-campaigns}

市場活動業務流程元件位於 **[!UICONTROL Campaigns]** 頁籤：在這裡，您可以看到市場營銷計畫和市場活動及其關聯要素的概覽。

營銷計畫由市場活動組成，市場活動由交付、資源等組成。 有關交貨、預算、審閱人和連結文檔的所有資訊均在市場活動中分組。

![](assets/campaigns-create-from-home.png)

![](assets/do-not-localize/how-to-video.png) [在視頻中發現計畫和活動](#video)

## 與方案和計畫合作{#work-with-plan-and-program}

### 建立計畫和方案層次結構 {#create-plan-and-program}

每個市場活動都屬於屬於計畫的計畫。 所有計畫、方案和活動均可通過 **[!UICONTROL Campaign calendar]** 的 **市場活動** 頁籤。

在開始構建市場活動和交貨之前，請為市場營銷計畫和計畫配置資料夾層次結構。

1. 按一下 **瀏覽器** 表徵圖
1. 按一下右鍵要在其中建立計畫的資料夾。
1. 選擇 **添加新資料夾>Campaign Management>計畫**。

   ![](assets/create-new-plan-folder.png)

1. 更名計畫。
1. 按一下右鍵新建立的計畫並選擇 **屬性……**。
1. 在 **常規** 頁籤 **內部名稱** 在包導出過程中避免重複。

   ![](assets/plan-properties.png)

1. 按一下 **保存**。
1. 按一下右鍵新建立的計畫並選擇 **新建「Program」資料夾**。

   ![](assets/program-folder.png)

1. 重複上述步驟以更名新程式資料夾及其內部名稱。


### 配置程式 {#edit-a-program}

編輯程式時，使用下面介紹的頁籤瀏覽和配置程式。

* 的 **計畫** 頁籤根據您在日曆標題中按一下的頁籤顯示月、周或日的程式日曆。 您可以從此頁建立市場活動、程式或任務。 [了解更多](#campaign-calendar)

* 的 **編輯** 頁籤，您可以個性化程式：名稱、起始日期和終止日期、預算、連結文檔等。

   ![](assets/new-program-edit-tab.png)

## 使用市場活動{#work-with-campaigns}

### 建立促銷活動 {#create-a-campaign}

您可以通過市場活動清單建立市場活動。 要顯示此視圖，請選擇 **[!UICONTROL Campaigns]** 的 **[!UICONTROL Campaigns]** 控制板，然後按一下 **[!UICONTROL Create]**。

的 **[!UICONTROL Program]** 欄位中，您可以選擇市場活動將附加到的方案。 此資訊是強制性的。

![](assets/new-campaign-settings.png)

也可以通過市場活動日曆或方案日曆建立市場活動。 [了解更多](#campaign-calendar)

在市場活動建立窗口中，選擇市場活動模板並添加市場活動的名稱和說明。 您還可以指定市場活動起始日期和終止日期。

按一下 **[!UICONTROL OK]** 建立市場活動。 它被添加到計畫日程和市場活動清單中。

然後，您可以編輯剛剛建立的市場活動並定義其參數。 要開啟和配置此市場活動，ypu可以：

1. 瀏覽市場活動日曆並選擇要顯示的市場活動，然後按一下 **[!UICONTROL Open]** 的子菜單。
1. 瀏覽 **[!UICONTROL Schedule]** 頁籤，選擇市場活動並開啟它。
1. 瀏覽市場活動清單，然後按一下要編輯的市場活動名稱。

所有這些操作都會將您帶到市場活動控制面板。

![](assets/campaigns-dashboard-approve.png)

訪問以下部分，瞭解如何配置市場活動：

* [新增傳遞](marketing-campaign-deliveries.md)
* [管理資產和文檔](marketing-campaign-assets.md)
* [構建目標受眾](marketing-campaign-target.md)
* [設定核准流程](marketing-campaign-approval.md)
* [管理庫存和預算](providers--stocks-and-budgets.md)


### 編輯市場活動設定 {#campaign-settings}

市場活動通過市場活動模板建立。 您可以配置可重用模板，其中已為其選擇了某些選項，並且已保存了其他設定。

對於每個市場活動，都提供以下功能：

* 參考文檔和資源：您可以將文檔與市場活動（簡報、報表、影像等）關聯。 支援所有文檔格式。 [了解更多資訊](marketing-campaign-deliveries.md#manage-associated-documents)。
* 定義成本：對於每個市場活動，Adobe Campaign允許您定義成本分錄和成本計算結構，在建立市場營銷市場活動時可以使用這些結構。 例如：印刷成本、使用外部代理、租房等。 [了解更多資訊](providers--stocks-and-budgets.md#defining-cost-categories)。
* 定義目標：您可以為市場活動定義可量化的目標，例如訂戶數、業務量等。 此資訊稍後將用於市場活動報告。
* 管理種子地址和控制組。 [了解更多](marketing-campaign-deliveries.md#defining-a-control-group)).
* 管理批准：您可以選擇要批准的處理，並根據需要選擇審閱運算子或運算子組。 [了解更多資訊](marketing-campaign-approval.md#checking-and-approving-deliveries)。

>[!NOTE]
>
>要訪問和更新市場活動設定，請瀏覽至 **[!UICONTROL Advanced campaign parameters...]** 連結 **[!UICONTROL Edit]** 頁籤。

### 監視市場活動 {#monitor-a-campaign}

對於每個市場活動，任務、資源和交貨都集中在控制面板中。 此介面允許您管理和協調營銷活動。

通過Adobe Campaign，您可以設定協作流程，以建立和批准您的市場活動的各個步驟：預算、目標、內容等的核准 此業務流程在 [此部分](marketing-campaign-approval.md)。

![](assets/campaigns-dashboard-approval-tab.png)

>[!NOTE]
>
>市場活動中可用的元件取決於其模板。 市場活動模板配置在 [此部分](marketing-campaign-templates.md#campaign-templates)。

活動完成後，使用 **[!UICONTROL Reports]** 連結以訪問市場活動報表。

![](assets/campaigns-reports-dashboard.png)

## 市場活動日曆 {#campaign-calendar}

市場活動日曆顯示所有方案、計畫、市場活動和交貨。

要編輯計畫、方案、市場活動或交付，請瀏覽到日曆中的名稱，然後使用 **[!UICONTROL Open]** 的子菜單。 然後，它將顯示在新頁籤中，如下所示：

![](assets/campaign-calendar.png)

您可以過濾市場活動日曆中顯示的資訊。 要執行此操作，請按一下 **[!UICONTROL Filter]** 連結並選擇篩選條件。

![](assets/campaign_planning_filter.png)

>[!NOTE]
>
>在日期篩選時，所有起始日期遲於指定日期和/或終止日期早於指定日期的市場活動都會顯示。 使用每個欄位右側的日曆選擇日期。

您還可以使用 **[!UICONTROL Search]** 欄位以篩選顯示的項。

連結到每個項目的表徵圖允許您查看其狀態：已完成、正在進行、正在編輯等。

要篩選要顯示的市場活動，請按一下 **[!UICONTROL Filter]** 連結並選擇要顯示的市場活動狀態。

![](assets/calendar-filter-options.png)

在瀏覽日曆時，您還可以建立程式或市場活動。

![](assets/campaign-create-from-calendar.png)

當通過 **[!UICONTROL Schedule]** 頁籤，市場活動將自動連結到相關的計畫。 的 **[!UICONTROL Program]** 的下界。


## 使用Web介面 {#use-the-web-interface-}

您可以通過Internet瀏覽器訪問Adobe Campaign控制台螢幕，以查看所有市場活動和交付以及資料庫中配置檔案的報告和資訊。 此訪問不啟用記錄建立。 根據操作員權限，您可以查看和/或對資料庫中的資料執行操作。 例如，您可以批准市場活動內容和目標、重新啟動或停止交付等。

1. 如常登錄：https://`<your instance>:<port>/view/home`。
1. 使用菜單訪問概覽。

   ![](assets/web-access-campaigns.png)

除了在市場活動中導航和查看它們外，您還可以執行以下類型的任務：

* 監視實例上的活動
* 參與驗證流程，例如批准或拒絕交付內容
* 執行其他快速操作，例如暫停工作流
* 訪問所有報告功能
* 參加論壇討論

此表匯總了您可以從瀏覽器對市場活動執行的操作：

| 頁面  | 動作 |
| --- | --- |
| 市場活動、交貨、優惠等清單 | 刪除清單項 |
| Campaign | 取消市場活動 |
| 傳遞 | 批准交付內容和目標<br/>提交交貨內容<br/>確認交貨<br/>暫停和停止交貨 |
| Web應用程式 | 建立Web應用程式<br/>編輯應用程式內容和屬性<br/>將應用程式內容另存為模板<br/>發佈應用程式 |
| 優惠 | 批准聘用內容和資格<br/>禁用線上服務 |
| 任務 | 完成任務<br/>取消任務 |
| 營銷資源 | 審核資源<br/>鎖定和解鎖資源 |
| 市場活動包 | 提交包以供審批<br/>批准或拒絕包<br/>取消包 |
| 市場活動訂單 | 建立訂單<br/>接受或拒絕訂單 |
| 存貨 | 刪除庫存行 |
| 提供模擬 | 啟動和停止模擬 |
| 目標工作流 | 啟動、暫停和停止工作流 |
| 報告 | 在報告歷史記錄中保存當前資料 |
| 論壇 | 添加討論<br/>回復討論中的郵件<br/>關注討論並取消訂閱 |

### 管理核准

目標或傳遞內容的批准可以通過web訪問進行。

![](assets/web-access-approval.png)

您還可以使用通知消息中包含的連結。 如需詳細資訊，請參閱[本章節](marketing-campaign-approval.md#checking-and-approving-deliveries)。


## 教程視頻 {#video}

此視頻顯示如何建立營銷計畫、計畫和市場活動。

>[!VIDEO](https://video.tv.adobe.com/v/333810?quality=12)

