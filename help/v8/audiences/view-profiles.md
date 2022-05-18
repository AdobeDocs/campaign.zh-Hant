---
title: 查看市場活動中的現有配置檔案
description: 瞭解如何在市場活動中訪問聯繫人資料
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 03f7a736-e0b9-4216-9550-507f10e6fcf6
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 16%

---

# 查看現有配置檔案{#view-profiles}

瀏覽到 **[!UICONTROL Profiles and targets]** 訪問儲存在Adobe Campaign資料庫中的收件人。

從此頁，您可以 [新建收件人](create-profiles.md)，編輯現有收件人並訪問其配置檔案詳細資訊。

![](assets/profiles-and-targets.png)

要處理更高級的配置檔案，請從 **[!UICONTROL Explorer]** 連結。

![](assets/recipients-in-explorer.png)


>[!CAUTION]
>
>內置的「收件人」螢幕是通過XML架構及其關聯表單定義的。 XML架構儲存在 **[!UICONTROL Administration > Configuration > Data schemas]** 的下界。 只有資深使用者可以變更這些結構描述。

## 編輯設定檔{#edit-a-profiles}

選擇配置檔案以在新頁籤中顯示詳細資訊。

![](assets/edit-a-profile.png)

用戶檔案相關的資料會被歸類在索引標籤中。這些頁籤及其內容取決於您的特定設定和已安裝的軟體包。

對於典型的內置收件人，您可以訪問以下頁籤：

* **[!UICONTROL General]**，用於所有常規配置檔案資料。 具體來說，它包含姓、名、電子郵件地址、電子郵件格式等。

   此頁籤還儲存 **選擇退出** 配置檔案的標誌：當 **[!UICONTROL No longer contact (by any channel)]** 選項，配置檔案在denylist上。 例如，如果收件人按一下了新聞簡報中的取消訂閱連結，則會將此資訊添加到聯繫資料中。 此類收件人不再是任何渠道（電子郵件、直郵等）的目標。 如需詳細資訊，請參閱[此頁面](../send/quarantines.md)。

* **聯繫資訊**，其中包含所選配置檔案的直接郵件地址。

   您可以在此螢幕中檢查地址的質量索引以及地址包含的錯誤數。 直接郵件提供商根據先前遞送過程中發現的錯誤數直接使用此資訊，無法手動更改。

* **其他**，用於可根據需要個性化和填充的特定欄位。

   使用 **[!UICONTROL Field properties…]** 上下文菜單，用於更改欄位的名稱並定義其格式。

   ![](assets/other-tab-field-properties.png)

   按如下方式輸入新設定：

   ![](assets/change-field-properties.png)

   在UI中檢查更新：

   ![](assets/other-tab-updated.png)


   >[!CAUTION]
   >更改適用於所有收件人。


* **訂閱**，用於所有服務的活動訂閱。 使用 **歷史** 頁籤，以訪問此聯繫人的訂閱和取消訂閱的詳細資訊。

   ![](assets/subscription-tab.png)

   瞭解有關訂閱的詳細資訊 [此部分](../start/subscriptions.md)。

* **交貨**，用於選定配置檔案的所有傳遞日誌。 使用此頁籤可訪問聯繫人的市場營銷歷史記錄：通過所有渠道發往配置檔案的所有傳遞操作的標籤、日期和狀態。


* **跟蹤**，用於選定配置檔案的所有跟蹤日誌。 此資訊用於追蹤歸檔用戶於傳遞後的活動。此索引標籤顯示在傳遞中追蹤的所有 URL 累積數目。清單是可配置的，通常包含：按一下的URL、按一下的日期和時間以及包含該URL的文檔

   瞭解有關跟蹤的更多資訊 [此部分](../start/tracking.md)。


## 使用中的設定檔案 {#active-profiles}

有效用戶檔案指的是可計費開立帳單的用戶檔案。

計費帳單僅會考慮&#x200B;**有效** 的用戶檔案。如果在過去 12 個月透過任何通路鎖定過用戶檔案或與其進行過通訊，那麼則該用戶檔案被視為有效。

已被多個交貨鎖定的配置檔案只計算一次。

活動配置檔案計數可用於 **市場營銷實例** 只是。 它不適用於執行實例，即MID（中間採購）和RT（消息中心/即時消息）實例。

>[!NOTE]
>
>您也可以直接從市場活動控制面板監視實例上有效配置檔案的數量。 有關詳細資訊，請參閱 [控制面板文檔](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html)。
