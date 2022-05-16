---
title: 運算子配置檔案
description: 建立優惠管理運算子
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 1%

---

# 運算子配置檔案 {#operator-profiles}

兩種類型的運算子可以使用市場活動交互： **提供經理** 和 **交付經理**。 每個權限和限制都特定。 瞭解有關市場活動操作員和權限的詳細資訊 [此頁](../start/permissions.md)。

* 的 **[!UICONTROL Offer manager]** 建立和維護優惠。
* 的 **[!UICONTROL Delivery manager]** 批准和使用優惠

## 建立聘用管理器運算子{#offer-manager}

1. 建立運算子。

   ![](../assets/do-not-localize/book.png) 在市場活動中建立操作員的步驟詳見 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. 轉到 **[!UICONTROL Groups and named rights]** 窗口，按一下 **[!UICONTROL Add]** 的 **[!UICONTROL Offer manager]** 組。

分配給聘用經理的權限使他們能夠執行以下任務：

* 修改 **[!UICONTROL Design]** 環境。
* 視圖 **[!UICONTROL Live]** 環境。
* 配置管理函式（預定義的空格和篩選器）。
* 建立和更改類別。
* 建立優惠。
* 配置優惠資格。
* 批准聘用。

如果在工作流中使用了聘用，則必須將操作員添加到 **[!UICONTROL Administrator]** 或 **[!UICONTROL Offer managers]** 執行工作流的運算子組。

>[!NOTE]
>
>**提供經理** 僅當未指定審閱者或在聘用模板中已將其聲明為審閱者時，才能批准聘用。

## 建立交貨管理器運算子 {#delivery-manager}

1. 建立運算子。

   ![](../assets/do-not-localize/book.png) 在市場活動中建立操作員的步驟詳見 [Campaign Classicv7文檔](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. 轉到 **[!UICONTROL Groups and named rights]** 窗口，按一下 **[!UICONTROL Add]** 的 **[!UICONTROL Delivery manager]** 組。

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
   <td> 類型學<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 類型規則<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 提供目錄<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 優惠類別<br /> </td> 
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
   <td> 類型學<br /> </td> 
   <td> 閱讀<br /> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 類型規則<br /> </td> 
   <td> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 提供目錄<br /> </td> 
   <td> 閱讀<br /> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 優惠類別<br /> </td> 
   <td> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
 </tbody> 
</table>
