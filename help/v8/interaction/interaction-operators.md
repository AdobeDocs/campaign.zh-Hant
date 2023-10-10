---
title: 運運算元設定檔
description: 建立優惠方案管理操作者
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 8%

---

# 運運算元設定檔 {#operator-profiles}

有兩種型別的運運算元可以使用Campaign互動： **優惠方案管理員** 和 **傳遞管理員**. 每一個都有特定的許可權和限制。 進一步瞭解Campaign運運算元和許可權，位於 [此頁面](../start/gs-permissions.md).

* 此 **[!UICONTROL Offer manager]** 建立和維護選件。
* 此 **[!UICONTROL Delivery manager]** 核准並使用優惠方案

## 建立優惠方案管理員運運算元{#offer-manager}

1. 建立運運算元。 [了解更多](../start/manage-permissions.md#add-users)
1. 瀏覽至 **[!UICONTROL Groups and named rights]** 視窗，按一下 **[!UICONTROL Add]** 並選取 **[!UICONTROL Offer manager]** 群組。

說明與優惠方案管理員相關的許可權 [此處](../start/manage-permissions.md#ootb-productprofiles)

## 建立傳遞管理員操作員 {#delivery-manager}

1. 建立運運算元。 [了解更多](../start/manage-permissions.md#add-users)
1. 瀏覽至 **[!UICONTROL Groups and named rights]** 標籤，按一下 **[!UICONTROL Add]** 並選取 **[!UICONTROL Delivery manager]** 群組。

指派給傳遞管理員的許可權可讓他們執行下列工作：

* 顯示 **[!UICONTROL Live]** 環境。
* 顯示和修改優惠方案類別。
* 如果優惠方案為稽核者，則核准優惠方案。

  >[!NOTE]
  >
  >**傳遞管理員** 只有在優惠方案設定中已宣告為檢閱者時，才能核准優惠方案。

## 每個互動運運算元的許可權矩陣 {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Offer Manager （設計環境）</strong><br /> </td> 
   <td> <strong>Offer Manager （即時環境）</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>樹狀結構層級</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 正在編輯的優惠/即時優惠<br /> </td> 
   <td> 讀取/寫入<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 收件者 — 環境<br /> </td> 
   <td> 讀取/寫入<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 管理<br /> </td> 
   <td> 讀取/寫入<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 空間<br /> </td> 
   <td> 讀取/寫入<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 預先定義的選件篩選器<br /> </td> 
   <td> 讀取/寫入<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 類型<br /> </td> 
   <td> 讀取/寫入<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 類型規則<br /> </td> 
   <td> 讀取/寫入<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 優惠方案目錄<br /> </td> 
   <td> 讀取/寫入<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 優惠方案類別<br /> </td> 
   <td> 讀取/寫入<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>傳遞管理員（設計環境）</strong><br /> </td> 
   <td> <strong>傳遞管理員（即時環境）</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>樹狀結構層級</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 正在編輯的優惠/即時優惠<br /> </td> 
   <td> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 收件者 — 環境<br /> </td> 
   <td> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 管理<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 空間<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 預先定義的選件篩選器<br /> </td> 
   <td> 讀取<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 類型<br /> </td> 
   <td> 讀取<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 類型規則<br /> </td> 
   <td> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 優惠方案目錄<br /> </td> 
   <td> 讀取<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 優惠方案類別<br /> </td> 
   <td> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
 </tbody> 
</table>
