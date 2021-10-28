---
title: 促銷活動互動運算子
description: 建立優惠方案管理運算子
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: 7234ca65f785b005b11851a5cd88add8cddeff4f
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 1%

---

# 運算子設定檔 {#operator-profiles}

兩種運算子可以使用促銷活動互動： **優惠方案經理** 和 **傳送管理員**. 每個都有特定權限和限制。 進一步了解Campaign運算子和權限，位於 [本頁](../start/permissions.md).

* 此 **[!UICONTROL Offer manager]** 建立和維護選件。
* 此 **[!UICONTROL Delivery manager]** 核准和使用優惠方案

## 建立優惠方案管理員運算子{#offer-manager}

1. 建立運算子。

   ![](../assets/do-not-localize/book.png) 在Campaign中建立運算子的步驟在 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. 前往 **[!UICONTROL Groups and named rights]** 按一下 **[!UICONTROL Add]** ，然後選取 **[!UICONTROL Offer manager]** 群組。

指派給優惠方案管理員的權限可讓他們執行下列工作：

* 修改 **[!UICONTROL Design]** 環境。
* 檢視 **[!UICONTROL Live]** 環境。
* 配置管理函式（預定義空格和篩選器）。
* 建立和更改類別。
* 建立優惠方案。
* 設定優惠方案資格。
* 核准優惠方案。

如果在工作流程中使用選件，必須將運算子新增至 **[!UICONTROL Administrator]** 或 **[!UICONTROL Offer managers]** 運算元群組，以執行工作流程。

>[!NOTE]
>
>**優惠方案經理** 只有在未指定審核者，或在優惠方案範本中已宣告為審核者時，才能核准優惠方案。

## 建立傳送管理員運算子 {#delivery-manager}

1. 建立運算子。

   ![](../assets/do-not-localize/book.png) 在Campaign中建立運算子的步驟在 [Campaign Classicv7檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. 前往 **[!UICONTROL Groups and named rights]** 按一下 **[!UICONTROL Add]** ，然後選取 **[!UICONTROL Delivery manager]** 群組。

指派給傳送管理員的權限可讓他們執行下列工作：

* 顯示 **[!UICONTROL Live]** 環境。
* 顯示和修改優惠方案類別。
* 如果優惠方案是其審核者，請核准優惠方案。

   >[!NOTE]
   >
   >**傳送管理員** 只有在優惠方案設定中宣告為審核者時，才能核准優惠方案。

## 每個交互運算子的權限矩陣 {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>優惠方案管理員（設計環境）</strong><br /> </td> 
   <td> <strong>優惠方案管理員（即時環境）</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>樹結構級別</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 正在編輯的選件/即時選件<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 收件者 — 環境<br /> </td> 
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
   <td> 預先定義的選件篩選器<br /> </td> 
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
   <td> 選件類別<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>傳送管理器（設計環境）</strong><br /> </td> 
   <td> <strong>傳送管理器（即時環境）</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>樹結構級別</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 正在編輯的選件/即時選件<br /> </td> 
   <td> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
  <tr> 
   <td> 收件者 — 環境<br /> </td> 
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
   <td> 預先定義的選件篩選器<br /> </td> 
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
   <td> 選件類別<br /> </td> 
   <td> </td> 
   <td> 閱讀<br /> </td> 
  </tr> 
 </tbody> 
</table>
