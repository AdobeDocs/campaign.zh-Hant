---
product: Adobe Campaign
title: 促銷活動互動運算子
description: 建立優惠方案管理運算子
feature: 概覽
role: Data Engineer
level: Beginner
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 1%

---


# 運算子配置式{#operator-profiles}

兩種運算子可以使用促銷活動互動：**選件管理員**&#x200B;和&#x200B;**傳送管理員**。 每個都有特定權限和限制。 在[本頁面](../start/permissions.md)中深入了解Campaign運算子和權限。

* **[!UICONTROL Offer manager]**&#x200B;會建立並維護選件。
* **[!UICONTROL Delivery manager]**&#x200B;核准並使用優惠方案

## 建立優惠方案管理員運算子{#offer-manager}

1. 建立新運算子。

   [!DNL :arrow_upper_right:] 在Campaign v7檔案中詳細說明建立運 [算子的步驟](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. 轉至&#x200B;**[!UICONTROL Groups and named rights]**&#x200B;窗口，按一下&#x200B;**[!UICONTROL Add]**&#x200B;並選擇&#x200B;**[!UICONTROL Offer manager]**&#x200B;組。

指派給優惠方案管理員的權限可讓他們執行下列工作：

* 修改&#x200B;**[!UICONTROL Design]**&#x200B;環境。
* 查看&#x200B;**[!UICONTROL Live]**&#x200B;環境。
* 配置管理函式（預定義的空格和篩選器）。
* 建立和更改類別。
* 建立優惠方案。
* 設定優惠方案資格。
* 核准優惠方案。

請注意，如果工作流中使用選件，則必須將運算子新增至&#x200B;**[!UICONTROL Administrator]**&#x200B;或&#x200B;**[!UICONTROL Offer managers]**&#x200B;運算子群組，才能執行工作流。

>[!NOTE]
>
>**優惠方案管理員**&#x200B;只有在未指定審核者，或在優惠方案所依據的優惠方案範本中已宣告其為審核者時，才能核准優惠方案。

## 建立傳遞管理器運算子{#delivery-manager}

1. 建立新運算子。

   [!DNL :arrow_upper_right:] 在Campaign v7檔案中詳細說明建立運 [算子的步驟](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. 轉至&#x200B;**[!UICONTROL Groups and named rights]**&#x200B;窗口，按一下&#x200B;**[!UICONTROL Add]**&#x200B;並選擇&#x200B;**[!UICONTROL Delivery manager]**&#x200B;組。

指派給傳送管理員的權限是/讓他們執行下列工作：

* 顯示&#x200B;**[!UICONTROL Live]**&#x200B;環境。
* 顯示和修改優惠方案類別。
* 如果指定其審核者之一，則核准優惠方案。

   >[!NOTE]
   >
   >**傳遞管理員**&#x200B;只有在優惠方案設定期間宣告其為審核者時，才能核准優惠方案。

## 每個交互運算子的權限矩陣{#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>選件管理器（設計環境）</strong><br /> </td> 
   <td> <strong>選件管理器（即時環境）</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>樹結構級別</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 正在編輯的選件/即時選件<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 收件者 — 環境<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 管理員<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 空格<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 預先定義的選件篩選器<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 類型<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 類型規則<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 優惠方案目錄<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 選件類別<br /> </td> 
   <td> 讀/寫<br /> </td> 
   <td> 讀取<br /> </td> 
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
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 收件者 — 環境<br /> </td> 
   <td> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 管理員<br /> </td> 
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
   <td> 選件類別<br /> </td> 
   <td> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
 </tbody> 
</table>
