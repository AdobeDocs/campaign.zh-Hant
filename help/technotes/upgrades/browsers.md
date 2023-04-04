---
product: campaign
title: Chrome Firefox和Edge瀏覽器中的Campaign網頁元件和100版
description: Chrome、Firefox和Edge瀏覽器中的Campaign網頁元件和100版
exl-id: 912ad71e-2b23-4b16-b5f9-47d547fc83d5
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 0%

---

# 3位數的瀏覽器版本對Campaign Web元件的影響 {#version-100}

Google和Mozilla警告，Chrome和Firefox可能會因為某些網站即將推出的3位數版本而破壞其內容。

Chrome v100已設為在 **2022年3月29日**，和Firefox v100 on **2022年5月3日**.

Microsoft於2022年3月早些時候發行Edge v100。

版本號碼從2位變更為3位，可能會在造訪未準備好進行此變更的網站時造成一些問題。 某些網頁可能會停止在這些新瀏覽器版本中正確顯示。

主要網站的相容性已提前測試。 如果在發佈這些版本之前無法修復的站點問題，則公司有備份計畫可以確保站點不受影響。

網站上的潛在問題或功能喪失源自瀏覽器傳送至您正在造訪之網站的使用者代理字串：使用者代理是瀏覽器傳送至網站的字串，讓網站知道您使用的瀏覽器和版本，以及相關技術。 當您的瀏覽器傳送要求至網站時，它會先以使用者代理字串來識別自己，再擷取您要求的內容。 使用者代理字串中的資料可協助網站以適合您瀏覽器的格式傳送內容。 使用者代理的版本會隨瀏覽器版本號碼而增加。 從2位移至3位可能會造成問題。

## 您有受到影響嗎？{#version-100-impact}

Adobe建議您測試您的Campaign網頁應用程式，包括網頁表單和調查，以確保這些應用程式仍可與這些新瀏覽器版本搭配運作。

此建議適用於所有Web應用程式，尤其是當您已包含JavaScript程式碼時。

您必須檢查所有瀏覽器、行動裝置和案頭。

## 如何測試？{#version-100-test}

您可以設定瀏覽器，立即將版本報告為100，然後報告並修正您遇到的任何問題。

透過這些設定，瀏覽器會將新的使用者代理字串傳送至網站，指出瀏覽器為v100。 如果您的網路表單發生任何問題，應為瀏覽器編輯器建立錯誤。 請考慮在這些更新全面推出之前，先重新建立這些網路表單。

### 使用Firefox 100進行測試{#test-firefox-100}

若要使用Mozilla Firefox 100測試您的網頁，您可以手動變更使用者代理字串，以模擬即將在您的網頁應用程式上進行的使用者代理變更。

1. 開啟Firefox，輸入 `about:config` 在地址欄中，然後按enter鍵。
1. 搜尋 `general.useragent.override`.
1. 選取「字串」，然後按一下加號(+)。

   ![](assets/force-user-agent-firefox.png)

1. 在欄位中輸入下列文字：

   ```
   Mozilla/5.0 (Windows NT 10.0; rv:100.0) Gecko/20100101 Firefox/100.0
   ```

1. 按一下藍色核取記號按鈕以儲存設定。
1. 關閉並重新啟動瀏覽器。

若要將您的使用者代理變回預設值，只需回到 `about:config` 和搜索 `general.useragent.override` 中。  出現此設定時，按一下垃圾桶圖示以刪除設定，然後重新啟動瀏覽器。

### 使用Chrome 100進行測試{#test-chrome-100}

若要在您自己的網頁應用程式上測試Google Chrome 100使用者代理程式，您可以使用下列步驟來啟用此測試：

1. 開啟Chrome，輸入 `chrome://flags` 在地址欄中，然後按enter鍵。
1. 搜尋 `Force major version to 100 in User-Agent` 在搜尋欄位中，並啟用，如下所示。

   ![](assets/force-user-agent-chrome.png)

1. 重新啟動瀏覽器。
1. 關閉 `chrome://flags` 標籤。

若要將使用者代理變回預設值，只需依照此程式操作，並將標幟的設定變更為 `Default` 然後重新啟動瀏覽器。


### 使用Microsoft Edge 100進行測試{#test-ms-edge-100}

從v97開始，網站擁有者可以啟用實驗標幟來模擬此版本  `#force-major-version-to-100` in `edge://flags`.

1. 開啟Microsoft Edge，輸入 `edge://flags` 在地址欄中，然後按enter鍵。
1. 搜尋 `force-major-version-to-100` 欄位，並啟用它，如下所示。

   ![](assets/force-user-agent-edge.png)

1. 重新啟動瀏覽器。
1. 關閉 `edge://flags` 標籤。

若要將使用者代理變回預設值，只需依照此程式操作，並將標幟的設定變更為 `Default` 然後重新啟動瀏覽器。
