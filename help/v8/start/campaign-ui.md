---
title: 發現活動工作區
description: 瞭解如何瀏覽和使用市場活動工作區
feature: Overview
role: Data Engineer
level: Beginner
exl-id: a7846b95-7570-4dce-b3f4-d3cc23eefcac
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 21%

---

# 發現市場活動用戶介面

## 訪問市場活動UI

Campaign 工作區可在[用戶端主控台](../architecture/general-architecture.md)提供。

瞭解如何在中安裝和配置市場活動客戶端控制台 [此部分](../start/connect.md)。

![](assets/home-page.png)

您還可以使用Web瀏覽器訪問市場活動。 在此上下文中，只有市場活動功能的子集可用。 [了解更多](#web-browser)

## 瀏覽UI

連接到「市場活動」後，即可訪問首頁。 瀏覽訪問權能的連結。 UI中可用的權能集取決於您的選項和權限。

從首頁的中心部分，使用連結訪問市場活動幫助資料、社區和支援網站。

使用上部分的頁籤瀏覽市場活動關鍵功能：

![](assets/overview-home.png)

>[!NOTE]
>
>您可以訪問的核心功能清單取決於您的權限和實施。

對於每種功能，您都可以訪問 **[!UICONTROL Browsing]** 的子菜單。 的 **[!UICONTROL More]** 連結允許您訪問所有其他元件。

例如，瀏覽到 **[!UICONTROL Profiles and targets]** 頁籤，您可以訪問收件人清單、訂閱服務、現有目標工作流以及建立所有這些元件的快捷方式。

![](assets/overview-list.png)

在螢幕中選擇元素時，它將載入到新頁籤中，以便您可以輕鬆瀏覽內容。

![](assets/new-tab.png)

## 建立元素 {#create-an-element}

在 **[!UICONTROL Create]** 的子菜單。 您還可以使用 **[!UICONTROL Create]** 按鈕，將新元素添加到當前清單中。

例如，在傳遞頁面上，使用 **[!UICONTROL Create]** 按鈕來建立新的傳遞。

![](assets/new-recipient.png)

## 使用Web瀏覽器 {#web-browser}

您還可以通過Web瀏覽器訪問市場活動功能的子集。

Web訪問介面與控制台介麵類似。 在瀏覽器中，您可以使用與控制台相同的導航和顯示功能，但只能對市場活動執行一組縮減的操作。 例如，您可以查看和取消市場活動，但不能修改市場活動。

![](../assets/do-not-localize/glass.png) [瞭解有關活動Web訪問的詳細資訊](../start/connect.md#web-access)。

## 訪問市場活動瀏覽器 {#ac-explorer-ui}

瀏覽市場活動瀏覽器以訪問所有Adobe Campaign功能和設定。

![](assets/explorer.png)

此工作區允許您訪問瀏覽器樹以瀏覽所有功能和選項。

左部分顯示「市場活動瀏覽器」樹，允許您根據您的權限瀏覽實例的所有元件和設定。

上部部分顯示當前資料夾中的記錄清單。 這些清單完全可自定義。 [了解更多](customize-ui.md)

下部部分顯示選定記錄的詳細資訊。


## 語言

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

語言影響日期和時間格式。


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
