---
title: 在Campaign中檢視現有設定檔
description: 了解如何在Campaign中存取連絡人資料
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 03f7a736-e0b9-4216-9550-507f10e6fcf6
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 16%

---

# 檢視現有設定檔{#view-profiles}

瀏覽至 **[!UICONTROL Profiles and targets]** 存取儲存在Adobe Campaign資料庫中的收件者。

從本頁，您可以 [建立新收件者](create-profiles.md)，編輯現有的收件者並存取其設定檔詳細資訊。

![](assets/profiles-and-targets.png)

如需進階設定檔操作，請從 **[!UICONTROL Explorer]** Adobe Campaign首頁上的連結。

![](assets/recipients-in-explorer.png)


>[!CAUTION]
>
>內建的收件者畫面是透過XML架構及其相關表單來定義。 XML架構儲存在 **[!UICONTROL Administration > Configuration > Data schemas]** Adobe Campaign資源管理器樹的節點。 只有資深使用者可以變更這些結構描述。

## 編輯設定檔{#edit-a-profiles}

選取設定檔以在新索引標籤中顯示詳細資料。

![](assets/edit-a-profile.png)

用戶檔案相關的資料會被歸類在索引標籤中。這些標籤及其內容取決於您的特定設定和已安裝的套件。

對於典型的內建收件者，您可以存取下列標籤：

* **[!UICONTROL General]**，以取得所有一般設定檔資料。 尤其包含姓氏、名字、電子郵件地址、電子郵件格式等。

   此索引標籤也會儲存 **選擇退出** 設定檔的旗標：當 **[!UICONTROL No longer contact (by any channel)]** 選項，則配置檔案位於封鎖清單中。 舉例來說，如果收件者按一下電子報中的取消訂閱連結，此資訊便會新增至聯絡資料。 此類收件者不再是任何通道（電子郵件、直接郵件等）上的目標。 如需詳細資訊，請參閱[此頁面](../send/quarantines.md)。

* **聯絡資訊**，包含所選設定檔的直接郵件地址。

   您可以在此螢幕中檢查地址的質量索引，以及地址包含的錯誤數。 直接郵件提供者會根據先前傳送期間發現的錯誤數直接使用此資訊，且無法手動變更。

* **其他**，以根據您的需求個人化和填入的特定欄位。

   使用 **[!UICONTROL Field properties…]** 內容功能表來變更欄位名稱並定義其格式。

   ![](assets/other-tab-field-properties.png)

   輸入新設定，如下所示：

   ![](assets/change-field-properties.png)

   在UI中檢查更新：

   ![](assets/other-tab-updated.png)


   >[!CAUTION]
   >變更會套用至所有收件者。


* **訂閱**，適用於所有服務的作用中訂閱。 使用 **歷史記錄** 頁簽以訪問此聯繫人的訂閱和取消訂閱的詳細資訊。

   ![](assets/subscription-tab.png)

   深入了解訂閱 [在本節](../start/subscriptions.md).

* **傳遞**，以取得所選設定檔的所有傳送記錄。 使用此索引標籤來存取連絡人的行銷記錄：透過所有管道傳送給設定檔的所有傳送動作的標籤、日期和狀態。


* **追蹤**，以取得所選設定檔的所有追蹤記錄。 此資訊用於追蹤歸檔用戶於傳遞後的活動。此索引標籤顯示在傳遞中追蹤的所有 URL 累積數目。清單是可設定的，通常包含：點按的URL、點按的日期和時間，以及包含URL的檔案

   進一步了解追蹤 [在本節](../start/tracking.md).


## 使用中的設定檔案 {#active-profiles}

有效用戶檔案指的是可計費開立帳單的用戶檔案。

計費帳單僅會考慮&#x200B;**有效** 的用戶檔案。如果在過去 12 個月透過任何通路鎖定過用戶檔案或與其進行過通訊，那麼則該用戶檔案被視為有效。

已由數個傳送定位的設定檔只會計算一次。

活動設定檔計數可用於 **行銷例項** 只有。 它不適用於執行例項，亦即MID（中間來源）和RT（訊息中心/即時訊息）例項。

>[!NOTE]
>
>您也可以直接從Campaign控制面板監控執行個體上作用中設定檔的數量。 有關詳細資訊，請參閱 [控制面板檔案](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
