---
title: 探索促銷活動工作區
description: 了解如何瀏覽及使用Campaign工作區
feature: Overview
role: Admin, Developer, User
level: Beginner
exl-id: a7846b95-7570-4dce-b3f4-d3cc23eefcac
source-git-commit: 2aa5dd736b93990317f842bcbe1f87374279f538
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 探索Campaign使用者介面

## 存取Campaign UI{#ui-access}

Campaign 工作區可在[用戶端主控台](../architecture/general-architecture.md)提供。

了解如何在 [本節](../start/connect.md).

![](assets/home-page.png)

您也可以使用網頁瀏覽器來存取Campaign。 在此情境中，僅有Campaign功能的子集可供使用。 [了解更多](#web-browser)

## 瀏覽UI{#ui-browse}

連線至Campaign後，即可存取首頁。 瀏覽連結以存取功能。 UI中可用的功能集取決於您的選項和權限。

從首頁的中央區段，使用連結來存取Campaign說明資料、社群和支援網站。

使用上方區段的標籤來瀏覽Campaign索引鍵功能：

![](assets/overview-home.png)

>[!NOTE]
>
>您可以存取的核心功能清單取決於您的權限和實作。

對於每個功能，您可以存取 **[!UICONTROL Browsing]** 區段。 此 **[!UICONTROL More]** 連結可讓您存取所有其他元件。

例如，瀏覽至 **[!UICONTROL Profiles and targets]** 索引標籤，您可以存取收件者清單、訂閱服務、現有目標工作流程，以及建立所有這些元件的捷徑。

![](assets/overview-list.png)

當您在畫面中選取元素時，元素會載入到新索引標籤中，以便您輕鬆瀏覽內容。

![](assets/new-tab.png)

## 建立元素 {#create-an-element}

在 **[!UICONTROL Create]** 區段以新增元素。 您也可以使用 **[!UICONTROL Create]** 按鈕，將新元素添加到當前清單。

例如，在傳遞頁面上，使用 **[!UICONTROL Create]** 按鈕來建立新的傳遞。

![](assets/new-recipient.png)

## 使用網頁瀏覽器 {#web-browser}

您也可以透過網頁瀏覽器存取Campaign功能的子集。

Web訪問介面與控制台介麵類似。 在瀏覽器中，您可以使用與主控台相同的導覽和顯示功能，但您只能對行銷活動執行精簡的動作集。 例如，您可以檢視和取消促銷活動，但無法修改促銷活動。

![](../assets/do-not-localize/glass.png) [深入了解Campaign網路存取](../start/connect.md#web-access).

## 存取Campaign Explorer {#ac-explorer-ui}

瀏覽Campaign Explorer以存取所有Adobe Campaign功能和設定。

![](assets/explorer.png)

此工作區允許您訪問資源管理器樹以瀏覽所有功能和選項。

左側區段顯示「促銷活動總管」樹狀結構，並可讓您根據您的權限，瀏覽執行個體的所有元件和設定。

上部部分顯示當前資料夾中的記錄清單。 這些清單可完全自訂。 [了解更多](../config/ui-settings.md)

下部顯示所選記錄的詳細資訊。

## 語言{#languages}

Campaign v8 使用者介面提供下列語言版本：

* 英文 (英國)
* 英文 (美國)
* 法文
* 德文
* 日文

在安裝過程中選擇語言。

>[!CAUTION]
>
>建立執行個體後無法變更語言。

語言會影響日期和時間格式。

英文 (US) 和英文 (EN) 的主要差異如下：

<table> 
 <thead> 
  <tr> 
   <th> 格式<br /> </th> 
   <th> 英文 (美國)<br /> </th> 
   <th> 英文 (EN)<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 日期<br /> </td> 
   <td> 週開始於星期日<br /> </td> 
   <td> 週開始於星期一<br /> </td> 
  </tr> 
  <tr> 
   <td> 簡短日期<br /> </td> 
   <td> <p>%2M/%2D/%4Y</p><p><strong>範例：09/25/2018</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y</p><p><strong>範例：25/09/2018</strong></p> </td> 
  </tr> 
  <tr> 
   <td> 帶時間的簡短日期<br /> </td> 
   <td> <p>%2M/%2D/%4Y %I:%2N:%2S %P</p><p><strong>例如：09/25/2018 10:47:25 PM</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y %2H:%2N:%2S</p><p><strong>例如：25/09/2018 22:47:25</strong></p> </td> 
  </tr> 
 </tbody> 
</table>
