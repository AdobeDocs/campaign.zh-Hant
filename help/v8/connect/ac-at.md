---
title: 合作使用Campaign與Adobe Target
description: 瞭解如何使用Campaign和Adobe Target
feature: Target Integration
role: Admin, User
level: Beginner, Intermediate
exl-id: 891a9a87-f3a4-405a-87ed-a7703be90a67
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '970'
ht-degree: 0%

---

# 合作使用Campaign與Adobe Target

連結Campaign和Target，在Adobe Campaign電子郵件傳遞中加入Adobe Target的選件。

此整合可協助您實作如下的使用案例：收件者開啟透過Adobe Campaign傳送的電子郵件時，呼叫Adobe Target可讓您顯示內容的動態版本。 此動態版本是根據建立電子郵件時預先指定的規則計算。

>[!NOTE]
>* 整合僅支援靜態影像。 其他型別的內容無法個人化。
>
>* 作為Managed Cloud Service使用者，[連絡Adobe](../start/campaign-faq.md#support)以透過Campaign實作Experience Cloud觸發程式。

Adobe Target可使用下列型別的資料：

* Adobe Campaign資料庫的資料
* 連結至Adobe Target中的訪客ID的區段，前提是使用的資料不受法律限制
* Adobe Target資料：使用者代理、IP位址、地理本地化資料

## 插入動態內容

在下列範例中，您將瞭解如何將Adobe Target中的&#x200B;**動態優惠方案**&#x200B;整合到Adobe Campaign電子郵件中。

我們想要使用會根據收件者國家/地區動態變更的影像來建立訊息。 資料會隨每個mbox要求傳送，視訪客的IP位址而定。

在此電子郵件中，我們希望其中一個影像能根據下列使用者體驗動態變化：

* 電子郵件已在法國開啟。
* 此電子郵件在美國已開啟。
* 如果這些條件都不適用，則會顯示預設影像。

![](assets/target_4.png)

您需要在Adobe Campaign和Adobe Target中完成以下步驟：

1. [在電子郵件中插入動態優惠方案](#inserting-dynamic-offer)
1. [建立重新導向選件](#create-redirect-offers)
1. [建立客群](#audiences-target)
1. [建立體驗鎖定目標活動](#creating-targeting-activity)
1. [預覽和傳送訊息](#preview-send-email)

### 在電子郵件中插入動態優惠方案 {#inserting-dynamic-offer}

在Adobe Campaign中，定義電子郵件的目標和內容。 您可以從Adobe Target插入動態影像。

若要這麼做，請指定預設影像的URL、位置名稱，以及您要傳輸至Adobe Target的欄位。

在Adobe Campaign中，有兩種方式可將Target的動態影像插入電子郵件中：

* 如果您使用數位內容編輯器，請選擇現有影像，然後從工具列選取&#x200B;**[!UICONTROL Insert]** > **[!UICONTROL Dynamic image served by Adobe Target]**。

  ![](assets/target_5.png)

* 如果您使用標準編輯器，請將游標置於您要插入影像的位置，然後從個人化下拉式選單中選取&#x200B;**[!UICONTROL Include]** > **[!UICONTROL Dynamic image served by Adobe Target...]**。

  ![](assets/target_12.png)

然後您可以定義影像引數：

* **[!UICONTROL Default image]**&#x200B;的URL為不符合任何條件時所顯示的影像。 您也可以從Assets資料庫中選取影像。
* **[!UICONTROL Target location]**&#x200B;是動態選件位置的名稱。 您必須在Adobe Target活動中選取此位置。
* **[!UICONTROL Landing Page]**&#x200B;可讓您將預設影像重新導向至預設登陸頁面。 此URL只適用於最終電子郵件中顯示預設影像時。 這是選擇性的。
* **[!UICONTROL Additional decision parameters]**&#x200B;定義了Adobe Target區段中所定義欄位與Adobe Campaign欄位之間的對應。 使用的Adobe Campaign欄位必須在rawbox中指定。 在我們的範例中，已新增「國家/地區」欄位。

如果您在Adobe Target的設定中使用企業許可權，請在此欄位中新增對應的屬性。 在[Adobe Target檔案](https://experienceleague.adobe.com/zh-hant/docs/target/using/administer/manage-users/enterprise/properties-overview#administer){target="_blank"}中進一步瞭解Target企業許可權。

![](assets/target_13.png)

### 建立重新導向選件 {#create-redirect-offers}

在Adobe Target中，您可以建立不同版本的選件。 根據每位使用者體驗，您可以建立重新導向選件，並指定要顯示的影像。

在我們的案例中，我們需要兩個重新導向選件，第三個選件（預設值）將在Adobe Campaign中定義。

1. 若要在Target Standard中建立新的重新導向選件，請從&#x200B;**[!UICONTROL Content]**&#x200B;索引標籤，按一下&#x200B;**[!UICONTROL Code offers]**。

1. 按一下 **[!UICONTROL Create]**，之後 **[!UICONTROL Redirect Offer]**。

   ![](assets/target_9.png)

1. 輸入選件的名稱和影像的URL。

   ![](assets/target_6.png)

1. 對其餘的重新導向選件遵循相同程式。 如需詳細資訊，請參閱此[Adobe Target檔案](https://experienceleague.adobe.com/docs/target/using/experiences/offers/offer-redirect.html?lang=zh-Hant#experiences){target="_blank"}。

### 建立客群 {#audiences-target}

在Adobe Target中，您需要建立兩個受眾，造訪您選件的人員將針對不同的內容進行分類。 針對每個對象，新增規則以定義能夠檢視選件的對象。

1. 若要在Target中建立新的對象，請從&#x200B;**[!UICONTROL Audiences]**&#x200B;索引標籤，按一下&#x200B;**[!UICONTROL Create Audience]**。

   ![](assets/audiences_1.png)

1. 新增名稱至您的對象。

   ![](assets/audiences_2.png)

1. 按一下&#x200B;**[!UICONTROL Add a rule]**&#x200B;並選取類別。 規則會使用特定條件來鎖定訪客。 您可以新增條件或在其他類別中建立新規則來調整規則。

1. 對其餘對象執行相同的程式。

### 建立體驗鎖定目標活動 {#creating-targeting-activity}

在Adobe Target中，我們需要建立體驗鎖定目標活動、定義不同體驗，並將它們與對應的選件建立關聯。

首先，您必須定義對象：

1. 若要建立體驗鎖定目標活動，請從&#x200B;**[!UICONTROL Activities]**&#x200B;索引標籤，按一下&#x200B;**[!UICONTROL Create Activity]**&#x200B;然後&#x200B;**[!UICONTROL Experience Targeting]**。

   ![](assets/target_10.png)

1. 選取&#x200B;**[!UICONTROL Form]**&#x200B;作為&#x200B;**[!UICONTROL Experience Composer]**。

1. 按一下&#x200B;**[!UICONTROL Change audience]**&#x200B;按鈕以選擇對象。

   ![](assets/target_10_2.png)

1. 選取在先前步驟中建立的對象。

   ![](assets/target_10_3.png)

1. 按一下&#x200B;**[!UICONTROL Add Experience Targeting]**&#x200B;以建立另一個體驗。

然後為每個對象新增內容：

1. 選取您在Adobe Campaign中插入動態選件時選擇的位置名稱。

   ![](assets/target_15.png)

1. 按一下下拉式按鈕並選取&#x200B;**[!UICONTROL Change Redirect Offer]**。

   ![](assets/target_content.png)

1. 選取您先前建立的重新導向選件。

   ![](assets/target_content_2.png)

1. 對第二個體驗執行相同的步驟。

**[!UICONTROL Target]**&#x200B;視窗會摘要列出您的活動。 如有需要，您可以新增其他體驗。

![](assets/target_experience.png)

**[!UICONTROL Goal & Settings]**&#x200B;視窗可讓您設定優先順序、目標或持續時間，以個人化您的活動。

**[!UICONTROL Reporting Settings]**&#x200B;區段可讓您選取動作並編輯將決定何時達成目標的引數。

![](assets/target_experience_2.png)

## 預覽和傳送訊息 {#preview-send-email}

在Adobe Campaign中，您現在可以預覽電子郵件，並測試其對不同收件者的轉譯。

您會發現影像會根據建立的不同體驗而變更。

您現在已準備好傳送包含Target動態優惠方案的電子郵件。

![](assets/target_20.png)
