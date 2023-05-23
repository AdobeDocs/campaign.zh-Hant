---
title: 運算子配置檔案
description: 建立優惠管理運算子
feature: Interaction, Offers
role: Data Engineer
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: eed3396584940f99a865eef2358887b6bf5c4936
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 8%

---

# 運算子配置檔案 {#operator-profiles}

兩種類型的運算子可以使用市場活動交互： **提供經理** 和 **交付經理**。 每個權限和限制都特定。 瞭解有關市場活動操作員和權限的詳細資訊 [此頁](../start/gs-permissions.md)。

* 的 **[!UICONTROL Offer manager]** 建立和維護優惠。
* 的 **[!UICONTROL Delivery manager]** 批准和使用優惠

## 建立聘用管理器運算子{#offer-manager}

1. 建立運算子。 [了解更多](../start/manage-permissions.md#add-users)
1. 瀏覽到 **[!UICONTROL Groups and named rights]** 窗口，按一下 **[!UICONTROL Add]** 的 **[!UICONTROL Offer manager]** 組。

描述了與聘用經理關聯的權限 [這裡](../start/manage-permissions.md#ootb-productprofiles)

## 建立交貨管理器運算子 {#delivery-manager}

1. 建立運算子。 [了解更多](../start/manage-permissions.md#add-users)
1. 瀏覽到 **[!UICONTROL Groups and named rights]** 按鈕 **[!UICONTROL Add]** 的 **[!UICONTROL Delivery manager]** 組。

分配給交付經理的權限使他們能夠執行以下任務：

* 顯示 **[!UICONTROL Live]** 環境。
* 顯示和修改優惠類別。
* 如果報價是其審核人，則批准報價。

   >[!NOTE]
   >
   >**交付經理** 僅當在聘用配置中將其聲明為審閱者時，才能批准聘用。

## 每個交互運算子的權限矩陣 {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>服務經理（設計環境）</strong><br /> </td> 
   <td> <strong>服務經理（即時環境）</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>樹結構級別</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 正在編輯的服務/即時服務<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 收件人 — 環境<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 管理<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 空格<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 預定義的服務篩選器<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 類型<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 類型規則<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 優惠方案目錄<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 優惠方案類別<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>交付管理器（設計環境）</strong><br /> </td> 
   <td> <strong>交付管理器(Live env.)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>樹結構級別</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 正在編輯的服務/即時服務<br /> </td> 
   <td> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 收件人 — 環境<br /> </td> 
   <td> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 管理<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 空格<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 預定義的服務篩選器<br /> </td> 
   <td> 閱讀<br /> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 類型<br /> </td> 
   <td> 閱讀<br /> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 類型規則<br /> </td> 
   <td> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 優惠方案目錄<br /> </td> 
   <td> 閱讀<br /> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 優惠方案類別<br /> </td> 
   <td> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
 </tbody> 
</table>
