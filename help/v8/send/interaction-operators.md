---
solution: Campaign
product: Adobe Campaign
title: 促銷活動互動運算子
description: 建立選件管理運算子
feature: 概覽
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: b9de052de5aaeee4b089feb70bf20723be5c9cfa
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 1%

---


# 運算子描述檔{#operator-profiles}

兩種運算子可使用促銷活動互動：**選件管理員**&#x200B;和&#x200B;**遞送管理員**。 每一個都有特定的權限和限制。 進一步瞭解[本頁](../start/permissions.md)中的促銷活動運算子和權限。

* **[!UICONTROL Offer manager]**&#x200B;會建立並維護選件。
* **[!UICONTROL Delivery manager]**&#x200B;核准並使用選件

## 建立選件管理員運算元{#offer-manager}

1. 建立新運算子。

:arrow_upper_right:在促銷活動中建立運算子的步驟詳見[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. 轉至&#x200B;**[!UICONTROL Groups and named rights]**&#x200B;窗口，按一下&#x200B;**[!UICONTROL Add]**&#x200B;並選擇&#x200B;**[!UICONTROL Offer manager]**&#x200B;組。

指派給選件管理員的權限可讓他們執行下列工作：

* 修改&#x200B;**[!UICONTROL Design]**&#x200B;環境。
* 查看&#x200B;**[!UICONTROL Live]**&#x200B;環境。
* 設定管理函式（預先定義的空格和篩選器）。
* 建立和變更類別。
* 建立選件。
* 設定優惠資格。
* 核准選件。

請注意，如果選件用於工作流程中，則必須將運算元新增至&#x200B;**[!UICONTROL Administrator]**&#x200B;或&#x200B;**[!UICONTROL Offer managers]**&#x200B;運算元群組，以執行工作流程。

>[!NOTE]
>
>**選件管理員**&#x200B;只有在未指定審核者，或在選件所依據的選件範本中宣告其為審核者時，才能核准選件。

## 建立傳送管理員運算子{#delivery-manager}

1. 建立新運算子。

:arrow_upper_right:在促銷活動中建立運算子的步驟詳見[Campaign Classic檔案](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. 轉至&#x200B;**[!UICONTROL Groups and named rights]**&#x200B;窗口，按一下&#x200B;**[!UICONTROL Add]**&#x200B;並選擇&#x200B;**[!UICONTROL Delivery manager]**&#x200B;組。

分配給「交付管理器」的權限可／使其執行以下任務：

* 顯示&#x200B;**[!UICONTROL Live]**&#x200B;環境。
* 顯示和修改選件類別。
* 如果指定選件為其審核者之一，請核准選件。

   >[!NOTE]
   >
   >**傳送管理員**&#x200B;只有在選件設定期間宣告其為審核者時，才能核准選件。

## 每個Interaction運算子的權限矩陣{#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>選件管理員（設計環境）</strong><br /> </td> 
   <td> <strong>選件管理器（即時環境）</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>樹結構層</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 正在編輯的選件／即時選件<br /> </td> 
   <td> 讀／寫<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 收件人——環境<br /> </td> 
   <td> 讀／寫<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 管理員<br /> </td> 
   <td> 讀／寫<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 空格<br /> </td> 
   <td> 讀／寫<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 預先定義的選件篩選器<br /> </td> 
   <td> 讀／寫<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 類型學<br /> </td> 
   <td> 讀／寫<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 類型規則<br /> </td> 
   <td> 讀／寫<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 選件目錄<br /> </td> 
   <td> 讀／寫<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 選件類別<br /> </td> 
   <td> 讀／寫<br /> </td> 
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
   <td> <strong>樹結構層</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 正在編輯的選件／即時選件<br /> </td> 
   <td> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 收件人——環境<br /> </td> 
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
   <td> 類型學<br /> </td> 
   <td> 讀取<br /> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 類型規則<br /> </td> 
   <td> </td> 
   <td> 讀取<br /> </td> 
  </tr> 
  <tr> 
   <td> 選件目錄<br /> </td> 
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
