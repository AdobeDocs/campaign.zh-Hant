---
product: campaign
title: 建立行銷活動
description: 了解如何建立和執行行銷活動
feature: Campaigns, Cross Channel Orchestration, Programs
exl-id: 90dd2dad-1380-490e-b958-4a28a7d930ed
source-git-commit: 38c300555b847c9d1fd210d2fe60e4ffa1e314d2
workflow-type: tm+mt
source-wordcount: '1297'
ht-degree: 4%

---

# 建立方案和行銷活動{#create-programs-and-campaigns}

可在 **[!UICONTROL Campaigns]** 標籤：您可以在此處查看行銷方案和行銷活動及其相關元素的概述。

行銷方案由行銷活動組成，行銷活動由傳遞、資源等組成。 有關傳遞、預算、審閱者和連結文檔的所有資訊都在活動中分組。

![](assets/campaigns-create-from-home.png)

![](assets/do-not-localize/how-to-video.png) [探索影片中的方案和行銷活動](#video)

## 使用方案和計畫{#work-with-plan-and-program}

### 建立計畫和方案層次結構 {#create-plan-and-program}

每個促銷活動都屬於屬於某個計畫的方案。 所有計畫、方案和行銷活動皆可透過 **[!UICONTROL Campaign calendar]** 功能表 **行銷活動** 標籤。

開始建立行銷活動和傳送之前，請先為行銷計畫和方案設定資料夾階層。

1. 按一下 **瀏覽器** 表徵圖。
1. 以滑鼠右鍵按一下您要建立計畫的資料夾。
1. 選擇 **新增資料夾> Campaign Management >計畫**.

   ![](assets/create-new-plan-folder.png)

1. 更名計畫。
1. 按一下右鍵新建立的計畫並選擇 **屬性……**.
1. 在 **一般** 頁簽，修改 **內部名稱** 以在套件匯出期間避免重複。

   ![](assets/plan-properties.png)

1. 按一下 **儲存**.
1. 按一下右鍵新建立的計畫並選擇 **建立新的「程式」資料夾**.

   ![](assets/program-folder.png)

1. 重複上述步驟，更名新程式資料夾及其內部名稱。


### 設定方案 {#edit-a-program}

編輯程式時，請使用下面描述的頁簽來瀏覽和配置它。

* 此 **排程** 頁簽顯示月、周或日的方案日曆，具體取決於您在日曆頁首中按一下的頁簽。 您可以從此頁面建立促銷活動、方案或任務。 [了解更多](#campaign-calendar)

* 此 **編輯** 標籤可讓您個人化方案：名稱、開始和結束日期、預算、連結的檔案等。

   ![](assets/new-program-edit-tab.png)

## 使用行銷活動{#work-with-campaigns}

### 建立促銷活動 {#create-a-campaign}

您可以透過促銷活動清單建立促銷活動。 若要顯示此檢視，請選取 **[!UICONTROL Campaigns]** 功能表 **[!UICONTROL Campaigns]** 控制面板，然後按一下 **[!UICONTROL Create]**.

此 **[!UICONTROL Program]** 欄位可讓您選取要附加促銷活動的方案。 此資訊是強制性的。

![](assets/new-campaign-settings.png)

您也可以從行銷活動或方案行事歷建立行銷活動。 [了解更多](#campaign-calendar)

在促銷活動建立視窗中，選取促銷活動範本並新增促銷活動的名稱和說明。 您也可以指定促銷活動的開始和結束日期。

按一下 **[!UICONTROL OK]** 來建立促銷活動。 它會新增至方案排程和促銷活動清單中。

然後，您可以編輯您剛建立的促銷活動並定義其參數。 若要開啟和設定此促銷活動，ypu可以：

1. 瀏覽促銷活動日曆，並選取您要顯示的促銷活動，然後按一下 **[!UICONTROL Open]** 連結。
1. 瀏覽 **[!UICONTROL Schedule]** 方案的索引標籤，選取促銷活動並開啟它。
1. 瀏覽促銷活動清單，然後按一下要編輯的促銷活動名稱。

所有這些動作都會帶您進入促銷活動控制面板。

![](assets/campaigns-dashboard-approve.png)

存取下列章節，了解如何設定您的行銷活動：

* [新增傳遞](marketing-campaign-deliveries.md)
* [管理資產和檔案](marketing-campaign-assets.md)
* [建立目標對象](marketing-campaign-target.md)
* [設定核准流程](marketing-campaign-approval.md)
* [管理庫存和預算](providers--stocks-and-budgets.md)


### 編輯促銷活動設定 {#campaign-settings}

行銷活動是透過行銷活動範本建立。 您可以配置可重複使用的模板，其中已為其選擇了某些選項，並且已保存了其他設定。

對於每個促銷活動，可使用下列功能：

* 參考檔案和資源：您可以將檔案與促銷活動（簡報、報表、影像等）建立關聯。 支援所有文檔格式。 [了解更多資訊](marketing-campaign-deliveries.md#manage-associated-documents)。
* 定義成本：對於每個促銷活動，Adobe Campaign可讓您定義建立行銷活動時可使用的成本項目和成本計算結構。 例如：印刷成本、使用外部代理、房間租賃等。 [了解更多資訊](providers--stocks-and-budgets.md#defining-cost-categories)。
* 定義目標：您可以為促銷活動定義可量化的目標，例如訂閱者數量、業務量等。 此資訊稍後會用於行銷活動報表。
* 管理種子地址和控制組。 [了解更多資訊](marketing-campaign-deliveries.md#defining-a-control-group)。
* 管理批准：您可以選取要核准的處理，並視需要選取檢閱運算子或運算子群組。 [了解更多資訊](marketing-campaign-approval.md#checking-and-approving-deliveries)。

>[!NOTE]
>
>若要存取和更新促銷活動設定，請瀏覽至 **[!UICONTROL Advanced campaign parameters...]** 連結 **[!UICONTROL Edit]** 標籤。

### 監視促銷活動 {#monitor-a-campaign}

對於每個促銷活動，工作、資源和傳送會集中在控制面板中。 此介面可讓您管理和協調行銷動作。

透過Adobe Campaign，您可以設定協作流程，以建立和核准行銷活動的各個步驟：預算、目標、內容等的核准。 此協調在 [本節](marketing-campaign-approval.md).

![](assets/campaigns-dashboard-approval-tab.png)

>[!NOTE]
>
>促銷活動中可用的元件取決於其範本。 行銷活動範本設定顯示在 [本節](marketing-campaign-templates.md#campaign-templates).

促銷活動完成後，請使用 **[!UICONTROL Reports]** 連結以存取促銷活動報表。

![](assets/campaigns-reports-dashboard.png)

## 行銷活動日曆 {#campaign-calendar}

行銷活動行事歷會顯示所有方案、計畫、行銷活動和傳送。

若要編輯計畫、方案、促銷活動或傳送，請在日曆中瀏覽至其名稱，然後使用 **[!UICONTROL Open]** 連結。 接著會顯示在新標籤中，如下所示：

![](assets/campaign-calendar.png)

您可以篩選行銷活動日曆中顯示的資訊。 若要這麼做，請按一下 **[!UICONTROL Filter]** 連結，然後選取篩選條件。

![](assets/campaign_planning_filter.png)

>[!NOTE]
>
>當您依日期篩選時，會顯示所有開始日期晚於指定日期和/或結束日期早於指定日期的促銷活動。 使用每個欄位右側的日曆來選取日期。

您也可以使用 **[!UICONTROL Search]** 欄位來篩選顯示的項目。

連結至每個項目的圖示可讓您檢視其狀態：已完成、進行中、正在編輯等。

若要篩選要顯示的促銷活動，請按一下 **[!UICONTROL Filter]** 連結，並選取要顯示的促銷活動狀態。

![](assets/calendar-filter-options.png)

瀏覽日曆時，您也可以建立方案或促銷活動。

![](assets/campaign-create-from-calendar.png)

當您透過 **[!UICONTROL Schedule]** 頁簽，則促銷活動會自動連結至相關方案。 此 **[!UICONTROL Program]** 欄位在此情況下會隱藏。


## 使用Web介面 {#use-the-web-interface-}

您可以透過網際網路瀏覽器存取Adobe Campaign主控台畫面，以檢視所有促銷活動和傳送，以及資料庫中設定檔的報表和資訊。 此訪問不啟用記錄建立。 根據操作員權限，您可以查看和/或對資料庫中的資料執行操作。 例如，您可以核准促銷活動內容及鎖定目標、重新啟動或停止傳送等。

1. 照常透過https://登入`<your instance>:<port>/view/home`.
1. 使用功能表存取概述。

   ![](assets/web-access-campaigns.png)

除了瀏覽各個促銷活動並檢視它們，您還可以執行下列類型的工作：

* 監視執行個體上的活動
* 參與驗證程式，例如核准或拒絕傳送內容
* 執行其他快速動作，例如暫停工作流程
* 存取所有報表功能
* 參加論壇討論

此表格會摘要您可從瀏覽器對促銷活動採取的動作：

| 頁面  | 動作 |
| --- | --- |
| 促銷活動、傳送、選件等的清單。 | 刪除清單項目 |
| Campaign | 取消促銷活動 |
| 傳遞 | 核准傳遞內容和目標<br/>提交傳遞內容<br/>確認傳送<br/>暫停並停止傳送 |
| 網頁應用程式 | 建立Web應用程式<br/>編輯應用程式內容和屬性<br/>將應用程式內容另存為模板<br/>發佈應用程式 |
| 優惠 | 核准優惠方案內容和資格<br/>停用線上優惠方案 |
| 任務 | 完成任務<br/>取消任務 |
| 行銷資源 | 核准資源<br/>鎖定和解除鎖定資源 |
| 行銷活動套件 | 提交套件以進行核准<br/>批准或拒絕包<br/>取消包 |
| 行銷活動訂單 | 建立訂單<br/>接受或拒絕訂單 |
| 庫存 | 刪除庫存行 |
| 優惠方案模擬 | 啟動和停止模擬 |
| 目標工作流程 | 啟動、暫停和停止工作流程 |
| 報告 | 在報表歷史記錄中儲存目前的資料 |
| 論壇 | 添加討論<br/>回復討論中的郵件<br/>按照討論結果取消訂閱 |

### 管理核准

目標或傳遞內容的核准可透過Web存取執行。

![](assets/web-access-approval.png)

您也可以使用通知訊息中包含的連結。 如需詳細資訊，請參閱[本章節](marketing-campaign-approval.md#checking-and-approving-deliveries)。


## 教學課程影片 {#video}

此影片說明如何建立行銷計畫、方案和行銷活動。

>[!VIDEO](https://video.tv.adobe.com/v/333810?quality=12)
